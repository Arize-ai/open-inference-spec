# Feature

A feature is a column that captures the inputs to the model. Features are typically numeric or categorical values that are used to make the prediction but can extend more complex data types such as embeddings as well. For example, a feature could be the age of a user or their FICO score. Feature columns are prefixed with the category `:feature:` in the column name.

## Single Value Features

If the column name is only prefixed with the **category** `:feature:` and a **data_type** with a unique **name**, then it is assumed that the column is a single value column (e.g. a key-value pair). Here is an example of a set of feature columns:

<table>
 <thead>
    <tr>
     <th>:feature.int:age</th>
     <th>:feature.str:bank</th>
     <th>:feature.int:fico_score</th>
     <th>:feature.bool:is_gold_member</th>
    </tr>
 </thead>
 <tbody>
 <tr>
    <td>25</td>
    <td>Chase</td>
    <td>750</td>
    <td>true</td>
    </tr>
    <tr>
    <td>35</td>
    <td>Wells Fargo</td>
    <td>800</td>
    <td>false</td>
    </tr>
    <tr>
    <td>45</td>
    <td>Bank of America</td>
    <td>null</td>
    <td>false</td>
 </tbody>
</table>

Note that the `:feature.int:fico_score` column has a value of `null`. This is because the user did not provide their FICO score. This is a valid value for a single value feature column.

## Embedding Features

If a set of columns are meant to be grouped into a "composite", they MUST have matching names. For example, if there is a column named `:feature.vector:prompt` and `feature.text:prompt, then these two columns are meant to be grouped. It is this mechanism that can be used to associate data to a embedding vector.

Here is an example of an embedding for a prompt:

<table>
 <thead>
    <tr>
     <th>:feature.vector:prompt</th>
     <th>:feature.text:prompt</th>
     <th>:prediction.text:response</th>
    </tr>
 </thead>
 <tbody>
 <tr>
    <td>[0.1, 0.2, 0.3]</td>
    <td>What is the weather like today?</td>
    <td>It is rainy</td>
    </tr>
    <tr>
    <td>[0.4, 0.5, 0.6]</td>
    <td>What is the weather like tomorrow?</td>
    <td>It is sunny</td>
    </tr>
    <tr>
    <td>[0.7, 0.8, 0.9]</td>
    <td>What is the weather like in 5 days?</td>
    <td>It is cloudy</td>
 </tbody>
 <table>

Here is an example of an embedding for an image:

<table>
    <thead>
        <tr>
        <th>:feature.vector:my_image</th>
        <th>:feature.url:my_image</th>
        </tr>
    </thead>
    <tbody>
    <tr>
        <td>[0.1, 0.2, 0.3]</td>
        <td>https://example.com/image1.jpg</td>
        </tr>
        <tr>
        <td>[0.4, 0.5, 0.6]</td>
        <td>https://example.com/image2.jpg</td>
        </tr>
        <tr>
        <td>[0.7, 0.8, 0.9]</td>
        <td>https://example.com/image3.jpg</td>
    </tbody>
</table>
