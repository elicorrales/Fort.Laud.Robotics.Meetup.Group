
# the complete installation reference URL:

https://www.pyimagesearch.com/2019/09/16/install-opencv-4-on-raspberry-pi-4-and-raspbian-buster/


# Step 1: (optional) gain more SDCARD space; remove unneed software

sudo apt-get purge -y wolfram-engine; echo;echo;echo;
sudo apt-get purge -y libreoffice*; echo;echo;echo;
sudo apt-get clean; echo;echo;echo;
sudo apt-get autoremove -y; echo;echo;echo;


# Step 2: install dependencies

sudo apt-get install -y build-essential cmake pkg-config;

sudo apt-get install -y libjpeg-dev libtiff5-dev libjasper-dev libpng-dev;

sudo apt-get install -y libavcodec-dev libavformat-dev libswscale-dev libv4l-dev;

sudo apt-get install -y libxvidcore-dev libx264-dev;

sudo apt-get install -y libfontconfig1-dev libcairo2-dev;

sudo apt-get install -y libgdk-pixbuf2.0-dev libpango1.0-dev;

sudo apt-get install -y libgtk2.0-dev libgtk-3-dev;

sudo apt-get install -y libatlas-base-dev gfortran

sudo apt-get install -y libhdf5-dev libhdf5-serial-dev libhdf5-103

sudo apt-get install -y libqtgui4 libqtwebkit4 libqt4-test python3-pyqt5

sudo apt-get install -y python3-dev


# Step 3: create virtual python environment (need pip, virtualenv , virtualenvwrapper)

wget https://bootstrap.pypa.io/get-pip.py

sudo python get-pip.py

sudo python3 get-pip.py

sudo rm -rf ~/.cache/pip

sudo pip install virtualenv virtualenvwrapper


# Step 4: EDIT .bashrc, add to bottom:

export WORKON_HOME=$HOME/.virtualenvs <br/>
export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3 <br/>
source /usr/local/bin/virtualenvwrapper.sh <br/>


# Steo 5: save, exit .bashrc, reload:

source ~/.bashrc


# Step 6: now create the virtual environment (we're calling it 'cv')

mkvirtualenv cv -p python3


# Step 7: install opencv4 into 'cv' virtual environment using 'pip'

pip3 install opencv-contrib-python

pip3 install matplotlib

pip3 install numpy

pip3 install scipy

pip3 install scikit-learn

# Step 8: (might not need)
you may see an error trying to run your python OpenCV script.
if so, try this.  Notice that we are first defining and
assigning a new Bash env variable, and immediately on the
same line, starting the python3 interpretor.

Example:
LD_PRELOAD=/usr/lib/arm-linux-gnueabihf/libatomic.so.1.2.0   python3  myPythonOpenCvScript.py

if the above works, you could
create alias python command that pre loads a library
edit ~/.bashrc at bottom, add:

alias pythonOpenCV='LD_PRELOAD=/usr/lib/arm-linux-gnueabihf/libatomic.so.1.2.0 python3'

Example:
pythonOpenCV  myPythonOpenCvScript.py

