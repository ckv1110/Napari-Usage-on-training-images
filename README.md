# Napari Usage on Training Images
## A tutorial and script for using napari to segment images
1. ### Installing anaconda and napari on Windows, Linux, and Intel-chip Macs
    - Anaconda installation can be found here: https://docs.anaconda.com/free/anaconda/install/index.html
    - After installation, you can launch it in terminal by typing `conda` in the terminal
    - Create an isolated environment in `conda` so you can install napari without fuss. 
        * `conda create -y -n napari-env -c conda-forge python=3.10`
    - Once it is created, you can enter the environment via: `conda activate napari-env`
        * Now that you are in the environment, you should see (napari-env) at the begining of your terminal
    - __Note! If you have an M-chip Mac, please skip to Step 2!__
    - Now, type in `python -m pip install "napari[all]"` to install napari within the environment
    - You can then upgrade the package by typing `python -m pip install "napari[all]" --upgrade`
    - To imrpove compatibility with opening images:
        * Get imagecodecs `python -m pip install -U "imagecodecs[all]"` or `conda install conda-forge::imagecodecs`
            - Either command will work the same.
    - Your Napari should be fully installed!
2. ### Installing anaconda and napari on M-chip Macs
    - After anaconda is installed and the environemnt is creted, enter the environment
    - Type this to install napari: `conda install -c conda-forge napari pyqt`
    - Upgrade napari via `conda update napari`
    - You will need imagecodecs to improve compatibility with opening images
        * `conda install conda-forge::imagecodecs`
3. ### Running Napari
    - You can simply open Napari by typing `napari` in the terminal
    - If a new napari window is opened, you will know that your installation is succesful and the program is working
4. ### Opening images and segmenting them
    - You can open images simply by dragging them into your napari viewing window or by accessing _File > Open File_
    ![Open file in napari](https://i.imgur.com/T3g1zm7.png)
    - Once the image is opened, you may create a __New Labels Layer__, which you can see where it is located in the image below
    ![Loaction of New Labels Layer](https://i.imgur.com/XOcwFtG.jpeg)
    - You will see this after the new labels layer is created. Here are some key parts that you will be using!
        * __Label tab__ __(1)__ - Important for selecting which class of tumour microenvironment to segment. Here is the convention that we are sticking with (The tumour microenvironment will correspond with the number):
            1. Normal Brain __(1)__
            2. Leading Edge of the Tumour __(2)__
            3. Tumour Core __(3)__
            4. Peri-Necrotic Zone __(4)__
            5. Necrotic Zone __(5)__
            - Note that we will be segmenting the entire tumour slide
            - You can use the + and - signs in the __label__ tab to switch labels to whichever tumour microenvironment class that you want to segment first 
        * __Paint Brush tool (Green box)__ - Useful for drawing boundaries for each tumour microenvironment class
        * __Paint Bucket tool (Red box)__ - Useful for filling in the drawn boundaries
            * _Note!_ By default, most of the shown tools at the top bar are hot keyed to the numbers shown below:
            1. Eraser __(1)__
            2. Paint Brush __(2)__
            3. Paint Bucket __(3)__
            4. Pick Mode __(4)__
            5. Move image __(5)__
            * __Important!__ Remember select the move image mode if you want to move the image. You might accidentally draw or paint bucket the entire image if you forget to select the move image mode!
        * __Opacity tab (2)__ - Useful for adjusting the transparency of your labels to aid in your segmentation process
        * __Brush Size tab (3)__ - To adjust your brush size tool
    ![Label layer overlay](https://i.imgur.com/Aj6kzAq.jpeg)

5. ### Saving Labels layer
    - Once you are happy with your segmentation of the 5 tumour microenvironment classes, you can save them by first selecting the labels layer and then saving it via _File > Save Selected Layer_ or `Ctrl/Cmd + S`
    - Please save it as a .tif file and with a reference to the case that you were working on!

I hope this tutorial helps and if you have any questions or issues please feel free to open an issue in the github repository and I will try my best to help you!