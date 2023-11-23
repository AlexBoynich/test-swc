<template>
    <div>
        <div>
            <input type="radio" id="one" value=true v-model="radioButton">
                <label for="one">Открыть все</label>
            <input type="radio" id="two" value=false v-model="radioButton">
                <label for="two">Закрыть все</label>
        </div>
        <div                 
            v-for="item in list" 
            :key="item.id" type="checkbox" 
        >
            <input 
                type="checkbox"
                :id="item.id" 
                :value="item.id"
                v-model="checkedBoxes"
            >
            <label :for="item.id">{{item.id}}</label>
        </div>
        <AccordionItem 
            :defaultDetails="defaultDetails"
            :checkedBoxes="checkedBoxes"
            :list="list"
        />
        <AccordionItem
            :list="[{title: 'title', id: 1000}]"
            :defaultDetails="defaultDetails"
        >
            <AccordionItem 
                :defaultDetails="defaultDetails"
                :checkedBoxes="checkedBoxes"
                :list="list"
            />
        </AccordionItem>
        <button @click="addElement">Добавить элемент</button>
        <button @click="removeElement">Удалить элемент</button>
    </div>
</template>

<script setup>
import {ref, watch} from 'vue'
import AccordionItem from './AccordionItem.vue';

    let radioButton = ref('false')

    let defaultDetails = ref(false);

    const list = ref([
        {title: 'title', id: 1},
        {title: 'title', id: 2},
        {title: 'title', id: 3},
        {title: 'title', id: 4},
])

    const checkedBoxes = ref([])
    
    watch(radioButton, (newValue) => {
      if (newValue =='true') return defaultDetails.value =  true
      else return defaultDetails.value =  false
    });

    function addElement () {
        list.value.push({title: 'title', id: list.value.length + 1})
    }
    function removeElement () {
        list.value.pop()
    }

</script>

<style lang="sass">

</style>