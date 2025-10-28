# Scripty-
A beginners tool designed to help young minds curate their own screenplays.
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Little scribblers🖍️ - Fun Screenwriting for Beginners!</title>
    <style>
        /* 🌈 Fun, Childish, Colorful Theme */
        @import url('https://fonts.googleapis.com/css2?family=Comic+Neue:wght@400;700&family=Patrick+Hand&display=swap');

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Comic Neue', cursive;
            background: linear-gradient(135deg, #a8e6cf, #dcedc1, #ffd3b6, #ffaaa5);
            background-size: 400% 400%;
            animation: gradientBG 15s ease infinite;
            color: #333;
            line-height: 1.6;
            min-height: 100vh;
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        header {
            text-align: center;
            padding: 2rem 1rem;
            background: rgba(255, 255, 255, 0.8);
            border-bottom: 5px dashed #ff6b6b;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
        }

        h1 {
            font-family: 'Patrick Hand', cursive;
            font-size: 3rem;
            color: #ff6b6b;
            text-shadow: 2px 2px 0px #ffb6b6;
            margin-bottom: 0.5rem;
        }

        .subtitle {
            font-size: 1.3rem;
            color: #4ecdc4;
            font-weight: bold;
        }

        .container {
            max-width: 1100px;
            margin: 2rem auto;
            padding: 0 1rem;
        }

        /* 🎨 Character Creator */
        .character-creator {
            background: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            padding: 1.5rem;
            margin-bottom: 2rem;
            box-shadow: 0 8px 20px rgba(0,0,0,0.1);
            border: 4px solid #ffe66d;
        }

        .character-creator h2 {
            font-size: 2rem;
            color: #4ecdc4;
            text-align: center;
            margin-bottom: 1rem;
            text-shadow: 1px 1px 0px #a0e9e2;
        }

        .char-form {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1rem;
            margin-bottom: 1rem;
        }

        .char-form input, .char-form select, .char-form textarea {
            padding: 0.8rem;
            border: 3px solid #ff9ff3;
            border-radius: 12px;
            font-family: 'Comic Neue', cursive;
            font-size: 1rem;
            background: #fffdf9;
        }

        .char-form textarea {
            resize: vertical;
            min-height: 80px;
        }

        .add-char-btn {
            background: #ffe66d;
            color: #333;
            border: none;
            padding: 0.8rem 1.5rem;
            font-size: 1.1rem;
            font-weight: bold;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
            transition: all 0.3s;
        }

        .add-char-btn:hover {
            transform: translateY(-3px);
            background: #ffd93d;
        }

        .characters-list {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            margin-top: 1rem;
        }

        .character-card {
            background: #a0e7ff;
            border: 3px solid #6bc5e8;
            border-radius: 16px;
            padding: 1rem;
            width: 220px;
            position: relative;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
            transition: transform 0.3s;
        }

        .character-card:hover {
            transform: scale(1.05);
        }

        .char-avatar {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: #fff;
            margin: 0 auto 0.5rem;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            border: 3px solid #ff6b6b;
        }

        .char-name {
            font-weight: bold;
            font-size: 1.2rem;
            text-align: center;
            color: #2d3436;
            margin-bottom: 0.5rem;
        }

        .char-details {
            font-size: 0.9rem;
            color: #2d3436;
        }

        .delete-char {
            position: absolute;
            top: 5px;
            right: 5px;
            background: #ff6b6b;
            color: white;
            border: none;
            width: 24px;
            height: 24px;
            border-radius: 50%;
            font-size: 0.8rem;
            cursor: pointer;
        }

        /* 🎬 Scene Board - Like a Storyboard with Fun Dividers */
        .scene-board {
            background: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            padding: 1.5rem;
            box-shadow: 0 8px 20px rgba(0,0,0,0.1);
            border: 4px solid #95e1d3;
        }

        .scene-board h2 {
            font-size: 2rem;
            color: #95e1d3;
            text-align: center;
            margin-bottom: 1rem;
            text-shadow: 1px 1px 0px #c1f0e7;
        }

        .add-scene-btn {
            display: block;
            margin: 0 auto 1.5rem;
            background: #95e1d3;
            color: white;
            border: none;
            padding: 0.8rem 2rem;
            font-size: 1.1rem;
            font-weight: bold;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
        }

        .add-scene-btn:hover {
            background: #70d9c8;
        }

        .scenes-container {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
        }

        .scene {
            background: #f8f9fa;
            border-radius: 16px;
            padding: 1.5rem;
            border: 4px solid #ffe66d;
            position: relative;
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
        }

        .scene-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1rem;
            padding-bottom: 0.5rem;
            border-bottom: 3px dashed #ff9ff3;
        }

        .scene-title {
            font-size: 1.5rem;
            font-weight: bold;
            color: #6c5ce7;
        }

        .scene-location {
            font-style: italic;
            color: #a29bfe;
        }

        .scene-actions {
            display: flex;
            gap: 0.5rem;
        }

        .btn-small {
            background: #fd79a8;
            color: white;
            border: none;
            padding: 0.4rem 0.8rem;
            border-radius: 20px;
            font-size: 0.9rem;
            cursor: pointer;
        }

        .btn-small:hover {
            background: #fd5c94;
        }

        .scene-content {
            margin-top: 1rem;
        }

        .action-line, .dialogue-line {
            margin-bottom: 1rem;
            padding: 0.8rem;
            border-radius: 12px;
            background: #fff;
            border: 2px dashed #ddd;
            min-height: 60px;
            font-family: 'Patrick Hand', cursive;
            font-size: 1.1rem;
        }

        .dialogue-line {
            background: #fffacd;
            border-style: dotted;
            border-color: #ffe66d;
        }

        .dialogue-line::before {
            content: "💬 ";
            font-size: 1.3rem;
        }

        .add-line {
            display: flex;
            gap: 0.5rem;
            margin-top: 1rem;
        }

        .add-line select {
            padding: 0.6rem;
            border: 2px solid #ff9ff3;
            border-radius: 10px;
            background: white;
        }

        .add-line-btn {
            background: #6c5ce7;
            color: white;
            border: none;
            padding: 0.6rem 1rem;
            border-radius: 50px;
            cursor: pointer;
        }

        .fun-divider {
            height: 30px;
            background: repeating-linear-gradient(
                45deg,
                #ff9ff3,
                #ff9ff3 10px,
                #ffe66d 10px,
                #ffe66d 20px
            );
            border-radius: 15px;
            margin: 1.5rem 0;
            animation: slide 10s linear infinite;
        }

        @keyframes slide {
            0% { background-position: 0 0; }
            100% { background-position: 100px 0; }
        }

        /* 🎉 Footer */
        footer {
            text-align: center;
            padding: 2rem;
            color: #666;
            font-size: 0.9rem;
            margin-top: 3rem;
        }

        /* Responsive */
        @media (max-width: 768px) {
            h1 { font-size: 2.2rem; }
            .char-form { grid-template-columns: 1fr; }
            .character-card { width: 100%; }
        }
    </style>
