<template>


    <div class="cell" v-on:click="onClickCell">
      <template v-if='a'>{{text}}</template>
      <template v-else></template>
    </div>

</template>

<script>
  export default {
    props: ['n'],
    data() {
      return {a: false, text: ''}
    },
    methods: {
      onClickCell() {
        if(this.text!==''){return}
        this.a = true
        this.text = this.n % 2 === 0 ? 'X' : 'O'
        this.$emit('click', this.text)
      }
    }
  }
</script>

<style>
  .cell {
    border: 1px solid black;
    width: 100px;
    height: 100px;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 80px;
  }
</style>
