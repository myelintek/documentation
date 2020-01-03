***********************
Segmentation Template
***********************


UNet Keras template 
===================

https://github.com/myelintek/unet

The code is refer to https://github.com/zhixuhao/unet, and we fixed some issues.


Dataset
+++++++

This program was designed for the http://brainiac2.mit.edu/isbi_challenge/.

Train Input
+++++++++++

In main.py, you can edit the input path:

.. code-block:: console

    train_path='/mlsteam/input/train'

The train_path should has two child folders named 'image' and 'label', but if you want a different name, edit the line:

.. code-block:: console

    myGene = trainGenerator(batch_one_gpu,train_path,'image','label',data_gen_args,save_to_dir = aug_path)


Test Input and Predict Output
+++++++++++++++++++++++++++++

After training, the model will predict those images in test folder, and save the results in predict folder.

.. code-block:: console

    test_path='/mlsteam/input/test'
    predict_path='./data/predict'



Train Input Augmentation
++++++++++++++++++++++++

The augmentation can adjust parameters at

.. code-block:: console

  data_gen_args = dict(rotation_range=0.2,
                      width_shift_range=0.05,
                      height_shift_range=0.05,
                      shear_range=0.05,
                      zoom_range=0.05,
                      horizontal_flip=True,
                      fill_mode='nearest')

If you want no augmentation, use a empty dict().

And if you want store those augmented images to observe them, specify the path to store. (note: For large Dataset, It might to run slower and cost huge disk space)

.. code-block:: console

    aug_path=None

Customize Output
++++++++++++++++

Edit the callback logger function:

.. code-block:: console

  class TrainLogger(Callback):
      def on_batch_end(self, batch, logs={}):
          print("Train step={} loss={} acc={}".format(batch, logs.get('loss'), logs.get('accuracy')))

And change the content of print()

