<template>
    <div class="company-table-wrapper">   
        <tr @click="ShipCompany" class="company-name-wrapper">
            <div class="company-name">
                <td class="org-item">{{company.properties.name}}</td>
                <td  class=" ord-item company__city">{{company.properties.description}}</td>
            </div>
            <button 
                class="radio"
                :class="{active: isChoose}"
                @click="chooseCompany"
            ></button>
            
        </tr>
    </div>
</template>
<script>
export default {
    name:"CompanyItem",
    props:{
        company:{type:Object},
    },
    data() {
        return {
            isChoose: false,            
        }
    },
    methods:{
        ShipCompany(){
            let organization = {
                    name: this.company.properties.name,
                    address: this.company.properties.description
                }
            this.$emit('ship-company',organization)
        },
         chooseCompany() {
            this.isChoose = !this.isChoose
        },
    }
}
</script>

<style>
.org-item + .org-item{
    margin-top: 20px;
}
.company-item-wrapper{
    display:flex;
    flex-direction:row;
    
    border-bottom: 1px solid black;
}
.company__city{
    padding-left: 20px;
}
.company-table-wrapper{
    border-bottom:3px solid #004D45;
}
.company-name-wrapper{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    padding: 10px 0;
}
</style>