</head>
<body>
    <header>
        <h1>🖍️ Little Scribblers</h1>
        <p class="subtitle">Where Beginner Screenwriters Draw Their Dreams! ✨</p>
    </header>

    <div class="container">

        <!-- Character Creator -->
        <section class="character-creator">
            <h2>🎭 Create Your Cast!</h2>
            <div class="char-form">
                <input type="text" id="charName" placeholder="Character Name (e.g., Luna the Brave)">
                <input type="number" id="charAge" placeholder="Age" min="1" max="120">
                <select id="charGender">
                    <option value="">Gender</option>
                    <option value="Girl">👧 Girl</option>
                    <option value="Boy">👦 Boy</option>
                    <option value="Non-binary">🦄 Non-binary</option>
                    <option value="Other">🌟 Other</option>
                </select>
                <input type="text" id="charLook" placeholder="Looks like... (e.g., pink hair, robot arm)">
                <textarea id="charPersonality" placeholder="Personality & Backstory... (fun facts!)"></textarea>
                <button class="add-char-btn" onclick="addCharacter()">➕ Add Hero!</button>
            </div>
            <div class="characters-list" id="charactersList"></div>
        </section>

        <div class="fun-divider"></div>

        <!-- Scene Board -->
        <section class="scene-board">
            <h2>🎬 Your Storyboard Adventure!</h2>
            <button class="add-scene-btn" onclick="addScene()">🆕 Start a New Scene!</button>
            <div class="scenes-container" id="scenesContainer"></div>
        </section>
    </div>

    <footer>
        <p>Made with ❤️ and crayons for beginner screenwriters everywhere!</p>
    </footer>

    <script>
        // Character Management
        let characters = [];
        let characterIdCounter = 0;

        const emojiMap = {
            'Girl': '👧', 'Boy': '👦', ‘Animal’: '🦄', 'Other': '🌟'
        };

        function addCharacter() {
            const name = document.getElementById('charName').value.trim();
            const age = document.getElementById('charAge').value;
            const gender = document.getElementById('charGender').value;
            const look = document.getElementById('charLook').value.trim();
            const personality = document.getElementById('charPersonality').value.trim();

            if (!name) {
                alert("🚨 Every hero needs a name!");
                return;
            }

            const char = {
                id: characterIdCounter++,
                name,
                age: age || '?',
                gender,
                look: look || 'mysterious',
                personality: personality || 'full of surprises!',
                emoji: emojiMap[gender] || '🎭'
            };

            characters.push(char);
            renderCharacters();
            clearCharForm();
        }

        function clearCharForm() {
            document.getElementById('charName').value = '';
            document.getElementById('charAge').value = '';
            document.getElementById('charGender').value = '';
            document.getElementById('charLook').value = '';
            document.getElementById('charPersonality').value = '';
        }

        function renderCharacters() {
            const list = document.getElementById('charactersList');
            list.innerHTML = '';

            characters.forEach(char => {
                const card = document.createElement('div');
                card.className = 'character-card';
                card.innerHTML = `
                    <button class="delete-char" onclick="deleteCharacter(${char.id})">✕</button>
                    <div class="char-avatar">${char.emoji}</div>
                    <div class="char-name">${char.name}</div>
                    <div class="char-details">
                        <strong>Age:</strong> ${char.age}<br>
                        <strong>Looks:</strong> ${char.look}<br>
                        <strong>Personality:</strong> ${char.personality}
                    </div>
                `;
                list.appendChild(card);
            });
        }

        function deleteCharacter(id) {
            characters = characters.filter(c => c.id !== id);
            renderCharacters();
        }

        // Scene Management
        let scenes = [];
        let sceneIdCounter = 0;
        let lineIdCounter = 0;

        function addScene() {
            const scene = {
                id: sceneIdCounter++,
                title: `Scene ${scenes.length + 1}: The Adventure Begins!`,
                location: 'A magical forest 🌳',
                lines: []
            };
            scenes.push(scene);
            renderScenes();
        }

        function renderScenes() {
            const container = document.getElementById('scenesContainer');
            container.innerHTML = '';

            scenes.forEach((scene, sceneIndex) => {
                const sceneEl = document.createElement('div');
                sceneEl.className = 'scene';
                sceneEl.innerHTML = `
                    <div class="scene-header">
                        <div>
                            <input type="text" class="scene-title" value="${scene.title}" onchange="updateSceneTitle(${scene.id}, this.value)">
                            <div class="scene-location">
                                📍 <input type="text" value="${scene.location}" onchange="updateSceneLocation(${scene.id}, this.value)" style="border:none; background:transparent; font-style:italic; color:#a29bfe; width:200px;">
                            </div>
                        </div>
                        <div class="scene-actions">
                            <button class="btn-small" onclick="duplicateScene(${scene.id})">📋 Copy</button>
                            <button class="btn-small" style="background:#ff6b6b;" onclick="deleteScene(${scene.id})">🗑️ Delete</button>
                        </div>
                    </div>
                    <div class="scene-content" id="lines-${scene.id}"></div>
                    <div class="add-line">
                        <select id="lineType-${scene.id}">
                            <option value="action">🎬 Action</option>
                            <option value="dialogue">💬 Dialogue</option>
                        </select>
                        ${characters.length > 0 ? `
                        <select id="speaker-${scene.id}" style="display:none;">
                            <option value="">-- Choose Speaker --</option>
                            ${characters.map(c => `<option value="${c.name}">${c.emoji} ${c.name}</option>`).join('')}
                        </select>` : ''}
                        <button class="add-line-btn" onclick="addLine(${scene.id})">➕ Add Line</button>
                    </div>
                `;

                // Show speaker select only for dialogue
                const lineTypeSelect = sceneEl.querySelector(`#lineType-${scene.id}`);
                const speakerSelect = sceneEl.querySelector(`#speaker-${scene.id}`);
                if (speakerSelect) {
                    lineTypeSelect.addEventListener('change', () => {
                        speakerSelect.style.display = lineTypeSelect.value === 'dialogue' ? 'block' : 'none';
                    });
                }

                container.appendChild(sceneEl);
                renderLines(scene.id);
            });
        }

        function updateSceneTitle(id, newTitle) {
            const scene = scenes.find(s => s.id === id);
            if (scene) scene.title = newTitle;
        }

        function updateSceneLocation(id, newLocation) {
            const scene = scenes.find(s => s.id === id);
            if (scene) scene.location = newLocation;
        }

        function addLine(sceneId) {
            const scene = scenes.find(s => s.id === sceneId);
            const type = document.getElementById(`lineType-${sceneId}`).value;
            const speaker = type === 'dialogue' ? document.getElementById(`speaker-${sceneId}`).value : '';

            if (type === 'dialogue' && !speaker) {
                alert("💬 Pick a character to speak!");
                return;
            }

            const line = {
                id: lineIdCounter++,
                type,
                content: type === 'action' ? 'Something exciting happens...' : 'Hello! I have something to say!',
                speaker: speaker || null
            };

            scene.lines.push(line);
            renderLines(sceneId);
        }

        function renderLines(sceneId) {
            const linesContainer = document.getElementById(`lines-${sceneId}`);
            const scene = scenes.find(s => s.id === sceneId);
            linesContainer.innerHTML = '';

            scene.lines.forEach((line, index) => {
                const lineEl = document.createElement('div');
                lineEl.className = line.type === 'dialogue' ? 'dialogue-line' : 'action-line';
                lineEl.contentEditable = true;
                lineEl.textContent = line.type === 'dialogue' ? `${line.speaker}: ${line.content}` : line.content;
                lineEl.addEventListener('blur', () => {
                    const newText = lineEl.textContent;
                    if (line.type === 'dialogue') {
                        const parts = newText.split(': ');
                        line.speaker = parts[0];
                        line.content = parts.slice(1).join(': ');
                    } else {
                        line.content = newText;
                    }
                });

                const deleteBtn = document.createElement('button');
                deleteBtn.textContent = '✕';
                deleteBtn.style.cssText = 'float:right; background:#ff6b6b; color:white; border:none; border-radius:50%; width:24px; height:24px; cursor:pointer; margin:5px;';
                deleteBtn.onclick = () => {
                    scene.lines = scene.lines.filter(l => l.id !== line.id);
                    renderLines(sceneId);
                };

                lineEl.appendChild(deleteBtn);
                linesContainer.appendChild(lineEl);
            });
        }

        function deleteScene(id) {
            scenes = scenes.filter(s => s.id !== id);
            renderScenes();
        }

        function duplicateScene(id) {
            const original = scenes.find(s => s.id === id);
            const copy = {
                id: sceneIdCounter++,
                title: original.title + " (Copy)",
                location: original.location,
                lines: original.lines.map(l => ({ ...l, id: lineIdCounter++ }))
            };
            scenes.push(copy);
            renderScenes();
        }

        // Auto-save to localStorage
        function saveToLocalStorage() {
            const data = { characters, scenes };
            localStorage.setItem('scriptyScribblesData', JSON.stringify(data));
        }

        function loadFromLocalStorage() {
            const data = localStorage.getItem('scriptyScribblesData');
            if (data) {
                const parsed = JSON.parse(data);
                characters = parsed.characters || [];
                scenes = parsed.scenes || [];
                characterIdCounter = characters.length ? Math.max(...characters.map(c => c.id)) + 1 : 0;
                sceneIdCounter = scenes.length ? Math.max(...scenes.map(s => s.id)) + 1 : 0;
                lineIdCounter = scenes.reduce((max, s) => Math.max(max, ...s.lines.map(l => l.id)), 0) + 1;
                renderCharacters();
                renderScenes();
            }
        }

        // Save on change
        setInterval(saveToLocalStorage, 5000);
        window.addEventListener('beforeunload', saveToLocalStorage);

        // Load on start
        window.onload = loadFromLocalStorage;

        // Welcome message
        if (!localStorage.getItem('Little ScribblersData')) {
            setTimeout(() => {
                alert("🎉 Welcome to Little Scribblers!\n\nCreate characters, then add scenes and write your story! Everything auto-saves! 🪄");
            }, 1000);
        }
    </script>
</body>
</html>
