# Overview

The OpenInference specification defines a set of columns that semantically map to segments of a model's inference. OpenInference defines a set of columns that capture production inference logs that can be used on top of many file formats.

# Naming Convention

The column names in OpenInference encode semantics via a well-formed prefix, where aset of `:`s are used to encapsulate machine parsable information. Parsers of the OpenInference specification should use the `:` as a delimiter to extract the ontological information about the column. The anatomy of a column name is as follows:

```
:<category>.<data_type>.<[identifier]>:<name>
```

Where `category` MUST be provided. The `data_type` and `identifier` MUST be provided depending on the `category`. The `name` is optional ONLY if the `category` is a reserved singleton category for the row (e.g. `:id:`).

In the specification, `category`, `data_type`, and `identifier` will be referred to as **parts**.

Between the `:`s, the **parts** are separated by a `.`. The following is an example of an integer column named `age`:

```
:feature.int:age
```

## Categories

A single row or inference record is composed of a set of columns that capture the following information:

- **prediction ID** or **ID**: a unique identifier for the inference. This is typically a UUID.
- **timestamp**: the timestamp of the inference. This is the time at which the inference was made, typically in production.
- **model version**: the version of the model that was used to make the inference.
- **features**: The inputs to the model. This is a set of columns that contain numeric and categorical values that were used to make the inference.
- **predictions**: The output of the model.
- **actuals**: The ground truth or actual value of the prediction. This is used to evaluate the model's performance.
- **tags**: A set of columns that capture metadata about the inference. This can include information such as business KPIs or additional information that is useful for debugging and analysis.

In the specification, the above information will be referred to as **categories**. The above categories are captured in the prefix-based naming convention as the first item. The following is a list of prefixes that are used to capture the above:

- **ID**: `:id:`
- **timestamp**: `:timestamp:`
- **model version**: `:version:`
- **features**: `:feature:`
- **predictions**: `:prediction:`
- **actuals**: `:actual:`
- **tags**: `:tag:`

The above prefixes are used to capture the semantic category of the column. For example, a column named `:feature:int:age` would be a column that captures the age of the user and that is used as an input to the model. A column named `:prediction:float:score` would be a column that captures the score of the prediction.

The **features**, **predictions**, **actuals**, and **tags** categories will be referred to in this specification as **dimensions**.

## Data Types

OpenInference is designed to be transport and file format agnostic. As such, it relies on the underlying file format to define the primitive types. However not all file formats are crated equal and a super-set of data types are required to fully capture the data (For example, JSON has no concept of `float`). For this reason, we reserve the second part of the prefix for the `data_type`. The following is a list of data types that are supported by OpenInference:

- primitive data types

  - **int**: an integer
  - **float**: a floating point number
  - **bool**: a boolean
  - **str**: a string, typically a label that can be enumerated

- high-level data types

  - **text**: a string that is a sentence or paragraph
  - **id**: a `str` or `int` that is a unique identifier
  - **url**: a string that is a URL. MUST start with `http://` or `https://`

- temporal data types
  - **iso_8601**: a string that is an ISO 8601 timestamp
  - **milliseconds**: a numeric value that is the number of milliseconds
  - **seconds**: a numeric value that is the number of seconds
  - **minutes**: a numeric value that is the number of minutes

### List Types

The above data types can be used to define a list of values by wrapping the data type in `[]`s. For example, a column that captures a list of `int`s can be defined as `:feature.[id]:document_ids`.

## Specifiers

Specifiers designate a reserved semantic meaning to the column. Specifiers are used to capture specific reserved information about the column. The following is a list of specifiers that are supported by OpenInference:

- **score**: the score of the prediction. This is a numeric value.
- **label**: the label of the prediction. This is a string or bool.
- **importance**: the importance of the feature. This is a numeric value.
- **embedding**: the embedding of the feature. This is always a list of numeric values.
- **retrieved_document_ids**: the list of document IDs that were retrieved using an embedding. This is always a list of `id` types. See [features](./feature.md) for more information.
- **retrieved_document_scores**: the list of document scores that were retrieved using an embedding. See [features](./feature.md) for more information.

For full details on each of the columns, consult the sub-sections below.

## Columns

- [id](./id.md)
- [timestamp](./timestamp.md)
- [features](./feature.md)
- [predictions](./prediction.md)
- [actuals](./actual.md)
- [tags](./tag.md)
