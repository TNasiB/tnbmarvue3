<template>
    <div class="city">
        <div class="container">
            <div class="city-inner">
                <h2 class="city-title title">Выберите город и организацию</h2>
                <input class="input-city completed shadow" type="text" placeholder="Выберите город">

                <input class="input-org shadow" type="text" placeholder="Выберите организацию">
                <ul class="org-table shadow">
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
.city-title 
    font-size: 40px
    color: #004D45
    margin: 40px 0
    padding-left: 20px
input.completed 
    background-color: #26A69A
    color: #fff
input.completed::placeholder
    color: #fff
.org-table
    font-size: 24px
    color: #004D45
    font-weight: 400
    margin: 0px
    padding: 20px
    border: 2px solid #26A69A
    position: relative
    top: -34px
    z-index: -1
    padding-top: 50px
.org-item + .org-item
    margin-top: 20px
</style>
