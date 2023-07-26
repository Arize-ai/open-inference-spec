# OpenInference Specification

- [Overview](./overview.md)
- Inference Record Columns
  - [ID](./id.md)
  - [Timestamp](./timestamp.md)
- Dimension Columns
  - [Feature](./feature.md)
  - [Tag](./tag.md)
  - [Prediction](./prediction.md)
  - [Actual](./actual.md)

## Notation Conventions and Compliance

The keywords "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD",
"SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY", and "OPTIONAL" in the
specification are to be interpreted as described in [BCP
14](https://tools.ietf.org/html/bcp14)
[[RFC2119](https://tools.ietf.org/html/rfc2119)]
[[RFC8174](https://tools.ietf.org/html/rfc8174)] when, and only when, they
appear in all capitals, as shown here.

An implementation of the specification is not compliant if it fails to
satisfy one or more of the "MUST", "MUST NOT", "REQUIRED", "SHALL", or "SHALL
NOT" requirements defined in the specification. Conversely, an
implementation of the specification is compliant if it satisfies all the
"MUST", "MUST NOT", "REQUIRED", "SHALL", and "SHALL NOT" requirements defined in
the specification.

The specification uses a set of conventions to describe the structure of
strings. Terms surrounded by `<` and `>` are placeholders for the actual value.
For example, `<name>` is a placeholder for the actual name of the column. Terms
surrounded by `[` and `]` are optional. For example, `<[name]>` means that the
name is optional.

## Project Naming

- The official project name is "OpenInference" (with no space between "Open" and
  "Inference").
