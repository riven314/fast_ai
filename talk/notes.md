1. Launch AWS Instance, type g2.2xlarge that comes with a fast GPU, using Deep Learning Ubuntu AMI.

2. $ ssh ubuntu@52.54.210.53

3. $ vim .keras/keras.json
"backend": "theano"

4. $ wget https://github.com/zupo/fast_ai/raw/master/talk/pia.jpg

5. $ mkdir test/test && mv pia.jpg test/test/

6. $ wget https://github.com/zupo/fast_ai/raw/master/talk/training_images.zip

7. $ unzip training_images.zip

8. $ wget https://raw.githubusercontent.com/fastai/courses/master/deeplearning1/nbs/vgg16bn.py

9. vim cat_or_dog.py

```python
from vgg16bn import Vgg16BN
vgg = Vgg16BN()

batches = vgg.get_batches('training_images/train', batch_size=32)
val_batches = vgg.get_batches('training_images/validate', batch_size=32)

vgg.finetune(batches)
vgg.fit(batches, val_batches, nb_epoch=1)

pia = next(vgg.get_batches('test'))[0]
prediction = vgg.predict(pia)

print('~~~ Pia is a {}!'.format(prediction[-1][0].replace('s', '')))
```
