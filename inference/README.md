# OpenInference

The OpenInference specification is edited in markdown files found in the [spec directory](./spec/README.md).

## Overview

This is a a working draft of the specification for OpenInference, a specification for capturing and storing AI model inferences. It's designed to provide an open, interoperable data specification that is designed for ML systems such as inference servers and ML Observability platforms can use to interface with each other. The specification is transport and file-format agnostic, and is intended to be used in conjunction with other specifications such as [Parquet](https://github.com/apache/parquet-format).

OpenInference defines a set of columns that capture production inference logs that can be used on top of many file formats including Parquet, Avro, CSV, and JSON. It will also support future formats such as Lance.

## Model Types / Use-Cases

OpenInference is designed to capture records for a variety of model types and use-cases. The following is a list of model types and use-cases that OpenInference is designed to capture.

Natural Language Processing

-   Text Classification
-   NER Span Categorization

Tabular

-   Regression
-   Classification
-   Classification + Score
-   Multi-Classification
-   Ranking
-   Multi-Output/Label
-   Time Series Forecasting

Computer Vision

-   Classification
-   Bounding Box
-   Segmentation

Large Language Models

-   Text Generation via Prompt-Response
-   Retrieval-Augmented Generation
