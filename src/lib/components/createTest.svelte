<script>
  // import { sizesStore } from '$lib/stores/store';
  import { prefixObjArr, sizesStore, pointSystem } from "$lib/stores/store.js";
  $: console.log("prefixObjArr", $prefixObjArr);
  $: console.log("sizesStore", $sizesStore);
  $: console.log("pointSystem", $pointSystem);

  // function parseObjectKeys(obj) {
  //   for (var objKey in obj) {
  //     //  let cfx = obj[objKey].customPfx;
  //     var sub = obj[objKey];
  //     if (typeof sub == "object") {
  //       parseObjectKeys(sub);
  //       let cfx = sub["customPfx"];
  //       if (cfx) {
  //         pfxArr.splice(objKey, 1, cfx);
  //       }
  //     }
  //   }
  //   console.log(pfxArr);
  // }
</script>

<!-- <div class="form-group"> -->
<pre>
     {JSON.stringify($prefixObjArr, null, 2)}
    </pre>
<!-- </div> -->

<!-- <style>
  .form-group {
    display: flex;
    flex: 1 0 300px;
    flex-direction: column;
  }
</style> -->
