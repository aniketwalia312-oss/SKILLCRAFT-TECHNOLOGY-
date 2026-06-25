# SKILLCRAFT-TECHNOLOGY-
                                   TASK-4(TO-DO-LIST): QUEST:DAILY GOALS
My last and final task is also completed and with this my internship at skillcraft technology is also done. Genuinely I learnt a lot of thing and develop my skills for better and also develop experience and perfection in web development. throughtout this journey It is difficult and fun, enjoyable too. I hope my career growth is developing with this and make new and bigger projects and at last my 4th task is about to-do-list that I completed well and cleanly....
                                              
                                                    QUESTION:
Develop a basic to-do app that enables a user to add maintain tasks.
Allow users to add/organize items in lists. Mark them Completed, Edit them, Set Date & TIme of tasks.
                                                
                                              CODE AND EXICUTION:
FILE:[index.html](https://github.com/user-attachments/files/29339698/index.html)


FOR LIVE VIEW AND MOBILE: https://todolistog.netlify.app/

CODE:


  
 
    /* ==========================================================================
       DAILY GOALS & REMINDERS - COZY DESK STYLESHEET
       ========================================================================== */

    /* Design Variables */
    :root {
      --font-body: 'Outfit', sans-serif;
      --font-handwriting: 'Kalam', cursive;

      /* Theme Colors: Soft Warm Cream & Sage (Default) */
      --bg-desktop: #f5f2eb;
      --bg-panel: #ffffff;
      --bg-input: #FAF8F5;
      --border-color: #e5e0d4;
      --border-focus: #a3baa0;
      
      --text-main: #333d47;
      --text-muted: #7e8b93;
      
      /* Accent Colors */
      --accent-sage: #6e826b;
      --accent-sage-dark: #52634f;
      --accent-sage-light: #e4eae2;
      --accent-warm: #c58671;
      --accent-terracotta: #b8542f;

      /* Sticky Note Pastel Sheets */
      --note-yellow: #fff2c2;
      --note-yellow-border: #ebd88a;
      --note-pink: #ffd6e0;
      --note-pink-border: #e9a3b2;
      --note-green: #d2f5d1;
      --note-green-border: #9ed99d;
      --note-purple: #e9d4ff;
      --note-purple-border: #c8a7e5;
      --note-blue: #d0edff;
      --note-blue-border: #99cff0;

      /* Priority Accent Markers */
      --priority-high: #e74c3c;
      --priority-medium: #f1c40f;
      --priority-low: #2ecc71;

      /* Shadow Design */
      --shadow-cozy: 0 4px 15px rgba(110, 130, 107, 0.05), 0 2px 4px rgba(110, 130, 107, 0.02);
      --shadow-card: 0 10px 30px rgba(51, 61, 71, 0.04), 0 2px 8px rgba(51, 61, 71, 0.01);
      --shadow-note: 0 8px 18px rgba(112, 101, 88, 0.07);
      --shadow-drag: 0 25px 45px rgba(112, 101, 88, 0.16);

      --border-radius-sm: 8px;
      --border-radius-md: 14px;
      --border-radius-lg: 20px;
      
      --transition-speed: 0.25s;
    }

    /* Theme Variant: Cool Slate/Mint */
    [data-theme="cool"] {
      --bg-desktop: #ebf0f3;
      --bg-panel: #ffffff;
      --bg-input: #f2f5f7;
      --border-color: #d8e0e5;
      --border-focus: #9ab0c2;
      
      --text-main: #2b3d52;
      --text-muted: #7d8b92;
      
      --accent-sage: #53759a;
      --accent-sage-dark: #3a5573;
      --accent-sage-light: #e1ebf5;
      --accent-warm: #b8865e;
    }

    /* ==========================================================================
       RESET & BASE STYLES
       ========================================================================== */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      -webkit-tap-highlight-color: transparent;
    }

    body {
      font-family: var(--font-body);
      background-color: var(--bg-desktop);
      color: var(--text-main);
      min-height: 100vh;
      position: relative;
      overflow-x: hidden;
      transition: background-color var(--transition-speed), color var(--transition-speed);
    }

    #ambient-canvas {
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      pointer-events: none;
      z-index: 0;
    }

    /* ==========================================================================
       LAYOUT STRUCTURE
       ========================================================================== */
    .app-container {
      max-width: 1550px;
      margin: 0 auto;
      padding: 24px;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      gap: 20px;
      position: relative;
      z-index: 1;
    }

    /* ==========================================================================
       NOTIFICATION BANNER (ALARM)
       ========================================================================== */
    .notification-banner {
      position: fixed;
      top: 0;
      left: 0;
      right: 0;
      z-index: 9999;
      background: var(--bg-panel);
      border-bottom: 2px solid var(--accent-warm);
      box-shadow: 0 10px 30px rgba(0,0,0,0.15);
      transform: translateY(-110%);
      transition: transform 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.2);
      display: flex;
      justify-content: center;
      padding: 14px 24px;
    }

    .notification-banner.active {
      transform: translateY(0);
    }

    .notification-content {
      display: flex;
      align-items: center;
      gap: 16px;
      max-width: 800px;
      width: 100%;
    }

    .notification-icon {
      font-size: 1.5rem;
      color: var(--accent-warm);
    }

    .notification-text {
      flex: 1;
      display: flex;
      flex-direction: column;
      gap: 2px;
    }

    .notification-text strong {
      font-size: 0.9rem;
      color: var(--text-main);
    }

    .notification-text span {
      font-size: 0.78rem;
      color: var(--text-muted);
    }

    .notification-close {
      background: transparent;
      border: none;
      color: var(--text-muted);
      cursor: pointer;
      font-size: 1.1rem;
      padding: 4px;
      transition: color 0.2s;
    }

    .notification-close:hover {
      color: var(--priority-high);
    }

    /* Swing Alarm animation */
    @keyframes swing {
      0%, 100% { transform: rotate(0); }
      20% { transform: rotate(15deg); }
      40% { transform: rotate(-15deg); }
      60% { transform: rotate(10deg); }
      80% { transform: rotate(-10deg); }
    }
    .animate-swing {
      animation: swing 1s ease-in-out infinite;
    }

    /* ==========================================================================
       HEADER SECTION
       ========================================================================== */
    .app-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding-bottom: 16px;
      border-bottom: 1px solid var(--border-color);
      flex-wrap: wrap;
      gap: 16px;
    }

    .logo-area {
      display: flex;
      align-items: center;
      gap: 14px;
    }

    .logo-icon {
      font-size: 2.2rem;
      color: var(--accent-sage);
      filter: drop-shadow(0 2px 4px rgba(110, 130, 107, 0.2));
    }

    .logo-area h1 {
      font-size: 1.45rem;
      font-weight: 700;
      letter-spacing: 0.5px;
      color: var(--text-main);
    }

    .subtitle {
      font-size: 0.8rem;
      color: var(--text-muted);
      font-weight: 400;
      display: block;
      margin-top: 2px;
    }

    .header-controls {
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .btn-icon {
      background: var(--bg-panel);
      border: 1px solid var(--border-color);
      color: var(--text-main);
      width: 40px;
      height: 40px;
      border-radius: 50%;
      cursor: pointer;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 1rem;
      transition: all var(--transition-speed) ease;
      box-shadow: var(--shadow-cozy);
    }

    .btn-icon:hover {
      background: var(--accent-sage-light);
      border-color: var(--border-focus);
      color: var(--accent-sage-dark);
      transform: translateY(-2px);
    }

    /* ==========================================================================
       DESK MAIN PANEL DIVISION
       ========================================================================== */
    .main-desk {
      display: grid;
      grid-template-columns: 380px 1fr;
      gap: 24px;
      align-items: start;
    }

    .left-panel {
      display: flex;
      flex-direction: column;
      gap: 20px;
      position: sticky;
      top: 24px;
    }

    .right-panel {
      display: flex;
      flex-direction: column;
      gap: 20px;
    }

    /* ==========================================================================
       COZY PANEL CARD STYLES & 3D PERSPECTIVE HOVER
       ========================================================================== */
    .panel-card {
      background-color: var(--bg-panel);
      border: 1px solid var(--border-color);
      border-radius: var(--border-radius-md);
      box-shadow: var(--shadow-card);
      padding: 24px;
      transition: border-color var(--transition-speed), transform 0.1s ease-out, box-shadow 0.1s ease-out;
      transform-style: preserve-3d;
      will-change: transform;
    }

    .panel-card:hover {
      border-color: rgba(110, 130, 107, 0.25);
      box-shadow: 0 12px 35px rgba(110, 130, 107, 0.08);
    }

    .panel-card h3 {
      font-size: 0.95rem;
      font-weight: 700;
      letter-spacing: 0.5px;
      color: var(--text-main);
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .panel-card h3 i {
      color: var(--accent-sage);
    }

    /* ==========================================================================
       DAILY PROGRESS HUD (CIRCULAR SVG)
       ========================================================================== */
    .progress-card {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 16px;
      padding: 20px 24px;
    }

    .progress-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      width: 100%;
    }

    .progress-day-label {
      font-size: 0.72rem;
      font-weight: 700;
      letter-spacing: 1px;
      color: var(--accent-sage);
      background: var(--accent-sage-light);
      padding: 3px 10px;
      border-radius: 12px;
    }

    .progress-ring-wrapper {
      position: relative;
      width: 120px;
      height: 120px;
      display: flex;
      justify-content: center;
      align-items: center;
    }

    .progress-ring {
      transform: rotate(-90deg);
    }

    .progress-ring-bg {
      stroke: var(--bg-desktop);
    }

    .progress-ring-fill {
      stroke: var(--accent-sage);
      stroke-linecap: round;
      transition: stroke-dashoffset 0.6s cubic-bezier(0.4, 0, 0.2, 1);
      filter: drop-shadow(0 0 4px rgba(110, 130, 107, 0.25));
    }

    /* Glow when progress is complete */
    .progress-card.complete .progress-ring-fill {
      stroke: var(--accent-warm);
      filter: drop-shadow(0 0 8px rgba(197, 134, 113, 0.5));
    }

    .progress-percent {
      position: absolute;
      font-size: 1.6rem;
      font-weight: 700;
      color: var(--text-main);
      letter-spacing: -0.5px;
    }

    .progress-summary {
      font-size: 0.8rem;
      color: var(--text-muted);
      min-height: 20px;
    }

    /* ==========================================================================
       TASK CREATOR FORM
       ========================================================================== */
    .creator-card h3 {
      margin-bottom: 16px;
    }

    .form-group {
      margin-bottom: 14px;
    }

    .form-group label {
      display: block;
      font-size: 0.7rem;
      font-weight: 700;
      text-transform: uppercase;
      letter-spacing: 1.2px;
      color: var(--text-muted);
      margin-bottom: 6px;
    }

    input[type="text"],
    textarea,
    select {
      width: 100%;
      background: var(--bg-input);
      border: 1px solid var(--border-color);
      border-radius: var(--border-radius-sm);
      color: var(--text-main);
      padding: 8px 12px;
      font-family: var(--font-body);
      font-size: 0.85rem;
      outline: none;
      transition: all 0.2s;
    }

    input[type="text"]:focus,
    textarea:focus,
    select:focus {
      border-color: var(--border-focus);
      background: var(--bg-panel);
      box-shadow: 0 0 0 3px rgba(163, 186, 160, 0.25);
    }

    textarea {
      resize: vertical;
    }

    .form-row {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 12px;
    }

    /* Recurring option row */
    .checklist-check-row {
      display: flex;
      align-items: center;
    }

    .checkbox-label {
      display: flex;
      align-items: center;
      gap: 8px;
      cursor: pointer;
      user-select: none;
    }

    .checkbox-label input[type="checkbox"] {
      width: 16px;
      height: 16px;
      accent-color: var(--accent-sage);
      cursor: pointer;
    }

    .checkbox-label span {
      font-size: 0.78rem;
      font-weight: 500;
      color: var(--text-main);
    }

    /* Subtask Builder inside Creator Form */
    .subtask-adder {
      display: flex;
      gap: 8px;
    }

    .btn-action-small {
      background: var(--accent-sage-light);
      border: 1px solid var(--border-focus);
      color: var(--accent-sage-dark);
      width: 34px;
      height: 34px;
      border-radius: var(--border-radius-sm);
      display: flex;
      justify-content: center;
      align-items: center;
      cursor: pointer;
      transition: all 0.2s;
    }

    .btn-action-small:hover {
      background: var(--accent-sage);
      color: #ffffff;
    }

    .subtask-form-list {
      list-style: none;
      margin-top: 8px;
      display: flex;
      flex-direction: column;
      gap: 6px;
    }

    .subtask-form-item {
      background: var(--bg-input);
      border: 1px solid var(--border-color);
      border-radius: 4px;
      padding: 6px 10px;
      font-size: 0.78rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
      animation: slideIn 0.2s ease-out;
    }

    .subtask-form-item button {
      background: transparent;
      border: none;
      color: var(--priority-high);
      cursor: pointer;
      font-size: 0.85rem;
      opacity: 0.6;
      transition: opacity 0.2s;
    }

    .subtask-form-item button:hover {
      opacity: 1;
    }

    /* Form Submit Button */
    .btn-submit {
      display: block;
      width: 100%;
      background: var(--accent-sage);
      color: #ffffff;
      border: none;
      padding: 10px 16px;
      font-size: 0.85rem;
      font-weight: 700;
      border-radius: var(--border-radius-sm);
      cursor: pointer;
      box-shadow: var(--shadow-cozy);
      transition: all 0.2s;
      margin-top: 18px;
    }

    .btn-submit:hover {
      background: var(--accent-sage-dark);
      transform: translateY(-1px);
    }

    /* ==========================================================================
       DAILY CHECKLIST (STRUCTURED TASK LIST)
       ========================================================================== */
    .list-card {
      padding: 20px 24px;
    }

    .list-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      border-bottom: 1px solid var(--border-color);
      padding-bottom: 12px;
      margin-bottom: 16px;
      flex-wrap: wrap;
      gap: 12px;
    }

    .title-with-count {
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .badge-count {
      background: var(--bg-input);
      border: 1px solid var(--border-color);
      font-size: 0.72rem;
      font-weight: 700;
      color: var(--text-muted);
      padding: 2px 8px;
      border-radius: 12px;
    }

    .list-filters {
      display: flex;
      gap: 8px;
      align-items: center;
    }

    .search-box {
      position: relative;
      min-width: 180px;
    }

    .search-box i {
      position: absolute;
      left: 10px;
      top: 50%;
      transform: translateY(-50%);
      color: var(--text-muted);
      font-size: 0.75rem;
    }

    .search-box input {
      padding-left: 28px;
      padding-top: 6px;
      padding-bottom: 6px;
      font-size: 0.78rem;
    }

    .select-small {
      padding: 6px 10px;
      font-size: 0.78rem;
      width: auto;
      cursor: pointer;
    }

    /* Tasks Container */
    .tasks-container {
      min-height: 180px;
    }

    .empty-state {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      text-align: center;
      padding: 40px 10px;
      color: var(--text-muted);
    }

    .empty-icon {
      font-size: 2.2rem;
      margin-bottom: 12px;
      color: var(--border-color);
    }

    .empty-state p {
      font-size: 0.8rem;
      max-width: 320px;
      line-height: 1.4;
    }

    .tasks-list {
      display: flex;
      flex-direction: column;
      gap: 12px;
    }

    /* Task Item Card (Elastic bounce slide in) */
    .task-item {
      border: 1px solid var(--border-color);
      border-radius: var(--border-radius-sm);
      padding: 12px 16px;
      background: var(--bg-panel);
      display: flex;
      flex-direction: column;
      gap: 8px;
      animation: elasticDrop 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.25) forwards;
      transition: all 0.25s, transform 0.1s ease-out;
      transform-style: preserve-3d;
      will-change: transform;
    }

    .task-item:hover {
      box-shadow: var(--shadow-cozy);
      border-color: rgba(110, 130, 107, 0.2);
    }

    .task-item-header {
      display: flex;
      align-items: flex-start;
      gap: 12px;
      justify-content: space-between;
    }

    .task-item-left {
      display: flex;
      align-items: flex-start;
      gap: 12px;
      flex: 1;
    }

    /* Dynamic Draw Checkbox */
    .task-checkbox-btn {
      background: transparent;
      border: 2px solid var(--accent-sage-light);
      width: 20px;
      height: 20px;
      border-radius: 50%;
      display: flex;
      justify-content: center;
      align-items: center;
      cursor: pointer;
      transition: all 0.25s cubic-bezier(0.175, 0.885, 0.32, 1.275);
      margin-top: 2px;
      flex-shrink: 0;
      padding: 0;
    }

    .task-checkbox-btn:hover {
      border-color: var(--accent-sage);
      transform: scale(1.1);
    }

    .task-checkbox-svg {
      width: 12px;
      height: 10px;
      fill: none;
      stroke: #ffffff;
      stroke-width: 2;
      stroke-linecap: round;
      stroke-linejoin: round;
    }

    .checkmark-path {
      stroke-dasharray: 20;
      stroke-dashoffset: 20;
      transition: stroke-dashoffset 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    }

    .task-item.completed .task-checkbox-btn {
      background: var(--accent-sage);
      border-color: var(--accent-sage);
      transform: scale(1.03);
    }

    .task-item.completed .checkmark-path {
      stroke-dashoffset: 0;
    }

    /* Title & Description */
    .task-details {
      display: flex;
      flex-direction: column;
      gap: 2px;
    }

    .task-title {
      font-size: 0.9rem;
      font-weight: 600;
      color: var(--text-main);
      transition: color 0.2s;
    }

    .task-item.completed .task-title {
      text-decoration: line-through;
      color: var(--text-muted);
    }

    .task-desc {
      font-size: 0.78rem;
      color: var(--text-muted);
      line-height: 1.35;
    }

    .task-item.completed .task-desc {
      color: rgba(126, 139, 147, 0.55);
      text-decoration: line-through;
    }

    /* Action Controls */
    .task-actions {
      display: flex;
      gap: 6px;
    }

    .btn-task-action {
      background: transparent;
      border: none;
      color: var(--text-muted);
      width: 26px;
      height: 26px;
      border-radius: 4px;
      cursor: pointer;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 0.8rem;
      transition: all 0.2s;
    }

    .btn-task-action:hover {
      background: var(--bg-input);
      color: var(--text-main);
    }

    .btn-task-action.delete-btn:hover {
      color: var(--priority-high);
      background: rgba(231, 76, 60, 0.05);
    }

    /* Task Meta footer */
    .task-item-footer {
      display: flex;
      justify-content: space-between;
      align-items: center;
      border-top: 1px dashed var(--border-color);
      padding-top: 8px;
      margin-top: 2px;
      font-size: 0.72rem;
      color: var(--text-muted);
    }

    .task-meta-left {
      display: flex;
      gap: 10px;
      align-items: center;
    }

    .task-tag {
      background: var(--accent-sage-light);
      color: var(--accent-sage-dark);
      padding: 2px 6px;
      border-radius: 4px;
      font-weight: 500;
    }

    .task-due {
      display: flex;
      align-items: center;
      gap: 4px;
    }

    .task-due.overdue {
      color: var(--priority-high);
      font-weight: 650;
    }

    .task-recurring-badge {
      background: #fdf2e9;
      color: var(--accent-warm);
      padding: 2px 5px;
      border-radius: 4px;
      font-weight: 600;
    }

    /* Priority Indicator Badge */
    .priority-badge {
      display: flex;
      align-items: center;
      gap: 4px;
      padding: 2px 6px;
      border-radius: 4px;
      background: var(--bg-input);
      font-weight: 500;
    }

    .priority-dot {
      width: 6px;
      height: 6px;
      border-radius: 50%;
      display: inline-block;
    }

    .priority-dot.low { background-color: var(--priority-low); }
    .priority-dot.medium { background-color: var(--priority-medium); }
    .priority-dot.high { background-color: var(--priority-high); }

    /* Task Subtasks list inside items */
    .task-item-subtasks {
      list-style: none;
      padding-left: 32px;
      display: flex;
      flex-direction: column;
      gap: 6px;
      margin-top: 4px;
    }

    .task-subtask-node {
      display: flex;
      align-items: center;
      gap: 8px;
      font-size: 0.75rem;
      color: var(--text-main);
      cursor: pointer;
    }

    .subtask-node-checkbox {
      width: 14px;
      height: 14px;
      border: 1px solid var(--text-muted);
      border-radius: 3px;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 0.55rem;
      color: transparent;
      transition: all 0.2s;
    }

    .task-subtask-node.checked .subtask-node-checkbox {
      background: var(--accent-sage);
      border-color: var(--accent-sage);
      color: #ffffff;
    }

    .task-subtask-node.checked span {
      text-decoration: line-through;
      color: var(--text-muted);
    }

    /* ==========================================================================
       STICKY NOTES WALL
       ========================================================================== */
    .corkboard-card {
      padding: 20px 24px;
    }

    .corkboard-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      border-bottom: 1px solid var(--border-color);
      padding-bottom: 12px;
      margin-bottom: 16px;
      flex-wrap: wrap;
      gap: 12px;
    }

    .corkboard-subtitle {
      font-size: 0.72rem;
      color: var(--text-muted);
      margin-top: 2px;
    }

    .corkboard-actions {
      display: flex;
      gap: 8px;
    }

    .btn-corkboard-action {
      background: var(--bg-input);
      border: 1px solid var(--border-color);
      color: var(--text-main);
      padding: 6px 12px;
      font-size: 0.78rem;
      font-weight: 600;
      border-radius: var(--border-radius-sm);
      cursor: pointer;
      display: flex;
      align-items: center;
      gap: 6px;
      transition: all 0.2s;
    }

    .btn-corkboard-action:hover {
      background: var(--accent-sage-light);
      border-color: var(--border-focus);
      color: var(--accent-sage-dark);
    }

    .btn-danger-cork:hover {
      background: #fdf2f2;
      border-color: #fca5a5;
      color: var(--priority-high);
    }

    /* Corkboard Viewport / Desk */
    .corkboard-viewport {
      height: 460px;
      background-color: #faf6ee;
      background-image: radial-gradient(#d3cbbe 1.2px, transparent 1.2px);
      background-size: 20px 20px;
      border: 1px solid var(--border-color);
      border-radius: var(--border-radius-sm);
      position: relative;
      overflow: hidden;
      box-shadow: inset 0 2px 8px rgba(112, 101, 88, 0.05);
    }

    .corkboard-empty {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      pointer-events: none;
      z-index: 0;
    }

    /* Sticky Note Card (Elastic Landing) */
    .sticky-note {
      position: absolute;
      width: 170px;
      height: 170px;
      padding: 14px 12px 8px 12px;
      display: flex;
      flex-direction: column;
      gap: 6px;
      box-shadow: var(--shadow-note);
      border-radius: 2px;
      z-index: 5;
      cursor: grab;
      /* Default styling is Yellow note */
      background-color: var(--note-yellow);
      border: 1px solid var(--note-yellow-border);
      animation: elasticDrop 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.2) forwards;
      transition: box-shadow 0.2s, transform 0.1s ease-out;
      transform-style: preserve-3d;
      will-change: transform;
      
      /* CRITICAL: Disable mobile screen scrolling when dragging notes */
      touch-action: none;
    }

    .sticky-note:hover {
      box-shadow: 0 12px 24px rgba(112, 101, 88, 0.12);
    }

    /* Dragging state override - Peel Lift Effect */
    .sticky-note.dragging {
      cursor: grabbing;
      z-index: 1000 !important;
      box-shadow: var(--shadow-drag) !important;
      transform: scale(1.05) rotate(0deg) !important;
    }

    /* Pushpin Decoration */
    .sticky-note-pin {
      position: absolute;
      top: -8px;
      left: 50%;
      transform: translateX(-50%);
      font-size: 1.1rem;
      color: var(--accent-terracotta);
      filter: drop-shadow(0 2px 3px rgba(0,0,0,0.15));
      z-index: 10;
      cursor: grab;
      
      /* CRITICAL: Disable mobile default touch events on the pin */
      touch-action: none;
    }

    .sticky-note.dragging .sticky-note-pin {
      cursor: grabbing;
      transform: translateX(-50%) scale(1.1);
    }

    /* Content Textarea */
    .sticky-note-content {
      width: 100%;
      flex: 1;
      background: transparent;
      border: none;
      outline: none;
      resize: none;
      font-family: var(--font-handwriting);
      font-size: 0.95rem;
      line-height: 1.35;
      color: #2c3e50;
      overflow-y: auto;
      padding: 0;
    }

    .sticky-note-content::-webkit-scrollbar {
      width: 4px;
    }

    .sticky-note-content::-webkit-scrollbar-thumb {
      background: rgba(0,0,0,0.06);
      border-radius: 2px;
    }

    /* Footer Colors & Controls */
    .sticky-note-footer {
      display: flex;
      justify-content: space-between;
      align-items: center;
      border-top: 1px dashed rgba(0, 0, 0, 0.06);
      padding-top: 4px;
      z-index: 5;
      opacity: 0.3;
      transition: opacity 0.2s;
    }

    .sticky-note:hover .sticky-note-footer {
      opacity: 0.9;
    }

    .note-colors {
      display: flex;
      gap: 3px;
    }

    .btn-note-color {
      width: 10px;
      height: 10px;
      border-radius: 50%;
      border: 1px solid rgba(0,0,0,0.1);
      cursor: pointer;
      padding: 0;
      transition: transform 0.15s;
    }

    .btn-note-color:hover {
      transform: scale(1.25);
    }

    .color-yellow { background-color: var(--note-yellow-border); }
    .color-pink { background-color: var(--note-pink-border); }
    .color-green { background-color: var(--note-green-border); }
    .color-purple { background-color: var(--note-purple-border); }
    .color-blue { background-color: var(--note-blue-border); }

    /* Note Colors Variations */
    .sticky-note.yellow { background-color: var(--note-yellow); border-color: var(--note-yellow-border); }
    .sticky-note.pink   { background-color: var(--note-pink);   border-color: var(--note-pink-border); }
    .sticky-note.green  { background-color: var(--note-green);  border-color: var(--note-green-border); }
    .sticky-note.purple { background-color: var(--note-purple); border-color: var(--note-purple-border); }
    .sticky-note.blue   { background-color: var(--note-blue);   border-color: var(--note-blue-border); }

    .btn-note-delete {
      background: transparent;
      border: none;
      color: #34495e;
      cursor: pointer;
      font-size: 0.72rem;
      padding: 2px;
      transition: color 0.15s;
    }

    .btn-note-delete:hover {
      color: var(--priority-high);
    }

    /* ==========================================================================
       MODAL DIALOGS
       ========================================================================== */
    .modal-overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      background: rgba(45, 55, 72, 0.4);
      backdrop-filter: blur(4px);
      z-index: 1000;
      display: flex;
      justify-content: center;
      align-items: center;
      opacity: 0;
      pointer-events: none;
      transition: opacity 0.3s ease;
    }

    .modal-overlay.active {
      opacity: 1;
      pointer-events: all;
    }

    .modal-content {
      background: var(--bg-panel);
      border: 1px solid var(--border-color);
      border-radius: var(--border-radius-md);
      padding: 28px;
      max-width: 500px;
      width: 90%;
      box-shadow: var(--shadow-card);
      transform: scale(0.95);
      transition: transform 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.2);
    }

    .modal-overlay.active .modal-content {
      transform: scale(1);
    }

    .help-card h2 {
      font-size: 1.15rem;
      font-weight: 700;
      margin-bottom: 14px;
      color: var(--text-main);
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .help-card h2 i {
      color: var(--accent-sage);
    }

    .help-body {
      max-height: 380px;
      overflow-y: auto;
      padding-right: 8px;
      margin-bottom: 20px;
    }

    .help-body::-webkit-scrollbar {
      width: 5px;
    }

    .help-body::-webkit-scrollbar-thumb {
      background: var(--border-color);
      border-radius: 3px;
    }

    .help-body p {
      font-size: 0.82rem;
      line-height: 1.5;
      color: var(--text-muted);
      margin-bottom: 12px;
    }

    .help-body h3 {
      font-size: 0.9rem;
      font-weight: 700;
      margin: 16px 0 6px 0;
      color: var(--text-main);
    }

    .help-body ul {
      padding-left: 18px;
      font-size: 0.8rem;
      color: var(--text-muted);
      line-height: 1.5;
    }

    .help-body li {
      margin-bottom: 6px;
    }

    /* ==========================================================================
       ANIMATIONS KEYFRAMES & UTILITIES
       ========================================================================== */

    /* Elastic bounce scale landing */
    @keyframes elasticDrop {
      0% {
        opacity: 0;
        transform: translateY(-50px) scale(0.7);
      }
      60% {
        opacity: 1;
        transform: translateY(6px) scale(1.03);
      }
      85% {
        transform: translateY(-2px) scale(0.99);
      }
      100% {
        opacity: 1;
        transform: translateY(0) scale(1);
      }
    }

    /* 3D Crumple-up paper trash toss */
    @keyframes crumple {
      0% {
        transform: scale(1) rotate(0deg) skew(0deg) rotateY(0);
        opacity: 1;
        filter: blur(0px);
      }
      30% {
        transform: scale(0.85) rotate(-6deg) skew(4deg, 4deg) rotateX(15deg);
        filter: blur(0.5px);
        box-shadow: 0 4px 10px rgba(0,0,0,0.1);
      }
      100% {
        transform: scale(0) rotate(-45deg) rotateY(90deg) translateY(120px);
        opacity: 0;
        filter: blur(5px);
      }
    }

    .crumpling-delete {
      animation: crumple 0.4s cubic-bezier(0.55, 0.055, 0.675, 0.19) forwards !important;
      pointer-events: none;
    }

    @keyframes slideIn {
      from {
        opacity: 0;
        transform: translateX(-10px);
      }
      to {
        opacity: 1;
        transform: translateX(0);
      }
    }

    /* Utilities */
    .text-center { text-align: center; }
    .text-muted { color: var(--text-muted); }
    .margin-top-6 { margin-top: 6px; }

    /* ==========================================================================
       RESPONSIVE DESIGN
       ========================================================================== */
    @media (max-width: 1050px) {
      .main-desk {
        grid-template-columns: 1fr;
      }
      .left-panel {
        position: static;
      }
    }

    @media (max-width: 768px) {
      .app-header {
        flex-direction: column;
        align-items: flex-start;
      }
      .header-controls {
        width: 100%;
        justify-content: flex-end;
      }
      .list-header {
        flex-direction: column;
        align-items: stretch;
      }
      .list-filters {
        flex-direction: column;
        align-items: stretch;
      }
      .search-box {
        width: 100%;
      }
      .form-row {
        grid-template-columns: 1fr;
        gap: 0;
      }
    }
  </style>
</head>
<body>
  <!-- Alarm/Notification alert banner that slides down -->
  <div id="notification-banner" class="notification-banner">
    <div class="notification-content">
      <i class="fa-solid fa-bell-ring notification-icon animate-swing"></i>
      <div class="notification-text">
        <strong id="noti-title">Task Due!</strong>
        <span id="noti-desc">Take a moment to check your deadline.</span>
      </div>
      <button id="close-notification-btn" class="notification-close"><i class="fa-solid fa-xmark"></i></button>
    </div>
  </div>

  <!-- Ambient background canvas for zen dust floaters -->
  <canvas id="ambient-canvas"></canvas>

  <div class="app-container">
    <!-- Top Desk Header -->
    <header class="app-header">
      <div class="logo-area">
        <i class="fa-solid fa-feather-pointed logo-icon"></i>
        <div>
          <h1>QUESTS: DAILY GOALS</h1>
          <span class="subtitle">Focus mindfully, plan structured tasks, pin quick thoughts</span>
        </div>
      </div>
      
      <!-- Serene Controls -->
      <div class="header-controls">
        <button id="toggle-sound-effects" class="btn-icon" title="Toggle Sound Effects">
          <i class="fa-solid fa-volume-high"></i>
        </button>
        <button id="toggle-theme" class="btn-icon" title="Toggle Theme (Warm/Cool)">
          <i class="fa-solid fa-sun"></i>
        </button>
        <button id="show-help" class="btn-icon" title="Show Help Guide">
          <i class="fa-solid fa-circle-question"></i>
        </button>
      </div>
    </header>

    <!-- Main Desk Layout -->
    <main class="main-desk">
      
      <!-- LEFT PANEL: Structured Task Organizer & Focus Timer -->
      <section class="left-panel">
        
        <!-- Daily Progress HUD (SVG Radial Ring) -->
        <div class="panel-card progress-card tilt-target">
          <div class="progress-header">
            <h3><i class="fa-solid fa-seedling"></i> DAILY FOCUS</h3>
            <span class="progress-day-label" id="current-day-name">TODAY</span>
          </div>
          
          <div class="progress-ring-wrapper">
            <svg class="progress-ring" width="120" height="120">
              <circle class="progress-ring-bg" stroke-width="8" fill="transparent" r="50" cx="60" cy="60"/>
              <circle id="progress-ring-fill" class="progress-ring-fill" stroke-width="8" fill="transparent" r="50" cx="60" cy="60" stroke-dasharray="314.16" stroke-dashoffset="314.16"/>
            </svg>
            <div id="progress-text" class="progress-percent">0%</div>
          </div>
          
          <div class="progress-summary">
            <span id="progress-desc" class="text-center text-muted">No goals completed today.</span>
          </div>
        </div>

        <!-- Task Creator Form -->
        <div class="panel-card creator-card tilt-target">
          <h3><i class="fa-solid fa-pen-nib"></i> EMBARK ON GOAL</h3>
          <form id="task-form">
            <div class="form-group">
              <label for="task-title">Task Name</label>
              <input type="text" id="task-title" placeholder="What will you conquer today?" required maxlength="60">
            </div>

            <div class="form-group">
              <label for="task-desc">Notes / Details (Optional)</label>
              <textarea id="task-desc" placeholder="Details or notes about this goal..." rows="2" maxlength="150"></textarea>
            </div>

            <div class="form-row">
              <div class="form-group">
                <label for="task-category">Category</label>
                <select id="task-category">
                  <option value="Personal">🌸 Personal</option>
                  <option value="Work">💼 Work</option>
                  <option value="Study">📚 Study</option>
                  <option value="Chores">🧹 Chores</option>
                  <option value="Wellness">🌱 Wellness</option>
                </select>
              </div>
              <div class="form-group">
                <label for="task-priority">Priority</label>
                <select id="task-priority">
                  <option value="Low">🟢 Low</option>
                  <option value="Medium" selected>🟡 Medium</option>
                  <option value="High">🔴 High</option>
                </select>
              </div>
            </div>

            <div class="form-row">
              <div class="form-group">
                <label for="task-date">Deadline Date</label>
                <input type="date" id="task-date">
              </div>
              <div class="form-group">
                <label for="task-time">Deadline Time</label>
                <input type="time" id="task-time" value="23:59">
              </div>
            </div>

            <div class="form-group checklist-check-row">
              <label for="task-recurring" class="checkbox-label">
                <input type="checkbox" id="task-recurring">
                <span>🔄 Repeat Quest Daily (Auto-Resets)</span>
              </label>
            </div>

            <!-- Subtasks Checklist Creator -->
            <div class="form-group">
              <label>Breakdown Sub-steps (Checklist)</label>
              <div class="subtask-adder">
                <input type="text" id="subtask-input" placeholder="Add a checklist step..." maxlength="50">
                <button type="button" id="btn-add-subtask" class="btn-action-small"><i class="fa-solid fa-plus"></i></button>
              </div>
              <ul id="subtask-form-list" class="subtask-form-list">
                <!-- Dynamic checklist items -->
              </ul>
            </div>

            <button type="submit" id="submit-task-btn" class="btn-submit">
              <i class="fa-solid fa-feather-pointed"></i> Decree Goal Objective
            </button>
          </form>
        </div>
      </section>

      <!-- RIGHT PANEL: Structured To-Do List & Sticky Notes Corkboard -->
      <section class="right-panel">
        
        <!-- Structured List Panel -->
        <div class="panel-card list-card tilt-target">
          <div class="list-header">
            <div class="title-with-count">
              <h3><i class="fa-solid fa-list-check"></i> DAILY OBJECTIVES</h3>
              <span id="task-completion-count" class="badge-count">0 / 0</span>
            </div>
            
            <div class="list-filters">
              <div class="search-box">
                <i class="fa-solid fa-magnifying-glass"></i>
                <input type="text" id="search-tasks" placeholder="Search tasks...">
              </div>
              <select id="filter-priority" class="select-small">
                <option value="All">All Priorities</option>
                <option value="High">🔴 High</option>
                <option value="Medium">🟡 Medium</option>
                <option value="Low">🟢 Low</option>
              </select>
              <select id="filter-category" class="select-small">
                <option value="All">All Categories</option>
                <option value="Personal">🌸 Personal</option>
                <option value="Work">💼 Work</option>
                <option value="Study">📚 Study</option>
                <option value="Chores">🧹 Chores</option>
                <option value="Wellness">🌱 Wellness</option>
              </select>
            </div>
          </div>

          <!-- Structured Tasks Container -->
          <div class="tasks-container">
            <div id="empty-tasks-state" class="empty-state">
              <i class="fa-solid fa-scroll empty-icon"></i>
              <p>Your decree scroll is clean. Write down a daily goal on the left to begin organizing your schedule.</p>
            </div>
            <div id="tasks-list" class="tasks-list">
              <!-- Dynamic task items go here -->
            </div>
          </div>
        </div>

        <!-- Sticky Notes Wall -->
        <div class="panel-card corkboard-card tilt-target">
          <div class="corkboard-header">
            <div>
              <h3><i class="fa-solid fa-thumbtack"></i> DESK STICKY NOTES</h3>
              <p class="corkboard-subtitle">Double-click corkboard to pin note. Hold pushpins to drag them around!</p>
            </div>
            <div class="corkboard-actions">
              <button id="add-sticky-btn" class="btn-corkboard-action"><i class="fa-solid fa-plus"></i> Pin Note</button>
              <button id="clear-stickies-btn" class="btn-corkboard-action btn-danger-cork"><i class="fa-solid fa-trash-sweep"></i> Sweep Wall</button>
            </div>
          </div>

          <!-- Corkboard viewport -->
          <div class="corkboard-viewport" id="corkboard">
            <div id="empty-corkboard-state" class="empty-state corkboard-empty">
              <i class="fa-solid fa-thumbtack empty-icon animate-bounce-slow"></i>
              <p>Double-click empty board to scatter sticky notes for quick thoughts, calculations, or reminders.</p>
            </div>
            
            <!-- Draggable sticky notes will be generated here -->
          </div>
        </div>

      </section>
    </main>
  </div>

  <!-- HELP GUIDE MODAL -->
  <div id="help-modal" class="modal-overlay">
    <div class="modal-content help-card animated-zoom">
      <h2><i class="fa-solid fa-book-open"></i> Desk Guide & Features</h2>
      <div class="help-body">
        <p>This layout focuses on **essential, highly useful to-do list features** and **satisfying premium animations**:</p>
        
        <h3>📝 Structured Task Decrees</h3>
        <p>Create tasks with deadlines, subtasks, priorities, and categories. When completed, checkmarks draw themselves dynamically. Deleting crumples the card in 3D space.</p>
        
        <h3>🔄 Daily Reset (Recurring Tasks)</h3>
        <p>Check the <strong>Repeat Quest Daily</strong> box. Completed daily tasks will automatically reset back to active status at midnight so you can re-conquer them tomorrow!</p>
        
        <h3>⏰ Deadline Alarms</h3>
        <p>Set a deadline. When the due time arrives, a **soft zen bell chime** will sound, and a beautiful notification card will slide down from the top of the desk to remind you.</p>

        <h3>📊 Daily Progress HUD</h3>
        <p>The circular progress ring tracks your completions for today. Fill it to 100% to witness a screen-wide celebratory sparkle explosion!</p>

        <h3>📌 Draggable 3D Sticky Notes</h3>
        <p>Pin notes for quick ideas. Hover to see them tilt in 3D. Drag them around by their red pushpins to arrange your work desk.</p>
      </div>
      <button id="close-help-btn" class="btn-submit">Close & Begin</button>
    </div>
  </div>

  <!-- Standalone inline JS Application engine -->
  <script>
    // --- APPLICATION STATE ---
    let state = {
      tasks: [],
      notes: [],
      soundEffects: true,
      theme: 'warm',
      lastCheckDate: ''
    };

    // Initial default sticky notes if empty
    const DEFAULT_NOTES = [
      { id: 'note-welcome', text: "📌 Sticky Reminders!\n\n• Double-click anywhere on the corkboard to pin a new note.\n• Drag notes by their red pushpins to organize your desk.\n• Change paper colors below.\n• Type notes directly!", color: 'yellow', x: 20, y: 30 },
      { id: 'note-breathing', text: "🌱 Daily Reminder:\n\nTake deep breaths. Drink water. Stretch your body. Success is the sum of small daily achievements.", color: 'green', x: 220, y: 150 }
    ];

    let activeFormSubtasks = [];
    let editingTaskId = null;
    let lastProgressPercent = 0; // Check to trigger 100% celebrations

    // --- WEB AUDIO API ZEN SOUND GENERATOR ---
    let audioCtx = null;

    function initAudio() {
      if (!audioCtx) {
        audioCtx = new (window.AudioContext || window.webkitAudioContext)();
      }
    }

    // Unlocks AudioContext on first touch/click (crucial for mobile iOS/Android Chrome & Safari)
    function unlockAudioContext() {
      initAudio();
      if (audioCtx) {
        if (audioCtx.state === 'suspended') {
          audioCtx.resume().then(() => {
            removeUnlockListeners();
          });
        } else {
          removeUnlockListeners();
        }
      }
    }

    function removeUnlockListeners() {
      window.removeEventListener('click', unlockAudioContext);
      window.removeEventListener('touchstart', unlockAudioContext);
    }

    window.addEventListener('click', unlockAudioContext);
    window.addEventListener('touchstart', unlockAudioContext);

    // Tibetan Singing Bowl Chime (for Alarms & completions)
    function playTibetanBowlChime() {
      if (!state.soundEffects) return;
      initAudio();
      if (audioCtx.state === 'suspended') audioCtx.resume();

      const now = audioCtx.currentTime;
      const duration = 5.0; // Long ringing decay
      const fundamental = 160.0; // Resonant frequency
      
      // Harmonic profiles
      const harmonics = [
        { mult: 1.00, vol: 0.16, decay: 1.0 },
        { mult: 1.99, vol: 0.10, decay: 0.85 },
        { mult: 3.01, vol: 0.08, decay: 0.65 },
        { mult: 4.08, vol: 0.04, decay: 0.45 },
        { mult: 5.15, vol: 0.02, decay: 0.30 }
      ];

      harmonics.forEach(h => {
        const osc = audioCtx.createOscillator();
        const gain = audioCtx.createGain();
        
        osc.type = 'sine';
        osc.frequency.setValueAtTime(fundamental * h.mult, now);
        
        gain.gain.setValueAtTime(0, now);
        gain.gain.linearRampToValueAtTime(h.vol, now + 0.12); // slow warm attack
        gain.gain.exponentialRampToValueAtTime(0.0001, now + duration * h.decay);
        
        osc.connect(gain);
        gain.connect(audioCtx.destination);
        
        osc.start(now);
        osc.stop(now + duration);
      });
    }

    // Gentle double chime (for Checklist completion)
    function playTaskCompleteChime() {
      if (!state.soundEffects) return;
      initAudio();
      if (audioCtx.state === 'suspended') audioCtx.resume();

      const now = audioCtx.currentTime;
      
      // Note 1 (E5)
      const osc1 = audioCtx.createOscillator();
      const gain1 = audioCtx.createGain();
      osc1.type = 'sine';
      osc1.frequency.setValueAtTime(659.25, now);
      gain1.gain.setValueAtTime(0, now);
      gain1.gain.linearRampToValueAtTime(0.08, now + 0.02);
      gain1.gain.exponentialRampToValueAtTime(0.0001, now + 0.35);
      osc1.connect(gain1);
      gain1.connect(audioCtx.destination);
      osc1.start(now);
      osc1.stop(now + 0.4);

      // Note 2 (A5) shortly after
      setTimeout(() => {
        if (!state.soundEffects) return;
        const now2 = audioCtx.currentTime;
        const osc2 = audioCtx.createOscillator();
        const gain2 = audioCtx.createGain();
        osc2.type = 'sine';
        osc2.frequency.setValueAtTime(880.00, now2);
        gain2.gain.setValueAtTime(0, now2);
        gain2.gain.linearRampToValueAtTime(0.06, now2 + 0.02);
        gain2.gain.exponentialRampToValueAtTime(0.0001, now2 + 0.55);
        osc2.connect(gain2);
        gain2.connect(audioCtx.destination);
        osc2.start(now2);
        osc2.stop(now2 + 0.6);
      }, 100);
    }

    // Soft woodblock clock click
    function playWoodClick() {
      if (!state.soundEffects) return;
      initAudio();
      if (audioCtx.state === 'suspended') audioCtx.resume();

      const now = audioCtx.currentTime;
      const osc = audioCtx.createOscillator();
      const gain = audioCtx.createGain();
      
      osc.type = 'triangle';
      osc.frequency.setValueAtTime(400, now);
      osc.frequency.exponentialRampToValueAtTime(80, now + 0.04);
      
      gain.gain.setValueAtTime(0.1, now);
      gain.gain.exponentialRampToValueAtTime(0.0001, now + 0.045);
      
      osc.connect(gain);
      gain.connect(audioCtx.destination);
      osc.start(now);
      osc.stop(now + 0.05);
    }

    // Swish (for deletion)
    function playDeleteSwish() {
      if (!state.soundEffects) return;
      initAudio();
      if (audioCtx.state === 'suspended') audioCtx.resume();

      const now = audioCtx.currentTime;
      const osc = audioCtx.createOscillator();
      const gain = audioCtx.createGain();
      
      osc.type = 'sine';
      osc.frequency.setValueAtTime(250, now);
      osc.frequency.exponentialRampToValueAtTime(70, now + 0.2);
      
      gain.gain.setValueAtTime(0.08, now);
      gain.gain.exponentialRampToValueAtTime(0.0001, now + 0.2);
      
      osc.connect(gain);
      gain.connect(audioCtx.destination);
      osc.start(now);
      osc.stop(now + 0.22);
    }


    // --- ZEN CANVAS PARTICLES ENGINE ---
    const canvas = document.getElementById('ambient-canvas');
    const canvasCtx = canvas.getContext('2d');
    let particles = [];

    function resizeCanvas() {
      canvas.width = window.innerWidth;
      canvas.height = window.innerHeight;
    }
    window.addEventListener('resize', resizeCanvas);
    resizeCanvas();

    class ZenParticle {
      constructor(x, y, isSparkle = false) {
        this.x = x !== undefined ? x : Math.random() * canvas.width;
        this.y = y !== undefined ? y : Math.random() * canvas.height;
        this.isSparkle = isSparkle;
        
        if (isSparkle) {
          const angle = Math.random() * Math.PI * 2;
          const speed = Math.random() * 5 + 1.5;
          this.vx = Math.cos(angle) * speed;
          this.vy = Math.sin(angle) * speed - Math.random() * 2;
          this.size = Math.random() * 4 + 1.5;
          this.alpha = 1.0;
          this.decay = Math.random() * 0.015 + 0.01;
          this.gravity = 0.08;
        } else {
          this.vx = (Math.random() - 0.5) * 0.15;
          this.vy = -Math.random() * 0.2 - 0.05;
          this.size = Math.random() * 2 + 0.5;
          this.alpha = Math.random() * 0.25 + 0.05;
          this.decay = 0;
          this.gravity = 0;
        }
      }

      update() {
        this.x += this.vx;
        this.y += this.vy;
        this.vy += this.gravity;
        
        if (this.isSparkle) {
          this.alpha -= this.decay;
        } else {
          if (this.y < 0) {
            this.y = canvas.height;
            this.x = Math.random() * canvas.width;
          }
          if (this.x < 0 || this.x > canvas.width) {
            this.x = Math.random() * canvas.width;
          }
        }
      }

      draw() {
        canvasCtx.save();
        canvasCtx.globalAlpha = this.alpha;
        canvasCtx.fillStyle = state.theme === 'warm' ? '#6e826b' : '#53759a';
        if (this.isSparkle) {
          canvasCtx.shadowBlur = 8;
          canvasCtx.shadowColor = state.theme === 'warm' ? '#c58671' : '#bd8a61';
          canvasCtx.fillStyle = state.theme === 'warm' ? '#c58671' : '#bd8a61';
        }
        canvasCtx.beginPath();
        canvasCtx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
        canvasCtx.fill();
        canvasCtx.restore();
      }
    }

    function initAmbientParticles() {
      particles = [];
      const count = Math.min(25, Math.floor(window.innerWidth / 50));
      for (let i = 0; i < count; i++) {
        particles.push(new ZenParticle());
      }
    }
    initAmbientParticles();

    function spawnSparkles(x, y, count = 35) {
      for (let i = 0; i < count; i++) {
        particles.push(new ZenParticle(x, y, true));
      }
    }

    function animateParticles() {
      canvasCtx.clearRect(0, 0, canvas.width, canvas.height);
      particles = particles.filter(p => !p.isSparkle || p.alpha > 0);
      particles.forEach(p => {
        p.update();
        p.draw();
      });
      requestAnimationFrame(animateParticles);
    }
    animateParticles();

    // --- 3D TILT PARALLAX EFFECT ENGINE ---
    function apply3DTilt(e, card) {
      const rect = card.getBoundingClientRect();
      const w = rect.width;
      const h = rect.height;
      
      const x = e.clientX - rect.left;
      const y = e.clientY - rect.top;
      
      const dx = (x - w / 2) / (w / 2);
      const dy = (y - h / 2) / (h / 2);
      
      const tiltMax = card.classList.contains('sticky-note') ? 10 : 5;
      const rotateX = -dy * tiltMax;
      const rotateY = dx * tiltMax;
      
      let baseRotation = 0;
      if (card.classList.contains('sticky-note')) {
        const seed = parseInt(card.id.split('-').pop()) || 0;
        baseRotation = (seed % 5) - 2.5;
      }
      
      card.style.transform = `perspective(600px) rotateX(${rotateX}deg) rotateY(${rotateY}deg) rotate(${baseRotation}deg) scale(1.02)`;
      card.style.boxShadow = '0 16px 30px rgba(112, 101, 88, 0.12)';
    }

    function reset3DTilt(card) {
      let baseRotation = 0;
      if (card.classList.contains('sticky-note')) {
        const seed = parseInt(card.id.split('-').pop()) || 0;
        baseRotation = (seed % 5) - 2.5;
      }
      
      card.style.transform = `perspective(600px) rotateX(0deg) rotateY(0deg) rotate(${baseRotation}deg) scale(1)`;
      card.style.boxShadow = card.classList.contains('sticky-note') ? 'var(--shadow-note)' : 'var(--shadow-card)';
    }

    function init3DTiltListeners() {
      // Tilt hovers are only suitable for desktop devices with mice hovers (prevents bugs on mobile touch)
      if (window.matchMedia("(pointer: coarse)").matches) return;

      document.querySelectorAll('.tilt-target, .task-item, .sticky-note').forEach(card => {
        if (card.dataset.tiltActive) return;
        card.dataset.tiltActive = "true";
        
        card.addEventListener('mousemove', (e) => {
          if (card.classList.contains('dragging')) return;
          apply3DTilt(e, card);
        });
        
        card.addEventListener('mouseleave', () => {
          reset3DTilt(card);
        });
      });
    }


    // --- CORE LOGIC HANDLERS ---

    function loadState() {
      const saved = localStorage.getItem('cozy_goals_state_polished');
      if (saved) {
        try {
          state = { ...state, ...JSON.parse(saved) };
        } catch(e) {
          console.error("Error loading state", e);
        }
      } else {
        state.notes = [...DEFAULT_NOTES];
        state.lastCheckDate = new Date().toDateString();
        saveState();
      }
      
      document.body.setAttribute('data-theme', state.theme || 'warm');
      document.getElementById('toggle-sound-effects').querySelector('i').className = 
        state.soundEffects ? 'fa-solid fa-volume-high' : 'fa-solid fa-volume-xmark';
      document.getElementById('toggle-theme').querySelector('i').className = 
        state.theme === 'warm' ? 'fa-solid fa-sun' : 'fa-solid fa-snowflake';

      checkDailyRecurringResets();
    }

    function saveState() {
      localStorage.setItem('cozy_goals_state_polished', JSON.stringify(state));
    }

    function checkDailyRecurringResets() {
      const today = new Date().toDateString();
      if (state.lastCheckDate !== today) {
        let resetMade = false;
        state.tasks.forEach(t => {
          if (t.recurring && t.completed) {
            t.completed = false;
            t.notified = false;
            if (t.subtasks) {
              t.subtasks.forEach(sub => sub.completed = false);
            }
            resetMade = true;
          }
        });
        
        state.lastCheckDate = today;
        saveState();
        
        if (resetMade) {
          setTimeout(() => {
            triggerNotificationBanner("Daily Reset Completed!", "Your recurring tasks have been reset to active. Have a great day!");
          }, 1000);
        }
      }
    }

    function triggerNotificationBanner(title, desc) {
      playTibetanBowlChime();
      
      document.getElementById('noti-title').innerText = title;
      document.getElementById('noti-desc').innerText = desc;
      
      const banner = document.getElementById('notification-banner');
      banner.classList.add('active');
      
      setTimeout(() => {
        banner.classList.remove('active');
      }, 8000);
    }

    // --- DYNAMIC RENDER ENGINES ---

    function updateProgressHUD() {
      const fillRing = document.getElementById('progress-ring-fill');
      const percentText = document.getElementById('progress-text');
      const descText = document.getElementById('progress-desc');
      const card = document.querySelector('.progress-card');
      
      const total = state.tasks.length;
      const completed = state.tasks.filter(t => t.completed).length;
      const percent = total === 0 ? 0 : Math.round((completed / total) * 100);
      
      const circumference = 314.16;
      const offset = circumference - (percent / 100) * circumference;
      
      fillRing.style.strokeDashoffset = offset;
      percentText.innerText = `${percent}%`;
      
      if (total === 0) {
        descText.innerText = "Add a task below to start your progress.";
        card.classList.remove('complete');
      } else if (percent === 100) {
        descText.innerHTML = "✨ <strong>Desk Accomplished!</strong> Stellar work today.";
        card.classList.add('complete');
        
        if (lastProgressPercent < 100) {
          trigger100PercentCelebration();
        }
      } else {
        descText.innerText = `${completed} of ${total} objectives cleared.`;
        card.classList.remove('complete');
      }
      
      lastProgressPercent = percent;
    }

    function trigger100PercentCelebration() {
      const w = window.innerWidth;
      const h = window.innerHeight;
      
      for (let i = 0; i < 4; i++) {
        setTimeout(() => {
          spawnSparkles(
            (w / 5) * (i + 1) + (Math.random() - 0.5) * 50, 
            h / 2 + (Math.random() - 0.5) * 100, 
            25
          );
        }, i * 200);
      }
    }

    function renderTasks() {
      const list = document.getElementById('tasks-list');
      const emptyState = document.getElementById('empty-tasks-state');
      
      const query = document.getElementById('search-tasks').value.toLowerCase().trim();
      const filterCat = document.getElementById('filter-category').value;
      const filterPri = document.getElementById('filter-priority').value;

      let filtered = state.tasks.filter(t => {
        const matchesSearch = t.title.toLowerCase().includes(query) || (t.desc && t.desc.toLowerCase().includes(query));
        const matchesCat = (filterCat === 'All' || t.category === filterCat);
        const matchesPri = (filterPri === 'All' || t.priority === filterPri);
        return matchesSearch && matchesCat && matchesPri;
      });

      filtered.sort((a, b) => {
        if (a.completed !== b.completed) {
          return a.completed ? 1 : -1;
        }
        const priMap = { High: 3, Medium: 2, Low: 1 };
        if (priMap[b.priority] !== priMap[a.priority]) {
          return priMap[b.priority] - priMap[a.priority];
        }
        if (!a.dueDate) return 1;
        if (!b.dueDate) return -1;
        return new Date(`${a.dueDate} ${a.dueTime || '23:59'}`) - new Date(`${b.dueDate} ${b.dueTime || '23:59'}`);
      });

      const total = state.tasks.length;
      const completed = state.tasks.filter(t => t.completed).length;
      document.getElementById('task-completion-count').innerText = `${completed} / ${total}`;

      updateProgressHUD();

      if (filtered.length === 0) {
        list.innerHTML = '';
        emptyState.style.display = 'flex';
        return;
      }
      
      emptyState.style.display = 'none';

      list.innerHTML = filtered.map(t => {
        const isOverdue = t.dueDate && !t.completed && (new Date(`${t.dueDate} ${t.dueTime || '23:59'}`) < new Date());
        
        let dateStr = 'No deadline';
        if (t.dueDate) {
          const d = new Date(t.dueDate + 'T00:00:00');
          dateStr = d.toLocaleDateString(undefined, { month: 'short', day: 'numeric' });
          if (t.dueTime) {
            dateStr += ` @ ${formatTime(t.dueTime)}`;
          }
        }

        let subtaskHtml = '';
        if (t.subtasks && t.subtasks.length > 0) {
          subtaskHtml = `
            <ul class="task-item-subtasks">
              ${t.subtasks.map((s, index) => `
                <li class="task-subtask-node ${s.completed ? 'checked' : ''}" onclick="toggleTaskSubtask('${t.id}', ${index})">
                  <div class="subtask-node-checkbox">
                    <i class="fa-solid fa-check"></i>
                  </div>
                  <span>${escapeHTML(s.text)}</span>
                </li>
              `).join('')}
            </ul>
          `;
        }

        return `
          <div class="task-item ${t.completed ? 'completed' : ''}" id="task-${t.id}">
            <div class="task-item-header">
              <div class="task-item-left">
                <button class="task-checkbox-btn" onclick="toggleTaskCompletion('${t.id}')" title="Complete Goal">
                  <svg class="task-checkbox-svg" viewBox="0 0 12 10">
                    <polyline class="checkmark-path" points="1.5 5 4.5 8 10.5 1.5"></polyline>
                  </svg>
                </button>
                <div class="task-details">
                  <span class="task-title">${escapeHTML(t.title)}</span>
                  ${t.desc ? `<p class="task-desc">${escapeHTML(t.desc)}</p>` : ''}
                </div>
              </div>
              <div class="task-actions">
                ${!t.completed ? `
                  <button class="btn-task-action" onclick="editTask('${t.id}')" title="Edit Goal"><i class="fa-solid fa-pen-to-square"></i></button>
                ` : ''}
                <button class="btn-task-action delete-btn" onclick="deleteTask('${t.id}')" title="Abandon Goal"><i class="fa-solid fa-trash-can"></i></button>
              </div>
            </div>
            
            ${subtaskHtml}

            <div class="task-item-footer">
              <div class="task-meta-left">
                <span class="task-tag">${escapeHTML(t.category)}</span>
                <div class="task-due ${isOverdue ? 'overdue' : ''}">
                  <i class="fa-regular ${isOverdue ? 'fa-circle-exclamation' : 'fa-calendar'}"></i>
                  <span>${dateStr} ${isOverdue ? '(Overdue)' : ''}</span>
                </div>
                ${t.recurring ? `<span class="task-recurring-badge"><i class="fa-solid fa-arrows-spin"></i> Daily</span>` : ''}
              </div>
              <div class="priority-badge">
                <span class="priority-dot ${t.priority.toLowerCase()}"></span>
                <span>${t.priority}</span>
              </div>
            </div>
          </div>
        `;
      }).join('');

      init3DTiltListeners();
    }

    function toggleTaskCompletion(id) {
      const task = state.tasks.find(t => t.id === id);
      if (!task) return;
      
      task.completed = !task.completed;
      
      if (task.completed) {
        playTaskCompleteChime();
        
        const btn = document.querySelector(`#task-${id} .task-checkbox-btn`);
        if (btn) {
          const rect = btn.getBoundingClientRect();
          spawnSparkles(rect.left + rect.width / 2, rect.top + rect.height / 2, 18);
        }
        
        if (task.subtasks) {
          task.subtasks.forEach(s => s.completed = true);
        }
      } else {
        playWoodClick();
      }
      
      saveState();
      renderTasks();
    }

    function toggleTaskSubtask(taskId, subtaskIndex) {
      const task = state.tasks.find(t => t.id === taskId);
      if (!task) return;
      
      task.subtasks[subtaskIndex].completed = !task.subtasks[subtaskIndex].completed;
      playWoodClick();
      
      saveState();
      renderTasks();
    }

    function deleteTask(id) {
      playDeleteSwish();
      
      const card = document.getElementById(`task-${id}`);
      if (card) {
        card.classList.add('crumpling-delete');
      }
      
      setTimeout(() => {
        state.tasks = state.tasks.filter(t => t.id !== id);
        saveState();
        renderTasks();
      }, 400);
    }

    function editTask(id) {
      const task = state.tasks.find(t => t.id === id);
      if (!task) return;
      
      playWoodClick();
      editingTaskId = id;
      
      document.getElementById('task-title').value = task.title;
      document.getElementById('task-desc').value = task.desc || '';
      document.getElementById('task-category').value = task.category;
      document.getElementById('task-priority').value = task.priority;
      document.getElementById('task-date').value = task.dueDate || '';
      document.getElementById('task-time').value = task.dueTime || '23:59';
      document.getElementById('task-recurring').checked = task.recurring || false;
      
      activeFormSubtasks = [...task.subtasks];
      renderFormSubtaskPreview();
      
      const submitBtn = document.getElementById('submit-task-btn');
      submitBtn.innerHTML = `<i class="fa-solid fa-pen-to-square"></i> Save Goal Decree`;
      
      document.getElementById('task-form').scrollIntoView({ behavior: 'smooth' });
    }


    // --- DRAGGABLE STICKY NOTES ENGINE ---
    let activeDraggingNote = null;
    let dragOffsetX = 0;
    let dragOffsetY = 0;

    function renderStickyNotes() {
      const corkboard = document.getElementById('corkboard');
      const emptyState = document.getElementById('empty-corkboard-state');
      
      document.querySelectorAll('.sticky-note').forEach(n => n.remove());
      
      if (state.notes.length === 0) {
        emptyState.style.display = 'flex';
        return;
      }
      
      emptyState.style.display = 'none';
      
      state.notes.forEach(note => {
        const card = document.createElement('div');
        card.className = `sticky-note ${note.color}`;
        card.id = note.id;
        card.style.left = `${note.x}px`;
        card.style.top = `${note.y}px`;
        
        const seed = parseInt(note.id.split('-').pop()) || 0;
        const rotation = (seed % 5) - 2.5; 
        card.style.transform = `rotate(${rotation}deg)`;
        
        card.innerHTML = `
          <div class="sticky-note-pin"><i class="fa-solid fa-thumbtack"></i></div>
          <textarea class="sticky-note-content" placeholder="Type a reminder...">${escapeHTML(note.text)}</textarea>
          <div class="sticky-note-footer">
            <div class="note-colors">
              <button class="btn-note-color color-yellow" data-color="yellow" title="Yellow Note"></button>
              <button class="btn-note-color color-pink" data-color="pink" title="Pink Note"></button>
              <button class="btn-note-color color-green" data-color="green" title="Green Note"></button>
              <button class="btn-note-color color-purple" data-color="purple" title="Purple Note"></button>
              <button class="btn-note-color color-blue" data-color="blue" title="Blue Note"></button>
            </div>
            <button class="btn-note-delete" title="Delete Note"><i class="fa-solid fa-trash-can"></i></button>
          </div>
        `;
        
        const textarea = card.querySelector('.sticky-note-content');
        textarea.addEventListener('input', (e) => {
          note.text = e.target.value;
          saveState();
        });
        
        card.querySelectorAll('.btn-note-color').forEach(btn => {
          btn.addEventListener('click', (e) => {
            e.stopPropagation();
            const col = btn.dataset.color;
            card.className = `sticky-note ${col}`;
            note.color = col;
            playWoodClick();
            saveState();
          });
        });
        
        card.querySelector('.btn-note-delete').addEventListener('click', (e) => {
          e.stopPropagation();
          playDeleteSwish();
          
          card.classList.add('crumpling-delete');
          
          setTimeout(() => {
            state.notes = state.notes.filter(n => n.id !== note.id);
            saveState();
            renderStickyNotes();
          }, 400);
        });
        
        const pin = card.querySelector('.sticky-note-pin');
        
        pin.addEventListener('mousedown', (e) => {
          e.preventDefault();
          startDragging(card, note, e.clientX, e.clientY);
        });
        
        pin.addEventListener('touchstart', (e) => {
          if (e.touches.length === 1) {
            e.preventDefault();
            startDragging(card, note, e.touches[0].clientX, e.touches[0].clientY);
          }
        }, { passive: false });
        
        corkboard.appendChild(card);
      });

      init3DTiltListeners();
    }

    function startDragging(element, noteObject, clientX, clientY) {
      initAudio();
      playWoodClick();
      
      activeDraggingNote = { element, note: noteObject };
      element.classList.add('dragging');
      
      const rect = element.getBoundingClientRect();
      dragOffsetX = clientX - rect.left;
      dragOffsetY = clientY - rect.top;
      
      document.querySelectorAll('.sticky-note').forEach(n => n.style.zIndex = 5);
      element.style.zIndex = 100;
    }

    function handleDragging(clientX, clientY) {
      const corkboard = document.getElementById('corkboard');
      const boardRect = corkboard.getBoundingClientRect();
      const noteElement = activeDraggingNote.element;
      
      let newX = clientX - boardRect.left - dragOffsetX;
      let newY = clientY - boardRect.top - dragOffsetY;
      
      const maxLeft = boardRect.width - noteElement.offsetWidth - 2;
      const maxTop = boardRect.height - noteElement.offsetHeight - 2;
      
      newX = Math.max(2, Math.min(newX, maxLeft));
      newY = Math.max(2, Math.min(newY, maxTop));
      
      noteElement.style.left = `${newX}px`;
      noteElement.style.top = `${newY}px`;
      
      activeDraggingNote.note.x = newX;
      activeDraggingNote.note.y = newY;
    }

    function endDragging() {
      if (!activeDraggingNote) return;
      
      activeDraggingNote.element.classList.remove('dragging');
      reset3DTilt(activeDraggingNote.element);
      activeDraggingNote = null;
      saveState();
    }

    document.addEventListener('mousemove', (e) => {
      if (activeDraggingNote) handleDragging(e.clientX, e.clientY);
    });

    document.addEventListener('touchmove', (e) => {
      if (activeDraggingNote && e.touches.length === 1) {
        handleDragging(e.touches[0].clientX, e.touches[0].clientY);
      }
    }, { passive: false });

    document.addEventListener('mouseup', endDragging);
    document.addEventListener('touchend', endDragging);

    function spawnStickyNote(x = 40, y = 40) {
      const colors = ['yellow', 'pink', 'green', 'purple', 'blue'];
      const randomColor = colors[Math.floor(Math.random() * colors.length)];
      const timestamp = Date.now();
      
      const newNote = {
        id: `note-${timestamp}`,
        text: '',
        color: randomColor,
        x: x,
        y: y
      };
      
      state.notes.push(newNote);
      saveState();
      renderStickyNotes();
      
      setTimeout(() => {
        const el = document.getElementById(newNote.id);
        if (el) el.querySelector('.sticky-note-content').focus();
      }, 100);
    }

    document.getElementById('corkboard').addEventListener('dblclick', (e) => {
      if (e.target.id === 'corkboard' || e.target.id === 'empty-corkboard-state') {
        const rect = document.getElementById('corkboard').getBoundingClientRect();
        let x = e.clientX - rect.left - 85; 
        let y = e.clientY - rect.top - 85;
        
        x = Math.max(10, Math.min(x, rect.width - 180));
        y = Math.max(10, Math.min(y, rect.height - 180));
        
        spawnStickyNote(x, y);
      }
    });


    // --- CREATOR FORM STEPS CHEKLIST ---
    function handleAddFormSubtask() {
      const input = document.getElementById('subtask-input');
      const text = input.value.trim();
      if (!text) return;
      
      activeFormSubtasks.push({ text: text, completed: false });
      input.value = '';
      playWoodClick();
      renderFormSubtaskPreview();
    }

    function removeFormSubtask(index) {
      activeFormSubtasks.splice(index, 1);
      playDeleteSwish();
      renderFormSubtaskPreview();
    }

    function renderFormSubtaskPreview() {
      const list = document.getElementById('subtask-form-list');
      list.innerHTML = activeFormSubtasks.map((sub, index) => `
        <li class="subtask-form-item">
          <span>${escapeHTML(sub.text)}</span>
          <button type="button" onclick="removeFormSubtask(${index})"><i class="fa-solid fa-circle-xmark"></i></button>
        </li>
      `).join('');
    }


    // --- ALARM DEADLINES MONITOR LOOP ---
    function runDeadlineMonitor() {
      const now = new Date();
      let updated = false;
      
      state.tasks.forEach(t => {
        if (!t.completed && !t.notified && t.dueDate) {
          const deadline = new Date(`${t.dueDate} ${t.dueTime || '23:59'}`);
          if (now >= deadline) {
            t.notified = true;
            updated = true;
            
            triggerNotificationBanner(
              `Deadline Alarm: "${t.title}"`, 
              `Objective reached its deadline! Take a moment to review and complete it.`
            );
          }
        }
      });
      
      if (updated) {
        saveState();
        renderTasks();
      }
    }

    setInterval(runDeadlineMonitor, 10000);


    // --- INIT & LISTENERS ---

    document.addEventListener('DOMContentLoaded', () => {
      loadState();
      renderTasks();
      renderStickyNotes();
      
      const days = ['Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday'];
      const dayName = days[new Date().getDay()].toUpperCase();
      document.getElementById('current-day-name').innerText = dayName;

      if (!localStorage.getItem('cozy_goals_first_time')) {
        document.getElementById('help-modal').classList.add('active');
        localStorage.setItem('cozy_goals_first_time', 'completed');
      }

      // --- TOP CONTROLS ---
      
      // Sound FX
      const soundFxBtn = document.getElementById('toggle-sound-effects');
      soundFxBtn.addEventListener('click', () => {
        state.soundEffects = !state.soundEffects;
        soundFxBtn.querySelector('i').className = 
          state.soundEffects ? 'fa-solid fa-volume-high' : 'fa-solid fa-volume-xmark';
        playWoodClick();
        saveState();
      });

      // Theme
      const themeBtn = document.getElementById('toggle-theme');
      themeBtn.addEventListener('click', () => {
        state.theme = state.theme === 'warm' ? 'cool' : 'warm';
        document.body.setAttribute('data-theme', state.theme);
        themeBtn.querySelector('i').className = 
          state.theme === 'warm' ? 'fa-solid fa-sun' : 'fa-solid fa-snowflake';
        playWoodClick();
        saveState();
      });

      // Modal guides
      document.getElementById('show-help').addEventListener('click', () => {
        playWoodClick();
        document.getElementById('help-modal').classList.add('active');
      });
      document.getElementById('close-help-btn').addEventListener('click', () => {
        playWoodClick();
        document.getElementById('help-modal').classList.remove('active');
      });
      document.getElementById('close-notification-btn').addEventListener('click', () => {
        document.getElementById('notification-banner').classList.remove('active');
      });

      // --- CORKBOARD BUTTONS ---
      document.getElementById('add-sticky-btn').addEventListener('click', () => {
        const x = 50 + Math.random() * 80;
        const y = 50 + Math.random() * 80;
        spawnStickyNote(x, y);
      });
      
      document.getElementById('clear-stickies-btn').addEventListener('click', () => {
        if (state.notes.length === 0) return;
        const ok = confirm("Do you want to sweep all sticky notes off your desk corkboard?");
        if (ok) {
          playDeleteSwish();
          state.notes = [];
          saveState();
          renderStickyNotes();
        }
      });

      // --- FORM SUBMITS ---
      document.getElementById('btn-add-subtask').addEventListener('click', handleAddFormSubtask);
      document.getElementById('subtask-input').addEventListener('keydown', (e) => {
        if (e.key === 'Enter') {
          e.preventDefault();
          handleAddFormSubtask();
        }
      });

      document.getElementById('task-form').addEventListener('submit', (e) => {
        e.preventDefault();
        playWoodClick();
        
        const titleInput = document.getElementById('task-title');
        const descInput = document.getElementById('task-desc');
        const categorySelect = document.getElementById('task-category');
        const prioritySelect = document.getElementById('task-priority');
        const dateInput = document.getElementById('task-date');
        const timeInput = document.getElementById('task-time');
        const recurringCheckbox = document.getElementById('task-recurring');
        
        if (editingTaskId) {
          const task = state.tasks.find(t => t.id === editingTaskId);
          if (task) {
            task.title = titleInput.value.trim();
            task.desc = descInput.value.trim();
            task.category = categorySelect.value;
            task.priority = prioritySelect.value;
            task.dueDate = dateInput.value || null;
            task.dueTime = dateInput.value ? timeInput.value : null;
            task.recurring = recurringCheckbox.checked;
            task.subtasks = [...activeFormSubtasks];
            task.notified = false;
          }
          editingTaskId = null;
          document.getElementById('submit-task-btn').innerHTML = `<i class="fa-solid fa-feather-pointed"></i> Decree Goal Objective`;
        } else {
          const newTask = {
            id: 'task-' + Date.now(),
            title: titleInput.value.trim(),
            desc: descInput.value.trim(),
            category: categorySelect.value,
            priority: prioritySelect.value,
            dueDate: dateInput.value || null,
            dueTime: dateInput.value ? timeInput.value : null,
            recurring: recurringCheckbox.checked,
            subtasks: [...activeFormSubtasks],
            completed: false,
            notified: false,
            createdDate: Date.now()
          };
          state.tasks.push(newTask);
        }
        
        titleInput.value = '';
        descInput.value = '';
        dateInput.value = '';
        timeInput.value = '23:59';
        categorySelect.value = 'Personal';
        prioritySelect.value = 'Medium';
        recurringCheckbox.checked = false;
        activeFormSubtasks = [];
        renderFormSubtaskPreview();
        
        saveState();
        renderTasks();
      });

      // --- FILTERS ---
      document.getElementById('search-tasks').addEventListener('input', renderTasks);
      document.getElementById('filter-category').addEventListener('change', renderTasks);
      document.getElementById('filter-priority').addEventListener('change', renderTasks);
    });

    // --- HELPER UTILS ---

    function escapeHTML(str) {
      if (!str) return '';
      return str.replace(/[&<>'"]/g, 
        tag => ({
          '&': '&amp;',
          '<': '&lt;',
          '>': '&gt;',
          "'": '&#39;',
          '"': '&quot;'
        }[tag] || tag)
      );
    }

    function formatTime(time24) {
      if (!time24) return '';
      const [hourStr, minStr] = time24.split(':');
      let hour = parseInt(hourStr);
      const ampm = hour >= 12 ? 'PM' : 'AM';
      hour = hour % 12 || 12;
      return `${hour}:${minStr} ${ampm}`;
    }
  </script>
</body>
</html>
