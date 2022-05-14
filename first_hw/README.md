# machine-learning-and-neural-network
machine learning and neural network homework repo
### 1. download repo and install requirements
```
git clone repo.git
pip3 install -r requirements.txt
```
### 2. download mnist in program dir
链接: https://pan.baidu.com/s/1vR-izcak1sKpGNIftT1KxQ  密码: 4tet

### 3. train and test model
```
python train.py 'train'. # train
python train.py 'test' --model_dir 'mlp_best.npy' --params_dir 'params_best.npy' # test
```
### 4. visualize your train 
after training and in program dir
```
tensorboard --logdir './'
```
