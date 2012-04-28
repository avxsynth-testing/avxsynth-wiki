#Testing Summary

# Introduction

AVXSynth is experimental software, and much of its code has not been tested for correct operation. This page will serve to document the current status of testing and describe the testing methodology. Mainline Avisynth 2.5.8 for Windows will be used as the reference. Testing scripts used can be found in the /tests/ directory of the SVN repository.

# General Limitations

 * Some functions that depend on Windows-specific functionality (e.g. AVISource, DirectShowSource) have not been ported.
 * Assembly code has not been ported. This may result in different output from Windows.

# Tested Functions

## Audio

DelayAudio

 * Negative delays working
 * Positive delays working

AmplifyDB

 * Volume increase working
 * Volume decrease working

Amplify

 * Volume increase working
 * Volume decrease working
 * Negative gains (phase inversion) not tested

AssumeSampleRate

 * Speedup working
 * Slowdown working

Normalize

 * Working
 * "show" not tested as simultaneous A/V is not supported

MixAudio

 * Working

ResampleAudio

 * Normal resampling working
 * Fractional resampling working
 * Downsampling and upsampling working

ConvertToMono

 * Working

EnsureVBRMP3Sync

 * Not tested as simultaneous A/V is not supported

MonoToStereo

 * Working

MergeChannels

 * Working

GetChannel family

 * Working

KillVideo / KillAudio

 * Working

ConvertAudio family

 * Working

## Cache

Cache / InternalCache

 * Not intended for end-users and not testable

## Core

AlignPlanar

 * API function. Not intended for end-users and not testable.

Compare

 * Not working. Will always claim colorspaces are not the same.

        BlankClip().KillAudio()
        Compare(last, last) # The colorspaces are obviously the same

ShowFrameNumber / ShowSMPTE / ShowTime / Subtitle

 * Timestamp display working
 * offset parameter working
 * text_color and halo_color working
 * font and size parameters working
 * Some text formatting is not implemented
   * [ShowFrameNumber] scroll parameter not working
   * Default text positioning is different from Windows for ShowX functions
   * align, spc, font_width, font_angle parameters, interlaced parameters are ignored

Info

 * Working on frame-based video
 * Not working on field-based video (does not print anything)

        ColorBars().Info() # This works
        ColorBars().SeparateFields().Info() # This doesn't work

## Convert

ConvertToYV12 / ConvertToYUY2

 * PC and TV levels working
 * Rec.601 and Rec.709 working
 * Interlaced conversion working

ConvertToRGB24 / ConvertToRGB32

 * Only TV levels working
 * Only Rec.601 working
 * Interlaced conversion working

ConvertBackToYUY2

 * Not necessary as the chroma shift bug in mainline Avisynth has been fixed

## Color

ColorYUV

 * gain, off, gamma, cont working
 * levels conversion working (TV->PC and PC->TV)
 * opt=coring working
 * autowhite, autogain working
 * showYUV working
 * analyze *not* working

## Combine

StackHorizontal / StackVertical/ ShowFiveVersions

 * working

Animate

 * working

ApplyRange

 * aborts with exception

        ColorBars().KillAudio()
        ApplyRange(1, 2, "Crop") # internal error occurs

## Conditional

ConditionalFilter

 * working

ScriptClip / FrameEvaluate:

 * after_frame working
 * show working

ConditionalReader:

 * bool, float, int working
 * range, interpolate, default working
 * show working

WriteFile family:

 * WriteFile, WriteFileIf, WriteFileStart working
 * WriteFileEnd not working (?)

        BlankClip()
        WriteFileEnd("writefile.txt", """ "The End" """) # Nothing is written

## Convolution

GeneralConvolution:

 * Working

## Debug

Null

 * Not testable

PlanarLegacyAlignment

 * Requires external plugins to test

ErrorHandlingExternal

 * Requires additional software to test

## Edit

Trim / FreezeFrame / DeleteFrame / DuplicateFrame

 * Working

AlignedSplice / UnalignedSplice

 * Working

AudioDub / AudioDubEx

 * Working

Dissolve

 * Working

FadeIn/Out/IO family

 * All functions except FadeIn/Out/IO0 truncate audio-only streams

        FadeIO2(Tone(length=3), 48, fps=48) # The total length should be 3.25s, but only 3s of audio is generated

## Field

All working (except Bob is not implemented).

## Focus

All working (except TemporalSoften is not implemented).

## FPS

All working (ConvertFPS in switch mode is not tested, but appears to be working).

## Histogram

Not tested thoroughly, but appears to be working.