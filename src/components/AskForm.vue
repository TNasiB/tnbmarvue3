<template>
    <div class="frame-form-entry-wrapper flex-column">
        <input type="text" placeholder="ФИО" class="form-entry__name">
        <input type="text" placeholder="Номер телефона" class="form-entry__number">
        <input type="e-mail" placeholder="E-mail" class="form-entry__mail">
        <button class="form-entry__button" @click="NextFrame">Продолжить</button>
    </div>
</template>

<script>
export default {
    name: "AskForm",
    methods:{
        NextFrame(){
            // let inputName=document.querySelector('.form-entry__name')
            // // let inputNumber=document.querySelector('.form-entry__number')
            // // let inputMail=document.querySelector('.form-entry__mail')
            // // let form=document.querySelector('.frame-form-entry-wrapper')
            // if (inputName.value=''){
            //     inputName.classList.add('red')
            // }

        }


    },
}
</script>

<style scoped>
.red{
    border: 3px solid red;
}
.red::placeholder{
    color: red;
}
</style>
