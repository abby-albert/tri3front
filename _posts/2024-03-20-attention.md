
### What was your subject in number the number key: 0 is science, 1 is math, 2 is history, and 3 is English
<input type="text" id="userInput" placeholder="Type here">

### Was your attention focused or divided?
<input type="text" id="userInput" placeholder="Type here">

### How many solutions did you find (0-4)
<input type="text" id="userInput" placeholder="Type here">

<div>
  <button onclick="submitText()">Submit</button>
</div>
<script>
  function submitText() {
    var userInput = document.getElementById("userInput").value;
    alert("You typed: " + userInput);
  }
</script>
