# Easy4RTK

[[中]](./README-zh.md) &ensp; [[EN]](./README.md)

An easily ported Real-Time Kinematic (RTK) Toolbox coded in Python.

This is a part of open-source toolbox Easy4PNT. Other toolboxs of Easy4PNT is listed here (clicked to jump to the target): [[Easy4SPP]](https://github.com/alxanderjiang/Easy4SPP), [[Easy4B2b]](https://github.com/alxanderjiang/Easy4B2b), [[Easy4PPP]](https://github.com/alxanderjiang/Easy4PPP), [[Easy4PTK]](https://github.com/alxanderjiang/Easy4PTK).

## Quick Start
1. We provide a set of example data and a quick-start jupyter notebook tutorial "rtk_multi.ipynb". Make sure that you have sucessufully installed the Python as well as the numpy (for matrix computation), ipykernel (for running the Jupyter Notebook), numba (for accelerating Python computation).
2. Due to the file size limitation of github (no more than 25MB for a file), we compress the "data" and "nav_result" folders into zip files and uploaded them to the Cloud Drive ([[Google Driver]](https://drive.google.com/drive/folders/1jiUGXHMB1W6iSe09Hc1iVTmT-9wfPqOy?usp=drive_link) or [[Lanzou Driver]](https://wwbwg.lanzouv.com/b01bje99pa)). In order to try the provided example of C+E dual-frequency RTK solutions, you need first download and unzip the "data.zip" into the "data" folder in the project path. The example results for visualization is stored in 'nav_result.zip'. The above zip files are necessary to run Easy4PTK. 
3. After unzipping the "data" folder, run all the blocks of "rtk_multi.ipynb", you all get an Easy4PNT solution log file in form of ".npy". The running script is following the configuration block of "rtk_multi.ipynb": using the WUH2-HKCL baseline to conduct kinematic ultra-long distance RTK results. The details of configuration is shown in "rtk_multi.ipynb".
4. We provided an example of visualizing the solution log file. Run the visulization blocks of rtk_multi.ipynb, or run all the blocks of 'nav_result.ipynb'  you can get figures about the RTK convergence curve, receiver clock bias, dSTEC scatter and the residuls scatter plot.

## Downloading and preperations
1. Download the **zip pakeage directly** or using git clone by running the following commend:
```bash
git clone https://github.com/alxanderjiang/Easy4RTK.git
```
2. Download the "data.zip" and "nav_result.zip" files from Google Drive ([[https://drive.google.com/drive/folders/1jiUGXHMB1W6iSe09Hc1iVTmT-9wfPqOy?usp=drive_link]](https://drive.google.com/drive/folders/1jiUGXHMB1W6iSe09Hc1iVTmT-9wfPqOy?usp=drive_link))) or LanZou Drive ([[https://wwbwg.lanzouv.com/b01bje99pa]](https://wwbwg.lanzouv.com/b01bje99pa)) . 
3. Unzip the sample data folders: data.zip and nav_result.zip to the same path of Easy4RTK. If linux but no GUI, please run the following commends:

```bash
cd Easy4RTK
unzip data.zip
unzip nav_result.zip
```
4. Ensure that the numpy, tqdm, ipykernel, numba, Pyyaml and pyserial are available in your Python environment. If not, please run the following commends to install:

```bash
pip install numpy
pip install tqdm
pip install ipykernel
pip install numba
pip install Pyyaml
pip install pyserial
```

  numpy and tqdm is used in the core codes while ipykernel is necessary to run Jupyter Notebook tutorials. numba is used to accelerate the computation (this can be ignored by change all the "numba_inv" function to simple "inv()" function). Easy4RTK only supports running from the Jupyter Notebook with variables definition for post solving.
Some problems may happen when install or use numba because of laking the library scipy, please install it by running the following commends:

```bash
pip install scipy
```

## Pseudo-range Differential GNSS (DGNSS) mode

Easy4RTK provides pseudo-range differential GNSS (DGNSS) mode for low-cost single-frequency and non-carrier phase output devices such as smart phones. Run all the blocks of 'dgnss.ipynb', you can get "G+C" DGNSS static solutions of HKKT-HKSC basline in DOY 132, 2024. The figure below shows the positioning errors and residuals on L1 of this example results. The configurations are set in the third block, users can change it according to your own dataset. 

<img src=./image/dgnss.png>

## Single-frequency RTK mode

Easy4RTK provides traditional single-frequency RTK (SF-RTK) mode for carrier phase available devices. Run all the blocks of 'rtk_single_freq.ipynb', you can get BDS static SF-RTK solutions of WUH2-JFNG basline in DOY 131, 2023. The figure below shows the positioning errors and ambiguities on B1 of this example results. The configurations are set in the third block, users can change it according to your own dataset. 

<img src=./image/SFRTK.png>

## Dual-frequency RTK mode

Easy4RTK provides uncombined dual-frequency RTK (DF-RTK) mode for carrier phase available devices especially for those long or ultra long baseline users. Run all the blocks of 'rtk_multi.ipynb', you can get BDS+GAL kinematic DF-RTK solutions of WUH2-HKFN basline (about 900 km in length) in DOY 131, 2023. The figure below shows the positioning errors, dSTEC and residuals on B1 of this example as well as the HKCL-HKFN baseline (about 30 km in length) results. The configurations are set in the third block, users can change it according to your own dataset. 

<img src=./image/DFRTK.png>

## Contact Authors
All the libaries and softwares in this toolbox are coded by Zhuojun Jiang, Zeen Yang, Wenjing Huang, Chuang Qian from Wuhan University of Technology. Any commends or bug reports are welcomed by sending email to its0122112380219@163.com.
