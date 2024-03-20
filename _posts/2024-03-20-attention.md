### What was your subject?
Choose a number: 0 for Science, 1 for Math, 2 for History, 3 for English

<input type="text" id="subjectInput" placeholder="Type here">

### Was your attention focused or divided? (Type 'focused' or 'divided')
<input type="text" id="attentionInput" placeholder="Type here">

### How many solutions did you find? (Enter a number between 0 and 4)
<input type="text" id="solutionsInput" placeholder="Type here">

<div>
  <button onclick="calculateProbability()">Calculate Probability of score above 9.0/10.0</button>
</div>

<script>
  function calculateProbability() {
    var subject = document.getElementById("subjectInput").value;
    var attention = document.getElementById("attentionInput").value;
    var solutions = document.getElementById("solutionsInput").value;
    
    // Send data to backend
    fetch('/process_data', {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json'
      },
      body: JSON.stringify({ subject: subject, attention: attention, solutions: solutions })
    })
    .then(response => response.json())
    .then(data => {
      // Display probability result
      alert("Probability of getting a score above 9.0: " + data.probability.toFixed(2) + "%");
    })
    .catch(error => {
      console.error('Error:', error);
    });
  }
</script>