<template>
    <div>
        <form @submit.prevent>
            <h4>Название поста</h4>
            <my-input class="my-input" type="text" name="" id="" placeholder="Название" v-model="post.title" />
            <my-input class="my-input" type="text" name="" id="" placeholder="Описание" v-model="post.description" />
            <my-button class="btn" @click="$emit('createPost', post )">Создать</my-button>
        </form>
    </div>
</template>

<script>

export default {
    data() {
        return {
            post: {
                title: '',
                description: ''
            }
        }
    },
    components: {

    }
}
</script>

<style scoped lang="sass">
form
  display: flex
  flex-direction: column
.btn
    align-self: flex-end
    margin-top: 15px
</style>