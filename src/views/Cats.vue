<template>
    <div>
        <h2 class="mb-4">Cats Component</h2>
        <b-table striped hover :items="cats">
            <template slot="name" slot-scope="data">
                <router-link :to="`/pets/${data.index}`">
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
      'cats'
    ])
  }
}
</script>
