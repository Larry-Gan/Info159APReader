<script>
  import articles from './assets/articles.json';

  let fileTitle = "";
  let fileText = "";
  let fileNumber = "0";

  function loadText() {
      fileTitle = articles[fileNumber]["Title"];
      fileText = articles[fileNumber]["Text"];
      return fileNumber;
}
  
  

let answer = '';
  

</script>

<div class="index">
  <form on:submit|preventDefault={() => fileNumber = loadText()}>
      <label for="fname">Index of article:</label>
      <input type="text" class = "income-entry" bind:value={fileNumber} on:input={loadText}><br><br>
    </form>
</div> 

<p>{fileTitle}</p>
<p>{fileText}</p>


<style>
  .index {
      text-align: center;
      margin: 20px auto;
  }
</style>
