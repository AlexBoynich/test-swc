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

        <button @click="addElement(list)">Добавить элемент</button>
        <button @click="removeElement(list)">Удалить элемент</button>

        <br/>
        <br/>
        <br/>

        <AccordionItem
            :list="[{title: 'Accordion', id: '100'}]"
        >
        <div>
            <input type="radio" id="one" value=true v-model="secondRadioButton">
                <label for="one">Открыть все</label>
            <input type="radio" id="two" value=false v-model="secondRadioButton">
                <label for="two">Закрыть все</label>
        </div>
        <div                 
            v-for="itemSecond in secondList" 
            :key="itemSecond.id" type="checkbox" 
        >
            <input 
                type="checkbox"
                :id="itemSecond.id" 
                :value="itemSecond.id"
                v-model="checkedSecondBoxes"
            >
            <label :for="itemSecond.id">{{itemSecond.id}}</label>
        </div>
            <AccordionItem 
                :defaultDetails="defaultSecondDetails"
                :checkedBoxes="checkedSecondBoxes"
                :list="secondList"
            />

            <button @click="addElement(secondList)">Добавить элемент</button>
            <button @click="removeElement(secondList)">Удалить элемент</button>


        </AccordionItem>
    </div>
</template>

<script setup>
import {ref, watch} from 'vue'
import AccordionItem from './AccordionItem.vue';

    let radioButton = ref('false')

    let defaultDetails = ref(false);

    const checkedBoxes = ref([])

    const checkedSecondBoxes = ref([])

    let secondRadioButton = ref('false')

    let defaultSecondDetails = ref(false);

    const list = ref([
        {title: 'title', id: 1},
        {title: 'title', id: 2},
        {title: 'title', id: 3},
        {title: 'title', id: 4},
    ])

    const secondList = ref([
        {title: 'Accordion', id: 1},
    ])

    
    watch(radioButton, (newValue) => {
      if (newValue =='true') return defaultDetails.value =  true
      else return defaultDetails.value =  false
    });
    watch(secondRadioButton, (newValue) => {
      if (newValue =='true') return defaultSecondDetails.value =  true
      else return defaultSecondDetails.value =  false
    });

    function addElement (a) {
        a.push({title: 'title', id: a.length + 1})
    }
    function removeElement (a) {
        a.pop()
    }

</script>

<style lang="sass">

</style>