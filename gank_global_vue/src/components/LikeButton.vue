<script>
import { ref } from 'vue'

export default {
    setup() {
        return {
            countLike: ref(0),
        }
    }
}
</script>


<template>
    <div class="share-button" @click="countLike++">
        <font-awesome-icon v-if="countLike > 0" icon="fa-solid fa-heart" />
        <font-awesome-icon v-else icon="far fa-heart" />
    </div>
    {{ countLike }}
</template>
  
<style scoped>

</style>
  