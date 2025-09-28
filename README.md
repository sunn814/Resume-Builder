<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Enhanced Resume Builder</title>
  <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;700&display=swap" rel="stylesheet">
  <style>
    body {
      font-family: 'Roboto', sans-serif;
      padding: 20px;
      background-color: #f4f7f8;
    }

    h1 {
      text-align: center;
      margin-bottom: 20px;
      color: #2c3e50;
    }

    .container {
      display: flex;
      flex-wrap: wrap;
      gap: 30px;
      max-width: 1200px;
      margin: 0 auto;
    }

    .form-section, .preview-section {
      background-color: #fff;
      padding: 30px;
      border-radius: 10px;
      flex: 1 1 400px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.08);
    }
    
    .form-section {
        min-width: 350px;
    }

    label {
      display: block;
      margin-top: 15px;
      font-weight: 700;
      color: #34495e;
    }

    input, textarea {
      width: 100%;
      padding: 10px;
      margin-top: 5px;
      border-radius: 5px;
      border: 1px solid #bdc3c7;
      box-sizing: border-box;
      font-size: 15px;
      transition: border-color 0.3s;
    }

    input:focus, textarea:focus {
        border-color: #3498db;
        outline: none;
    }

    textarea {
      resize: vertical;
      min-height: 100px;
    }

    button {
      margin-top: 20px;
      padding: 12px 25px;
      font-size: 16px;
      font-weight: 700;
      background-color: #3498db;
      color: #fff;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      transition: background-color 0.3s;
    }

    button:hover {
      background-color: #2980b9;
    }
    
    .form-separator {
        border-top: 1px solid #ecf0f1;
        margin: 20px 0;
    }

    .preview-section {
      max-width: 700px;
      line-height: 1.6;
    }

    #p-name {
      margin: 0;
      font-size: 30px;
      color: #2c3e50;
      text-align: center;
    }

    #p-role {
      margin: 2px 0 10px 0;
      font-size: 18px;
      color: #3498db;
      text-align: center;
      font-weight: 400;
    }
    
    #p-contact {
      text-align: center;
      margin-bottom: 20px;
      font-size: 14px;
      color: #7f8c8d;
      border-bottom: 2px solid #ecf0f1;
      padding-bottom: 10px;
    }
    
    .preview-section h4 {
        margin: 15px 0 5px 0;
        font-size: 16px;
        color: #fff;
        background-color: #34495e;
        padding-left: 10px;
        border-radius: 3px;
    }
    
    .preview-section p {
      margin: 5px 0;
      color: #555;
    }
    
    .experience-item, .education-item {
        margin-bottom: 15px;
        padding-left: 10px;
        border-left: 3px solid #3498db;
    }

    .job-title, .degree {
        font-weight: 700;
        color: #34495e;
        margin-bottom: 2px;
    }
    
    .company, .school {
        font-style: italic;
        color: #7f8c8d;
        font-size: 14px;
        margin-bottom: 5px;
    }

    @media print {
      body {
        background-color: #fff;
        padding: 0;
      }
      .form-section {
        display: none;
      }
      .preview-section {
        box-shadow: none;
        border: none;
        max-width: none;
        width: 100%;
        margin: 0;
        padding: 0;
      }
      .container {
          gap: 0;
      }
      .preview-section h4 {
          background-color: #ecf0f1;
          color: #34495e;
      }
    }
  </style>
