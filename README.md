![abcjs](https://paulrosen.github.io/abcjs/img/abcjs_comp_extended_08.svg)

# Javascript library for rendering standard music notation in a browser.

This library makes it easy to incorporate **sheet music** into your **websites**. You can also turn visible **ABC** text into sheet music on websites that you don't own using a greasemonkey script, or change your own website that contains ABC text with no other changes than the addition of one javascript file. You can also generate **MIDI files** or play them directly in your browser.

[List of Examples](https://cdn.rawgit.com/paulrosen/abcjs/main/examples/toc.html)

Full documentation is here: [abcjs documentation](https://paulrosen.github.io/abcjs/)

## Major New Feature! 6.0.0-beta.36

String tablature is now available by adding an option to the `renderAbc` parameters. See [tablature documentation](https://paulrosen.github.io/abcjs/visual/tablature.html)

## Fix to audio in octave clefs 6.0.0-beta.31

If you are using an octave clef (for instance `K:C clef=treble-8`) it will now sound an octave different. The octave calculation was happening twice.

## Last version supporting midi.js is 6.0.0-beta.28

The file [abcjs version supporting midi.js](https://github.com/paulrosen/historical-abcjs-versions/blob/main/version-6/abcjs_midi-min.js) is the last version of the old style of sound production that will receive updates.

## Rename the default branch to `main`

The default branch is now named `main`. If you have cloned this repo previously, you can change it with:
```shell
git branch -m master main
git fetch origin
git branch -u origin/main main
```

## New css for audio control 6.0.0-beta.27

Be sure to download the latest abcjs-audio.css file if you are using it. If you are styling the audio control with your own css, add the rule:
```css
.abcjs-css-warning {
	display: none;
}
```

## Historical abcjs Packages 6.0.0-beta.27

Old versions of abcjs have been removed from this repo. If you are looking for them, you can find them here: [Historical Versions](https://github.com/paulrosen/historical-abcjs-versions)

## Breaking change when using midi.js for 6.0.0-beta.26

The midi.js package is no longer a direct dependency, it is now a peerDependency so it is not included by default. That way, users who aren't using the old style of sound generation won't need to load the package. If you are using the old style that uses midi.js, include this line in your `package.json` file:

```
"midi": "https://github.com/paulrosen/MIDI.js.git#abcjs"
```
Note that if you are using the minified version of the library with a `<script>` tag this does not apply to you.

## Change in wrapping behavior for 6.0.0-beta.25

There have been some tweaks to the way wrapping is calculated. Hopefully this will make your music layout a little better. If you start seeing odd results, let me know.

## Change in output folders for 6.0.0-beta.25

The files in `/bin` are being phased out. You can get the executables from `/dist` and the file names will not have the version number attached.

Many of the old versions that were in `/bin` are no longer kept in the active branches. If you need a particular old version then you can go to the branch with that tag to get it. 

The last version in each major version number is still available in the active branch as well as many recent versions.

## Default soundfont change for 6.0.0-beta.21

In this beta the default soundfont was changed to https://paulrosen.github.io/midi-js-soundfonts/abcjs/ Hopefully you will find that sounds better. If you set the soundfont directly then you won't notice any change. If you prefer the old soundfont, use the `soundFontUrl: "https://paulrosen.github.io/midi-js-soundfonts/FluidR3_GM/"` option when calling the synth functions.

## Informal roadmap
I'm getting close to taking version 6.0.0 out of beta.

These are the changes that are planned:
* Test and improve the sound of the soundfont.
* Add all the typescript definitions.
* Bug fixes.

If you have a particular issue that is impeding your usage of this library, please mention it in the issue.

After the 6.0.0 release, I'll be working on some more architecture changes which will go in a 7.0.0 release:

* Improve the API for controlling the synth. That is, make the parameters less confusing.
* Create a plugin architecture so that large features that are not widely used can be added without bloating this library.
* Change the build to use typescript while still maintaining legacy browser capability.
* Reduce the size of the library by optimizing code.
* Control the spacing of the elements on the line better: support equal size measures, and support allowing control of the spacing between notes.
* Improved documentation, particularly for synth.
* Bug fixes.

Thanks, Paul

## Future breaking changes
For most users of abcjs there probably won't be any more breaking changes in this beta.

There will probably still be some changes to the structure of the SVG that is created but if you aren't doing post-processing you won't notice except for better layout of the music.

There might be a few changes to the data that is returned from the callbacks, both the click listener and timing callbacks. Hopefully that will just be added data and won't affect any code.

## Issues

Thanks so much for the bug reports and feature requests that are pouring into the issues. I appreciate you taking the time to help improve abcjs. This is not a full time project, though, so I can't promise a quick turn around on the issues. I am going to attempt to be caught up on responding once a week at least.

And I would love some help on this project, including documentation, bug fixes, testing, refactoring, modernizing tools, and adding features. If you are so inclined, please get in touch.

## Supported by BrowserStack
If you aren't using the same browser and machine that I use, you can thank [BrowserStack](https://browserstack.com/) for their support of this open-source project.

![BrowserStack](https://paulrosen.github.io/abcjs/img/browserstack-logo-600x315.png)
