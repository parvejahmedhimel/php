<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>⚡ PHP Compiler</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.65.2/codemirror.min.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.65.2/theme/dracula.min.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #6c5ce7;
            --dark: #2d3436;
            --light: #f5f6fa;
            --danger: #ff4757;
            --success: #00b894;
            --info: #0984e3;
            --php: #787cb5;
        }

        body {
            font-family: 'Segoe UI', sans-serif;
            background: var(--light);
            color: var(--dark);
            margin: 0;
            padding: 20px;
            transition: all 0.3s;
        }

        body.dark-mode {
            background: var(--dark);
            color: var(--light);
        }

        .container {
            max-width: 1000px;
            margin: 0 auto;
        }

        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }

        h1 {
            color: var(--php);
        }

        .btn {
            padding: 12px 20px;
            border: none;
            border-radius: 6px;
            cursor: pointer;
            font-weight: bold;
            margin-right: 12px;
            font-size: 16px;
            transition: all 0.2s;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }

        .btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
        }

        .btn-run {
            background: var(--php);
            color: white;
        }

        .btn-clear {
            background: var(--danger);
            color: white;
        }

        .btn-upload {
            background: var(--success);
            color: white;
        }

        .btn-save {
            background: var(--info);
            color: white;
        }

        .button-container {
            margin-bottom: 20px;
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
        }

        .editor-container {
            display: flex;
            gap: 20px;
            height: 60vh;
        }

        .code-editor {
            flex: 1;
            height: 100%;
            overflow: hidden;
            border-radius: 8px;
        }

        .CodeMirror {
            height: 100% !important;
            border-radius: 8px;
            font-size: 16px;
        }

        .output-container {
            flex: 1;
            background: white;
            border-radius: 8px;
            padding: 15px;
            overflow-y: auto;
            height: 100%;
            box-sizing: border-box;
        }

        .dark-mode .output-container {
            background: #1e272e;
        }

        #output {
            white-space: pre-wrap;
            font-family: monospace;
            height: calc(100% - 30px);
            overflow-y: auto;
        }

        .error {
            color: var(--danger);
        }

        #fileInput {
            display: none;
        }

        .loading {
            display: inline-block;
            width: 20px;
            height: 20px;
            border: 3px solid rgba(255,255,255,.3);
            border-radius: 50%;
            border-top-color: white;
            animation: spin 1s ease-in-out infinite;
        }

        @keyframes spin {
            to { transform: rotate(360deg); }
        }

        .api-notice {
            background: #fff3cd;
            color: #856404;
            padding: 10px;
            border-radius: 5px;
            margin-bottom: 15px;
            border-left: 4px solid #ffeeba;
        }

        .dark-mode .api-notice {
            background: #343a40;
            color: #ffeeba;
            border-left-color: #ffc107;
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1><i class="fab fa-php"></i> PHP Compiler</h1>
            <button id="themeBtn" class="btn">
                <i class="fas fa-moon"></i> Dark Mode
            </button>
        </header>

        <div class="api-notice">
            <strong>Note:</strong> This compiler uses a free PHP execution API. For heavy usage or sensitive code, 
            consider <a href="#" id="localBtn">setting up a local server</a>.
        </div>

        <div class="button-container">
            <button id="runBtn" class="btn btn-run">
                <i class="fas fa-play"></i> Run Code
            </button>
            <button id="clearBtn" class="btn btn-clear">
                <i class="fas fa-trash"></i> Clear Output
            </button>
            <button id="uploadBtn" class="btn btn-upload">
                <i class="fas fa-upload"></i> Load PHP File
            </button>
            <button id="saveBtn" class="btn btn-save">
                <i class="fas fa-download"></i> Save Code
            </button>
            <input type="file" id="fileInput" accept=".php,.txt">
        </div>

        <div class="editor-container">
            <div class="code-editor">
                <textarea id="editor"><?php
// Welcome to PHP Compiler
// Basic PHP code example

function greet($name) {
    return "Hello, " . $name . "!";
}

$message = greet("PHP Developer");
echo $message . "\n\n";

// Show server information
echo "Current Date: " . date('Y-m-d') . "\n";
echo "PHP Version: " . phpversion() . "\n";

// Simple calculation
$a = 5;
$b = 3;
echo "{$a} + {$b} = " . ($a + $b) . "\n";
?></textarea>
            </div>
            <div class="output-container">
                <h3><i class="fas fa-terminal"></i> Output</h3>
                <div id="output"></div>
            </div>
        </div>
    </div>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.65.2/codemirror.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.65.2/mode/htmlmixed/htmlmixed.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.65.2/mode/php/php.min.js"></script>
    <script>
        // Initialize Editor
        const editor = CodeMirror.fromTextArea(document.getElementById('editor'), {
            mode: 'application/x-httpd-php',
            theme: 'default',
            lineNumbers: true,
            indentUnit: 4,
            lineWrapping: true
        });

        // DOM Elements
        const outputDiv = document.getElementById('output');
        const runBtn = document.getElementById('runBtn');
        const clearBtn = document.getElementById('clearBtn');
        const themeBtn = document.getElementById('themeBtn');
        const uploadBtn = document.getElementById('uploadBtn');
        const saveBtn = document.getElementById('saveBtn');
        const fileInput = document.getElementById('fileInput');
        const localBtn = document.getElementById('localBtn');

        // Available API endpoints (fallback system)
        const API_ENDPOINTS = [
            'https://php-compiler.fly.dev/compile',
            'https://php-compiler-api.herokuapp.com/compile'
        ];

        // Current API index
        let currentApiIndex = 0;

        // Run PHP Code with fallback mechanism
        async function runCode() {
            outputDiv.innerHTML = '';
            const originalText = runBtn.innerHTML;
            runBtn.innerHTML = '<span class="loading"></span> Running...';
            runBtn.disabled = true;
            
            try {
                const response = await fetch(API_ENDPOINTS[currentApiIndex], {
                    method: 'POST',
                    headers: {
                        'Content-Type': 'application/json',
                    },
                    body: JSON.stringify({
                        code: editor.getValue()
                    })
                });

                if (!response.ok) throw new Error('API Error');
                
                const data = await response.json();
                
                if (data.error) {
                    outputDiv.innerHTML = `<span class="error">PHP Error: ${data.error}</span>`;
                } else {
                    outputDiv.textContent = data.output || "No output (code executed successfully)";
                }
            } catch (error) {
                // Try next API endpoint if available
                if (currentApiIndex < API_ENDPOINTS.length - 1) {
                    currentApiIndex++;
                    outputDiv.innerHTML = `<span class="error">Trying alternative API...</span>`;
                    setTimeout(runCode, 1000);
                    return;
                }
                
                outputDiv.innerHTML = `
                    <span class="error">
                        Connection Error: ${error.message}<br><br>
                        Possible solutions:<br>
                        1. Check your internet connection<br>
                        2. Try again later<br>
                        3. <a href="#" id="localBtn">Setup local server</a>
                    </span>
                `;
            } finally {
                runBtn.innerHTML = originalText;
                runBtn.disabled = false;
            }
        }

        // Clear Output
        function clearOutput() {
            outputDiv.innerHTML = '';
        }

        // Toggle Dark Mode
        function toggleTheme() {
            document.body.classList.toggle('dark-mode');
            editor.setOption('theme', 
                document.body.classList.contains('dark-mode') ? 'dracula' : 'default'
            );
            themeBtn.innerHTML = document.body.classList.contains('dark-mode') 
                ? '<i class="fas fa-sun"></i> Light Mode' 
                : '<i class="fas fa-moon"></i> Dark Mode';
        }

        // Handle file upload
        function handleFileUpload(event) {
            const file = event.target.files[0];
            if (!file) return;

            const reader = new FileReader();
            reader.onload = function(e) {
                editor.setValue(e.target.result);
            };
            reader.readAsText(file);
        }

        // Save code to file
        function saveCode() {
            const code = editor.getValue();
            const blob = new Blob([code], { type: 'text/php' });
            const url = URL.createObjectURL(blob);
            
            const a = document.createElement('a');
            a.href = url;
            a.download = 'script.php' || 'code.php';
            document.body.appendChild(a);
            a.click();
            
            setTimeout(() => {
                document.body.removeChild(a);
                URL.revokeObjectURL(url);
            }, 100);
        }

        // Show local setup instructions
        function showLocalSetup() {
            outputDiv.innerHTML = `
                <strong>How to setup local PHP server:</strong><br><br>
                1. Install XAMPP/WAMP/MAMP on your computer<br>
                2. Save your PHP files in the htdocs/www folder<br>
                3. Access via http://localhost/yourfile.php<br><br>
                <i>For security reasons, online compilers cannot execute certain PHP functions.</i>
            `;
            return false;
        }

        // Event Listeners
        runBtn.addEventListener('click', runCode);
        clearBtn.addEventListener('click', clearOutput);
        themeBtn.addEventListener('click', toggleTheme);
        uploadBtn.addEventListener('click', () => fileInput.click());
        fileInput.addEventListener('change', handleFileUpload);
        saveBtn.addEventListener('click', saveCode);
        localBtn.addEventListener('click', (e) => {
            e.preventDefault();
            showLocalSetup();
        });

        // Check if online
        window.addEventListener('offline', () => {
            outputDiv.innerHTML = `<span class="error">You are offline. Please check your internet connection.</span>`;
        });
    </script>
</body>
</html>
