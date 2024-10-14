# ARCHSCAN

ARCHSCAN is an innovative tool designed to streamline the surveying process for large construction projects, specifically targeting the UK's underinvested infrastructure. By leveraging aerial footage, ARCHSCAN provides insightful summaries that go beyond human vision, reducing the need for extensive on-site visits.

## Inspiration
The UK's infrastructure has faced significant challenges due to prolonged underinvestment. Surveying and assessing the condition of infrastructure elements like bridges, buildings, and tunnels are labor-intensive and require skilled personnel. ARCHSCAN aims to simplify this process and empower surveyors and landowners by automating aerial footage analysis, providing actionable insights.

## What it Does
ARCHSCAN processes aerial footage to:
- Generate targeted, descriptive summaries of the site.
- Identify specific infrastructure elements and assess their condition.
- Offer actionable insights without requiring manual review of footage.

## How We Built It
ARCHSCAN combines two advanced AI models in a multi-agent system:

1. **Pixtral**:
   - Fine-tuned on drone and aerial imagery, along with Visual Question Answering (VQA) pairs.
   - Provides descriptive summaries and identifies key infrastructure elements.
   - Uses Nebius-hosted NVIDIA H100 machine for finetuning and inference.

2. **Mistral Large 2**:
   - Processes Pixtral's outputs to generate actionable insights and recommendations.
   - Leverages large parameter counts for advanced reasoning and synthesis.

The tool is accessible through a Gradio UI, allowing users to select frames and receive summarized outputs.

## Finetuning Details
- **LoRA Finetuning**: Focused on drone and aerial imagery, using datasets like FloodNet Track 2 and FGVC Aircraft for enhanced contextual understanding.
- **Hardware**: Finetuning and inference were carried out on an NVIDIA H100 machine for optimal performance.

## Workflow
1. Extract frames from video footage.
2. Process each frame with Pixtral.
3. Summarize and synthesize the results using Mistral Large 2 for actionable insights.

## Challenges
- Rate limiting on Mistral API.
- High inference time per frame on Pixtral, which affects processing speed for large sets of frames.

## Accomplishments
- Successfully fine-tuned Pixtral for accurate and relevant summaries.
- Created a practical tool that can help surveyors and landowners reduce on-site workload.

## What We Learned
- Multi-agent frameworks can provide powerful results with combined VLM and LLM capabilities.
- Fine-tuning specific models like Pixtral significantly enhances output relevance.

## What's Next for ARCHSCAN
- **Human-in-the-loop**: Incorporate surveyor feedback to refine outputs.
- **Dataset Expansion**: Enhance accuracy with more specialized datasets.
- **Advanced Techniques**: Use multimodal embeddings and RAG (Retrieval-Augmented Generation) for faster, higher-quality summaries.

## Built With
- GitHub
- Gradio
- NVIDIA H100
- Mistral
- Nebius
- Python
- PyTorch
---

Submit your feedback, and explore our continuous updates on our progress and new features.
