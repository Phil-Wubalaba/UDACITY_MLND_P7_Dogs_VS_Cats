
# Kaggle Dog Vs Cat 
## using mixed model in pytorch
### README

cpu--- i5-4590  
gpu--- rtx2070  
内存--- 8G  

操作系统 windows10 64位 企业版 **你可能需要更改dir，在三个主要文件中开头都有dir**

explore.ipynb，preprocess.ipynb，main.ipynb为最主要三个文件。

环境请看evironment.yml，不过没有用到keras，opencv，tensorflow等的功能，纯pytorch。

具体操作流程：先安装好最新的cuda 10.0.130，最新的cudnn7.3.1（这个不确定是否用到），最新的python3.7.3，pytorch1.0.1
，以及其他一系列numpy，pandas，h5py，matplotlib等等常见库就可以了。具体看environment.yml。

接下来有两个方向   
**explore.ipynb ---> preprocess.ipynb ---> main.ipynb**  
或者
**preprocess.ipynb ---> main.ipynb**  
进行这条线时，需要注意按照提示解注释   
### explore.ipynb
explore.ipynb：作用是处理异常值并可视化。原理是使用一个已经预训练好的模型，从imagenet原有的1000个输出中找出该图片是否能识别出狗或者猫来，或者这张图片的预测结果是否错得离谱。**用时30分钟左右**  
### preprocess.ipynb
preprocess.ipynb：作用是预处理，和explore有些重叠之处，但此文件最重要的目的是导出特征向量。**用时30分钟左右，导出的H5文件将消耗接近2G储存空间，重复运行前，请确保本地没有同名h5文件**
### main.ipynb
main.ipynb：作用是设计最后的简单分类器模型，并且在已导出的特征向量上训练，预测测试集结果，可视化预测结果，可视化训练曲线。**用时2分钟左右，将会在原地保存一个用于提交给kaggle的csv文件**


如果以上步骤全部顺利的话，那么提交给kaggle的分数将在前2%。

visualization是一个无关紧要的文件，只是对其中一些数据进行了可视化。