</head>
<body>

  <h1>Enhanced Resume Builder ✨</h1>
  <div class="container">
    <div class="form-section">
        <h2>Personal Details</h2>
      <label for="name">Name:</label>
      <input type="text" id="name" placeholder="Enter your full name" oninput="updatePreview()">

      <label for="role">Desired Role:</label>
      <input type="text" id="role" placeholder="Enter desired role" oninput="updatePreview()">

      <label for="email">Email:</label>
      <input type="email" id="email" placeholder="Enter your email" oninput="updatePreview()">

      <label for="phone">Phone:</label>
      <input type="text" id="phone" placeholder="Enter phone number" oninput="updatePreview()">

      <label for="website">Website/LinkedIn:</label>
      <input type="text" id="website" placeholder="Enter website or LinkedIn" oninput="updatePreview()">

      <label for="location">Location:</label>
      <input type="text" id="location" placeholder="Enter location" oninput="updatePreview()">
      
      <div class="form-separator"></div>
      
      <h2>Summary</h2>
      <label for="summary">Professional Summary:</label>
      <textarea id="summary" placeholder="Write a short professional summary..." oninput="updatePreview()"></textarea>

      <div class="form-separator"></div>
      
      <h2>Experience</h2>
      <label for="job1-title">Job 1 Title & Dates:</label>
      <input type="text" id="job1-title" placeholder="e.g., Software Engineer, 2020 - Present" oninput="updatePreview()">
      <label for="job1-company">Company 1:</label>
      <input type="text" id="job1-company" placeholder="Company name" oninput="updatePreview()">
      <label for="job1-desc">Job 1 Description:</label>
      <textarea id="job1-desc" placeholder="Responsibilities and achievements..." oninput="updatePreview()"></textarea>

      <div class="form-separator"></div>
      
      <h2>Education</h2>
      <label for="edu1-degree">Degree & Dates:</label>
      <input type="text" id="edu1-degree" placeholder="e.g., B.Sc. Computer Science, 2016 - 2020" oninput="updatePreview()">
      <label for="edu1-school">School 1:</label>
      <input type="text" id="edu1-school" placeholder="University/College name" oninput="updatePreview()">
      <label for="edu1-desc">Relevant Details:</label>
      <input type="text" id="edu1-desc" placeholder="e.g., GPA, Honors" oninput="updatePreview()">

      <button onclick="printResume()">Print Resume</button>
    </div>

    <div class="preview-section">
      <h2 id="p-name">Your Name</h2>
      <h3 id="p-role">Your Role</h3>
      <p id="p-contact">Email | Phone | Website/LinkedIn | Location</p>
      
      <h4 class="section-title">PROFESSIONAL SUMMARY</h4>
      <p id="p-summary">Your professional summary will appear here.</p>
      
      <h4 class="section-title">EXPERIENCE</h4>
      <div id="p-experience">
          <div class="experience-item">
              <p class="job-title">Job Title, Dates</p>
              <p class="company">Company Name</p>
              <p class="job-desc">Job description details.</p>
          </div>
      </div>
      
      <h4 class="section-title">EDUCATION</h4>
      <div id="p-education">
          <div class="education-item">
              <p class="degree">Degree Name, Dates</p>
              <p class="school">School Name</p>
              <p class="edu-desc">Relevant Details.</p>
          </div>
      </div>

    </div>
  </div>

  <script>
    document.addEventListener('DOMContentLoaded', () => {
        updatePreview(); 
    });
    
    function formatDescription(text) {
        if (!text) return "";
        let lines = text.split('\n').filter(line => line.trim() !== '');
        if (lines.every(line => line.trim().startsWith('-'))) {
            let listHtml = '<ul>';
            lines.forEach(line => {
                let content = line.trim().replace(/^-/, '').trim();
                if (content) listHtml += `<li>${content}</li>`;
            });
            listHtml += '</ul>';
            return listHtml;
        }
        return text.replace(/\n/g, '<br>');
    }

    function updatePreview() {
      document.getElementById("p-name").innerText = document.getElementById("name").value || "Your Name";
      document.getElementById("p-role").innerText = document.getElementById("role").value || "Your Role";

      let email = document.getElementById("email").value || "Email";
      let phone = document.getElementById("phone").value || "Phone";
      let website = document.getElementById("website").value || "Website/LinkedIn";
      let location = document.getElementById("location").value || "Location";
      
      let contactParts = [email, phone, website, location].filter(part => !["Email","Phone","Website/LinkedIn","Location"].includes(part));
      document.getElementById("p-contact").innerText = contactParts.length ? contactParts.join(' | ') : "Email | Phone | Website/LinkedIn | Location";

      document.getElementById("p-summary").innerText = document.getElementById("summary").value || "Your professional summary will appear here.";
      
      const expDiv = document.getElementById("p-experience");
      expDiv.innerHTML = "";
      const job1Title = document.getElementById("job1-title").value;
      const job1Company = document.getElementById("job1-company").value;
      const job1Desc = document.getElementById("job1-desc").value;
      
      if (job1Title || job1Company || job1Desc) {
          expDiv.innerHTML = `
            <div class="experience-item">
                <p class="job-title">${job1Title || "Job Title, Dates"}</p>
                <p class="company">${job1Company || "Company Name"}</p>
                <p class="job-desc">${formatDescription(job1Desc) || "Job description details."}</p>
            </div>
          `;
      } else {
          expDiv.innerHTML = `
            <div class="experience-item">
                <p class="job-title">Job Title, Dates</p>
                <p class="company">Company Name</p>
                <p class="job-desc">Job description details.</p>
            </div>
          `;
      }

      const eduDiv = document.getElementById("p-education");
      eduDiv.innerHTML = "";
      const edu1Degree = document.getElementById("edu1-degree").value;
      const edu1School = document.getElementById("edu1-school").value;
      const edu1Desc = document.getElementById("edu1-desc").value;
      
      if (edu1Degree || edu1School || edu1Desc) {
          eduDiv.innerHTML = `
            <div class="education-item">
                <p class="degree">${edu1Degree || "Degree Name, Dates"}</p>
                <p class="school">${edu1School || "School Name"}</p>
                <p class="edu-desc">${edu1Desc || "Relevant Details."}</p>
            </div>
          `;
      } else {
          eduDiv.innerHTML = `
            <div class="education-item">
                <p class="degree">Degree Name, Dates</p>
                <p class="school">School Name</p>
                <p class="edu-desc">Relevant Details.</p>
            </div>
          `;
      }
    }

    function printResume() {
      window.print();
    }
  </script>

</body>
</html>
