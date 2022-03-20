<template>
    <div class="frame-form">
        <div class="container">
            <h2 class="frame-form__title title">Заявка на медицинское обследование</h2>
            <div class="frame-form-inner frame-wrapper">
                <div class="frame-form-wrapper flex">
                    <AskForm
                    @get-value="getValue"
                    />
                    <div class="frame-form__img"></div>
                </div>
            </div>
        </div>
    </div>
</template>


<script>
import AskForm from "./AskForm"

export default {
    name: "Frame-one",
    components: {
        AskForm
    },
    methods: {
        getValue(user) {
            this.$emit("get-value", user)
        }
    }
}
</script>

<style>
.frame-form__title{
    font-family: 'Roboto';
    font-weight: 700;
    font-size: 30px;
    line-height: 46px;
    text-transform: uppercase;
    color: #004D45;
    text-align: center;
}
.frame-form__img{
    width: 40%;
    background-image: url(../assets/img/med_main.png);
    background-size: contain;
    height: 40vw;
}
.frame-form-wrapper{
    width: 100%;
    align-items: center;
    height: 50vh;
    justify-content: center;

}
.frame-form-entry-wrapper{
    width: 60%;
    align-items: center;
}
.form-entry__name,.form-entry__number,.form-entry__mail{
    width: 100%;
    height: 7vh;
    margin-bottom: 20px;
    border: 3px solid #26A69A;
    border-radius: 50px;
    padding-left: 15px;
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 700;
    font-size: 20px;
    line-height: 28px;
    color: #004D45;
}
.form-entry__name::placeholder,.form-entry__number::placeholder,.form-entry__mail::placeholder{
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 700;
    font-size: 20px;
    line-height: 28px;
    color: #004D45;
}
.form-entry__button{
    width: 100%;
    height: 8vh;
    background: #26A69A;
    border-radius: 50px;
    border: 0;
    font-family: 'Roboto';
    font-weight: 700;
    font-size: 20px;
    line-height: 28px;
    color: #FFFFFF;
    text-align: center;
}
.form-entry__button:hover{
    background: #004D45;
}
@media (max-width:900px){
    .frame-form__img{
        width: 44%;
        height: 46vw;
    }
    .frame-form-entry-wrapper{
        width: 50%;
    }
}
@media (max-width:640px){
    .frame-form__img{
        width: 52%;
        height: 52vw;
    }
    .frame-form-entry-wrapper{
        width: 50%;
    }
    .form-entry__name::placeholder, .form-entry__number::placeholder, .form-entry__mail::placeholder{
        font-size: 18px;
    }
    .frame-form__title{
        line-height: 30px;
    }
}
@media (max-width:520px){
    .frame-form__img{
        display: none;
    }
    .frame-form-entry-wrapper{
        width: 90%;
    }
}
</style>