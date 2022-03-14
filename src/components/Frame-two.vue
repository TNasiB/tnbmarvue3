<template>
    <div class="city">
        <div class="container">
            <h2 class="city-title title">Выберите город и организацию</h2>
            <div class="city-inner frame-wrapper">
                <input class="input-city completed shadow" @input="GetInfo" type="text" placeholder="Выберите город">
                <input class="input-org shadow" type="text" placeholder="Выберите организацию">
                <ul class="org-table shadow">
                    <!-- Отдельными компонентами -->
                    <li class="org-item">Меги, Уфа,Давлетшиной 30</li>
                    <li class="org-item">Меги, Уфа,Давлетшиной 30</li>
                    <li class="org-item">Меги, Уфа,Давлетшиной 30</li>
                    <li class="org-item">Меги, Уфа,Давлетшиной 30</li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "Frame-two",
    methods:{
        GetInfo(){
            let InputCompany=document.querySelector('.input-city')
            let value=InputCompany.value
            this.$emit('get-info',value)
        }
    }
}
</script>

<style lang="sass" scoped>
input
    width: 100%
    border: 2px solid #26A69A
    font-size: 30px
    color: #004D45
    padding: 15px
    border-radius: 35px
    padding-left: 35px
    transition: background .2s, color .2s
input::placeholder
    color: #004D45
input + input 
    margin-top: 30px
input.completed 
    background-color: #26A69A
    color: #fff
input.completed::placeholder
    color: #fff
.org-table
    font-size: 24px
    color: #004D45
    font-weight: 400
    // margin: 0px
    padding: 20px
    border: 2px solid #26A69A
    border-radius: 40px
    margin-top: 20px
.org-item + .org-item
    margin-top: 20px
</style>
