<script>
  export let id = "";
  export let label = "";
  export let span = "";
  export let type = "text";
  export let value = "0";
</script>

<div class="input-component">
  <p class="input-heading">{label}</p>

  <div class="input__c">
    <div class="form-group">
      <span class="btn-select ">{span}</span>
      <input class="form-field" {id} {label} {type} {value} on:input/>
    </div>
  </div>
</div>

<style>
  * {
    box-sizing: border-box;
  }
  :root {
    --input-color: #99a3ba;
    --input-border: #cdd9ed;
    --input-background: #fff;
    --input-placeholder: #cbd1dc;
    --input-border-focus: #275efe;
    --group-color: var(--input-color);
    --group-border: var(--input-border);
    --group-background: #eef4ff;
    --group-color-focus: #fff;
    --group-border-focus: var(--input-border-focus);
    --group-color-error: #ff5a5f;
    --group-background-focus: #678efe;
  }

  .input-component {
    position: relative;
  }
  .input__c {
    font-family: "Open Sans", sans-serif;
    display: flex;
  }

  .form-field {
    display: block;
    width: 100%;
    padding: 8px 16px;
    line-height: 25px;
    font-size: 15px;
    font-weight: 500;
    font-family: inherit;
    border-radius: 6px;
    -webkit-appearance: none;
    color: var(--input-color);
    border: 1px solid var(--input-border);
    background: var(--input-background);
    transition: border 0.3s ease;
  }
  .form-field::-moz-placeholder {
    color: var(--input-placeholder);
  }
  .form-field:-ms-input-placeholder {
    color: var(--input-placeholder);
  }
  .form-field::placeholder {
    color: var(--input-placeholder);
  }
  /* .form-field:focus {
  outline: none;
  border-color: var(--input-border-focus);
} */

  .form-group {
    position: relative;
    display: flex;
    width: 100%;
  }
  .form-group > span,
  .form-group .form-field {
    white-space: nowrap;
    display: block;
    /* text-transform: uppercase; */
  }
  .form-group > span:not(:first-child):not(:last-child),
  .form-group .form-field:not(:first-child):not(:last-child) {
    border-radius: 0;
  }
  .form-group > span:first-child,
  .form-group .form-field:first-child {
    border-radius: 6px 0 0 6px;
  }
  .form-group > span:last-child,
  .form-group .form-field:last-child {
    border-radius: 0 6px 6px 0;
  }
  .form-group > span:not(:first-child),
  .form-group .form-field:not(:first-child) {
    margin-left: -1px;
  }
  .form-group .form-field {
    position: relative;
    z-index: 1;
    flex: 1 1 auto;
    width: 1%;
    margin-top: 0;
    margin-bottom: 0;
  }
  .form-group > span {
    text-align: center;
    padding: 8px 12px;
    font-size: 14px;
    line-height: 25px;
    color: var(--group-color);
    background: var(--group-background);
    border: 1px solid var(--group-border);
    transition: background 0.3s ease, border 0.3s ease, color 0.3s ease;
  }
  /* .form-group:focus-within > span {
  color: var(--group-color-focus);
  background: var(--group-background-focus);
  border-color: var(--group-border-focus);
} */

  .btn-select {
    text-transform: uppercase;
    /* cursor: pointer; */
  }

  /* .form-group .selected {
    background: var(--input-border-focus);
    color: var(--group-color-focus);
    background: var(--group-background-focus);
  } */
  .input-heading {
    font-family: "Montserrat", "sans-serif";
    text-transform: uppercase;
    font-size: 0.8rem;
    font-weight: 300;
    letter-spacing: 0.05rem;
    line-height: 0;
    /* padding-left: 36px; */
  }
  /* .disabled {
    color: #ccc;
    pointer-events: none;
  } */
  /* .danger {
    position: absolute;
    bottom: -24px;
    left: 36px;
    color: #ff5a5f;
    font-size: 0.8rem;
  } */
  /* .bg-alert {
    background: var(--group-color-error) !important;
  } */
  /* Webkit browsers like Safari and Chrome */
  /* input[type="number"]::-webkit-inner-spin-button,
  input[type="number"]::-webkit-outer-spin-button {
    -webkit-appearance: none;
    margin: 0;
  }
  input[type="number"] {
    -moz-appearance: textfield;
  } */
</style>
