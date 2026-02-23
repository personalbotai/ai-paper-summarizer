# AI Research Paper Summarizer

A web application that fetches and displays AI/ML research papers from ArXiv with AI-generated summaries (demo version). Built with vanilla JavaScript and Tailwind CSS.

## Features

- **ArXiv Search**: Search papers by keywords or arXiv ID
- **Paper List**: View search results with titles, authors, categories, and abstracts
- **Detail Modal**: Click to see full paper details and simulated AI summary
- **PDF Link**: Direct link to download the PDF
- **Responsive Design**: Works on all devices
- **Dark Theme**: Easy on the eyes
- **GitHub Pages**: Deploy as static site

## Tech Stack

- **Frontend**: Vanilla HTML/JS
- **Styling**: Tailwind CSS (CDN)
- **Syntax Highlighting**: highlight.js
- **Icons**: Font Awesome
- **Data Source**: ArXiv API (public)
- **Deployment**: GitHub Pages

## Usage

1. Open `index.html` in a browser
2. Enter a search term or arXiv ID (e.g., "transformer" or "2301.07041")
3. Click a paper to view details and summary

### Local Development

```bash
python -m http.server 8000
# Open http://localhost:8000
```

## Deployment to GitHub Pages

1. Push this repository to GitHub
2. Go to repository Settings → Pages
3. Set source to "Deploy from a branch"
4. Select branch: `main`, folder: `/ (root)`
5. Save. Site will be available at: `https://<username>.github.io/ai-paper-summarizer/`

## Project Structure

```
ai-paper-summarizer/
├── index.html       # Main application
├── README.md        # This file
└── .gitignore       # Git ignore file
```

## Real AI Summarization

This demo uses simulated summaries. To add real AI summarization:

1. Set up a backend service (e.g., on Vercel, Netlify, or a separate server)
2. Integrate with an LLM API (OpenAI, Anthropic, or open-source model)
3. Modify the `generateSimulatedSummary()` function to call your backend:
   ```javascript
   async function fetchSummary(paperId) {
       const response = await fetch('https://your-backend.com/summarize', {
           method: 'POST',
           body: JSON.stringify({ paperId })
       });
       return response.json().summary;
   }
   ```

## API Notes

- ArXiv API is rate-limited but generous for low-volume use
- No API key required
- Returns Atom XML format (parsed client-side)

## License

MIT