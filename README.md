# Top 50 New AI/LLM GitHub Repos

A polished, searchable directory of the top 50 trending new AI and LLM GitHub repositories from the last 30 days, sorted by stars.

## What is this?

This is a static HTML website that displays a curated list of the top 50 newly created AI and LLM GitHub repositories. The data is based on a GitHub search snapshot for repositories created on or after 2026-04-25, matching the query "ai OR llm" and sorted by star count.

## Features

- **Searchable Directory**: Filter repositories by name, owner, description, or category
- **Multiple Sort Options**: Sort by stars (high/low), name (A-Z/Z-A), or original rank
- **Category Filtering**: Browse by categories including Agents, Coding, Infra, Learning, Security, Tooling, Creative, Data, and Other
- **Featured Top 5**: Highlighted section showcasing the top 5 most starred repositories
- **Pagination**: Results are paginated with 12 repositories per page
- **Dark/Light Theme**: Toggle between dark and light themes with persistent preference storage
- **Responsive Design**: Mobile-friendly layout that adapts to different screen sizes
- **Visual Progress Bars**: Star count visualization for each repository
- **Category Statistics**: Dynamic breakdown of visible repositories by category

## Technology Stack

- Pure HTML5, CSS3, and vanilla JavaScript
- No external dependencies or frameworks
- Self-contained single-page application
- Client-side rendering and filtering

## Running the Project

### Local Development

Since this is a static HTML site with no build process or dependencies, you can run it in several ways:

#### Option 1: Direct File Opening
Simply open `index.html` in your web browser:
```bash
# On macOS
open index.html

# On Linux
xdg-open index.html

# On Windows
start index.html
```

#### Option 2: Local HTTP Server (Recommended)
Using a local web server provides a more production-like environment:

**Python 3:**
```bash
python3 -m http.server 8000
# Visit http://localhost:8000
```

**Python 2:**
```bash
python -m SimpleHTTPServer 8000
# Visit http://localhost:8000
```

**Node.js (with http-server):**
```bash
npx http-server -p 8000
# Visit http://localhost:8000
```

**PHP:**
```bash
php -S localhost:8000
# Visit http://localhost:8000
```

### Deployment

This site can be deployed to any static hosting service:

- **GitHub Pages**: Push to a `gh-pages` branch or configure in repository settings
- **Netlify**: Drag and drop the directory or connect your repository
- **Vercel**: Deploy with `vercel` CLI or connect your repository
- **CloudFlare Pages**: Connect your repository and deploy
- **AWS S3**: Upload to an S3 bucket with static website hosting enabled
- **Azure Static Web Apps**: Deploy via Azure portal or CLI

No build step, environment variables, or server-side configuration is required.

## Project Structure

```
.
├── index.html          # Main HTML file containing all code, styles, and data
├── README.md           # This file
├── SECURITY.md         # Security policy and guidelines
└── .gitignore         # Git ignore rules
```

## Configuration

### Data Source
The repository data is hardcoded as a JavaScript array within `index.html` (starting at line 569). To update the data:

1. Locate the `repos` array in the `<script>` section
2. Modify or replace repository entries following this structure:
```javascript
{
  rank: 1,                              // Position in ranking
  name: "owner/repo",                   // Full repository name
  owner: "owner",                       // GitHub username/org
  repo: "repo",                         // Repository name
  stars: 4799,                          // Star count
  category: "creative",                 // One of: agent, coding, infra, learning, security, tooling, creative, data, other
  url: "https://github.com/owner/repo", // Full GitHub URL
  desc: "Description of the repository" // Brief description
}
```

### Theme Customization
CSS custom properties (CSS variables) are defined in the `:root` selector (lines 12-28 for dark theme, 30-45 for light theme). Modify these to change the color scheme:

```css
:root {
  --bg: #07111f;           /* Main background */
  --accent: #6ea8fe;       /* Primary accent color */
  --text: #edf3ff;         /* Main text color */
  /* ... and more */
}
```

### Pagination
The number of repositories per page can be adjusted by changing the `perPage` constant on line 634:
```javascript
const perPage = 12;  // Change this value
```

## Browser Support

This site uses modern web APIs and should work in all current browsers:
- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Opera 76+

Features used that require modern browsers:
- CSS Grid and Flexbox
- CSS Custom Properties (variables)
- Template literals
- Array methods (map, filter, sort)
- LocalStorage API
- Clipboard API (for copy functionality)
- Smooth scrolling

## Accessibility

- Semantic HTML5 elements (`<header>`, `<main>`, `<section>`, `<article>`)
- Proper heading hierarchy (h1, h2, h3)
- Alt text and ARIA labels where applicable
- Keyboard navigation support
- Sufficient color contrast ratios
- Responsive text sizing

## License

This project's license is not specified. Contact the repository owner for licensing information.

## Contributing

To suggest improvements or report issues, please open an issue or pull request on the GitHub repository.

## Contact

For questions or feedback, please contact the repository maintainer through GitHub.

---

**Last Updated**: August 2026  
**Data Snapshot**: Repositories created on or after 2026-04-25
