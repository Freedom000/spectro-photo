# spectro-photo
Turns an image into an audio file. Image is visible on the spectrogram. 
<img src = "face.png"/>
##Building
```bash
git clone https://github.com/kylophone/spectro-photo
cd spectro-photo
gcc ./spectro-photo.c -o spectrophoto -std=c99 -lm -O3
```
##Usage
```
spectrophoto in.jpg out.raw
```
##Output
This will generate a 48k/32-bit floating point raw PCM file. You can listen to it with SoX like this:

`play -c 1 -r 48000 -b 32 -e float -t raw out.raw`

Generating a spectrogram with SoX looks like this:

`sox -c 1 -r 48000 -b 32 -e float -t raw out.raw -n spectrogram`
