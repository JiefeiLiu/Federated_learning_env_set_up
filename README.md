# Federated Learning(FL) Environment Set up for NMSU CS machine
This is a tutorial to set up an environment on CS machine 

## Install Anaconda on CS machine, if you already installed Anaconda please skip step 1~3
1. You can download either download Anaconda or miniconda <br/>
```wget http://repo.continuum.io/archive/Anaconda3-4.0.0-Linux-x86_64.sh```

2. Find your download file and install by using following command <br/>
```bash Anaconda3-4.0.0-Linux-x86_64.sh```

3. Add anaconda path into system <br/>
```export PATH=/home/hchen/anaconda3/bin:$PATH```
If it does not work you needs to add previous command into .bashrc and restart your terminal. 

###### Put Anaconda into back_up folder 
4. Anaconda folder will be very big when you set up mutiple environments. You will have a folder called student_no_backup which has no space limitation. <br/>   
   *To put anaconda folder into student_no_backup folder <br/>
```mv ~/anaconda3 /home/student_no_backup/<your_cs_username>/```

   *Link Anaconda to your home directory  <br/>
```ln -s /home/student_no_backup/<your_cs_username>/anaconda3 ~/anaconda3```

**More information on Trung's notes [link](https://github.com/huipingcao/papers)**

## setup new environment in anaconda
5. Create new environement with name "FL_env" <br/>
```conda create --name FL_env```

6. You can check your environment list <br/>
```conda env list```

7. Switch to new environment <br/>
```conda activate FL_env```

8. Install specific version of libraries <br/>
```conda install python=3.9```<br/>

To install newest pytorch version please visit [PyTorch](https://pytorch.org/)<br/>
```conda install pytorch torchvision torchaudio cudatoolkit=11.6 -c pytorch -c conda-forge```<br/>

To insall flowers for **federated learning** virtual netwrok please visit [flower](https://flower.dev/docs/installation.html)<br/>
```python -m pip install flwr```<br/>

You might also need install another related libraries: <br/>
```
   pip install sklearn
   pip install numpy 
   pip install pandas
```

> requirements.txt contains all libraries with versions, it might not contains the newest verion for all the libraries
if you want to directly install all the libraries, under your conda environment run 
```pip install -r requirements.txt```


## Another useful commonds
If your FL program terminated unusual the virtual network address still running you can use following command to check all running network ports <br/>
```ss -lntu```<br/>

If you want to find specific port you can use <br/>
```fuser 8080/tcp```

To kill port process <br/>
```fuser -k 8080/tcp```


## Setup FL environment on Mac
It might have some errors if you use conda to install flower, you can install all the libraries in **PyCharm**, Search "flwr" in pycharm interpreter, and install it.  
