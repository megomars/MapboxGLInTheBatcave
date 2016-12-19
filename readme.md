#MapboxGL in the batcave

##Here are 100 things that you need to know about MapboxGL:

1. Mapbox GL JS is a JavaScript library that uses WebGL to render interactive maps from vector tiles and Mapbox styles. Mapbox GL JS has no distinction between baselayers and overlay layers.

2. Including mapbox-gl onto your page
  ```
  <script src='https://api.mapbox.com/mapbox-gl-js/v0.28.0/mapbox-gl.js'></script>
  <link href='https://api.mapbox.com/mapbox-gl-js/v0.28.0/mapbox-gl.css' rel='stylesheet' />
  ```

3. Render your map on the page
    ```
    <div id='map' style='width: 400px; height: 300px;'></div>
    <script>
    mapboxgl.accessToken = '<your access token here>';
    var map = new mapboxgl.Map({
        container: 'map',
        style: 'mapbox://styles/mapbox/streets-v9'
    });
    </script>
    ```
4. Fundamentals of Mapbox GL JS
  - Client side rendering as vectors (this is a big deal)

  - The camera
    - Center point - long,Lat
    - Zoom level - any number
    - Bearing - rotation of the map
    - Tilt - 45 degree perspective

  - layers
    baselayers and overlays are combined

  - Essential functions
    - var map = new mapboxgl.Map({})
    - easeTo (animate between areas)
    - Add data to a map (1. add a source, 2. add a layer)
      - addSource(vector tiles, raster tiles, GeoJSON, image, video)
      - A source requires a unique ID and a URL
      ```
      map.on('load', function() {
        map.addSource('RPD_Parks', {
          type: 'vector',
          url: 'mapbox://mapbox.3o7ubwm8'
        });
      });
      ```
      - addLayer()
      ```
      map.on('load', function() {
        map.addSource('RPD_Parks', {
          type: 'vector',
          url: 'mapbox://mapbox.3o7ubwm8'
        });
        map.addLayer({
          id: 'rpd_parks',
          type: 'fill',
          source: 'RPD_Parks',
          'source-layer': 'RPD_Parks',
          layout: {
            visibility: 'visible'
          },
          paint: {
            'fill-color': 'rgba(61,153,80,0.55)'
          }
        });
      });
      ```
