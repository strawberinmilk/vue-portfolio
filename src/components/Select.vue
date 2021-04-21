<template>
  <div class="select" @click='changePage'>
    <h2> {{ display }} </h2>
  </div>
</template>

<script>
export default {
  name: 'Select',
  props: {
    name: String,
    path: String,
    display: String,
  },
  methods: {
    changePage(){
      this.$emit('changePage', this.name)
    }
  }
}
</script>

<style scoped>
  .select{
    background-color: #FFC0CB;
  }
</style>
