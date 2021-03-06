<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

### Table of Contents

-   [MapboxGeocoder](#mapboxgeocoder)
    -   [query](#query)
    -   [setInput](#setinput)
    -   [setProximity](#setproximity)
    -   [getProximity](#getproximity)
    -   [on](#on)
    -   [off](#off)

## MapboxGeocoder

A geocoder component using Mapbox Geocoding API

**Parameters**

-   `options` **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** 
    -   `options.accessToken` **[String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Required.
    -   `options.zoom` **[Number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)** On geocoded result what zoom level should the map animate to when a `bbox` isn't found in the response. If a `bbox` is found the map will fit to the `bbox`. (optional, default `16`)
    -   `options.flyTo` **[Boolean](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** If false, animating the map to a selected result is disabled. (optional, default `true`)
    -   `options.placeholder` **[String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Override the default placeholder attribute value. (optional, default `"Search"`)
    -   `options.proximity` **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)?** a proximity argument: this is
        a geographical point given as an object with latitude and longitude
        properties. Search results closer to this point will be given
        higher priority.
    -   `options.trackProximity` **[Boolean](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)** If true, the geocoder proximity will automatically update based on the map view. (optional, default `false`)
    -   `options.bbox` **[Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)?** a bounding box argument: this is
        a bounding box given as an array in the format [minX, minY, maxX, maxY].
        Search results will be limited to the bounding box.
    -   `options.types` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)?** a comma seperated list of types that filter
        results to match those specified. See <https://www.mapbox.com/developers/api/geocoding/#filter-type>
        for available types.
    -   `options.country` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)?** a comma separated list of country codes to
        limit results to specified country or countries.
    -   `options.minLength` **[Number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)** Minimum number of characters to enter before results are shown. (optional, default `2`)
    -   `options.limit` **[Number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)** Maximum number of results to show. (optional, default `5`)
    -   `options.language` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)?** Specify the language to use for response text and query result weighting. Options are IETF language tags comprised of a mandatory ISO 639-1 language code and optionally one or more IETF subtags for country or script. More than one value can also be specified, separated by commas.
    -   `options.filter` **[Function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function)?** A function which accepts a Feature in the [Carmen GeoJSON](https://github.com/mapbox/carmen/blob/master/carmen-geojson.md) format to filter out results from the Geocoding API response before they are included in the suggestions list. Return `true` to keep the item, `false` otherwise.
    -   `options.localGeocoder` **[Function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function)?** A function accepting the query string which performs local geocoding to supplement results from the Mapbox Geocoding API. Expected to return an Array of GeoJSON Features in the [Carmen GeoJSON](https://github.com/mapbox/carmen/blob/master/carmen-geojson.md) format.

**Examples**

```javascript
var geocoder = new MapboxGeocoder({ accessToken: mapboxgl.accessToken });
map.addControl(geocoder);
```

Returns **[MapboxGeocoder](#mapboxgeocoder)** `this`

### query

Set & query the input

**Parameters**

-   `searchInput` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** location name or other search input

Returns **[MapboxGeocoder](#mapboxgeocoder)** this

### setInput

Set input

**Parameters**

-   `searchInput` **[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** location name or other search input

Returns **[MapboxGeocoder](#mapboxgeocoder)** this

### setProximity

Set proximity

**Parameters**

-   `proximity` **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** The new options.proximity value. This is a geographical point given as an object with latitude and longitude properties.

Returns **[MapboxGeocoder](#mapboxgeocoder)** this

### getProximity

Get proximity

Returns **[Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)** The geocoder proximity

### on

Subscribe to events that happen within the plugin.

**Parameters**

-   `type` **[String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** name of event. Available events and the data passed into their respective event objects are:-   **clear** `Emitted when the input is cleared`
    -   **loading** `{ query } Emitted when the geocoder is looking up a query`
    -   **results** `{ results } Fired when the geocoder returns a response`
    -   **result** `{ result } Fired when input is set`
    -   **error** `{ error } Error as string`
-   `fn` **[Function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function)** function that's called when the event is emitted.

Returns **[MapboxGeocoder](#mapboxgeocoder)** this;

### off

Remove an event

**Parameters**

-   `type` **[String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)** Event name.
-   `fn` **[Function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function)** Function that should unsubscribe to the event emitted.

Returns **[MapboxGeocoder](#mapboxgeocoder)** this
