<template>
    <div class="company-table-wrapper">   
        <tr>
            <td @click="ShipCompany" class="org-item">{{company.properties.name}}</td>
            <td  class="company__city">{{company.properties.description}}</td>
            
        </tr>
    </div>
</template>
<script>
export default {
    name:"CompanyItem",
    props:{
        company:{type:Object},
    },
    methods:{
        ShipCompany(){
            let organization = {
                    name: this.company.properties.name,
                    address: this.company.properties.description
                }
            this.$emit('ship-company',organization)
        }
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

</style>