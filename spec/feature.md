# Feature

A feature is a column that captures the inputs to the model. Features are typically numeric or categorical values that are used to make the prediction but can extend more complex data types such as embeddings as well. For example, a feature could be the age of a user or their FICO score. Feature columns are prefixed with the category `:feature:` in the column name.

## Numeric and Categorical Features

If the column name is only prefixed with the **category** `:feature:` and a **data_type**, then it is assumed that the column is a numeric or categorical single value column (e.g. a key-value pair). Here is and example of a set of feature columns:

<table>
 <thead>
    <tr>
     <th>:feature:int:age</th>
     <th>:feature:str:bank</th>
     <th>:feature:int:fico_score</th>
    </tr>
 </thead>
 <body>
 <tr>
    <td>25</td>
    <td>Chase</td>
    <td>750</td>
    </tr>
    <tr>
    <td>35</td>
    <td>Wells Fargo</td>
    <td>800</td>
    </tr>
    <tr>
    <td>45</td>
    <td>Bank of America</td>
    <td>null</td>
 </body>
</table>

Note that the `:feature:int:fico_score` column has a value of `null`. This is because the user did not provide their FICO score. This is a valid value for a single value feature column.

## Embedding Features

If the column name is prefixed with `:feature:emb:`, then it is assumed that the column is associated with an embedding. An embedding is made up of a vector and a set of associated data. An embedding is composed of multiple columns. For this reason, a name follows the prefix parts to group the columns together (e.x. `:feature:emb:vector:prompt`) The following is an example of an embedding:

-   `:feature:emb:vector:<name>`: the vector of the embedding. This is a numeric array.
-   `:feature:emb:text:<name>`: the associated text data of the embedding if the embedding represents. This is a string.
-   `:feature:emb:url:<name>`: A URL that points to the raw data of the embedding. This is a string but is a URL to a file (e.x. an image or audio file).

Here is an example of an embedding for a prompt:

<table>
 <thead>
    <tr>
     <th>:feature:emb:vector:prompt</th>
     <th>:feature:emb:text:prompt</th>
    </tr>
 </thead>
 <tbody>
 <tr>
    <td>[0.1, 0.2, 0.3]</td>
    <td>What is the weather like today?</td>
    </tr>
    <tr>
    <td>[0.4, 0.5, 0.6]</td>
    <td>What is the weather like tomorrow?</td>
    </tr>
    <tr>
    <td>[0.7, 0.8, 0.9]</td>
    <td>What is the weather like in 5 days?</td>
 </tbody>
 <table>

Here is an example of an embedding for an image:

<table>
    <thead>
        <tr>
        <th>:feature:emb:vector:my_image</th>
        <th>:feature:emb:url:my_image</th>
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
