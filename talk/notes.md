1. Launch AWS Instance, type g2.2xlarge that comes with a fast GPU, using Deep Learning Ubuntu AMI.
2. $ ssh ubuntu@52.54.210.53
3. wget http://files.fast.ai/data/dogscats.zip
4. unzip dogscats.zip
3. wget https://raw.githubusercontent.com/fastai/courses/master/deeplearning1/nbs/vgg16bn.py
4. vim cat_or_dog.py


from vgg16bn import Vgg16BN

vgg = Vgg16BN()

batches = vgg.get_batches('train', batch_size=batch_size)



5.
