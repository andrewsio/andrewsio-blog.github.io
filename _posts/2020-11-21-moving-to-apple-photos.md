---
title:  "Moving from Google Photos to Apple Photos"
date:   2020-11-21
layout: post
categories: blog
tags: software apple google photos mac
location: "Upnor, Kent, UK"
---

A while back I moved all my photos from Google Photos to Apple Photos. It was a massive pain, because Google Takeout doesn't give you your photos in a very sensible way. If you have custom albums, photos are exported in the 'date' directories and then also exported in the 'custom' album directories - so you either need to ignore the custom albums or check for duplicates. Also, some files will retain their exif data (date/time, GPS, etc) but not all, those that don't google will have moved it to a .json file of the same name - which Apple doesn't read. I also found a bunch of files that where the exif data was just broken but could be repaired.

Here's a very simple overview of the steps that I took, to get my pictures into Apple. I've omitted some of the obvious steps, so engage brain before following this. All commands were run on my mac, locally - If you're using Apple photos and you're not on a Mac, you're going to have a bad time.

The first step is of course to actually get your data out of Google, you can ask for it in whatever size files you want. I picked 10Gb and so over a period of time downloaded each one. If you have a lot of photos/videos in Google then you're going to need to manage your storage on your mac carefully. Ideally, you want to run these commands and manage the import of files while they are located on the on-board SSD storage (unless you have a fast SSD external drive), running these commands while the files are on a slow disk drive will take a long-ass-time, but is certainly possible.

Once you've got your files downloaded and stored, extract everything. I found storing in folders by year worked best so I could manage the import in batches. Go ahead and do some folder house keeping to get that ready. If you see there are folders with friendly album names my experience shows that the files in here will also be in the dated folders too, so worry about the dated folders for the time being. You can always check back later and make sure you've got everything.

When you're ready to tackle your first batch, you can optionally choose to get rid of any edited images and duplicates. I had very few edited images, and those that I did have, weren't edited very well or were an artefact of Google's self-editing processes.  

## Delete all edited images to reduce duplicates.
The below command is quite aggressive, it'll delete anything with 'edited' in the name.
Once that's complete I use a software package called [Gemini2](https://macpaw.com/gemini) to check for duplicated files in the directory, this is a fantastic tool and not only does it check for exact duplicates it also checks for similar pictures. You can review these or delete them, I was aggressive and just deleted anything that was similar. It's best to run Gemini2 now, as you can run it against a specific directory, once you've imported to Apple Photos you can only run it against your whole library. If you run it now, you're also going to avoid Apple uploading potential duplicates to iCloud.

{% highlight shell %}
find ./ -name “*edited*” -type f -delete
{% endhighlight %}
You can then run the Gemini2 app against your directory.

## List number of file types per extension
This command will simply list the number of files and file types in each directory. If you have a lot of movie files, you can optionally move these elsewhere to speed up processing and help manage disk space - I did this, because I had tons of crappy videos. Take a note of the this output for later, it's helpful to just keep tabs on how many files you're processing.

{% highlight shell %}
find . -type f | perl -ne 'print $1 if m/\.([^.\/]+)$/' | sort | uniq -c | sort -n
{% endhighlight %}

## Check which files are missing data or are damaged
This command which you should run in the directory of your files will recursively check through the directory and add a line in a CSV with the date/time fields from the exif data of the image (not from the json) and the filename. It's set to ignore the DS_Store and json files so that they don't show up in the CSV. You could instead specify the image file types, although I found I had a bunch of random file types which were all images.

{% highlight shell %}
exiftool -DateTimeOriginal --ext json --ext DS_Store -r -csv ./ > out.csv
{% endhighlight %}

Once you've done that you can read the CSV and see how many files are broken and how many have got the right information. I found that about 10% of my images were broken.  

## Filter Broken Images
I used the sort functions in Excel to list only those files which didn't have date/time populated. I then copied the list of course files and stored in a text file called missing. You can create the file using Vi or Nano (as below) and then simply paste from Excel and save. I stored this file in the root of the batch's director alongside the CSV file (which you don't need to save).

{% highlight shell %}
vi missing.txt
{% endhighlight %}

## Prepare for Json shenanigans
The objective here is to repopulate the missing data for the broken files by extracting it from the file's json file. Not every file will have a json file, but most should. First we need to get a list of the json files. The below command duplicates the file we just created.

{% highlight shell %}
cp missing.txt missingjson.txt
{% endhighlight %}

Once that's done you can open the new file in Vi and using a snazzy command you can append .json to each line in the file.

{% highlight shell %}
vi missingjson.txt
{% endhighlight %}

Run this once you're in Vi:

{% highlight shell %}
%s/$/.json/
{% endhighlight %}

## Separate broken and non-broken files.
We'll create a new directory called broken and move all of the files which we've identified as broken to it. Once done, we'll also move all of the json files too. You're going to see some errors here because not all of the files will have an associated json file. You can make a note if you want. Some files may have trailing spaces and they won't move, so you can move these manually.

{% highlight shell %}
mkdir broken/
cat missing.txt | xargs -I % mv % broken/
cat missingjson.txt | xargs -I % mv % broken/
{% endhighlight %}

Now that we've done that we have a folder full of files that look like they're missing data. We can then begin to repair the data or fix it using the below commands.

## Repair the exif data in the files
This command is designed to fix corruption in exif data. You can read about it [here](https://exiftool.org/faq.html), point 20b. We're going to run this against all the files in the 'broken' directory. You're going to see some errors here but I saw good success in it fixing exif for a number of files.

{% highlight shell %}
exiftool -all= -tagsfromfile @ -all:all -unsafe -icc_profile ./broken/
{% endhighlight %}

## Fix GPS and Date
If that didn't work, hopefully we can restore from the json file. This command will read the file's json file and then restore to the files exif. It will overwrite the files when it does this. There are lots of fields in the json, I was only interested in data/time and GPS coordinates.

{% highlight shell %}
exiftool -r -d %s -tagsfromfile '%d/%F.json' '-GPSAltitude<GeoDataAltitude' '-GPSLatitude<GeoDataLatitude' '-GPSLatitudeRef<GeoDataLatitude' '-GPSLongitude<GeoDataLongitude' '-GPSLongitudeRef<GeoDataLongitude' '-DateTimeOriginal<PhotoTakenTimeTimestamp' -overwrite_original broken/
{% endhighlight %}

This won't work for all files. But we've done our best at this point.

## Check back over if you need.
You can use the earlier command to see how many files you've fixed the date for if you want, although you may be able to gauge from the CLI.

## Import to Apple Photos
When I importing into Photos import all pictures directly into an album (e.g. year_imported), this allow you to create a separate smart album filter against your specific import batch. Once you've imported you can use a smart album to see any photos which have a captured date before or after my selected year. If you don’t import to an album, it’s not possible to filter on 'recently imported' in the same way (date added variable is limited to the last 1 day, so you can’t differentiate multiple imports on the same day)

Once done, you can select all images/videos with incorrect date and manually set the date to something within that year (e.g. 1/1/year) to avoid photos showing up in completely the wrong place. You can do this in apple by selecting all photos.

## Repeat for each batch
This is a long winded process and is almost certainly not the most efficient way of doing this, but it seemed to work for me. Apologies if I haven't attributed anyone for the commands, I did this about 9 months ago and wrote this based on the notes I took at the time. I do however remember trying to piece things together and certainly didn't find a comprehensive guide on this.

If this helped, send me a [tweet](https://twitter.com/14zz4) ✌️
