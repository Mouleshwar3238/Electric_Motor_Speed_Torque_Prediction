# Electric_Motor_Speed_Torque_Prediction
Designed ML models with optimal hyperparameters to predict the speed/torque of an electric motor using the latter's operational parameters as features.

## Dataset Description
The dataset contains continuous-values attributes, which include the operational parameters of the motor, such as voltage and current components, motor and ambient temperatures etc., along with the corresponding speed as well as torque values.
* Title: **Electric Motor Temperature**
* URL: https://www.kaggle.com/datasets/wkirgsn/electric-motor-temperature
<table>
<thead>
  <tr>
    <th align="center" colspan="2">Generic Description</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td align="center">Number of samples</td>
    <td align="center">13,30,816</td>
  </tr>
  <tr>
    <td align="center">Number of attributes</td>
    <td align="center">13</td>
  </tr>
  <tr>
    <td align="center">Input features</td>
    <td align="center">11 (voltage and current components, temperature etc.)</td>
  </tr>
  <tr>
    <td align="center">Target variable</td>
    <td align="center">speed/torque</td>
  </tr>
</tbody>
</table>

The dataset was split into a training subset and test subset, with 80 % being used for training and 20 % being used for testing. Before being used, the data in both subsets was normalized using StandardScaler. The 'profile-id' attribute was removed from the dataset in the pre-processing stage, as it only indicates session of the particular measurement, and hence has no relation with the other attributes. 

For all the models (except linear regression and neural network), the optimal hyperparameters were found using halving grid search. The performance of all the models was compared in terms of their MSE and R2 scores, and the corresponding predictions were also visualized.

## Linear Regression
* It fits a linear model with arbitrary coefficients to minimize the residual sum of squares between the observed targets and predicted targets.
<table>
  <thead>
    <tr>
      <th align="center"></th>
      <th align="center"></th>
      <th align="center">MSE</th>
      <th align="center">R2 Score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center" rowspan="2"><strong>Speed Prediction</strong></td>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center">218977.652042</td>
      <td align="center">0.936707</td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center">219977.086242</td>
      <td align="center">0.936288</td>
    </tr>
    <tr>
      <td align="center" colspan="6"></td>
    </tr>
    <tr>
      <td align="center" rowspan="2"><strong>Torque Prediction</strong></td>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center">20.365407</td>
      <td align="center">0.996574</td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center">20.259357</td>
      <td align="center">0.996606</td>
    </tr>
  </tbody>
  </table>

## Elastic Net
* It is a modifed version of the standard linear regression model, and employs regularization using either the L1 or L2 norm on the former to prevent overfitting.
<table>
  <thead>
    <tr>
      <th align="center"></th>
      <th align="center"></th>
      <th align="center">MSE</th>
      <th align="center">R2 Score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center" rowspan="2"><strong>Speed Prediction</strong></td>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center">220286.614834</td>
      <td align="center">0.936329</td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center">221121.096788</td>
      <td align="center">0.935957</td>
    </tr>
    <tr>
      <td align="center" colspan="6"></td>
    </tr>
    <tr>
      <td align="center" rowspan="2"><strong>Torque Prediction</strong></td>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center">20.373511</td>
      <td align="center">0.996573</td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center">20.264708</td>
      <td align="center">0.996606</td>
    </tr>
  </tbody>
  </table>

## Linear SVR (Support Vector Regression)
* In general, the SVR model tries to find a function that best predicts the continuous output value for given input value(s), and can use both linear and non-linear kernels.
* Linear SVR provides better results than the standard SVR model for large datasets, but only uses the linear kernel.
<table>
  <thead>
    <tr>
      <th align="center"></th>
      <th align="center"></th>
      <th align="center">MSE</th>
      <th align="center">R2 Score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center" rowspan="2"><strong>Speed Prediction</strong></td>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center">312431.267948</td>
      <td align="center">0.909695</td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center">314449.427085</td>
      <td align="center">0.908926</td>
    </tr>
    <tr>
      <td align="center" colspan="6"></td>
    </tr>
    <tr>
      <td align="center" rowspan="2"><strong>Torque Prediction</strong></td>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center">20.373511</td>
      <td align="center">0.996573</td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center">20.264708</td>
      <td align="center">0.996606</td>
    </tr>
  </tbody>
  </table>

