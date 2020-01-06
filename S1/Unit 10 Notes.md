#Introducing Multimedia on the Web
HTML is the perfect tool to share text and data
The next major phase in HTML language was the introduction of multimedia support
Streaming audio, video, and interactive games, made the web a dominant entertainment platform
One of the biggest challenges{
    Delivering multimedia content in a form that can be retrieved quickly and easily without loss of quality
}

#Understanding Codecs and Containers

Codec{
    Computer program that encodes and decodes streams of data
    Compress data to transmit it in fast and efficent manner
    Decompress data it is to be read or played back
}
The compression method can be either lossy or lossless

Lossy compression: Nonessential data is removed in order to achieve a smaller file size{
    An audio file bight be compressed by removeing sounds the human ear can bairly hear
}
THe more the file is compressed the more content is lost
Data removed during compression cannot be recovered
Lossless compressions: data is compressed by removing redundant information{
    AAAABBBBBCCCCCC requires 15 caracters of info which can be rewritten using 6 characters as 4A5B6C
}
Lossless compression cannot achieve the same level of compression as with lossy compression
Ccodecs are placed within a container that handles the packaging, transportation, and prsentation of data
Container is the file format identified by a file extension

THe web supports a multitude of container and codec combinations
Not all containers and codecs are equally supported{
    The combination of the WebM container and VP8 codec is supported by Chrome but not by IE or Safarri/ the Apple builtin codec
}

#Understanding Plug-Ins

Media player{
    Decodes and plays multimedia content stored within a contaienr file
}
Plug-in{
    Software program accessed by a browser to provide a feature or capability not native to the browser
}
Embedded object{
    A plug-in can run in the window instead of running in a newly externally opened window
}

#Working with the audio element

Audio clips are embedded within a web page uing audio element{
    <audio src="url" attrubutes />
        Where URL specified the source of the audio file and attributes define how the audio clip should be handled by the browser
}

Audio Attributes{
    autoplay
        Starts playing the media clip as soon as it is loaded by the browser
    Controls
        Dispaly the play controls in the web pages
    Loop
        Automatically restarts the media clip when it's finished playing
    Muted
        Specifies that the audio output should be muted
    Preload="auto|metadata|none"
        Specifies whether the media clip should be preloaded by the browser, where the type is auto (to load whole clip), metadata (to preload only descriptive data about the clip), or none (don't preload anything)
    src="url"
        Specifies the source of the media clip where url is the location and name of the media file
}

#Browsers and Audio Formats

MP3{
    Desc: MPEG-1 Audio layer 3
    Codec: MP3
    File type: .mp3
    Support: all but Opera
    MIME type: audio/mpeg
}
AAC{
    Desc: Advanced Audio Coding is the encoding standard for all apple products, YouTube, gaming systems, mobile devices. Introduced as the successor to MP3 with the goal of achieving better sound quality at similar compression rates
    Codec: AAC
    File type: .aac .mp4 .m4a
    Support: All but Opera and Firefox Mobile
    MIME Type: audio/mp4
}
OGG{
    Desc: A File compression format designed for web audio, ogg is open source and royalty-free format, in general ogg provudes better sound quality than MP3, especially at lower bit rates
    Codec: Vorbis
    File type: .ogg
    Support: Chrome, Firefox, Opera
    MIME Type: Audio/ogg
}
WAV{
    Desc: The original audio format for Windows PCs, WAV is commonly used for storing uncompressed audio making it impractical for all but the shortest audio clips
    Codec: PCM
    File Type: .wav
    Supported by: All but Edge and IE
    MIME type: Audio/wav
}

Nest severl source elements within a single audio element to proide several versions of the same medial file

<audio>
    <source src="url1" type="mime=type" />
    <source src="url2" type="mime=type" />
</audio>

# Applying styles to the media player

The appearance of a media player is determined by the browser itself

CSS can be applied to set the width of the media player, add borders and drop shadows, and apply filters and transformations to the player's appearance

# Exploring Embedded objects

Plug-Ins in older browsers are marked using the embed element{
    <embed src="url" type="mime-type" width="value" height="value" />
}

# Plug-in attributes

src, type, height, and width attributes are generic attributes applied to embed elements for any plug-in
For example, the following embed element adds attributes to dispaly th media player controls and prevvent playback from strting automatically{
    <embed src="CP_overture.mp3" width="250" height="50" controller="yes" autoplay="no" />
}

# Plug-ins as a fallback option

Add embed elements to the end of the audio element as a last option for a browser which doesn't support HTML5 multimedia elements
    Use of plug-ins has steadily declined since the wide spead adoption of the HTML 5 standard

# Video Formats and Codecs

A video file contains codecs for the following{
    Audio
    Video
    Images
}

H.264{
    Devloped by MPEG, the H.264 codec is industry standard for high-definition video streams, movie sharing websites such as YouTube, and video Plug-ins
}
Theora{
    Theora is a royalty free codec devloped by the xiph.org foundation that productes video streams that can be used with almost any container
}
VP8{
    Open-source royalty-free codec owned by google for use in googles webM format
}
VP9{
    Google's successor to the VP8 codec, offering the same video quality as VP8 at half the download size
}
MPEG-4{
    MPEG-4 or MP4 is a widly used proprietary format devloped by apple based on the Apple QuickTime format
    Codec: H.264
    File type: .mp4 .m4v
    MIME-Type: video/mp4
    Supported by: Everything
}
Ogg{
    Desc: Ogg is an open source format devloped by the Xiph.org foundation using the Theora codec as an alternative to the MPEG-4 codec
    Codec: Theora
    File type: .ogg
    MIME-type: video/ogg
}
WebM{
    Opensource format introduced by google to provide royalty-free video and audio to be used with the HTML5 video element
    Codec: VP8, VP9
    File type: .webm
    Supported by: Chrome, Firefox, Opera
}

# Using the HTML5 video element

Videos are embedded int oa web page using video element{
    <video attributes>
        <source src="url1" type="mime-type" />
        <source src="url2" type="mime-type" />
    </video>
        Where attriutes are HTML attributes that ocntrol the behavior and appearance of the video playback, url1, url2, are possible sourcces of the video
}

Poster attribute defines a video's preview image{
    <video poster="url"></video>
        Where URL points to the thumbnail file
}

