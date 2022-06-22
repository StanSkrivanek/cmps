<script>
  import { ps8, ps10, ps0, psRem } from "$lib/helpers";
  import { pointSys } from "$lib/stores/store";
  import { sizesStore } from "$lib/stores/store";
  // $: console.log("IN SCIRIPT - $pointSys", $pointSys.pointSystem);

  let showAlert = false;
  let charCodeNum = null;

  // let sizesStr = "";

  $: if ($pointSys.pointSystem === "1") {
    $sizesStore = ps8;
  } else if ($pointSys.pointSystem === "2") {
    $sizesStore = ps10;
  } else {
    $sizesStore = ps0;
  }

  function isNumber(evt) {
    charCodeNum = evt.key;
    if (
      charCodeNum == "," ||
      charCodeNum == "Backspace" ||
      charCodeNum == "ArrowUp" ||
      charCodeNum == "ArrowDown" ||
      charCodeNum == "ArrowRight" ||
      charCodeNum == "ArrowLeft" ||
      charCodeNum == "Enter" ||
      charCodeNum < 48 ||
      charCodeNum > 57 ||
      charCodeNum > 95 ||
      charCodeNum < 106
    ) {
      showAlert = false;
      // return false;
    } else {
      // console.log("Not a Number", evt.key);
      showAlert = true;
    }
    // console.log(evt.charCode);
  }

  // function createArray(sizes) {
  //   let sizesArr = [];
  //   sizes.forEach((item) => {
  //     sizesArr.push(item);
  //   }),
  //     console.log("sizesArr", sizesArr);
  //   return sizesArr;
  // }

  // $: console.log($sizesStore);
  // $: console.log("sizesStore-INPUT SIZE", sizesStr, $sizesStore);
</script>

<div class="container">
  <div class="input-component">
    <p class="input-heading">Custom sizes</p>
    <div class="input__c">
      <div class="form-group">
        <span
          class="btn-select {$sizesStore.length == 0
            ? 'disabled'
            : 'selected'} {showAlert ? 'bg-alert' : ''}">sizes</span
        >
        <input
          class="form-field"
          type="text"
          name="paddingPfx"
          bind:value={$sizesStore}
          on:keyup={isNumber}
        />
        <!--  $sizesStore = $sizesStore.replace(/,/g, '') -->
      </div>
    </div>

    <!-- wrap this in Svelte IF condition  -->
    <div class="input-heading danger">
      <p>{showAlert ? `[ ${charCodeNum} ] is not a number` : ""}</p>
    </div>
  </div>
</div>

<style>
  /* :root {
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
    --group-background-focus: #678efe;
    --group-color-error: #ff5a5f;
  } */

  .container {
    /* padding: 0 16px; */
    /* background-color: cadetblue; */
    /* width: 100%; */
    /* display: flex; */
    /* flex-direction: row; */
    /* margin-bottom: 24px; */
    /* flex-basis: 500px; */
    /* flex-wrap: wrap; */
    gap: 16px;
  }

  .input-component {
    position: relative;
    /* margin-bottom: 36px; */
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

  .form-group .selected {
    background: var(--input-border-focus);
    color: var(--group-color-focus);
    background: var(--group-background-focus);
  }
  .input-heading {
    font-family: "Montserrat", "sans-serif";
    text-transform: uppercase;
    font-size: 0.8rem;
    font-weight: 300;
    letter-spacing: 0.05rem;
    line-height: 0;
    /* padding-left: 12%; */
  }
  /* .disabled {
    color: #ccc;
    pointer-events: none;
  } */
  .danger {
    position: absolute;
    bottom: -24px;
    left: 64px;
    color: #ff5a5f;
    font-size: 0.8rem;
  }
  .bg-alert {
    background: var(--group-color-error) !important;
  }
</style>
