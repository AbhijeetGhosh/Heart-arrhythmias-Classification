# Heartbeat detection and classification using audio 

## Description
This is the code we built for, building a a solution to diagnosing anomaly in heart rhythms. performing a lot of digital singal processing, data processing on audio signals of Heart-Beat. Then a CNN and a RNN was trained on the data, building a classifier that diagnoses anomalous heart rythm noises. The research paper is under peer review, in Research Journal.

## How to use

Create virtual Environment:  

```
 Python -m venv venv 
```
Now active the environment
```
venv\Scripts\activate
```
Now install the necessary libraries
```
pip install -r requirement.txt
```

Now to test the project pretrained model
```
python predict.py c0001.wav
```


## For training 

use the Heartbeat Classifier.ipyb

in either vscode or jupyter

## Dataset used contained:

The Labels and their distribution, amongst classes within both sets are as follows:

                                                       ##SET A
                                                       
                        LABEL ELEMENT                                     QUANTITY
                     |-------------------------------------------------------------------------|
                         Normal                        |                 31 clips
                                                       |
                         Murmur                        |                 34 clips                
                                                       |
                         Extrahs                       |                 19 clips
                                                       |
                         Artifacts                     |                 40 clips
                                                       |
                         Unlabelled                    |                 52 clips
                            SET A
                                                       
                                                      ##SET B
                       
                       LABEL ELEMENT                                     QUANTITY
                     |-------------------------------------------------------------------------|
                         Normal                        |                 320 clips
                                                       |
                         Murmur                        |                 95 clips          
                                                       |
                         Extrasystole                      |                 46 clips
                                                       |
                         Unlabelled                    |                 195 clips
                                                      


## CNN Model Built, containes the following architecture:
Model: "sequential_2"
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
conv2d_8 (Conv2D)            (None, 39, 129, 16)       80        
_________________________________________________________________
max_pooling2d_8 (MaxPooling2 (None, 19, 64, 16)        0         
_________________________________________________________________
dropout_8 (Dropout)          (None, 19, 64, 16)        0         
_________________________________________________________________
conv2d_9 (Conv2D)            (None, 18, 63, 32)        2080      
_________________________________________________________________
max_pooling2d_9 (MaxPooling2 (None, 9, 31, 32)         0         
_________________________________________________________________
dropout_9 (Dropout)          (None, 9, 31, 32)         0         
_________________________________________________________________
conv2d_10 (Conv2D)           (None, 8, 30, 64)         8256      
_________________________________________________________________
max_pooling2d_10 (MaxPooling (None, 4, 15, 64)         0         
_________________________________________________________________
dropout_10 (Dropout)         (None, 4, 15, 64)         0         
_________________________________________________________________
conv2d_11 (Conv2D)           (None, 3, 14, 128)        32896     
_________________________________________________________________
max_pooling2d_11 (MaxPooling (None, 1, 7, 128)         0         
_________________________________________________________________
dropout_11 (Dropout)         (None, 1, 7, 128)         0         
_________________________________________________________________
global_average_pooling2d_2 ( (None, 128)               0         
_________________________________________________________________
dense_2 (Dense)              (None, 2)                 258       
=================================================================
Total params: 43,570
Trainable params: 43,570
Non-trainable params: 0


Hope, you understood the deatails clearly! For any questions or bugs, raise an issue, or mail me at ghoshabhijeet98@gmail.com!  Cheers!
