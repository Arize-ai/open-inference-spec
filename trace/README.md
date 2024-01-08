# OpenInference Tracing

> [!IMPORTANT]
> OpenInference Tracing is now being actively worked on via: [OpenInference](https://github.com/Arize-ai/openinference)
> This repository is maintained for historical purposes only.

The OpenInference Tracing specification is edited in markdown files found in the [spec directory](./spec/README.md).

OpenInference Tracing is a specification for capturing and storing LLM application executions. It's designed to provide insight into the invocation of LLMs and the surrounding application context such as retrieval from vector stores and the usage of external tools such as search engines or APIs. The specification is transport and file-format agnostic, and is intended to be used in conjunction with other specifications such as JSON, ProtoBuf, and DataFrames.

Observability lets us understand a system from the outside, by letting us ask questions about that system without knowing its inner workings. Furthermore, it allows us to easily troubleshoot and handle novel problems (i.e. “unknown unknowns”), and helps us answer the question, “Why is this happening?”

In order to be able to ask those questions of a system, the application must be properly instrumented. That is, the application code must emit signals such as traces, metrics, and logs. An application is properly instrumented when developers don’t need to add more instrumentation to troubleshoot an issue, because they have all of the information they need.

OpenInference tracing is the mechanism by which an LLM application is instrumented, to help make a system observable.