## Decision Tree Regressor
* It observes the features of an object and trains a model in the structure of a tree to make predictions for data in the future.
<table>
  <thead>
    <tr>
      <th align="center"></th>
      <th align="center"></th>
      <th align="center">MSE</th>
      <th align="center">R2 Score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center" rowspan="2"><strong>Speed Prediction</strong></td>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center">131.68398</td>
      <td align="center">0.999962</td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center">825.982098</td>
      <td align="center">0.999761</td>
    </tr>
    <tr>
      <td align="center" colspan="6"></td>
    </tr>
    <tr>
      <td align="center" rowspan="2"><strong>Torque Prediction</strong></td>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center">0.142327</td>
      <td align="center">0.999976</td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center">0.867584</td>
      <td align="center">0.999855</td>
    </tr>
  </tbody>
  </table>

## Bayesian Ridge Regression
* It is a modified version of the ridge regression model, and employs prior belief or knowledge about the data to create more accurate predictions.
* It is extremely useful in cases where the data is complex or ambiguous.
<table>
  <thead>
    <tr>
      <th align="center"></th>
      <th align="center"></th>
      <th align="center">MSE</th>
      <th align="center">R2 Score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center" rowspan="2"><strong>Speed Prediction</strong></td>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center">218977.652202</td>
      <td align="center">0.936707</td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center">219977.003862</td>
      <td align="center">0.936288</td>
    </tr>
    <tr>
      <td align="center" colspan="6"></td>
    </tr>
    <tr>
      <td align="center" rowspan="2"><strong>Torque Prediction</strong></td>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center">20.365407</td>
      <td align="center">0.996574</td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center">20.259357</td>
      <td align="center">0.996606</td>
    </tr>
  </tbody>
  </table>

## Stochastic Gradient Descent (SGD) Regressor
* It changes the model's parameters using a single randomly selected data point (or a small batch of data) at each iteration.
<table>
  <thead>
    <tr>
      <th align="center"></th>
      <th align="center"></th>
      <th align="center">MSE</th>
      <th align="center">R2 Score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center" rowspan="2"><strong>Speed Prediction</strong></td>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center">219356.695489</td>
      <td align="center">0.936598</td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center">220232.669834</td>
      <td align="center">0.936214</td>
    </tr>
    <tr>
      <td align="center" colspan="6"></td>
    </tr>
    <tr>
      <td align="center" rowspan="2"><strong>Torque Prediction</strong></td>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center">20.36786</td>
      <td align="center">0.996574</td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center">20.26058</td>
      <td align="center">0.996606</td>
    </tr>
  </tbody>
  </table>

## Neural Network
* A neural network consist of interconnected nodes or neurons, which process and learn patterns from the data by automatically extracting significant or important features from the latter.
* A neural network with 4 hidden layers was created for the given task, and it used ReLU and linear activation functions for the hidden and output layer(s) respectively.
* The above network was trained for 100 epochs with a batch size of 512, and to validate its performance, the training subset was further split into 2 new subsets (80% for training and 20% for validation).
<table>
  <thead>
    <tr>
      <th align="center"></th>
      <th align="center"></th>
      <th align="center">MSE</th>
      <th align="center">R2 Score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center" rowspan="2"><strong>Speed Prediction</strong></td>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center">725.778194</td>
      <td align="center">0.99979</td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center">808.079829</td>
      <td align="center">0.999766</td>
    </tr>
    <tr>
      <td align="center" colspan="6"></td>
    </tr>
    <tr>
      <td align="center" rowspan="2"><strong>Torque Prediction</strong></td>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center">1.195187</td>
      <td align="center">0.999799</td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center">1.165287</td>
      <td align="center">0.999805</td>
    </tr>
  </tbody>
  </table>

## Gradient Boosting Regressor
* It combines several weak learners into strong learners, in which each new model is trained to minimize the loss function such as mean squared error (regression) or cross-entropy (classification) of the previous model.
<table>
  <thead>
    <tr>
      <th align="center"></th>
      <th align="center"></th>
      <th align="center">MSE</th>
      <th align="center">R2 Score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center" rowspan="2"><strong>Speed Prediction</strong></td>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center">435.520003</td>
      <td align="center">0.999874</td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center">612.659493</td>
      <td align="center">0.999823</td>
    </tr>
    <tr>
      <td align="center" colspan="6"></td>
    </tr>
    <tr>
      <td align="center" rowspan="2"><strong>Torque Prediction</strong></td>
      <td align="center"><strong>Training Subset</strong></td>
      <td align="center">0.479665</td>
      <td align="center">0.999919</td>
    </tr>
    <tr>
      <td align="center"><strong>Test Subset</strong></td>
      <td align="center">0.555813</td>
      <td align="center">0.999907</td>
    </tr>
  </tbody>
  </table>
