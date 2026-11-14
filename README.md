#TeXStudio Web — Online LaTeX Editor

A modern, browser-based LaTeX editor with a split-screen workspace, syntax highlighting, real-time PDF compilation, and document preview.

Built to make writing LaTeX documents simple, accessible, and efficient.

✨ Features

- Monaco Code Editor — Professional code editing with LaTeX syntax highlighting.
- Split-Screen Workspace — Write LaTeX and preview compiled PDFs side by side.
- PDF Compilation — Compile ".tex" documents using the "pdflatex" engine.
- PDF Preview — View generated documents directly in your browser.
- Download PDF — Export compiled documents.
- Import & Export — Open and save ".tex" files.
- Starter Templates — Blank document, student assignment, and research paper.
- Dark & Light Mode — Switch between editor themes.
- Compilation Logs — View compilation output and errors.
- Responsive Design — Works across desktop and mobile screens.

🛠️ Tech Stack

Technology| Purpose
React.js| Frontend UI
Vite| Development and build tool
Monaco Editor| Code editor
Node.js| Backend runtime
Express.js| REST API
TeX Live| LaTeX compilation
PDF.js / Browser PDF Viewer| PDF rendering

📁 Project Structure

texstudio-web/
│
├── src/
│   ├── App.jsx
│   ├── main.jsx
│   └── styles.css
│
├── server/
│   └── index.js
│
├── index.html
├── package.json
├── vite.config.js
├── Dockerfile
├── docker-compose.yml
├── .gitignore
└── README.md

⚙️ Installation

Prerequisites

Install the following:

- Node.js 20 or later
- npm
- TeX Live with "pdflatex" installed

1. Clone the repository

git clone https://github.com/YOUR_USERNAME/texstudio-web.git

2. Navigate to the project

cd texstudio-web

3. Install dependencies

npm install

4. Start the development server

npm run dev

5. Open in browser

http://localhost:5173

The Vite frontend runs on port 5173, and the Express API runs on port 3001.

🚀 Deployment

Frontend — Netlify

1. Push your project to GitHub.
2. Connect the repository to Netlify.
3. Set the build command:

npm run build

4. Set the publish directory:

dist

5. Add the environment variable:

VITE_API_BASE_URL=https://your-backend-url

6. Deploy the website.

Backend — Docker Hosting

The backend requires a working LaTeX installation.

The included Dockerfile installs TeX Live and runs the Express server.

You can deploy the Docker image on a compatible container hosting platform.

Configure:

PORT=3001
CORS_ORIGIN=https://your-site.netlify.app

Verify the backend:

https://your-backend-url/api/health

Expected response:

{
  "ok": true,
  "engine": "pdflatex"
}

🔌 API Reference

Health Check

GET /api/health

Checks whether the backend is running.

Compile LaTeX

POST /api/compile
Content-Type: application/json

Request:

{
  "filename": "main.tex",
  "source": "\\documentclass{article}\\begin{document}Hello World\\end{document}"
}

Response:

- Success: Compiled PDF ("application/pdf").
- Failure: JSON error response with compilation logs.

🔒 Security

LaTeX compilation executes document-processing commands and must be treated as untrusted input.

Before public production deployment:

- Use isolated compilation containers or sandboxes.
- Disable shell escape.
- Restrict network access.
- Apply CPU, memory, and execution-time limits.
- Add API rate limiting and request validation.
- Run compilation under a non-root user.
- Clean up temporary compilation files.

The current project is an MVP and should not be exposed as an unrestricted public compilation service.

🗺️ Future Roadmap

- [ ] Live compilation
- [ ] Multiple file and project management
- [ ] Automatic document saving
- [ ] PDF page navigation
- [ ] Advanced LaTeX templates
- [ ] Resume builder
- [ ] BibTeX support
- [ ] User authentication
- [ ] Cloud project storage
- [ ] Project sharing
- [ ] Isolated compilation workers

🤝 Contributing

Contributions, feature requests, and bug reports are welcome.

1. Fork the repository.
2. Create a feature branch.
3. Commit your changes.
4. Open a Pull Request.

📄 License

This project is currently unlicensed. Add a LICENSE file before distributing or accepting contributions under specific reuse terms.

---

TeXStudio Web

Write LaTeX. Compile PDF. Create beautifully formatted documents.

Made with ❤️ for students, developers, and researchers.
