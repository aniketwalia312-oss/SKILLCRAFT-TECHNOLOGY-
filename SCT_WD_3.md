# SKILLCRAFT-TECHNOLOGY-
                                             TASK-3(GAME): TIC-TAC-TOE
My third task is also completed as a web developer intern at skillcraft technology and this time, I develop a game called tic-tac-toe and with cool feature and grphic animations wchich really seems to be cool and I generally learnt a lot of new things and how to use the promts and ai productively. this internship help me on working my skills and I gained experience with it ...
                                                    
                                                      QUESTION:
Build a tic-tac-toe web application against each other or Computer.
Implement functions to handle user clicks, track game state, and check for winning conditions, you can create an interactive and engaging tic-tac-toe game.
                                                    
                                                  CODE AND EXICUTION:
FILE: [index.html](https://github.com/user-attachments/files/29339081/index.html)

FOR LIVE VIEW AND MOBILE: https://tic-tac-toe-gc.netlify.app/

CODE:
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="NexusToe - A premium, visually stunning Tic-Tac-Toe game with dual grid sizes, advanced AI levels (including Minimax), customizable retro/neon themes, retro synthesized sound effects, and session statistics.">
    <title>Tic-Tac-Toe | Premium Grid Clash</title>
    
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;600;900&family=Outfit:wght@300;400;600;800&family=Inter:wght@300;400;600&display=swap" rel="stylesheet">
    
    <!-- FontAwesome for Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <!-- CSS Style Sheets -->
    <link rel="stylesheet" href="style.css">
</head>
<body class="theme-cyberpunk">
    <!-- Particle Background Canvas -->
    <canvas id="bg-canvas"></canvas>
    
    <!-- App Container -->
    <div class="app-container">
        
        <!-- Header -->
        <header class="game-header">
            <div class="logo-area">
                <i class="fa-solid fa-gamepad logo-icon"></i>
                <h1>TIC-TAC-<span>TOE</span></h1>
            </div>
            <p class="subtitle">Quantum Grid Battleground</p>
        </header>

        <!-- Main Dashboard Layout -->
        <main class="dashboard">
            
            <!-- Sidebar: Controls & Settings -->
            <section class="control-panel glass-panel">
                <h2 class="panel-title"><i class="fa-solid fa-sliders"></i> System Config</h2>
                
                <div class="control-group">
                    <label for="game-mode">Game Mode</label>
                    <div class="custom-select-wrapper">
                        <select id="game-mode">
                            <option value="pve" selected>Player vs AI</option>
                            <option value="pvp">Player vs Player (Local)</option>
                        </select>
                    </div>
                </div>

                <div class="control-group" id="difficulty-group">
                    <label for="ai-difficulty">AI Intelligence</label>
                    <div class="custom-select-wrapper">
                        <select id="ai-difficulty">
                            <option value="easy">Easy (Novice)</option>
                            <option value="medium">Medium (Adept)</option>
                            <option value="impossible" selected>Impossible (Minimax)</option>
                        </select>
                    </div>
                </div>

                <div class="control-group">
                    <label for="board-size">Grid Protocol</label>
                    <div class="toggle-buttons" id="board-size-toggle">
                        <button class="toggle-btn active" data-size="3">3 x 3 (Classic)</button>
                        <button class="toggle-btn" data-size="5">5 x 5 (Mega)</button>
                    </div>
                </div>

                <div class="control-group">
                    <label for="theme-select">Visual Matrix</label>
                    <div class="theme-grid">
                        <button class="theme-selector-btn active" data-theme="cyberpunk" title="Cyberpunk Neon">
                            <span class="color-dot bg-cyan-pink"></span> Cyberpunk
                        </button>
                        <button class="theme-selector-btn" data-theme="synthwave" title="Synthwave Sunset">
                            <span class="color-dot bg-orange-purple"></span> Synthwave
                        </button>
                        <button class="theme-selector-btn" data-theme="slate" title="Sleek Slate">
                            <span class="color-dot bg-emerald-slate"></span> Slate
                        </button>
                    </div>
                </div>

                <div class="control-group audio-control">
                    <div class="flex-between">
                        <span>Synthesized Sound</span>
                        <button id="sound-toggle" class="icon-toggle-btn active" aria-label="Toggle sound">
                            <i class="fa-solid fa-volume-high"></i>
                        </button>
                    </div>
                </div>

                <div class="actions-group">
                    <button id="btn-undo" class="secondary-btn" disabled>
                        <i class="fa-solid fa-rotate-left"></i> Undo Move
                    </button>
                    <button id="btn-restart" class="primary-btn">
                        <i class="fa-solid fa-arrows-rotate"></i> Reset Board
                    </button>
                    <button id="btn-reset-scores" class="danger-btn">
                        <i class="fa-solid fa-trash-can"></i> Clear Scores
                    </button>
                </div>
            </section>

            <!-- Center Panel: The Game Area -->
            <section class="game-area">
                <!-- Status Bar -->
                <div class="status-bar glass-panel">
                    <div class="status-indicator">
                        <span id="turn-badge" class="badge turn-x">❌ X Turn</span>
                    </div>
                    <div class="game-status-message" id="game-status">
                        Awaiting your move. Make it count.
                    </div>
                </div>

                <!-- Board Container -->
                <div class="board-outer-container glass-panel">
                    <!-- Overlay SVG for Line Drawing on Win -->
                    <svg id="winning-line-svg" viewBox="0 0 100 100" preserveAspectRatio="none">
                        <line id="winning-line" x1="0" y1="0" x2="0" y2="0" />
                    </svg>
                    
                    <div id="game-board" class="board-grid board-3x3">
                        <!-- Grid cells will be generated programmatically by JavaScript -->
                    </div>
                </div>

                <!-- Bottom Scoreboard -->
                <div class="scoreboard glass-panel">
                    <div class="score-card player-x-card active">
                        <div class="player-icon-wrapper font-x">❌</div>
                        <div class="player-details">
                            <input type="text" id="player-x-name" class="player-name-input" value="Player 1">
                            <span class="score-val" id="score-x">0</span>
                        </div>
                    </div>
                    <div class="score-card tie-card">
                        <div class="player-icon-wrapper"><i class="fa-solid fa-scale-balanced"></i></div>
                        <div class="player-details">
                            <span class="player-name-label">Draws</span>
                            <span class="score-val" id="score-ties">0</span>
                        </div>
                    </div>
                    <div class="score-card player-o-card">
                        <div class="player-icon-wrapper font-o">⭕</div>
                        <div class="player-details">
                            <input type="text" id="player-o-name" class="player-name-input" value="AI Opponent">
                            <span class="score-val" id="score-o">0</span>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Sidebar Right: Analytics & Logs -->
            <section class="analytics-panel glass-panel">
                <div class="tabs-header">
                    <button class="tab-btn active" data-tab="log"><i class="fa-solid fa-list-check"></i> Battle Log</button>
                    <button class="tab-btn" data-tab="rules"><i class="fa-solid fa-circle-info"></i> Rules & Intel</button>
                </div>
                
                <div class="tab-content" id="tab-log">
                    <div class="history-list" id="battle-log">
                        <div class="log-entry system-entry">System online. Selecting Cyberpunk protocol...</div>
                        <div class="log-entry system-entry">3x3 Grid mode initialized. Rule: 3 in a row wins.</div>
                    </div>
                </div>
                
                <div class="tab-content hidden" id="tab-rules">
                    <div class="rules-container">
                        <h3>Game Mechanics</h3>
                        <p>NexusToe operates on two grid protocols:</p>
                        
                        <div class="rule-section">
                            <h4><i class="fa-solid fa-border-all"></i> 3x3 Classic</h4>
                            <ul>
                                <li>Traditional gameplay.</li>
                                <li>Goal: Align <strong>3 matching symbols</strong> horizontally, vertically, or diagonally.</li>
                                <li>Minimax AI is active on this mode and will play optimally.</li>
                            </ul>
                        </div>

                        <div class="rule-section">
                            <h4><i class="fa-solid fa-table-cells"></i> 5x5 Mega Grid</h4>
                            <ul>
                                <li>Expanded grid layout.</li>
                                <li>Goal: Align <strong>4 matching symbols</strong> horizontally, vertically, or diagonally.</li>
                                <li>The AI utilizes a fast alpha-beta search heuristic to check blocking moves and instant wins.</li>
                            </ul>
                        </div>

                        <div class="rule-section">
                            <h4><i class="fa-solid fa-lightbulb"></i> Tips</h4>
                            <ul>
                                <li>Double-click player names to rename them.</li>
                                <li>Use the <strong>Undo Move</strong> button to correct misclicks.</li>
                                <li>Toggle themes on the fly.</li>
                            </ul>
                        </div>
                    </div>
                </div>
            </section>
        </main>
        
        <!-- Footer -->
        <footer class="app-footer">
            <p>SkillCraft Technology alternative task - Developed with Visual Excellence &copy; 2026</p>
        </footer>
    </div>

    <!-- Modal for Victory/Tie Celebration -->
    <div id="game-over-modal" class="modal-overlay hidden">
        <div class="modal-content glass-panel">
            <h2 id="modal-title">VICTORY DETECTED</h2>
            <p id="modal-subtitle">Player X has breached the core defenses!</p>
            <div class="modal-actions">
                <button id="modal-btn-restart" class="primary-btn"><i class="fa-solid fa-play"></i> Fight Again</button>
            </div>
        </div>
    </div>

    <!-- JS Scripts -->
    <script src="app.js"></script>
</body>
</html>

                                                  
