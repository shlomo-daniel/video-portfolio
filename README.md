# Videographer Portfolio

A simple, elegant single-page portfolio website for videographers with client-editable content via Google Sheets.

## Features

- ✅ Single-page responsive design
- ✅ Google Sheets as content management system
- ✅ Vimeo video integration with thumbnails
- ✅ Three category filters (Weddings, Corporate, Events)
- ✅ Click-to-play video functionality
- ✅ 1-hour localStorage caching for performance
- ✅ Graceful error handling with cache fallback
- ✅ Mobile-responsive design
- ✅ No backend required - fully static
- ✅ Free hosting on Vercel

## Technology Stack

- **Frontend:** HTML, CSS, JavaScript (Vanilla - no frameworks)
- **Video Hosting:** Vimeo (Free tier - 5GB storage)
- **CMS:** Google Sheets + Google Sheets API v4
- **Hosting:** Vercel
- **Caching:** localStorage (1-hour expiration)

## Project Structure

```
video-portfolio/
├── index.html          # Main website file (complete single-page app)
├── SETUP.md           # Developer setup instructions
├── CLIENT_GUIDE.md    # Client instructions for managing videos
└── README.md          # This file
```

## Quick Start for Developers

1. **Setup Google Sheets API** (see [SETUP.md](SETUP.md))
   - Create Google Cloud project
   - Enable Sheets API
   - Generate API key
   - Create Google Sheet with required columns

2. **Configure the website**
   - Open `index.html`
   - Replace `YOUR_GOOGLE_SHEET_ID_HERE` with your Sheet ID
   - Replace `YOUR_GOOGLE_API_KEY_HERE` with your API key

3. **Deploy to Vercel**
   ```bash
   vercel
   ```

For detailed setup instructions, see [SETUP.md](SETUP.md).

## Quick Start for Clients

See [CLIENT_GUIDE.md](CLIENT_GUIDE.md) for instructions on:

- How to upload videos to Vimeo
- How to add videos to the website
- How to manage categories
- Troubleshooting common issues

## Google Sheet Structure

The Google Sheet must have these columns (case-sensitive):

| Column        | Description                                   | Required | Example                    |
| ------------- | --------------------------------------------- | -------- | -------------------------- |
| `videoId`     | Vimeo video ID number                         | Yes      | `123456789`                |
| `title`       | Video title                                   | Yes      | `Beautiful Summer Wedding` |
| `description` | Video description                             | No       | `John & Sarah's ceremony`  |
| `category`    | Must be: `Weddings`, `Corporate`, or `Events` | Yes      | `Weddings`                 |

## Configuration Options

In `index.html`, you can customize:

```javascript
const CONFIG = {
  SHEET_ID: "YOUR_GOOGLE_SHEET_ID_HERE",
  API_KEY: "YOUR_GOOGLE_API_KEY_HERE",
  SHEET_NAME: "Videos", // Change if your sheet tab has a different name
  CACHE_DURATION: 60 * 60 * 1000, // 1 hour - adjust as needed
  CATEGORIES: ["Weddings", "Corporate", "Events"], // Add/modify categories
};
```

## Customization

### Change Colors

Edit CSS variables in `index.html`:

```css
:root {
  --primary-color: #2c3e50; /* Main dark color */
  --secondary-color: #3498db; /* Accent blue */
  --accent-color: #e74c3c; /* Error/alert red */
}
```

### Change Hero Content

Edit the hero section HTML:

```html
<section class="hero">
  <h1>Your Title Here</h1>
  <p>Your tagline here</p>
</section>
```

### Change About Section

Edit the about section HTML:

```html
<section class="about">
  <h2>About</h2>
  <p>Your bio here</p>
</section>
```

### Add More Categories

1. Update `CONFIG.CATEGORIES` array
2. Add category buttons to HTML
3. Update `CLIENT_GUIDE.md` with new category names

## Performance Features

- **localStorage caching:** Videos cached for 1 hour to reduce API calls
- **Lazy loading:** Video iframes only loaded when clicked
- **Thumbnail optimization:** Shows Vimeo thumbnails or color blocks
- **Error resilience:** Falls back to cache if API fails

## Browser Support

- Chrome 88+ ✅
- Firefox 87+ ✅
- Safari 14+ ✅
- Edge 89+ ✅
- Mobile browsers ✅

## Vimeo Free Tier Limits

- **Storage:** 5GB total
- **Videos:** Approximately 25-30 minutes of HD video
- **Upload:** Up to 500MB per week
- **Basic analytics:** View counts and play stats

To increase limits, upgrade to Vimeo Plus ($7/month) for 250GB storage.

## Troubleshooting

### Videos not loading

- Check API key and Sheet ID in `index.html`
- Verify Google Sheet is public (anyone with link can view)
- Check browser console for errors

### Vimeo videos won't play

- Videos must be set to "Public" or "Unlisted" (not "Private")
- Verify video IDs are correct
- Check video is fully processed on Vimeo

### Categories not working

- Category names must match exactly: `Weddings`, `Corporate`, `Events`
- Check for typos or extra spaces
- Values are case-sensitive

For more troubleshooting, see [CLIENT_GUIDE.md](CLIENT_GUIDE.md).

## Deployment

### Vercel (Recommended)

**Option 1: GitHub Integration**

```bash
git init
git add .
git commit -m "Initial commit"
git push origin main
```

Then connect repository in Vercel dashboard.

**Option 2: Vercel CLI**

```bash
npm install -g vercel
vercel
```

**Option 3: Drag & Drop**
Drag the project folder onto vercel.com

### Other Platforms

This is a static site and works on:

- Netlify
- GitHub Pages
- Cloudflare Pages
- Any static hosting service

## Security

- API key is restricted to specific domains in Google Cloud Console
- Google Sheet is read-only (public viewing only)
- No backend = no server vulnerabilities
- HTTPS enforced by Vercel

## Future Enhancements

Potential additions:

- Contact form integration
- Instagram feed integration
- Testimonials section
- Image gallery
- Search functionality
- More video platforms (YouTube, Wistia)
- Admin dashboard for non-technical clients
- Video upload directly from website

## License

This project is provided as-is for personal or commercial use.

## Support

For issues or questions:

1. Check [SETUP.md](SETUP.md) for setup issues
2. Check [CLIENT_GUIDE.md](CLIENT_GUIDE.md) for usage issues
3. Check browser console for errors
4. Contact your developer

## Credits

Built with vanilla HTML, CSS, and JavaScript. No frameworks, no build process, just simple and effective.
