# Skim

A minimalist web screenshot microservice built with **Express** and **Puppeteer**. Capture full-page website screenshots via a simple HTTP GET request.

## Features

- 📸 Full-page PNG screenshots of any public URL
- ⚡ Fast, headless Chrome rendering using Puppeteer
- 🎯 Custom viewport sizing via environment variables
- 🚀 Easily deployable to any Node.js environment

## Installation

Run this image with Docker:

```bash
docker run -d -p 3000:3000 --name skim \
  -e PORT=3000 \
  -e SCREEN_WIDTH=1920 \
  -e SCREEN_HEIGHT=1080 \
  ghcr.io/talyguryn/skim:latest
```

## Usage

Send a GET request to the `/` endpoint with the `url` query parameter:

```bash
curl "http://localhost:3000/?url=https://example.com"
```

The response will be a PNG image of the full-page screenshot.

### Additional Query Parameters

- `width`: Custom width for the screenshot (overrides `SCREEN_WIDTH` env var)
- `height`: Custom height for the screenshot (overrides `SCREEN_HEIGHT` env var)
- `fullPage`: Set to `true` to capture the full page (default: `true`)

## Environment Variables

- `PORT`: The port to run the server on (default: `3000`)
- `SCREEN_WIDTH`: Width of the viewport for screenshots (default: `1920`)
- `SCREEN_HEIGHT`: Height of the viewport for screenshots (default: `1080`)
