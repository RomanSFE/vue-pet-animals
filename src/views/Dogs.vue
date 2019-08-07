<template>
    <div>
        <h2 class="mb-4 dogs-cls">Dogs Table</h2>
        <b-table striped hover :items="dogs">
            <template slot="name" slot-scope="data">
                <router-link :to="`/pets/dogs/${data.index}`">
                    {{ data.value }}
                </router-link>
            </template>
        </b-table>
    </div>
</template>

<script>
import {mapState} from 'vuex'

export default {
    data(){
        return {}
    },
  computed: {
    ...mapState([
      'dogs'
    ])
  }
}
</script>
<style lang="css">
    h2.mb-4.dogs-cls {
    color: #ef355e;
}
</style>
