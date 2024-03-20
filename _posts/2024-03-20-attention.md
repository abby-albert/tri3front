

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
