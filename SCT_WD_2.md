
# SKILLCRAFT-TECHNOLOGY-

                                        TASK-2(STOP WATCH): FALCON DIVE
My second task is completed as a web developer intern at skillcraft technology and this time I develop a stop watch application and named as FALCON DIVE. This is with  reference to  the fastest animal on  earth and i.e. falcon bird, now in this application I add all the necessary features that are required in the stop watch and usefull too. 

                                                    QUESTION:
Create an interactive and user-friendly stopwatch web application. 
Implement functions for starting, pausing, and resetting the stopwatch, as well as tracking and displaying lap times, users can accurately measure and record time intervals.
                                                
                                              CODE AND EXICUTION:
FILE: [index.html](https://github.com/user-attachments/files/29338102/index.html)


FOR LIVE AND MOBILE VIEW: https://falcondivespeed.netlify.app/

CODE: 
    
   # FALCON DIVE

    /* ==========================================================================
       Falcon Dive - Single File Unified Stylesheet
       ========================================================================== */

    /* --------------------------------------------------------------------------
       1. Theme Configurations & Design System
       -------------------------------------------------------------------------- */

    :root {
      /* Fonts */
      --font-interface: 'Outfit', sans-serif;
      --font-digital: 'Orbitron', monospace;
      --font-mono: 'JetBrains Mono', monospace;
    }

    /* Theme: Falcon Dive (Default - Peregrine Falcon) */
    .theme-falcon {
      --bg-app: #060911; /* Aerodynamic deep sky black */
      --bg-card: rgba(15, 23, 38, 0.65); /* Slate navy glass */
      --border-color: rgba(255, 255, 255, 0.08);
      --border-color-hover: rgba(251, 191, 36, 0.25); /* Gold glow border */
      --text-main: #f8fafc; /* Feather light white */
      --text-muted: #94a3b8; /* Muted slate */
      --text-glow-opacity: 0.7;
      
      --accent-color: #fbbf24; /* Falcon Yellow-Gold */
      --accent-secondary: #38bdf8; /* Aerodynamic Sky Blue */
      --accent-gradient: linear-gradient(135deg, #fbbf24 0%, #38bdf8 100%);
      --accent-glow: rgba(251, 191, 36, 0.4);
      
      --dial-bg-start: #111827;
      --dial-bg-end: #060911;
      --dial-border: rgba(251, 191, 36, 0.25);
      --dial-border-inner: rgba(56, 189, 248, 0.15);
      --subdial-bg: rgba(9, 12, 20, 0.5);
      
      --glass-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.45);
      --glass-blur: 16px;
      
      --color-fastest: #10b981;
      --color-slowest: #ef4444;
    }

    /* Theme: Cyberpunk */
    .theme-cyberpunk {
      --bg-app: #030008;
      --bg-card: rgba(18, 5, 26, 0.60);
      --border-color: rgba(255, 0, 127, 0.2);
      --border-color-hover: rgba(0, 242, 254, 0.4);
      --text-main: #00ffcc;
      --text-muted: #ff007f;
      --text-glow-opacity: 0.8;
      
      --accent-color: #ff007f; /* Neon Hot Pink */
      --accent-secondary: #00f2fe; /* Neon Cyan */
      --accent-gradient: linear-gradient(135deg, #ff007f 0%, #00f2fe 100%);
      --accent-glow: rgba(255, 0, 127, 0.5);
      
      --dial-bg-start: #1b0222;
      --dial-bg-end: #05000a;
      --dial-border: rgba(255, 0, 127, 0.3);
      --dial-border-inner: rgba(0, 242, 254, 0.15);
      --subdial-bg: rgba(5, 0, 10, 0.6);
      
      --glass-shadow: 0 8px 32px 0 rgba(255, 0, 127, 0.15);
      --glass-blur: 12px;
      
      --color-fastest: #00ffcc;
      --color-slowest: #f43f5e;
    }

    /* Theme: Emerald Luxury */
    .theme-emerald {
      --bg-app: #07100e;
      --bg-card: rgba(12, 24, 21, 0.70);
      --border-color: rgba(212, 175, 55, 0.15);
      --border-color-hover: rgba(212, 175, 55, 0.3);
      --text-main: #f0f7f4;
      --text-muted: #a3b899;
      --text-glow-opacity: 0.5;
      
      --accent-color: #d4af37; /* Warm Gold */
      --accent-secondary: #10b981; /* Emerald Green */
      --accent-gradient: linear-gradient(135deg, #d4af37 0%, #10b981 100%);
      --accent-glow: rgba(212, 175, 55, 0.3);
      
      --dial-bg-start: #0f221c;
      --dial-bg-end: #050b09;
      --dial-border: rgba(212, 175, 55, 0.25);
      --dial-border-inner: rgba(16, 185, 129, 0.1);
      --subdial-bg: rgba(5, 11, 9, 0.5);
      
      --glass-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.5);
      --glass-blur: 20px;
      
      --color-fastest: #34d399;
      --color-slowest: #ef4444;
    }

    /* Theme: Ice Light */
    .theme-light {
      --bg-app: #f1f5f9;
      --bg-card: rgba(255, 255, 255, 0.75);
      --border-color: rgba(15, 23, 42, 0.08);
      --border-color-hover: rgba(15, 23, 42, 0.15);
      --text-main: #0f172a;
      --text-muted: #64748b;
      --text-glow-opacity: 0.2;
      
      --accent-color: #3b82f6; /* Electric Blue */
      --accent-secondary: #0ea5e9; /* Light Blue */
      --accent-gradient: linear-gradient(135deg, #3b82f6 0%, #0ea5e9 100%);
      --accent-glow: rgba(59, 130, 246, 0.2);
      
      --dial-bg-start: #ffffff;
      --dial-bg-end: #e2e8f0;
      --dial-border: rgba(59, 130, 246, 0.3);
      --dial-border-inner: rgba(15, 23, 42, 0.05);
      --subdial-bg: rgba(226, 232, 240, 0.5);
      
      --glass-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.08);
      --glass-blur: 16px;
      
      --color-fastest: #10b981;
      --color-slowest: #ef4444;
    }

    /* --------------------------------------------------------------------------
       2. Reset & Layout Setup
       -------------------------------------------------------------------------- */

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      user-select: none;
      -webkit-user-select: none;
      -webkit-tap-highlight-color: transparent; /* Disable tap highlight on mobile */
    }

    body {
      font-family: var(--font-interface);
      background-color: var(--bg-app);
      color: var(--text-main);
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      overflow-x: hidden;
      position: relative;
      transition: background-color 0.5s ease, color 0.3s ease;
    }

    /* Backdrops & Glowing Accents */
    .dot-grid {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-image: radial-gradient(var(--border-color) 1.5px, transparent 1.5px);
      background-size: 24px 24px;
      opacity: 0.6;
      z-index: 1;
      pointer-events: none;
    }

    .radial-glow-1 {
      position: absolute;
      top: 10%;
      left: 15%;
      width: 350px;
      height: 350px;
      background: var(--accent-gradient);
      border-radius: 50%;
      filter: blur(140px);
      opacity: 0.12;
      z-index: 1;
      pointer-events: none;
      transition: background 0.5s ease;
    }

    .radial-glow-2 {
      position: absolute;
      bottom: 15%;
      right: 10%;
      width: 400px;
      height: 400px;
      background: var(--accent-secondary);
      border-radius: 50%;
      filter: blur(160px);
      opacity: 0.08;
      z-index: 1;
      pointer-events: none;
      transition: background 0.5s ease;
    }

    /* App Outer Container */
    .app-container {
      width: 100%;
      max-width: 1100px;
      margin: 16px;
      display: flex;
      flex-direction: column;
      gap: 16px;
      z-index: 5;
      position: relative;
    }

    /* --------------------------------------------------------------------------
       3. Glassmorphic UI Components
       -------------------------------------------------------------------------- */

    .glass-card {
      background: var(--bg-card);
      backdrop-filter: blur(var(--glass-blur));
      -webkit-backdrop-filter: blur(var(--glass-blur));
      border: 1px solid var(--border-color);
      border-radius: 20px;
      box-shadow: var(--glass-shadow);
      transition: background 0.4s ease, border-color 0.4s ease, box-shadow 0.4s ease;
    }

    /* Mobile active/hover compatibility */
    @media (hover: hover) {
      .glass-card:hover {
        border-color: var(--border-color-hover);
      }
    }

    /* Header Component */
    .app-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 14px 20px;
      background: var(--bg-card);
      backdrop-filter: blur(var(--glass-blur));
      -webkit-backdrop-filter: blur(var(--glass-blur));
      border: 1px solid var(--border-color);
      border-radius: 20px;
    }

    .brand {
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .logo-icon {
      color: var(--accent-color);
      display: flex;
      align-items: center;
      filter: drop-shadow(0 0 8px var(--accent-glow));
      animation: pulse-glow 3s infinite ease-in-out;
    }

    .brand-text h1 {
      font-size: 1.15rem;
      font-weight: 800;
      letter-spacing: 0.15rem;
      text-transform: uppercase;
      background: var(--accent-gradient);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    .brand-text .tagline {
      font-size: 0.6rem;
      font-weight: 700;
      letter-spacing: 0.3em;
      color: var(--text-muted);
    }

    .header-controls {
      display: flex;
      align-items: center;
      gap: 12px;
    }

    /* Buttons & Touch Target Sizing */
    .icon-btn, .theme-select-btn, .control-btn, .text-btn {
      touch-action: manipulation; /* Removes 300ms mobile tap delay */
    }

    .icon-btn {
      background: rgba(255, 255, 255, 0.04);
      border: 1px solid var(--border-color);
      color: var(--text-main);
      width: 44px; /* Enhanced mobile tap size */
      height: 44px;
      border-radius: 12px;
      cursor: pointer;
      display: flex;
      justify-content: center;
      align-items: center;
      transition: all 0.3s ease;
    }

    @media (hover: hover) {
      .icon-btn:hover {
        background: rgba(255, 255, 255, 0.08);
        border-color: var(--accent-color);
        color: var(--accent-color);
        transform: translateY(-2px);
      }
    }
    .icon-btn:active {
      transform: translateY(1px);
    }

    .icon-btn.muted {
      color: var(--text-muted);
      background: rgba(239, 68, 68, 0.1);
      border-color: rgba(239, 68, 68, 0.2);
    }

    .icon-btn.muted:hover {
      color: #ef4444;
      border-color: #ef4444;
    }

    /* Theme Dropdown */
    .theme-selector {
      position: relative;
    }

    .theme-select-btn {
      background: rgba(255, 255, 255, 0.04);
      border: 1px solid var(--border-color);
      color: var(--text-main);
      padding: 10px 14px;
      border-radius: 12px;
      cursor: pointer;
      display: flex;
      align-items: center;
      gap: 8px;
      font-family: var(--font-interface);
      font-size: 0.8rem;
      font-weight: 600;
      transition: all 0.3s ease;
    }

    @media (hover: hover) {
      .theme-select-btn:hover {
        background: rgba(255, 255, 255, 0.08);
        border-color: var(--accent-color);
      }
    }

    .theme-menu {
      position: absolute;
      top: calc(100% + 8px);
      right: 0;
      width: 160px;
      background: var(--bg-card);
      backdrop-filter: blur(24px);
      -webkit-backdrop-filter: blur(24px);
      border: 1px solid var(--border-color);
      border-radius: 14px;
      padding: 6px;
      display: none;
      flex-direction: column;
      gap: 4px;
      z-index: 100;
      box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.5);
    }

    .theme-menu.show {
      display: flex;
      animation: slide-down 0.25s cubic-bezier(0.16, 1, 0.3, 1) forwards;
    }

    .theme-option {
      display: flex;
      align-items: center;
      gap: 10px;
      padding: 8px 12px;
      font-size: 0.8rem;
      font-weight: 500;
      border-radius: 8px;
      cursor: pointer;
      color: var(--text-muted);
      transition: all 0.2s ease;
    }

    .theme-option:hover, .theme-option:active {
      background: rgba(255, 255, 255, 0.05);
      color: var(--text-main);
    }

    .theme-option.active {
      background: rgba(255, 255, 255, 0.08);
      color: var(--text-main);
      font-weight: 700;
    }

    .theme-option .dot {
      width: 8px;
      height: 8px;
      border-radius: 50%;
    }

    .falcon-dot { background-color: #fbbf24; }
    .cyberpunk-dot { background-color: #ff007f; }
    .emerald-dot { background-color: #d4af37; }
    .light-dot { background-color: #3b82f6; }

    /* --------------------------------------------------------------------------
       4. Main Content Panels Grid
       -------------------------------------------------------------------------- */

    .app-main {
      display: grid;
      grid-template-columns: 1.1fr 1.2fr;
      gap: 16px;
    }

    /* Left Column: Visual Stopwatch Panel */
    .visual-panel {
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 24px;
      position: relative;
      overflow: hidden;
    }

    .task-badge {
      position: absolute;
      top: 16px;
      left: 16px;
      font-size: 0.65rem;
      font-weight: 700;
      letter-spacing: 0.15em;
      color: var(--accent-color);
      padding: 4px 8px;
      border-radius: 6px;
      background: rgba(255, 255, 255, 0.03);
      border: 1px solid var(--border-color);
    }

    /* Chronograph Dial Scaling */
    .chronograph-container {
      position: relative;
      width: 100%;
      max-width: 270px;
      aspect-ratio: 1;
      height: auto;
      margin-top: 24px;
      margin-bottom: 20px;
      display: flex;
      justify-content: center;
      align-items: center;
    }

    .dial-glow {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      width: 85%;
      height: 85%;
      border-radius: 50%;
      box-shadow: 0 0 35px 5px var(--accent-glow);
      opacity: 0.12;
      pointer-events: none;
      transition: opacity 0.5s ease, box-shadow 0.5s ease;
    }

    /* Analog Sweep SVG Styling & Exact Center Rotation */
    .analog-dial {
      width: 100%;
      height: 100%;
    }

    .dial-ticks line {
      stroke: var(--text-muted);
      stroke-linecap: round;
      opacity: 0.25;
    }

    .dial-ticks line.major {
      stroke-width: 1.5;
      opacity: 0.65;
    }

    .dial-ticks text {
      fill: var(--text-main);
      font-family: var(--font-interface);
      font-size: 9px;
      font-weight: 700;
      text-anchor: middle;
      dominant-baseline: middle;
      opacity: 0.8;
    }

    .subdial-text {
      fill: var(--text-muted);
      font-family: var(--font-interface);
      font-size: 8px;
      font-weight: 600;
      text-anchor: middle;
      dominant-baseline: middle;
    }

    .dial-brand {
      fill: var(--text-muted);
      font-family: var(--font-interface);
      font-size: 7px;
      font-weight: 800;
      letter-spacing: 2.5px;
      opacity: 0.45;
    }

    .dial-chrono {
      fill: var(--text-muted);
      font-family: var(--font-interface);
      font-size: 7px;
      font-weight: 800;
      letter-spacing: 2.5px;
      opacity: 0.45;
    }

    /* Transform Origin Corrections for SVG Rotations */
    #mainNeedleGroup {
      transform-origin: 150px 150px;
      transform: rotate(var(--sec-rot, 0deg));
    }

    #needleMin {
      transform-origin: 0px 0px;
      transform: rotate(var(--min-rot, 0deg));
    }

    #needleMs {
      transform-origin: 0px 0px;
      transform: rotate(var(--ms-rot, 0deg));
    }

    /* Smooth sweeping hand transition override for reset/init only */
    .reset-transition {
      transition: transform 0.45s cubic-bezier(0.175, 0.885, 0.32, 1.275) !important;
    }

    /* Digital readout */
    .digital-display {
      font-family: var(--font-digital);
      font-size: 2.1rem;
      font-weight: 700;
      letter-spacing: 0.05em;
      padding: 12px 24px;
      border-radius: 14px;
      background: rgba(0, 0, 0, 0.2);
      border: 1px solid var(--border-color);
      margin-bottom: 20px;
      color: var(--text-main);
      display: flex;
      align-items: baseline;
      justify-content: center;
      box-shadow: inset 0 2px 8px rgba(0,0,0,0.4);
      transition: all 0.3s ease;
      width: 100%;
      max-width: 320px;
    }

    .digital-display .time-part {
      min-width: 44px;
      text-align: center;
    }

    .digital-display .time-part-ms {
      min-width: 36px;
      font-size: 1.45rem;
      color: var(--accent-secondary);
    }

    .digital-display .colon,
    .digital-display .decimal {
      color: var(--text-muted);
      opacity: 0.6;
      margin: 0 1px;
    }

    /* Readout Glowing state based on timer */
    .digital-display.running {
      box-shadow: inset 0 2px 12px rgba(0, 0, 0, 0.6), 0 0 18px 1px var(--accent-glow);
      border-color: rgba(251, 191, 36, 0.3);
      animation: breathing-glow 2.5s infinite ease-in-out;
    }

    .digital-display.paused {
      box-shadow: inset 0 2px 12px rgba(0, 0, 0, 0.6), 0 0 14px 1px rgba(239, 68, 68, 0.2);
      border-color: rgba(239, 68, 68, 0.25);
      animation: paused-glow 2s infinite ease-in-out;
    }

    /* Controls Action Panel */
    .controls-panel {
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 12px;
      width: 100%;
    }

    .control-btn {
      font-family: var(--font-interface);
      font-size: 0.9rem;
      font-weight: 700;
      text-transform: uppercase;
      letter-spacing: 1px;
      border-radius: 14px;
      cursor: pointer;
      transition: all 0.25s cubic-bezier(0.4, 0, 0.2, 1);
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
    }

    .btn-primary {
      background: var(--accent-gradient);
      border: none;
      color: #060911;
      height: 48px;
      flex-grow: 1.5;
      box-shadow: 0 4px 14px var(--accent-glow);
    }

    @media (hover: hover) {
      .btn-primary:hover:not(:disabled) {
        transform: translateY(-2px);
        box-shadow: 0 6px 20px var(--accent-glow);
        filter: brightness(1.1);
      }
    }
    .btn-primary:active:not(:disabled) {
      transform: translateY(1px);
    }

    .btn-secondary {
      background: rgba(255, 255, 255, 0.04);
      border: 1px solid var(--border-color);
      color: var(--text-main);
      height: 48px;
      width: 90px;
    }

    @media (hover: hover) {
      .btn-secondary:hover:not(:disabled) {
        background: rgba(255, 255, 255, 0.08);
        border-color: var(--accent-color);
        color: var(--accent-color);
        transform: translateY(-2px);
      }
    }
    .btn-secondary:active:not(:disabled) {
      transform: translateY(1px);
    }

    .control-btn:disabled {
      opacity: 0.35;
      cursor: not-allowed;
      transform: none !important;
      box-shadow: none !important;
    }

    .btn-primary.running {
      background: linear-gradient(135deg, #ef4444 0%, #b91c1c 100%);
      color: white;
      box-shadow: 0 4px 14px rgba(239, 68, 68, 0.3);
    }

    /* --------------------------------------------------------------------------
       5. Diagnostics & Laps Dashboard Panel (Right Column)
       -------------------------------------------------------------------------- */

    .dashboard-panel {
      display: flex;
      flex-direction: column;
      gap: 16px;
    }

    /* Stats widgets grid */
    .stats-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 10px;
    }

    .stat-card {
      padding: 10px 12px;
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .stat-icon {
      width: 32px;
      height: 32px;
      border-radius: 8px;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 0.85rem;
      flex-shrink: 0;
    }

    .stat-fastest {
      background: rgba(16, 185, 129, 0.1);
      color: var(--color-fastest);
      border: 1px solid rgba(16, 185, 129, 0.2);
    }

    .stat-slowest {
      background: rgba(239, 68, 68, 0.1);
      color: var(--color-slowest);
      border: 1px solid rgba(239, 68, 68, 0.2);
    }

    .stat-average {
      background: rgba(255, 255, 255, 0.04);
      color: var(--accent-secondary);
      border: 1px solid var(--border-color);
    }

    .stat-info {
      display: flex;
      flex-direction: column;
      min-width: 0; /* Prevents overflow */
    }

    .stat-label {
      font-size: 0.6rem;
      font-weight: 700;
      text-transform: uppercase;
      color: var(--text-muted);
      letter-spacing: 0.5px;
      white-space: nowrap;
      overflow: hidden;
      text-overflow: ellipsis;
    }

    .stat-value {
      font-family: var(--font-mono);
      font-size: 0.8rem;
      font-weight: 700;
      color: var(--text-main);
      margin-top: 1px;
    }

    /* Card Header */
    .card-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 12px 16px;
      border-bottom: 1px solid var(--border-color);
    }

    .card-header h3 {
      font-size: 0.85rem;
      font-weight: 700;
      display: flex;
      align-items: center;
      gap: 6px;
      color: var(--text-main);
    }

    .card-header h3 i {
      color: var(--accent-color);
    }

    .chart-sub {
      font-size: 0.65rem;
      font-weight: 500;
      color: var(--text-muted);
    }

    /* Trend Chart Component */
    .chart-card {
      overflow: hidden;
    }

    .chart-container {
      padding: 12px;
      position: relative;
      height: 120px;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    #lapChart {
      width: 100%;
      height: 100%;
    }

    .chart-text {
      fill: var(--text-muted);
      font-family: var(--font-interface);
      font-size: 7.5px;
      font-weight: 600;
      opacity: 0.7;
    }

    .chart-placeholder {
      position: absolute;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 6px;
      color: var(--text-muted);
      font-size: 0.75rem;
      font-weight: 500;
      text-align: center;
    }

    .chart-placeholder i {
      font-size: 1.25rem;
      color: var(--accent-color);
      opacity: 0.6;
    }

    .chart-placeholder.hidden {
      display: none;
    }

    .chart-dot {
      fill: var(--bg-app);
      stroke: var(--accent-color);
      stroke-width: 2;
      transition: r 0.2s ease, stroke-width 0.2s ease;
      cursor: pointer;
    }

    @media (hover: hover) {
      .chart-dot:hover {
        r: 5.5;
        stroke-width: 3;
        stroke: var(--text-main);
      }
    }

    /* Laps List Table Component */
    .laps-card {
      flex-grow: 1;
      display: flex;
      flex-direction: column;
      min-height: 220px;
    }

    .text-btn {
      background: none;
      border: none;
      color: var(--accent-color);
      font-family: var(--font-interface);
      font-size: 0.75rem;
      font-weight: 700;
      cursor: pointer;
      display: flex;
      align-items: center;
      gap: 6px;
      padding: 4px 8px;
      border-radius: 6px;
      transition: all 0.2s ease;
    }

    @media (hover: hover) {
      .text-btn:hover:not(:disabled) {
        background: rgba(251, 191, 36, 0.08);
        transform: translateY(-1px);
      }
    }
    .text-btn:active {
      transform: translateY(1px);
    }

    .text-btn:disabled {
      opacity: 0.3;
      cursor: not-allowed;
    }

    .table-wrapper {
      overflow-y: auto;
      max-height: 180px;
      width: 100%;
    }

    .laps-table {
      width: 100%;
      border-collapse: collapse;
      text-align: left;
    }

    .laps-table th {
      padding: 10px 16px;
      font-size: 0.7rem;
      font-weight: 700;
      text-transform: uppercase;
      color: var(--text-muted);
      letter-spacing: 0.5px;
      border-bottom: 1.5px solid var(--border-color);
      position: sticky;
      top: 0;
      background: var(--bg-card);
      backdrop-filter: blur(var(--glass-blur));
      -webkit-backdrop-filter: blur(var(--glass-blur));
      z-index: 10;
    }

    .laps-table td {
      padding: 8px 16px;
      font-size: 0.8rem;
      color: var(--text-main);
      border-bottom: 1px solid var(--border-color);
    }

    .laps-table tbody tr {
      animation: row-entrance 0.35s cubic-bezier(0.16, 1, 0.3, 1) forwards;
    }

    .laps-table tr.lap-row-fastest td {
      color: var(--color-fastest);
      font-weight: 600;
    }

    .laps-table tr.lap-row-fastest .lap-num-badge {
      background: rgba(16, 185, 129, 0.12);
      border-color: rgba(16, 185, 129, 0.25);
      color: var(--color-fastest);
    }

    .laps-table tr.lap-row-slowest td {
      color: var(--color-slowest);
      font-weight: 600;
    }

    .laps-table tr.lap-row-slowest .lap-num-badge {
      background: rgba(239, 68, 68, 0.12);
      border-color: rgba(239, 68, 68, 0.25);
      color: var(--color-slowest);
    }

    .lap-num-badge {
      padding: 2px 6px;
      border-radius: 6px;
      background: rgba(255,255,255,0.03);
      border: 1px solid var(--border-color);
      font-family: var(--font-mono);
      font-size: 0.7rem;
      font-weight: 700;
    }

    .lap-time-col, 
    .total-time-col {
      font-family: var(--font-mono);
      font-weight: 600;
    }

    .delta-col {
      font-family: var(--font-mono);
      font-size: 0.75rem;
      font-weight: 600;
    }

    .delta-col.delta-plus {
      color: var(--color-slowest);
    }

    .delta-col.delta-minus {
      color: var(--color-fastest);
    }

    .empty-message {
      text-align: center;
      padding: 30px 16px !important;
      color: var(--text-muted);
    }

    .empty-message i {
      font-size: 1.5rem;
      margin-bottom: 6px;
      opacity: 0.5;
      color: var(--accent-color);
    }

    .empty-message p {
      font-size: 0.75rem;
      font-weight: 500;
      max-width: 240px;
      margin: 0 auto;
      line-height: 1.4;
    }

    /* --------------------------------------------------------------------------
       6. Footer Component
       -------------------------------------------------------------------------- */

    .app-footer {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 12px 20px;
      font-size: 0.7rem;
      color: var(--text-muted);
      gap: 12px;
    }

    .shortcuts-guide {
      display: flex;
      align-items: center;
      flex-wrap: wrap;
      gap: 6px;
    }

    .guide-title {
      font-weight: 700;
      text-transform: uppercase;
      margin-right: 4px;
      display: flex;
      align-items: center;
      gap: 4px;
      color: var(--accent-color);
    }

    .key-badge {
      background: rgba(255, 255, 255, 0.08);
      border: 1px solid var(--border-color);
      padding: 1px 5px;
      border-radius: 4px;
      font-family: var(--font-mono);
      font-weight: 700;
      color: var(--text-main);
      box-shadow: 0 1.5px 0 rgba(255, 255, 255, 0.15);
    }

    .key-desc {
      margin-right: 8px;
      font-weight: 500;
    }

    .footer-logo {
      font-weight: 600;
    }

    /* --------------------------------------------------------------------------
       7. Responsive Layout Breakpoints (Mobile Enhancements)
       -------------------------------------------------------------------------- */

    @media (max-width: 820px) {
      .app-main {
        grid-template-columns: 1fr;
      }
    }

    @media (max-width: 480px) {
      .app-container {
        margin: 10px;
        gap: 12px;
      }
      
      .app-header {
        padding: 10px 14px;
      }
      
      .brand-text h1 {
        font-size: 1rem;
      }
      
      .theme-select-btn {
        padding: 8px 10px;
        font-size: 0.75rem;
      }

      .theme-select-btn span {
        display: none; /* Icon only on extra small mobile to save space */
      }
      
      .visual-panel {
        padding: 16px 12px;
      }

      .chronograph-container {
        max-width: 240px;
        margin-top: 16px;
      }

      .digital-display {
        font-size: 1.7rem;
        padding: 10px 16px;
        max-width: 260px;
      }
      
      .digital-display .time-part {
        min-width: 36px;
      }
      
      .digital-display .time-part-ms {
        min-width: 30px;
        font-size: 1.25rem;
      }

      .control-btn {
        font-size: 0.8rem;
      }

      .btn-primary {
        height: 44px;
      }

      .btn-secondary {
        height: 44px;
        width: 76px;
      }

      .stats-grid {
        grid-template-columns: 1fr; /* Stacks stats vertically on mobile */
        gap: 8px;
      }

      .stat-card {
        padding: 8px 12px;
      }
      
      .app-footer {
        flex-direction: column;
        text-align: center;
        gap: 10px;
        padding: 12px;
      }

      .shortcuts-guide {
        display: none; /* Hide shortcut guides on mobile since there is no keyboard */
      }
    }

    /* --------------------------------------------------------------------------
       8. Animations
       -------------------------------------------------------------------------- */

    @keyframes pulse-glow {
      0%, 100% {
        filter: drop-shadow(0 0 4px var(--accent-glow));
        transform: scale(1);
      }
      50% {
        filter: drop-shadow(0 0 10px var(--accent-glow));
        transform: scale(1.05);
      }
    }

    @keyframes breathing-glow {
      0%, 100% {
        box-shadow: inset 0 2px 12px rgba(0, 0, 0, 0.6), 0 0 14px 1px var(--accent-glow);
      }
      50% {
        box-shadow: inset 0 2px 12px rgba(0, 0, 0, 0.6), 0 0 22px 4px var(--accent-glow);
      }
    }

    @keyframes paused-glow {
      0%, 100% {
        box-shadow: inset 0 2px 12px rgba(0, 0, 0, 0.6), 0 0 10px 1px rgba(239, 68, 68, 0.15);
      }
      50% {
        box-shadow: inset 0 2px 12px rgba(0, 0, 0, 0.6), 0 0 18px 3px rgba(239, 68, 68, 0.3);
      }
    }

    @keyframes slide-down {
      from {
        opacity: 0;
        transform: translateY(-8px) scale(0.96);
      }
      to {
        opacity: 1;
        transform: translateY(0) scale(1);
      }
    }

    @keyframes row-entrance {
      from {
        opacity: 0;
        transform: translateX(-10px);
      }
      to {
        opacity: 1;
        transform: translateX(0);
      }
    }

    .animate-spin {
      animation: spin-anim 1.8s linear infinite;
    }

    @keyframes spin-anim {
      from { transform: rotate(0deg); }
      to { transform: rotate(360deg); }
    }
    
  </style>
</head>
<body class="theme-falcon">
  <!-- Dotted Grid Background Accent -->
  <div class="dot-grid"></div>
  <div class="radial-glow-1"></div>
  <div class="radial-glow-2"></div>

  <div class="app-container">
    <!-- Header -->
    <header class="app-header">
      <div class="brand">
        <div class="logo-icon">
          <svg width="32" height="32" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M12 2L2 9L10 11L12 22L14 11L22 9L12 2Z" fill="currentColor" filter="url(#glow-effect)"/>
          </svg>
        </div>
        <div class="brand-text">
          <h1>Falcon Dive</h1>
          <span class="tagline">EXCEEDING SPEED</span>
        </div>
      </div>
      
      <div class="header-controls">
        <!-- Audio Toggle -->
        <button id="soundToggle" class="icon-btn" title="Toggle Sound FX (S)">
          <i class="fa-solid fa-volume-high"></i>
        </button>
        
        <!-- Theme Dropdown -->
        <div class="theme-selector">
          <button id="themeBtn" class="theme-select-btn">
            <i class="fa-solid fa-palette"></i>
            <span>Falcon Dive</span>
            <i class="fa-solid fa-chevron-down"></i>
          </button>
          <div class="theme-menu" id="themeMenu">
            <div class="theme-option active" data-theme="falcon">
              <span class="dot falcon-dot"></span> Falcon Dive
            </div>
            <div class="theme-option" data-theme="cyberpunk">
              <span class="dot cyberpunk-dot"></span> Cyberpunk
            </div>
            <div class="theme-option" data-theme="emerald">
              <span class="dot emerald-dot"></span> Emerald Gold
            </div>
            <div class="theme-option" data-theme="light">
              <span class="dot light-dot"></span> Ice Light
            </div>
          </div>
        </div>
      </div>
    </header>

    <!-- Main Workspace -->
    <main class="app-main">
      <!-- Left Column: Visual Stopwatch -->
      <section class="visual-panel glass-card">
        <div class="task-badge">TASK 02 - STOPWATCH</div>
        
        <!-- Chronograph Dials Container -->
        <div class="chronograph-container">
          <div class="dial-glow"></div>
          
          <svg class="analog-dial" id="mainDial" viewBox="0 0 300 300">
            <!-- Dial Face Definitions -->
            <defs>
              <radialGradient id="dialGrad" cx="50%" cy="50%" r="50%">
                <stop offset="70%" stop-color="var(--dial-bg-start)" stop-opacity="0.6" />
                <stop offset="100%" stop-color="var(--dial-bg-end)" stop-opacity="0.95" />
              </radialGradient>
              <filter id="glow-effect" x="-20%" y="-20%" width="140%" height="140%">
                <feGaussianBlur stdDeviation="5" result="blur" />
                <feComposite in="SourceGraphic" in2="blur" operator="over" />
              </filter>
            </defs>

            <!-- Face Background -->
            <circle cx="150" cy="150" r="140" fill="url(#dialGrad)" stroke="var(--dial-border)" stroke-width="3" />
            <circle cx="150" cy="150" r="132" fill="none" stroke="var(--dial-border-inner)" stroke-width="1" stroke-dasharray="2 4" />

            <!-- Dynamic Tick Marks (populated via JavaScript) -->
            <g id="ticks" class="dial-ticks"></g>

            <!-- SUB-DIAL 1: Minutes (30 Min) -->
            <g transform="translate(150, 95)" class="sub-dial">
              <circle cx="0" cy="0" r="32" fill="var(--subdial-bg)" stroke="var(--dial-border)" stroke-width="1" />
              <!-- Ticks and Numbers for Sub-Dial (Minutes) -->
              <circle cx="0" cy="0" r="28" fill="none" stroke="var(--dial-border-inner)" stroke-width="0.5" stroke-dasharray="1 3" />
              <text x="0" y="-20" class="subdial-text">30</text>
              <text x="20" y="4" class="subdial-text">10</text>
              <text x="-20" y="4" class="subdial-text">20</text>
              <!-- Sub-Dial Needle -->
              <line id="needleMin" x1="0" y1="0" x2="0" y2="-26" stroke="var(--accent-color)" stroke-width="1.5" stroke-linecap="round" />
              <circle cx="0" cy="0" r="2.5" fill="var(--accent-color)" />
            </g>

            <!-- SUB-DIAL 2: Milliseconds / Centiseconds (1s sweep) -->
            <g transform="translate(150, 205)" class="sub-dial">
              <circle cx="0" cy="0" r="32" fill="var(--subdial-bg)" stroke="var(--dial-border)" stroke-width="1" />
              <!-- Ticks and Numbers for Sub-Dial -->
              <circle cx="0" cy="0" r="28" fill="none" stroke="var(--dial-border-inner)" stroke-width="0.5" stroke-dasharray="1 3" />
              <text x="0" y="-20" class="subdial-text">0</text>
              <text x="20" y="4" class="subdial-text">25</text>
              <text x="0" y="24" class="subdial-text">50</text>
              <text x="-20" y="4" class="subdial-text">75</text>
              <!-- Sub-Dial Needle -->
              <line id="needleMs" x1="0" y1="0" x2="0" y2="-26" stroke="var(--accent-secondary)" stroke-width="1.5" stroke-linecap="round" />
              <circle cx="0" cy="0" r="2.5" fill="var(--accent-secondary)" />
            </g>

            <!-- Main Dial Ring Text (Brand & Target) -->
            <text x="95" y="154" class="dial-brand">FALCON</text>
            <text x="205" y="154" class="dial-chrono">DIVE</text>

            <!-- Main Sweep Second Needle (60s sweep) -->
            <g id="mainNeedleGroup">
              <line id="needleSec" x1="150" y1="150" x2="150" y2="28" stroke="var(--accent-color)" stroke-width="2.5" stroke-linecap="round" filter="url(#glow-effect)" />
              <!-- Fancy counterweight tail -->
              <line x1="150" y1="150" x2="150" y2="175" stroke="var(--accent-color)" stroke-width="3" stroke-linecap="round" />
              <circle cx="150" cy="150" r="6" fill="var(--accent-color)" stroke="var(--bg-card)" stroke-width="1.5" />
            </g>
          </svg>
        </div>

        <!-- Digital Readout Display -->
        <div class="digital-display" id="digitalDisplay">
          <span class="time-part text-glow" id="displayHours">00</span><span class="colon">:</span>
          <span class="time-part text-glow" id="displayMinutes">00</span><span class="colon">:</span>
          <span class="time-part text-glow" id="displaySeconds">00</span><span class="decimal">.</span>
          <span class="time-part-ms text-glow" id="displayMs">00</span>
        </div>

        <!-- Control Action Bar -->
        <div class="controls-panel">
          <button id="lapBtn" class="control-btn btn-secondary" disabled>
            <i class="fa-solid fa-flag"></i> Lap
          </button>
          
          <button id="startPauseBtn" class="control-btn btn-primary">
            <span class="play-icon"><i class="fa-solid fa-play"></i> START</span>
          </button>
          
          <button id="resetBtn" class="control-btn btn-secondary" disabled>
            <i class="fa-solid fa-rotate-left"></i> Reset
          </button>
        </div>
      </section>

      <!-- Right Column: Diagnostics & Data Dashboard -->
      <section class="dashboard-panel">
        <!-- Stats Widgets -->
        <div class="stats-grid">
          <div class="stat-card glass-card">
            <div class="stat-icon stat-fastest"><i class="fa-solid fa-bolt"></i></div>
            <div class="stat-info">
              <span class="stat-label">Fastest Lap</span>
              <span class="stat-value" id="fastestLapVal">--:--.--</span>
            </div>
          </div>
          
          <div class="stat-card glass-card">
            <div class="stat-icon stat-slowest"><i class="fa-solid fa-tortoise"></i></div>
            <div class="stat-info">
              <span class="stat-label">Slowest Lap</span>
              <span class="stat-value" id="slowestLapVal">--:--.--</span>
            </div>
          </div>

          <div class="stat-card glass-card">
            <div class="stat-icon stat-average"><i class="fa-solid fa-calculator"></i></div>
            <div class="stat-info">
              <span class="stat-label">Average Lap</span>
              <span class="stat-value" id="averageLapVal">--:--.--</span>
            </div>
          </div>
        </div>

        <!-- Lap Chart Card -->
        <div class="chart-card glass-card">
          <div class="card-header">
            <h3><i class="fa-solid fa-chart-line"></i> Lap Performance</h3>
            <span class="chart-sub">Trend visualizer</span>
          </div>
          <div class="chart-container">
            <svg id="lapChart" viewBox="0 0 400 150">
              <!-- Grid Lines -->
              <line x1="40" y1="20" x2="380" y2="20" stroke="var(--border-color)" stroke-opacity="0.3" stroke-width="1" />
              <line x1="40" y1="65" x2="380" y2="65" stroke="var(--border-color)" stroke-opacity="0.3" stroke-width="1" />
              <line x1="40" y1="110" x2="380" y2="110" stroke="var(--border-color)" stroke-opacity="0.3" stroke-width="1" />
              <line x1="40" y1="130" x2="380" y2="130" stroke="var(--border-color)" stroke-opacity="0.8" stroke-width="1.5" />
              
              <!-- Y Axis labels -->
              <text x="15" y="24" class="chart-text">Fast</text>
              <text x="15" y="69" class="chart-text">Avg</text>
              <text x="15" y="114" class="chart-text">Slow</text>

              <!-- Dynamic Chart Elements -->
              <path id="chartArea" d="" fill="url(#chartAreaGrad)" opacity="0.15" />
              <path id="chartLine" d="" fill="none" stroke="var(--accent-color)" stroke-width="3" stroke-linecap="round" stroke-linejoin="round" filter="url(#glow-effect)" />
              <g id="chartPoints"></g>

              <!-- Defs for Gradient -->
              <defs>
                <linearGradient id="chartAreaGrad" x1="0" y1="0" x2="0" y2="1">
                  <stop offset="0%" stop-color="var(--accent-color)" />
                  <stop offset="100%" stop-color="var(--accent-color)" stop-opacity="0" />
                </linearGradient>
              </defs>
            </svg>
            <div id="chartPlaceholder" class="chart-placeholder">
              <i class="fa-solid fa-hourglass-start animate-spin"></i>
              <p>Record laps to map performance stats</p>
            </div>
          </div>
        </div>

        <!-- Laps Table Card -->
        <div class="laps-card glass-card">
          <div class="card-header">
            <h3><i class="fa-solid fa-list-check"></i> Recorded Laps</h3>
            <button id="exportCsvBtn" class="text-btn" disabled>
              <i class="fa-solid fa-file-csv"></i> Export CSV
            </button>
          </div>
          
          <div class="table-wrapper">
            <table class="laps-table">
              <thead>
                <tr>
                  <th width="15%">Lap</th>
                  <th width="35%">Lap Time</th>
                  <th width="35%">Total Time</th>
                  <th width="15%">Delta</th>
                </tr>
              </thead>
              <tbody id="lapsBody">
                <tr id="emptyLapRow">
                  <td colspan="4" class="empty-message">
                    <i class="fa-regular fa-clock"></i>
                    <p>No laps recorded. Start the chronometer and click Lap to log time splits.</p>
                  </td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </section>
    </main>

    <!-- Footer Settings & Keys Help -->
    <footer class="app-footer glass-card">
      <div class="shortcuts-guide">
        <span class="guide-title"><i class="fa-regular fa-keyboard"></i> Shortcuts:</span>
        <span class="key-badge">Space</span> <span class="key-desc">Start / Pause</span>
        <span class="key-badge">L</span> <span class="key-desc">Lap</span>
        <span class="key-badge">R</span> <span class="key-desc">Reset</span>
        <span class="key-badge">S</span> <span class="key-desc">Toggle Sound</span>
      </div>
      <div class="footer-logo">
        Falcon Dive &copy; 2026. Exceeding Speed.
      </div>
    </footer>
  </div>

  <!-- Unified Javascript Logic -->



 
