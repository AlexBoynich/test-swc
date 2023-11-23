<template>
    <div>
        <details 
            v-for="itemList in list" 
            :open="props.defaultDetails || checked(itemList.id)"
            :key="itemList.id"
        >
            <summary>{{ itemList.id }}</summary>
            <p>{{ itemList.title }}</p>
            <slot></slot>
        </details>
    </div>
</template>

<script setup>
import {defineProps} from 'vue'


    const props = defineProps(['defaultDetails', 'checkedBoxes', 'list'])

    function checked(id) {
        let result
        result = props.checkedBoxes?.includes(id) ? true : false
        console.log(result)
        return result
    }

</script>

<style lang="sass">

</style>