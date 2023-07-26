# Actual

an actual is a column that captures the ground truth or actual value of the prediction. this is used to evaluate the model's performance. Since the actual is typically not known at inference time, this is typically added to the records at a later time. Actual columns are prefixed with the category `:actual:` in the column name and typically is symmetric with the [prediction](prediction.md) columns. For example, if there is a `:prediction:float:score` column, then there can be a corresponding `:actual.float.score:` column.

Similar to [predictions](./prediction.md), there a few reserved **specifiers**.

predictions have a few reserved **specifiers** that can be used to capture specific reserved information about the prediction. The following is a list of specifiers that are supported by OpenInference:

- **score**: the score of the ground truth. This is a numeric value.
- **label**: the label of the ground truth. This is a string or bool.

Here is an example of a set of actual columns:

<table>
 <thead>
    <tr>
     <th>:actual.float.score:confidence</th>
     <th>:actual.str.label:animal_type</th>
    </tr>
 </thead>
 <tbody>
 <tr>
    <td>0.8</td>
    <td>cat</td>
    </tr>
    <tr>
    <td>0.9</td>
    <td>dog</td>
    </tr>
    <tr>
    <td>0.2</td>
    <td>cat</td>
 </tbody>

If both predictions and actuals are present, these records can be used to evaluate the model's performance.
