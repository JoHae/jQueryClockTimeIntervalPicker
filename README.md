# jQueryClockIntervalPicker

##What ?
A responsive jQuery plugin for interactive time-interval selection based on a clock metaphor.

##Example
visit the [Project Page](http://johae.github.io/jQueryClockIntervalPicker) or see example folder of the repository .

##Usage - Interaction
| Commands | `no key` | `Ctrl-hold` |
| --- | --- | --- |
| `click` | Reset current - Select a point in time | - |
| `right-click` | Reset all intervals if there is at least one interval, select everything if there is no selection | - |
| `drag 'n' drop` | Reset current - Select interval | Add selection |

##Usage - Events
```html
<div id="time-picker" style="position: relative; width: 100%; height: 100%"></div>
```
...
```javascript
$( "#time-picker" ).clockTimeIntervalPicker()
    .on( "selectionStarted", function( event, timeObj ) {
        // Selection started Event - Returns the startTime
    })
    .on( "selectionEnded", function( event, interval ) {
        // Selection ended Event - Returns selected interval
    })
    .on( "selectionChanged", function( event, data ) {
        // Selection changed Event - Returns all intervals
    });
    
// Add responsive behaviour
$( window ).resize(function() {
    $( "#time-picker" ).clockTimeIntervalPicker('refresh');
});
```

##Options
You can pass an options object on initialization:
```javascript
$( "#time-picker" ).clockTimeIntervalPicker({useTwelveHoursLayout : false});
```

### List of available Options
| Option | Values |  Default | Description |
| --- | --- | --- | --- |
| **Interactions** |
| `multiSelection` | `true` / `false` | `true` | if `true`, allows the selection of more than one interval with CTRL-hold
| `enableAmPmButtons` | `true` / `false` | `true` | if `true`, shows buttons to switch between AM / PM and both
| `useTwelveHoursLayout` | `true` / `false` | `true` | if `true`, the clock layout is as usual, `false` shows a 24h layout
| `selectionTicksMinutes` | Integer (> 0) | 30 | defines the tick interval
| `showToggleLayoutButton` | `true` / `false` | `true` | if `true`, allows the user to switch between 12h/24h layout
| **Design** |
| `showHourLabels` | `true` / `false` | `true` |
| `showIndicatorLine` | `true` / `false` | `true` |
| `indicatorLineOptions` | svg options | | see below
| `faceTicksLargeLength` | Integer (> 0) | |
| `faceTicksLargeOptions` | svg options | | see below
| `faceTicksTinyLength` | Integer (> 0) | |
| `faceTicksTinyOptions` | svg options  | | see below
| `showFaceCircle` | `true` / `false` | `false` |
| `faceCircleOptions` | svg options | | see below
| `faceOverlayOptions` | svg options | | see below

Options with the suffix *Options* refer to a svg style object. See [Reference](https://www.w3.org/TR/SVG/styling.html) for possible options. Here is an example:
```javascript
faceCircleOptions: {
    fill: 'black',
    fillOpacity: 0.0,
    stroke: 'black',
    strokeOpacity: 0.0,
    strokeWidth: 2
}
```

##Requirements
- [jQuery 2.2.0](https://jquery.com)
- [jQuery UI 1.11.4](https://jquery.com)
- [jQuery SVG 1.5.0](https://jquery.com)

Other versions could work as well but are not tested yet.

##Found a bug or got ideas for new features ? 

Submit an issue above or here: 

<https://github.com/JoHae/jQueryClockIntervalPicker/issues>

##Work in Progress
- [x] Combine width / height of div and radius
- [x] 0 - 23 h Clock Layout
- [x] Costumizable ticks in minutes
- [x] Text labels for hours
- [ ] Add intervals programmatically
- [ ] Drag and Drop existing selection

##License
MIT License (MIT)