# Adding a Text Track to Video

Text track that needs to be read or recited to visually impaired users can be added to a media clip
Audio and video content accessible to all users
Text tracks are added to an audio or video clip using track element

<track kind="type" src="url" label="text" srclang="lang" />

Track "kind" attribute options{
    Captions{
        Brief text descriptions synced to specific time points within the media clip, designed for the hearing impaired user
    }
    Chapters{
        Chapter tites used by the media player
    }
    Descriptions{
        Longer descriptions synced to specified time points within the media clip, designed for the visually impaired
    }
    Subtitles{
        (default) Transition of diaglog from the medai clip, the language of the subtitle must be specified in the src lang attribute
    }
    metadata{
        metadata content used by external scripts accessing the media file
    }
}

# Making tracks with WebVTT

Tracks are stored as simple text files written in web video text tracks or webVTT language
Format of a webVTT file{
    WEBVTT
    cue1
    cue2
}
    Where cue1, cue2, etc are cues matched with specific 

List of cues is separated by a single blank line after a cue text
White spce is not ignored in WebVTT files
General form of a cue{
    label
    start --> stop
}
    Where label is the name assigned to the cue, start and stop or some sheit

# Placing Cue Text

size and position of a cue text ca nbe set using cue settings directly after the cue's time interval:
setting1:value1 setting2:value2
    Where setting1, setting2 etc defune the size and position of the cue text and value1, value2, are the setting values
No space betwen setting name and value

# Cue Attributes in WebVTT

Align:value
    Sets the horizontal alignment of the text within the cue, where value is start (left-aligned), middle (center-aligned), or end(right-aligned)
Line:value{
    Sets the vertical position of the cue within the end video window, where value ranges from 0% top to 100% bottom
}
Position:value{
    sets the vertical position of the cue within the end video window, where value ranges from 0% left to 100% right
}
size:value{
    sets teh width of the cue as a percentage of the width of the video window
}
vertical:type{
    Displays the cue text vertically rather than horizontally where type is rl (writing direction is right to left) or lr
}

# Applying Styles to Track Cues

Cue Pseudo-element to format the appearane of the cues appearing within a media clip{
    ::cue{
        styles;
    }
}
Styles for the cue pseudo-element are limited to background, color, font, opacity, outline, text-decoration, text-shadow, visibility, and white-space properties

Format specific cues or text strings within a cue using the fllowing markup tags{
    <i>Italicized</i>
    <b>Bold</b>
    <u>Underlined</u>
    <span>to mark spans of text</span>
    <ruby>Mark ruby text(non standard english chars)</ruby>
    <rt>Mark ruby text(non standard english chars)</rt>
    WebVTT supports tags that are not part of the HTML library
    <c>tag is used to mark text strings belonging to a particular class with <c.classname></c> </c>
    <v>Distinguish between one voice and another with <v name></v> </v>
}

# Using Third-party Video Players

Object element is used to define browsers with plug-ins{
    <object>Paramerers</object>
        Attributes = values passed to object controlling the object's appearance and actions
}
Parameters for the object are defined using param element{
    <param name="name" value="value" />
        Where name is the name of the parameter and value is the parameter's value
}

# Exploring the Flash Player???
{
    THe most-used plig-in for video playback is Adobe Flash Player embeddedusing the following object element{
        <object data="url" type="application/x-shockwave-flash" width="value" height></object>
    }
}

# Parameters of the flash player

