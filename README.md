# Terabox API

A Python Flask API for processing Terabox share links and generating direct download links.

## Features

- Extract direct download links from Terabox share URLs
- Support for multiple Terabox domains
- Folder support (processes files within folders)
- File size formatting
- Thumbnail information
- Error handling and retry logic

## Supported Domains

- terabox.com
- 1024terabox.com
- teraboxapp.com
- teraboxlink.com
- terasharelink.com
- terafileshare.com
- 1024tera.com
- 1024tera.cn
- teraboxdrive.com
- dubox.com

## Installation

1. Clone the repository
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

Run the Flask app:

```bash
python src/main.py
```

The API will start on port 3000.

### Endpoints

- `GET /`: Home endpoint with API information
- `GET /api?url=<TERABOX_SHARE_URL>`: Process a Terabox URL and return file information

### Example

```bash
curl "http://localhost:3000/api?url=https://terabox.com/s/1example"
```

Response:
```json
{
  "status": "success",
  "url": "https://terabox.com/s/1example",
  "files": [
    {
      "file_name": "example.mp4",
      "size": "1.23 GB",
      "size_bytes": 1320000000,
      "download_url": "https://...",
      "direct_download_url": "https://...",
      "is_directory": false,
      "modify_time": 1640995200,
      "thumbnails": {...}
    }
  ],
  "processing_time": "2.34s",
  "file_count": 1,
  "cookies": "valid"
}
```

## Deployment to Vercel

1. Install Vercel CLI:
   ```bash
   npm install -g vercel
   ```

2. Deploy to Vercel:
   ```bash
   vercel
   ```

   Follow the prompts to link your Vercel account and deploy the project.

3. The API will be available at the Vercel-provided URL.

## Disclaimer

This API is for educational purposes only. Please respect Terabox's terms of service and copyright laws.