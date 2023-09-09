# Semantic Conventions

The **Semantic Conventions** define the keys and values which describe commonly observed concepts, protocols, and operations used by applications. These conventions are used to populate the `attributes` of `spans` and span `events`.

## Reserved Attributes

The following attributes are reserved and MUST be supported by all OpenInference Tracing SDKs:

| Attribute                       | Type            | Example                                          | Requirement Level | Description                                                      |
| ------------------------------- | --------------- | ------------------------------------------------ | ----------------- | ---------------------------------------------------------------- |
| `exception.type`                | String          | `"NullPointerException"`                         | Required          | The type of exception that was thrown                            |
| `exception.message`             | String          | `"Null value encountered"`                       |                   | Detailed message describing the exception                        |
| `exception.escaped`             | Boolean         | `true`                                           |                   | Indicator if the exception has escaped the span's scope          |
| `exception.stacktrace`          | String          | `"at app.main(app.java:16)"`                     |                   | The stack trace of the exception                                 |
| `output.value`                  | String          | `"Hello, World!"`                                |                   | The output value of an operation                                 |
| `output.mime_type`              | String          | `"text/plain"`                                   |                   | MIME type representing the format of `output.value`              |
| `input.value`                   | String          | `{"query": "What is the weather today?"}`        | Required          | The input value to an operation                                  |
| `input.mime_type`               | String          | `"application/json"`                             |                   | MIME type representing the format of `input.value`               |
| `embedding.embeddings`          | List of objects | `[{vector: [...], text: "hello"}]`               |                   | List of embedding objects including text and vector data         |
| `embedding.model_name`          | String          | `"BERT-base"`                                    |                   | Name of the embedding model used                                 |
| `embedding.text`                | String          | `"hello world"`                                  |                   | The text represented in the embedding                            |
| `embedding.vector`              | List of floats  | `[0.123, 0.456, ...]`                            |                   | The embedding vector consisting of a list of floats              |
| `llm.function_call`             | String          | `{function_name: "add", args: [1, 2]}`           |                   | Object recording details of a function call in models or APIs    |
| `llm.invocation_parameters`     | JSON string     | `{model_name: "gpt-3", temperature: 0.7}`        |                   | Parameters used during the invocation of an LLM or API           |
| `llm.messages`                  | List of objects | `[{role: "user", content: "hello"}]`             |                   | List of messages exchanged in a chat API                         |
| `message.role`                  | String          | `"user"` or `"system"`                           |                   | Role of the entity in a message (e.g., user, system)             |
| `message.content`               | String          | `"What's the weather today?"`                    |                   | The content of a message in a chat                               |
| `llm.model_name`                | String          | `"gpt-3.5-turbo"`                                |                   | The name of the language model being utilized                    |
| `llm.prompt_template.template`  | String          | `"Weather forecast for {city} on {date}"`        |                   | Template used to generate prompts as Python f-strings            |
| `llm.prompt_template.variables` | List of strings | `["city", "date"]`                               |                   | List of variables to be used in the prompt template              |
| `llm.prompt_template.version`   | String          | `"v1.0"`                                         |                   | The version of the prompt template                               |
| `llm.token_count.prompt`        | Integer         | `5`                                              |                   | The number of tokens in the prompt                               |
| `llm.token_count.completion`    | Integer         | `15`                                             |                   | The number of tokens in the completion                           |
| `llm.token_count.total`         | Integer         | `20`                                             |                   | Total number of tokens, including prompt and completion          |
| `tool.name`                     | String          | `"WeatherAPI"`                                   | Required          | The name of the tool being utilized                              |
| `tool.description`              | String          | `"An API to get weather data."`                  |                   | Description of the tool's purpose and functionality              |
| `retrieval.documents`           | List of objects | `[{id: "1", score: 0.9, content: "..."}]`        |                   | List of retrieved documents                                      |
| `document.id`                   | String/Integer  | `"1234"` or `1`                                  |                   | Unique identifier for a document                                 |
| `document.score`                | Float           | `0.98`                                           |                   | Score representing the relevance of a document                   |
| `document.content`              | String          | `"This is a sample document content."`           | Required          | The content of a retrieved document                              |
| `document.metadata`             | JSON string     | `'{"author": "John Doe", "date": "2023-09-09"}'` |                   | Metadata associated with a document represented as a JSON string |
