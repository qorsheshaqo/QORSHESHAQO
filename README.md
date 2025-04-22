<!DOCTYPE html>
<html lang="fr">
<head>
  <!-- Basic Meta Tags -->
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="To-Do List Premium - Organisez vos tâches avec style 🇸🇴">
  <meta name="keywords" content="To-Do, Tasks, Organisation, Somalie, Islamic, Productivity">
  <meta name="author" content="Your Name">

  <!-- Open Graph / Facebook Meta Tags -->
  <meta property="og:type" content="website">
  <meta property="og:url" content="https://yourwebsite.com/todo-list">
  <meta property="og:title" content="To-Do List Premium | Somalie">
  <meta property="og:description" content="Organisez vos tâches avec style inspiré de la Somalie 🇸🇴">
  <meta property="og:image" content="https://yourwebsite.com/images/todo-preview.png">

  <!-- Twitter Meta Tags -->
  <meta name="twitter:card" content="summary_large_image">
  <meta name="twitter:url" content="https://yourwebsite.com/todo-list">
  <meta name="twitter:title" content="To-Do List Premium | Somalie">
  <meta name="twitter:description" content="Organisez vos tâches avec style inspiré de la Somalie 🇸🇴">
  <meta name="twitter:image" content="https://yourwebsite.com/images/todo-preview.png">

  <!-- Favicon -->
  <link rel="icon" type="image/png" href="favicon.png">

  <!-- Font Awesome Icons -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

  <title>To-Do List Premium | Somalie</title>

  <style>
    :root {
      --somali-blue: #4189DD;
      --somali-blue-dark: #2A5A9A;
      --white: #FFFFFF;
      --light-gray: #F5F7FA;
      --dark-gray: #2C3E50;
      --black: #1A1A1A;
      --red: #E74C3C;
      --orange: #F39C12;
      --green: #2ECC71;
      --night-blue: #0d1b3a;
    }

    /* General Styles */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background-color: var(--light-gray);
      color: var(--black);
      min-height: 100vh;
      position: relative;
      overflow-x: hidden;
    }

    /* Somali Flag Background with Geometric Pattern */
    .somali-flag-bg {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-color: var(--somali-blue);
      background-image: 
        radial-gradient(circle at 10% 20%, rgba(255,255,255,0.1) 1px, transparent 1px),
        radial-gradient(circle at 50% 80%, rgba(255,255,255,0.1) 1px, transparent 1px);
      background-size: 40px 40px;
      animation: patternMove 20s linear infinite;
      z-index: -1;
      transition: all 0.5s ease;
    }

    @keyframes patternMove {
      0% { background-position: 0 0; }
      100% { background-position: 40px 40px; }
    }

    /* Somali Star */
    .somali-star {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      width: 250px;
      height: 250px;
      background-image: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><polygon points="50,5 63,37 97,37 70,57 83,95 50,72 17,95 30,57 3,37 37,37" fill="white"/></svg>');
      background-size: contain;
      opacity: 0.1;
    }

    /* Islamic Floating Icons */
    .floating-icon {
      position: fixed;
      width: 60px;
      opacity: 0.08;
      animation: float 10s ease-in-out infinite;
      z-index: -1;
    }

    @keyframes float {
      0%, 100% { transform: translateY(0) rotate(0deg); }
      50% { transform: translateY(-40px) rotate(5deg); }
    }

    /* Arabic Calligraphy Watermark */
    body::after {
      content: "﷽";
      position: fixed;
      bottom: 30px;
      right: 30px;
      font-size: 3rem;
      opacity: 0.05;
      font-family: 'Traditional Arabic', Arial, sans-serif;
      pointer-events: none;
      z-index: -1;
    }

    /* Main App Container */
    .app-container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 30px;
      background-color: rgba(255, 255, 255, 0.95);
      border-radius: 15px;
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
      backdrop-filter: blur(5px);
      margin-top: 30px;
      margin-bottom: 30px;
    }

    /* Header */
    header {
      text-align: center;
      margin-bottom: 30px;
      color: var(--somali-blue-dark);
    }

    h1 {
      font-size: 2.5rem;
      margin-bottom: 10px;
    }

    /* Control Panel */
    .control-panel {
      display: flex;
      gap: 15px;
      margin-bottom: 25px;
      flex-wrap: wrap;
    }

    /* Task Form */
    #task-form {
      display: flex;
      gap: 10px;
      flex-grow: 1;
    }

    #task-input {
      flex-grow: 1;
      padding: 12px 15px;
      border: 1px solid #ddd;
      border-radius: 8px;
      font-size: 1rem;
    }

    #priority-select, #category-select, #due-date {
      padding: 12px;
      border: 1px solid #ddd;
      border-radius: 8px;
      background-color: white;
    }

    #task-form button {
      padding: 12px 20px;
      background-color: var(--somali-blue);
      color: white;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      font-weight: bold;
      transition: all 0.3s;
    }

    #task-form button:hover {
      background-color: var(--somali-blue-dark);
    }

    /* Search Bar */
    #search-bar {
      flex-grow: 1;
      padding: 12px 15px;
      border: 1px solid #ddd;
      border-radius: 8px;
      font-size: 1rem;
    }

    /* Filter Buttons */
    .filter-buttons {
      display: flex;
      gap: 10px;
      margin-bottom: 20px;
      flex-wrap: wrap;
    }

    .filter-btn {
      padding: 8px 15px;
      background-color: var(--light-gray);
      border: none;
      border-radius: 20px;
      cursor: pointer;
      transition: all 0.3s;
    }

    .filter-btn:hover, .filter-btn.active {
      background-color: var(--somali-blue);
      color: white;
    }

    /* Task List */
    #task-list {
      list-style: none;
      padding: 0;
    }

    .task-item {
      display: flex;
      align-items: center;
      padding: 15px;
      margin-bottom: 10px;
      background-color: white;
      border-radius: 10px;
      box-shadow: 0 2px 5px rgba(0, 0, 0, 0.05);
      transition: all 0.3s;
      border-left: 4px solid transparent;
    }

    .task-item.completed {
      opacity: 0.7;
      background-color: #F9F9F9;
    }

    .task-item.completed .task-text {
      text-decoration: line-through;
      color: #777;
    }

    /* Priorities */
    .task-item.priority-high { border-left-color: var(--red); }
    .task-item.priority-medium { border-left-color: var(--orange); }
    .task-item.priority-low { border-left-color: var(--green); }

    .task-checkbox {
      margin-right: 15px;
      transform: scale(1.3);
      cursor: pointer;
    }

    .task-content {
      flex-grow: 1;
    }

    .task-text {
      font-size: 1.1rem;
      margin-bottom: 5px;
    }

    .task-meta {
      display: flex;
      gap: 15px;
      font-size: 0.85rem;
      color: #666;
    }

    .task-priority, .task-category {
      padding: 3px 8px;
      border-radius: 10px;
      font-size: 0.75rem;
      font-weight: bold;
    }

    .priority-high { background-color: #FFEBEE; color: var(--red); }
    .priority-medium { background-color: #FFF8E1; color: var(--orange); }
    .priority-low { background-color: #E8F5E9; color: var(--green); }

    .task-due.overdue { color: var(--red); font-weight: bold; }

    /* Task Actions */
    .task-actions {
      display: flex;
      gap: 10px;
    }

    .task-btn {
      background: none;
      border: none;
      cursor: pointer;
      font-size: 1rem;
      opacity: 0.7;
      transition: all 0.3s;
    }

    .task-btn:hover { opacity: 1; }

    .edit-btn { color: var(--somali-blue); }
    .delete-btn { color: var(--red); }

    /* Statistics */
    .stats {
      display: flex;
      justify-content: space-between;
      margin-top: 25px;
      padding-top: 15px;
      border-top: 1px solid #eee;
      font-size: 0.9rem;
    }

    .stat-item { display: flex; align-items: center; gap: 5px; }
    .stat-value { font-weight: bold; color: var(--somali-blue); }

    /* Dark Mode */
    body.dark-mode {
      background-color: var(--dark-gray);
      color: white;
    }

    body.dark-mode .app-container {
      background-color: rgba(30, 30, 30, 0.95);
      color: white;
    }

    body.dark-mode .task-item {
      background-color: #333;
      color: white;
    }

    /* Dark Mode Toggle */
    #dark-mode-toggle {
      position: fixed;
      top: 20px;
      right: 20px;
      background: var(--somali-blue);
      color: white;
      border: none;
      border-radius: 50%;
      width: 40px;
      height: 40px;
      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: center;
      z-index: 1000;
    }

    /* Language Toggle */
    #language-toggle {
      position: fixed;
      top: 70px;
      right: 20px;
      background: var(--somali-blue);
      color: white;
      border: none;
      padding: 5px 10px;
      border-radius: 5px;
      cursor: pointer;
      z-index: 1000;
    }

    /* Responsive */
    @media (max-width: 768px) {
      .app-container { padding: 20px; }
      #task-form { flex-direction: column; }
      .control-panel { flex-direction: column; }
      #language-toggle { top: 60px; }
    }
  </style>
</head>
<body>
  <!-- Somali Flag Background with Geometric Pattern -->
  <div class="somali-flag-bg">
    <div class="somali-star"></div>
    
    <!-- Islamic Floating Icons -->
    <svg class="floating-icon" style="top:15%; left:5%;" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100">
      <path d="M50,10 L70,30 L70,60 L60,60 L60,90 L40,90 L40,60 L30,60 L30,30 Z" fill="white"/>
      <path d="M50,5 L55,10 L45,10 Z" fill="white"/>
    </svg>
    
    <svg class="floating-icon" style="top:75%; left:85%;" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100">
      <circle cx="50" cy="50" r="40" fill="none" stroke="white" stroke-width="2"/>
      <path d="M50,10 A40,40 0 0,1 50,90" fill="none" stroke="white" stroke-width="2"/>
    </svg>
  </div>

  <!-- Arabic Calligraphy Watermark (added via CSS) -->

  <!-- Dark Mode Toggle -->
  <button id="dark-mode-toggle">
    <i class="fas fa-moon"></i>
  </button>

  <!-- Language Toggle -->
  <button id="language-toggle">SOOMALI</button>

  <!-- Main App Container -->
  <div class="app-container">
    <header>
      <h1><i class="fas fa-tasks"></i> To-Do List Premium</h1>
      <p>Organisez votre journée avec style 🇸🇴</p>
    </header>

    <!-- Control Panel -->
    <div class="control-panel">
      <!-- Task Form -->
      <form id="task-form">
        <input type="text" id="task-input" placeholder="Nouvelle tâche..." required>
        <select id="priority-select">
          <option value="low">Basse</option>
          <option value="medium" selected>Moyenne</option>
          <option value="high">Haute</option>
        </select>
        <select id="category-select">
          <option value="">Catégorie</option>
          <option value="work">Travail</option>
          <option value="personal">Personnel</option>
          <option value="shopping">Courses</option>
          <option value="prayer">🕌 Prière</option>
          <option value="quran">📖 Coran</option>
        </select>
        <input type="date" id="due-date">
        <button type="submit"><i class="fas fa-plus"></i> Ajouter</button>
      </form>

      <!-- Search Bar -->
      <input type="text" id="search-bar" placeholder="Rechercher une tâche...">
    </div>

    <!-- Filter Buttons -->
    <div class="filter-buttons">
      <button class="filter-btn active" data-filter="all">Toutes</button>
      <button class="filter-btn" data-filter="active">Actives</button>
      <button class="filter-btn" data-filter="completed">Terminées</button>
      <button class="filter-btn" data-filter="high">Urgentes</button>
      <button class="filter-btn" data-filter="today">Aujourd'hui</button>
    </div>

    <!-- Task List -->
    <ul id="task-list">
      <!-- Filled dynamically -->
    </ul>

    <!-- Statistics -->
    <div class="stats">
      <div class="stat-item">
        <i class="fas fa-tasks"></i>
        <span>Total: <span class="stat-value" id="total-count">0</span></span>
      </div>
      <div class="stat-item">
        <i class="fas fa-check"></i>
        <span>Terminées: <span class="stat-value" id="completed-count">0</span></span>
      </div>
      <div class="stat-item">
        <i class="fas fa-exclamation-triangle"></i>
        <span>En retard: <span class="stat-value" id="overdue-count">0</span></span>
      </div>
    </div>
  </div>

  <script>
    document.addEventListener('DOMContentLoaded', function() {
      // DOM Elements
      const taskForm = document.getElementById('task-form');
      const taskInput = document.getElementById('task-input');
      const prioritySelect = document.getElementById('priority-select');
      const categorySelect = document.getElementById('category-select');
      const dueDateInput = document.getElementById('due-date');
      const searchBar = document.getElementById('search-bar');
      const taskList = document.getElementById('task-list');
      const filterButtons = document.querySelectorAll('.filter-btn');
      const darkModeToggle = document.getElementById('dark-mode-toggle');
      const languageToggle = document.getElementById('language-toggle');

      // State Variables
      let currentFilter = 'all';
      let tasks = JSON.parse(localStorage.getItem('tasks')) || [];

      // Translations
      const translations = {
        "Nouvelle tâche...": "Shaqo cusub...",
        "Ajouter": "Ku dar",
        "Toutes": "Dhammaan",
        "Actives": "Firfircoon",
        "Terminées": "Dhameystiran",
        "Urgentes": "Degdeg ah",
        "Aujourd'hui": "Maanta",
        "Organisez votre journée avec style": "Maalintaada u qaabilsii qaab qurux badan",
        "Total": "Wadarta",
        "En retard": "Daahid",
        "Rechercher une tâche...": "Raadi shaqo...",
        "Basse": "Hoos",
        "Moyenne": "Dhexdhexaad",
        "Haute": "Sare",
        "Catégorie": "Qayb",
        "Travail": "Shaqo",
        "Personnel": "Shakhsi",
        "Courses": "Alaab",
        "Prière": "Salaad",
        "Coran": "Qur'aan"
      };

      // Initialize
      renderTasks();
      updateStats();
      updateBackgroundForTime();

      // Event Listeners
      taskForm.addEventListener('submit', addTask);
      searchBar.addEventListener('input', searchTasks);
      filterButtons.forEach(btn => btn.addEventListener('click', () => applyFilter(btn.dataset.filter)));
      darkModeToggle.addEventListener('click', toggleDarkMode);
      languageToggle.addEventListener('click', toggleLanguage);

      // Functions
      function addTask(e) {
        e.preventDefault();
        const text = taskInput.value.trim();
        const priority = prioritySelect.value;
        const category = categorySelect.value;
        const dueDate = dueDateInput.value;

        if (text) {
          const newTask = {
            id: Date.now(),
            text,
            priority,
            category,
            dueDate,
            completed: false,
            createdAt: new Date().toISOString()
          };

          tasks.push(newTask);
          saveTasks();
          renderTasks();
          taskInput.value = '';
          updateStats();
        }
      }

      function renderTasks(filteredTasks = tasks) {
        taskList.innerHTML = '';

        if (filteredTasks.length === 0) {
          taskList.innerHTML = '<p style="text-align: center; padding: 20px; color: #777;">Aucune tâche trouvée.</p>';
          return;
        }

        filteredTasks.forEach(task => {
          const li = document.createElement('li');
          li.className = `task-item priority-${task.priority}`;
          li.dataset.id = task.id;

          if (task.completed) li.classList.add('completed');

          const isOverdue = task.dueDate && new Date(task.dueDate) < new Date() && !task.completed;

          li.innerHTML = `
            <input type="checkbox" class="task-checkbox" ${task.completed ? 'checked' : ''}>
            <div class="task-content">
              <div class="task-text">${task.text}</div>
              <div class="task-meta">
                ${task.priority ? `<span class="task-priority priority-${task.priority}">${getPriorityText(task.priority)}</span>` : ''}
                ${task.category ? `<span class="task-category">${getCategoryIcon(task.category)} ${task.category}</span>` : ''}
                ${task.dueDate ? `<span class="task-due ${isOverdue ? 'overdue' : ''}">📅 ${formatDate(task.dueDate)}</span>` : ''}
              </div>
            </div>
            <div class="task-actions">
              <button class="task-btn edit-btn"><i class="fas fa-edit"></i></button>
              <button class="task-btn delete-btn"><i class="fas fa-trash"></i></button>
            </div>
          `;

          const checkbox = li.querySelector('.task-checkbox');
          checkbox.addEventListener('change', () => toggleTaskCompletion(task.id, checkbox.checked));

          const editBtn = li.querySelector('.edit-btn');
          editBtn.addEventListener('click', () => editTask(task.id));

          const deleteBtn = li.querySelector('.delete-btn');
          deleteBtn.addEventListener('click', () => deleteTask(task.id));

          taskList.appendChild(li);
        });
      }

      function toggleTaskCompletion(taskId, isCompleted) {
        const task = tasks.find(t => t.id === taskId);
        if (task) {
          task.completed = isCompleted;
          saveTasks();
          updateStats();
        }
      }

      function editTask(taskId) {
        const task = tasks.find(t => t.id === taskId);
        if (!task) return;

        const taskElement = document.querySelector(`.task-item[data-id="${taskId}"]`);
        taskElement.innerHTML = `
          <form class="edit-form" style="display: flex; gap: 10px; width: 100%;">
            <input type="text" value="${task.text}" class="edit-input" style="flex-grow: 1;" required>
            <select class="edit-priority" value="${task.priority}">
              <option value="low">${translations["Basse"] || "Basse"}</option>
              <option value="medium">${translations["Moyenne"] || "Moyenne"}</option>
              <option value="high">${translations["Haute"] || "Haute"}</option>
            </select>
            <select class="edit-category">
              <option value="">${translations["Catégorie"] || "Catégorie"}</option>
              <option value="work">${translations["Travail"] || "Travail"}</option>
              <option value="personal">${translations["Personnel"] || "Personnel"}</option>
              <option value="shopping">${translations["Courses"] || "Courses"}</option>
              <option value="prayer">🕌 ${translations["Prière"] || "Prière"}</option>
              <option value="quran">📖 ${translations["Coran"] || "Coran"}</option>
            </select>
            <input type="date" class="edit-due-date" value="${task.dueDate || ''}">
            <button type="submit" class="save-btn"><i class="fas fa-save"></i></button>
            <button type="button" class="cancel-btn"><i class="fas fa-times"></i></button>
          </form>
        `;

        const form = taskElement.querySelector('.edit-form');
        const input = taskElement.querySelector('.edit-input');
        const prioritySelect = taskElement.querySelector('.edit-priority');
        const categorySelect = taskElement.querySelector('.edit-category');
        const dueDateInput = taskElement.querySelector('.edit-due-date');

        prioritySelect.value = task.priority;
        categorySelect.value = task.category || '';
        input.focus();

        form.addEventListener('submit', (e) => {
          e.preventDefault();
          task.text = input.value.trim();
          task.priority = prioritySelect.value;
          task.category = categorySelect.value || null;
          task.dueDate = dueDateInput.value || null;
          saveTasks();
          renderTasks();
        });

        const cancelBtn = taskElement.querySelector('.cancel-btn');
        cancelBtn.addEventListener('click', () => renderTasks());
      }

      function deleteTask(taskId) {
        tasks = tasks.filter(t => t.id !== taskId);
        saveTasks();
        renderTasks();
        updateStats();
      }

      function searchTasks() {
        const searchTerm = searchBar.value.toLowerCase();
        const filteredTasks = tasks.filter(task =>
          task.text.toLowerCase().includes(searchTerm)
        );
        renderTasks(filteredTasks);
      }

      function applyFilter(filter) {
        currentFilter = filter;
        filterButtons.forEach(btn => btn.classList.toggle('active', btn.dataset.filter === filter));

        let filteredTasks = tasks;
        const today = new Date().toISOString().split('T')[0];

        switch(filter) {
          case 'active': filteredTasks = tasks.filter(t => !t.completed); break;
          case 'completed': filteredTasks = tasks.filter(t => t.completed); break;
          case 'high': filteredTasks = tasks.filter(t => t.priority === 'high'); break;
          case 'today': filteredTasks = tasks.filter(t => t.dueDate === today); break;
        }

        renderTasks(filteredTasks);
      }

      function updateStats() {
        document.getElementById('total-count').textContent = tasks.length;
        document.getElementById('completed-count').textContent = tasks.filter(t => t.completed).length;

        const overdueCount = tasks.filter(t =>
          t.dueDate && new Date(t.dueDate) < new Date() && !t.completed
        ).length;

        document.getElementById('overdue-count').textContent = overdueCount;
      }

      function saveTasks() {
        localStorage.setItem('tasks', JSON.stringify(tasks));
      }

      function toggleDarkMode() {
        document.body.classList.toggle('dark-mode');
        const icon = darkModeToggle.querySelector('i');
        icon.classList.toggle('fa-moon');
        icon.classList.toggle('fa-sun');
      }

      function toggleLanguage() {
        const currentLang = languageToggle.textContent;
        const isSomali = currentLang === 'SOOMALI';
        languageToggle.textContent = isSomali ? 'FRANÇAIS' : 'SOOMALI';

        // Update UI text
        Object.entries(translations).forEach(([french, somali]) => {
          const elements = document.querySelectorAll(`input[placeholder="${french}"], option, button:not(#language-toggle):not(#dark-mode-toggle), span, p`);
          elements.forEach(el => {
            if (el.textContent.trim() === french || el.placeholder === french) {
              if (el.tagName === 'INPUT') {
                el.placeholder = isSomali ? french : somali;
              } else {
                el.textContent = isSomali ? french : somali;
              }
            }
          });
        });

        // Update select options
        if (!isSomali) {
          prioritySelect.querySelector('option[value="low"]').textContent = translations["Basse"];
          prioritySelect.querySelector('option[value="medium"]').textContent = translations["Moyenne"];
          prioritySelect.querySelector('option[value="high"]').textContent = translations["Haute"];
          
          const categoryOptions = categorySelect.querySelectorAll('option');
          categoryOptions[0].textContent = translations["Catégorie"];
          categoryOptions[1].textContent = translations["Travail"];
          categoryOptions[2].textContent = translations["Personnel"];
          categoryOptions[3].textContent = translations["Courses"];
          categoryOptions[4].textContent = `🕌 ${translations["Prière"]}`;
          categoryOptions[5].textContent = `📖 ${translations["Coran"]}`;
        } else {
          prioritySelect.querySelector('option[value="low"]').textContent = "Basse";
          prioritySelect.querySelector('option[value="medium"]').textContent = "Moyenne";
          prioritySelect.querySelector('option[value="high"]').textContent = "Haute";
          
          const categoryOptions = categorySelect.querySelectorAll('option');
          categoryOptions[0].textContent = "Catégorie";
          categoryOptions[1].textContent = "Travail";
          categoryOptions[2].textContent = "Personnel";
          categoryOptions[3].textContent = "Courses";
          categoryOptions[4].textContent = "🕌 Prière";
          categoryOptions[5].textContent = "📖 Coran";
        }
      }

      function updateBackgroundForTime() {
        const hours = new Date().getHours();
        const bg = document.querySelector('.somali-flag-bg');
        if (hours >= 18 || hours <= 5) {
          bg.style.backgroundColor = 'var(--night-blue)';
          bg.style.backgroundImage = 'none';
        } else {
          bg.style.backgroundColor = 'var(--somali-blue)';
          bg.style.backgroundImage = 'radial-gradient(circle at 10% 20%, rgba(255,255,255,0.1) 1px, transparent 1px), radial-gradient(circle at 50% 80%, rgba(255,255,255,0.1) 1px, transparent 1px)';
        }
      }

      // Utility Functions
      function getPriorityText(priority) {
        const texts = { 
          'low': translations["Basse"] || "Basse", 
          'medium': translations["Moyenne"] || "Moyenne", 
          'high': translations["Haute"] || "Haute" 
        };
        return texts[priority];
      }

      function getCategoryIcon(category) {
        const icons = { 
          'work': '💼', 
          'personal': '👤', 
          'shopping': '🛒',
          'prayer': '🕌',
          'quran': '📖'
        };
        return icons[category] || '';
      }

      function formatDate(dateString) {
        if (!dateString) return '';
        const date = new Date(dateString);
        const gregorian = date.toLocaleDateString('fr-FR', { 
          weekday: 'short', 
          day: 'numeric', 
          month: 'short' 
        });
        
        // Simple Hijri conversion (for demo)
        const hijriDay = (date.getDate() + 10) % 30 || 1;
        const hijriMonths = ['Muh.', 'Saf.', 'Rab. I', 'Rab. II', 'Jum. I', 'Jum. II', 'Raj.', 'Sha.', 'Ram.', 'Shaw.', 'Dhuʻl-Q.', 'Dhuʻl-H.'];
        const hijriMonth = hijriMonths[date.getMonth()];
        const hijriYear = 1445 + Math.floor(date.getFullYear() - 2023);
        
        return `${gregorian} • ${hijriDay} ${hijriMonth} ${hijriYear}H`;
      }

      // Check time every hour
      setInterval(updateBackgroundForTime, 3600000);
    });
  </script>
</body>
</html>
