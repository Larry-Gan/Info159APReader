<script>
  import articles from './assets/articles.json';

  let fileTitle = "";
  let fileText = "";
  let fileURL = "";
  let fileNumber = 0;

  function loadText() {
      fileTitle = articles[fileNumber.toString()]["Title"];
      fileText = articles[fileNumber.toString()]["Text"];
      fileURL = articles[fileNumber.toString()]["URL"];
      return fileNumber;
  }
  function inc() {
    if (fileNumber < 499) {
      fileNumber += 1;
    }
    loadText();
  }
  function dec() {
    if (fileNumber > 0) {
      fileNumber -= 1;
    }
    loadText();
  }
  loadText();
  

let answer = '';
  

</script>

<div class="index">
  <form on:submit|preventDefault={() => fileNumber = loadText()}>
      <label for="fname">Index of article:</label>
      <input type="number" class = "income-entry" bind:value={fileNumber} on:input={loadText}><br><br>
  </form>
  <button on:click={dec}>Previous Entry</button>
  <button on:click={inc}>Next Entry</button>
</div> 
<div class="text">
  <p><a href={fileURL}>{fileURL}</a></p>
  <h1>{fileTitle}</h1>
  <p>{fileText}</p>
</div>



<style>
  .index {
      text-align: center;
      margin: 20px auto;
  }
  .text {
      white-space: pre-line;
  }
</style>
