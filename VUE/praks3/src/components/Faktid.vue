<template>
  <div>
   <h1>Numbri faktid</h1>
   <p>Huvitavad faktid iga numbri kohta</p>
   <input type="number" min="0" v-model="number">
      <input type="number" min="0" v-model="increment">
   <p>{{ data }}</p>
   v-for
  </div>
</template>

<script>
const axios = require('axios')
    
export default {
  name: 'Faktid',
  data () {
      return {
         data: '',
         number: 0,
         increment: 0
        }
      },
    methods: {
      getFact () {
            if (this.number !== '', this.increment !== '') {
            let url = `http://numbersapi.com/${this.number}`
            this.number
            this.increment
            
            axios.get(url)
            .then(response => {
               this.data = response.data 
            })
            .catch(error => {
                console.log(error)
            }) 
          }
      }
     },
    watch: {
        number () {
            this.getResponse ()
        },
         increment () {
             this.getResponse ()
         }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
