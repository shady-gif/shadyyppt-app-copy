# ShadyPPT Copy Deployment Notes

This folder is the separate working copy for the new GitHub Desktop and Vercel project.

## Recommended Flow

1. Open GitHub Desktop.
2. Add this local folder:
   `/Users/sarrthakchauhan/Desktop/shadyyppt-app-copy`
3. Create or publish it as a new GitHub repository.
4. Connect that new repository to Vercel.
5. Set the Vercel build command to:
   `npm run build`
6. Set the Vercel output directory to:
   `dist`
7. Set this Vercel environment variable after the backend is deployed:
   `PPT_API_BASE_URL=https://your-backend-url`

## Backend Requirement

The Vercel site can host the frontend pages, including `/app`, but PowerPoint generation uses the Python backend in `server.py`.

For production generation, deploy the backend separately on Render or another Python-friendly service. The included `render.yaml` is prepared for Render.

Required backend environment variable:

`OPENAI_API_KEY`

Optional backend environment variables:

`OPENAI_MODEL=gpt-5-nano`
`DISABLE_OLLAMA_MAPPER=1`
`CORS_ORIGIN=*`

## Local Checks

Run these before committing major changes:

```bash
npm run build
npm run test:node
npm run test:python
```

## Collaboration Note

Design and product changes should happen in small steps. After each meaningful UI change, test locally, review visually, then commit through GitHub Desktop.
