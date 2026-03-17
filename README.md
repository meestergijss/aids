
‎index.html‎
+108
-66
Lines changed: 108 additions & 66 deletions
Original file line number	Diff line number	Diff line change
@@ -24,6 +24,9 @@
  button:hover { background:#444; transform:scale(1.02); }
  button:disabled { opacity: 0.5; cursor: not-allowed; transform: none !important; }
  .small { font-size:11px; opacity:.85; margin:8px 0; }
  .crossed-out { position: relative; opacity: 0.4; }
  .crossed-out::before { content: ''; position: absolute; top: 50%; left: 0; right: 0; height: 4px; background: red; transform: translateY(-50%) rotate(-15deg); z-index: 10; }
  .crossed-out::after { content: ''; position: absolute; top: 50%; left: 0; right: 0; height: 4px; background: red; transform: translateY(-50%) rotate(15deg); z-index: 10; }
  #titleScreen { position: fixed; top: 0; left: 0; width: 100vw; height: 100vh; background: linear-gradient(180deg, #87ceeb 0%, #f4a460 50%, #daa520 100%); background-size: 400% 400%; display: flex; flex-direction: column; justify-content: center; align-items: center; z-index: 1000; animation: desertShift 20s ease infinite; overflow-y: auto; overflow-x: hidden; }
  #titleScreen::before { content: ''; position: absolute; top: 10%; right: 15%; width: 150px; height: 150px; background: radial-gradient(circle, #ffeb3b 0%, #ff9800 50%, #ff5722 100%); border-radius: 50%; box-shadow: 0 0 60px #ff9800, 0 0 100px #ff5722; animation: sunPulse 4s ease-in-out infinite; }
  @keyframes sunPulse { 0%, 100% { transform: scale(1); opacity: 0.9; } 50% { transform: scale(1.1); opacity: 1; } }
@@ -40,6 +43,7 @@
  .modeBtn.plaag { background: linear-gradient(135deg, #8b0000 0%, #dc143c 50%, #ff4500 100%); color: #fff; animation: plaagPulse 2s ease-in-out infinite; }
  .modeBtn.hard { background: linear-gradient(135deg, #2c003e 0%, #6a0572 50%, #c70039 100%); color: #fff; animation: hardPulse 1.5s ease-in-out infinite; }
  .modeBtn.speed { background: linear-gradient(135deg, #0066cc 0%, #00aaff 50%, #00ffff 100%); color: #fff; animation: speedPulse 1s ease-in-out infinite; }
  .modeBtn.armoede { background: linear-gradient(135deg, #4a4a4a 0%, #2a2a2a 50%, #1a1a1a 100%); color: #aaa; border-color: #666; }
  .modeBtn.boss { background: linear-gradient(135deg, #ff0000 0%, #8b0000 50%, #4a0000 100%); color: #fff; animation: bossPulse 2s ease-in-out infinite; }
  .modeBtn.mutatie { background: linear-gradient(135deg, #00c853 0%, #006600 50%, #004400 100%); color: #adffa3; text-shadow: 0 0 10px #00ff44; animation: mutatiePulse 2s ease-in-out infinite; border-color: #00ff44; }
  .modeBtn.dubbelhealth { background: linear-gradient(135deg, #0d47a1 0%, #1565c0 50%, #1976d2 100%); color: #fff; text-shadow: 0 0 10px #4fc3f7; animation: dhPulse 2s ease-in-out infinite; }
@@ -92,6 +96,7 @@
  @keyframes highlight { 0%, 100% { box-shadow: 0 0 10px #ffd700; } 50% { box-shadow: 0 0 20px #ffd700; } }
  .restartBtn { padding: 18px 50px; font-size: 28px; margin-top: 35px; border: 4px solid #fff; border-radius: 15px; cursor: pointer; font-weight: bold; background: rgba(0,0,0,0.6); color: #fff; transition: all 0.3s; }
  .restartBtn:hover { transform: scale(1.1); background: rgba(255,255,255,0.2); box-shadow: 0 0 30px rgba(255,255,255,0.5); }
  /* Tower tooltip overlay */
  #towerTooltip { position: fixed; background: linear-gradient(160deg,rgba(18,12,2,0.98),rgba(30,20,5,0.97)); border: 2px solid #daa520; border-radius: 14px; padding: 13px 15px 10px; pointer-events: none; z-index: 500; display: none; min-width: 230px; max-width: 280px; box-shadow: 0 6px 28px rgba(0,0,0,0.9), 0 0 12px rgba(218,165,32,0.15); }
  #towerTooltip .tt-name { font-size: 14px; font-weight: bold; color: #ffd700; margin-bottom: 2px; letter-spacing: 1px; }
  #towerTooltip .tt-level { font-size: 11px; color: #cd853f; margin-bottom: 8px; letter-spacing: 0.5px; }
@@ -107,6 +112,7 @@
  #towerTooltip .tt-upgrade-header.max { color: #666; }
  #towerTooltip .tt-sell { font-size: 10px; color: #ff6b6b; margin-top: 6px; border-top: 1px solid rgba(255,100,100,0.2); padding-top: 6px; }
  #towerTooltip .tt-passive { font-size: 10px; color: #aaffcc; margin-top: 4px; border-top: 1px solid rgba(100,255,150,0.2); padding-top: 4px; font-style: italic; }
  /* Sell flash */
  #sellFlash { position: fixed; top: 0; left: 0; width: 100vw; height: 100vh; background: rgba(255,200,0,0.18); pointer-events: none; z-index: 998; display: none; animation: sellFade 0.4s ease-out; }
  @keyframes sellFade { 0% { opacity: 1; } 100% { opacity: 0; } }
</style>
@@ -154,6 +160,7 @@ <h1>🏜️ TSJAAD TD 🐪</h1>
    <button class="modeBtn plaag" onclick="startGame('plaag')" id="btn-plaag">🌋 PLAAG MODUS 🦠</button>
    <button class="modeBtn hard" onclick="startGame('hard')" id="btn-hard">💀 HARD MODUS ⚡</button>
    <button class="modeBtn speed" onclick="startGame('speed')" id="btn-speed">⚡ DUBBEL SNELHEID 🏎️</button>
    <button class="modeBtn armoede" onclick="startGame('armoede')" id="btn-armoede">💀 ARMOEDE MODUS 💀</button>
    <button class="modeBtn boss" onclick="startGame('boss')" id="btn-boss">👹 BOSS BATTLE 👹</button>
    <button class="modeBtn mutatie" onclick="startGame('mutatie')" id="btn-mutatie">🧬 MUTATIE MODUS 🧬</button>
    <button class="modeBtn dubbelhealth" onclick="startGame('dubbelhealth')" id="btn-dubbelhealth">💙 DUBBEL HEALTH 💙</button>
@@ -164,7 +171,7 @@ <h1>🏜️ TSJAAD TD 🐪</h1>

<div id="victoryScreen" class="endScreen">
  <h1 id="vs-title">🏆 OVERWINNING! 🏆</h1>
  <div class="message"><strong id="vs-line1">JE HEBT DE ULTRA MUG VERSLAGEN!</strong><br><span id="vs-line2">JE HEBT DE PLAAG IN TSJAAD OVERLEEFD!</span><br><em id="vs-line3">JE BENT TSJAADTASTISCH!!!</em></div>
  <div class="message"><strong id="vs-line1">JE HEBT DE MALARIA MUG VERSLAGEN!</strong><br><span id="vs-line2">JE HEBT DE PLAAG IN TSJAAD OVERLEEFD!</span><br><em id="vs-line3">JE BENT TSJAADTASTISCH!!!</em></div>
  <div class="stats"><span id="vs-rounds-label">⚔️ Rondes Overleefd:</span> <strong><span id="finalRound"></span></strong><br><span id="vs-money-label">💰 Totaal Verdiend:</span> <strong>€<span id="finalMoney"></span></strong></div>
  <button class="restartBtn" onclick="location.reload()" id="vs-restart">🔄 Opnieuw Spelen</button>
</div>
@@ -194,7 +201,7 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
  <button onclick="selectTower('aap')" id="tower-aap">🐵 Wilde Aap (€400)</button>
  <button onclick="selectTower('geweer')" id="tower-geweer">🔫 Soldaat (€550)</button>
  <button onclick="selectTower('atoom')" id="tower-atoom">💣 Atoombommenwerper (€600)</button>
  <button id="fabrieksBtn" onclick="selectTower('katoen')">🏭 Fabriek (€950)</button>
  <button id="katoenBtn" onclick="selectTower('katoen')">🌾 Katoen Plantage (€950)</button>
  <button onclick="selectTower('tsjaadinator')" id="tower-tsjaad">⚡ Tsjaadinator (€2500)</button>
  <button onclick="selectTower('sniper')" id="tower-sniper">🎯 Sniper (€3000)</button>
  <hr style="margin:10px 0; border-color:#444;">
@@ -214,71 +221,71 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
    'stg-title': '⚙️ INSTELLINGEN','stg-music-label': '🎵 MUZIEK VOLUME','stg-sfx-label': '🔊 GELUIDSEFFECTEN',
    'stg-lang-label': '🌍 TAAL / LANGUAGE / SPRACHE','title-subtitle': '⚔️ VECHT VOOR TSJAAD!!! ⚔️',
    'btn-standard': '🦟 STANDAARD MODUS','btn-plaag': '🌋 PLAAG MODUS 🦠','btn-hard': '💀 HARD MODUS ⚡',
    'btn-speed': '⚡ DUBBEL SNELHEID 🏎️','btn-boss': '👹 BOSS BATTLE 👹',
    'btn-speed': '⚡ DUBBEL SNELHEID 🏎️','btn-armoede': '💀 ARMOEDE MODUS 💀','btn-boss': '👹 BOSS BATTLE 👹',
    'btn-mutatie': '🧬 MUTATIE MODUS 🧬','btn-dubbelhealth': '💙 DUBBEL HEALTH 💙','btn-tsjaad': '🔥 TSJAAD MODUS 🔥',
    'vs-title': '🏆 OVERWINNING! 🏆','vs-line1': 'JE HEBT DE ULTRA MUG VERSLAGEN!',
    'vs-title': '🏆 OVERWINNING! 🏆','vs-line1': 'JE HEBT DE MALARIA MUG VERSLAGEN!',
    'vs-line2': 'JE HEBT DE PLAAG IN TSJAAD OVERLEEFD!','vs-line3': 'JE BENT TSJAADTASTISCH!!!',
    'vs-rounds-label': '⚔️ Rondes Overleefd:','vs-money-label': '💰 Totaal Verdiend:','vs-restart': '🔄 Opnieuw Spelen',
    'ds-title': '💀 GAME OVER LOSER 💀','ds-restart': '🔄 Opnieuw Proberen','lb-title': '🏆 LEADERBOARD 🏆',
    'ui-money-label': '💰 Geld:','ui-lives-label': '❤️ Levens:','ui-round-label': '🌊 Ronde:',
    'tower-speer': '⚔️ Speer Werper (€80)','tower-boog': '🏹 Boog Schutter (€125)','tower-fakkel': '🔥 Fakkel Drager (€150)',
    'tower-plaag': '💉 Plaag Dokter (€300)','tower-aap': '🐵 Wilde Aap (€400)','tower-geweer': '🔫 Soldaat (€550)',
    'tower-atoom': '💣 Atoombommenwerper (€600)','tower-katoen': '🏭 Fabriek (€950)',
    'tower-atoom': '💣 Atoombommenwerper (€600)','tower-katoen': '🌾 Katoen Plantage (€950)',
    'tower-tsjaad': '⚡ Tsjaadinator (€2500)','tower-sniper': '🎯 Sniper (€3000)',
    'btn-startround': '▶️ Start Ronde','ui-upgrade-hint': '💡 Hover toren = info & upgrade | Backspace = verkopen',
    'death-survived': 'JE OVERLEEFDE','death-rounds': 'RONDES IN','death-toostrong': 'DE VIJANDEN WAREN TE STERK...',
    'death-fell': '💀 Gevallen op Ronde:','death-earned': '💰 Totaal Verdiend:',
    'round-farms': '🏭 Fabriek: €','round-label': '▶️ Ronde ','auto-hard': '⚡ AUTO-START INSTANT!','auto-tsjaad': '🔥 AUTO-START INSTANT!',
    'round-farms': '🌾 Plantages: €','round-label': '▶️ Ronde ','auto-hard': '⚡ AUTO-START INSTANT!','auto-tsjaad': '🔥 AUTO-START INSTANT!',
    'mode-standard': 'STANDAARD','mode-plaag': 'PLAAG MODUS','mode-hard': 'HARD MODUS','mode-speed': 'DUBBEL SNELHEID',
    'mode-boss': 'BOSS MODE','mode-mutatie': 'MUTATIE MODUS',
    'mode-armoede': 'ARMOEDE MODUS','mode-boss': 'BOSS MODE','mode-mutatie': 'MUTATIE MODUS',
    'mode-dubbelhealth': 'DUBBEL HEALTH','mode-tsjaadmodus': 'TSJAAD MODUS',
    'btn-tsjaadplus': '💀☠️ TSJAAD MODUS PLUS ☠️💀','mode-tsjaadplus': 'TSJAAD MODUS PLUS',
  },
  en: {
    'stg-title': '⚙️ SETTINGS','stg-music-label': '🎵 MUSIC VOLUME','stg-sfx-label': '🔊 SOUND EFFECTS',
    'stg-lang-label': '🌍 LANGUAGE','title-subtitle': '⚔️ FIGHT FOR CHAD!!! ⚔️',
    'btn-standard': '🦟 STANDARD MODE','btn-plaag': '🌋 PLAGUE MODE 🦠','btn-hard': '💀 HARD MODE ⚡',
    'btn-speed': '⚡ DOUBLE SPEED 🏎️','btn-boss': '👹 BOSS BATTLE 👹',
    'btn-speed': '⚡ DOUBLE SPEED 🏎️','btn-armoede': '💀 POVERTY MODE 💀','btn-boss': '👹 BOSS BATTLE 👹',
    'btn-mutatie': '🧬 MUTATION MODE 🧬','btn-dubbelhealth': '💙 DOUBLE HEALTH 💙','btn-tsjaad': '🔥 CHAD MODE 🔥',
    'vs-title': '🏆 VICTORY! 🏆','vs-line1': 'YOU DEFEATED THE ULTRA MOSQUITO!',
    'vs-title': '🏆 VICTORY! 🏆','vs-line1': 'YOU DEFEATED THE MALARIA MOSQUITO!',
    'vs-line2': 'YOU SURVIVED THE PLAGUE IN CHAD!','vs-line3': 'YOU ARE CHADTASTIC!!!',
    'vs-rounds-label': '⚔️ Rounds Survived:','vs-money-label': '💰 Total Earned:','vs-restart': '🔄 Play Again',
    'ds-title': '💀 GAME OVER LOSER 💀','ds-restart': '🔄 Try Again','lb-title': '🏆 LEADERBOARD 🏆',
    'ui-money-label': '💰 Money:','ui-lives-label': '❤️ Lives:','ui-round-label': '🌊 Round:',
    'tower-speer': '⚔️ Spear Thrower (€80)','tower-boog': '🏹 Archer (€125)','tower-fakkel': '🔥 Torch Bearer (€150)',
    'tower-plaag': '💉 Plague Doctor (€300)','tower-aap': '🐵 Wild Monkey (€400)','tower-geweer': '🔫 Soldier (€550)',
    'tower-atoom': '💣 Atom Bomber (€600)','tower-katoen': '🏭 Factory (€950)',
    'tower-atoom': '💣 Atom Bomber (€600)','tower-katoen': '🌾 Cotton Plantation (€950)',
    'tower-tsjaad': '⚡ Chadinator (€2500)','tower-sniper': '🎯 Sniper (€3000)',
    'btn-startround': '▶️ Start Round','ui-upgrade-hint': '💡 Hover tower = info & upgrade | Backspace = sell',
    'death-survived': 'YOU SURVIVED','death-rounds': 'ROUNDS IN','death-toostrong': 'THE ENEMIES WERE TOO STRONG...',
    'death-fell': '💀 Fell at Round:','death-earned': '💰 Total Earned:',
    'round-farms': '🏭 Factory: €','round-label': '▶️ Round ','auto-hard': '⚡ AUTO-START INSTANT!','auto-tsjaad': '🔥 AUTO-START INSTANT!',
    'round-farms': '🌾 Plantations: €','round-label': '▶️ Round ','auto-hard': '⚡ AUTO-START INSTANT!','auto-tsjaad': '🔥 AUTO-START INSTANT!',
    'mode-standard': 'STANDARD','mode-plaag': 'PLAGUE MODE','mode-hard': 'HARD MODE','mode-speed': 'DOUBLE SPEED',
    'mode-boss': 'BOSS MODE','mode-mutatie': 'MUTATION MODE',
    'mode-armoede': 'POVERTY MODE','mode-boss': 'BOSS MODE','mode-mutatie': 'MUTATION MODE',
    'mode-dubbelhealth': 'DOUBLE HEALTH','mode-tsjaadmodus': 'CHAD MODE',
    'btn-tsjaadplus': '💀☠️ CHAD MODE PLUS ☠️💀','mode-tsjaadplus': 'CHAD MODE PLUS',
  },
  de: {
    'stg-title': '⚙️ EINSTELLUNGEN','stg-music-label': '🎵 MUSIKLAUTSTÄRKE','stg-sfx-label': '🔊 SOUNDEFFEKTE',
    'stg-lang-label': '🌍 SPRACHE','title-subtitle': '⚔️ KÄMPFE FÜR TSCHAD!!! ⚔️',
    'btn-standard': '🦟 STANDARD-MODUS','btn-plaag': '🌋 SEUCHEN-MODUS 🦠','btn-hard': '💀 HARD-MODUS ⚡',
    'btn-speed': '⚡ DOPPELTE GESCHWINDIGKEIT 🏎️','btn-boss': '👹 BOSS BATTLE 👹',
    'btn-speed': '⚡ DOPPELTE GESCHWINDIGKEIT 🏎️','btn-armoede': '💀 ARMUTS-MODUS 💀','btn-boss': '👹 BOSS BATTLE 👹',
    'btn-mutatie': '🧬 MUTATIONS-MODUS 🧬','btn-dubbelhealth': '💙 DOPPELTE GESUNDHEIT 💙','btn-tsjaad': '🔥 TSCHAD-MODUS 🔥',
    'vs-title': '🏆 SIEG! 🏆','vs-line1': 'DU HAST DIE ULTRA MÜCKE BESIEGT!',
    'vs-title': '🏆 SIEG! 🏆','vs-line1': 'DU HAST DIE MALARIA-MÜCKE BESIEGT!',
    'vs-line2': 'DU HAST DIE SEUCHE IN TSCHAD ÜBERLEBT!','vs-line3': 'DU BIST TSCHADTASTISCH!!!',
    'vs-rounds-label': '⚔️ Überlebte Runden:','vs-money-label': '💰 Gesamtverdienst:','vs-restart': '🔄 Nochmal Spielen',
    'ds-title': '💀 GAME OVER VERLIERER 💀','ds-restart': '🔄 Nochmal Versuchen','lb-title': '🏆 BESTENLISTE 🏆',
    'ui-money-label': '💰 Geld:','ui-lives-label': '❤️ Leben:','ui-round-label': '🌊 Runde:',
    'tower-speer': '⚔️ Speerwerfer (€80)','tower-boog': '🏹 Bogenschütze (€125)','tower-fakkel': '🔥 Fackelträger (€150)',
    'tower-plaag': '💉 Seuchenarzt (€300)','tower-aap': '🐵 Wilder Affe (€400)','tower-geweer': '🔫 Soldat (€550)',
    'tower-atoom': '💣 Atombomber (€600)','tower-katoen': '🏭 Fabrik (€950)',
    'tower-atoom': '💣 Atombomber (€600)','tower-katoen': '🌾 Baumwollplantage (€950)',
    'tower-tsjaad': '⚡ Tschadinator (€2500)','tower-sniper': '🎯 Scharfschütze (€3000)',
    'btn-startround': '▶️ Runde Starten','ui-upgrade-hint': '💡 Turm-Hover = Info & Upgrade | Backspace = Verkaufen',
    'death-survived': 'DU HAST','death-rounds': 'RUNDEN IN','death-toostrong': 'DIE FEINDE WAREN ZU STARK...',
    'death-fell': '💀 Gefallen in Runde:','death-earned': '💰 Gesamtverdienst:',
    'round-farms': '🏭 Fabrik: €','round-label': '▶️ Runde ','auto-hard': '⚡ AUTO-START SOFORT!','auto-tsjaad': '🔥 AUTO-START SOFORT!',
    'round-farms': '🌾 Plantagen: €','round-label': '▶️ Runde ','auto-hard': '⚡ AUTO-START SOFORT!','auto-tsjaad': '🔥 AUTO-START SOFORT!',
    'mode-standard': 'STANDARD','mode-plaag': 'SEUCHENMODUS','mode-hard': 'HARD MODUS','mode-speed': 'DOPPELTE GESCHWINDIGKEIT',
    'mode-boss': 'BOSS MODE','mode-mutatie': 'MUTATIONS-MODUS',
    'mode-armoede': 'ARMUTS-MODUS','mode-boss': 'BOSS MODE','mode-mutatie': 'MUTATIONS-MODUS',
    'mode-dubbelhealth': 'DOPPELTE GESUNDHEIT','mode-tsjaadmodus': 'TSCHAD-MODUS',
    'btn-tsjaadplus': '💀☠️ TSCHAD-MODUS PLUS ☠️💀','mode-tsjaadplus': 'TSCHAD-MODUS PLUS',
  }
@@ -295,7 +302,7 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
}

function applyTranslations() {
  const ids = ['stg-title','stg-music-label','stg-sfx-label','stg-lang-label','title-subtitle','btn-standard','btn-plaag','btn-hard','btn-speed','btn-boss','btn-mutatie','btn-dubbelhealth','btn-tsjaad','vs-title','vs-line1','vs-line2','vs-line3','vs-rounds-label','vs-money-label','vs-restart','ds-title','ds-restart','lb-title','ui-money-label','ui-lives-label','ui-round-label','tower-speer','tower-boog','tower-fakkel','tower-plaag','tower-aap','tower-geweer','tower-atoom','tower-katoen','tower-tsjaad','tower-sniper','btn-startround','ui-upgrade-hint'];
  const ids = ['stg-title','stg-music-label','stg-sfx-label','stg-lang-label','title-subtitle','btn-standard','btn-plaag','btn-hard','btn-speed','btn-armoede','btn-boss','btn-mutatie','btn-dubbelhealth','btn-tsjaad','vs-title','vs-line1','vs-line2','vs-line3','vs-rounds-label','vs-money-label','vs-restart','ds-title','ds-restart','lb-title','ui-money-label','ui-lives-label','ui-round-label','tower-speer','tower-boog','tower-fakkel','tower-plaag','tower-aap','tower-geweer','tower-atoom','tower-katoen','tower-tsjaad','tower-sniper','btn-startround','ui-upgrade-hint'];
  for (const id of ids) { const el = document.getElementById(id); if (el) el.textContent = t(id); }
  const moneyEl = document.getElementById('ui-money-label');
  if (moneyEl) { const val = document.getElementById('money') ? document.getElementById('money').textContent : '500'; moneyEl.innerHTML = t('ui-money-label') + ' <strong><span id="money">' + val + '</span></strong>'; }
@@ -315,7 +322,7 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
  document.getElementById('musicVolDisplay').textContent = val + '%';
  const slider = document.getElementById('musicVol');
  slider.style.background = `linear-gradient(to right, #daa520 0%, #daa520 ${val}%, #3a2a0a ${val}%, #3a2a0a 100%)`;
  for (const key of Object.keys(sounds)) { if (['mainTheme','volcanoTheme','hardTheme','doubleSpeed','bossMode','mutatieModus','dubbelHealthModus','tsjaadModus'].includes(key)) sounds[key].volume = musicVolume; }
  for (const key of Object.keys(sounds)) { if (['mainTheme','volcanoTheme','hardTheme','doubleSpeed','armoede','bossMode','mutatieModus','dubbelHealthModus','tsjaadModus'].includes(key)) sounds[key].volume = musicVolume; }
  localStorage.setItem('tsjaadTD_musicVol', val);
}
function updateSfxVol(val) {
@@ -378,7 +385,7 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
const sounds = {
  mainTheme: new Audio('Audio/MainTheme.mp3'), volcanoTheme: new Audio('Audio/VolcanoTheme.mp3'),
  hardTheme: new Audio('Audio/HardTheme.mp3'), doubleSpeed: new Audio('Audio/DoubleSpeedMode.mp3'),
  bossMode: new Audio('Audio/BossMode.mp3'),
  armoede: new Audio('Audio/ArmoedeModus.mp3'), bossMode: new Audio('Audio/BossMode.mp3'),
  mutatieModus: new Audio('Audio/MutatieModus.mp3'), dubbelHealthModus: new Audio('Audio/DubbelHealthModus.mp3'),
  tsjaadModus: new Audio('Audio/TsjaadModus.mp3'), explosion: new Audio('Audio/Explosion.mp3'),
  round: new Audio('Audio/Round.mp3'), kill: new Audio('Audio/Kill.mp3'),
@@ -387,7 +394,7 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
  sell: new Audio('Audio/Sell.mp3')
};
for(const key of Object.keys(sounds)){
  if(['mainTheme','volcanoTheme','hardTheme','doubleSpeed','bossMode','mutatieModus','dubbelHealthModus','tsjaadModus'].includes(key)){ sounds[key].loop=true; sounds[key].volume=musicVolume; }
  if(['mainTheme','volcanoTheme','hardTheme','doubleSpeed','armoede','bossMode','mutatieModus','dubbelHealthModus','tsjaadModus'].includes(key)){ sounds[key].loop=true; sounds[key].volume=musicVolume; }
}
let musicPlaying=false, currentTheme=null;
function playMusic() { if(currentTheme&&!musicPlaying){ currentTheme.volume=musicVolume; currentTheme.play().then(()=>{ musicPlaying=true; }).catch(e=>{}); } }
@@ -420,6 +427,7 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
  if(mode==='plaag'){ path=volcanoPath; document.getElementById('gameTitle').innerHTML='🌋 <span style="color:#ff6b35">'+t('mode-plaag')+'</span> 🦠'; document.getElementById('roundMax').textContent=''; lives=12; money=700; autoStartRounds=false; currentTheme=sounds.volcanoTheme; }
  else if(mode==='hard'){ path=hardPath; document.getElementById('gameTitle').innerHTML='💀 <span style="color:#c70039">'+t('mode-hard')+'</span> ⚡'; document.getElementById('roundMax').textContent='/50'; lives=20; money=300; autoStartRounds=true; autoRoundCountdown=0; document.getElementById('startRoundBtn').style.display='none'; document.getElementById('autoRoundMsg').textContent=t('auto-hard'); currentTheme=sounds.hardTheme; }
  else if(mode==='speed'){ path=racePath; document.getElementById('gameTitle').innerHTML='⚡ <span style="color:#00ffff">'+t('mode-speed')+'</span> 🏎️'; document.getElementById('roundMax').textContent='/30'; lives=20; money=2000; autoStartRounds=false; currentTheme=sounds.doubleSpeed; }
  else if(mode==='armoede'){ path=standardPath; document.getElementById('gameTitle').innerHTML='💀 <span style="color:#888">'+t('mode-armoede')+'</span> 💀'; document.getElementById('roundMax').textContent='/30'; lives=1; money=500; autoStartRounds=false; currentTheme=sounds.armoede; document.getElementById('katoenBtn').disabled=true; document.getElementById('katoenBtn').classList.add('crossed-out'); }
  else if(mode==='boss'){ path=bossPath; document.getElementById('gameTitle').innerHTML='👹 <span style="color:#ff0000">'+t('mode-boss')+'</span> 👹'; document.getElementById('roundMax').textContent='/1'; lives=20; money=1000; autoStartRounds=false; currentTheme=sounds.bossMode; }
  else if(mode==='mutatie'){ path=mutatiePath; document.getElementById('gameTitle').innerHTML='🧬 <span style="color:#00ff44">'+t('mode-mutatie')+'</span> 🧬'; document.getElementById('roundMax').textContent='/35'; lives=20; money=600; autoStartRounds=false; currentTheme=sounds.mutatieModus; }
  else if(mode==='dubbelhealth'){ path=dubbelHealthPath; document.getElementById('gameTitle').innerHTML='💙 <span style="color:#4fc3f7">'+t('mode-dubbelhealth')+'</span> 💙'; document.getElementById('roundMax').textContent='/30'; lives=20; money=500; autoStartRounds=false; currentTheme=sounds.dubbelHealthModus; }
@@ -434,16 +442,18 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>

// ===== TOWERS =====
const towerBaseRanges = {
  speer:90, boog:1300, plaagdokter:140, geweer:240, sniper:550,
  speer:90, boog:130, plaagdokter:140, geweer:240, sniper:550,
  tsjaadinator:180, atoom:180, katoen:0, aap:120, fakkel:95
};

const towerTypes={
  speer:{range:90,rate:40,dmg:3.6,speed:3.2,cost:80,ultCost:800},
  boog:{range:1300,rate:555,dmg:70,speed:20,cost:12,ultCost:150},
  boog:{range:130,rate:55,dmg:7,speed:2,cost:125,ultCost:1500},
  plaagdokter:{range:140,rate:40,dmg:8,speed:3.5,cost:300,ultCost:2000,slow:true},
  geweer:{range:240,rate:12,dmg:3.8,speed:7,cost:550,ultCost:5000},
  // CHANGED: sniper secretCost removed, cost stays same
  sniper:{range:550,rate:300,dmg:300,speed:10,cost:5000,ultCost:28000},
  // CHANGED: secretCost is now 300000
  tsjaadinator:{range:180,rate:5,dmg:3.8,speed:8,cost:2500,ultCost:15000,secretCost:300000},
  atoom:{range:180,rate:120,dmg:25,speed:3,cost:600,bomb:true,ultCost:3500},
  katoen:{range:0,rate:9999,dmg:0,speed:0,cost:950,farm:true,ultCost:4000},
@@ -454,6 +464,7 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
function getTowerRange(tw) {
  const baseRange = towerBaseRanges[tw.key] || towerTypes[tw.key].range || 0;
  let range = baseRange * (1 + tw.level * 0.05);
  // NEW: Apply speer ultimate range boost if active
  if(tw.speerRangeBoostUntil && Date.now() < tw.speerRangeBoostUntil){
    range *= 1.30;
  }
@@ -478,16 +489,15 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
  {name:'Kameel',hp:28,speed:0.4,size:20,reward:35,type:'kameel',minRound:18},
  {name:'Robo Leeuw',hp:20,speed:1.25,size:16,reward:40,type:'roboleeuw',minRound:16},
  {name:'Vogel',hp:10,speed:1.4,size:13,reward:30,type:'vogel',minRound:16},
  // Krokodil: same HP as Nijlpaard, immune to Sniper & Soldier, spawns after round 20 in all modes
  {name:'Krokodil',hp:28,speed:0.75,size:20,reward:38,type:'krokodil',minRound:20},
];
const bossType = {name:'Malaria Mug',hp:50000,speed:0.7,size:80,reward:1000,boss:true,type:'mug'};
const mutatedBossType = {name:'Gemuteerde Malaria Mug',hp:5000000,speed:0.75,size:95,reward:2500,boss:true,type:'mutatedmug'};
const slowBossType = {name:'Malaria Mug',hp:6500000,speed:0.15,size:120,reward:1000,boss:true,type:'mug'};
const hydraHydraBossType = {name:'Hydra Malaria Mug',hp:100000,speed:0.8,size:100,reward:2000,boss:true,type:'hydramug'};

// ===== ALL BOSSES RENAMED TO ULTRA MUG =====
const bossType = {name:'Ultra Mug',hp:50000,speed:0.7,size:80,reward:1000,boss:true,type:'mug'};
const mutatedBossType = {name:'Ultra Mug',hp:5000000,speed:0.75,size:95,reward:2500,boss:true,type:'mutatedmug'};
const slowBossType = {name:'Ultra Mug',hp:6500000,speed:0.15,size:120,reward:1000,boss:true,type:'mug'};
const hydraHydraBossType = {name:'Ultra Mug',hp:100000,speed:0.8,size:100,reward:2000,boss:true,type:'hydramug'};
function selectTower(t2){ selectedTower=t2; }
function selectTower(t2){ if(gameMode==='armoede'&&t2==='katoen') return; selectedTower=t2; }

const tooltipEl = document.getElementById('towerTooltip');
canvas.onmousemove = e => {
@@ -510,8 +520,7 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
canvas.onmouseleave=()=>{ hoveredTower=null; tooltipEl.style.display='none'; };

function getTowerName(key){
  // Katoen plantage renamed to Fabriek
  const names={speer:'Speer Werper',boog:'Boog Schutter',fakkel:'Fakkel Drager',plaagdokter:'Plaag Dokter',aap:'Wilde Aap',geweer:'Soldaat',atoom:'Atoombommenwerper',katoen:'Fabriek',tsjaadinator:'Tsjaadinator',sniper:'Sniper'};
  const names={speer:'Speer Werper',boog:'Boog Schutter',fakkel:'Fakkel Drager',plaagdokter:'Plaag Dokter',aap:'Wilde Aap',geweer:'Soldaat',atoom:'Atoombommenwerper',katoen:'Katoen Plantage',tsjaadinator:'Tsjaadinator',sniper:'Sniper'};
  return names[key]||key;
}

@@ -553,11 +562,15 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
    else if(tw.key==='fakkel'){ dmg = tw.dmg * 5.5; rate = tw.rate * 0.85; }
    else if(!tw.farm){ dmg = tw.dmg * 1.25; rate = tw.rate * 0.85; }
  } else if(!tw.ultimate){
    const isUltNext = true;
    // Ultimate upgrades
    if(tw.key==='atoom'){ dmg = tw.dmg * 2.8; rate = tw.rate * 0.55; }
    else if(tw.key==='tsjaadinator'){ dmg = tw.dmg * 2; rate = tw.rate * 0.25; }
    // UPDATED: speer ultimate now shows range boost passive
    else if(tw.key==='speer'){ dmg = tw.dmg * 3; rate = tw.rate * 1.2; }
    else if(tw.key==='geweer'){ dmg = 10; rate = tw.rate * 0.45; }
    else if(tw.key==='boog'){ dmg = tw.dmg * 1.9; rate = tw.rate * 0.50; }
    // UPDATED: sniper ultimate shows slow effect
    else if(tw.key==='sniper'){ dmg = 5000; }
    else if(tw.key==='plaagdokter'){ dmg = tw.dmg * 4; slow = null; plaagBonus = (tw.plaagDmgBonus||1.05) + 0.05; }
    else if(tw.key==='aap'){ dmg = tw.dmg * 2; }
@@ -579,7 +592,7 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>

function updateTooltip(tw, cx, cy){
  const name = getTowerName(tw.key);
  const icons = {speer:'⚔️',boog:'🏹',fakkel:'🔥',plaagdokter:'💉',aap:'🐵',geweer:'🔫',atoom:'💣',katoen:'🏭',tsjaadinator:'⚡',sniper:'🎯'};
  const icons = {speer:'⚔️',boog:'🏹',fakkel:'🔥',plaagdokter:'💉',aap:'🐵',geweer:'🔫',atoom:'💣',katoen:'🌾',tsjaadinator:'⚡',sniper:'🎯'};
  const icon = icons[tw.key]||'🏰';

  let lvlLabel, lvlColor;
@@ -645,18 +658,21 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
      html += statRow('🔥 Brand dmg/s', burnDmg, nextBurnDmg !== burnDmg ? nextBurnDmg : null);
      html += statRow('⏱️ Brand duur', tw.ultimate ? '8s' : '8s', null);
    }
    // UPDATED: Sniper ultimate - show slow passive
    if(tw.key==='sniper' && (tw.ultimate || isUltNext)){
      const curSlow = tw.ultimate ? '50% · 0.3s' : '—';
      const nextSlow2 = isUltNext ? '50% · 0.3s' : null;
      html += statRow('❄️ Raakshot slow', curSlow, !tw.ultimate ? nextSlow2 : null);
    }
    // UPDATED: Speer ultimate - show range aura passive
    if(tw.key==='speer' && (tw.ultimate || isUltNext)){
      const curAura = tw.ultimate ? '+30% range' : '—';
      const nextAura = isUltNext ? '+30% range' : null;
      html += statRow('📡 Range aura', curAura, !tw.ultimate ? nextAura : null);
    }
  }

  // Upgrade section
  html += `<hr class="tt-divider">`;
  if(tw.secret){
    html += `<div class="tt-upgrade-header max">✅ GOD MODE ACTIEF</div>`;
@@ -669,19 +685,22 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
  } else if(!tw.ultimate){
    const cost = cfg.ultCost;
    const canAfford = money >= cost;
    // UPDATED: speer and sniper show their new passives in upgrade description
    if(tw.key==='speer'){
      html += `<div class="tt-upgrade-header ult" style="color:${canAfford?'#ffd700':'#f44'}">⭐ ULTIMATE — €${cost} | 📡 +30% range aura</div>`;
    } else if(tw.key==='sniper'){
      html += `<div class="tt-upgrade-header ult" style="color:${canAfford?'#ffd700':'#f44'}">⭐ ULTIMATE — €${cost} | ❄️ Shot slow 50%</div>`;
    } else {
      html += `<div class="tt-upgrade-header ult" style="color:${canAfford?'#ffd700':'#f44'}">⭐ ULTIMATE — €${cost}</div>`;
      html += `<div class="tt-upgrade-header ult" style="color:${canAfford?'#ffd700':'#ف44'}">⭐ ULTIMATE — €${cost}</div>`;
    }
  } else if(tw.key==='tsjaadinator'){
    // UPDATED: Secret cost is now 300000, no tower removal
    const canAfford = money >= 300000;
    html += `<div class="tt-upgrade-header ult" style="color:${canAfford?'#ffd700':'#f44'}">👁️ GOD MODE — €300,000</div>`;
    html += `<div style="font-size:9px;color:#aaa;margin-top:2px;">⚠️ Haalt GEEN torens weg</div>`;
  }

  // Passive description section for active ultimates
  if(tw.ultimate){
    if(tw.key==='speer'){
      const activeBoost = tw.speerRangeBoostUntil && Date.now() < tw.speerRangeBoostUntil;
@@ -783,10 +802,12 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>

  if(t2.ultimate){
    if(t2.key==='tsjaadinator'&&!t2.secret){
      // CHANGED: Now costs 300000, and does NOT remove other towers
      const sCost=300000;
      if(money<sCost) return;
      money-=sCost;
      const bonusMultiplier = 5.0;
      // NO tower removal - just empower the Tsjaadinator
      const bonusMultiplier = 5.0; // Fixed large bonus since no removal mechanic
      t2.secretDmgBonus = bonusMultiplier;
      t2.secret=true; t2.level=5;
      t2.upText=200; playSound('upgrade');
@@ -801,9 +822,11 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>

  if(t2.key==='atoom'){ t2.dmg*=3.8; t2.rate*=0.55; t2.nukeTimer=0; t2.fireBonusMultiplier=(t2.fireBonusMultiplier||1.20)+0.10; }
  else if(t2.key==='tsjaadinator'){ t2.dmg*=2; t2.rate*=0.25; }
  // UPDATED: speer ultimate also buffs nearby towers range
  else if(t2.key==='speer'){ t2.dmg*=3; t2.rate*=1.2; t2.speerRangeBoostUntil=0; }
  else if(t2.key==='geweer'){ t2.dmg=10; t2.rate*=0.45; }
  else if(t2.key==='boog'){ t2.dmg*=1.9; t2.rate*=0.50; t2.poisonArrows=true; }
  // UPDATED: sniper ultimate enables slow on hit
  else if(t2.key==='sniper'){ t2.dmg=5000; t2.sniperSlowOnHit=true; }
  else if(t2.key==='plaagdokter'){ t2.dmg*=4; t2.slowDuration=999999; t2.plaagDmgBonus=(t2.plaagDmgBonus||1.05)+0.05; }
  else if(t2.key==='aap'){ t2.dmg*=2; }
@@ -835,6 +858,7 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
  if(gameMode==='plaag') baseEnemies=Math.floor(10+round*2.5);
  else if(gameMode==='hard') baseEnemies=Math.floor(7+round*2.5);
  else if(gameMode==='speed') baseEnemies=Math.floor(5+round*1.8);
  else if(gameMode==='armoede') baseEnemies=Math.floor(5+round*1.8);
  else if(gameMode==='mutatie') baseEnemies=Math.floor(6+round*2);
  else if(gameMode==='dubbelhealth') baseEnemies=Math.floor(5+round*1.8);
  else if(gameMode==='tsjaadmodus') baseEnemies=Math.floor(8+round*2.5);
@@ -845,7 +869,7 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
}

function getMaxRound(){
  if(gameMode==='standard'||gameMode==='speed'||gameMode==='dubbelhealth') return 30;
  if(gameMode==='standard'||gameMode==='speed'||gameMode==='armoede'||gameMode==='dubbelhealth') return 30;
  if(gameMode==='hard'||gameMode==='tsjaadmodus') return 50;
  if(gameMode==='boss') return 1;
  if(gameMode==='mutatie') return 35;
@@ -884,9 +908,10 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>

  if(round===maxRound){
    if(gameMode==='mutatie'){ enemies.push(makeEnemy({...hydraHydraBossType})); return; }
    if(gameMode==='standard'||gameMode==='speed'||gameMode==='dubbelhealth'){ enemies.push(makeEnemy({...bossType})); return; }
    if(gameMode==='standard'||gameMode==='speed'||gameMode==='armoede'){ enemies.push(makeEnemy({...bossType})); return; }
    if(gameMode==='hard'){ enemies.push(makeEnemy({...mutatedBossType})); return; }
    if(gameMode==='boss'){ enemies.push(makeEnemy({...slowBossType})); return; }
    if(gameMode==='dubbelhealth'){ enemies.push(makeEnemy({...bossType})); return; }
    if(gameMode==='tsjaadmodus'){ enemies.push(makeEnemy({...mutatedBossType})); return; }
    if(gameMode==='tsjaadplus'){ enemies.push(makeEnemy({...mutatedBossType})); return; }
  }
@@ -1011,8 +1036,10 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
    }
  }

  // Update bird eggs
  for(const egg of birdEggs){ egg.timer--; }

  // Bird wind aura
  for(const bird of enemies){
    if(!bird.isBird || bird.hp <= 0) continue;
    const radius = bird.windRadius || 80;
@@ -1091,6 +1118,7 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
    if(tw.boosted&&tw.boostEndTime>0){ tw.boostEndTime--; if(tw.boostEndTime<=0) tw.boosted=false; }
  }

  // Egg hatching
  const eggsToHatch = birdEggs.filter(e=>e.timer<=0&&!e.destroyed);
  for(const egg of eggsToHatch){
    const childBird = makeEnemy({...animalTypes.find(a=>a.type==='vogel'), hp: Math.floor(animalTypes.find(a=>a.type==='vogel').hp*(1+round*0.14)), speed: 1.4*(1+round*0.02), reward:15});
@@ -1104,6 +1132,7 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
    enemies.push(childBird);
  }

  // Handle projectile/egg collision
  for(const p of projectiles){
    for(let ei=0;ei<birdEggs.length;ei++){
      const egg = birdEggs[ei];
@@ -1153,6 +1182,7 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
      if(tw.key==='tsjaadinator'&&tw.secret){ if((e.mutation==='kogelvrije'||e.mutation2==='kogelvrije')) return false; return true; }
      if(Math.hypot(e.x-tw.x,e.y-tw.y)>=effectiveRange) return false;
      if(e.isRoboLeeuw && (tw.key==='geweer'||tw.key==='sniper')) return false;
      // Krokodil: immune to sniper and soldier (thick scales)
      if(e.isKrokodil && (tw.key==='geweer'||tw.key==='sniper')) return false;
      if((e.mutation==='metalen'||e.mutation2==='metalen')&&tw.key!=='atoom') return false;
      if((e.mutation==='kogelvrije'||e.mutation2==='kogelvrije')&&(tw.key==='geweer'||tw.key==='sniper')) return false;
@@ -1176,7 +1206,9 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
      fire:tw.fire,
      fireBurnDmg: tw.fire ? (tw.ultimate ? 80 : 1) : 0,
      poisonArrow: tw.key==='boog' && tw.poisonArrows,
      // NEW: pass sniper slow flag
      sniperSlowOnHit: tw.key==='sniper' && tw.sniperSlowOnHit,
      // NEW: pass speer ultimate aura flag
      speerUltAura: tw.key==='speer' && tw.ultimate,
      speerTower: tw.key==='speer' ? tw : null,
    });
@@ -1203,27 +1235,33 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
        p.target.burning=true; p.target.burnDuration=480; p.target.burnTickTimer=0;
        p.target.burnDamagePerSec=Math.max(p.target.burnDamagePerSec||0, p.fireBurnDmg);
      }
      // NEW: Sniper ultimate slow on hit (50% speed for 0.3s = 18 frames)
      if(p.sniperSlowOnHit && p.target.hp > 0){
        const slowFactor = 0.5;
        // Only apply if not already slowed more
        if(!p.target.sniperSlowed){
          p.target.sniperSlowedPrevSpeed = p.target.speed;
          p.target.sniperSlowedPrevBaseSpeed = p.target.baseSpeed;
          p.target.speed *= slowFactor;
          p.target.baseSpeed *= slowFactor;
          p.target.sniperSlowed = true;
        }
        p.target.sniperSlowEndTime = 18;
        p.target.sniperSlowEndTime = 18; // 0.3s at 60fps
      }
      // NEW: Speer ultimate - give nearby towers +30% range for 3 seconds on shot hit
      if(p.speerUltAura && p.speerTower){
        const spTw = p.speerTower;
        const auraRange = getTowerRange(spTw);
        const boostUntil = Date.now() + 3000;
        const boostUntil = Date.now() + 3000; // 3 seconds
        for(const other of towers){
          if(Math.hypot(other.x-spTw.x,other.y-spTw.y) <= auraRange){
            other.speerRangeBoostUntil = Math.max(other.speerRangeBoostUntil||0, boostUntil);
          }
        }
      }
      if(p.bomb) explosions.push({x:p.target.x,y:p.target.y,r:12,t:22,gold:p.gold});
      if(p.secret&&p.towerKey==='tsjaadinator'){
        explosions.push({x:p.target.x,y:p.target.y,r:5,t:20,gold:true,subtle:true});
@@ -1233,10 +1271,12 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
    } else { p.x+=dx/d*p.speed; p.y+=dy/d*p.speed; }
  }

  // Update sniper slow timers
  for(const e of enemies){
    if(e.sniperSlowed && e.sniperSlowEndTime > 0){
      e.sniperSlowEndTime--;
      if(e.sniperSlowEndTime <= 0){
        // Restore speed
        e.speed = e.sniperSlowedPrevSpeed || e.baseSpeed;
        e.baseSpeed = e.sniperSlowedPrevBaseSpeed || e.baseSpeed;
        e.sniperSlowed = false;
@@ -1253,7 +1293,7 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
      if(e.boss){ winGame(); return false; }

      const hasOnstabiel = e.mutation==='onstabiele' || e.mutation2==='onstabiele';
      if(hasOnstabiel && !e.onstabielExploded){ }
      if(hasOnstabiel && !e.onstabielExploded){ /* killed early, no explosion */ }

      if(e.mutation==='radioactieve'||e.mutation2==='radioactieve'){ triggerEnemyNuclearExplosion(e, false); }
      if(e.isRoboLeeuw){ triggerEnemyNuclearExplosion(e, false); }
@@ -1376,6 +1416,12 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
    ctx.beginPath(); ctx.moveTo(path[0].x,path[0].y); for(const p of path) ctx.lineTo(p.x,p.y); ctx.stroke();
    ctx.strokeStyle='#ffeb3b'; ctx.lineWidth=3; ctx.setLineDash([15,10]);
    ctx.beginPath(); ctx.moveTo(path[0].x,path[0].y); for(const p of path) ctx.lineTo(p.x,p.y); ctx.stroke(); ctx.setLineDash([]);
  } else if(gameMode==='armoede'){
    const gradient=ctx.createLinearGradient(0,0,canvas.width,canvas.height);
    gradient.addColorStop(0,'#3a3a3a'); gradient.addColorStop(0.5,'#2a2a2a'); gradient.addColorStop(1,'#1a1a1a');
    ctx.fillStyle=gradient; ctx.fillRect(0,0,canvas.width,canvas.height);
    ctx.strokeStyle='#666'; ctx.lineWidth=26; ctx.lineCap='round';
    ctx.beginPath(); ctx.moveTo(path[0].x,path[0].y); for(const p of path) ctx.lineTo(p.x,p.y); ctx.stroke();
  } else if(gameMode==='boss'){
    const gradient=ctx.createLinearGradient(0,0,canvas.width,canvas.height);
    gradient.addColorStop(0,'#2a0a0a'); gradient.addColorStop(0.5,'#440000'); gradient.addColorStop(1,'#2a0a0a');
@@ -1515,6 +1561,7 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
    if(mutation==='beschermde'&&e.beschermdActive){ ctx.strokeStyle='rgba(255,255,255,0.9)'; ctx.lineWidth=4; ctx.shadowBlur=15; ctx.shadowColor='#fff'; ctx.beginPath(); ctx.arc(0,0,e.size+6,0,Math.PI*2); ctx.stroke(); ctx.fillStyle='rgba(255,255,255,0.15)'; ctx.beginPath(); ctx.arc(0,0,e.size+6,0,Math.PI*2); ctx.fill(); ctx.shadowBlur=0; }
  }
  if(e.slowEndTime>0){ ctx.strokeStyle='#9333ea'; ctx.lineWidth=2; ctx.globalAlpha=0.5; ctx.beginPath(); ctx.arc(0,0,e.size+3,0,Math.PI*2); ctx.stroke(); ctx.globalAlpha=1; }
  // Sniper slow indicator
  if(e.sniperSlowed && e.sniperSlowEndTime > 0){
    ctx.strokeStyle='rgba(150,220,255,0.9)'; ctx.lineWidth=3;
    ctx.shadowBlur=8; ctx.shadowColor='#88ccff';
@@ -1603,6 +1650,7 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
  }
  if(e.burning&&e.burnDuration>0){ ctx.fillStyle='rgba(255,120,0,0.9)'; ctx.font='bold 8px Arial'; ctx.fillText('🔥'+(e.burnDamagePerSec||0).toFixed(1)+'/s',0,-48); }
  if(e.poisoned&&e.poisonTimer>0){ ctx.fillStyle='rgba(0,255,80,0.95)'; ctx.font='bold 8px Arial'; ctx.fillText('☠️10/s',e.burning?22:0,-48); }
  // Sniper slow
  if(e.sniperSlowed&&e.sniperSlowEndTime>0){ ctx.fillStyle='rgba(150,220,255,0.95)'; ctx.font='bold 8px Arial'; ctx.fillText('❄️-50%',0,-56); }
  const hasOnstabiel = e.mutation==='onstabiele'||e.mutation2==='onstabiele';
  if(hasOnstabiel&&!e.onstabielExploded&&e.onstabielTimer>0){
@@ -1612,6 +1660,7 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
    ctx.fillText('💥'+secsLeft+'s',0,-64);
  }
  if(e.plaagDebuffed){ ctx.fillStyle='rgba(233,30,99,0.8)'; ctx.font='7px Arial'; ctx.fillText('💉',barW/2+4,-24); }
  // Krokodil: show immunity indicator under name
  if(e.isKrokodil){ ctx.fillStyle='rgba(255,215,0,0.9)'; ctx.font='bold 7px Arial'; ctx.textAlign='center'; ctx.fillText('🔫❌🎯❌',-barW/2+barW*0.5,-37); }
}

@@ -1626,8 +1675,10 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
  const bodyCol = e.infected ? '#2a4a1a' : '#2d6a2d';
  const scaleCol = e.infected ? '#1a3a0a' : '#1e4d1e';
  const bellyCol = e.infected ? '#4a6a2a' : '#7aaa4a';
  // Body
  ctx.fillStyle = bodyCol;
  ctx.beginPath(); ctx.ellipse(0, 2, 20, 10, 0, 0, Math.PI*2); ctx.fill();
  // Back ridge spines
  ctx.fillStyle = scaleCol;
  for(let si = -3; si <= 3; si++){
    const sx = si * 5;
@@ -1638,22 +1689,31 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
    const sx=si*5;
    ctx.beginPath(); ctx.moveTo(sx-3,-6); ctx.lineTo(sx,-13); ctx.lineTo(sx+3,-6); ctx.stroke();
  }
  // Belly
  ctx.fillStyle = bellyCol;
  ctx.beginPath(); ctx.ellipse(0, 6, 16, 5, 0, 0, Math.PI*2); ctx.fill();
  // Head - flat snout
  ctx.fillStyle = bodyCol;
  ctx.beginPath(); ctx.moveTo(14,-4); ctx.lineTo(26,-2); ctx.lineTo(28,2); ctx.lineTo(26,4); ctx.lineTo(14,6); ctx.closePath(); ctx.fill();
  // Teeth
  ctx.fillStyle = '#f0f0e0';
  ctx.fillRect(20,-2,2,3); ctx.fillRect(24,-1,2,3); ctx.fillRect(18,3,2,2); ctx.fillRect(22,3,2,2);
  // Eye - slit pupil
  ctx.fillStyle='#d4aa00'; ctx.beginPath(); ctx.ellipse(16,-3,3,2,0,0,Math.PI*2); ctx.fill();
  ctx.fillStyle='#111'; ctx.beginPath(); ctx.ellipse(16,-3,1,2,0,0,Math.PI*2); ctx.fill();
  // Nostril
  ctx.fillStyle='#1a4a1a'; ctx.beginPath(); ctx.arc(25,0,1.2,0,Math.PI*2); ctx.fill();
  // Legs
  ctx.fillStyle = scaleCol;
  ctx.fillRect(-16,8,5,8); ctx.fillRect(-6,9,5,7); ctx.fillRect(4,9,5,7); ctx.fillRect(14,8,5,8);
  // Tail
  ctx.strokeStyle=bodyCol; ctx.lineWidth=7; ctx.lineCap='round';
  ctx.beginPath(); ctx.moveTo(-20,2); ctx.quadraticCurveTo(-28,0,-30,6); ctx.stroke();
  ctx.lineWidth=4; ctx.beginPath(); ctx.moveTo(-28,1); ctx.lineTo(-36,5); ctx.stroke();
  // Tail spines
  ctx.strokeStyle=scaleCol; ctx.lineWidth=1;
  for(let ri=0;ri<4;ri++){ const rx=-20-ri*4; ctx.beginPath(); ctx.moveTo(rx,-1); ctx.lineTo(rx+1,-5); ctx.lineTo(rx+2,-1); ctx.stroke(); }
  // Immunity shield indicator
  ctx.fillStyle='rgba(255,215,0,0.9)'; ctx.font='bold 9px Arial'; ctx.textAlign='center';
  ctx.fillText('🛡️',0,-20);
}
@@ -1675,6 +1735,7 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
    ctx.beginPath(); ctx.arc(0,0,effRange,0,Math.PI*2); ctx.stroke(); ctx.setLineDash([]);
  }

  // NEW: Show speer range boost aura circle when active
  if(tw.key==='speer' && tw.ultimate && tw.speerRangeBoostUntil && Date.now() < tw.speerRangeBoostUntil){
    const effRange = getTowerRange(tw) / scale;
    const timeLeft = tw.speerRangeBoostUntil - Date.now();
@@ -1718,6 +1779,7 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
function drawFakkelTower(tw){ ctx.fillStyle=tw.ultimate?'#ff6b35':'#8b4513'; ctx.fillRect(-8,-10,16,20); ctx.fillStyle='#d2b48c'; ctx.beginPath(); ctx.arc(0,-12,6,0,Math.PI*2); ctx.fill(); ctx.fillStyle=tw.ultimate?'#ff4500':'#8b7355'; ctx.fillRect(8,-8,3,12); ctx.fillStyle=tw.ultimate?'#ff0000':'#ff8800'; ctx.beginPath(); ctx.moveTo(9.5,-10); ctx.lineTo(7,-16); ctx.lineTo(9.5,-14); ctx.lineTo(12,-16); ctx.closePath(); ctx.fill(); if(tw.level>=2){ ctx.fillStyle='#ffeb3b'; ctx.beginPath(); ctx.arc(9.5,-13,2,0,Math.PI*2); ctx.fill(); } if(tw.level>=3){ ctx.fillStyle='#ff4500'; ctx.beginPath(); ctx.moveTo(9.5,-16); ctx.lineTo(6,-22); ctx.lineTo(9.5,-19); ctx.lineTo(13,-22); ctx.closePath(); ctx.fill(); } if(tw.ultimate){ ctx.strokeStyle='#ff0000'; ctx.lineWidth=2; ctx.globalAlpha=0.7; ctx.beginPath(); ctx.arc(0,0,15,0,Math.PI*2); ctx.stroke(); ctx.globalAlpha=1; ctx.fillStyle='rgba(255,50,0,0.8)'; ctx.beginPath(); ctx.moveTo(9.5,-20); ctx.lineTo(5,-30); ctx.lineTo(9.5,-26); ctx.lineTo(14,-30); ctx.closePath(); ctx.fill(); } }

function drawSpeerTower(tw){
  // Draw range aura effect when boosted (pulsing purple glow for ultimate)
  if(tw.ultimate && tw.speerRangeBoostUntil && Date.now() < tw.speerRangeBoostUntil){
    ctx.fillStyle='rgba(180,150,255,0.25)'; ctx.beginPath(); ctx.arc(0,0,14,0,Math.PI*2); ctx.fill();
  }
@@ -1727,6 +1789,7 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
  ctx.fillStyle=tw.ultimate?'#dcd6f7':'#ccc'; ctx.beginPath(); ctx.moveTo(12,0); ctx.lineTo(6,-4); ctx.lineTo(6,4); ctx.fill();
  if(tw.level>=2){ ctx.strokeStyle='#e0e0e0'; ctx.lineWidth=2; ctx.beginPath(); ctx.moveTo(-8,-6); ctx.lineTo(8,-6); ctx.stroke(); ctx.fillStyle='#ccc'; ctx.beginPath(); ctx.moveTo(8,-6); ctx.lineTo(4,-9); ctx.lineTo(4,-3); ctx.fill(); }
  if(tw.level>=3){ ctx.strokeStyle='#e0e0e0'; ctx.lineWidth=2; ctx.beginPath(); ctx.moveTo(-8,6); ctx.lineTo(8,6); ctx.stroke(); ctx.fillStyle='#ccc'; ctx.beginPath(); ctx.moveTo(8,6); ctx.lineTo(4,3); ctx.lineTo(4,9); ctx.fill(); }
  // Ultimate: extra radiant rings
  if(tw.ultimate){
    ctx.strokeStyle='rgba(180,150,255,0.5)'; ctx.lineWidth=1.5;
    ctx.beginPath(); ctx.arc(0,0,11,0,Math.PI*2); ctx.stroke();
@@ -1745,36 +1808,14 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
  if(tw.level>=3){ ctx.fillStyle=tw.ultimate?'#ffd700':'#78909c'; ctx.fillRect(-7,6,3,6); ctx.fillRect(4,6,3,6); }
  if(tw.ultimate){
    ctx.strokeStyle='#00e5ff'; ctx.lineWidth=2; ctx.globalAlpha=0.7; ctx.strokeRect(-8,-7,16,14); ctx.globalAlpha=1;
    // Sniper ultimate: ice/frost ring indicating slow ability
    ctx.strokeStyle='rgba(150,220,255,0.5)'; ctx.lineWidth=1.5; ctx.setLineDash([3,2]);
    ctx.beginPath(); ctx.arc(0,0,14,0,Math.PI*2); ctx.stroke(); ctx.setLineDash([]);
  }
}

function drawAtoomTower(tw){ ctx.fillStyle=tw.ultimate?'#e74c3c':'#4caf50'; ctx.beginPath(); ctx.arc(0,0,10,0,Math.PI*2); ctx.fill(); ctx.fillStyle=tw.ultimate?'#e67e22':'#b2ffb2'; ctx.beginPath(); ctx.arc(0,0,5,0,Math.PI*2); ctx.fill(); const symbols=tw.level>=3?4:3; ctx.strokeStyle='#000'; ctx.lineWidth=2; for(let i=0;i<symbols;i++){ ctx.save(); ctx.rotate(i*Math.PI*2/symbols); ctx.beginPath(); ctx.moveTo(0,0); ctx.lineTo(0,-8); ctx.stroke(); ctx.restore(); } if(tw.level>=3){ ctx.fillStyle='#76ff03'; ctx.beginPath(); ctx.arc(0,0,3,0,Math.PI*2); ctx.fill(); } }
// Fabriek (previously Katoen)
function drawKatoenTower(tw){
  // Draw as factory instead of cotton field
  ctx.fillStyle=tw.ultimate?'#555':'#444'; ctx.fillRect(-12,-12,24,18); // main building
  ctx.fillStyle=tw.ultimate?'#888':'#666'; ctx.fillRect(-10,-12,6,6); // window left
  ctx.fillStyle=tw.ultimate?'#888':'#666'; ctx.fillRect(4,-12,6,6); // window right
  // Smokestacks
  ctx.fillStyle=tw.ultimate?'#cc3300':'#8b4513';
  ctx.fillRect(-8,-22,5,12);
  ctx.fillRect(3,-26,5,16);
  // Smoke puffs
  const t_sm = Date.now()*0.003;
  ctx.fillStyle=`rgba(200,200,200,${0.4+Math.sin(t_sm)*0.2})`;
  ctx.beginPath(); ctx.arc(-5.5,-24+Math.sin(t_sm)*3,4,0,Math.PI*2); ctx.fill();
  ctx.beginPath(); ctx.arc(5.5,-28+Math.sin(t_sm+1)*3,5,0,Math.PI*2); ctx.fill();
  // Door
  ctx.fillStyle=tw.ultimate?'#ffd700':'#8b6914'; ctx.fillRect(-3,0,6,6);
  if(tw.ultimate){
    ctx.strokeStyle='#ffd700'; ctx.lineWidth=2; ctx.globalAlpha=0.6;
    ctx.beginPath(); ctx.arc(0,0,16,0,Math.PI*2); ctx.stroke(); ctx.globalAlpha=1;
  }
}
function drawKatoenTower(tw){ ctx.fillStyle=tw.ultimate?'#27ae60':'#e8e2b8'; ctx.fillRect(-12,-12,24,24); ctx.fillStyle=tw.ultimate?'#2ecc71':'#fff'; ctx.beginPath(); ctx.arc(0,0,7,0,Math.PI*2); ctx.fill(); const bollen=[[0,0],[-4,-4],[4,-4],[4,4],[-4,4]]; for(let i=1;i<=tw.level&&i<bollen.length;i++){ ctx.beginPath(); ctx.arc(bollen[i][0],bollen[i][1],3,0,Math.PI*2); ctx.fill(); } }
function drawTsjaadinator(tw){
  if(tw.secret){
    const t_now=Date.now()*0.002;
@@ -1836,6 +1877,7 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>
      ctx.beginPath(); ctx.moveTo(-4,0); ctx.quadraticCurveTo(0,-5,8,-2); ctx.quadraticCurveTo(12,0,8,2); ctx.quadraticCurveTo(0,5,-4,0); ctx.fill(); ctx.shadowBlur=0;
    } else if(p.towerKey==='plaagdokter'){ ctx.strokeStyle=p.gold?'#ffd700':'#e91e63'; ctx.fillStyle=p.gold?'#ffd700':'#f8bbd0'; ctx.lineWidth=2; ctx.beginPath(); ctx.moveTo(-6,0); ctx.lineTo(6,0); ctx.stroke(); ctx.fillStyle=p.gold?'#ffd700':'#e91e63'; ctx.beginPath(); ctx.moveTo(6,0); ctx.lineTo(9,-2); ctx.lineTo(9,2); ctx.closePath(); ctx.fill(); ctx.fillRect(-8,-1,3,2); }
    else if(p.towerKey==='sniper'){
      // Sniper ultimate projectile has ice/blue tint
      ctx.fillStyle=p.sniperSlowOnHit?'rgba(150,220,255,0.95)':(p.gold?'#ffd700':'#ffeb3b');
      ctx.beginPath(); ctx.ellipse(0,0,4,1.5,0,0,Math.PI*2); ctx.fill();
      if(p.sniperSlowOnHit){ ctx.shadowBlur=6; ctx.shadowColor='#88ddff'; ctx.strokeStyle='rgba(100,200,255,0.8)'; ctx.lineWidth=1; ctx.beginPath(); ctx.ellipse(0,0,4,1.5,0,0,Math.PI*2); ctx.stroke(); ctx.shadowBlur=0; }
@@ -1930,8 +1972,8 @@ <h2 id="gameTitle">🛡️ Tsjaad TD</h2>

function loop(){ update(); draw(); if(!gameWon) requestAnimationFrame(loop); }

console.log('🏜️ Tsjaad TD – Updated Edition 🐪');
console.log('CHANGES: Armoede Modus removed | Katoen Plantage → Fabriek | All bosses → Ultra Mug');
console.log('🏜️ Tsjaad TD – Ultimate Edition v4 🐪');
console.log('UPDATES: Speer Ultimate +30% range aura on shot | Sniper Ultimate 50% slow 0.3s on hit | Secret Tsjaadinator €300k (no tower removal) | UI tooltips updated');
</script>
</body>
</html>
0 commit comments
Comments
0
 (0)
Please sign in to comment.
There are no files selected for viewing
