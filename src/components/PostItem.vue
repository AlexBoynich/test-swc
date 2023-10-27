<template>
    <div class="post">
        <div>
            <div>Название: <strong>{{post.title}}</strong></div>
            <div>Описание: <strong>{{ post.description }}</strong></div>
        </div>
        <div class="post__btns">
            <my-button @click="remove(post)">Удалить</my-button>
        </div>
    </div>
</template>

<script>
export default {
  components: { 
    },
    props: {
        post: {
            type: Object, 
            required: true
        }
    },
    methods: {
        remove(post) {
            this.$emit('remove', post)
        }
    }
}
</script>

<style lang="sass" scoped>
.post
  padding: 15px
  border: 2px solid teal
  margin-top: 15px
  display: flex
  align-items: center
  justify-content: space-between
</style>