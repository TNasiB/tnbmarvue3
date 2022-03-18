<template>
    <div class="frame-form-entry-wrapper flex-column">
        <input :class="{invalid: !isValid}" type="text" placeholder="ФИО" class="form-entry__name">
        <input :class="{invalid: !isValid}" type="text" placeholder="Номер телефона" class="form-entry__number">
        <input :class="{invalid: !isValid}" type="e-mail" placeholder="E-mail" class="form-entry__mail">
        <button class="form-entry__button" @click="GetValue">Продолжить</button>
        <p :class="{invalid: !isValid}" class="validation-text">Введены не все необходимые данные</p>
    </div>
</template>

<script>
import { useSwiper } from 'swiper/vue';
export default {
    name: "AskForm",
    data() {
        return {
            isValid: true
        }
    },
    methods:{
        GetValue(){
            let name = document.querySelector(".form-entry__name"),
                number = document.querySelector(".form-entry__number"),
                mail = document.querySelector(".form-entry__mail")

            if ( (name.value == "") || (number.value == "") || (mail.value == "") ) {
                this.isValid = !this.isValid
            } else {
                if (this.isValid === false) {
                    this.isValid = !this.isValid
                }
                let user = {
                        name: name.value,
                        number: number.value,
                        mail: mail.value
                    }
    
                this.$emit("get-value", user)
                name.value = ""
                number.value = ""
                mail.value = ""
                this.swiper.slideNext()
            }
        }   
    },
    setup() {
      const swiper = useSwiper();

      return {
        swiper,
      };
    },
}
</script>

<style scoped>
.validation-text {
    display: none;
    text-align: center;
    margin-top: 5px;
}
.validation-text.invalid {
    display: block;
}
input.invalid {
    border: 3px solid red
}
.red{
    border: 3px solid red;
}
.red::placeholder{
    color: red;
}
</style>
