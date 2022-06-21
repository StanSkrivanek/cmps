<script>
  export let type = "text";
  export let btColor = null;
  export let caption = null;
  export let disabled = false;
</script>

<button class="{btColor}" {type} on:click|preventDefault {disabled}>{caption}</button>

<style>
  button {
    font-family: "Montserrat", sans-serif;
    text-transform: uppercase;
    /* border: 1px solid #cf0056; */
    border: none;
    background: #d9e4f6;
    padding: 0.5rem 1rem;
    color: rgb(92, 91, 91);
    border-radius: 4px;
    letter-spacing: 0.05rem;
    /* box-shadow: 3px 4px 9px rgba(0, 0, 0, 0.15); */
    cursor: pointer;
    text-decoration: none;
  }
  button:disabled,
  button:disabled:hover,
  button:disabled:active {
    background: #ccc;
    border-color: #ccc;
    color: #959595;
    box-shadow: none;
    cursor: not-allowed;
  }
  .primary {
    background: #678efe;
    color:white
  }
  .error {
    background: #ff5a5f;
    color:white
  }
  .action {
    background: #66ff99;
    color:black
  }
</style>
