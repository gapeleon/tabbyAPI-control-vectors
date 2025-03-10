# TabbyAPI with Control Vectors Support

<p  align="left">
<img  src="https://img.shields.io/badge/Python-3.10%20|%203.11%20|%203.12-blue"  alt="Python 3.10, 3.11, and 3.12">
<a  href="/LICENSE">
<img  src="https://img.shields.io/badge/License-AGPLv3-blue.svg"  alt="License: AGPL v3"/>
</a>
</p>
<p  align="left">
<a  href="https://theroyallab.github.io/tabbyAPI">
<img  src="https://img.shields.io/badge/Documentation-API-orange"  alt="Developer facing API documentation">
</a>
</p>

This fork of TabbyAPI adds support for control vectors with the Exllamav2 backend, allowing fine-tuned control over model behavior using vector-based steering.

**[IMPORTANT]**

Control vectors are currently not compatible with tensor parallelism (`tensor_parallel: true`). If tensor parallelism is enabled, control vectors will not be applied to the model.

## Control Vectors Setup

1. Create a directory alongside your model with `-vectors` appended to the name:

```

models/Gemma-2-9B-It-SPPO-Iter3-exl2/ # Model directory

models/Gemma-2-9B-It-SPPO-Iter3-exl2-vectors/ # Control vectors directory

```

2. Add control vector configuration to your `config.yml`:

```yaml

control_vectors_enabled: true

control_vectors: "vector_name:direction:scale,vector_name:direction:scale"

```

Example:

```yaml

control_vectors: "honesty_vs_machiavellianism:machiavellianism:0.5,humility_vs_narcissism:narcissism:0.3"

```

## Getting Started

**[IMPORTANT]**

 This is an unofficial fork. The README does not have instructions for setting up other than control vectors. Please read the original Wiki.

For a step-by-step guide, choose the format that works best for you:

📖 Read the [Wiki](https://github.com/theroyallab/tabbyAPI/wiki/1.-Getting-Started) – Covers installation, configuration, API usage, and more.

🎥 Watch the [Video Guide](https://www.youtube.com/watch?v=03jYz0ijbUU) – A hands-on walkthrough to get you up and running quickly.

## Features

- OpenAI compatible API
- Loading/unloading models
- HuggingFace model downloading
- Embedding model support
- JSON schema + Regex + EBNF support
- AI Horde support
- Speculative decoding via draft models

- Multi-lora with independent scaling (ex. a weight of 0.9)
- Inbuilt proxy to override client request parameters/samplers
- Flexible Jinja2 template engine for chat completions that conforms to HuggingFace
- Concurrent inference with asyncio
- Utilizes modern python paradigms
- Continuous batching engine using paged attention
- Fast classifier-free guidance
- OAI style tool/function calling

And much more. If something is missing here, PR it in!

## Supported Model Types

TabbyAPI uses Exllamav2 as a powerful and fast backend for model inference, loading, etc. Therefore, the following types of models are supported:

- Exl2 (Highly recommended)

- GPTQ

- FP16 (using Exllamav2's loader)

In addition, TabbyAPI supports parallel batching using paged attention for Nvidia Ampere GPUs and higher.

## Contributing

Use the template when creating issues or pull requests, otherwise the developers may not look at your post.

If you have issues with the project:

- Describe the issue in detail

- If you have a feature request, please indicate it as such.

If you have a Pull Request

- Describe the pull request in detail, what, and why you are changing something

## Acknowldgements

TabbyAPI would not exist without the work of other contributors and FOSS projects:

- [ExllamaV2](https://github.com/turboderp/exllamav2)
- [Aphrodite Engine](https://github.com/PygmalionAI/Aphrodite-engine)
- [infinity-emb](https://github.com/michaelfeil/infinity)
- [FastAPI](https://github.com/fastapi/fastapi)
- [Text Generation WebUI](https://github.com/oobabooga/text-generation-webui)
- [SillyTavern](https://github.com/SillyTavern/SillyTavern)

  

## Developers and Permissions

This fork adds control vector support to the original TabbyAPI. Original TabbyAPI developers:
- [kingbri](https://github.com/bdashore3)
- [Splice86](https://github.com/Splice86)
- [Turboderp](https://github.com/turboderp)

Control vectors implementation by [Gapeleon](https://github.com/gapeleon)

