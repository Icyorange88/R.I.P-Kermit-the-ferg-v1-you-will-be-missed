# R.I.P-Kermit-the-ferg-v1-you-will-be-missed
touch index.html
# Then paste the HTML code into the file
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
  <title>chinatown · I'm not a robot</title>
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
      padding: 2.2rem 2rem 2.5rem;
      box-shadow: 0 30px 50px rgba(0, 0, 0, 0.7), inset 0 1px 0 rgba(255, 255, 255, 0.08);
      border: 1px solid rgba(255, 255, 255, 0.1);
      max-width: 550px;
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
      font-size: 1.7rem;
      letter-spacing: 2px;
      margin-bottom: 1.6rem;
      text-shadow: 0 2px 5px rgba(0,0,0,0.5);
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }
    h2 span {
      background: #3a4a6b;
      padding: 0.2rem 0.8rem;
      border-radius: 3rem;
      font-size: 1.3rem;
      color: #ffd966;
    }

    .captcha-panel {
      background: #f5f0e7;
      border-radius: 2.2rem;
      padding: 1.8rem 1.5rem 1.5rem;
      width: 100%;
      box-shadow: inset 0 0 10px rgba(0,0,0,0.3), 0 15px 25px rgba(0, 0, 0, 0.6);
      border: 2px solid #b9a68c;
      background: #f9f3e9;
      margin-bottom: 1.8rem;
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
      font-size: 1.3rem;
      color: #1e2b3c;
      letter-spacing: 0.3px;
    }

    .recaptcha-logo {
      display: flex;
      align-items: center;
      gap: 0.3rem;
      color: #4a4a4a;
      font-size: 0.9rem;
    }
    .recaptcha-logo img {
      width: 28px;
      opacity: 0.8;
    }

    .challenge-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 0.9rem;
      margin: 1.2rem 0 1.8rem;
    }

    .grid-image {
      aspect-ratio: 1 / 1;
      background-size: cover;
      background-position: center;
      border-radius: 1rem;
      cursor: pointer;
      border: 3px solid transparent;
      box-shadow: 0 6px 12px rgba(0,0,0,0.3);
      transition: 0.2s ease;
      position: relative;
      background-color: #d9cdb6;
    }

    .grid-image.selected {
      border: 4px solid #ffb74d;
      box-shadow: 0 0 18px #ffa726;
      transform: scale(0.97);
    }

    .grid-image::after {
      content: "✓";
      position: absolute;
      top: 5px;
      right: 8px;
      font-size: 1.7rem;
      font-weight: bold;
      color: #ffb703;
      text-shadow: 0 0 8px black;
      display: none;
    }
    .grid-image.selected::after {
      display: block;
    }

    .action-buttons {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 1rem;
      margin-top: 0.5rem;
    }

    .btn {
      background: #4a627a;
      border: none;
      padding: 0.7rem 1.5rem;
      border-radius: 2.5rem;
      font-weight: 600;
      letter-spacing: 0.5px;
      color: #f0e6d3;
      background: #2e4057;
      cursor: pointer;
      transition: 0.2s;
      box-shadow: 0 5px 0 #1a2533;
      border: 1px solid #6d7f94;
      font-size: 0.95rem;
      display: flex;
      align-items: center;
      gap: 0.3rem;
    }

    .btn:hover {
      background: #3b5068;
      transform: translateY(-2px);
      box-shadow: 0 7px 0 #1a2533;
    }

    .btn:active {
      transform: translateY(2px);
      box-shadow: 0 3px 0 #1a2533;
    }

    .btn.primary {
      background: #d4a373;
      border-color: #f3d5b5;
      color: #2d1f0c;
      font-weight: bold;
      box-shadow: 0 5px 0 #936639;
    }

    .verify-status {
      font-size: 0.9rem;
      color: #c9b896;
      margin-left: 0.5rem;
    }

    .message-box {
      margin-top: 1rem;
      background: #1e2638;
      padding: 0.7rem 1.2rem;
      border-radius: 2rem;
      color: #ffcf9a;
      font-weight: 500;
      text-align: center;
      min-height: 3.2rem;
      display: flex;
      align-items: center;
      justify-content: center;
      border: 1px solid #ffb74d40;
    }

    .hidden {
      display: none !important;
    }

    .footer-note {
      color: #8f9bb0;
      margin-top: 0.8rem;
      font-size: 0.8rem;
      opacity: 0.8;
    }

    @media (max-width: 450px) {
      .game-container {
        padding: 1.5rem 1.2rem;
      }
      .grid-image {
        border-radius: 0.7rem;
      }
    }
  </style>
