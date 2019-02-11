Sebastian Raschka, last updated: 02/11/2019

# PyTorch Installation Guide/Help for Enabling GPU Support

Here are some summarized steps for enabling GPU support for PyTorch.

## Installing PyTorch if you already have your graphic card configured

As I mentioned in class, PyTorch already brings its own CUDA & cuDNN binaries, so installing them seperately will not be necessary (unless you compile PyTorch from source).

You can check whether your NVIDIA graphic card drivers are properly installed by running

    nvidia-smi

in the command line. If everything works correctly, you should see something like this:

```
+-----------------------------------------------------------------------------+
| NVIDIA-SMI 410.78       Driver Version: 410.78       CUDA Version: 10.0     |
|-------------------------------+----------------------+----------------------+
| GPU  Name        Persistence-M| Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp  Perf  Pwr:Usage/Cap|         Memory-Usage | GPU-Util  Compute M. |
|===============================+======================+======================|
|   0  GeForce GTX 108...  Off  | 00000000:05:00.0  On |                  N/A |
| 25%   42C    P8    18W / 250W |    189MiB / 11175MiB |      0%      Default |
+-------------------------------+----------------------+----------------------+
|   1  GeForce GTX 108...  Off  | 00000000:06:00.0 Off |                  N/A |
| 25%   38C    P8    16W / 250W |      2MiB / 11178MiB |      0%      Default |
+-------------------------------+----------------------+----------------------+
|   2  GeForce GTX 108...  Off  | 00000000:09:00.0 Off |                  N/A |
| 25%   35C    P8    16W / 250W |      2MiB / 11178MiB |      0%      Default |
+-------------------------------+----------------------+----------------------+
|   3  GeForce GTX 108...  Off  | 00000000:0A:00.0 Off |                  N/A |
| 25%   26C    P8    17W / 250W |      2MiB / 11178MiB |      0%      Default |
+-------------------------------+----------------------+----------------------+
```

If that's not the case, please move forward to the next section. Otherwise, you
can install PyTorch by selecting the appropriate installer from https://pytorch.org.

Then, after installing PyTorch, you can verify CUDA support by executing the following
code in Python:

    import torch
    torch.cuda.is_available()

(It should return `True`.)

## If you are setting up a new environment

This section goes through the basic steps for setting up a fresh OS installation (i.e., **Ubuntu 18.04** in this example) for PyTorch with CUDA support. (For more details, please see: https://sebastianraschka.com/pdf/books/dlb/appendix_cloud-computing.pdf)


### Step 1: Updating existing packages

Update your existing packages via

    sudo apt-get update
    sudo apt-get upgrade

### Step 2: Install basic system packages

sudo apt-get install -y build-essential \
g++ gfortran git libfreetype6-dev libxft-dev \
libncurses-dev libopenblas-dev libblas-dev \
liblapack-dev libatlas-base-dev \
linux-headers-generic linux-image-extra-virtual \
zlib1g-dev libcurl3-dev

### Step 3: Install NVIDIA drivers (Part 1)

Check what graphics card you have via 

    lspci -nnk | grep -i

Then, get the latest graphics card driver from http://www.nvidia.com/Download/index.aspx:

- select your graphics card from the menu and click on "Search"
- on the next page, click "Download"
- a new page will load, which contains another "Download" button: right-click on that button and select "copy link"

Then, download the driver via the link copied above via `wget`. E.g.,

    wget http://us.download.nvidia.com/XFree86/Linux-x86_64/410.93/NVIDIA-Linux-x86_64-410.93.run

Run the installer via

    bash NVIDIA-Linux-x86_64-410.93.run

and follow the on-screen instructions.

### Step 4: Install NVIDIA drivers (Part 2)

After downloading and installing the NVIDIA drivers (part 1), we need to blacklist the default Linux graphics card driver (called `noveau`, which is a reverse-engineered open-source version of the NVIDIA driver). 

Use the following to open (or create) the config file:

    sudo vi /etc/modprobe.d/blacklist-nouveau.conf

Enter the following information:

    blacklist nouveau
    options nouveau modeset=0

and then save and close the file.

Finally, we need to update the "inital RAM file system" by executing the following:

    sudo update-initramfs -u

### Step 5: Install Miniconda

You can skip this step if you have Miniconda already installed.

    wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
    sudo bash Miniconda3-latest-Linux-x86_64.sh

(Follow the installation instructions shown on your screen.)

### Step 7: Install PyTorch

See the section at the top of this document entitled "Installing PyTorch if you already have your graphic card configured."

---

- For more details, please see: https://sebastianraschka.com/pdf/books/dlb/appendix_cloud-computing.pdf

---

### Additional tips

Additional tips I received from a student in the class (Yien Xu)

> I have finally managed to install PyTorch v1.0 with GPU support on my Ubuntu 18.04 machine. Here's what I've done:

- Make sure to install an up-to-date driver. Mine is nvidia-driver-390.
- install anaconda w/ python 3.7
- create a new conda env: 
   - `conda create -n torch anaconda (this comes with all anaconda default packages)`
- switch to that env: 
-    `conda activate torch`
- Install pytorch (w/ CUDA 9.0)
   - `conda install pytorch torchvision -c pytorch`
   - Note that even though ubuntu 18.04 does not officially support CUDA 9.0, this command still works fine
- Reboot    **this is very important**
- switch to torch env again
- run   `python -c "import torch; print(torch.cuda.is_available())"`  to verify
- What's important is that there is no need to install CUDA. CUDA is installed together with pytorch itself. There is also no need to change PATH or LD_LIBRARY_PATH, as conda does these steps automatically. 
- Hope this will be helpful for other students taking 479 next semester:)