<template>
    <div class="block">
        <img src="@/assets/img/logo.svg" class="logo" alt="лого">
        <div class="burger"></div>
        <div class="header">
            <ul
            v-for="page of pages"
            :page="page"
            :key="page.id"
            >
                <li class="header5">{{page.title}}</li>
            </ul>
        </div>
    </div>
</template>

<script>
 import { ref } from 'vue'

export default {
    setup() {
        const pages = ref([
            {title: 'Преимущества', id: 0},
            {title: 'Услуги', id: 1},
            {title: 'Виджет', id: 2},
            {title: 'Кому', id: 3},
            {title: 'Тарифы', id: 4},
            {title: 'Блог', id: 5},
        ])

        return {
            pages,
        }
    }
}
</script>

<style lang="sass" scoped>
.logo
    @media( max-width: 870px) 
        width: 15px
        height: 15px
.header
    display: flex
    flex-direction: row
    justify-content: end
ul
    list-style-type: none
.header5
    margin-right: 35px
    @media( max-width: 1350px) 
        margin-right: 15px
    @media( max-width: 870px) 
        margin-right: 8px
.block
    display: flex 
    flex-direction: row
    justify-content: space-between
    margin-top: 32px
    align-items: center
    @media( max-width: 1350px) 
        margin-top: 20px
        justify-content: space-around
    @media( max-width: 500px) 
        margin-top: 10px
</style>