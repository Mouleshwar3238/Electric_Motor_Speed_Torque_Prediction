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

## Linear Regression
The linear regression model of the sklearn library does not have any hyperparameters, and only fits a linear model with arbitrary coefficients to minimize the residual sum of squares between the observed targets and predicted targets. After fitting this model, the performance metrics (MSE and R2 scores) were computed, and the results were visualized for the training as well as test datasets. </br>
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
