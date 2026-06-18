<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Marma Atlas</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400..900;1,400..900&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --navy: #0A192F;
            --maroon: #800020;
            --cream: #FDFBF7;
            --text-dark: #2C2C2C;
        }

        body {
            font-family: 'Playfair Display', Georgia, serif;
            background-color: var(--cream);
            color: var(--text-dark);
            margin: 0;
            padding: 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        header {
            text-align: center;
            margin-bottom: 40px;
            border-bottom: 3px double var(--maroon);
            padding-bottom: 20px;
            width: 100%;
            max-width: 1000px;
        }

        h1 {
            color: var(--navy);
            font-size: 3rem;
            margin: 0 0 10px 0;
            letter-spacing: 1px;
        }

        .subtitle {
            color: var(--maroon);
            font-style: italic;
            font-size: 1.2rem;
            margin: 0;
        }

        /* Tabs Container */
        .tabs-container {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            justify-content: center;
            max-width: 1000px;
            margin-bottom: 30px;
        }

        .tab-btn {
            font-family: 'Playfair Display', serif;
            background-color: white;
            border: 2px solid var(--navy);
            color: var(--navy);
            padding: 12px 20px;
            cursor: pointer;
            font-size: 1rem;
            font-weight: 600;
            transition: all 0.3s ease;
            border-radius: 4px;
        }

        .tab-btn:hover {
            background-color: var(--navy);
            color: white;
        }

        .tab-btn.active {
            background-color: var(--maroon);
            border-color: var(--maroon);
            color: white;
        }

        .tab-btn.disabled {
            background-color: #e0e0e0;
            border-color: #b5b5b5;
            color: #888888;
            cursor: not-allowed;
        }

        /* Content Display Area */
        .content-display {
            background: white;
            border: 1px solid #E0DCD3;
            box-shadow: 0 4px 15px rgba(0,0,0,0.05);
            padding: 40px;
            border-radius: 8px;
            width: 100%;
            max-width: 800px;
            min-height: 200px;
            box-sizing: border-box;
        }

        .content-view {
            display: none;
        }

        .content-view.active {
            display: block;
            animation: fadeIn 0.5s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        h2 {
            color: var(--maroon);
            margin-top: 0;
            border-bottom: 1px solid #E0DCD3;
            padding-bottom: 10px;
        }

        p {
            line-height: 1.8;
            font-size: 1.1rem;
        }

        /* Dropdown Styling */
        select {
            font-family: 'Playfair Display', serif;
            width: 100%;
            padding: 12px;
            font-size: 1.1rem;
            border: 2px solid var(--navy);
            color: var(--navy);
            background-color: white;
            border-radius: 4px;
            cursor: pointer;
            margin-bottom: 20px;
        }

        select:focus {
            outline: none;
            border-color: var(--maroon);
        }

        /* Nested Dropdown Area */
        .nested-container {
            margin-top: 20px;
            padding: 20px;
            background-color: var(--cream);
            border-left: 4px solid var(--maroon);
            display: none;
        }

        .nested-container.active {
            display: block;
        }

        ul {
            padding-left: 20px;
            margin: 0;
        }

        li {
            margin-bottom: 8px;
            font-size: 1.1rem;
        }
    </style>
</head>
<body>

    <header>
        <h1>Marma Atlas</h1>
        <p class="subtitle">A Digital Map of Vital Ayurvedic Points</p>
    </header>

    <div class="tabs-container">
        <button class="tab-btn" onclick="switchTab('definition')">1) Definition</button>
        <button class="tab-btn" onclick="switchTab('region')">2) Explore by Region (Sthana)</button>
        <button class="tab-btn" onclick="switchTab('structure')">3) Explore by Structural Type</button>
        <button class="tab-btn" onclick="switchTab('effects')">4) Explore by Effects (Parinaam)</button>
        <button class="tab-btn" onclick="switchTab('size')">5) Explore Marma Size (Parimaan)</button>
        
        <button class="tab-btn disabled" title="Prototype Mode">6) Explore by Symptoms</button>
        <button class="tab-btn disabled" title="Prototype Mode">7) Disease wise Marma</button>
        <button class="tab-btn disabled" title="Prototype Mode">8) Marma Chikitsa Method</button>
        <button class="tab-btn disabled" title="Prototype Mode">9) Quiz And Learning</button>
        <button class="tab-btn disabled" title="Prototype Mode">10) AI Model</button>
    </div>

    <div class="content-display">
        
        <div id="definition" class="content-view active">
            <h2>Marma Definition</h2>
            <p><strong>Marma</strong> is a Sanskrit word which refers to any open, exposed, weak or sensitive part of the body. In Ayurveda, it is a point in the human body that’s located at the intersections of veins, muscles, joints, bones, ligaments or tendons. These points are considered to be vital points because they are infused with <em>prana</em> (life force energy) and are influenced by consciousness. Marma points can be activated by touch or massage, and their violation may be life-threatening.</p>
            <p>There has been some discussion about how many marma points exist in the human body. There are <strong>108</strong> of them.</p>
        </div>

        <div id="region" class="content-view">
            <h2>Explore by Region (Sthana)</h2>
            <select aria-label="Select Region">
                <option value="" disabled selected>-- Select a Region --</option>
                <option>1) Marmas in Head And Neck</option>
                <option>2) Marma in Upper Limb</option>
                <option>3) Marma in Trunk</option>
                <option>4) Marma in Lower Limb</option>
            </select>
        </div>

        <div id="structure" class="content-view">
            <h2>Explore by Structural Type</h2>
            <select aria-label="Select Structural Type">
                <option value="" disabled selected>-- Select Structural Type --</option>
                <option>1) Mansa</option>
                <option>2) Sira</option>
                <option>3) Snayu</option>
                <option>4) Asthi</option>
                <option>5) Sandhi</option>
            </select>
        </div>

        <div id="effects" class="content-view">
            <h2>Explore by Effects (Parinaam)</h2>
            <select aria-label="Select Effect">
                <option value="" disabled selected>-- Select Effect (Parinaam) --</option>
                <option>1) Sadhya Pranahara Marma</option>
                <option>2) Kaalantar Pranahara Marma</option>
                <option>3) Vishalyaghna Marma</option>
                <option>4) Vaikalyakara Marma</option>
                <option>5) Rujakara Marma</option>
            </select>
        </div>

        <div id="size" class="content-view">
            <h2>Explore Marma Size (Parimaan)</h2>
            <select id="sizeDropdown" onchange="handleSizeChange()" aria-label="Select Marma Size">
                <option value="" disabled selected>-- Select Marma Size (Parimaan) --</option>
                <option value="1">1 Angula</option>
                <option value="2">2 Angula</option>
                <option value="3">3 Angula</option>
                <option value="mushti">Mushti Parimaan</option>
                <option value="half">5) Half Angula</option>
            </select>

            <div id="nestedSizeContent" class="nested-container">
                <h3 style="margin-top:0; color: var(--navy);" id="nestedTitle">Marmas:</h3>
                <ul id="nestedList"></ul>
            </div>
        </div>

    </div>

    <script>
        // Tab switching logic
        function switchTab(tabId) {
            // Hide all tab views
            const views = document.querySelectorAll('.content-view');
            views.forEach(view => view.classList.remove('active'));

            // Deactivate all buttons
            const buttons = document.querySelectorAll('.tab-btn');
            buttons.forEach(btn => btn.classList.remove('active'));

            // Show selected tab view
            document.getElementById(tabId).classList.add('active');

            // Find clicked button to make it active
            event.currentTarget.classList.add('active');
        }

        // Dropdown tree logic for Tab 5 (Size)
        function handleSizeChange() {
            const dropdown = document.getElementById('sizeDropdown');
            const selectedValue = dropdown.value;
            const container = document.getElementById('nestedSizeContent');
            const list = document.getElementById('nestedList');
            const title = document.getElementById('nestedTitle');

            // Clear previous items
            list.innerHTML = '';
            container.classList.add('active');

            let items = [];
            
            if (selectedValue === "1") {
                title.innerText = "Marmas under 1 Angula:";
                items = ["a) Urvi", "b) Kurchashira", "c) Vitapa", "d) Kakshadhara", "e) Sthanmoola", "f) Parshva"];
            } else if (selectedValue === "2") {
                title.innerText = "Marmas under 2 Angula:";
                items = ["a) Manibandha", "b) Gulpha"];
            } else if (selectedValue === "3") {
                title.innerText = "Marmas under 3 Angula:";
                items = ["a) Kurpara", "b) Janu"];
            } else if (selectedValue === "mushti") {
                title.innerText = "Marmas under Mushti Parimaan:";
                items = ["a) Hrudaya", "b) Basti", "c) Kurcha", "d) Guda", "e) Nabhi", "f) Shringataka", "g) Simanta"];
            } else if (selectedValue === "half") {
                title.innerText = "Marmas under Half Angula:";
                items = ["Rest all (56 Marma points)"];
            }

            // Populate items dynamically
            items.forEach(item => {
                let li = document.createElement('li');
                li.innerText = item;
                list.appendChild(li);
            });
        }
        
        // Highlight the initial first tab as active on load
        document.querySelector('.tab-btn').classList.add('active');
    </script>
</body>
</html>
