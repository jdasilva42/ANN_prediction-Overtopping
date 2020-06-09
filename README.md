# ANN_prediction-Overtopping

ANN model for overtopping prediction. The ANN model has been trained and tested on the CLASH database initiated by deltares.
Based on sequential ANN regression model, the overtopping discharge can be provided.

### ANN model

the ANN regression model contains two hidden layers with 80 neurons for each one. 2 Batch normalization layers have been included after each hidden layer. The activation function is LeakyReLU with alpha= 0,2. The last layer contains one neuron with a linear activation function.

Adam optimizer has been used with learning rate = 0.001. The lost function used is mean_squared_error.

```
Layer (type)                 Output Shape              Param #   
=================================================================
dense_16 (Dense)             (None, 80)                1200      
_________________________________________________________________
batch_normalization_v1_10 (B (None, 80)                320       
_________________________________________________________________
leaky_re_lu_10 (LeakyReLU)   (None, 80)                0       
_________________________________________________________________
dense_17 (Dense)             (None, 80)                6480      
_________________________________________________________________
batch_normalization_v1_11 (B (None, 80)                320           
_________________________________________________________________
leaky_re_lu_11 (LeakyReLU)   (None, 80)                0       
_________________________________________________________________
dense_18 (Dense)             (None, 1)                 81        
=================================================================
Total params: 8,401
Trainable params: 8,081
Non-trainable params: 320
```
### validation and test 
score prediction on the validation set
```
############## SCORE DATASET TEST ########

R2 TEST
0.8674138015376512

RMSE TEST
0.0020239420582337064
```
score prediction on test set
```
############## SCORE DATASET TEST ########

R2 TEST
0.9171918633188854

RMSE TEST
0.0020066650711043957
```

### ANN prediction vs EUROTOP prediction
ANN predictions have been done regarding breakwater with no berm. For compare the predictions, the overtopping discharges have been computed with the empirical formulations from EUROTOP 2018.


