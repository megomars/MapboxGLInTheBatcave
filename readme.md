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
