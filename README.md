# Environment Set up for NMSU CS machine (Linux Server) 
This tutorial outlines the steps to set up a Federated Learning (FL) environment on the CS machine.

## Install Anaconda on the CS machine. If you have already installed Anaconda, please skip steps 1~3
1. You can download either Anaconda or miniconda <br/>
```wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh```

2. Find your download file and install by using the following command <br/>
```bash Miniconda3-latest-Linux-x86_64.sh```

3. Add anaconda path into the system, find the path of your conda bin file, and export the path <br/>
```export PATH=/home/jliu/miniconda3/bin:$PATH```<br/>
If it does not work, you need to add the previous command to .bashrc and restart your terminal. 

###### Put Anaconda into the back_up folder 
4. Anaconda folder will be very big when you set up multiple environments. You will have a folder called student_no_backup, which has no space limitation. <br/>   
   *To put anaconda folder into student_no_backup folder <br/>
```mv ~/anaconda3 /home/student_no_backup/<your_cs_username>/```

   *Link Anaconda to your home directory  <br/>
```ln -s /home/student_no_backup/<your_cs_username>/anaconda3 ~/anaconda3```

**More information on Trung's notes [link](https://github.com/huipingcao/papers)**

## setup new environment in Anaconda
5. Create a new environment with the name "FL_env" <br/>
```conda create --name FL_env```

6. You can check your environment list <br/>
```conda env list```

7. Switch to new environment <br/>
```conda activate FL_env```

8. Install a specific version of libraries <br/>
```conda install python=3.9```<br/>

To install the newest PyTorch version, please visit [PyTorch](https://pytorch.org/)<br/>
```conda install pytorch torchvision torchaudio pytorch-cuda=11.7 -c pytorch -c nvidia```<br/>

To insall flowers for **federated learning** virtual netwrok please visit [flower](https://flower.dev/docs/installation.html)<br/>
```python -m pip install flwr```<br/>

You might also need to install another related library: <br/>
```
   pip install scikit-learn
   pip install numpy 
   pip install pandas
```

> requirements.txt contains all libraries with versions, it might not contain the newest version for all the libraries
If you want to directly install all the libraries, run 
```pip install -r requirements.txt``` after step 8.


## Another useful command
If your FL program terminated unusual the virtual network address is still running. You can use the  following command to check all running network ports <br/>
```ss -lntu```<br/>

If you want to find a specific port, you can use <br/>
```fuser 8080/tcp```

To kill the port process <br/>
```fuser -k 8080/tcp```


## Setup FL environment on Mac
It may contain errors if you use conda to install Flower. You can install all the libraries in **PyCharm**, search "flwr" in the PyCharm interpreter, and install it.  
