<script>
  export default{
    data(){
      return{
        userName1: '홍길동',
        userName2: '',
        num: 0,
      }
    },

    methods: {
      greeting(){
        return 'Hi, there ' + this.userName1
      },
      bye(userName2){
        return 'Bye, there ' + userName2
      },
      increment(){
        this.num++
      },
      decrease(){
        this.num--
      }
    }
      
  }
</script>

<template>
  <h1> {{  greeting() }}</h1>
  <h1> {{  bye('김길동') }}</h1>
  <button @click="increment"> Increase Number </button>
  <button @click="decrease"> Decrease Number </button>
  <p> {{  num }}</p>
</template>

<style scoped></style>
