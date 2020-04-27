<template>
  <div>
    <!-- <h2>{{this.dataItem.type}}</h2> -->
    <label for="read">Read</label>
    <input type="checkbox" id="read" v-model="readResult" @change="changeCheckBox" :checked="readResult">
    <br>

    <label for="write">Write</label>
    <input type="checkbox" id="write" v-model="writeResult" @change="changeCheckBox" :checked="writeResult">   
    <br>

    <label for="execute">Execute</label> 
    <input type="checkbox" id="execute" v-model="executeResult" @change="changeCheckBox" :checked="executeResult">
    <br>  
     
  </div>
</template>

<script>
export default {
  name: 'PermissionItem',
  data: function () {
    return {
      readResult: this.dataItem.bit[0] === '0',
      writeResult: this.dataItem.bit[1] === '0',
      executeResult: this.dataItem.bit[2] === '0'
    }
  },
  props: {
    dataItem: Object
  },
  methods: {
    changeCheckBox: function () {
      let newBit = [~~this.readResult, ~~this.writeResult, ~~this.executeResult].join('');
      this.$emit('changeCheckBox', newBit, this.dataItem.id)
    }
  }

}
</script>

<style scoped>

</style>