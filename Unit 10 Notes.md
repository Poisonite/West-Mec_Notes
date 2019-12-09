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

#Applying styles to the media player

The appearance of a media player is determined by the browser itself

CSS can be applied to set the width of the media player, add borders and drop shadows, and apply filters and transformations to the player's appearance

#Exploring Embedded objects

Plug-Ins in older browsers are marked using the embed element{
    <embed src="url" type="mime-type" width="value" height="value" />
}

#Plug-in attributes

src, type, height, and width attributes are generic attributes applied to embed elements for any plug-in
For example, the following embed element adds attributes to dispaly th media player controls and prevvent playback from strting automatically{
    <embed src="CP_overture.mp3" width="250" height="50" controller="yes" autoplay="no" />
}

#Plug-ins as a fallback option

Add embed elements to the end of the audio element as a last option for a browser which doesn't support HTML5 multimedia elements
    Use of plug-ins has steadily declined since the wide spead adoption of the HTML 5 standard

#Video Formats and Codecs

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

#Using the HTML5 video element

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

#Adding a Text Track to Video

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

#Making tracks with WebVTT

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

#Placing Cue Text

size and position of a cue text ca nbe set using cue settings directly after the cue's time interval:
setting1:value1 setting2:value2
    Where setting1, setting2 etc defune the size and position of the cue text and value1, value2, are the setting values
No space betwen setting name and value

#Cue Attributes in WebVTT

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