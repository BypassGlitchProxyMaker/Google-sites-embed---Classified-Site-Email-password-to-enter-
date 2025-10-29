# Google-sites-embed---Classified-Site-Email-password-to-enter-

Code:

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Email Validator</title>
  <style>
    body {
      font-family: 'Roboto', Arial, sans-serif;
      background: linear-gradient(135deg, #f5f7fa 0%, #e4edf9 100%);
      margin: 0;
      padding: 20px;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
    }
   
    .container {
      max-width: 600px;
      width: 100%;
      background: white;
      border-radius: 16px;
      box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
      overflow: hidden;
    }
   
    .header {
      background: #4f46e5;
      color: white;
      padding: 24px;
      text-align: center;
    }
   
    .header h1 {
      margin: 0;
      font-size: 24px;
      font-weight: 700;
    }
   
    .header p {
      margin: 8px 0 0;
      opacity: 0.9;
    }
   
    .content {
      padding: 24px;
    }
   
    .form-group {
      margin-bottom: 20px;
    }
   
    .form-group label {
      display: block;
      margin-bottom: 8px;
      font-weight: 500;
      color: #374151;
    }
   
    .form-control {
      width: 100%;
      padding: 14px;
      border: 1px solid #d1d5db;
      border-radius: 8px;
      font-size: 16px;
      box-sizing: border-box;
      transition: border-color 0.2s;
    }
   
    .form-control:focus {
      outline: none;
      border-color: #4f46e5;
      box-shadow: 0 0 0 3px rgba(79, 70, 229, 0.1);
    }
   
    .btn {
      width: 100%;
      padding: 14px;
      background: #4f46e5;
      color: white;
      border: none;
      border-radius: 8px;
      font-size: 16px;
      font-weight: 600;
      cursor: pointer;
      transition: background 0.2s;
    }
   
    .btn:hover {
      background: #4338ca;
    }
   
    .btn-outline {
      background: white;
      color: #4f46e5;
      border: 1px solid #c7d2fe;
    }
   
    .btn-outline:hover {
      background: #f0f4ff;
    }
   
    .status-message {
      padding: 16px;
      border-radius: 8px;
      text-align: center;
      margin-bottom: 20px;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 12px;
    }
   
    .status-success {
      background: #dcfce7;
      color: #166534;
    }
   
    .status-error {
      background: #fee2e2;
      color: #991b1b;
    }
   
    .icon {
      width: 24px;
      height: 24px;
    }
   
    .embed-container {
      margin: 20px 0;
      border-radius: 8px;
      overflow: hidden;
      box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
    }
   
    .embed-container iframe {
      width: 100%;
      height: 400px;
      border: none;
    }
   
    .hidden {
      display: none;
    }
   
    .text-center {
      text-align: center;
    }
   
    .mt-4 {
      margin-top: 16px;
    }
   
    .step-indicator {
      display: flex;
      justify-content: center;
      margin-bottom: 20px;
    }
   
    .step {
      width: 30px;
      height: 30px;
      border-radius: 50%;
      background: #e5e7eb;
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: bold;
      margin: 0 10px;
      position: relative;
    }
   
    .step.active {
      background: #4f46e5;
      color: white;
    }
   
    .step.completed {
      background: #10b981;
      color: white;
    }
   
    .step:not(:last-child):after {
      content: '';
      position: absolute;
      width: 40px;
      height: 2px;
      background: #e5e7eb;
      left: 40px;
      top: 50%;
      transform: translateY(-50%);
    }
   
    .hint {
      text-align: center;
      color: #6b7280;
      font-size: 14px;
      margin-top: 10px;
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="header">
      <h1>Content Access Portal</h1>
      <p>Enter your email and code to access exclusive content</p>
    </div>
   
    <div class="content">
      <div class="step-indicator">
        <div class="step active" id="step1">1</div>
        <div class="step" id="step2">2</div>
      </div>
     
      <div id="email-step">
        <form id="email-form">
          <div class="form-group">
            <label for="email-input">Email Address</label>
            <input
              type="email"
              id="email-input"
              class="form-control"
              placeholder="Enter your email"
              required
            />
          </div>
          <button type="submit" class="btn">
            Continue
          </button>
        </form>
      </div>
     
      <div id="code-step" class="hidden">
        <form id="code-form">
          <div class="form-group">
            <label for="code-input">Access Code</label>
            <input
              type="password"
              id="code-input"
              class="form-control"
              placeholder="Enter access code"
              required
            />
          </div>
          <div class="hint">Hint: Be a beta tester </div>
          <button type="submit" class="btn mt-4">
            Validate Code
          </button>
          <button type="button" id="back-to-email" class="btn btn-outline mt-4">
            Back
          </button>
        </form>
      </div>
     
      <div id="result-container" class="hidden">
        <div id="status-message" class="status-message">
          <!-- Status message will be inserted here -->
        </div>
       
        <div id="content-container" class="hidden">
          <h3 class="text-center" style="margin: 0 0 16px; color: #374151; font-weight: 600;">Your Exclusive Content</h3>
          <div class="embed-container">
            <iframe
              src="https://blockblast.org/"
              title="Julgames Embed"
              allowfullscreen
            ></iframe>
          </div>
        </div>
       
        <button id="reset-button" class="btn btn-outline mt-4">
          Start Over
        </button>
      </div>
    </div>
  </div>

  <script>
    document.addEventListener('DOMContentLoaded', function() {
      // DOM Elements
      const emailForm = document.getElementById('email-form');
      const codeForm = document.getElementById('code-form');
      const emailInput = document.getElementById('email-input');
      const codeInput = document.getElementById('code-input');
      const emailStep = document.getElementById('email-step');
      const codeStep = document.getElementById('code-step');
      const resultContainer = document.getElementById('result-container');
      const statusMessage = document.getElementById('status-message');
      const contentContainer = document.getElementById('content-container');
      const resetButton = document.getElementById('reset-button');
      const backToEmail = document.getElementById('back-to-email');
      const step1 = document.getElementById('step1');
      const step2 = document.getElementById('step2');
     
      // Validation data
      const validEmails = [
        "29schreinerskyelar@apcsd.org",
        "user2@example.com",
        "admin@example.com",
        "test@example.com"
      ];
      const validCode = "12312";
     
      // Store validated email
      let validatedEmail = "";
     
      // Email form submission
      emailForm.addEventListener('submit', function(e) {
        e.preventDefault();
        const email = emailInput.value.trim();
       
        if (validEmails.includes(email)) {
          validatedEmail = email;
          // Move to code step
          emailStep.classList.add('hidden');
          codeStep.classList.remove('hidden');
          step1.classList.remove('active');
          step1.classList.add('completed');
          step2.classList.add('active');
        } else {
          alert("Email not recognized. Please try again.");
        }
      });
     
      // Code form submission
      codeForm.addEventListener('submit', function(e) {
        e.preventDefault();
        const code = codeInput.value.trim();
       
        if (code === validCode) {
          // Show success
          showResult(true);
        } else {
          alert("Invalid code. Please try again.");
        }
      });
     
      // Back to email step
      backToEmail.addEventListener('click', function() {
        codeStep.classList.add('hidden');
        emailStep.classList.remove('hidden');
        step2.classList.remove('active');
        step1.classList.add('active');
        step1.classList.remove('completed');
      });
     
      // Reset button
      resetButton.addEventListener('click', function() {
        resultContainer.classList.add('hidden');
        emailStep.classList.remove('hidden');
        emailInput.value = '';
        codeInput.value = '';
        validatedEmail = '';
        step1.classList.add('active');
        step1.classList.remove('completed');
        step2.classList.remove('active');
      });
     
      // Show result function
      function showResult(isValid) {
        codeStep.classList.add('hidden');
        resultContainer.classList.remove('hidden');
        step2.classList.remove('active');
        step2.classList.add('completed');
       
        if (isValid) {
          statusMessage.innerHTML = `
            <svg class="icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path>
            </svg>
            <span>Access granted! Welcome back, ${validatedEmail}.</span>
          `;
          statusMessage.className = 'status-message status-success';
          contentContainer.classList.remove('hidden');
        } else {
          statusMessage.innerHTML = `
            <svg class="icon" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
            </svg>
            <span>Access denied. Invalid code.</span>
          `;
          statusMessage.className = 'status-message status-error';
          contentContainer.classList.add('hidden');
        }
      }
    });
  </script>
</body>
</html>
