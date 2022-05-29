# ffmpeg quick docs


[ffmpeg](https://ffmpeg.org/download.html#build-windows) is awesome

## Install

execute the files directly from powershell or be lazy and copy into system32 folder to access from anywhere

## Basic Flow

 - open up file location in explorer
 - rename/copy the video to "`input`" (commands below assume it is an mp4 file)
 - shift+right click in the **folder** and click the option "`open powershell here`"
 - mess around with the ffmpeg command (possibly in notepad) and copy/paste (paste via right click)

## Basic Video Compression

quicky 720 compressor


```
ffmpeg -i input.mp4 -vcodec libx265 -crf 28 -vf scale=1280:720 output.mp4
```

### input file
`-i input.mp4` 

### output file
`output.mp4`

Note you can change the file type if you wanted an avi/mov/mkv or some other format and it will *mostly* auto magic it.

### Scale
`-vf scale=1280:720`


### basic compression
 `-vcodec libx265 -crf 20`
 
  - 0 = lossless
  - 51= horrible
  - 12-28 sane
 
 ### bitrate (crf alternative I think)
 `-b:v 1M`

## Audio to Video with a plain color

```
ffmpeg -f lavfi -i color=c=blue:s=1280x720 -i input.mp3 -shortest -fflags +shortest output.mp4
```
