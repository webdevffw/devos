We want to implement in the following workflow pattern

- Gain a high level understanding of the problem domain & the available tools
- Implement domain solutions one layer at a time and keep track of the methodology & structure
  - Structure & configuration
  - Concepts & information
  - Purpose & preferences
- Abstract the methodology and structue into a reproduceable workflow for modular implementation

We also want to create a similar overview of the AI tool stack, perhaps less the centralized config structure, broken down into the following layers based on a local machine or personal server space (running the models on owned environments like VPS or a dedicated server):
- LLM Models
- Whatever functionality Ollama provides
- Whatever functionality Huggingface provides (What exactly are transformers?)
- Connecting local systems to hosted AI models & interfaces (HTTP? SSH?)
- Local interfaces for AI enhanced coding
  - What are agents, do they fit in this context, & how do they serve us?
  - CLI coding functionality (Aider, Opencode)
  - IDE integrations that rely on backend models (Continue, Aider?)
- AI model analysis (LM Studio)
- System analysis tools & methods for observing resource usage

For the AI brainstorming, we also want to generate a similar brainstorm, but including categories specific to this space (AI in general, or the specific tool layer if applicable).

Later, when we come to implement the AI platform, we will run a top down process instead of only installing & using a single module at a time. Including the option to use multiple interfaces that perform the same action interchangeably, such as simultaneous access to Aider & Opencode.
