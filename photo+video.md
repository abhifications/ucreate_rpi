## Taking Pictures and Videos with Webcam on Raspberry Pi

### 1. Install Required Software

Before you start, ensure that you have the necessary utilities installed on your Raspberry Pi.

```bash
sudo apt update
sudo apt install fswebcam
sudo apt install ffmpeg
```

### 2. Check that the webcam is listed as an output

```bash
lsusb
```

### 3. Capture a picture using the following command

```bash
fswebcam image.jpg
```

### 4. Capture a video using the following command:

```bash
ffmpeg -f v4l2 -framerate 30 -video_size 640x480 -i /dev/video0 video.mp4
```
