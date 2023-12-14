<script>
import { ref } from 'vue'


export default {
    data() {
        return {
            inputValue: '',
        };
    },
    computed: {
        capitalizedInput() {
            return this.inputValue.toUpperCase();
        },
    },
    setup() {
        let sampleComment = {
            name: "Shumie",
            comment: "this is sample comment",
            profilePicture: "https://lh3.googleusercontent.com/a/ACg8ocIl439dNPaMANh130UjU2IqNXqS2-4399R4iS6xXpFp=s96-c"
        }

        return {
            countLike: ref(0),
            comments: ref([sampleComment, sampleComment, sampleComment, sampleComment]),
            sampleComment: sampleComment,
            inputValue: ''
        }
    }
}
</script>


<template>
    <div class="add_comment">
        <img :src="sampleComment?.profilePicture" alt="profile picture add comment" class="profile_picture"/>
        <input type="text" v-model="inputValue" placeholder="Write a comment..." />

    </div>
    <div v-for="(comment, index) in comments" :key="index" class="comment_container">
        <img :src="comment.profilePicture" alt="profile picture" class="profile_picture" value="inputValue" />
        <div>
            <div class="comment">
                <span class="name">{{ comment.name }}</span>
                <span>{{ comment.comment }}</span>
            </div>
            <div>
                <span class="reply">Reply</span>
                <span>15 hours ago</span>
            </div>
        </div>
    </div>
</template>
  
<style scoped>
    .comment_container {
        display: flex;
        margin-bottom: 10px;
    }
    .profile_picture {
        border-radius: 20px;
        width: 40px;
        height: 40px;
        margin-right: 10px;
    }

    .comment {
        background: rgba(0,0,0,0.3);
        padding: 10px 14px;
        border-radius: 12px;
    }
    .comment span {
        display: block;
        color: #fff;
    }
    .name {
        font-weight: bold;
    }
    .reply {
        font-weight: bold;
        margin-left: 10px;
        margin-right: 14px;
    }
    
</style>
  