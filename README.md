<!DOCTYPE html>
<html>
<head>
  <title>Class 11th And 12th Science Bot</title>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      background-color: #f4f9ff;
      margin: 0;
      padding: 0;
      text-align: center;
    }
    .container {
      max-width: 500px;
      margin: 50px auto;
      padding: 20px;
      background: white;
      border-radius: 20px;
      box-shadow: 0 0 15px rgba(0,0,0,0.2);
    }
    button {
      background-color: #007BFF;
      color: white;
      border: none;
      padding: 10px 20px;
      border-radius: 10px;
      font-size: 18px;
      margin: 10px;
      cursor: pointer;
    }
    #chat {
      display: none;
      margin-top: 20px;
      text-align: left;
    }
    input {
      width: 80%;
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 10px;
      margin-bottom: 10px;
    }
    .footer {
      margin-top: 20px;
      font-size: 14px;
    }
    .footer a {
      text-decoration: none;
      color: #007BFF;
    }
  </style>
</head>
<body onload="welcomeVoice()">
  <div class="container">
    <h2>🙏 Namaste Student</h2>
    <button onclick="showClassSelection()">Start</button>

    <div id="classSelection" style="display:none;">
      <button onclick="selectClass('11')">Class 11th</button>
      <button onclick="selectClass('12')">Class 12th</button>
    </div>

    <div id="chat">
      <input type="text" id="userInput" placeholder="Type your question here...">
      <button onclick="getAnswer()">Ask</button>
      <div id="response"></div>
    </div>

    <div class="footer">
      <p>Made by Alpha Trader | <a href="https://t.me/Sonu_18_45" target="_blank">Support</a></p>
    </div>
  </div>

  <script>
    let selectedClass = null;

    function welcomeVoice() {
      const msg = new SpeechSynthesisUtterance("Ye Bot Aapka Swagat Karta Hai");
      window.speechSynthesis.speak(msg);
    }

    function showClassSelection() {
      document.getElementById('classSelection').style.display = 'block';
    }

    function selectClass(cls) {
      selectedClass = cls;
      document.getElementById('classSelection').style.display = 'none';
      document.getElementById('chat').style.display = 'block';
    }

    function getAnswer() {
      const question = document.getElementById('userInput').value.toLowerCase();
      let answer = "Sorry, I don't understand that question.";

      if (selectedClass === '11') {
        if (question.includes("what is biology")) {
          answer = "Biology is the branch of science that deals with the study of living organisms.";
        } else if (question.includes("scientific name of human")) {
          answer = "Homo sapiens";
        } else if (question.includes("define biodiversity")) {
          answer = "Biodiversity refers to the variety and variability of living organisms in a particular area or on the entire Earth.";
        } else if (question.includes("what is nomenclature")) {
          answer = "Nomenclature is the process of naming organisms scientifically.";
        } else if (question.includes("binomial nomenclature")) {
          answer = "It is the system of giving two scientific names (Genus + Species) to an organism, such as Homo sapiens for humans.";
        } else if (question.includes("why are living organisms classified")) {
          answer = "To standardize identification and study, and avoid confusion due to local names.";
        } else if (question.includes("who introduced binomial nomenclature")) {
          answer = "Carl Linnaeus";
        } else if (question.includes("full form of iczn")) {
          answer = "ICZN – International Code of Zoological Nomenclature, ICBN – International Code of Botanical Nomenclature";
        } else if (question.includes("what is taxonomy")) {
          answer = "Taxonomy is the science of identification, classification, and naming of organisms.";
        } else if (question.includes("what is systematics")) {
          answer = "Systematics is the study of diversity of organisms and their evolutionary relationships.";
        } else if (question.includes("taxonomic categories and taxonomic hierarchy")) {
          answer = "Categories are levels like species, genus, etc., hierarchy is the ordered arrangement of these levels.";
        } else if (question.includes("what is a species")) {
          answer = "A species is the basic unit of classification that includes organisms capable of interbreeding and producing fertile offspring.";
        } else if (question.includes("what is a herbarium")) {
          answer = "A herbarium is a storehouse where dried and pressed plant specimens are preserved on sheets for study.";
        } else if (question.includes("what is a key in taxonomy")) {
          answer = "A key is a tool used for identifying organisms based on traits.";
        } else if (question.includes("modern taxonomy vs classical taxonomy")) {
          answer = "Modern taxonomy includes internal and molecular traits while classical taxonomy is based on morphology.";
        }
      }

      document.getElementById('response').innerText = answer;
    }
  </script>
</body>
</html>

