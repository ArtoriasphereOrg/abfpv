![Nuke](https://image.abfpv.workers.dev/2b5e9aec33ec8e37121ff7bd9b060019782d01edde95ee7f561d1ef7d182a4bb.webp)

# ABFPV - Always Best Free Packed Vault

[![GitHub Repo](https://img.shields.io/badge/GitHub-Repo-blue?logo=github)](https://github.com/ArtoriasphereOrg/ABFPV)  
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)  
[![Project](https://img.shields.io/badge/Project-AITRD-orange)](https://github.com/ArtoriasphereOrg/)

## Description

ABFPV (Always Best Free Packed Vault) is a specialized file upload system designed for easy uploading, link generation, and sharing. It allows users to upload files up to 100MB, automatically generates timestamped shareable links, and supports embedding or distribution. The system features a modern, responsive UI with drag-and-drop functionality, multilingual support (English and Thai), and an API for integration.

This project is part of the **AITRD (ArtoriasphereOrg)** initiative, focusing on secure and efficient file handling tools for research and development.

### Dependencies
- **External Libraries (CDN):**
  - Highlight.js (for code syntax highlighting): `https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.7.0/`
  - Google Fonts: Noto Sans JP and Sarabun.
- No npm/yarn dependencies; everything is embedded or loaded via CDN.

### API Usage
Integrate file uploads into your applications using the provided endpoint.

#### Endpoint
```
POST https://image.abfpv.workers.dev/
```

#### Parameters
- `file`: The file to upload (multipart/form-data).

#### cURL Example
```
curl -X POST \
  -F "file=@your-file.ext" \
  https://image.abfpv.workers.dev/
```
- Response: A direct URL to the uploaded file (plain text).

#### JavaScript Example
```javascript
const formData = new FormData();
formData.append("file", myFile);

fetch("https://image.abfpv.workers.dev/", {
  method: "POST",
  body: formData
})
.then(response => response.text())
.then(url => console.log(url));
```

**Note:** The server handles the upload and returns a link. File size limit: 100MB. Ensure your backend enforces security (e.g., file type validation).
