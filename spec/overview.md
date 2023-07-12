# Overview

The Open Inference specification defines a set of columns that semantically maps to segments of a model's inference. A single row or inference record is composed of a set of columns that capture the following information:

-   **prediction ID** or **ID**: a unique identifier for the inference. This is typically a UUID.
-   **timestamp**: the timestamp of the inference. This is the time at which the inference was made, typically in production.
-   **model version**: the version of the model that was used to make the inference.
-   **features**: The inputs to the model. This is a set of columns that contain numeric and categorical values that were used to make the inference.
-   **predictions**: The output of the model.
-   **actuals**: The ground truth or actual value of the prediction. This is used to evaluate the model's performance.
-   **tags**: A set of columns that capture metadata about the inference. This can include information such as business KPIs or additional information that is useful for debugging and analysis.

## Naming convention

The above topology of data is captured via a prefix-based naming convention. The following is a list of prefixes that are used to capture the above information:

-   **prediction ID** or **ID**: `:id:`
-   **timestamp**: `:timestamp:`
-   **model version**: `:version:`
-   **features**: `:feature:`
-   **predictions**: `:prediction:`
-   **actuals**: `:actual:`
-   **tags**: `:tag:`

The above prefixes are used to capture the semantic category of the column. For example, a column named `:feature:age` would be a column that captures the age of the user and that is used as an input to the model. A column named `:prediction:score` would be a column that captures the score of the prediction.

The **features**, **predictions**, **actuals**, and **tags** categories will be referred to in this specification as **dimension**.

For full details on each of the dimensions, consult the sub-sections below.

## Dimensions

-   [features](./feature.md)

## Data Types

Open Inference is designed to be transport and file format agnostic. As such, it does not define a set of data types. Instead, it relies on the underlying file format to define the data types. For example, if the data is stored in Parquet, then the data types are defined by the Parquet specification. If the data is stored in CSV, then the data types are defined by the CSV specification.
