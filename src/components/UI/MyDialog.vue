<template>
    <div
    v-if="show"
     class="dialog"
     @click="hideDialog">
        <div 
        class="dialog__content"
        @click.stop>
            <slot></slot>
        </div>
    </div>
</template>

<script>
export default {
 name: 'my-dialog',
 props :{
     show: {
        type: Boolean, 
        default: false,
     }
 },
 methods: {
    hideDialog() {
        this.$emit('update:show', false)
    }
 }
}
</script>

<style scoped lang="sass">
.dialog
    top: 0
    bottom: 0
    right: 0
    left: 0
    position: fixed
    display: flex
    background: rgba(0,0 ,0 ,0.5 )
.dialog__content
    margin: auto
    background: white
    border-radius: 12px
    min-height: 50px
    min-width: 300px
    padding: 38px
    @media( max-width: 870px) 
        padding: 10px
</style>