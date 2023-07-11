# Open Inference

The Open Inference specification is edited in markdown files found in the `spec`,

## Overview

This is a a working draft of the specification for Open Inference, a specification for capturing and storing AI model inferences. It's designed to provide an open, interoperable data specification that is designed for ML systems such as inference servers and ML Observability platforms can use to interface with each other. The specification is transport and file format agnostic, and is intended to be used in conjunction with other specifications such as [Parquet](https://github.com/apache/parquet-format)

Open Inference defines a set of columns that capture production inference logs that can be used on top of many file formats including Parquet, Avro, CSV, and JSON. It will also support future formats such as Lance.

Open inference data is designed to be stored in a data lake or data warehouse.

## Model Types / Use-Cases

Open Inference is designed to capture

Natural Language Processing

    -   Text Generative - Prompt and Response
    -   Text Classification
    -   NER Span Categorization

Tabular:

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
