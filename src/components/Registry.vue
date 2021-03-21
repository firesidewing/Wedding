<template>
  <div id='registry'>
    
  </div>
</template>



<script>
export default {
  name: "Registry",
  mounted() {
    let registryScript = document.createElement('script')
    registryScript.setAttribute('src', '//www.myregistry.com//Visitors/GiftList/iFrames/EmbedRegistry.ashx?r=mjUC49KQVEVuqxwNjhMPnQ2&v=2')
    registryScript.setAttribute('id', 'script_myregistry_giftlist_iframe')
    let r = document.getElementById('registry')
    r.appendChild(registryScript)
  }
}
</script>
<style>

</style>