# R.I.P-Kermit-the-ferg-v1-you-will-be-missed
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
  <title>I'm not a robot</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: linear-gradient(145deg, #1a1e2b 0%, #2a3142 100%);
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: 'Segoe UI', 'Inter', system-ui, -apple-system, sans-serif;
      padding: 1rem;
      margin: 0;
    }

    .game-container {
      background: rgba(18, 22, 32, 0.9);
      backdrop-filter: blur(20px);
      border-radius: 3rem;
      padding: 2rem 2rem 2.5rem;
      box-shadow: 0 30px 50px rgba(0, 0, 0, 0.7), inset 0 1px 0 rgba(255, 255, 255, 0.08);
      border: 1px solid rgba(255, 255, 255, 0.1);
      max-width: 580px;
      width: 100%;
      display: flex;
      flex-direction: column;
      align-items: center;
      transition: all 0.2s ease;
    }

    .chinatown-badge {
      font-size: 0.85rem;
      letter-spacing: 0.3rem;
      text-transform: uppercase;
      color: #ff6b6b;
      margin-bottom: 0.4rem;
      font-weight: 500;
      text-shadow: 0 0 8px #ff3b3b80;
      opacity: 0.9;
    }

    h2 {
      color: #f0e9d8;
      font-weight: 500;
      font-size: 1.6rem;
      letter-spacing: 2px;
      margin-bottom: 1rem;
      text-shadow: 0 2px 5px rgba(0,0,0,0.5);
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }
    h2 span {
      background: #3a4a6b;
      padding: 0.2rem 0.8rem;
      border-radius: 3rem;
      font-size: 1.2rem;
      color: #ffd966;
    }

    .level-indicator {
      display: flex;
      align-items: center;
      gap: 0.5rem;
      margin-bottom: 1.2rem;
      color: #ffcf9a;
      font-weight: 600;
    }
    .level-dots {
      display: flex;
      gap: 0.3rem;
    }
    .level-dot {
      width: 12px;
      height: 12px;
      border-radius: 50%;
      background: #3a4a6b;
      transition: 0.3s;
    }
    .level-dot.active {
      background: #ffb74d;
      box-shadow: 0 0 10px #ffa726;
    }
    .level-dot.completed {
      background: #2d6a4f;
    }

    .captcha-panel {
      background: #f5f0e7;
      border-radius: 2.2rem;
      padding: 1.8rem 1.5rem 1.5rem;
      width: 100%;
      box-shadow: inset 0 0 10px rgba(0,0,0,0.3), 0 15px 25px rgba(0, 0, 0, 0.6);
      border: 2px solid #b9a68c;
      background: #f9f3e9;
      margin-bottom: 1.5rem;
      transition: 0.3s;
    }

    .captcha-panel.hard-mode {
      border-color: #c78b5c;
      box-shadow: inset 0 0 20px rgba(180, 80, 20, 0.3), 0 15px 25px rgba(0, 0, 0, 0.7);
    }

    .captcha-panel.expert-mode {
      border-color: #b3541c;
      box-shadow: inset 0 0 25px rgba(200, 60, 10, 0.4), 0 15px 30px rgba(0, 0, 0, 0.8);
      animation: pulse-border 2s infinite;
    }

    @keyframes pulse-border {
      0%, 100% { border-color: #b3541c; }
      50% { border-color: #e8652a; }
    }

    .robot-check-row {
      display: flex;
      align-items: center;
      justify-content: space-between;
      background: white;
      border-radius: 1.8rem;
      padding: 0.7rem 1.3rem;
      box-shadow: 0 5px 12px rgba(0,0,0,0.2);
      border: 2px solid #cfc3b0;
      margin-bottom: 1.5rem;
      transition: all 0.2s;
    }

    .checkbox-area {
      display: flex;
      align-items: center;
      gap: 1rem;
    }

    .custom-checkbox {
      width: 38px;
      height: 38px;
      background: white;
      border: 3px solid #2c3e50;
      border-radius: 0.7rem;
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
      transition: all 0.2s ease;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }
    .custom-checkbox.checked {
      background: #2d6a4f;
      border-color: #1b4d3e;
      box-shadow: 0 0 15px #2d6a4faa;
    }
    .custom-checkbox svg {
      opacity: 0;
      transform: scale(0.5);
      transition: 0.15s ease;
    }
    .custom-checkbox.checked svg {
      opacity: 1;
      transform: scale(1);
    }

    .label-text {
      font-weight: 600;
      font-size: 1.2rem;
      color: #1e2b3c;
      letter-spacing: 0.3px;
    }

    .recaptcha-logo {
      display: flex;
      align-items: center;
      gap: 0.3rem;
      color: #4a4a4a;
      font-size: 0.8rem;
    }

    .challenge-instruction {
      color: #1f2a3a;
      font-weight: 600;
      margin-bottom: 0.7rem;
      font-size: 1.05rem;
      line-height: 1.4;
    }
    .challenge-instruction strong {
      color: #b3541c;
    }

    .timer-display {
      text-align: right;
      font-size: 0.85rem;
      color: #7c5c3e;
      margin-bottom: 0.3rem;
      font-weight: 600;
    }
    .timer-display.warning {
      color: #c0392b;
      animation: blink 0.5s infinite;
    }
    @keyframes blink {
      50% { opacity: 0.5; }
    }

    .challenge-grid {
      display: grid;
      gap: 0.8rem;
      margin: 1rem 0 1.5rem;
    }
    .challenge-grid.grid-3x3 {
      grid-template-columns: repeat(3, 1fr);
    }
    .challenge-grid.grid-4x4 {
      grid-template-columns: repeat(4, 1fr);
    }

    .grid-image {
      aspect-ratio: 1 / 1;
      border-radius: 0.8rem;
      cursor: pointer;
      border: 3px solid transparent;
      box-shadow: 0 4px 10px rgba(0,0,0,0.3);
      transition: 0.2s ease;
      position: relative;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 2.5rem;
      background-color: #d9cdb6;
    }
    .grid-4x4 .grid-image {
      font-size: 2rem;
      border-radius: 0.6rem;
    }

    .grid-image.selected {
      border: 4px solid #ffb74d;
      box-shadow: 0 0 18px #ffa726;
      transform: scale(0.95);
    }

    .grid-image::after {
      content: "✓";
      position: absolute;
      top: 3px;
      right: 6px;
      font-size: 1.3rem;
      font-weight: bold;
      color: #ffb703;
      text-shadow: 0 0 6px black;
      display: none;
    }
    .grid-4x4 .grid-image::after {
      font-size: 1rem;
      top: 2px;
      right: 4px;
    }
    .grid-image.selected::after {
      display: block;
    }

    .traffic-light-cell {
      background: linear-gradient(135deg, #2c3e50 0%, #34495e 100%);
    }
    .non-traffic-cell {
      background: linear-gradient(135deg, #e8d5b7 0%, #d4a574 100%);
    }

    .action-buttons {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 0.8rem;
      margin-top: 0.5rem;
      flex-wrap: wrap;
    }

    .btn {
      background: #4a627a;
      border: none;
      padding: 0.6rem 1.2rem;
      border-radius: 2.5rem;
      font-weight: 600;
      letter-spacing: 0.5px;
      color: #f0e6d3;
      background: #2e4057;
      cursor: pointer;
      transition: 0.2s;
      box-shadow: 0 4px 0 #1a2533;
      border: 1px solid #6d7f94;
      font-size: 0.9rem;
      display: flex;
      align-items: center;
      gap: 0.3rem;
    }

    .btn:hover {
      background: #3b5068;
      transform: translateY(-2px);
      box-shadow: 0 6px 0 #1a2533;
    }
    .btn:active {
      transform: translateY(2px);
      box-shadow: 0 2px 0 #1a2533;
    }
    .btn:disabled {
      opacity: 0.4;
      cursor: not-allowed;
      transform: none;
    }

    .btn.primary {
      background: #d4a373;
      border-color: #f3d5b5;
      color: #2d1f0c;
      font-weight: bold;
      box-shadow: 0 4px 0 #936639;
    }

    .message-box {
      margin-top: 1rem;
      background: #1e2638;
      padding: 0.7rem 1.2rem;
      border-radius: 2rem;
      color: #ffcf9a;
      font-weight: 500;
      text-align: center;
      min-height: 3rem;
      display: flex;
      align-items: center;
      justify-content: center;
      border: 1px solid #ffb74d40;
      font-size: 0.9rem;
    }

    .hidden {
      display: none !important;
    }

    .footer-note {
      color: #8f9bb0;
      margin-top: 0.8rem;
      font-size: 0.75rem;
      opacity: 0.8;
    }

    @media (max-width: 450px) {
      .game-container {
        padding: 1.5rem 1rem;
      }
      .grid-image {
        font-size: 2rem;
        border-radius: 0.6rem;
      }
      .grid-4x4 .grid-image {
        font-size: 1.5rem;
      }
    }
  </style>
</head>
<body>
<div class="game-container">
  <div class="chinatown-badge">chinatown</div>
  <h2>I'M NOT A ROBOT <span>🔐</span></h2>
  
  <div class="level-indicator">
    <span>Level:</span>
    <div class="level-dots" id="levelDots">
      <div class="level-dot active"></div>
      <div class="level-dot"></div>
      <div class="level-dot"></div>
      <div class="level-dot"></div>
      <div class="level-dot"></div>
    </div>
  </div>

  <div class="captcha-panel" id="captchaPanel">
    <div class="robot-check-row" id="initialCheckRow">
      <div class="checkbox-area">
        <div class="custom-checkbox" id="mainCheckbox">
          <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="4">
            <polyline points="4 12 10 18 20 6"></polyline>
          </svg>
        </div>
        <span class="label-text">I'm not a robot</span>
      </div>
      <div class="recaptcha-logo">
        <span style="font-weight:bold; color:#2c5282;">reCAPTCHA</span>
      </div>
    </div>

    <div id="challengeSection" class="hidden">
      <div class="challenge-instruction" id="challengeInstruction">
        Select all images with <strong>traffic lights</strong>
      </div>
      <div class="timer-display" id="timerDisplay"></div>
      <div class="challenge-grid grid-3x3" id="imageGrid"></div>
      <div class="action-buttons">
        <button class="btn" id="skipBtn">↻ Skip</button>
        <span style="font-size:0.8rem;color:#7c5c3e;" id="attemptsLeft"></span>
        <button class="btn primary" id="verifyBtn">✅ VERIFY</button>
      </div>
    </div>
  </div>

  <div class="message-box" id="messageDisplay">
    Prove you're human
  </div>
  <div class="footer-note">level 1/5 · select all traffic lights to proceed</div>
</div>

<script>
  (function() {
    // ----- Level definitions -----
    const levels = [
      {
        name: "Easy",
        gridSize: 3,        // 3x3 = 9 cells
        targetCount: { min: 2, max: 3 },
        timeLimit: 0,       // no timer
        maxAttempts: 999,
        description: "Select traffic lights"
      },
      {
        name: "Medium",
        gridSize: 3,
        targetCount: { min: 3, max: 4 },
        timeLimit: 15,
        maxAttempts: 3,
        description: "Select traffic lights"
      },
      {
        name: "Hard",
        gridSize: 4,        // 4x4 = 16 cells
        targetCount: { min: 4, max: 6 },
        timeLimit: 20,
        maxAttempts: 3,
        description: "Select traffic lights"
      },
      {
        name: "Expert",
        gridSize: 4,
        targetCount: { min: 5, max: 7 },
        timeLimit: 15,
        maxAttempts: 2,
        description: "Select traffic lights"
      },
      {
        name: "Impossible",
        gridSize: 4,
        targetCount: { min: 6, max: 8 },
        timeLimit: 10,
        maxAttempts: 2,
        description: "Select traffic lights"
      }
    ];

    // ----- Emoji pools -----
    const trafficEmojis = ["🚦", "🚥"];
    const nonTrafficEmojis = ["🌳", "🚗", "🐕", "🚲", "🏠", "☕", "⭐", "🌸", "📱", "🎵", "🍕", "⚽", "📚", "🎸", "🌙", "🍎"];

    // ----- Game state -----
    let currentLevel = 1;           // 1-5
    let currentImages = [];
    let selectedIndices = new Set();
    let challengeActive = false;
    let verificationSuccess = false;
    let gameCompleted = false;
    let attemptsRemaining = 999;
    let timerInterval = null;
    let timeRemaining = 0;
    let levelPassed = [false, false, false, false, false]; // track which levels passed

    // ----- DOM elements -----
    const mainCheckbox = document.getElementById('mainCheckbox');
    const challengeSection = document.getElementById('challengeSection');
    const imageGrid = document.getElementById('imageGrid');
    const skipBtn = document.getElementById('skipBtn');
    const verifyBtn = document.getElementById('verifyBtn');
    const messageDisplay = document.getElementById('messageDisplay');
    const timerDisplay = document.getElementById('timerDisplay');
    const attemptsLeftSpan = document.getElementById('attemptsLeft');
    const challengeInstruction = document.getElementById('challengeInstruction');
    const captchaPanel = document.getElementById('captchaPanel');
    const levelDots = document.getElementById('levelDots').children;
    const footerNote = document.querySelector('.footer-note');

    // ----- Helpers -----
    const shuffleArray = (arr) => {
      for (let i = arr.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [arr[i], arr[j]] = [arr[j], arr[i]];
      }
      return arr;
    };

    function createImagePool(targetCount) {
      const pool = [];
      // Traffic lights
      for (let i = 0; i < targetCount; i++) {
        pool.push({
          emoji: trafficEmojis[i % 2],
          isTarget: true,
          bgClass: 'traffic-light-cell'
        });
      }
      // Non-traffic
      const shuffledNonTraffic = shuffleArray([...nonTrafficEmojis]);
      const totalCells = levels[currentLevel - 1].gridSize ** 2;
      const nonTargetCount = totalCells - targetCount;
      for (let i = 0; i < nonTargetCount; i++) {
        pool.push({
          emoji: shuffledNonTraffic[i % shuffledNonTraffic.length],
          isTarget: false,
          bgClass: 'non-traffic-cell'
        });
      }
      return shuffleArray(pool);
    }

    function generateChallengeImages() {
      const level = levels[currentLevel - 1];
      const targetCount = Math.floor(Math.random() * (level.targetCount.max - level.targetCount.min + 1)) + level.targetCount.min;
      return createImagePool(targetCount);
    }

    function updateLevelDisplay() {
      // Update dots
      for (let i = 0; i < 5; i++) {
        levelDots[i].classList.remove('active', 'completed');
        if (levelPassed[i]) {
          levelDots[i].classList.add('completed');
        } else if (i + 1 === currentLevel && !gameCompleted) {
          levelDots[i].classList.add('active');
        }
      }
      
      // Update panel style
      captchaPanel.classList.remove('hard-mode', 'expert-mode');
      if (currentLevel === 3 || currentLevel === 4) captchaPanel.classList.add('hard-mode');
      if (currentLevel === 5) captchaPanel.classList.add('expert-mode');
      
      // Update grid class
      const level = levels[currentLevel - 1];
      imageGrid.className = 'challenge-grid';
      if (level.gridSize === 3) imageGrid.classList.add('grid-3x3');
      else imageGrid.classList.add('grid-4x4');
      
      // Update footer
      footerNote.textContent = `level ${currentLevel}/5 · ${level.name} · ${level.description}`;
    }

    function renderGrid() {
      imageGrid.innerHTML = '';
      currentImages.forEach((img, idx) => {
        const div = document.createElement('div');
        div.className = `grid-image ${img.bgClass}`;
        div.textContent = img.emoji;
        div.dataset.index = idx;
        div.dataset.target = img.isTarget;
        
        if (selectedIndices.has(idx)) {
          div.classList.add('selected');
        }
        
        div.addEventListener('click', (e) => {
          if (!challengeActive) return;
          const index = parseInt(e.currentTarget.dataset.index, 10);
          toggleSelection(index);
        });
        
        imageGrid.appendChild(div);
      });
    }

    function toggleSelection(index) {
      if (selectedIndices.has(index)) {
        selectedIndices.delete(index);
      } else {
        selectedIndices.add(index);
      }
      const gridItems = document.querySelectorAll('.grid-image');
      if (gridItems[index]) {
        gridItems[index].classList.toggle('selected');
      }
    }

    function stopTimer() {
      if (timerInterval) {
        clearInterval(timerInterval);
        timerInterval = null;
      }
      timerDisplay.textContent = '';
      timerDisplay.classList.remove('warning');
    }

    function startTimer() {
      const level = levels[currentLevel - 1];
      if (level.timeLimit === 0) {
        timerDisplay.textContent = '';
        return;
      }
      
      timeRemaining = level.timeLimit;
      timerDisplay.textContent = `⏱ ${timeRemaining}s`;
      timerDisplay.classList.remove('warning');
      
      stopTimer();
      timerInterval = setInterval(() => {
        timeRemaining--;
        timerDisplay.textContent = `⏱ ${timeRemaining}s`;
        
        if (timeRemaining <= 5) {
          timerDisplay.classList.add('warning');
        }
        
        if (timeRemaining <= 0) {
          stopTimer();
          handleTimeout();
        }
      }, 1000);
    }

    function handleTimeout() {
      messageDisplay.textContent = '⏰ Time\'s up! Challenge failed.';
      attemptsRemaining--;
      updateAttemptsDisplay();
      
      if (attemptsRemaining <= 0) {
        failLevel();
      } else {
        resetChallenge();
      }
    }

    function updateAttemptsDisplay() {
      const level = levels[currentLevel - 1];
      if (level.maxAttempts < 999) {
        attemptsLeftSpan.textContent = `Attempts: ${attemptsRemaining}/${level.maxAttempts}`;
      } else {
        attemptsLeftSpan.textContent = '';
      }
    }

    function resetChallenge() {
      selectedIndices.clear();
      currentImages = generateChallengeImages();
      renderGrid();
      challengeActive = true;
      stopTimer();
      startTimer();
    }

    function resetAndShowChallenge() {
      const level = levels[currentLevel - 1];
      attemptsRemaining = level.maxAttempts;
      updateAttemptsDisplay();
      
      selectedIndices.clear();
      currentImages = generateChallengeImages();
      renderGrid();
      challengeActive = true;
      challengeSection.classList.remove('hidden');
      challengeInstruction.innerHTML = `Select all images with <strong>traffic lights</strong>`;
      
      stopTimer();
      startTimer();
      
      messageDisplay.textContent = `🔍 Level ${currentLevel}: ${level.name} - Select traffic lights!`;
    }

    function hideChallenge() {
      challengeSection.classList.add('hidden');
      challengeActive = false;
      selectedIndices.clear();
      stopTimer();
    }

    function levelUp() {
      levelPassed[currentLevel - 1] = true;
      
      if (currentLevel >= 5) {
        // Game complete!
        gameCompleted = true;
        challengeActive = false;
        challengeSection.classList.add('hidden');
        mainCheckbox.classList.add('checked');
        stopTimer();
        messageDisplay.innerHTML = '🏆 <strong>ALL LEVELS COMPLETE!</strong> You are definitely human! 🎉';
        footerNote.textContent = 'game complete · social credit: MAXIMUM';
        updateLevelDisplay();
        return;
      }
      
      currentLevel++;
      hideChallenge();
      mainCheckbox.classList.remove('checked');
      verificationSuccess = false;
      updateLevelDisplay();
      messageDisplay.innerHTML = `✅ <strong>Level ${currentLevel - 1} passed!</strong> Level ${currentLevel}: ${levels[currentLevel - 1].name} unlocked!`;
      footerNote.textContent = `level ${currentLevel}/5 · click checkbox to continue`;
    }

    function failLevel() {
      challengeActive = false;
      challengeSection.classList.add('hidden');
      mainCheckbox.classList.remove('checked');
      stopTimer();
      messageDisplay.innerHTML = `❌ <strong>Level ${currentLevel} failed!</strong> Restarting level...`;# Workflow that automatically deploys the website to GitHub Pages
name: Deploy GitHub Pages

# Trigger conditions: runs on push to main branch or manual trigger
on:
  push:
    branches: ["main"]  # Automatically deploy when code is pushed to main
  workflow_dispatch:    # Allow manual trigger from GitHub UI

# Grant necessary permissions for the workflow
permissions:
  contents: read      # Read access to repository contents
  pages: write        # Permission to write/deploy to GitHub Pages
  id-token: write     # Generate OIDC token for secure authentication

# Prevent multiple deployments running simultaneously
concurrency:
  group: "pages"              # Group all pages deployments together
  cancel-in-progress: true    # Cancel any in-progress deployments when new one starts
:fish:
Click to react
:thinking:
Click to react
:flag_aq:
Click to react
Add Reaction
Reply
Forward
More
[10:34 AM]Saturday, June 13, 2026 10:34 AM
# Define deployment job
jobs:
  deploy:
    # Use GitHub Pages environment for deployment tracking
    environment:
      name: github-pages                                    # Environment name
      url: ${{ steps.deployment.outputs.page_url }}         # Output the deployed site URL

    # Run on the latest Ubuntu runner
    runs-on: ubuntu-latest

    # Steps to execute the deployment
    steps:
      # Step 1: Download the repository code
      - name: Get code
        uses: actions/checkout@v5

      # Step 2: Configure GitHub Pages settings for the repository
      - name: Setup Pages
        uses: actions/configure-pages@v6

      # Step 3: Package the website files for deployment (entire repo folder)
      - name: Upload website
        uses: actions/upload-pages-artifact@v5
        with:
          path: "."  # Upload all files from root directory

      # Step 4: Deploy the packaged website to GitHub Pages
      - name: Deploy website
        id: deployment              # Save output for later use
        uses: actions/deploy-pages@v5
:fish:
Click to react
:thinking:
Click to react
:flag_aq:
Click to react
Add Reaction
Reply
Forward
More
[10:35 AM]Saturday, June 13, 2026 10:35 AM
      
      // Reset current level progress
      setTimeout(() => {
        hideChallenge();
        verificationSuccess = false;
        messageDisplay.textContent = `🔄 Level ${currentLevel} restarted. Prove you're human.`;
      }, 1500);
    }

    function performVerification() {
      if (!challengeActive) {
        messageDisplay.textContent = '⏳ No active challenge. Click checkbox.';
        return;
      }

      const targetIndices = new Set();
      currentImages.forEach((img, idx) => {
        if (img.isTarget) targetIndices.add(idx);
      });

      // Check if all targets selected and no extras
      let correct = selectedIndices.size === targetIndices.size;
      if (correct) {
        for (let sel of selectedIndices) {
          if (!targetIndices.has(sel)) {
            correct = false;
            break;
          }
        }
      }

      if (correct) {
        // SUCCESS!
        stopTimer();
        verificationSuccess = true;
        challengeActive = false;
        challengeSection.classList.add('hidden');
        mainCheckbox.classList.add('checked');
        messageDisplay.innerHTML = `✅ <strong>Correct!</strong> Level ${currentLevel} complete!`;
        setTimeout(() => levelUp(), 1000);
      } else {
        // FAIL
        attemptsRemaining--;
        updateAttemptsDisplay();
        
        if (attemptsRemaining <= 0) {
          stopTimer();
          messageDisplay.textContent = '❌ No attempts remaining!';
          setTimeout(() => failLevel(), 800);
        } else {
          messageDisplay.textContent = `❌ Incorrect! ${attemptsRemaining} attempts left. Try again.`;
          selectedIndices.clear();
          renderGrid();
          // Flash effect
          imageGrid.style.opacity = '0.6';
          setTimeout(() => { imageGrid.style.opacity = '1'; }, 150);
        }
      }
    }

    function skipChallenge() {
      if (!challengeActive) {
        resetAndShowChallenge();
        return;
      }
      stopTimer();
      resetChallenge();
      messageDisplay.textContent = '🔄 New challenge. Select traffic lights.';
    }

    function onMainCheckboxClick() {
      if (gameCompleted) {
        messageDisplay.textContent = '🏆 Game complete! You\'re verified forever. (double-click to reset)';
        return;
      }
      
      if (verificationSuccess && levelPassed[currentLevel - 1]) {
        messageDisplay.textContent = '🎯 Level passed! Double-click to replay.';
        return;
      }
      
      if (challengeActive) {
        hideChallenge();
        messageDisplay.textContent = '⏸️ Challenge dismissed. Click checkbox to try.';
        mainCheckbox.classList.remove('checked');
        return;
      }
      
      resetAndShowChallenge();
      mainCheckbox.classList.add('checked');
    }

    // Double-click to fully reset game
    mainCheckbox.addEventListener('dblclick', function(e) {
      stopTimer();
      gameCompleted = false;
      verificationSuccess = false;
      currentLevel = 1;
      levelPassed = [false, false, false, false, false];
      hideChallenge();
      mainCheckbox.classList.remove('checked');
      updateLevelDisplay();
      messageDisplay.textContent = '🔄 Full reset. Prove you are human from level 1.';
      footerNote.textContent = 'level 1/5 · select all traffic lights to proceed';
    });

    mainCheckbox.addEventListener('click', onMainCheckboxClick);
    verifyBtn.addEventListener('click', performVerification);
    skipBtn.addEventListener('click', skipChallenge);

    // Initialize
    updateLevelDisplay();
    messageDisplay.textContent = '👆 Click checkbox to start level 1';
    updateAttemptsDisplay();

    console.log('"I\'m not a robot" multi-level ready. Social credit protected.');
  })();
</script>
</body>
</html>
