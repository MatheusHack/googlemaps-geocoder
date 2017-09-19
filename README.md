# googlemaps
Show marker in map by address or coordinates geography

# Usage
Minimal usage:
```js
google.maps.event.addDomListener(window, "load", GoogleMaps.init({
    target: 'mapa',    
    inputAddress:  $('input[name="address"]'),
    inputLatitude: $('input[name="latitude"]'),
    inputLongitude: $('input[name="longitude"]')
}));
// Outputs: Div with map
```

#Usage events input
Minimal usage events input:
```js
$(document).ready(function(){
    $('input[data-geocoder]').change(function(){
        var type = $(this).data('geocoder');
        GoogleMaps.findLocation(type);
    });                
});
```

# Browser
```html
<!doctype html>
<!DOCTYPE html>
<html lang="en">
    <head>
        <title></title>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <link rel="stylesheet" href="css/style.css">
        <script src="https://code.jquery.com/jquery-3.2.1.min.js"></script>
        <script src="http://maps.google.com/maps/api/js?sensor=false"></script>
    </head>
    <body>
        <h2>Mapa</h2>
        <hr>
        <div id="mapa"></div>

        <div id="informacoes">
            <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Accusantium odit ea accusamus aspernatur maxime! Atque impedit ex maiores ipsam quia, cumque dolores et ullam dignissimos earum saepe, voluptatibus esse deleniti.</p>
            <form>
                <div class="group-input width-12">
                    <label>Endereço</label>
                    <input type="text" class="width-12" name="address" data-geocoder="address">
                </div>
                <div class="group-input width-6">
                    <label>Latitude</label>
                    <input type="text" class="width-12" name="latitude" data-geocoder="latitude">
                </div>                
                <div class="group-input width-6">
                    <label>Longitude</label>
                    <input type="text" class="width-12" name="longitude" data-geocoder="longitude">
                </div>                                
            </form>
        </div>
        <script>
            $(document).ready(function(){
                $('input[data-geocoder]').change(function(){
                    var type = $(this).data('geocoder');
                    GoogleMaps.findLocation(type);
                });                
            });

            google.maps.event.addDomListener(window, "load", GoogleMaps.init({
                target: 'mapa',
                inputAddress:  $('input[name="address"]'),
                inputLatitude: $('input[name="latitude"]'),
                inputLongitude: $('input[name="longitude"]')
            }));
        </script>        
    </body>
</html>        
```