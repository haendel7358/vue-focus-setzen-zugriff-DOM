<template>
  <div class="hello" >
    <h3>{{ msg }}</h3>
    <br/>
    <input 
      type="text"
      placeholder="Eingabe"
      ref='eingabe'
    />
    <!--Zugriff mit ref auf den DOM  -->
    <div ref= "elRef">
      <h3>Zugriff mit ref auf den DOM</h3>
    </div>
    <!--  -->
  </div>
</template>

<script>
import {ref, onMounted} from 'vue'

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  setup(){
    const eingabe = ref(null)
    const elRef = ref(null)

    onMounted(()=>{
      eingabe.value.focus();
      // Zugriff mit ref auf den DOM
      console.log(elRef.value.textContent);
     }
    )
   
    return{
      eingabe,
      elRef
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
