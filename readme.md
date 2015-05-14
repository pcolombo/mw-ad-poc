# Media Wall Ad Support PoC

## Goals

Using overrides or a forked version of a Livefyre Media Wall, enable publishers to run tests to see how a Media Wall experience with ads performs.

If these pages show promise, publisher will work on a more stable integration.

The approach is to inject the ad units into the correct position at runtime. This allows more consistent positioning, especially when new items are added to the stream. This also allows infinite re-use. Adding placeholders to the collection data would require each collection to be carefully managed.

## Requirements

1. Inject an ad unit into a media wall every X position - IN PROGRESS
2. Turn the modal view into a slideshow / carousel
3. Inject an ad unit into the modal view (desktop/tablet only)
4. Click events will be trackable

## Ad Format
Within the Media Wall, the following containers should be added for the customer's developers to attach display ad units to: 


```
    <div id='lf-mediawall-leaderboard-1' class='mediaWallAd'>
    <div id='lf-mediawall-leaderboard-2' class='mediaWallAd'>
    <div id='lf-mediawall-rectangle-1' class='mediaWallAd'>
    <div id='lf-mediawall-rectangle-2' class='mediaWallAd'>

```


## Files

###injector.html

[View](http://pcolombo.github.io/mw-ad-poc/injector.html) | [Source](single.html)

Injects a placehlder for an ad unit at every nth item. (Configurable via LFWall.adInterval).
Additional logic can be added to LFWall.getAdTemplate() as desired.




###single.html

[View](http://pcolombo.github.io/mw-ad-poc/single.html) | [Source](single.html)

Example of a single tile being injected.

- **Livefyre: ** 
    - Fix issue where injected tiles disppears on resize/re-render.
    - Add iteration to inject multiples at proper location
    - Find a better way to handle Wall.render() complete 
- **Customer: ** Inject a display ad onto the div to test rendering.