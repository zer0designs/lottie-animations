# lottie-animations
A Repo for my Lottie JSON files


**HOW IT WORKS**



**PART I. The Trouble with LottieFiles**

There are a lot of free animations hosted on LottieFiles.com, but only so-called 'free' because in order to embed them in your website,
you'll need to jump through a lot of hurdles.

Typically, you'll need to register an account, then select the free animation you like to "upload" to your project on LottieFiles.
Only after that do they allow you to generate the link to their .JSON file, that has to be plugged into their web play script, on:

    https://lottiefiles.com/web-player

So you'll get an embed code like this:

    <script src=“https://unpkg.com/@lottiefiles/lottie-player@latest/dist/lottie-player.js”></script>
    <lottie-player src=“https://lottie.host/c404786e-2d84-4239-a092-5fa55366d5a7/DRPRrsgJH4.json” 
    background=“Transparent” speed=“1” style=“width: 300px; height: 300px” 
    direction=“1” mode=“normal” loop controls autoplay></lottie-player>

In which the first src=".../lottie-player.js" loads their web player script,
and the second src="...DRPRrsgJH4.json" loads the specific JSON file hosted on their server.

However, on certain websites like Zyro (Hostinger) and Weebly, if you use LottieFiles' web player script, the animation won't load at all.
This is because the web player script they provided is faulty and whoever programmed that lottie-player.js file should go to hell.

There's actually a workaround for this, but it just uses an iframe for a file on their server

    <iframe src="https://lottie.host/?file=ec788595-877b-493e-9912-cc7edf680969/qPTiNZIVn2.json"
    frameborder="0" style="width: 100%; height: 100%; border-radius: 25px; aspect-ratio: 800/240;">
    </iframe>

In which the link https://lottie.host/?file=ec788595-877b-493e-9912-cc7edf680969/qPTiNZIVn2.json
is a link to an animation file that plays directly in the browser. For example, for the raw .json file above, the playable link is

    https://lottie.host/?file=c404786e-2d84-4239-a092-5fa55366d5a7/DRPRrsgJH4.json

But we can't do this with every animation file found on LottieFiles, since a free account only allows you to store 10 files,
whether you create and upload your own Lottie animation or save an animation created by someone else. 'Free,' my butt!




**PART II. The Solution using Lordicon**

Thankfully, Lordicon.com provides plenty of free animations that actually work well in embeds.
For example, select the gift box animation on this address then click the HTML button:

    https://lordicon.com/icons/wired/outline?group=free&categoryId=112

Then we get this script:

    <script src="https://cdn.lordicon.com/bhenfmcm.js"></script>
    <lord-icon
        src="https://cdn.lordicon.com/nkmsrxys.json"
        trigger="hover"
        colors="primary:#121331,secondary:#08a88a"
        style="width:250px;height:250px">
    </lord-icon>

Notice how they're using a different .js script for the animation player, named "bhenfmcm.js"
This is what makes all the difference in the world, because this actually works on websites like Zyro and Weebly.

So we can simply replace the link to the .json file with our own, whether it's hosted on GitHub or elsewhere, and it'll run beautifully.
However not all attributes and properties will work the same way, so we'll need to modify it a bit (see below).

Also unlike using an iframe, there's no way to style this to have rounded corners, unfortunately.




**III. The Conclusion**

Finally, we can use this modified script:

    <script src="https://cdn.lordicon.com/bhenfmcm.js"></script>
    <lord-icon
        src="https://raw.githubusercontent.com/zzerodesigns/lottie-animations/main/Logo-3-%5Bremix%5D.json"
        trigger="hover"
        style="width: 100%; height: 100%; aspect-ratio: 860/240;">
    </lord-icon>

Replace the .json link with the link to the raw .json file that you already uploaded to GitHub, and edit the trigger and styles.

Possible triggers (tested & working):

    trigger="hover"                           -> animation plays once on hover
    trigger="click"                           -> animation plays once on click
    trigger="loop" delay="2000"               -> animation loops with 2 second delay
    trigger="loop-on-hover" delay="2000"      -> animation loops on hover with 2 second delay
    trigger="morph"                           -> animation plays once on hover, then reverses on release
    trigger="boomerang"                       -> animation plays and reverses once on hover

Styles:

    style="width: 100%; height: 100%; aspect-ratio: 860/240;"
    
Replace number in the aspect-ratio with the actual dimensions of the Lottie animation being used.

This styling ensures that the embeded animation will be responsive to screen sizes,
aand you can also resize the code box in Zyro and it'll adjust accordingly while keeping the ratio.

TL;DR What all of this means is you can have UNLIMITED Lottie Animations, if you:
  - create your own Lottie JSON using Jitter.video
  - download Lottie JSON made by others
  - host them all on GitHub. AMAZING.
