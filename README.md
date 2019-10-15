# F7Cordova
---
# Stap 1
## Stappen om tot deze versie van de app te komen :
 * framework7-cli cordova installeren
 ```
 npm i framework7-cli cordova -g
 ```
 * aanmaken van de app via de CLI
 ```
 framework7 create --ui
 ```
 * kies in de UI die verschijnt de gewenste opties. 
   De opties staan hieronder beschreven.

---
# Stap 2
## 'Barebones' Framework7-app

In deze branch zijn een aantal bestanden en opties verwijderd, zodat we een meer 'lege' app hebben, vanwaar we kunnen opbouwen.

### Verwijderd 
 * in index.html
   * right panel
   * het icoontje om de right panel te openen :
     * id="view-home" > class="page" > class="navbar navbar-large" > class="navbar-inner" > ```div class="right"```
   * commentaar
   * content ivm een popup, panels, login-scherm  
 * de pages die we niet willen gebruiken verwijderd
   * plus die pages verwijderd uit ```routes.js```


### Aangepast 
 * Wat placeholders toegevoegd.
 * Een paar aanpassingen zodat de 'Home', 'Locatie' en 'Data' zichtbaar zijn in ```index.html```.
 * Een paar icoontjes :
   * https://framework7.io/icons/  -> F7 icons
   * https://material.io/resources/icons/?style=baseline -> MD icons
 * In app.js
   * De login scherm code (we hebben die verwijderd uit de html)
 * In routes.js
   * ```routes.js``` aanpassen voor de toegevoegde/verwijderde bestanden

## Toegevoegde bestanden
 * gegevens.html
 * locatie.html

---
# Stap 3
## Locatie toevoegen
 *  de locatie plugin toevoegen met 
 ```
 cordova plugin add cordova-plugin-geolocation
 ```
 Meer informatie over deze plugin vind je op : https://cordova.apache.org/docs/en/latest/reference/cordova-plugin-geolocation/index.html


## 3 Nieuwe functies toegevoegd 
  * **showPosition** : toont details van je positie wanneer een positie object returned (*app.js*)
  * **positionError** : toont een boodschap indien er een fout is met de locatie (*app.js*)
  * **getLocatie** 
    * start de watch van de positie (*locatie.html*)
    * zie de link tussen **@click** en de methods in dit script
    
Test als je kan de app op je eigen toestel :
```
cordova run android
```
Als je niet op je eigen toestel kan testen :
```
cordova emulate android
```
Hiervoor moet je wel al minstens 1 virtueel toestel hebben toegevoegd via bv Android Studio.

Enkele caveats :

* Test eerst of je emulator wel kan opstarten
* Op sommige versies van je emulator moet je
  * in het virtuele toestel de developers options unlocken
  * USB debugging aanzetten (SETTINGS > DEVELOPER OPTIONS)
  * toestemming geven aan je computer wanneer je virtuele toestel een melding geeft ivm het toestaan van adb toegang naar jouw computer




---
## Framework7 CLI Options

Framework7 app created with following options:

```
{
  "cwd": "C:\\dev\\webmobile\\f7Cordova",
  "type": [
    "cordova"
  ],
  "name": "F7Cordova",
  "framework": "core",
  "template": "tabs",
  "bundler": false,
  "cssPreProcessor": false,
  "theming": {
    "customColor": false,
    "color": "#007aff",
    "darkTheme": true,
    "iconFonts": true,
    "fillBars": true
  },
  "customBuild": false,
  "pkg": "net.ophalvens.wmF7Cordova",
  "cordova": {
    "folder": "cordova",
    "platforms": [
      "android"
    ],
    "plugins": [
      "cordova-plugin-statusbar",
      "cordova-plugin-keyboard",
      "cordova-plugin-splashscreen",
      "cordova-plugin-device"
    ]
  }
}
```

## NPM Scripts

* 🔥 `start` - run development server
* 🔧 `serve` - run development server
* 📱 `build-cordova` - build cordova app
## Cordova

Cordova project located in `cordova` folder. You shouldn't modify content of `cordova/www` folder. Its content will be correctly generated when you call `npm run cordova-build-prod`.

## Documentatie & Bronnen

* [Framework7 Core Documentation](https://framework7.io/docs/)
* [Framework7 Icons Reference](https://framework7.io/icons/)
* [Community Forum](https://forum.framework7.io)
