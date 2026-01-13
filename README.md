# Image2URL

## Description

Image2URL is a web-based service hosted on Cloudflare Workers that allows users to easily upload videos and receive direct, shareable links automatically. It supports simple drag-and-drop or file selection for uploads, primarily focusing on video formats like .mp4 and .mov. This tool is ideal for quick video sharing without complex setups.

**Note:** Despite the name suggesting images, the current implementation appears to emphasize video uploads based on the site's interface. If image support is intended, it may be available via API or future updates.

## Features

- **Easy Upload Interface:** Drag and drop videos or click to select files directly on the webpage.
- **Supported File Formats:** Primarily .mp4 and .mov (other formats may work but are not explicitly supported).
- **Automatic Link Generation:** Upon successful upload, a direct URL to the video is provided instantly.
- **No Account Required:** Anonymous uploads for quick sharing.
- **Built on Cloudflare Workers:** Ensures fast, scalable, and serverless deployment.

## Usage

1. Visit the website: [https://image.abfpv.workers.dev/](https://image.abfpv.workers.dev/).
2. On the main page, you'll see the upload area with the prompt: "คลิกหรือลากวิดีโอมาวางที่นี่ (รองรับ .mp4, .mov เป็นหลัก)" (Click or drag video here - mainly supports .mp4, .mov).
3. Drag your video file into the designated area or click the "อัปโหลดวิดีโอ" (Upload Video) button to select a file.
4. Wait for the upload to complete (status: "กำลังอัปโหลด..." - Uploading...).
5. Once done, copy the automatically generated link to share your video.

### Example

- Upload a sample .mp4 file.
- Receive a link like `https://image.abfpv.workers.dev/uploads/example.mp4` (hypothetical; actual links depend on the service).

## Installation / Deployment

If you're looking to deploy a similar service:

1. **Prerequisites:**
   - A Cloudflare account with Workers enabled.
   - Basic knowledge of JavaScript and Cloudflare Workers.

2. **Steps:**
   - Create a new Worker in the Cloudflare dashboard.
   - Implement upload logic using Cloudflare's KV (Key-Value) storage or R2 for file hosting.
   - Use HTML/JS for the frontend interface (e.g., a simple form with drag-and-drop support).
   - Deploy to a workers.dev subdomain.

For a basic code skeleton (hypothetical, based on common patterns):

```javascript
addEventListener('fetch', event => {
  event.respondWith(handleRequest(event.request));
});

async function handleRequest(request) {
  if (request.method === 'POST') {
    // Handle file upload logic here (e.g., store in R2 or KV)
    // Return URL
  }
  // Serve HTML for GET requests
  return new Response(html, { headers: { 'Content-Type': 'text/html' } });
}

// Sample HTML for upload page
const html = `
<!DOCTYPE html>
<html lang="th">
<head>
  <title>อัปโหลดวิดีโอ - Image2URL</title>
</head>
<body>
  <h1>อัปโหลดวิดีโอ - Image2URL</h1>
  <p>อัปโหลดวิดีโอ ส่งไฟล์วิดีโอแล้วจะได้ลิงก์อัตโนมัติ</p>
  <div id="drop-area">คลิกหรือลากวิดีโอมาวางที่นี่ (รองรับ .mp4, .mov เป็นหลัก)</div>
  <button>อัปโหลดวิดีโอ</button>
  <!-- Add JS for drag-drop and upload handling -->
</body>
</html>
`;
```


For questions or issues, contact the developer via the associated X account or other channels (not specified on the site). 

*Last updated: January 13, 2026*
