<script>
  export default{
    data(){
      return{
        click: true,
        kValue:  ''
      }
    },
    /*methods: {
      createAlert(){
        if( this.click){
          alert('경고창이 뜸')
          this.click = false
        
      }
    }
  }*/
    methods: {
      createAlert(){
        alert('경고창 한번만')
      },
      getKey(e){
        this.kValue = e.key;
      }
    }
}
</script>

<template>
  <!-- <button @click="createAlert"> 경고 </button> -->
  <button @click.once="createAlert"> 경고 한번만 </button>
  <input type="text" v-on:keydown.s="getKey"> <br>
  <span> {{ kValue }}</span>
</template>

<style></style>
