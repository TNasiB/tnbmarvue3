<template>
    <div class="city">
        <div class="container">
            <h2 class="city-title title">Выберите город и организацию</h2>
            <div class="city-inner frame-wrapper">
                <input class="input-city completed shadow" @keyup.enter="GetInfo" type="text" placeholder="Введите организацию">
                <!-- <input class="input-org shadow" type="text" placeholder="Выберите организацию"> -->
               <CompanyWrapper
                @send-company="SendCompany"
                :companies="companies"
                :isInput="isInput"
                />
            </div>
        </div>
    </div>
</template>

<script>
import CompanyWrapper from './CompanyWrapper.vue'
export default {
    name: "Frame-two",
    data(){
        return{
            isInput:false,
        }
    },
    props:{
        companies:{type:Object}
    },
    methods:{
        GetInfo(){
            let InputCompany=document.querySelector('.input-city')
            let value=InputCompany.value
            if (value==""){
                this.isInput=false
            }
            else{
                this.isInput=true
            }
            this.$emit('get-info',value)
            
        },
       SendCompany(organization){
            this.$emit('send-organization',organization)
        }
    },
    components:{
        CompanyWrapper,
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
@media (max-width:780px)
    .input-city 
        height: 54px
    

@media (max-width:780px)
    .input-city 
        height: 54px
        font-size: 20px
    
    .org-item
        font-size: 20px


</style>
