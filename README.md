# Neon Dodger

A fast-paced, neon-themed dodging game built with HTML5 Canvas and JavaScript. Dodge falling blocks as the difficulty increases over time. Integrated with Farcade SDK for cross-platform compatibility.

![Game Screenshot](https://via.placeholder.com/320x480/020617/22c55e?text=Neon+Dodger) <!-- Replace with actual screenshot -->

## 🚀 How to Play

- Move your glowing orb left and right to avoid the falling blocks.
- Survive as long as possible to achieve the highest score.
- Difficulty ramps up every 15 seconds with faster blocks and shorter spawn intervals.

## 🎮 Controls

- **Desktop**: Arrow keys (← →) or A/D keys
- **Mobile**: Tap the on-screen left (⇦) and right (⇨) buttons

## ✨ Features

- Responsive design for desktop and mobile
- Smooth animations and neon glow effects
- Background music and sound effects
- Local high score persistence
- Farcade SDK integration for Remix/Farcade platforms
- Haptic feedback on supported devices
- Progressive difficulty scaling

## 🛠 Technologies Used

- **HTML5 Canvas** for rendering
- **JavaScript (ES6+)** for game logic
- **CSS3** for styling and animations
- **Web Audio API** for sound management
- **Farcade Game SDK** for platform integration

## 🔗 SDK Integration

This game is hooked for Farcade / Mini App / Remix platforms using the Farcade SDK:

- Initializes with `remixSdk.singlePlayer.actions.ready()`
- Reports game over scores with `remixSdk.singlePlayer.actions.gameOver()`
- Handles haptic feedback on game over
- Listens for `play_again` and `toggle_mute` events

## 🏃‍♂️ Running Locally

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/neon-dodger.git
   cd neon-dodger
   ```

2. Open `Neon Dodger.html` in your web browser.

No build process required—it's a pure client-side game!

## 🚀 Deployment

The game is a single HTML file, making it easy to deploy anywhere that serves static files:

- **GitHub Pages**: Enable Pages in repository settings, point to root.
- **Netlify/Vercel**: Drag and drop the HTML file or connect the repo.
- **Farcade/Remix**: Upload or integrate via their platforms.

## 🤖 GitHub Workflows

This repository includes GitHub Actions for automated deployment:

### Deploy to GitHub Pages

```yaml
# .github/workflows/deploy.yml
name: Deploy to GitHub Pages

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  build-and-deploy:
    runs-on: ubuntu-latest
    steps:
    - name: Checkout
      uses: actions/checkout@v4

    - name: Setup Node.js
      uses: actions/setup-node@v4
      with:
        node-version: '18'

    - name: Install dependencies (if any)
      run: npm install  # Add if you add build tools later

    - name: Build (if needed)
      run: npm run build  # Add if you add build tools later

    - name: Deploy to GitHub Pages
      uses: peaceiris/actions-gh-pages@v3
      if: github.ref == 'refs/heads/main'
      with:
        github_token: ${{ secrets.GITHUB_TOKEN }}
        publish_dir: .  # Since it's a single file, deploy from root
```

### CI/CD for Code Quality

```yaml
# .github/workflows/ci.yml
name: CI

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  lint:
    runs-on: ubuntu-latest
    steps:
    - name: Checkout
      uses: actions/checkout@v4

    - name: Setup Node.js
      uses: actions/setup-node@v4
      with:
        node-version: '18'

    - name: Install ESLint
      run: npm install -g eslint

    - name: Run ESLint
      run: eslint Neon\ Dodger.html  # Or extract JS to separate files for better linting
```

## 📝 Development

- Edit `Neon Dodger.html` for changes
- Test in browser with developer tools
- For advanced features, consider extracting JS/CSS to separate files

## 🎵 Audio Credits

- Background Music: [Source]
- Start Sound: [Source]
- Hit Sound: [Source]

Replace with actual credits or remove if not applicable.

## 📄 License

MIT License - feel free to use and modify!

## 🤝 Contributing

Fork, make changes, submit PR. For major changes, open an issue first.

---

Made with ❤️ for the web gaming community.