# 🖊️ DRAW THE FLOOR! — CrazyGames Submission Package

## 📦 Package contents
```
draw-the-floor/
├── index.html                          ← game (single file, no dependencies)
└── covers/
    ├── cover_landscape_1920x1080.png   ← mandatory 16:9
    ├── cover_portrait_800x1200.png     ← mandatory 2:3
    └── cover_square_800x800.png        ← mandatory 1:1
```

Total size: ~600 KB (limit: 250 MB ✅) | Files: 4 (limit: 1500 ✅) | Initial download: < 100 KB ✅

## 🎮 Game description (copy-paste for the submission form)

**Short description:**
> Draw the Floor! — A physics puzzle game where you draw floors with your mouse or finger. The ball never stops falling — guide it into the target before it drops!

**Full description:**
> In DRAW THE FLOOR!, gravity is always on and there is no floor anywhere! Hold and drag to draw blue floors in mid-air, and guide the falling ball into the green target to score. Every stroke uses limited ink, so plan your lines carefully. You have 3 lives — each time the ball falls off the bottom you lose one. Watch a rewarded video ad at game over to earn an extra life and keep going. Simple to learn, hard to master — how many targets can you hit?

**Controls:**
- 🖱️ Mouse / 👆 Touch: Hold & drag to draw floors
- ⌨️ R: Restart game
- ⏎ Enter: Start / play again

**Category:** Puzzle / Physics / Casual
**Tags:** physics, drawing, puzzle, ball, gravity, casual, one-button, hypercasual
**Language:** English
**PEGI:** 3+ (no violence, no inappropriate content)

## ⚙️ Technical notes for the submission form
- Single HTML5 file, no external assets, no build step
- CrazyGames SDK v3 integrated (script in `<head>`):
  - `gameplayStart()` / `gameplayStop()` on game start / game over / pause / resume
  - **Rewarded video ads (3 placements):** ① Menu — "Watch Ad · Start with +1 Life" (once per session) ② Game Over — "Watch Ad · +1 Life" (continue) ③ Game Over — "Watch Ad · 2x Score" (once per game over)
  - **Midgame ad** requested at game over (death screen) with a 3-minute manual cooldown backup
  - **Responsive banner** automatically shown on menu & game over screens, cleared during gameplay (best practice: banners only on menu/summary screens)
  - `muteAudio` setting fully respected (game uses WebAudio sound effects)
  - `happytime()` every 5 goals (level up) · `reportGameCompletedPercentage()` per goal · `setGameContext({score, level, combo})`
- Works with adblockers (game fully playable without ads; ad buttons hidden when SDK unavailable)
- No sitelock implemented
- No user data collection beyond SDK events (no privacy policy required)
- Mouse, touch and keyboard supported; mobile-friendly (responsive canvas, touch-action: none)

## 🚀 How to submit (step by step)
1. Go to **https://developer.crazygames.com/** → sign up (free) → verify your e-mail
2. Click **"Submit a game"**
3. Upload the `draw-the-floor` folder (or zip it) — entry file must be `index.html`
4. Upload the 3 cover images from `covers/`
5. Paste the description, controls, category and tags from above
6. Use the **Preview tool** to test your game as it will appear on CrazyGames
7. Submit for QA review

## 💰 How you earn money
- **Basic Launch** (first 7–21 days, need 500+ plays): game is live, no monetization yet
- If metrics (avg. playtime, conversion, retention) are good → **Full Launch**
- **Full Launch** = ads enabled → you get a **revenue share** from every ad view
- Payouts: see https://docs.crazygames.com/payouts/ (PayPal / wire, threshold applies)

## 📢 After publication (to reach 500 plays faster)
- Share on Reddit: r/gaming, r/webgames, r/IndieGaming, r/HyperCasualGames
- Post on Twitter/X, TikTok with a 15s gameplay clip
- Share in Discord game-dev servers
- ⚠️ Do NOT publish the same game on other portals before CrazyGames — it can disqualify you from revenue share

## 🔧 Local testing
The SDK shows demo ads on `localhost` / `127.0.0.1`. To test:
```
cd draw-the-floor
python -m http.server 8000        # or: npx serve
# open http://localhost:8000
```
(Opening index.html directly as a file:// also works — SDK is simply disabled there and the game runs without ads.)
