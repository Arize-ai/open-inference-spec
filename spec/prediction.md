# Prediction

A prediction is a column that captures the output of the model. Predictions are prefixed with the category `:prediction:` in the column name.

## Single Value Predictions

predictions have a few reserved **specifiers** that can be used to capture specific reserved information about the prediction. The following is a list of specifiers that are supported by OpenInference:

- **score**: the score of the prediction. This is a numeric value.
- **label**: the label of the prediction. This is a string or bool.

Here is an example of a set of prediction columns:

<table>
 <thead>
    <tr>
     <th>:prediction.float.score:confidence</th>
     <th>:prediction.str.label:predicted_animal</th>
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
</table>

## Text Predictions

In some cases (e.g. LLMs, NLP), the prediction is a sentence or paragraph. In this case, the prediction is prefixed with `:prediction:text:`. Here is an example of a text prediction:

<table>
 <thead>
    <tr>
     <th>:prediction.text:response</th>
    </tr>
 </thead>
 <tbody>
 <tr>
    <td>Yes, the capital of Japan is Tokyo</td>
    </tr>
    <tr>
    <td>The population of Ireland is less than England</td>
    </tr>
    <tr>
    <td>the quick brown fox jumped over the lazy dog</td>
 </tbody>
</table>

## Embedding Predictions

In some cases (e.g. LLMs, NLP), the prediction can be encoded as an embedding. The following is an example of a set of embedding predictions:

<table>
    <thead>
        <tr>
        <th>:prediction.vector:response</th>
        <th>:prediction.text:response</th>
        </tr>
    </thead>
    <tbody>
    <tr>
        <td>[0.1, 0.2, 0.3]</td>
        <td>Yes, the capital of Japan is Tokyo</td>
        </tr>
        <tr>
        <td>[0.1, 0.2, 0.3]</td>
        <td>The population of Ireland is less than England</td>
        </tr>
        <tr>
        <td>[0.1, 0.2, 0.3]</td>
        <td>the quick brown fox jumped over the lazy dog</td>
    </tbody>
</table>

Embedding predictions can also be associated with a URL to the raw data of the embedding. This is a string but is a URL to a file (e.x. an image or audio file). In this case, the prediction is prefixed with `:prediction.url:`. Here is an example of a set of embedding predictions with a URL:

<table>
    <thead>
        <tr>
        <th>:prediction.vector:response</th>
        <th>:prediction.text:response</th>
        <th>:prediction.url:response</th>
        </tr>
    </thead>
    <tbody>
    <tr>
        <td>[0.1, 0.2, 0.3]</td>
        <td>An image of tokyo</td>
        <td>https://example.com/image.jpg</td>
        </tr>
        <tr>
        <td>[0.1, 0.2, 0.3]</td>
        <td>A map of Ireland</td>
        <td>https://example.com/image.jpg</td>
        </tr>
        <tr>
        <td>[0.1, 0.2, 0.3]</td>
        <td>The Eiffel tower</td>
        <td>https://example.com/image.jpg</td>
    </tbody>
</table>
