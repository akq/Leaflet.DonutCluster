Leaflet.DonutCluster
=====================

A lightweight standalone [Leaflet](https://leafletjs.com)  plugin to display donut charts instead of circles in map when using [Leaflet marker cluster](https://github.com/Leaflet/Leaflet.markercluster). This lib copies the codes which generate the donut svg from [donutjs](https://github.com/finom/donutjs).


**Only depends on Leaflet and Leaflet.markercluster, NOT on other chart library like d3.js**

[Online Demo -- basic](https://jsfiddle.net/b43c1xkf/1/embedded/result,html/)
[Online Demo -- sum by field](https://jsfiddle.net/b43c1xkf/1/embedded/result,html/)

![cluster map example](screenshot.png)



## Usage
First include the Leaflet.DonutCluster.js, but you don't need to include the css file, as it's optional. if you want to include the css file, you can comment the line in the .js file. 
```javascript
text.setAttribute('style', ...)
```
```javascript
                //create the markercluster
                var markers = L.DonutCluster(
                    //the first parameter is  markercluster's configuration file
                    {
                        chunkedLoading: true
                    }
                    //the second parameter is  DonutCluster's configuration file
                    , {
                    key: 'title', //indicates the grouped field, set it in the options of marker
                    sumField: 'value', // indicates the value field to sum. set it in the options of marker
                    arcColorDict: { // the ark color for each group.
                        A: 'red',
                        B: 'blue',
                        C: 'yellow',
                        D: 'black'
                    }
                })
```
Then add the marker into the markercluster.
```javascript
        var marker = L.marker(L.latLng(a[0], a[1]), {
            title: title //the value to group
        });

        ...

        markers.addLayer(marker);
```

## License

MIT