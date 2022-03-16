<template>
    <div class="frame-form-entry-wrapper flex-column">
        <input type="text" placeholder="ФИО" class="form-entry__name">
        <input type="text" placeholder="Номер телефона" class="form-entry__number">
        <input type="e-mail" placeholder="E-mail" class="form-entry__mail">
        <button class="form-entry__button" @click="GetValue">Продолжить</button>
    </div>
</template>

<script>
export default {
    name: "AskForm",
    methods:{
        GetValue(){
            let name = document.querySelector(".form-entry__name"),
                number = document.querySelector(".form-entry__number"),
                mail = document.querySelector(".form-entry__mail"),
                user = {
                    name: name.value,
                    number: number.value,
                    mail: mail.value
                }

            this.$emit("get-value", user)
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
