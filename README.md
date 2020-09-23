<div align="center">

## Play \.WAV \(example 1\)


</div>

### Description

Check if soundcard exist and then play a wave-file. http://137.56.41.168:2080/VisualBasicSource/vb4playwav.txt
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Found on the World Wide Web](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/found-on-the-world-wide-web.md)
**Level**          |Unknown
**User Rating**    |4.2 (161 globes from 38 users)
**Compatibility**  |VB 3\.0, VB 4\.0 \(16\-bit\), VB 4\.0 \(32\-bit\), VB 5\.0, VB 6\.0
**Category**       |[Windows System Services](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/windows-system-services__1-35.md)
**World**          |[Visual Basic](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/visual-basic.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/found-on-the-world-wide-web-play-wav-example-1__1-682/archive/master.zip)

### API Declarations

```
Declare Function sndPlaySound Lib "winmm.dll" Alias "sndPlaySoundA" (ByVal lpszSoundName As String, ByVal uFlags As Long) As Long
Public Declare Function waveOutGetNumDevs Lib "winmm" () As Long
Global Const SND_SYNC = &H0 'just after the sound is ended exit function
Global Const SND_ASYNC = &H1 'just after the beginning of the sound exit function
Global Const SND_NODEFAULT = &H2 'if the sound cannot be found no error message
Global Const SND_LOOP = &H8 'repeat the sound until the function is called again
GLOBAL Const SND_NOSTOP = &H10 'if currently a sound is played the function will return without playing the selected sound
Global Const Flags& = SND_ASYNC Or SND_NODEFAULT
```


### Source Code

```
'Add the following code to the Command1_Click event on a form:
Private Sub Command1_Click()
'Add the following code to the Command1_Click event:
  Dim i As Long
  Const SoundFileName$ = "c:\sb16\samples\s_16_44.wav"
  i = waveOutGetNumDevs()
  If i > 0 Then  'There is at least one sound device.
	i& = sndPlaySound(SoundFileName$, Flags&)
  Else
   Beep
  End If
End Sub
```