</head>
<body>
<div class="game-container">
  <div class="chinatown-badge">chinatown</div>
  <h2>🤖 I'M NOT A ROBOT <span>🔐</span></h2>

  <div class="captcha-panel">
    <!-- initial checkbox area -->
    <div class="robot-check-row" id="initialCheckRow">
      <div class="checkbox-area">
        <div class="custom-checkbox" id="mainCheckbox">
          <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="4">
            <polyline points="4 12 10 18 20 6"></polyline>
          </svg>
        </div>
        <span class="label-text">I'm not a robot</span>
      </div>
      <div class="recaptcha-logo">
        <span style="font-weight:bold; color:#2c5282;">reCAPTCHA</span>
      </div>
    </div>

    <!-- challenge section (hidden initially) -->
    <div id="challengeSection" class="hidden">
      <p style="color:#1f2a3a; font-weight:600; margin-bottom:0.7rem; font-size:1.1rem;">
        🖼️ Select all images with <strong style="color:#b3541c;">traffic lights</strong>
      </p>
      <div class="challenge-grid" id="imageGrid"></div>
      <div class="action-buttons">
        <button class="btn" id="skipBtn">↻ Skip</button>
        <button class="btn primary" id="verifyBtn">✅ VERIFY</button>
      </div>
    </div>
  </div>

  <div class="message-box" id="messageDisplay">
    🤔 Prove you're human
  </div>
  <div class="footer-note">chinatown · reimagined captcha</div>
</div>