bgcolor:color
flashvar:text
id:text
loop:true|false
menu:true|false
name:text
play:true|false
quality:low|autolow|autohigh|medium|high|best
scale:showall|noborder|exactfit
    Defines how a clip is scaled within a given space, noborder perserves aspect ratio, exact fit does not
wmode:window|opaque|transparent
    window opens in seperate window, opaque hides anything behind the background, transparant lets the page background show through transparant sections on the player

# Embedding Videos from

Youtube videos are easy to embed in a web page using YouTube's HTML5 video player
Click te share button below the YouTube video player to share it
YouTube providesoptions to post a hypertext link to the video of a multitude of social media sites or to share the link via email

To embed a video within a website click Embed which brings up a preview of the player and the HTML that needs to be added to the web page

General code for an embedded player{
    <iframe width="value" height="value" src="url" frameborder="0" allowfullscreen></iframe>
        Where the url provides the link to the YouTube Video
        Width and height attributes define the dimensions of the player embedded on a web page
        Frameborder attribute sets the width of the border around the player in pixels
        Allowfullscreen attribute allows the user to play the video in full screen mode
}

iframe element - Used to mark inline frames (video)

inline frames -  windows embedded within a web page that display that content

# HTML5 Video Players

Works within a browser with css and Javascript files

Presents customizable player that can be adapted to the needs of business or organization

HTML5 video players{
    JWPlayer (jwplayer.com)
    Video.js (videojs.com)
    Media Element.js (mediaelementjs.com)
    Projekktor (projekktor.com)
    Flowplayer/Flash Player (flowplayer.org)
}

# Introducing Transitions

Transition: change in object's style from inital state to ending state (possible keyframes in between)
Slows down change from 1 color to another so changes feel smoother and less abrupt

Create transitions with the following style{
    transition: property duration;
        Where property is a property of the object that changes betwen the inital and end states
        and where Duration is the transition time in seconds or milliseconds
}
Varying speed of transition is defuned using{

    where timing-function is one of the following keywords
        ease: (default) transition occurs more rapidly at the beginning and slows down at the end
}

Ease-in
Ease-out
Ease-in-out
Linear

# setting the transition timing

Timing function can be visualized as a graph
Shows progress of transition vs. duration
Graphical repersentation of the timing finction is the basis of another measuer of transition timing using{
    transition: cubic-bezier(n, n, n, n);
        Where n parameter values define the sape of the timing curve
}

# Delaying a Transition

Transition does not need to start immediately after the event that triggers it
Start of the transition can be delayed by adding delay value to the following{
    transition property duration timing-function delay;
        where delay is measured in seconds or milliseconds
}

# Creating a Hover Transition

Limitations of a transition{
    Can only be run when a CSS property is being changed, like during a hover event
    It's run once and then can't be looped for repetition
    Inital and end states of the transition can be defined but not the styles of intermediate states
}
Annimation is done to overcome these limitations

# Animating Objects with CSS

Key frame - Sequence of changing images to create illusive movement for animation
CSS replaces the concept of key frames images with key frame styles that are applied in rapid succession to a page object @keyframes rule{
    @keyframes name{
        keyframe1 {styles;}
        keyframe2 {styles;}
    }
}

Name provides the name or title f the animated sequence
Keyframe 1, 2 etc defines the progress of individual key frames that are expressed as persentages or with keywords from and to
Styles are styyles applied within each keyframe

# Applying an Animation

Key frames animating is applied to an object using animation-name and animation-duration properties{
    animation-name: keyframes;
    animation-duration: times;
        Where keyframes is a comma-separated list of animatons applied to the object the names from the @keyframes rule an times are the legnths of each animation expressed in seconds or milliseconds
}

# Animation Properties

animation-name = keyframes
animation-duration = time
    Default = 0s
animation-timing-function = ease|ease-in|ease-out|ease-in-out|linear|cubic-bezier(n,n,n,n)
    Defines default timing between key frames in the animation (default = ease)
animation-delay = time
    deafult = 0s
animation-iteration-count = value|infinite
    Specifies the number of times the animation is played, default = 1
animation-play-state = running|paused
    Default = running
animation-direction = normal|reverse|alternate|alternate-reverse
    Defines the direction of the animation where normal follows the @keyframes rule, reverse reverses the order, alternate plays the animation in normal order followed by the reverse direction, alternate-reverse plays the animation in reverse direction first and then normal
animation-fill-mode = none|backwards|forwards|both
    Defines what styles from the animation are applied to the object outside the time it is running where none does not apply any styles, backwards applies the styles from the first keyframe, fowards applies the styles from the last keyframe, both applies styles in both directions (default is none)

# controlling an Animation

Animation can have two states of operation - play or pause
Check box can be used to control animation

Checkboxes can be replaced with more attractive icons
    Can be a reload symble
    Can be a hand to stop
    The two symbols have the Unicode values \21bb and \270b, respecively