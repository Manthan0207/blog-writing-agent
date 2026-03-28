# blog_agent.ipynb

LangGraph notebook that generates a technical blog post and optionally adds AI-generated images.

## What It Does
- Routes topic as `closed_book` / `hybrid` / `open_book`
- Runs Tavily web research when needed
- Builds a structured blog plan
- Writes sections in parallel with LangGraph workers
- Merges markdown and inserts image placeholders
- Generates images with Gemini and saves final markdown

## Required Environment Variables
Create a `.env` file in this folder (or copy from `.env.example`):

```env
OPENAI_API_KEY=your_openai_api_key
TAVILY_API_KEY=your_tavily_api_key
GOOGLE_API_KEY=your_google_api_key
```

## Quick Setup
```bash
pip install -U langgraph langchain-openai langchain-community pydantic python-dotenv tavily-python google-genai
```

## Run
1. Open `5_bwa_image.ipynb`
2. Run all cells
3. Call:

```python
run("Neural Network")
```

## Output
- `<topic_slug>.md` in this folder
- Generated images in `images/`

## Notes
- If image generation fails, the notebook keeps the markdown output with a fallback block.
- `GOOGLE_API_KEY` is required only for image generation.
