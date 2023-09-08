# Semantic Conventions

The **Semantic Conventions** define the keys and values which describe commonly observed concepts, protocols, and operations used by applications.

## Reserved Attributes

-   `exception.type`
-   `exception.message`
-   `exception.escaped`
-   `exception.stacktrace`
-   `output.value`
-   `output.mime_type` - The type of output.value. If unspecified, the type is plain text by default
-   `input.value`
-   `input.mime_type`
-   `embedding.embeddings` - A list of objects containing embedding data, including the vector and represented piece of text.
-   `embedding.model_name` - The name of the embedding model.
-   `embedding.text` - The text represented by the embedding.
-   `embedding.vector` - The embedding vector. A list of floats.

-   `llm.function_call` - For models and APIs that support function calling. Records attributes such as the function name and
    arguments to the called function.

-   `llm.invocation_parameters` - Invocation parameters passed to the LLM or API, such as the model name, temperature, etc.

-   `llm.messages` - Messages provided to a chat API.
-   `message.role` - The role of the message, such as `user` or `system`.
-   `message.content` - The content of the message to the llm
-   `llm.model_name` - The name of the model being used.
-   `llm.prompt_template.template` - The prompt template as a Python f-string.
-   `llm.prompt_template.variables` - A list of input variables to the prompt template.
-   `llm.prompt_template.version` -The version of the prompt template being used.
    -   `llm.token_count.prompt` - Number of tokens in the prompt.
-   `llm.token_count.completion` - Number of tokens in the completion.
-   `llm.token_count.total` - Total number of tokens, including both prompt and completion.
-   `tool.name` - Name of the tool being used.
-   `tool.description` - Description of the tool's purpose, typically used to select the tool.
-   `retrieval.documents`
-   `document.id`
-   `document.score`
-   `document.content`
-   `document.metadata` - Document metadata as a string representing a JSON object
