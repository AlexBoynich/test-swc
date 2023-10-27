<template>
    <div class="container">
        <div class="startBlock">
            <img src="@/assets/img/image.svg" class="image1" alt="фон">
            <img src="@/assets/img/image2.svg" class="image2" alt="фон2">
            <my-dialog 
            v-model:show="dialogVisible">
                <ContactBlock />
            </my-dialog>
            <div  class="leftSide">
                <HeaderComponent />
                <h1>{{ mainTitle }}</h1>
                <h4 class="inter">{{ subTitle }}</h4>
                <div>
                    <my-button 
                    class="btn"
                    >
                    Подключиться
                </my-button>
                </div>
                <div class="arrowBlock">
                    <img src="@/assets/img/arrow.svg" alt="вниз">
                </div>
            </div>
            <RightSideBlock
             class="rightSide"
            @changeVisible="changeDialogVisible"
            />
        </div>
    </div>
</template>

<script>
import HeaderComponent from './base/HeaderComponent.vue'
import RightSideBlock from './RightSideBlock.vue';
import { ref } from 'vue'
import MyButton from './UI/MyButton.vue';
import MyDialog from './UI/MyDialog.vue';
import ContactBlock from './UI/ContactBlock.vue';

export default {
    components: {
        HeaderComponent,
        RightSideBlock,
        MyButton,
        MyDialog,
        ContactBlock
    },
    setup() {
        const mainTitle = ref('Техническая поддержка сайтов, CRM систем и мобильных приложений')
        const subTitle = ref('Профессиональное техническое сопровождение и обслуживание сайтов: полный комплекс услуг от опытных экспертов')
        let dialogVisible = ref(false)
        const changeDialogVisible = () => {
            console.log('Работате')
            dialogVisible.value = !dialogVisible.value
        }
        return {
            mainTitle,
            subTitle,
            dialogVisible,
            changeDialogVisible
        }
    }
}
</script>

<style lang="sass" scoped>
.container
    width: 100%
    margin: auto
    padding: 0 0 0 135px
    height: 100vh
    @media( max-width: 1350px) 
        padding-left: 70px
    @media( max-width: 870px) 
        padding-left: 35px
    @media( max-width: 500px) 
        padding-left: 8px
    
.startBlock
    display: flex
    flex-direction: row
    position: relative
    .leftSide
        width: 69%
        h1
            max-width: 570px
            margin-top: 164px
            @media( max-width: 1350px) 
                max-width: 400px
                margin-top: 80px
            @media( max-width: 870px) 
                max-width: 200px
                margin-top: 40px
        .inter
            margin-top: 40px
            max-width: 480px
            letter-spacing: -1px
            @media( max-width: 1350px) 
                max-width: 300px
            @media( max-width: 870px)
                max-width: 160px
                margin-top: 20px
        .btn 
            margin-top: 40px
            @media( max-width: 1350px) 
                margin-top: 20px
            @media( max-width: 870px) 
                margin-top: 16px
        .arrowBlock
            margin-top: 40px
            width: 54px
            height: 54px
            display: flex
            justify-content: center
            align-items: center
            border: 1px solid rgba(233, 234, 240, 1)
            border-radius: 10px

    .rightSide
        width: 37%
        @media( max-width: 870px) 
            width: 40%
.image1
    position: absolute
    right: 0
    top: 130px
    width: 56%
    @media( max-width: 870px) 
        top: 130px
    @media( max-width: 470px) 
        top: 100px
.image2
    position: absolute
    top: 90px
    right: 250px
    width: 42%
    @media( max-width: 1350px) 
        right: 170px
    @media( max-width: 870px) 
        top: 50px
        right: 120px
    @media( max-width: 500px) 
        top: 80px
        right: 70px
    @media( max-width: 400px) 
        top: 140px
        right: 70px

</style>