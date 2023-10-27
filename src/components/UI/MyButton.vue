<template>
    <div>
        <button>
            <slot></slot>
        </button>
    </div>
</template>

<script>
export default {
    name: 'MyButton',
}
</script>

<style scoped lang="sass">
button
    font-family: SF Pro Display
    padding: 15px 15px
    background: rgba(80, 108, 207, 1)
    color: rgba(255, 255, 255, 1)
    border-radius: 10px
    border: none
    font-size: 16px
    font-weight: 500
    line-height: 22px
    letter-spacing: 0px
    text-align: center
    @media( max-width: 1350px) 
        padding: 12px 12px
    @media( max-width: 8700px) 
        padding: 8px 8px
        font-size: 8px
        line-height: 12px

</style>