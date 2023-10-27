<template>
    <div class="block">
        <div class="rightSideHeader">
            <h5 class="lang header5">En</h5>
            <div class="contactBlock">
            <a href="tel:+7 (495) 123-45-67" class="inter btn">+7 (495) 123-45-67</a>
            <button class="btn" @click="$emit('changeVisible')">Контакты</button>
        </div>
        </div>
    </div>
</template>

<script>
export default {

}
</script>

<style lang="sass" scoped>
h5
    font-family: SF Pro Display
.block
    height: 100vh
    background: linear-gradient(rgba(80, 108, 207, 1), rgba(52, 83, 194, 1),)
    .rightSideHeader
        display: flex
        flex-direction: row
        padding: 32px 40px 0
        justify-content: space-between
        align-items: center
        @media( max-width: 1350px) 
            padding: 20px 20px 0
        @media( max-width: 870px) 
            padding: 20px 8px 0
        @media( max-width: 500px) 
            padding: 10px 4px 0
        button
            background: rgba(73, 161, 241, 1)
            border-radius: 10px
            border: none
            padding: 12px 24px
            margin-left: 15px
            cursor: pointer
            @media( max-width: 1350px) 
                padding: 8px 12px
            @media( max-width: 870px) 
                padding: 4px
    .lang 
        color: rgba(139, 159, 204, 1)

    .contactBlock
        display: flex
        flex-direction: row
        align-items: center
        .inter
            text-decoration: none

</style>