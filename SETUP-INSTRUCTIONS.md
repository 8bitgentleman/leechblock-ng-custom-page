# Custom LeechBlock Delay Page - Setup Instructions

## Overview
This custom delay page replaces LeechBlock's default delay screen with a modern, beautiful interface featuring:
- Smooth animations and transitions
- Gradient background with floating elements
- Large countdown timer with progress bar
- **Theme customization via URL parameters** (6 built-in themes!)
- **Custom messages and icons via URL parameters**
- Clean, minimalist design inspired by modern productivity apps
- Mobile-responsive layout

## 🎨 Built-in Themes

- **purple** (default) - Purple gradient
- **ocean** - Blue ocean gradient
- **sunset** - Orange/red sunset
- **forest** - Green forest gradient
- **dark** - Dark gray/black
- **rose** - Pink/purple rose
- **mint** - Teal/green mint

## 📋 Requirements

**Important:** Your file URL must include `lb-custom` in the path for LeechBlock to inject its countdown script!

✅ Good: `https://example.com/lb-custom-delayed.html`
✅ Good: `https://example.com/pages/lb-custom.html`
❌ Bad: `https://example.com/delayed.html` (no "lb-custom" in URL)

## Setup Instructions

### Step 1: Host the HTML File Online

**Option A: GitHub Pages (Recommended)**

1. Create a new GitHub repository
2. Upload `leechblock-custom-delayed.html` (keep the filename or rename to include "lb-custom")
3. Go to repository Settings → Pages
4. Enable GitHub Pages from main branch
5. Your URL will be: `https://yourusername.github.io/repo-name/leechblock-custom-delayed.html`

**Option B: Other Free Hosts**
- Netlify Drop (drag & drop deployment)
- Cloudflare Pages
- Vercel
- Any static file hosting

**Important:** Make sure the filename or path contains `lb-custom`!

### Step 2: Configure LeechBlock

1. Open Firefox → Menu → Add-ons → LeechBlock NG → Settings
2. Go to **Block Set 1** tab
3. Scroll to **"How to Block"** section
4. Find: **"Enter the fully specified URL of the page to show instead of these blocked sites:"**
5. Enter your URL with parameters:

**Basic URL (purple theme, default message):**
```
https://YOUR-HOSTED-URL.com/leechblock-custom-delayed.html?$S&$U
```

**With custom theme:**
```
https://YOUR-HOSTED-URL.com/leechblock-custom-delayed.html?theme=ocean&$S&$U
```

**With custom theme + message:**
```
https://YOUR-HOSTED-URL.com/leechblock-custom-delayed.html?theme=sunset&message=Get%20back%20to%20work!&$S&$U
```

**With theme + message + icon:**
```
https://YOUR-HOSTED-URL.com/leechblock-custom-delayed.html?theme=forest&message=Focus%20time!&icon=🎯&$S&$U
```

**⚠️ CRITICAL:** Always end with `?` followed by your parameters, then `&$S&$U` at the very end!

6. Click **"Save Options"**
7. Close and reopen Firefox
8. Try visiting a blocked site!

### Step 3: Test It

Visit x.com (or your blocked site) and you should see your beautiful custom delay page!

## 🎨 Customization Examples

### Example 1: Ocean theme with motivational message
```
?theme=ocean&message=Is%20this%20really%20important?&$S&$U
```

### Example 2: Dark theme with target icon
```
?theme=dark&icon=🎯&message=Stay%20focused!&$S&$U
```

### Example 3: Sunset theme with meditation icon
```
?theme=sunset&icon=🧘&message=Breathe%20and%20refocus&$S&$U
```

### Example 4: Multiple block sets with different themes

**Block Set 1** (Social Media - Purple):
```
https://your-url.com/leechblock-custom-delayed.html?theme=purple&message=Social%20media%20break?&icon=📱&$S&$U
```

**Block Set 2** (News Sites - Ocean):
```
https://your-url.com/leechblock-custom-delayed.html?theme=ocean&message=News%20can%20wait&icon=📰&$S&$U
```

**Block Set 3** (YouTube - Rose):
```
https://your-url.com/leechblock-custom-delayed.html?theme=rose&message=Time%20for%20videos?&icon=🎬&$S&$U
```

## 📝 URL Parameter Reference

| Parameter | Purpose | Example Values |
|-----------|---------|----------------|
| `theme` | Change color scheme | `ocean`, `sunset`, `forest`, `dark`, `rose`, `mint`, `purple` |
| `message` | Custom message | `Focus%20time!`, `Is%20this%20important?` |
| `icon` | Custom emoji icon | `🎯`, `🧘`, `⏰`, `🌟`, `💎`, `🔥` |

**Note:** Use `%20` for spaces in URL parameters (URL encoding)

## 🛠️ Advanced: Creating Your Own Theme

If you want colors beyond the 6 built-in themes, you can edit the HTML file:

1. Open `leechblock-custom-delayed.html` in a text editor
2. Find the `:root` section (around line 8)
3. Add a new theme:

```css
[data-theme="mytheme"] {
    --gradient-start: #your-color-1;
    --gradient-end: #your-color-2;
}
```

4. Use it: `?theme=mytheme&$S&$U`

### Popular Color Combinations

**Lavender:**
```css
[data-theme="lavender"] {
    --gradient-start: #A18CD1;
    --gradient-end: #FBC2EB;
}
```

**Fire:**
```css
[data-theme="fire"] {
    --gradient-start: #ff0844;
    --gradient-end: #ffb199;
}
```

**Northern Lights:**
```css
[data-theme="aurora"] {
    --gradient-start: #00c6ff;
    --gradient-end: #0072ff;
}
```

## ⚠️ Troubleshooting

### Problem: Custom page doesn't show, I get the default LeechBlock page

**Solution:** Make sure your URL contains `lb-custom` somewhere in the path!
- ✅ `leechblock-custom-delayed.html`
- ✅ `lb-custom.html`
- ✅ `pages/lb-custom-delay.html`
- ❌ `delay.html` (missing lb-custom)

### Problem: Countdown stays at 0 or doesn't count down

**Solution:** LeechBlock injects its script into pages with `lb-custom` in the URL. Check:
1. URL contains `lb-custom`
2. URL ends with `?[params]&$S&$U`
3. LeechBlock "Delaying Page" option is selected in Block Set settings

### Problem: Theme or custom message doesn't appear

**Solution:** 
1. Check URL parameter syntax: `?theme=ocean&message=Hello&$S&$U`
2. Make sure spaces in messages use `%20`: `Get%20back%20to%20work!`
3. Parameters come BEFORE the `&$S&$U` at the end

### Problem: Page works on desktop but not Android

**Solution:** This is expected and works fine on Android Firefox! No special config needed.

## 🎯 Complete Example

Here's a complete URL you might use:

```
https://myusername.github.io/leechblock/leechblock-custom-delayed.html?theme=ocean&message=Is%20this%20really%20important?&icon=🎯&$S&$U
```

This creates an ocean-themed page with the message "Is this really important?" and a target emoji 🎯.

## 💡 Pro Tips

1. **Different themes for different sites:** Use different Block Sets with different theme parameters
2. **Motivational messages:** Change the message parameter to keep it fresh
3. **Icon variety:** Switch between 🧘 (zen), ⏰ (time), 🎯 (focus), 🌟 (star), 💎 (diamond)
4. **Test locally first:** Open the HTML file in your browser to test themes before uploading

## 📱 Mobile Users

Everything works perfectly on Firefox Android! The page is fully responsive and looks great on phone screens.

## Need Help?

If you run into issues or want more customization, let me know!
