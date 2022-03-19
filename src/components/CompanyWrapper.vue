<template>
         <table class="org-table shadow" @click="test" :class="{none:!isInput}">
             <CompanyItem
             v-for="(company,index) in companies" :key="index" :company="company"
             @ship-company="shipCompany"
             />
        </table>
</template>
<script>
import CompanyItem from './CompanyItem.vue'
export default {
    name:"CompanyWrapper",
    props:{
        companies:{type:Array},
        company:{type:Object},
        isInput:{type:Boolean},
    },
    components:{
        CompanyItem,
    },
    methods:{
        shipCompany(organization){
            this.$emit('send-company',organization)
        },
        test(){
            console.log(this.isInput)
        }
    }
}
</script>

<style lang="sass">
.org-table
    font-size: 24px
    color: #004D45
    font-weight: 400
    // margin: 0px
    padding: 20px
    border: 2px solid #26A69A
    border-radius: 40px
    margin-top: 20px
.none
    display: none
</style>