<script>
  (function() {
    // ----- game state -----
    const imagePool = [
      { id: 0, src: "https://placehold.co/200x200/3b5e4b/white?text=🚦+LIGHT", isTarget: true },
      { id: 1, src: "https://placehold.co/200x200/7c5c3e/white?text=🌳+TREE", isTarget: false },
      { id: 2, src: "https://placehold.co/200x200/4a6c8f/white?text=🚗+CAR", isTarget: false },
      { id: 3, src: "https://placehold.co/200x200/9b4b3e/white?text=🚥+SIGNAL", isTarget: true },
      { id: 4, src: "https://placehold.co/200x200/5e6b4b/white?text=🐕+DOG", isTarget: false },
      { id: 5, src: "https://placehold.co/200x200/8f6b4c/white?text=🚲+BIKE", isTarget: false },
      { id: 6, src: "https://placehold.co/200x200/3e6b5c/white?text=🚦+CROSS", isTarget: true },
      { id: 7, src: "https://placehold.co/200x200/5a4a6b/white?text=🏠+HOUSE", isTarget: false },
      { id: 8, src: "https://placehold.co/200x200/2f5e4f/white?text=🚏+STOP", isTarget: true },
      { id: 9, src: "https://placehold.co/200x200/7c6b5c/white?text=☕+CUP", isTarget: false }
    ];

    // current challenge images (9 items shuffled)
    let currentImages = [];
    let selectedIndices = new Set(); // indices in current grid array (0-8)
    let challengeActive = false;
    let verificationSuccess = false;

    // DOM elements
    const mainCheckbox = document.getElementById('mainCheckbox');
    const initialCheckRow = document.getElementById('initialCheckRow');
    const challengeSection = document.getElementById('challengeSection');
    const imageGrid = document.getElementById('imageGrid');
    const skipBtn = document.getElementById('skipBtn');
    const verifyBtn = document.getElementById('verifyBtn');
    const messageDisplay = document.getElementById('messageDisplay');

    // ----- helper: shuffle array -----
    const shuffleArray = (arr) => {
      for (let i = arr.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [arr[i], arr[j]] = [arr[j], arr[i]];
      }
      return arr;
    };

    // ----- prepare new challenge (pick 9 images, ensure at least 2 targets) -----
    function generateChallengeImages() {
      // We want exactly 9 images for grid, with mix of targets/non-targets.
      let targets = imagePool.filter(img => img.isTarget);
      let nonTargets = imagePool.filter(img => !img.isTarget);
      
      // Shuffle both
      targets = shuffleArray([...targets]);
      nonTargets = shuffleArray([...nonTargets]);

      // Decide number of targets: between 2 and 4 (makes it interesting)
      const targetCount = Math.floor(Math.random() * 3) + 2; // 2,3,4
      const selectedTargets = targets.slice(0, targetCount);
      const neededNonTargets = 9 - targetCount;
      const selectedNonTargets = nonTargets.slice(0, neededNonTargets);
      
      let combined = [...selectedTargets, ...selectedNonTargets];
      // Shuffle combined array to randomize positions
      return shuffleArray(combined);
    }

    // ----- render grid -----
    function renderGrid() {
      imageGrid.innerHTML = '';
      currentImages.forEach((img, idx) => {
        const div = document.createElement('div');
        div.className = 'grid-image';
        div.style.backgroundImage = `url('${img.src}')`;
        div.dataset.index = idx;
        div.dataset.target = img.isTarget;
        
        // if selected, add class
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

    // ----- toggle selection -----
    function toggleSelection(index) {
      if (selectedIndices.has(index)) {
        selectedIndices.delete(index);
      } else {
        selectedIndices.add(index);
      }
      // update UI class for that grid item
      const gridItems = document.querySelectorAll('.grid-image');
      if (gridItems[index]) {
        gridItems[index].classList.toggle('selected');
      }
    }

    // ----- reset challenge state (clear selections, generate new) -----
    function resetAndShowChallenge() {
      selectedIndices.clear();
      currentImages = generateChallengeImages();
      renderGrid();
      challengeActive = true;
      challengeSection.classList.remove('hidden');
      // update message
      messageDisplay.textContent = '🔍 Select traffic lights, then verify.';
    }

    // ----- hide challenge, return to checkbox idle -----
    function hideChallenge() {
      challengeSection.classList.add('hidden');
      challengeActive = false;
      selectedIndices.clear();
      // also uncheck main checkbox if needed
      mainCheckbox.classList.remove('checked');
    }

    // ----- verify selection -----
    function performVerification() {
      if (!challengeActive) {
        messageDisplay.textContent = '⏳ No active challenge. Click checkbox.';
        return;
      }

      // Determine which indices are actual targets
      const targetIndices = new Set();
      currentImages.forEach((img, idx) => {
        if (img.isTarget) targetIndices.add(idx);
      });

      const selectedArray = Array.from(selectedIndices);
      
      // Check if selection exactly matches target set (all targets selected, no extras)
      let correct = true;
      
      if (selectedIndices.size !== targetIndices.size) {
        correct = false;
      } else {
        // same size, check every selected is target
        for (let sel of selectedIndices) {
          if (!targetIndices.has(sel)) {
            correct = false;
            break;
          }
        }
      }

      if (correct) {
        // SUCCESS
        verificationSuccess = true;
        challengeActive = false;
        challengeSection.classList.add('hidden');
        mainCheckbox.classList.add('checked');
        messageDisplay.innerHTML = '✅ <strong>Verified: Human confirmed!</strong> 🎉 chinatown welcomes you.';
        // also disable further interaction via checkbox? keep it happy.
        // keep mainCheckbox visually checked.
      } else {
        // FAIL
        messageDisplay.textContent = '❌ Incorrect selection. Try again or skip.';
        // shake effect? small hint. Reset selections but keep same challenge? 
        // For classic captcha, often it refreshes or keeps same. We'll keep same grid but clear selections.
        selectedIndices.clear();
        renderGrid(); // re-render to remove all selections
        // brief flash
        imageGrid.style.transition = '0.1s';
        imageGrid.style.opacity = '0.7';
        setTimeout(() => {
          imageGrid.style.opacity = '1';
        }, 120);
        challengeActive = true; // still active
      }
    }

    // ----- skip: load new challenge -----
    function skipChallenge() {
      if (!challengeActive) {
        // if somehow hidden, but skip pressed, show new
        resetAndShowChallenge();
        return;
      }
      // fresh challenge
      selectedIndices.clear();
      currentImages = generateChallengeImages();
      renderGrid();
      messageDisplay.textContent = '🔄 New challenge. Select traffic lights.';
      challengeActive = true;
    }

    // ----- Main checkbox click: start challenge if not already verified -----
    function onMainCheckboxClick() {
      // If already verified success, we could do nothing or allow reset? 
      if (verificationSuccess) {
        messageDisplay.textContent = '🎯 You already passed. (click to restart?)';
        // optional: allow reset by clicking again? We'll implement reset on double-check click.
        return;
      }
      
      if (challengeActive) {
        // if challenge is already visible, maybe hide it? (toggle behavior)
        hideChallenge();
        messageDisplay.textContent = '⏸️ Challenge dismissed. Click checkbox to try.';
        mainCheckbox.classList.remove('checked');
        return;
      }
      
      // Otherwise, start challenge
      resetAndShowChallenge();
      mainCheckbox.classList.add('checked'); // indicate active
    }

    // Allow re-trigger even after success: hold click to reset?
    mainCheckbox.addEventListener('dblclick', function(e) {
      // double click resets entire verification
      verificationSuccess = false;
      mainCheckbox.classList.remove('checked');
      hideChallenge();
      messageDisplay.textContent = '🔄 Reset. Prove you are human.';
    });

    mainCheckbox.addEventListener('click', onMainCheckboxClick);

    // Verify button
    verifyBtn.addEventListener('click', performVerification);

    // Skip button
    skipBtn.addEventListener('click', skipChallenge);

    // Extra: if user clicks checkbox while challenge active, it toggles off.
    // already handled in onMainCheckboxClick.

    // Initial message
    messageDisplay.textContent = '👆 Click checkbox to start';

    // Clean up any selection outside grid
    document.addEventListener('click', function(e) {
      if (!e.target.closest('.grid-image') && !e.target.closest('#verifyBtn') && !e.target.closest('#skipBtn')) {
        // Not needed, but prevent accidental deselection? No, we keep selection.
      }
    });

    // Preload a challenge in background? not necessary.
    console.log('chinatown · “I’m not a robot” ready.');
  })();
</script>
</body>
</html>
