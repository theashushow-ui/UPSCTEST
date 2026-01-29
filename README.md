<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>UPSC Test Series Platform</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        :root {
            --primary: #1a237e;
            --primary-light: #534bae;
            --secondary: #ff5722;
            --light: #f5f5f5;
            --dark: #212121;
            --success: #4caf50;
            --danger: #f44336;
        }
        
        body {
            background-color: #f0f2f5;
            color: var(--dark);
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        /* Header */
        header {
            background: linear-gradient(135deg, var(--primary), var(--primary-light));
            color: white;
            padding: 20px 0;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .logo h1 {
            font-size: 1.8rem;
            font-weight: 700;
        }
        
        .logo-icon {
            font-size: 2rem;
        }
        
        nav ul {
            display: flex;
            list-style: none;
            gap: 25px;
        }
        
        nav a {
            color: white;
            text-decoration: none;
            font-weight: 600;
            padding: 8px 16px;
            border-radius: 4px;
            transition: all 0.3s ease;
        }
        
        nav a:hover, nav a.active {
            background-color: rgba(255, 255, 255, 0.15);
        }
        
        /* Main Content */
        .dashboard {
            display: grid;
            grid-template-columns: 1fr 300px;
            gap: 30px;
            margin-top: 30px;
        }
        
        .card {
            background: white;
            border-radius: 10px;
            padding: 25px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            margin-bottom: 25px;
        }
        
        .card h2 {
            color: var(--primary);
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid #eee;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .card h2 i {
            color: var(--secondary);
        }
        
        /* Test Controls */
        .test-controls {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-bottom: 25px;
        }
        
        .control-group {
            display: flex;
            flex-direction: column;
        }
        
        label {
            font-weight: 600;
            margin-bottom: 8px;
            color: var(--dark);
        }
        
        input, select, textarea {
            padding: 12px 15px;
            border: 1px solid #ddd;
            border-radius: 6px;
            font-size: 1rem;
            transition: all 0.3s ease;
        }
        
        input:focus, select:focus, textarea:focus {
            outline: none;
            border-color: var(--primary-light);
            box-shadow: 0 0 0 3px rgba(26, 35, 126, 0.1);
        }
        
        .btn {
            padding: 12px 24px;
            border: none;
            border-radius: 6px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }
        
        .btn-primary {
            background-color: var(--primary);
            color: white;
        }
        
        .btn-primary:hover {
            background-color: var(--primary-light);
            transform: translateY(-2px);
        }
        
        .btn-secondary {
            background-color: #e0e0e0;
            color: var(--dark);
        }
        
        .btn-secondary:hover {
            background-color: #d0d0d0;
        }
        
        .btn-success {
            background-color: var(--success);
            color: white;
        }
        
        .btn-danger {
            background-color: var(--danger);
            color: white;
        }
        
        /* Timer */
        .timer-display {
            background: linear-gradient(135deg, #1a237e, #283593);
            color: white;
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            margin-bottom: 20px;
        }
        
        .timer-display h3 {
            margin-bottom: 10px;
            font-size: 1.2rem;
        }
        
        #timer {
            font-size: 3rem;
            font-weight: 700;
            font-family: 'Courier New', monospace;
            margin: 10px 0;
        }
        
        .timer-controls {
            display: flex;
            gap: 10px;
            justify-content: center;
        }
        
        /* PDF Viewer */
        .pdf-viewer {
            width: 100%;
            height: 600px;
            border: 1px solid #ddd;
            border-radius: 8px;
            overflow: hidden;
            margin-bottom: 20px;
        }
        
        .pdf-container {
            width: 100%;
            height: 100%;
            background-color: #f9f9f9;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-direction: column;
            padding: 20px;
        }
        
        .pdf-placeholder {
            text-align: center;
            color: #777;
        }
        
        .pdf-placeholder i {
            font-size: 4rem;
            margin-bottom: 15px;
            color: var(--primary-light);
        }
        
        /* Test List */
        .test-list {
            display: grid;
            gap: 15px;
        }
        
        .test-item {
            background: #f9f9f9;
            padding: 18px;
            border-radius: 8px;
            border-left: 4px solid var(--primary);
            transition: all 0.3s ease;
        }
        
        .test-item:hover {
            background: #f0f0f0;
            transform: translateX(5px);
        }
        
        .test-item h4 {
            color: var(--primary);
            margin-bottom: 8px;
        }
        
        .test-meta {
            display: flex;
            gap: 15px;
            font-size: 0.9rem;
            color: #666;
            margin-bottom: 10px;
        }
        
        .test-actions {
            display: flex;
            gap: 10px;
            margin-top: 12px;
        }
        
        /* Upload Area */
        .upload-area {
            border: 2px dashed #ccc;
            border-radius: 10px;
            padding: 40px 20px;
            text-align: center;
            background-color: #fafafa;
            margin-bottom: 20px;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .upload-area:hover, .upload-area.dragover {
            border-color: var(--primary);
            background-color: #f0f5ff;
        }
        
        .upload-icon {
            font-size: 3rem;
            color: var(--primary-light);
            margin-bottom: 15px;
        }
        
        /* Answer Submission */
        .answer-form {
            display: grid;
            gap: 15px;
        }
        
        .answer-row {
            display: grid;
            grid-template-columns: 50px 1fr;
            gap: 15px;
            align-items: center;
            padding: 15px;
            background: #f9f9f9;
            border-radius: 6px;
        }
        
        .answer-row input {
            padding: 10px 15px;
        }
        
        /* Footer */
        footer {
            background-color: var(--dark);
            color: #bbb;
            padding: 30px 0;
            margin-top: 50px;
            text-align: center;
        }
        
        /* Responsive */
        @media (max-width: 992px) {
            .dashboard {
                grid-template-columns: 1fr;
            }
            
            .header-content {
                flex-direction: column;
                gap: 20px;
            }
            
            nav ul {
                flex-wrap: wrap;
                justify-content: center;
            }
        }
        
        @media (max-width: 768px) {
            .test-controls {
                grid-template-columns: 1fr;
            }
            
            .timer-controls {
                flex-wrap: wrap;
            }
        }
    </style>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container header-content">
            <div class="logo">
                <div class="logo-icon"><i class="fas fa-graduation-cap"></i></div>
                <h1>UPSC Test Series Platform</h1>
            </div>
            <nav>
                <ul>
                    <li><a href="#" class="active"><i class="fas fa-home"></i> Dashboard</a></li>
                    <li><a href="#"><i class="fas fa-book-open"></i> Tests</a></li>
                    <li><a href="#"><i class="fas fa-chart-bar"></i> Analytics</a></li>
                    <li><a href="#"><i class="fas fa-user"></i> Admin</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <main class="container">
        <!-- Test Controls -->
        <div class="card">
            <h2><i class="fas fa-cogs"></i> Test Configuration</h2>
            <div class="test-controls">
                <div class="control-group">
                    <label for="testName"><i class="fas fa-heading"></i> Test Name</label>
                    <input type="text" id="testName" placeholder="e.g., UPSC Prelims GS Paper 1 - Mock Test 1">
                </div>
                <div class="control-group">
                    <label for="testDuration"><i class="fas fa-clock"></i> Duration (minutes)</label>
                    <input type="number" id="testDuration" value="120" min="1">
                </div>
                <div class="control-group">
                    <label for="testDate"><i class="fas fa-calendar"></i> Schedule Date</label>
                    <input type="date" id="testDate">
                </div>
                <div class="control-group">
                    <label for="maxMarks"><i class="fas fa-star"></i> Maximum Marks</label>
                    <input type="number" id="maxMarks" value="200">
                </div>
            </div>
            <button class="btn btn-primary" id="saveConfig"><i class="fas fa-save"></i> Save Test Configuration</button>
        </div>

        <div class="dashboard">
            <!-- Left Column: PDF & Test Interface -->
            <div>
                <!-- Timer -->
                <div class="timer-display">
                    <h3><i class="fas fa-hourglass-half"></i> Test Timer</h3>
                    <div id="timer">02:00:00</div>
                    <p>Time remaining for current test</p>
                    <div class="timer-controls">
                        <button class="btn btn-secondary" id="startTimer"><i class="fas fa-play"></i> Start Timer</button>
                        <button class="btn btn-secondary" id="pauseTimer"><i class="fas fa-pause"></i> Pause</button>
                        <button class="btn btn-danger" id="resetTimer"><i class="fas fa-redo"></i> Reset</button>
                    </div>
                </div>

                <!-- PDF Upload & Viewer -->
                <div class="card">
                    <h2><i class="fas fa-file-pdf"></i> Question Paper (PDF)</h2>
                    <div class="upload-area" id="uploadArea">
                        <div class="upload-icon">
                            <i class="fas fa-cloud-upload-alt"></i>
                        </div>
                        <h3>Upload Question Paper PDF</h3>
                        <p>Drag & drop your PDF file here or click to browse</p>
                        <p class="small-text">Maximum file size: 10MB</p>
                        <input type="file" id="pdfUpload" accept=".pdf" hidden>
                        <button class="btn btn-secondary" id="browseBtn" style="margin-top: 15px;">
                            <i class="fas fa-folder-open"></i> Browse Files
                        </button>
                    </div>
                    
                    <div class="pdf-viewer">
                        <div class="pdf-container" id="pdfContainer">
                            <div class="pdf-placeholder" id="pdfPlaceholder">
                                <i class="fas fa-file-pdf"></i>
                                <h3>No PDF Loaded</h3>
                                <p>Upload a question paper PDF to display it here</p>
                            </div>
                            <!-- PDF will be displayed here -->
                        </div>
                    </div>
                    
                    <div class="pdf-controls" style="display: flex; gap: 10px; margin-top: 15px;">
                        <button class="btn btn-secondary" id="prevPage"><i class="fas fa-chevron-left"></i> Previous</button>
                        <button class="btn btn-secondary" id="nextPage"><i class="fas fa-chevron-right"></i> Next</button>
                        <span style="margin-left: auto; padding: 10px; font-weight: 600;">Page: <span id="currentPage">1</span></span>
                    </div>
                </div>

                <!-- Answer Submission -->
                <div class="card">
                    <h2><i class="fas fa-pencil-alt"></i> Answer Submission</h2>
                    <div class="answer-form" id="answerForm">
                        <div class="answer-row">
                            <span class="question-number">Q1</span>
                            <input type="text" placeholder="Enter your answer for question 1">
                        </div>
                        <div class="answer-row">
                            <span class="question-number">Q2</span>
                            <input type="text" placeholder="Enter your answer for question 2">
                        </div>
                        <div class="answer-row">
                            <span class="question-number">Q3</span>
                            <input type="text" placeholder="Enter your answer for question 3">
                        </div>
                        <div class="answer-row">
                            <span class="question-number">Q4</span>
                            <input type="text" placeholder="Enter your answer for question 4">
                        </div>
                        <div class="answer-row">
                            <span class="question-number">Q5</span>
                            <input type="text" placeholder="Enter your answer for question 5">
                        </div>
                    </div>
                    <button class="btn btn-success" id="submitTest" style="margin-top: 20px; width: 100%;">
                        <i class="fas fa-paper-plane"></i> Submit Test Answers
                    </button>
                </div>
            </div>

            <!-- Right Column: Test List & Answer Key -->
            <div>
                <!-- Scheduled Tests -->
                <div class="card">
                    <h2><i class="fas fa-list"></i> Scheduled Tests</h2>
                    <div class="test-list">
                        <div class="test-item">
                            <h4>UPSC Prelims GS Paper 1 - Mock 5</h4>
                            <div class="test-meta">
                                <span><i class="fas fa-clock"></i> 120 min</span>
                                <span><i class="fas fa-star"></i> 200 marks</span>
                            </div>
                            <p>General Studies - Current Affairs & History Focus</p>
                            <div class="test-actions">
                                <button class="btn btn-primary btn-small"><i class="fas fa-play"></i> Start</button>
                                <button class="btn btn-secondary btn-small"><i class="fas fa-eye"></i> Preview</button>
                            </div>
                        </div>
                        <div class="test-item">
                            <h4>CSAT Paper 2 - Mock 3</h4>
                            <div class="test-meta">
                                <span><i class="fas fa-clock"></i> 120 min</span>
                                <span><i class="fas fa-star"></i> 200 marks</span>
                            </div>
                            <p>Comprehension, Reasoning & Quantitative Aptitude</p>
                            <div class="test-actions">
                                <button class="btn btn-primary btn-small"><i class="fas fa-play"></i> Start</button>
                                <button class="btn btn-secondary btn-small"><i class="fas fa-eye"></i> Preview</button>
                            </div>
                        </div>
                        <div class="test-item">
                            <h4>Mains Essay Paper - Practice 2</h4>
                            <div class="test-meta">
                                <span><i class="fas fa-clock"></i> 180 min</span>
                                <span><i class="fas fa-star"></i> 250 marks</span>
                            </div>
                            <p>Essay writing on contemporary issues</p>
                            <div class="test-actions">
                                <button class="btn btn-primary btn-small"><i class="fas fa-play"></i> Start</button>
                                <button class="btn btn-secondary btn-small"><i class="fas fa-eye"></i> Preview</button>
                            </div>
                        </div>
                    </div>
                    <button class="btn btn-secondary" style="width: 100%; margin-top: 15px;">
                        <i class="fas fa-plus"></i> Create New Test
                    </button>
                </div>

                <!-- Answer Key Upload -->
                <div class="card">
                    <h2><i class="fas fa-key"></i> Answer Key Management</h2>
                    <p style="margin-bottom: 15px;">Upload answer key PDF for auto-grading</p>
                    <div class="upload-area" style="padding: 20px;" id="answerKeyArea">
                        <div class="upload-icon">
                            <i class="fas fa-key"></i>
                        </div>
                        <h4>Upload Answer Key</h4>
                        <p>PDF with correct answers for auto-grading</p>
                        <input type="file" id="answerKeyUpload" accept=".pdf" hidden>
                        <button class="btn btn-secondary" id="browseAnswerKey" style="margin-top: 10px;">
                            <i class="fas fa-upload"></i> Upload Answer Key
                        </button>
                    </div>
                    <div id="answerKeyStatus" style="margin-top: 15px; padding: 10px; background: #e8f5e9; border-radius: 6px; display: none;">
                        <i class="fas fa-check-circle" style="color: var(--success);"></i>
                        <span>Answer key uploaded successfully. Ready for auto-grading.</span>
                    </div>
                </div>

                <!-- Quick Stats -->
                <div class="card">
                    <h2><i class="fas fa-chart-line"></i> Quick Stats</h2>
                    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px; margin-top: 10px;">
                        <div style="text-align: center; padding: 15px; background: #e3f2fd; border-radius: 8px;">
                            <h3 style="color: var(--primary); font-size: 2rem;">12</h3>
                            <p>Tests Created</p>
                        </div>
                        <div style="text-align: center; padding: 15px; background: #f3e5f5; border-radius: 8px;">
                            <h3 style="color: var(--primary-light); font-size: 2rem;">156</h3>
                            <p>Students Enrolled</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </main>

    <footer>
        <div class="container">
            <p>UPSC Test Series Platform &copy; 2023 | Designed for UPSC Aspirants</p>
            <p style="margin-top: 10px; font-size: 0.9rem;">
                <i class="fas fa-envelope"></i> admin@upsctestseries.com | 
                <i class="fas fa-phone"></i> +91 9876543210
            </p>
        </div>
    </footer>

    <script>
        // DOM Elements
        const pdfUpload = document.getElementById('pdfUpload');
        const browseBtn = document.getElementById('browseBtn');
        const uploadArea = document.getElementById('uploadArea');
        const pdfContainer = document.getElementById('pdfContainer');
        const pdfPlaceholder = document.getElementById('pdfPlaceholder');
        const answerKeyUpload = document.getElementById('answerKeyUpload');
        const browseAnswerKey = document.getElementById('browseAnswerKey');
        const answerKeyArea = document.getElementById('answerKeyArea');
        const answerKeyStatus = document.getElementById('answerKeyStatus');
        const startTimerBtn = document.getElementById('startTimer');
        const pauseTimerBtn = document.getElementById('pauseTimer');
        const resetTimerBtn = document.getElementById('resetTimer');
        const timerDisplay = document.getElementById('timer');
        const testNameInput = document.getElementById('testName');
        const testDurationInput = document.getElementById('testDuration');
        const saveConfigBtn = document.getElementById('saveConfig');
        const submitTestBtn = document.getElementById('submitTest');
        const prevPageBtn = document.getElementById('prevPage');
        const nextPageBtn = document.getElementById('nextPage');
        const currentPageSpan = document.getElementById('currentPage');

        // Timer variables
        let timerInterval;
        let totalSeconds = 7200; // 2 hours in seconds
        let isTimerRunning = false;
        let currentPage = 1;

        // Initialize timer display
        updateTimerDisplay();

        // PDF Upload functionality
        browseBtn.addEventListener('click', () => pdfUpload.click());
        browseAnswerKey.addEventListener('click', () => answerKeyUpload.click());

        uploadArea.addEventListener('dragover', (e) => {
            e.preventDefault();
            uploadArea.classList.add('dragover');
        });

        uploadArea.addEventListener('dragleave', () => {
            uploadArea.classList.remove('dragover');
        });

        uploadArea.addEventListener('drop', (e) => {
            e.preventDefault();
            uploadArea.classList.remove('dragover');
            
            if (e.dataTransfer.files.length) {
                const file = e.dataTransfer.files[0];
                if (file.type === 'application/pdf') {
                    handlePDFUpload(file);
                } else {
                    alert('Please upload a PDF file only.');
                }
            }
        });

        pdfUpload.addEventListener('change', (e) => {
            if (e.target.files.length) {
                handlePDFUpload(e.target.files[0]);
            }
        });

        answerKeyUpload.addEventListener('change', (e) => {
            if (e.target.files.length) {
                const file = e.target.files[0];
                if (file.type === 'application/pdf') {
                    handleAnswerKeyUpload(file);
                } else {
                    alert('Please upload a PDF file only.');
                }
            }
        });

        function handlePDFUpload(file) {
            // In a real implementation, you would upload to a server
            // For this demo, we'll simulate success
            pdfPlaceholder.innerHTML = `
                <i class="fas fa-check-circle" style="color: var(--success);"></i>
                <h3>${file.name}</h3>
                <p>PDF uploaded successfully</p>
                <p class="small-text">${(file.size / 1024 / 1024).toFixed(2)} MB</p>
            `;
            
            // Simulate PDF display
            simulatePDFDisplay();
            
            // Show success message
            alert(`Question paper "${file.name}" uploaded successfully!`);
        }

        function handleAnswerKeyUpload(file) {
            // In a real implementation, you would upload to a server
            answerKeyStatus.style.display = 'block';
            answerKeyArea.innerHTML = `
                <div class="upload-icon">
                    <i class="fas fa-check-circle" style="color: var(--success);"></i>
                </div>
                <h4>${file.name}</h4>
                <p>Answer key uploaded successfully</p>
                <p class="small-text">Ready for auto-grading</p>
            `;
            
            alert(`Answer key "${file.name}" uploaded successfully! Auto-grading is now enabled.`);
        }

        // Timer functionality
        startTimerBtn.addEventListener('click', startTimer);
        pauseTimerBtn.addEventListener('click', pauseTimer);
        resetTimerBtn.addEventListener('click', resetTimer);

        function startTimer() {
            if (isTimerRunning) return;
            
            isTimerRunning = true;
            timerInterval = setInterval(() => {
                if (totalSeconds <= 0) {
                    clearInterval(timerInterval);
                    timerComplete();
                    return;
                }
                totalSeconds--;
                updateTimerDisplay();
            }, 1000);
            
            startTimerBtn.disabled = true;
            pauseTimerBtn.disabled = false;
        }

        function pauseTimer() {
            clearInterval(timerInterval);
            isTimerRunning = false;
            startTimerBtn.disabled = false;
            pauseTimerBtn.disabled = true;
        }

        function resetTimer() {
            clearInterval(timerInterval);
            isTimerRunning = false;
            totalSeconds = parseInt(testDurationInput.value) * 60;
            updateTimerDisplay();
            startTimerBtn.disabled = false;
            pauseTimerBtn.disabled = false;
        }

        function updateTimerDisplay() {
            const hours = Math.floor(totalSeconds / 3600);
            const minutes = Math.floor((totalSeconds % 3600) / 60);
            const seconds = totalSeconds % 60;
            
            timerDisplay.textContent = 
                `${hours.toString().padStart(2, '0')}:${minutes.toString().padStart(2, '0')}:${seconds.toString().padStart(2, '0')}`;
            
            // Change color when time is running low
            if (totalSeconds < 300) { // Less than 5 minutes
                timerDisplay.style.color = 'var(--danger)';
            } else if (totalSeconds < 600) { // Less than 10 minutes
                timerDisplay.style.color = '#ff9800';
            } else {
                timerDisplay.style.color = 'white';
            }
        }

        function timerComplete() {
            timerDisplay.textContent = "00:00:00";
            timerDisplay.style.color = 'var(--danger)';
            alert("Time's up! Test will be submitted automatically.");
            // In real implementation, auto-submit the test
        }

        // Save configuration
        saveConfigBtn.addEventListener('click', () => {
            const testName = testNameInput.value || 'Untitled Test';
            const duration = testDurationInput.value;
            
            // Update timer with new duration
            totalSeconds = duration * 60;
            updateTimerDisplay();
            
            // Show success message
            alert(`Test configuration saved:\n\nTest Name: ${testName}\nDuration: ${duration} minutes`);
            
            // Add to test list (in a real app, this would be saved to database)
            const testList = document.querySelector('.test-list');
            const newTestItem = document.createElement('div');
            newTestItem.className = 'test-item';
            newTestItem.innerHTML = `
                <h4>${testName}</h4>
                <div class="test-meta">
                    <span><i class="fas fa-clock"></i> ${duration} min</span>
                    <span><i class="fas fa-star"></i> 200 marks</span>
                </div>
                <p>Newly created test - ready for students</p>
                <div class="test-actions">
                    <button class="btn btn-primary btn-small"><i class="fas fa-play"></i> Start</button>
                    <button class="btn btn-secondary btn-small"><i class="fas fa-eye"></i> Preview</button>
                </div>
            `;
            testList.prepend(newTestItem);
        });

        // Submit test
        submitTestBtn.addEventListener('click', () => {
            // Collect answers
            const answerInputs = document.querySelectorAll('#answerForm input');
            const answers = Array.from(answerInputs).map((input, index) => ({
                question: index + 1,
                answer: input.value || 'Not answered'
            }));
            
            // Show submission confirmation
            const answeredCount = answers.filter(a => a.answer !== 'Not answered').length;
            
            if (confirm(`Submit test with ${answeredCount} questions answered?`)) {
                // In real implementation, send to server
                alert(`Test submitted successfully!\n\nQuestions answered: ${answeredCount}/5\n\nAnswers have been saved for grading.`);
                
                // Reset form
                answerInputs.forEach(input => input.value = '');
                
                // Stop timer if running
                pauseTimer();
            }
        });

        // Simulate PDF page navigation
        function simulatePDFDisplay() {
            currentPage = 1;
            updatePageDisplay();
            
            prevPageBtn.addEventListener('click', () => {
                if (currentPage > 1) {
                    currentPage--;
                    updatePageDisplay();
                }
            });
            
            nextPageBtn.addEventListener('click', () => {
                currentPage++;
                updatePageDisplay();
            });
        }

        function updatePageDisplay() {
            currentPageSpan.textContent = currentPage;
            prevPageBtn.disabled = currentPage <= 1;
            // In a real implementation, you would render the actual PDF page
        }

        // Initialize test name with today's date
        const today = new Date().toISOString().split('T')[0];
        const formattedDate = new Date().toLocaleDateString('en-IN', { 
            day: 'numeric', 
            month: 'short', 
            year: 'numeric' 
        });
        testNameInput.value = `UPSC Prelims Mock Test - ${formattedDate}`;
        testDateInput.value = today;

        // Initialize page display
        updatePageDisplay();
    </script>
</body>
</html>
