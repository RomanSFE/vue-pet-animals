<template>
    <div>
        <h2 class="mb-4">Dogs Component</h2>
        <b-table striped hover :items="dogs"></b-table>
    </div>
</template>

<script>
import dogs from '@/data/dogs'
export default {
    data(){
        return {
            dogs
        }
    }
}
</script>
