# Client Guide - Managing Your Videos

This guide will help you add, edit, and remove videos from your portfolio website.

## Quick Start

1. Open your Google Sheet: [Link to your sheet]
2. Add a new row with video information
3. Save (auto-saves)
4. Refresh your website to see the changes

## How to Upload Videos to Vimeo

### Step 1: Upload Your Video

1. Go to [Vimeo](https://vimeo.com) and login
2. Click the "Upload" button (top right)
3. Drag and drop your video file or click to browse
4. Wait for upload and processing to complete

### Step 2: Configure Video Settings

**Important:** Make sure your video visibility is set correctly:

1. After upload, click on your video
2. Click "Settings" → "Privacy"
3. Choose one of these options:
   - **"Public"** - Anyone can find and watch
   - **"Unlisted"** - Only people with the link can watch (recommended for client work)

   ⚠️ **DO NOT choose "Private"** - Private videos cannot be embedded on websites

4. Click "Save"

### Step 3: Get Video ID

1. Open your video on Vimeo
2. Look at the URL in your browser
3. The URL looks like: `https://vimeo.com/123456789`
4. The numbers at the end (`123456789`) are your Video ID
5. Copy this number

**Example:**

- URL: `https://vimeo.com/987654321`
- Video ID: `987654321`

## How to Add Videos to Your Website

### Step 1: Open Your Google Sheet

1. Click on your bookmarked Google Sheet link
2. You should see columns: `videoId`, `title`, `description`, `category`

### Step 2: Add a New Row

Click on the next empty row and fill in:

| Column          | What to Enter                                        | Example                           |
| --------------- | ---------------------------------------------------- | --------------------------------- |
| **videoId**     | The number from Vimeo URL                            | `987654321`                       |
| **title**       | Name of your video                                   | `Beautiful Summer Wedding`        |
| **description** | Brief description                                    | `John & Sarah's outdoor ceremony` |
| **category**    | Must be one of: `Weddings`, `Corporate`, or `Events` | `Weddings`                        |

**Important Rules:**

- ✅ **videoId**: Must be numbers only, no spaces
- ✅ **title**: Required - this appears on your website
- ✅ **description**: Optional but recommended
- ✅ **category**: Must be exactly `Weddings`, `Corporate`, or `Events` (capital first letter)

### Step 3: Save and Wait

1. The sheet auto-saves (you'll see "All changes saved" at the top)
2. Wait 2-3 seconds
3. Go to your website and refresh the page
4. Your new video should appear in the correct category!

## How to Edit Videos

1. Find the row with the video you want to edit
2. Click on the cell and change the information
3. The sheet auto-saves automatically
4. Refresh your website to see the changes

## How to Remove Videos

1. Find the row with the video you want to remove
2. Right-click on the row number (on the left side)
3. Click "Delete row"
4. Refresh your website

## How to Reorder Videos

Videos appear on your website in the same order as in the Google Sheet (top to bottom).

To change the order:

1. Click on the row number to select the entire row
2. Drag and drop to reorder
3. Refresh your website

## Category Filters

Your website has 3 category buttons:

- **Weddings** - For wedding videos
- **Corporate** - For business/corporate events
- **Events** - For other events (birthdays, parties, etc.)

Make sure each video has exactly one of these categories in the `category` column.

## Common Mistakes to Avoid

### ❌ Wrong Video Privacy Setting

**Problem:** Video doesn't play on website  
**Solution:** Go to Vimeo → Settings → Privacy → Set to "Public" or "Unlisted"

### ❌ Wrong Category Name

**Problem:** Video doesn't appear in any category  
**Solution:** Use exactly `Weddings`, `Corporate`, or `Events` (check spelling and capital letters)

### ❌ Missing Video ID

**Problem:** Row appears but video doesn't load  
**Solution:** Make sure the `videoId` column has the Vimeo video number

### ❌ Special Characters in Video ID

**Problem:** Video doesn't load  
**Solution:** Video ID should only contain numbers (e.g., `123456789`)

### ❌ Deleting Header Row

**Problem:** Website stops working  
**Solution:** Never delete the first row! It must always have: `videoId`, `title`, `description`, `category`

## Monitoring Your Vimeo Storage

You have 5GB of free storage on Vimeo. To check your usage:

1. Go to [Vimeo](https://vimeo.com)
2. Click on your profile picture (top right)
3. Go to "Settings" → "Billing"
4. You'll see your storage usage

**Tips to manage storage:**

- Each minute of HD video = approximately 150-200 MB
- 5GB = approximately 25-30 minutes of HD video
- Consider upgrading to Vimeo Plus ($7/month) for 250GB if you need more

## Website Caching

Your website caches video data for 1 hour to improve loading speed. This means:

- Changes may take up to 1 hour to appear for visitors who recently visited
- You can force refresh by pressing `Ctrl + F5` (Windows) or `Cmd + Shift + R` (Mac)
- First-time visitors will always see the latest data

## Troubleshooting

### Problem: I added a video but it doesn't appear

**Checklist:**

1. ✅ Is the `videoId` correct? (check the Vimeo URL)
2. ✅ Is the video set to "Public" or "Unlisted" on Vimeo? (not "Private")
3. ✅ Is the `category` spelled correctly? (`Weddings`, `Corporate`, or `Events`)
4. ✅ Did you save the sheet? (should say "All changes saved")
5. ✅ Did you refresh your website?
6. ✅ Try hard refresh: `Ctrl + F5` (Windows) or `Cmd + Shift + R` (Mac)

### Problem: Video thumbnail doesn't show

This is normal - if Vimeo's thumbnail doesn't load, your website will show a colored block with the video title instead. The video will still play when clicked.

### Problem: Video won't play when clicked

**Checklist:**

1. ✅ Check video privacy on Vimeo (must be "Public" or "Unlisted")
2. ✅ Verify the video ID is correct
3. ✅ Make sure the video is fully processed on Vimeo (may take a few minutes after upload)

### Problem: "Unable to load videos" error message

**Solution:**

1. Check your internet connection
2. Click the "Retry" button
3. If the problem persists, contact your developer

The website will show cached videos if it can't reach Google Sheets, so visitors can still see content even if there's a temporary issue.

## Support

If you encounter issues not covered in this guide, contact your web developer with:

1. A screenshot of the problem
2. Description of what you were trying to do
3. The video ID or row number in your sheet

## Quick Reference

### Valid Category Values

- `Weddings` ← capital W
- `Corporate` ← capital C
- `Events` ← capital E

### Sheet Column Order

1. `videoId` - Vimeo video number
2. `title` - Video name
3. `description` - Optional description
4. `category` - One of the three categories above

### Getting Vimeo Video ID

URL: `https://vimeo.com/123456789`  
Video ID: `123456789` ← These numbers

### Video Privacy Requirements

✅ Public or Unlisted  
❌ Private (won't work)

---

**Need the Google Sheet link?** Bookmark this: [Your Google Sheet URL]

**Need the website link?** Bookmark this: [Your Website URL]
