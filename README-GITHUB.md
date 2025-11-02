# Photo Gallery for GitHub Pages

## 🎉 Perfect for Your Setup!

This version is specifically designed for **GitHub Pages** - it automatically reads your photos directly from your GitHub repository using the GitHub API. No PHP, no Python scripts, just pure JavaScript!

## ✨ How It Works

Every time someone visits your page, it:
1. Calls the GitHub API to get the list of files in your `photos/` folder
2. Filters for image files (jpg, png, gif, webp)
3. Automatically generates the gallery layout
4. Creates the lightbox slideshow

**You just push photos to GitHub and they appear automatically!**

## 🚀 Setup (Super Easy)

1. **Replace your current `index.html`** with the new `index-github.html` (rename it to `index.html`)

2. **That's it!** Your photos are already in the repo, so it will just work.

## 📸 Adding New Photos

```bash
# Add photos to your repo
git add photos/new-photo-1.jpg photos/new-photo-2.jpg
git commit -m "Add new photos"
git push

# Wait a few seconds for GitHub Pages to update
# Visit your site - photos appear automatically! ✨
```

No scripts to run, no files to generate - just push and go!

## 🔧 Configuration

The configuration is at the top of the HTML file (around line 279):

```javascript
const GITHUB_USER = 'qiuyanliao';  // Your GitHub username
const GITHUB_REPO = 'qiuyanliao.github.io';  // Your repo name
const PHOTOS_PATH = 'photos';  // Folder where photos are stored
```

If you ever change your folder name or repo, just update these values.

## 📊 Sorting Options

Images are sorted **alphabetically by filename** by default. To change this, edit line 321:

```javascript
// Alphabetical (current)
.sort((a, b) => a.filename.localeCompare(b.filename));

// Reverse alphabetical
.sort((a, b) => b.filename.localeCompare(a.filename));

// You can also rename files to control order:
// 01-photo.jpg
// 02-photo.jpg
// 03-photo.jpg
```

## 🎨 Features

- ✅ **Fully automatic** - Reads directly from GitHub repo
- ✅ **No build step** - Pure client-side JavaScript
- ✅ **Smart masonry layout** - Adapts to any image size
- ✅ **Professional lightbox** - Click to zoom, navigate with arrows
- ✅ **Slideshow mode** - Auto-play through your photos
- ✅ **Keyboard navigation**:
  - `←` / `→` - Previous/Next photo
  - `Space` - Play/Pause slideshow
  - `ESC` - Close viewer
- ✅ **Mobile-friendly** - Responsive design
- ✅ **Fast loading** - Lazy-loaded images

## 🌐 GitHub API Rate Limits

The GitHub API allows 60 requests per hour for unauthenticated requests. Since your gallery only makes 1 request when the page loads, this is more than enough for a personal portfolio site.

If you have thousands of visitors per hour, you could add caching, but for a typical portfolio this is not necessary.

## 💡 Pro Tips

1. **Optimize your images** before uploading:
   - Max 2000px on longest side for web
   - Use JPEG for photos (smaller file size)
   - Use PNG for graphics with transparency
   
2. **File naming for order**:
   - Use numbers: `01-sunset.jpg`, `02-portrait.jpg`
   - Or dates: `2024-01-15-photo.jpg`
   
3. **Keep your repo clean**:
   - Delete old photos you don't want to display
   - The gallery only shows what's in the `photos/` folder

## 🐛 Troubleshooting

**Gallery shows "Loading gallery from GitHub" forever?**
- Check browser console for errors (F12)
- Verify your repo is public
- Check the GitHub username and repo name in the config

**Photos not appearing?**
- Make sure images are in the `photos/` folder
- Verify file extensions: .jpg, .jpeg, .png, .gif, .webp
- Check that files are committed and pushed to GitHub

**Images loading slowly?**
- Large image files take time to load
- Consider optimizing/compressing your images
- GitHub Pages has bandwidth limits for very high traffic

## 🎯 Compared to Your Old Version

**Before:**
```html
<figure>
  <a href="photos/work-01.jpg">
    <img src="photos/work-01.jpg" alt="...">
  </a>
</figure>
<!-- Repeat for each image... -->
<div class="break"></div>  <!-- Manual row breaks -->
```

**Now:**
- ✅ Just push images to GitHub
- ✅ Automatic layout (no manual breaks)
- ✅ Professional viewer with slideshow
- ✅ Much easier to maintain!

---

**Enjoy your automatic photo gallery! 🎉📸**
