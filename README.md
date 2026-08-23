# Top 50 New AI/LLM GitHub Repos

A polished, searchable directory of the top 50 trending new AI and LLM GitHub repositories from the last 30 days, sorted by stars.

[![Security](https://img.shields.io/badge/security-hardened-green.svg)](SECURITY.md)
[![License](https://img.shields.io/badge/license-contact_owner-blue.svg)](#license)

## What is this?

This is a static HTML website that displays a curated list of the top 50 newly created AI and LLM GitHub repositories. The data is based on a GitHub search snapshot for repositories created on or after 2026-04-25, matching the query "ai OR llm" and sorted by star count.

## Features

- ⚡ **Searchable Directory**: Filter repositories by name, owner, description, or category
- 🔄 **Multiple Sort Options**: Sort by stars (high/low), name (A-Z/Z-A), or original rank
- 📁 **Category Filtering**: Browse by Agents, Coding, Infra, Learning, Security, Tooling, Creative, Data, and Other
- ⭐ **Featured Top 5**: Highlighted section showcasing the most starred repositories
- 📄 **Pagination**: Results paginated with 12 repositories per page
- 🌓 **Dark/Light Theme**: Toggle with persistent preference storage
- 📱 **Responsive Design**: Mobile-friendly layout for all screen sizes
- 📊 **Visual Progress Bars**: Star count visualization for each repository
- 📈 **Category Statistics**: Dynamic breakdown by category

## Technology Stack

- Pure HTML5, CSS3, and vanilla JavaScript
- No external dependencies or frameworks
- Self-contained single-page application
- Client-side rendering and filtering

## Running Locally

### Quick Start

Since this is a static HTML site with no build process, you can run it directly:

```bash
# Open directly in browser
open index.html  # macOS
xdg-open index.html  # Linux
start index.html  # Windows
```

### Local HTTP Server (Recommended)

For a production-like environment:

**Python 3:**
```bash
python3 -m http.server 8000
# Visit http://localhost:8000
```

**Node.js:**
```bash
npx http-server -p 8000
# Visit http://localhost:8000
```

**PHP:**
```bash
php -S localhost:8000
# Visit http://localhost:8000
```

## Deployment

Deploy to any static hosting service:

- **GitHub Pages**: Push to `gh-pages` branch or configure in settings
- **Netlify**: Drag and drop or connect repository
- **Vercel**: Deploy with `vercel` CLI or connect repository
- **CloudFlare Pages**: Connect repository
- **AWS S3**: Upload to bucket with static hosting enabled

No build step, environment variables, or server configuration required.

## Project Structure

```
.
├── index.html          # Main HTML file with all code and data
├── README.md           # This file
├── SECURITY.md         # Security policy and guidelines
└── .gitignore          # Git ignore rules
```

## Configuration

### Updating Repository Data

The repository data is in a JavaScript array within `index.html` (line ~569). Update entries following this structure:

```javascript
{
  rank: 1,
  name: "owner/repo",
  owner: "owner",
  repo: "repo",
  stars: 4799,
  category: "creative",  // agent, coding, infra, learning, security, tooling, creative, data, other
  url: "https://github.com/owner/repo",
  desc: "Repository description"
}
```

### Theme Customization

CSS variables in `:root` (lines 12-45). Modify to change colors:

```css
:root {
  --bg: #07111f;
  --accent: #6ea8fe;
  --text: #edf3ff;
  /* ...more */
}
```

### Pagination

Change items per page by modifying `perPage` (line ~638):

```javascript
const perPage = 12;  // Adjust this value
```

## Browser Support

Works in all modern browsers:
- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Opera 76+

## Security

This project implements comprehensive security measures:

- ✅ XSS protection via HTML escaping
- ✅ Safe DOM manipulation
- ✅ No hardcoded secrets
- ✅ Secure external links with `rel="noreferrer"`
- ✅ Bounds checking for all dynamic values

See [SECURITY.md](SECURITY.md) for full security policy and reporting procedures.

## Accessibility

- Semantic HTML5 elements
- Proper heading hierarchy
- Keyboard navigation support
- Sufficient color contrast ratios
- Responsive text sizing

## License

License not specified. Contact the repository owner for licensing information.

## Contributing

To suggest improvements or report issues, please open an issue or pull request.

## Contact

For questions or feedback, contact the maintainer through GitHub.

---

**Last Updated**: August 2026  
**Data Snapshot**: Repositories created on or after 2026-04-25
