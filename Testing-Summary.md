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

 * Limited functionality. All clips are converted to RGB24 internally.

        BlankClip(pixel_type="YV12")
        Compare(last, last, "Y") # reports "invalid channel 'Y'"

        BlankClip(pixel_type="YV12")
        Compare(last, last, "R") # works

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

 * Working

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
 * analyze *not* working: Text rendering is distorted and upside down.

## Combine

StackHorizontal / StackVertical/ ShowFiveVersions

 * working

Animate

 * working

ApplyRange

 * Working

## Conditional

ConditionalFilter

 * Working

ScriptClip / FrameEvaluate:

 * after_frame working
 * show working

ConditionalReader:

 * bool, float, int working
 * range, interpolate, default working
 * show working

WriteFile family:

 * All working

## Convolution

GeneralConvolution:

 * Working

## Debug

Null

 * Not testable

PlanarLegacyAlignment

 * Requires external plugins to test

ErrorHandlingExternal

 * Working

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

 * Working

## Field

All working (except Bob is not implemented).

## Focus

All working (except TemporalSoften is not implemented).

## FPS

All working (ConvertFPS in switch mode is not tested, but appears to be working).

## Histogram

Not tested thoroughly, but appears to be working.

## Layer

All working (except Invert, Layer, Overlay, Mask, ColorKeyMask not implemented)

## Levels

Levels

 * Working

RGBAdjust

 * Working

Tweak

 * Working

Limiter

 * Working

## Merge

All working

## Misc

FixLuminance / FixBrokenChromaUpsampling / PeculiarBlend

 * These filters are obsolete and have not been tested.

## Planeswap

All working

## Resample

Avisynth resamplers have been remapped to libswscale functions. Point, Bilinear, Bicubic, Lanczos, and Spline algorithms are available. Only setting the target frame dimensions is currently supported. Counter-intuitively, the resizers are defined in Avxsynth core, but require the avxffms2 plugin to run.

## Resize

VerticalReduceBy2

 * The top line is handled differently from mainline Avisynth (see issue #22).

HorizontalReduceBy2

 * Working

ReduceBy2

 * See VerticalReduceBy2

## Source

BlankClip / Blackness

 * Working

MessageClip

 * Working

ColorBars

 * Working

Tone

 * Working

Version

 * Working, but dimensions and text have been updated to match new project.

## Transform

FlipVertical / FlipHorizontal

 * Working

Crop / CropBottom / LetterBox

 * Working

TurnLeft / TurnRight / Turn180

 * Working