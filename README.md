# BioinformaticsUPF #

## How to start ##

First we need to download VirtualBox software to run the image of the course. 

### Donwload VirtualBox ###
#### Ubuntu 16.04 ####

First we will add the source list of VB to our host

```sudo nano /etc/apt/sources.list```

Then we will append the following line

```deb http://download.virtualbox.org/virtualbox/debian xenial contrib```

Press ```Ctrl+0``` to save and ```Ctrl+X``` to close the file

Now, we need the Oracle public key

```wget -q https://www.virtualbox.org/download/oracle_vbox_2016.asc -O- | sudo apt-key add -```

And finally, we will updater the index and install VB

```
sudo apt update
sudo apt install virtualbox-5.1
```

#### Windows ####

For Windows platform, we only need to go the the VirtualBox site and download the executable.
You can find it here ```https://www.virtualbox.org/wiki/Downloads```

#### MacOsX ####
_Coming soon..._

### Download the image ###

Download the VB image [VB](https://mega.nz/file/mNNzxKhC#YlcSU-xsldheWmCfJYP5P7sJAcvhPw7hkLIPtBvDuJY)

And we will get a file with the extension ```.ova``` 

### Run VB with our image ###

Now, open VirtualBox and follow the steps to import the image.

Click on ```File > Import Appliance``` (Image below)

![Image 001](https://github.com/edgano/BioinformaticsUPF/blob/master/resources/001.png) 

Then click on the icon on the right and select the image you have download in the step before

![Image 002](https://github.com/edgano/BioinformaticsUPF/blob/master/resources/002.png) 

Then, is just the 1st rule of ***Installation Guide***, it means...```Import>>Next>>Next>>...>>Accept``` at the end of the proccess it can take some time to import the image. Keep Calm

![Image 003](https://github.com/edgano/BioinformaticsUPF/blob/master/resources/003.png) 

The last step is to run the image. Select the image and click on ```Start``` and it will run and popup a new windows with all the enviroment and software ready to use.

![Image 004](https://github.com/edgano/BioinformaticsUPF/blob/master/resources/004.png) 

## Software Included ##
* Nextflow (ver. 0.26.4.4741)
* Python (ver. 2.7.12)
    + BioPython
* Blast (ver. 2.2.24)
* SeqAnn Package
* T_Coffee (dev@20171228_16:49)
* ViennaRNA Package (ver. 2.4.3)

We need to add some extra software in our image.

Open a text editor and copy this code:

```
wget http://evolution.gs.washington.edu/phylip/download/phylip-3.697.tar.gz
tar -zxvf phylip-3.697.tar.gz
cd phylip-3.697/src
make -f Makefile.unx install
cd ..
cd exe
export PATH=$PATH:$PWD
cd ../../
rm phylip-3.697.tar.gz
```
Save the file as ```installPhy.sh``` then change the permission of the file with this command ```chmod +x installPhy.sh``` and now run the script with ```./installPhy.sh```. It will install and configure the software ***PHYLIP***

## You can find the course material here: ```http://edgargarriga.com/2018_upf_bioinfo.zip``` ##
