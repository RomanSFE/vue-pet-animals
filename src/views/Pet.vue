<template>
    <div>
        <!-- <img :src="`{{animal.image}}`" alt="img"/> -->
        <h2>Name: {{animal.name}}</h2>
        <p>Gender: {{animal.gender}}</p>
        <p>Age: {{animal.age}}</p>
        <p>Color: {{animal.color}}</p>
        <p>Location: {{animal.location}}</p>
    </div>
</template>

<script>
import {mapState} from 'vuex'

export default {
    data(){
        return {
            animal: {}
        }
    },
  computed: {
    ...mapState([
      'cats',
      'dogs'
    ])
  },
  mounted(){
      const animal = this[this.$route.params.species] [this.$route.params.id]
      this.animal = animal
  }
}
</script>

<style lang="css">
  h2 {
    color: #71def1;
}
p {
    color: #e860a4;
}
</style>