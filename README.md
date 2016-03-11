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
| `multiSelection` | `true` / `false` | |
| `enableAmPmButtons` | `true` / `false` | |
| `useTwelveHoursLayout` | `true` / `false` | |
| `selectionTicksMinutes` | Integer (> 0) | |
| `showToggleLayoutButton` | `true` / `false` | |
| **Design** |
| `showHourLabels` | `true` / `false` | |
| `showIndicatorLine` | `true` / `false` | |
| `indicatorLineOptions` |  | |
| `faceTicksLargeLength` |  | |
| `faceTicksLargeOptions` | | |
| `faceTicksTinyLength` | | |
| `faceTicksTinyOptions` | | |
| `showFaceCircle` | `true` / `false` | |
| `faceCircleOptions` | | |
| `faceOverlayOptions` | | |

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
- [ ] 0 - 23 h Clock Layout
- [ ] Costumizable ticks in minutes
- [ ] Text labels for hours
- [ ] Add intervals programmatically
- [ ] Drag and Drop existing selection

##License
MIT License (MIT)
