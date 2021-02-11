## index.js

let map;

function initMap() {
  map = new google.maps.Map(document.getElementById("map"), {
    center: { lat: -34.397, lng: 150.644 },
    zoom: 8,
  });
}

// создает объект (?) google.maps.Map в элементе с айди #map 

<!-- 
Map(mapDiv[, opts])
Parameters: 
mapDiv:  Element
opts:  MapOptions optional
Creates a new map inside of the given HTML container, which is typically a DIV element. 
-->


To load the Maps JavaScript API inline in an HTML file, add a script tag as show below.

<script defer
    src="https://maps.googleapis.com/maps/api/js?key=YOUR_API_KEY&callback=initMap">
</script>

src: The URL where the Maps JavaScript API is loaded from, including all of the symbols and definitions you need for using the Maps JavaScript API. The URL in this example has two parameters: key, where you provide your API key, and callback, where you specify the name of a global function to be called once the Maps JavaScript API loads completely. Read more about URL parameters.

defer: Asks the browser to parse the HTML document first before loading the script. When the script is executed, it will call the function specified using the callback parameter.

https://developers.google.com/maps/documentation/javascript/reference/map#MapOptions


## google.maps.MapOptions interface

MapOptions object used to define the properties that can be set on a Map.

## Properties:

backgroundColor
**center**
heading 
mapTypeId
minZoom 
maxZoom 
**zoom**

etc.

получилось вставить карту через iframe, скопипастив код в Widget Code в редимаге

<iframe
  width="600"
  height="450"
  frameborder="0" style="border:0"
  src="https://www.google.com/maps/embed/v1/place?key=API_KEY
    &q=Space+Needle,Seattle+WA" allowfullscreen>
</iframe>

  <!-- <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3254.424564870511!2d37.99093832823089!3d55.91965545651473!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x46b52d2823321799%3A0xce2927e41ce8b54e!2z0YPQuy4g0JrQvtC80LDRgNC-0LLQsCwgMSwg0KnRkdC70LrQvtCy0L4sINCc0L7RgdC60L7QstGB0LrQsNGPINC-0LHQuy4sIDE0MTEwMA!5e0!3m2!1sru!2sru!4v1612995015526!5m2!1sru!2sru" width="600" height="450" frameborder="0" style="border:0;" allowfullscreen="" aria-hidden="false" tabindex="0"></iframe> -->

google.maps.Marker ?????

function initMap() {
  const myLatLng = { lat: -25.363, lng: 131.044 };
  const map = new google.maps.Map(document.getElementById("map"), {
    zoom: 4,
    center: myLatLng,
  });
  new google.maps.Marker({
    position: myLatLng,
    map,
    title: "Hello World!",
  });
}

