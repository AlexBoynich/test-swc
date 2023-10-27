<template>
    <div v-if="posts.length > 0">
        <post-item
        v-for="post of posts"
        :key="post.id"
        class="post"
        :post="post"
        @remove="remove" >
        </post-item>
    </div>
    <h2 v-else
    class="pure">Список постов пуст!</h2>
</template>

<script>
import PostItem from './PostItem.vue'

export default {
    props: {
        posts: {
            type: Array,
            required: true
        }
    },
    components: {
        PostItem,
    },
    methods: {
        remove(post) {
            this.$emit('remove', post)
        }

    }
}
</script>

<style scoped lang="sass">
.pure
    color: red
</style>