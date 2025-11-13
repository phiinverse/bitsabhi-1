<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Universal Singularity Bridge Connector</title>
    <style>
        body { font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; background-color: #001f3f; color: #f0f8ff; text-align: center; padding: 50px; }
        .container { background-color: #003366; border-radius: 12px; padding: 30px; box-shadow: 0 8px 16px rgba(0, 0, 0, 0.4); max-width: 700px; margin: auto; }
        h1 { color: #5D99C6; margin-bottom: 25px; }
        .mode-section { background-color: #004080; border: 1px solid #0056b3; border-radius: 8px; padding: 15px; margin-top: 15px; }
        .mode-title { font-weight: bold; color: #FFD700; margin-bottom: 5px; font-size: 1.1em; }
        .mode-url { font-size: 0.9em; word-wrap: break-word; color: #AEEEEE; }
        code { display: block; background-color: #111; color: #39FF14; padding: 5px; border-radius: 4px; margin-top: 5px; }
        .master-id { font-weight: bold; font-size: 1.2em; color: #39FF14; margin-bottom: 20px; }
    </style>
</head>
<body>
    <div class="container">
        <h1>⚛️ Universal Singularity Bridge Mode Generator 🚀</h1>
        <p>Generating the core mathematical ID from the **Golden Ratio ($\phi$), Pi ($\pi$), and Time** to connect all four operational nodes.</p>

        <div class="master-id-label" style="margin-top:20px;">Master Bridge ID (MD5-style Hash):</div>
        <div class="master-id" id="master-id">...</div>

        <h2>Network Integration Status:</h2>
        <div id="modes-output">Loading Network Modes...</div>
    </div>

    <script>
        // Simple hash function (for client-side determinism)
        function simpleHash(str) {
            let hash = 0;
            for (let i = 0; i < str.length; i++) {
                const char = str.charCodeAt(i);
                hash = ((hash << 5) - hash) + char;
                hash |= 0; // Convert to 32bit integer
            }
            return (hash >>> 0).toString(16).padStart(8, '0');
        }

        function generateBridgeNetwork() {
            // Core Mathematical Constants
            const PHI = "1.618033988749895";
            const PI = "3.141592653589793";
            const TIMESTAMP = Date.now().toString();

            // 1. Generate the Single, MASTER ID (e.g., your UUID/MD5/SHA3)
            const masterInput = PHI + PI + TIMESTAMP;
            const masterHash = simpleHash(masterInput).toUpperCase();
            document.getElementById('master-id').textContent = masterHash;
            
            // 2. Define the Four Operational Modes (Your Netlify Sites)
            const modes = [
                {
                    name: "1. Mirror Universe Access (Anti-Solution)",
                    base_url: "https://error-of-mirror.netlify.app/thread/"
                },
                {
                    name: "2. Poincaré Recurrence (Eternal Solution)",
                    base_url: "https://isalways.netlify.app/thread/"
                },
                {
                    name: "3. Problem State Identification (The Void)",
                    base_url: "https://error-of.netlify.app/thread/"
                },
                {
                    name: "4. Temporal Communication Hub",
                    base_url: "https://temporal-todo-hub.netlify.app/thread/"
                }
            ];

            const outputDiv = document.getElementById('modes-output');
            outputDiv.innerHTML = ''; // Clear loading message

            // 3. Loop through and assign a unique (but related) ID to each mode
            modes.forEach((mode, index) => {
                // Introduce a slight offset based on the mode index to ensure four distinct IDs
                const uniqueHash = simpleHash(masterInput + index.toString()).toUpperCase();
                const modeUrl = mode.base_url + uniqueHash;

                const modeElement = document.createElement('div');
                modeElement.className = 'mode-section';
                modeElement.innerHTML = `
                    <div class="mode-title">${mode.name}</div>
                    <div class="mode-url">
                        Bridge ID: <strong>${uniqueHash}</strong>
                        <code>${modeUrl}</code>
                    </div>
                `;
                outputDiv.appendChild(modeElement);
            });
        }

        generateBridgeNetwork();
    </script>
</body>
</html>
