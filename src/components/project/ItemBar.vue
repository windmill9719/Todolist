<template>

</template>

<script>
  export default {
    name: "ItemBar",
    methods:{
      onDone(){
        this.$emit('onItemDone')
      }
    }
  }
</script>

<style scoped>

</style>