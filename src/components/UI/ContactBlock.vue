<template>
    <div class="contactBlock header5">
        <h2>Контактная информация</h2>
        <div class="locationBlock subBlock">
            <div class="location">
                <img src="@/assets/img/location-mark.svg" alt="Тут ">
                <h4 class="">Наш офис</h4>
            </div>
            <h4 class="black">Санкт-Петербург, ул. Такая-то, д. 1</h4>
            <a class="btn" href="#">Показать на карте</a>
        </div>
        <div class="subBlock row between">
            <div class="callAndWrite">
                <h4>Звоните: <a class="black" href="tel:+7 (495) 123-45-67">+7 (495) 123-45-67</a></h4>
                <h4>Пишите: <a class="black" href="mailto:info@test.ru">info@test.ru</a></h4>
            </div>
            <button>Заказать звонок</button>
        </div>
        <div class="subBlock">
            <div class="operationMode">
                <img src="@/assets/img/clock.svg" alt="Часы ">
                <h4>Режим работы: </h4>
            </div>
            <h4 class="black">Пн-Пт — с 10:00 до 18:00</h4>
            <h4 class="black">Сб-Вс — выходной</h4>
        </div>
        <div class="subBlock">
            <h4>Мы в соцсетях</h4>
            <div class="socialIcons">
                <img src="@/assets/img/inst.svg" alt="Инста">
                <img src="@/assets/img/vk.svg" alt="Вк">
                <img src="@/assets/img/zen.svg" alt="ЯДзен">
            </div>
        </div>
    </div>
</template>

<script>
export default {
    setup() {
        
    },
}
</script>

<style lang="sass" scoped>
h4
    font-family: SF Pro Display
.contactBlock
    min-width: 500px
    min-height: 500px
    @media( max-width: 870px) 
        min-width: 70vw
        min-height: auto
.location, .operationMode
    display: flex
.subBlock
    margin-top: 40px
    button
        padding: 18px 28px
        border-radius: 10px
        border: 2px solid rgba(95, 107, 119, 1)
        background: rgba(255, 255, 255, 1)
        color: rgba(95, 107, 119, 1)
        @media( max-width: 870px) 
            padding: 10px 12px 
.row
    display: flex
    flex-direction: row
    @media( max-width: 870px) 
        flex-direction: column
.between
    justify-content: space-between
.callAndWrite
    display: flex
    flex-direction: column
    justify-content: space-between
.socialIcons
    display: flex
    justify-content: start
    align-items: center
    img
        margin: 12px 18px 0 0
.btn
    color: rgba(80, 108, 207, 1)
.black
    color: rgba(0, 0, 0, 1)
</style>