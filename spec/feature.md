# Feature

A feature is a column that captures the inputs to the model. Features are typically numeric or categorical values that are used to make the prediction but can extend more complex data types as well. For example, a feature could be the age of a user or their FICO score. Feature columns are prefixed with `:feature:` in the column name.

## Numeric and Categorical Features

If the column name is only prefixed with `:feature:`, then it is assumed that the column is a numeric or categorical. Here is and example of a set of feature columns:

<table>
 <thead>
    <tr>
     <th>:feature:age</th>
     <th>:feature:bank</th>
     <th>:feature:fico_score</th>
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
    <td>700</td>
 </body>
</table>

## Embedding Features

If the column name is prefixed with `:feature:emb:`, then it is assumed that the column is associated with an embedding. An embedding is made up of a vector and a set of associated data. An embedding is composed of multiple columns. For this reason, a human friendly name follows the prefix to group the columns together (e.x. `:feature:emb:prompt`) The following is an example of an embedding:

-   `:feature:emb:<name>:vector:`: the vector of the embedding. This is a numeric array.
-   `:feature:emb:<name>:text:`: the associated text data of the embedding if the embedding represents. This is a string.
-   `:feature:emb:<name>:url:`: A URL that points to the raw data of the embedding. This is a string but is a URL to a file (e.x. an image or audio file).

Here is an example of an embedding for a prompt:

<table>
 <thead>
    <tr>
     <th>:feature:emb:prompt:vector:</th>
     <th>:feature:emb:prompt:text:</th>
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
        <th>:feature:emb:image:vector:</th>
        <th>:feature:emb:image:url:</th>
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
