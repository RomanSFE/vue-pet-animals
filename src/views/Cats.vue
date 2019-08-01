<template>
    <div>
        <h2 class="mb-4">Cats Component</h2>
        <b-table striped hover :items="cats"></b-table>
    </div>
</template>

<script>
import cats from '@/data/cats'
export default {
    data(){
        return {
            cats
        }
    }
}
</script>
