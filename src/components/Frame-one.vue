<template>
    <div class="frame-wrapper">
        <div class="frame-form">
            <div class="container">
                <div class="frame-form__title">Заявка на медицинское обследование</div>
                <div class="frame-form-wrapper flex">
                     <div class="frame-form-entry-wrapper flex-column">
                         <input type="text" placeholder="ФИО" class="form-entry__name">
                         <input type="text" placeholder="Номер телефона" class="form-entry__number">
                         <input type="e-mail" placeholder="E-mail" class="form-entry__mail">
                         <button class="form-entry__button">Записаться на прием</button>
                     </div>
                     <div class="frame-form__img"></div>
                </div>
            </div>

        </div>
    </div>
</template>


<script>
export default {
    
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
    margin-top: 50px;
}
.frame-form__img{
    width: 40%;
    background-image: url(../assets/img/med_main.png);
    background-size: cover;
    height: 40vw;
}
.frame-form-wrapper{
    width: 100%;
    align-items: center;

}
.frame-form-entry-wrapper{
    width: 60%;
    align-items: center;
}
.form-entry__name,.form-entry__number,.form-entry__mail{
    width: 85%;
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
    width: 90%;
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
</style>