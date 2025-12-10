# RevealJS Slideshow - ALHF in Azure AI Foundry

This folder contains a RevealJS-based slideshow presentation about Human-Feedback Driven Agent Improvement (ALHF-style) in Azure AI Foundry.

## 📋 Contents

- `index.html` - Main presentation file
- `README.md` - This file

## 🚀 How to Run

### Option 1: Open Directly in Browser
Simply open `index.html` in any modern web browser. All dependencies are loaded from CDN.

### Option 2: Run with Local Server (Recommended)

#### Using Python:
```powershell
# Python 3
python -m http.server 8000

# Then open: http://localhost:8000
```

#### Using Node.js (http-server):
```powershell
npx http-server -p 8000

# Then open: http://localhost:8000
```

#### Using VS Code Live Server:
1. Install the "Live Server" extension
2. Right-click on `index.html`
3. Select "Open with Live Server"

## 🎮 Keyboard Controls

- **→ / ←** - Navigate slides
- **Space** - Next slide
- **Esc** - Slide overview
- **F** - Fullscreen mode
- **S** - Speaker notes view
- **B** or **.** - Pause (black screen)

## 🎨 Features

- **17+ slides** covering the complete ALHF implementation in Azure
- **Responsive design** - works on desktop, tablet, and mobile
- **Custom Azure theme** - branded colors (#0078d4, #50e6ff)
- **Visual diagrams** - ASCII art flow diagrams
- **Highlight boxes** - emphasized content sections
- **Two-column layouts** - for comparison content
- **Smooth transitions** - professional slide animations

## 📚 Slide Topics

1. Title & Introduction
2. Why This Matters
3. Conceptual Architecture
4. Foundry Components
5. Step 1: Build & Instrument Agent
6. Step 2: Capture Human Feedback
7. Step 3: Add Automated/Synthetic Evaluation
8. Step 4: Build Unified Feedback Dataset
9. Step 5: Apply Improvements
10. Step 6: Continuous Evaluation
11. Multi-Agent Extension
12. Recommended Operating Model
13. Deliverables for Production
14. Example Visual Diagram
15. Summary
16. Next Steps
17. Azure ML Studio Integration (4 sub-slides)

## 🔧 Customization

### Change Theme
Replace the theme link in `index.html`:
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/reveal.js@5.0.4/dist/theme/[THEME_NAME].css">
```

Available themes: `black`, `white`, `league`, `beige`, `sky`, `night`, `serif`, `simple`, `solarized`, `moon`

### Modify Colors
Edit the custom styles in the `<style>` section of `index.html`:
```css
.reveal h1 { color: #0078d4; }  /* Azure blue */
.reveal h2 { color: #50e6ff; }  /* Azure cyan */
```

### Add Speaker Notes
Add notes to any slide:
```html
<section>
    <h2>Slide Title</h2>
    <p>Slide content</p>
    <aside class="notes">
        These are speaker notes that appear when you press 'S'
    </aside>
</section>
```

## 📦 Dependencies (CDN)

All dependencies are loaded from CDN, no installation required:
- RevealJS 5.0.4
- RevealJS Plugins (Notes, Markdown, Highlight)
- Monokai syntax highlighting theme

## 🌐 Browser Support

Works on all modern browsers:
- Chrome/Edge (recommended)
- Firefox
- Safari
- Opera

## 📄 Source

This presentation is based on: `alhf-databricks-foundry-ml-slides.md`

Author: Johnny Harbieh, Principal Solution Engineer

---

**Date Created:** December 10, 2025
