<template>
    <div v-if="posts.length > 0">

        <h3>Список пользователей</h3>

        <PostItem 
            v-for="post in posts"
            :post="post" 
            :key="post.id"
            @remove="$emit('remove', post)"
        />
        
    </div>

    <div v-else style='color:red'>
        Список постов пуст
    </div>
</template>

<script>
import PostItem from './PostItem.vue';
    export default {
    props: {
        posts: {
            type: Array,
            required: true
        }
    },
    components: { PostItem }
}
</script>

<style scoped>

 

</style>