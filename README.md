# Handbrake-tut
Video compression with handbrake-cli

You never even touched upon the "video" tab ... where all the most important HandBrake options for video optimization and filesize reduction are (although, I realize it might seem a little intimidating if you don't know what they do). Perhaps I could help.

Your reduced ~500Mb export could have easily been reduced further to around ~200Mb just from experimenting with the video export options on that tab. Meaning, your average 1 hour upload time could be slashed again in half without any apparent loss in quality. If you're uploading regularly, this could be a real time-saver for you, since once you've found the right optimization, you can save the settings to a preset, which you can just select for all subsequent transcodes.

I've been using HandBrake for many years now. The best version to use is "HandBrake Nightly" as it's their most optimized and up-to-date build: Just Google: "HandBrake Nightly" for the official download website

Once you find your perfect settings, you can just save a "preset" template, so you don't have to keep tweaking these options for every new video you want to transcode.

To find out the best quality settings, it's really very easy to do. Just tweak the video settings and then do an short test render. Make sure to change the "chapters" dropdown menu to "seconds" and set this to a short test duration of around 30 seconds or so, to render out for testing (name each test render with the settings you used, so you can compare them side-by-side afterwards, when deciding which is best for your purposes). 

Audio: Your Premiere Pro export default settings, are set to export your audio as: 
AAC, 320kbps, 48kHz, Stereo. 

In HandBrake "Audio" tab, instead of transcoding to MP3 at 320kbps, you should instead simply select "AAC Passthru", as this will ensure that HandBrake leaves your original audio exactly as Premier Pro exported it, untouched. You never want to transcode an already lossy audio format to another lossy format, where possible (as there will always be some amount of fidelity degradation).

As for the best video settings (under the "Video" tab), You'll have to play around with these to find the perfect balance, and comparing the short rendered test clips. But here are some suggestions, based upon the type of content you had in this video (remember to use the latest version of "HandBrake Nightly" as your version will likely be out of date.

Video Codec: 
set this to: "H.265 10-bit (x265)" 
...this will render the maximum video quality, at the lowest possible filesize. No other video codecs come close to matching HEVC for quality-per-filesize.

Framerate FPS: "same as source" 

Quality: Constant Quality: RF (Rate Factor)... 
try 24, 23, 22, 21 (the higher the # = the lower the quality)
If you set a CQ RF of 24 and don't see much degradation from one rendered at ~21, then use the higher number (as you'll get a much smaller filesize) 

Optimise Video (Encoder Preset): 

Generally, anything between "Ultrafast" to "Fast" are good enough. However, if your CPU can handle it, at a decent speed, then "Medium" is usually optimal for most purposes.

One last thing, make sure to select the checkbox labeled "Fast Decode", this makes the exported video easier to view for people with lower-powered devices, like cell phones etc.

I hope this can help you and others even further.
