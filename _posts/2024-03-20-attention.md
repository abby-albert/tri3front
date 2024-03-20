
### What was your subject?
Choose a number: 0 for Science, 1 for Math, 2 for History, 3 for English
<input type="text" id="subjectInput" placeholder="Type here">

### Was your attention focused or divided? (Type 'focused' or 'divided')
<input type="text" id="attentionInput" placeholder="Type here">

### How many solutions did you find? (Enter a number between 0 and 4)
<input type="text" id="solutionsInput" placeholder="Type here">

<div>
  <button onclick="calculateProbability()">Calculate Probability</button>
</div>

<script>
  function calculateProbability() {
    var subject = document.getElementById("subjectInput").value;
    var attention = document.getElementById("attentionInput").value;
    var solutions = document.getElementById("solutionsInput").value;
    
    // Load attention.csv data
    // Assuming the data is loaded and stored in the variable 'data'
    
    // Preprocess data to filter scores above 9.0 based on user input
    var filteredData = data.filter(function(row) {
      return row.subject == subject && row.attention == attention && row.solutions == solutions && row.score > 9.0;
    });
    
    // Calculate probability
    var totalAbove9 = filteredData.length;
    var totalRecords = data.length;
    var probability = totalAbove9 / totalRecords * 100;
    
    alert("Probability of getting a score above 9.0: " + probability.toFixed(2) + "%");
  }
</script>

