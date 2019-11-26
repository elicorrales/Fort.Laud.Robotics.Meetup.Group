In order to get the Raspberry to stream video images from the webcam,you might use the following, based on 'mjpg-streamer'.

This assumes we are dealing with a USB webcam.  I have not used any of this with the picamera.

On your Raspberry Pi, do:

git clone https://github.com/jacksonliam/mjpg-streamer.git

Then cd (change directory) into the mjpg-streamer that was just downloaded.   Then cd again to mjpg-streamer-experimental.

If your Raspberry Pi is up-to-date, you should only have to do:

make
sudo make install

And that's it, you now have mjpg-streamer.

If the make fails, 

do 'sudo apt-get install -y cmake libjpeg8-dev' .

if you don't have 'cmake', then first do a  'sudo apt-get install -y cmake' .

Try doing 'make' again in the mjpg-streamer/mjpg-streamer-experimental directory.

There is a helpful script in this github section to help you run mjpg-streamer and view live feed.
