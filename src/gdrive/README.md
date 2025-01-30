# Google Drive server
[![smithery badge](https://smithery.ai/badge/@smithery-ai/gdrive)](https://smithery.ai/server/@smithery-ai/gdrive)

This MCP server integrates with Google Drive to allow listing, reading, and searching over files.

## Components

### Tools

- **search**
  - Search for files in Google Drive
  - Input: `query` (string): Search query
  - Returns file names and MIME types of matching files

### Resources

The server provides access to Google Drive files:

- **Files** (`drive:///<file_id>`)
  - Supports all file types
  - Google Workspace files are automatically exported:
    - Docs → Markdown
    - Sheets → CSV
    - Presentations → Plain text
    - Drawings → PNG
  - Other files are provided in their native format

## Getting started

1. [Create a new Google Cloud project](https://console.cloud.google.com/projectcreate)
2. [Enable the Google Drive API](https://console.cloud.google.com/apis/library/drive.googleapis.com)
3. [Configure an OAuth consent screen](https://console.cloud.google.com/apis/credentials/consent)
4. Add OAuth scope `https://www.googleapis.com/auth/drive.readonly`
5. [Create an OAuth Client ID](https://console.cloud.google.com/apis/credentials/oauthclient) for application type "Desktop App"
6. Download the JSON file of your client's OAuth keys
7. Rename the key file to `gdrive-oauth.keys.json` and place into the root of this repo

Make sure to build the server with either `npm run build` or `npm run watch`.

### Installing via Smithery

To install Google Drive for Claude Desktop automatically via [Smithery](https://smithery.ai/server/@smithery-ai/gdrive):

```bash
npx -y @smithery/cli install @smithery-ai/gdrive --client claude
```

### Authentication

To authenticate and save credentials:

1. Run the server with the `auth` argument: `node ./dist auth`
2. This will open an authentication flow in your system browser
3. Complete the authentication process
4. Credentials will be saved in the root of this repo

## License

This MCP server is licensed under the MIT License. This means you are free to use, modify, and distribute the software, subject to the terms and conditions of the MIT License. For more details, please see the LICENSE file.
