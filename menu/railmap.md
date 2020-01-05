---
layout: page
title: The Rail Map
---

I don't claim to be a train nut, but I certainly do enjoy travelling by rail - a pet project of many years, the below map highlights in green the major railway lines which I have travelled on in the UK. Most travel has been for pleasure but some trips have been for work too, a passion that has allowed me to observe the wonderful corners of our country. 

A particular favourite route is Fort William to Mallaig on the Mallaig Extension Railway, the journey takes passengers over the famous Glenfinnan Viaduct. The line from London Paddington to Penzance is too very special, providing a link to family in the west country; many hours have been spent travelling, in many different levels of comfort. 

<div id="openseadragon1" style="width: 100%"></div>


<script src="/assets/maps/openseadragon.min.js"></script>

<div id="travelmap" style="width: 100%; height: 1500px;"></div>
<script type="text/javascript">
    OpenSeadragon({
        id:            "travelmap",
        defaultZoomLevel: 	2,
        visibilityRatio: 1.0,
        tileSources:   {
            type: 'image',
            url:  '/assets/img/import/4872c-rail_map.png'
        }
    });
</script>
<noscript>
    <p>OpenSeadragon is not available unless JavaScript is enabled.</p>
    <img src='/assets/img/import/4872c-rail_map.png'
         />
</noscript>

_The image above and linked document/image are copyright to National Rail and are hosted here for my own personal non-commercial purposes. My website generates no profit and I do not claim ownership. Originally sourced from:_ [here][2]


[1]: https://s3-eu-west-1.amazonaws.com/14zz4-cdn/Master_Transit_Map.pdf
[2]: http://www.nationalrail.co.uk/stations_destinations/maps.aspx
[photo-1]: /assets/img/import/4872c-rail_map.png
