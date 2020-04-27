<template>
  <div class="row">
    <div class="col">
      <h3>Numeric value: {{dataMonitor.numValue}} </h3>
    </div>
    
    <div class="col">
      <h3>Symbolic value: {{dataMonitor.symValue}} </h3>
    </div>
  </div>
</template>

<script>
export default {
  name: 'PermissionMonitor',
  data: function () {
    return {}
  },
  props: {
    dataMonitor: Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}

</style>
