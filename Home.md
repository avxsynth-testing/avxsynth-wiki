## What Is AvxSynth?

AvxSynth is a Linux port of the AviSynth toolkit. The objective of the porting effort was to bring the power of AviSynth into the Linux world. In particular, we are interested in AviSynth as a frame server front-end to the encode step of our Media Pipeline.

The AvxSynth port was based on the AviSynth 2.5.8 code base, and we are calling this version 4.0, so as to differentiate from the dead AviSynth 3.0 project.

## Getting Started

To build and run AvxSynth, follow these instructions

## Porting Discussion

You can read about the porting effort here.

You can see the status of the built-in function porting here. 

## The AvxSynth Frame Server

The AvxSynth toolkit includes a frame server application that delivers decoded frames through stdout. This can be piped to X264. You can see how to use AvxSynth with X.264 here.
Watch

Click Here to see a short video of AvxSynth in action. Or watch in low-res below. This video demonstrates the ffmpeg source, ffmpeg scaling, ShowSMPTE, and AvxSubtitle, a new filter that does caption burn-in.

## Error Handling

The AvxSynth error handling model is discussed here.

## Discuss

Doom9 discussion is here

## Contribute

If you would like to contribute to AvxSynth, we have need for developers, testers, and build-install experts. More information can be found here. 
