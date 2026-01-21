# Setup Instructions

## Google Cloud Console Setup

### Step 1: Create Google Cloud Project

1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Click on the project dropdown at the top
3. Click "New Project"
4. Enter project name: "Videographer Portfolio"
5. Click "Create"

### Step 2: Enable Google Sheets API

1. In the Google Cloud Console, go to "APIs & Services" → "Library"
2. Search for "Google Sheets API"
3. Click on "Google Sheets API"
4. Click "Enable"

### Step 3: Create API Key

1. Go to "APIs & Services" → "Credentials"
2. Click "Create Credentials" → "API Key"
3. Copy the API key (you'll need this later)
4. Click on the API key to edit it

### Step 4: Restrict API Key (Important for Security)

1. Under "API restrictions":
   - Select "Restrict key"
   - Check only "Google Sheets API"

2. Under "Website restrictions":
   - Select "HTTP referrers (websites)"
   - Click "Add an item"
   - Add your domain (e.g., `https://yourdomain.com/*`)
   - Add Vercel preview domains: `https://*.vercel.app/*`
   - For local testing, add: `http://localhost:*`

3. Click "Save"

## Google Sheet Setup

### Step 1: Create Google Sheet

1. Go to [Google Sheets](https://sheets.google.com/)
2. Create a new spreadsheet
3. Name it "Videographer Portfolio Videos"

### Step 2: Set Up Columns

Create the following columns in the first row (these are headers):

| Column A | Column B | Column C    | Column D |
| -------- | -------- | ----------- | -------- |
| videoId  | title    | description | category |

**Important:** The header names must be exactly as shown above (case-sensitive).

### Step 3: Add Sample Data

Add some sample rows to test:

| videoId   | title                | description                         | category  |
| --------- | -------------------- | ----------------------------------- | --------- |
| 123456789 | Beautiful Wedding    | Amazing ceremony in the countryside | Weddings  |
| 987654321 | Corporate Event 2025 | Annual company meeting highlights   | Corporate |
| 456789123 | Birthday Party       | Surprise party celebration          | Events    |

**Note:** Replace these with real Vimeo video IDs once you have them.

### Step 4: Make Sheet Public

1. Click "Share" button (top right)
2. Click "Change to anyone with the link"
3. Make sure it's set to "Viewer" (not Editor)
4. Click "Done"

### Step 5: Get Sheet ID

1. Look at your browser's URL bar
2. The URL looks like: `https://docs.google.com/spreadsheets/d/SHEET_ID_HERE/edit`
3. Copy the `SHEET_ID_HERE` part (long string of letters and numbers)

## Update Website Configuration

1. Open `index.html` in a text editor
2. Find this section near the top of the `<script>` tag:

```javascript
const CONFIG = {
  SHEET_ID: "YOUR_GOOGLE_SHEET_ID_HERE",
  API_KEY: "YOUR_GOOGLE_API_KEY_HERE",
  SHEET_NAME: "Videos",
  // ...
};
```

3. Replace `YOUR_GOOGLE_SHEET_ID_HERE` with your Sheet ID
4. Replace `YOUR_GOOGLE_API_KEY_HERE` with your API Key
5. If your sheet tab is named something other than "Videos", update `SHEET_NAME`
6. Save the file

## Deploy to Vercel

### Option 1: Using GitHub (Recommended)

1. Create a GitHub repository
2. Push your code:

   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git remote add origin https://github.com/yourusername/your-repo.git
   git push -u origin main
   ```

3. Go to [Vercel](https://vercel.com)
4. Sign up/login with GitHub
5. Click "New Project"
6. Import your repository
7. Click "Deploy"

### Option 2: Using Vercel CLI

1. Install Vercel CLI:

   ```bash
   npm install -g vercel
   ```

2. Login to Vercel:

   ```bash
   vercel login
   ```

3. Deploy:

   ```bash
   cd video-portfolio
   vercel
   ```

4. For production:
   ```bash
   vercel --prod
   ```

### Option 3: Drag & Drop

1. Go to [Vercel](https://vercel.com)
2. Sign up/login
3. Drag the `video-portfolio` folder onto the Vercel dashboard
4. Wait for deployment

## Custom Domain (Optional)

1. In Vercel dashboard, go to your project
2. Click "Settings" → "Domains"
3. Add your custom domain
4. Follow Vercel's instructions to update DNS records
5. Wait for DNS propagation (up to 48 hours)

## Update API Key Restrictions

Once deployed:

1. Go back to Google Cloud Console → Credentials
2. Edit your API key
3. Add your production domain to "Website restrictions":
   - `https://yourdomain.com/*`
   - Keep the Vercel domain: `https://your-project.vercel.app/*`

## Testing

1. Open your deployed website
2. Check browser console (F12) for any errors
3. Verify videos load correctly
4. Test category filtering
5. Test click-to-play functionality
6. Test on mobile devices

## Troubleshooting

### Videos Not Loading

- **Check API Key:** Make sure it's correctly copied in `index.html`
- **Check Sheet ID:** Verify the Sheet ID is correct
- **Check Sheet Permissions:** Sheet must be public (anyone with link can view)
- **Check Column Names:** Headers must be: `videoId`, `title`, `description`, `category`
- **Check Browser Console:** Open DevTools (F12) and look for error messages

### API Key Restrictions Issues

- Make sure your domain is added to the API key restrictions
- Include wildcard: `https://yourdomain.com/*`
- For local testing: `http://localhost:*`

### Vimeo Thumbnails Not Loading

- Verify video IDs are correct
- Check that videos are set to "Public" or "Unlisted" in Vimeo
- Private videos won't load thumbnails or play embedded

### Categories Not Working

- Make sure the `category` column uses exact values: "Weddings", "Corporate", or "Events"
- Categories are case-sensitive
- Check for extra spaces in category names

## Next Steps

Proceed to `CLIENT_GUIDE.md` for instructions on how to add and manage videos.
