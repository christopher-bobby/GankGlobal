<template>
  <Comments />
  <ShareButton />
  <LikeButton />
  <div>
    <h1>Data Fetching Example</h1>
    
    <ul>
      <li v-for="item in data" :key="item.id">
        {{ item.name }}
        {{ item.email }}
      </li>
    </ul>
  </div>
</template>

<script>
import { ref, onMounted } from 'vue';
import axios from 'axios';
import ShareButton from './ShareButton.vue'
import LikeButton from './LikeButton.vue'
import Comments from './Comments.vue'


export default {
    setup() {
        // Define reactive data property
        const data = ref([]);
        // Fetch data when the component is mounted
        onMounted(async () => {
            try {
                const response = await axios.get('https://jsonplaceholder.typicode.com/users');
                // Update the reactive data property with the fetched data
                data.value = response.data;
            }
            catch (error) {
                console.error('Error fetching data:', error);
            }
        });
        // Return data for the template to use
        return {
            data
        };
    },
    components: { ShareButton, LikeButton, Comments }
};
</script>

<style scoped>
/* Add your component-specific styles here */
</style>