<script>
  // import { createEventDispatcher } from "svelte";
  // const dis = createEventDispatcher();

  export let btnLabel = "label";
  export let name = "name";
  export let isChecked = false;
</script>

<label class="input__control">
  <input {btnLabel} type="checkbox" {name} bind:checked={isChecked} on:click />
  <span class="outside">
    <span class="inside" />
  </span>
  {btnLabel}
</label>

<style>
  input[type="checkbox"] {
    /* Add if not using autoprefixer */
    -webkit-appearance: none;
    appearance: none;
    /* For iOS < 15 to remove gradient background */
    /* background-color: red; */
    /* Not removed via appearance */
    margin: 0;
  }
  .input__control {
    position: relative;
    font-family: "Montserrat", "sans-serif";
    font-size: 1rem;
    line-height: 1.1;
    display: grid;
    grid-template-columns: 1em auto;
    gap: 0.4em;
  }

  .outside {
    display: inline-block;
    position: absolute;
    left: -4px;
    top: 50%;
    margin-top: -10px;

    width: 20px;
    height: 20px;
    border: 2px solid var(--col-active);
    border-radius: 2px;
    -webkit-box-sizing: border-box;
    box-sizing: border-box;
    background: none;
  }

  .inside {
    position: absolute;
    top: 50%;
    left: 50%;
    -webkit-transform: translate(-50%, -50%);
    transform: translate(-50%, -50%);
    display: inline-block;
    border-radius: 2px;
    width: 10px;
    height: 10px;
    background: var(--col-active);
    left: 3px;
    top: 3px;
    -webkit-transform: scale(0, 0);
    transform: scale(0, 0);
  }

  /* .no-transforms .inside {
    left: auto;
    top: auto;
    width: 0;
    height: 0;
  } */

  /* input { */
  /*  &:focus, &:active {
        + .outside {
          border-color: $almost-black;
        }
      }*/
  /* } */
  input:checked + .outside .inside {
    -webkit-animation: radio-select 0.1s linear;
    animation: radio-select 0.1s linear;
    -webkit-transform: scale(1, 1);
    transform: scale(1, 1);
  }
  .no-transforms input:checked + .outside .inside {
    width: 10px;
    height: 10px;
  }
  /* @supports (-webkit-appearance: none) or (-moz-appearance: none) {
    input[type="checkbox"]{
      --active: #678efe;
      --active-inner: #fff;
      --focus: 2px rgba(39, 94, 254, 0.3);
      --border: #bbc1e1;
      --border-hover: #678efe;
      --background: #fff;
      --disabled: #f6f8ff;
      --disabled-inner: #e1e6f9;
      -webkit-appearance: none;
      -moz-appearance: none;
      height: 20px;
      outline: none;
      display: inline-block;
      vertical-align: top;
      position: relative;
      margin: 0;
      cursor: pointer;
      border: 1px solid var(--bc, var(--border));
      background: var(--b, var(--background));
      transition: background 0.3s, border-color 0.3s, box-shadow 0.2s;
    }
    input[type="checkbox"]:after{
      content: "";
      display: block;
      left: 0;
      top: 0;
      position: absolute;
      transition: transform var(--d-t, 0.3s) var(--d-t-e, ease),
        opacity var(--d-o, 0.2s);
    }
    input[type="checkbox"]:checked{
      --b: var(--active);
      --bc: var(--active);
      --d-o: 0.3s;
      --d-t: 0.6s;
      --d-t-e: cubic-bezier(0.2, 0.85, 0.32, 1.2);
    }
    input[type="checkbox"]:disabled {
      --b: var(--disabled);
      cursor: not-allowed;
      opacity: 0.9;
    }
    input[type="checkbox"]:disabled:checked {
      --b: var(--disabled-inner);
      --bc: var(--border);
    } */
  /* input[type="checkbox"]:disabled + label {
      cursor: not-allowed;
    } */
  /* input[type="checkbox"]:hover:not(:checked):not(:disabled){
      --bc: var(--border-hover);
    }
    input[type="checkbox"]:focus {
      box-shadow: 0 0 0 var(--focus);
    }
    input[type="checkbox"]:not(.switch) {
      width: 21px;
    }
    input[type="checkbox"]:not(.switch):after {
      opacity: var(--o, 0);
    }
    input[type="checkbox"]:not(.switch):checked {
      --o: 1;
    } */
  /* input[type="checkbox"] + label {
      font-size: 14px;
      line-height: 21px;
      display: inline-block;
      vertical-align: top;
      cursor: pointer;
      margin-left: 4px;
    } */

  /* input[type="checkbox"]:not(.switch) {
      border-radius: 7px;
    }
    input[type="checkbox"]:not(.switch):after {
      width: 5px;
      height: 9px;
      border: 2px solid var(--active-inner);
      border-top: 0;
      border-left: 0;
      left: 7px;
      top: 4px;
      transform: rotate(var(--r, 20deg));
    }
    input[type="checkbox"]:not(.switch):checked {
      --r: 43deg;
    } */
  /* input[type="checkbox"].switch {
      width: 38px;
      border-radius: 11px;
    } */
  /* input[type="checkbox"].switch:after {
      left: 2px;
      top: 2px;
      border-radius: 50%;
      width: 15px;
      height: 15px;
      background: var(--ab, var(--border));
      transform: translateX(var(--x, 0));
    } */
  /* input[type="checkbox"].switch:checked {
      --ab: var(--active-inner);
      --x: 17px;
    } */
  /* input[type="checkbox"].switch:disabled:not(:checked):after {
      opacity: 0.6;
    } */

  /* }  */

  /* ======================================================== */

  /* ul {
  margin: 12px;
  padding: 0;
  list-style: none;
  width: 100%;
  max-width: 320px;
}
ul li {
  margin: 16px 0;
  position: relative;
} */

  /* html {
  box-sizing: border-box;
}

* {
  box-sizing: inherit;
}
*:before, *:after {
  box-sizing: inherit;
} */

  /* body {
  min-height: 100vh;
  font-family: "Inter", Arial, sans-serif;
  color: #8A91B4;
  display: flex;
  justify-content: center;
  align-items: center;
  background: #F6F8FF;
}
@media (max-width: 800px) {
  body {
    flex-direction: column;
  }
} */
  /* ======================================================== */
  /* input[type="checkbox"] { */
  /* Add if not using autoprefixer */
  /* -webkit-appearance: none; */
  /* appearance: none; */
  /* For iOS < 15 to remove gradient background */
  /* background-color: red; */
  /* Not removed via appearance */
  /* margin: 0; */
  /* } */

  /* .input__control {
    position: relative;
    font-family: "Montserrat", "sans-serif";
    font-size: 1rem;
    line-height: 1.1; */
  /* display: grid;
    grid-template-columns: 1em auto; */
  /* gap: 0.4em; */
  /* } */
  /* 
  .outside {
    display: inline-block;
    position: absolute;
    left: -4px;
    top: 50%;
    margin-top: -10px;

    width: 18px;
    height: 18px;
    border: 2px solid #678efe;
    border-radius: 2px;
    -webkit-box-sizing: border-box;
    box-sizing: border-box;
    background: none;
  }

  .inside {
    position: absolute;
    top: 50%;
    left: 50%;
    -webkit-transform: translate(-50%, -50%);
    transform: translate(-50%, -50%);
    display: inline-block;
    border-radius: 50%;
    width: 10px;
  } */
</style>
