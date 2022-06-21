<script>
  import { previewerValues } from "$lib/stores/store.js";
  import Previewer from "$lib/components/Previewer.svelte";
  import { pointSys } from "$lib/stores/store";
  import RadioInput from "$lib/components/shared/RadioInput.svelte";
  import InputBasic from "$lib/components/shared/InputBasic.svelte";
  // import Form from "./Form.svelte";
  // import Button from "$lib/components/shared/Button.svelte";

  let pointSystem = "0";
  let units = "0";
  let isNumber = true;
  let isEmpty = false;

  $: units == 1
    ? ($previewerValues.unit = "rem")
    : ($previewerValues.unit = "px");

  $: if (pointSystem) {
    $pointSys = { pointSystem };
  }

  function updateSeparator(e) {
    let value = e.target.value;
    console.log(value);
    $previewerValues.separator = value;
  }

  function updateRootSize(e) {
    let value = Number(e.target.value);
    console.log("value", value);

    var re = new RegExp("^[0-9]");
    if (re.test(value)) {
      isNumber = true;
    } else {
      isNumber = false;
    }
    value === 0 ? (isEmpty = true) : (isEmpty = false);
    $previewerValues.rootsize = value;
  }
</script>

<div class="container">
  <div class="options">
    <div class="btn-group__c">
      <div class="btns__w">
        <RadioInput
          btnLabel=" Custom"
          name="system"
          bind:group={pointSystem}
          value="0"
        />
        <RadioInput
          btnLabel=" 8pt system"
          name="system"
          bind:group={pointSystem}
          value="1"
        />
        <RadioInput
          btnLabel=" 10pt system"
          name="system"
          bind:group={pointSystem}
          value="2"
        />
      </div>
      <div class="input__w">
        <InputBasic
          type="text"
          label="separator"
          span="&#8211;"
          value={$previewerValues.separator}
          on:input={updateSeparator}
        />
      </div>
    </div>
    <div class="btn-group__c">
      <div class="btns__w">
        <RadioInput
          btnLabel="px units"
          name="units"
          bind:group={units}
          value="0"
        />

        <RadioInput
          btnLabel="rem units"
          name="units"
          bind:group={units}
          value="1"
        />
      </div>

      <div class="input__w">
        {#if units == 1}
          <InputBasic
            type="text"
            label="root size"
            span="&#177;"
            value={$previewerValues.rootsize}
            on:input={updateRootSize}
          />
          <div class="input-heading danger">
            <p>{!isNumber || isEmpty || 0 ? "use Numbers only" : ""}</p>
            <!-- <p>{isEmpty ? "Are you sure?" : ""}</p> -->
          </div>
        {/if}
      </div>
    </div>
  </div>

  <Previewer />
  <!-- <Visual /> -->
</div>

<style>
  * {
    box-sizing: border-box;
  }
  .container {
    display: flex;
    /* flex: 0 1 50%; */
    flex-wrap: wrap;
    justify-content: space-between;
    /* min-height: 140px; */
    gap: 16px;
    align-items: top;
    /* border: 1px solid green; */
    /* margin-bottom: 24px; */
  }
  .options {
    display: flex;
    flex: 1 1 40%;
    /* flex-wrap: wrap; */
    gap: 16px;
    /* margin-bottom: 24px; */
  }
  .btn-group__c {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    flex: 1 1 40%;
    /* border: 1px solid red; */
    gap: 16px;
    /* padding-top: 24px; */
  }
  .btns__w {
    display: flex;
    flex-direction: column;
    justify-content: start;
    align-items: start;
    gap: 16px;
  }
  .input__w {
    position: relative;
    max-width: 100%;
    /* display: flex;
    gap: 16px; */
  }
  /* .input-heading {
    font-family: "Montserrat", "sans-serif";
    text-transform: uppercase;
    font-size: 0.8rem;
    font-weight: 300;
    letter-spacing: 0.05rem;
    line-height: 0;
    padding-left: 36px;
  } */
  .danger {
    position: absolute;
    font-family: "Montserrat", "sans-serif";
    text-transform: uppercase;
    top: -8px;
    right: 0;
    color: #ff5a5f;
    font-size: 0.8rem;
    text-align: right;
  }
  /* .hidden {
    visibility: hidden;
  } */
  /* .visible {
    visibility: visible;
  } */
</style>
