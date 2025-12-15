# Development Guide

## Quick Start

1. **Install Dependencies**
   ```bash
   npm install
   ```

2. **Start Development Server**
   ```bash
   npm run dev
   ```
   The server will start on `http://localhost:3000` and automatically open in your browser.

3. **Make Changes**
   - Edit `index.html` for HTML changes
   - Edit `src/styles.css` for styling
   - Edit `src/script.js` for JavaScript functionality
   - Add images to `public/images/`

4. **Auto-Reload**
   The development server automatically reloads when you save changes to any file.

## Project Structure

```
├── index.html          # Main entry point
├── src/                # Source files
│   ├── styles.css     # All CSS styles
│   └── script.js      # All JavaScript
├── public/            # Static assets
│   ├── images/        # Image files
│   ├── robots.txt     # SEO configuration
│   └── sitemap.xml    # SEO sitemap
└── docs/              # Documentation files
```

## Available Scripts

- `npm run dev` - Start development server with live reload (port 3000)
- `npm start` - Same as `npm run dev`
- `npm run serve` - Start http-server (alternative server)

## Development Tips

1. **File Paths**: All paths in HTML are relative to the root directory
   - CSS: `src/styles.css`
   - JS: `src/script.js`
   - Images: `public/images/filename.png`

2. **Browser DevTools**: Use browser developer tools to debug and test responsive designs

3. **Testing**: Test on multiple browsers and devices for compatibility

4. **Performance**: The site uses vanilla JavaScript and CSS for optimal performance

## Production Deployment

For production, you can deploy the entire project folder to:
- GitHub Pages
- Netlify
- Vercel
- Any static hosting service

No build step is required - just upload the files!

