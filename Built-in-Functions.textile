Built in Functions

h1. Audio

{background:#ddd}. |_. Function |_. Ported |_. Tested |_. Notes |
|<. DelayAudio|<. Yes |<. Yes |<.  |
|<. AmplifydB|<. Yes |<. Yes  |<.  |
|<. Amplify|<. Yes |<. Yes  |<.  |
|<. AssumeSampleRate|<. Yes |<. Yes  |<.  |
|<. Normalize|<. Yes |<. Yes  |<.  |
|<. MixAudio|<. Yes |<. Yes  |<.  |
|<. ResampleAudio|<. Yes |<. Yes  |<.  |
|<. ConvertToMono|<. Yes |<. Yes  |<.  |
|<. EnsureVBRMP3Sync|<. Yes |<. No  |<. Not tested as simultaneous A/V is not supported |
|<. MergeChannels|<. Yes |<. Yes  |<.  |
|<. MonoToStereo|<. Yes |<. Yes  |<.  |
|<. GetLeftChannel|<. Yes |<. Yes  |<.  |
|<. GetRightChannel|<. Yes |<. Yes  |<.  |
|<. GetChannel|<. Yes |<. Yes  |<.  |
|<. GetChannels|<. Yes |<. Yes  |<.  |
|<. KillVideo|<. Yes |<. Yes  |<.  |
|<. KillAudio|<. Yes |<. Yes  |<.  |
|<. ConvertAudioTo16bit|<. Yes |<. Yes  |<.  |
|<. ConvertAudioTo8bit|<. Yes |<. Yes  |<.  |
|<. ConvertAudioTo24bit|<. Yes |<. Yes  |<.  |
|<. ConvertAudioTo32bit|<. Yes |<. Yes  |<.  |
|<. ConvertAudioToFloat|<. Yes |<. Yes  |<.  |
|<. ConvertAudio|<. Yes |<. Yes  |<.  |


h1. Cache

{background:#ddd}. |_. Function |_. Ported |_. Tested |_. Notes |
|<. Cache|<. Yes |<. Not testable |<. Not intended for end-users |
|<. InternalCache|<. Yes |<. Not testable |<. Not intended for end-users |

h1. Core

{background:#ddd}. |_. Function |_. Ported |_. Tested |_. Notes |
|<. AlignPlanar |<. Yes |<. Not testable |<. API function. Not intended for end-users. |
|<. Compare|<. Yes |<. Yes |<. Limited functionality. All clips are converted to RGB24 internally. |
|<. ShowFrameNumber|<. Yes |<. Some functionalities |<. [ShowFrameNumber] scroll parameter not working. Default text positioning is different from Windows for ShowX functions. align, spc, font_width, font_angle parameters, interlaced parameters are ignored. |
|<. ShowSMPTE|<. Yes |<. Some functionalities |<. Default text positioning is different from Windows for ShowX functions. align, spc, font_width, font_angle parameters, interlaced parameters are ignored. |
|<. ShowTime|<. Yes |<. Some functionalities |<. Default text positioning is different from Windows for ShowX functions. align, spc, font_width, font_angle parameters, interlaced parameters are ignored. |
|<. Info|<. Yes |<. Yes |<.  |
|<. Subtitle|<. Yes |<. Some functionalities |<. Default text positioning is different from Windows for ShowX functions. align, spc, font_width, font_angle parameters, interlaced parameters are ignored. |

h1. Convert

{background:#ddd}. |_. Function |_. Ported |_. Tested |_. Notes |
|<. ConvertToRGB |<.  Yes |<. Some functionalities |<.  MMX and SSE not ported. PC levels and Rec. 709 not working. |
|<. ConvertToRGB24 |<.  Yes |<. Some functionalities |<.  MMX and SSE not ported. PC levels and Rec. 709 not working. |
|<. ConvertToRGB32 |<.  Yes |<. Some functionalities |<.  MMX and SSE not ported. PC levels and Rec. 709 not working. |
|<. ConvertToYV12|<.  Yes |<. Yes |<.  MMX and SSE not ported |
|<. ConvertToYUY2|<.  Yes |<. Yes |<.  MMX and SSE not ported |
|<. ConvertBackToYUY2|<.  Yes |<. Not necessary |<.  MMX and SSE not ported. Not necessary as the chroma shift bug in mainline Avisynth has been fixed. |

h1. Color

{background:#ddd}. |_. Function |_. Ported |_. Tested |_. Notes |
|<. ColorYUV |<. Yes |<. Some functionalities |<. Analyze not working. |

h1. Combine

{background:#ddd}. |_. Function |_. Ported |_. Tested |_. Notes |
|<. StackVertical|<.  Yes |<. Yes |<.  |
|<. StackHorizontal|<.  Yes |<. Yes |<.  |
|<. ShowFiveVersions|<.  Yes |<. Yes |<.  |
|<. Animate|<.  Yes |<. Yes |<.  |
|<. ApplyRange|<.  Yes |<. Yes |<.  |

h1. Conditional

{background:#ddd}. |_. Function |_. Ported |_. Tested |_. Notes |
|<. ConditionalFilter|<. Yes |<. Yes |<.  |
|<. ScriptClip|<. Yes |<. Yes |<.  |
|<. ConditionalReader|<. Yes |<. Yes |<.  |
|<. WriteFile|<. Yes |<. Yes |<.  |
|<. WriteFileIf|<. Yes |<. Yes |<.  |
|<. WriteFileStart|<. Yes |<. Yes |<.  |
|<. WriteFileEnd|<. Yes |<. Yes |<.  |

h1. Convolution

{background:#ddd}. |_. Function |_. Ported |_. Tested |_. Notes |
|<. Convolution|<. Yes |<. Yes |<. |

h1. Debug

{background:#ddd}. |_. Function |_. Ported |_. Tested |_. Notes |
|<. Null|<.  Yes |<. Not testable |<.  |
|<. PlanarLegacyAlignment|<.  Yes |<. Not testable |<. Requires external plugins to test |
|<. ErrorHandlingExternal|<.  Yes |<. Yes |<. New command added by AvxSynth |

h1. Edit

{background:#ddd}. |_. Function |_. Ported |_. Tested |_. Notes |
|<. Trim|<.  Yes |<. Yes |<.  |
|<. FreezeFrame|<.  Yes |<. Yes |<.  |
|<. DeleteFrame|<.  Yes |<. Yes |<.  |
|<. DuplicateFrame|<.  Yes |<. Yes |<.  |
|<. UnalignedSplice|<.  Yes |<. Yes |<.  |
|<. AlignedSplice|<.  Yes |<. Yes |<.  |
|<. AudioDub|<.  Yes |<. Yes |<.  |
|<. AudioDubEx|<.  Yes |<. Yes |<.  |
|<. Dissolve|<.  Yes |<. Yes |<.  MMX and SSE not ported |
|<. FadeOut0|<.  Yes |<. Yes |<.  MMX and SSE not ported |
|<. FadeOut|<.  Yes |<. Yes |<.  MMX and SSE not ported |
|<. FadeOut2|<.  Yes |<. Yes |<.  MMX and SSE not ported |
|<. FadeIn|<.  Yes |<. Yes |<.  MMX and SSE not ported |
|<. FadeIn2|<.  Yes |<. Yes |<.  MMX and SSE not ported |
|<. FadeIO|<.  Yes |<. Yes |<.  MMX and SSE not ported |
|<. FadeIO2|<.  Yes |<. Yes |<.  MMX and SSE not ported |
|<. Loop|<.  Yes |<.  |<.  MMX and SSE not ported |

h1. Field

{background:#ddd}. |_. Function |_. Ported |_. Tested |_. Notes |
|<. ComplementParity|<.  Yes |<. Yes |<.  |
|<. AssumeTFF|<.  Yes |<. Yes |<.  |
|<. AssumeBFF|<.  Yes |<. Yes |<.  |
|<. AssumeFieldBased|<.  Yes |<. Yes |<.  |
|<. AssumeFrameBased|<.  Yes |<. Yes |<.  |
|<. SeparateFields|<.  Yes |<. Yes |<.  |
|<. Weave|<.  Yes |<. Yes |<.  |
|<. DoubleWeave|<.  Yes |<. Yes |<.  |
|<. Pulldown|<.  Yes |<. Yes |<.  |
|<. SelectEvery|<.  Yes |<. Yes |<.  |
|<. SelectEven|<.  Yes |<. Yes |<.  |
|<. SelectOdd|<.  Yes |<. Yes |<.  |
|<. Interleave|<.  Yes |<. Yes |<.  |
|<. SwapFields|<.  Yes |<. Yes |<.  |
|<. Bob|<.  No |<. No |<.  |
|<. SelectRangeEvery|<.  Yes |<. Yes |<.  |

h1. Focus

{background:#ddd}. |_. Function |_. Ported |_. Tested |_. Notes |
|<. Blur|<.  Yes |<. Yes |<.  MMX and SSE not ported |
|<. Sharpen|<.  Yes |<. Yes |<.  MMX and SSE not ported |
|<. TemporalSoften|<.  No |<. No |<.  |
|<. SpatialSoften|<.  Yes |<. Yes |<.  |

h1. Fps

{background:#ddd}. |_. Function |_. Ported |_. Tested |_. Notes |
|<. AssumeFPS|<.  Yes |<. Yes |<.  |
|<. ChangeFPS|<.  Yes |<. Yes |<.  |
|<. ConvertFPS|<.  Yes |<. Appears to be |<. Not tested, but appears to be working |

h1. Grayscale

{background:#ddd}. |_. Function |_. Ported |_. Tested |_. Notes |
|<. Grayscale|<. Yes |<. No |<. MMX and SSE not ported |

h1. Histogram

{background:#ddd}. |_. Function |_. Ported |_. Tested |_. Notes |
|<. Histogram|<. Yes |<. Appears to be |<. Not thoroughly tested, but appears to be working |

h1. Layer

{background:#ddd}. |_. Function |_. Ported |_. Tested |_. Notes |
|<. Mask|<.  No |<. No |<.  |
|<. ColorKeyMask|<.  No |<. No |<.  |
|<. ResetMask|<.  Yes |<. Yes |<.  |
|<. Invert|<.  No |<. No |<.  |
|<. ShowAlpha|<.  Yes |<. Yes |<.  |
|<. ShowRed|<.  Yes |<. Yes |<.  |
|<. ShowGreen|<.  Yes |<. Yes |<.  |
|<. ShowBlue|<.  Yes |<. Yes |<.  |
|<. MergeRGB|<.  Yes |<. Yes |<.  |
|<. MergeARGB|<.  Yes |<. Yes |<.  |
|<. Layer|<.  No |<. No |<.  |
|<. Subtract|<.  Yes |<. Yes |<.  |

h1. Levels

{background:#ddd}. |_. Function |_. Ported |_. Tested |_. Notes |
|<. Levels|<.  Yes |<. Yes |<.  |
|<. RGBAdjust|<.  Yes |<. Yes |<.  |
|<. Tweak|<.  Yes |<. Yes |<.  |
|<. Limiter|<.  Yes |<. Yes |<.  |

h1. Merge

{background:#ddd}. |_. Function |_. Ported |_. Tested |_. Notes |
|<. Merge|<.  Yes |<. Yes |<.  MMX and SSE not ported |
|<. MergeChroma|<.  Yes |<. Yes |<.  MMX and SSE not ported |
|<. MergeLuma|<.  Yes |<. Yes |<.  MMX and SSE not ported |

h1. Misc

{background:#ddd}. |_. Function |_. Ported |_. Tested |_. Notes |
|<. FixLuminance|<.  Yes |<. No |<. Obsoleted |
|<. FixBrokenChromaUpsampling|<.  Yes |<. No |<. Obsoleted |
|<. PeculiarBlend|<.  Yes |<. No |<. Obsoleted |

h1. Planeswap

{background:#ddd}. |_. Function |_. Ported |_. Tested |_. Notes |
|<. SwapUV|<.  Yes |<. Yes |<.  MMX and SSE not ported |
|<. UToY|<.  Yes |<. Yes |<.  MMX and SSE not ported |
|<. VToY|<.  Yes |<. Yes |<.  MMX and SSE not ported |
|<. YToUV|<.  Yes |<. Yes |<.  MMX and SSE not ported |

h1. Resample

{background:#ddd}. |_. Function |_. Ported |_. Tested |_. Notes |
|<. PointResize|<.  No, but invokes SWScale external plugin |<. Yes |<.  Need SWScale |
|<. BilinearResize|<.  No, but invokes SWScale external plugin |<. Yes |<.  Need SWScale |
|<. BicubicResize|<.  No, but invokes SWScale external plugin |<. Yes |<.  Need SWScale |
|<. LanczosResize|<.  No, but invokes SWScale external plugin |<. Yes |<.  Need SWScale |
|<. Lanczos4Resize|<.  No, but invokes SWScale external plugin |<. Yes |<.  Need SWScale. Mapped to Lanczos algorithm in sws. |
|<. BlackmanResize|<.  No, but invokes SWScale external plugin |<. Yes |<.  Need SWScale. Mapped to Lanczos algorithm in sws. |
|<. Spline16Resize|<.  No, but invokes SWScale external plugin |<. Yes |<.  Need SWScale. Mapped to Spline algorithm in sws. |
|<. Spline36Resize|<.  No, but invokes SWScale external plugin |<. Yes |<.  Need SWScale. Mapped to Spline algorithm in sws. |
|<. Spline64Resize|<.  No, but invokes SWScale external plugin |<. Yes |<.  Need SWScale. Mapped to Spline algorithm in sws. |
|<. GaussResize|<.  No, but invokes SWScale external plugin |<. Yes |<.  Need SWScale |

h1. Resize

{background:#ddd}. |_. Function |_. Ported |_. Tested |_. Notes |
|<. VerticalReduceBy2|<.  Yes |<. Partial |<.  MMX and SSE not ported. The top line is handled differently from mainline Avisynth (see issue #22). |
|<. HorizontalReduceBy2|<.  Yes |<. Yes |<.  MMX and SSE not ported |
|<. ReduceBy2|<.  Yes |<. Partial |<.  MMX and SSE not ported. The top line is handled differently from mainline Avisynth (see issue #22). |

h1. Script

{background:#ddd}. |_. Function |_. Ported |_. Tested |_. Notes |
|<. muldiv|<.  Yes |<. No |<.  |
|<. floor|<.  Yes |<. No |<.  |
|<. ceil|<.  Yes |<. No |<.  |
|<. round|<.  Yes |<. No |<.  |
|<. sin|<.  Yes |<. No |<.  |
|<. cos|<.  Yes |<. No |<.  |
|<. pi|<.  Yes |<. No |<.  |
|<. log|<.  Yes |<. No |<.  |
|<. exp|<.  Yes |<. No |<.  |
|<. pow|<.  Yes |<. No |<.  |
|<. sqrt|<.  Yes |<. No |<.  |
|<. abs|<.  Yes |<. No |<.  |
|<. abs (f)|<.  Yes |<. No |<.  |
|<. sign|<.  Yes |<. No |<.  |
|<. lcase|<.  Yes |<. No |<.  |
|<. ucase|<.  Yes |<. No |<.  |
|<. strlen|<.  Yes |<. No |<.  |
|<. revstr|<.  Yes |<. No |<.  |
|<. leftstr|<.  Yes |<. No |<.  |
|<. midstr|<.  Yes |<. No |<.  |
|<. rightstr|<.  Yes |<. No |<.  |
|<. rand|<.  Yes |<. No |<.  |
|<. Select|<.  Yes |<. No |<.  |
|<. nop|<.  Yes |<. No |<.  |
|<. width|<.  Yes |<. No |<.  |
|<. height|<.  Yes |<. No |<.  |
|<. framecount|<.  Yes |<. No |<.  |
|<. framerate|<.  Yes |<. No |<.  |
|<. frameratenumerator|<.  Yes |<. No |<.  |
|<. frameratedenominator|<.  Yes |<. No |<.  |
|<. audiorate|<.  Yes |<. No |<.  |
|<. audiolength|<.  Yes |<. No |<.  |
|<. audiolengthf|<.  Yes |<. No |<.  |
|<. audiochannels|<.  Yes |<. No |<.  |
|<. audiobits|<.  Yes |<. No |<.  |
|<. IsAudioFloat|<.  Yes |<. No |<.  |
|<. IsAudioInt|<.  Yes |<. No |<.  |
|<. IsRGB|<.  Yes |<. No |<.  |
|<. IsYUY2|<.  Yes |<. No |<.  |
|<. IsYUV|<.  Yes |<. No |<.  |
|<. IsYV12|<.  Yes |<. No |<.  |
|<. IsPlanar|<.  Yes |<. No |<.  |
|<. IsInterleaved|<.  Yes |<. No |<.  |
|<. IsRGB24|<.  Yes |<. No |<.  |
|<. IsRGB32|<.  Yes |<. No |<.  |
|<. IsFieldBased|<.  Yes |<. No |<.  |
|<. IsFrameBased|<.  Yes |<. No |<.  |
|<. GetParity|<.  Yes |<. No |<.  |
|<. String|<.  Yes |<. No |<.  |
|<. IsBool|<.  Yes |<. No |<.  |
|<. IsInt|<.  Yes |<. No |<.  |
|<. IsString|<.  Yes |<. No |<.  |
|<. IsClip|<.  Yes |<. No |<.  |
|<. Defined|<.  Yes |<. No |<.  |
|<. Default|<.  Yes |<. No |<.  |
|<. Eval|<.  Yes |<. No |<.  |
|<. Apply|<.  Yes |<. No |<.  |
|<. Import|<.  Yes |<. No |<.  |
|<. Assert|<.  Yes |<. No |<.  |
|<. Assert (s)|<.  Yes |<. No |<.  |
|<. SetMemoryMax|<.  Yes |<. No |<.  |
|<. SetWorkingDir|<.  Yes |<. No |<.  |
|<. Chr|<.  Yes |<. No |<.  |
|<. Time|<.  Yes |<. No |<.  |
|<. Spline|<.  Yes |<. No |<.  |
|<. int|<.  Yes |<. No |<.  |
|<. frac|<.  Yes |<. No |<.  |
|<. float|<.  Yes |<. No |<.  |
|<. value|<.  Yes |<. No |<.  |
|<. hexvalue|<.  Yes |<. No |<.  |
|<. VersionNumber|<.  Yes |<. No |<.  |
|<. VersionString|<.  Yes |<. No |<.  |
|<. HasVideo|<.  Yes |<. No |<.  |
|<. HasAudio|<.  Yes |<. No |<.  |
|<. Min|<.  Yes |<. No |<.  |
|<. Max|<.  Yes |<. No |<.  |

h1. Source

{background:#ddd}. |_. Function |_. Ported |_. Tested |_. Notes |
|<. BlankClip|<.  Yes |<. Yes |<.  |
|<. Blackness|<.  Yes |<. Yes |<.  |
|<. MessageClip|<.  Yes |<. Yes |<.  |
|<. ColorBars|<.  Yes |<. Yes |<.  |
|<. Tone|<.  Yes |<. Yes |<.  |
|<. Version|<.  Yes |<. Yes |<. Dimensions and text have been updated to match new project. |

h1. Transform

{background:#ddd}. |_. Function |_. Ported |_. Tested |_. Notes |
|<. FlipVertical|<.  Yes |<. Yes |<.  |
|<. FlipHorizontal|<.  Yes |<. Yes |<.  |
|<. Crop|<.  Yes |<. Yes |<.  |
|<. CropBottom|<.  Yes |<. Yes |<.  |
|<. AddBorders|<.  Yes |<. Yes |<.  |
|<. Letterbox|<.  Yes |<. Yes |<.  |

h1. Turn

{background:#ddd}. |_. Function |_. Ported |_. Tested |_. Notes |
|<. TurnLeft|<.  Yes |<. Yes |<.  |
|<. TurnRight|<.  Yes |<. Yes |<.  |
|<. Turn180|<.  Yes |<. Yes |<.  |
