
### 1. Install mjpg_streamer

```bash
sudo apt update
sudo apt install cmake libjpeg-dev
git clone https://github.com/jacksonliam/mjpg-streamer.git mjpg-streamer
cd mjpg-streamer/mjpg-streamer-experimental
make
sudo make install
```

###2. Start stream

```bash
mjpg_streamer -i "input_uvc.so -d /dev/video0 -r 1280x720 -f 30" -o "output_http.so -w ./www"
```

