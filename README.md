# LLM Wrapper Documentation

The LLM (Language Model) Wrapper is a versatile tool designed to interact with OpenAI's language models. It provides a higher-level interface to handle conversation-based interactions and text completions. The wrapper is developed using Python and integrates OpenAI's APIs for both chat-based models and text completion models.

## Overview

The LLM Wrapper is organized into three main components:

1. **ChatModelWrapper**: This component facilitates interactions with chat-based models, which are designed to engage in back-and-forth conversations. It handles conversation history, message formatting, and response generation.

2. **CompletionModelWrapper**: This component interacts with text completion models, which generate text based on prompts. It maintains memory of past interactions and dynamically manages the amount of text fed to the model.

3. **LLMWrapper**: This is the primary interface that allows you to choose between chat-based models and text completion models based on the `model_type` parameter.

## Components and Features

### ChatModelWrapper

The `ChatModelWrapper` class offers the following features:

- Conversation History: It maintains a conversation history by storing messages from both users and the AI. The history can be used to provide context for generating responses.
- Memory Management: It handles memory usage and ensures that the conversation history does not exceed the maximum token limit set by OpenAI.
- Message Prioritization: You can prioritize messages in the conversation history to ensure that higher-priority messages are considered first.

### CompletionModelWrapper

The `CompletionModelWrapper` class offers these features:

- Memory Usage: It maintains a memory of past interactions, allowing the model to build upon previous prompts and responses.
- Dynamic Memory Management: The component efficiently manages memory usage by removing old interactions as needed to fit within the token limit.
- Text Completion: Generates text completions based on the provided prompt. The generated text is influenced by the context of past interactions.

### LLMWrapper

The `LLMWrapper` class is a higher-level interface that allows you to choose between chat-based models and text completion models based on the `model_type` parameter. This provides flexibility in choosing the appropriate model for your use case.

## How to Use

To use the LLM Wrapper, follow these steps:

1. Instantiate the appropriate wrapper class: `ChatModelWrapper` for chat-based models or `CompletionModelWrapper` for text completion models.

2. Call the `generate_response` method with relevant parameters:
   - `messages`: A list of `ChatMessage` instances containing the conversation history.
   - `max_tokens`: The maximum number of tokens for the generated response.
   - Additional parameters specific to the wrapper, such as `temperature` for text completions.

3. The method will return a response that you can extract using the `.choices[0].message` attribute for chat-based models or `.choices[0].text.strip()` for text completion models.

## Conclusion

The LLM Wrapper simplifies interactions with OpenAI's language models, providing a convenient way to generate responses based on conversations or prompts. It handles memory management, conversation history, and context-aware completions. By utilizing this wrapper, you can seamlessly integrate powerful language models into your applications and projects.

For more information about OpenAI's models and APIs, please refer to the OpenAI documentation.
