# venv-pillow
Using a python3 venv virtual environment to install old version of pillow

# Intro.
Problem I had was that on ubuntu 14.04 pillow version 2.3.0 was installed and the rotate and resize 
functionality worked well with that but in ubuntu 16.04 pillow version 3.1.2 is installed

# Set up python3 for venv
sudo apt-get install python3-setuptools python3-dev build-essential

sudo apt-get install python3-venv

sudo apt-get install python3-pip

# libraries required for my usage of pillow, install before pillow install
sudo apt-get install libjpeg-dev

sudo apt-get install libfreetype6-dev

# set up venv and install pillow
cd your-venv-root-directory-name

pyvenv pillowtest

source pillowtest/bin/activate

pip3 install wheel 

pip3 install --no-cache-dir -I pillow==2.3.0

be aware to activate a virtual envrionment from a shell script I had to use the "." command rather than the "source" command

#ready to go!

nice, but be aware also the font directory names may have changed subtly as in my usage 
so check the font you use (if you use one) actually exists where it used to.

also reading the manuals discovered basically what has happened is that in PILLOW 3.2.0 an extra parameter has been added to the image.rotate command.

Image.rotate(90,expand=True)

but I wanted to test using venv or virtualenv, looks like venv works ok for simple level I require.

# finish and back to default python installation
deactivate
