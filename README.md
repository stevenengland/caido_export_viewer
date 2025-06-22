# Caido Export Viewer

A web-based tool for viewing and analyzing HTTP request data exported from Caido in a human-friendly format.

## Overview

[Caido](https://caido.io/) is a lightweight web security auditing toolkit that allows security professionals to intercept, modify, and analyze HTTP traffic. While Caido provides excellent functionality for capturing and exporting HTTP requests and responses, it doesn't include a built-in viewer for the exported JSON data.

This viewer bridges that gap by providing an intuitive, web-based interface to analyze your exported Caido data without needing to parse raw JSON files manually.

## The Problem

When you export HTTP requests from Caido, you receive a JSON file containing all the captured traffic data. However, this exported data has several limitations:

- **Raw Format**: The request and response data is base64-encoded and difficult to read
- **No Visual Interface**: You need to manually parse JSON to understand the HTTP traffic
- **Poor Readability**: Headers, bodies, and metadata are mixed together in the raw format
- **Time-Consuming Analysis**: Finding specific requests or comparing request/response pairs is tedious

## The Solution

The Caido Export Viewer provides:

- **Clean Visual Interface**: Side-by-side view of requests and responses
- **Automatic Parsing**: Automatically decodes and separates headers from body content
- **Easy Navigation**: Searchable table view of all requests with key information
- **Detailed Analysis**: Clear separation of request info, headers, and body content
- **No Installation Required**: Works directly in your browser

## Usage

### Getting Started

1. **Export Data from Caido**:

   - In Caido, select the requests you want to analyze
   - Export them as JSON format
   - Save the file to your computer

2. **Open the Viewer**:

   - Open `caido-viewer.html` in any modern web browser
   - No installation or server setup required

3. **Load Your Data**:
   - Drag and drop your exported JSON file onto the upload area, or
   - Click the upload area to select your file

## Supported Data Format

The viewer expects JSON files exported from Caido with the following structure:

```json
[
  {
    "id": 3000,
    "host": "example.com",
    "method": "GET",
    "path": "/api/endpoint",
    "port": 443,
    "is_tls": true,
    "length": 852,
    "raw": "base64-encoded-request-data",
    "response": {
      "id": 2205,
      "status_code": 200,
      "length": 1740,
      "raw": "base64-encoded-response-data"
    }
  }
]
```

## Security & Privacy

- **No Data Upload**: All processing happens locally in your browser
- **No Network Requests**: The viewer doesn't send data to any external servers
- **Client-Side Only**: Your sensitive HTTP traffic data never leaves your machine

## Troubleshooting

### Common Issues

**File won't load**:

- Ensure the file is a valid JSON export from Caido
- Check that the file isn't corrupted or truncated

**Headers not displaying**:

- This usually indicates the raw data isn't properly base64-encoded
- Verify the export was completed successfully in Caido

**Empty body content**:

- Some requests (like GET requests) may not have body content
- This is normal and expected behavior

**Note**: This viewer is an independent tool and is not officially affiliated with Caido. It's designed to complement Caido's functionality by providing better visualization of exported data.
