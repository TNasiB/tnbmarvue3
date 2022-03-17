<template>
    <div class="frame-total">
        <div class="container">
            <h2 class="title">Общая информация</h2>
            <div class="frame-total-wrapper frame-wrapper">
                <div class="total-wrapper flex">
                    <div class="total-wrapper-key">
                        <div class="text__key">ФИО</div> 
                        <div class="text__key">Номер телефона</div>
                        <div class="text__key">E-mail</div>
                        <div class="text__key">Город</div>
                        <div class="text__key">Организация</div>
                        <div class="text__key">Адрес</div>
                        <div class="text__key">Количество пациентов</div>
                        <div class="text__key">Специалист</div>
                        <div class="text__key">Дата приема</div>
                        <div class="text__key">Время приема</div>
                        <div class="text__key">Стоимость</div>
                    </div>
                    <div class="total-wrapper-value">
                        <div class="text__value">{{ user.name }}</div>
                        <div class="text__value">{{ user.number }}</div>
                        <div class="text__value">{{ user.mail }}</div>
                        <div class="text__value">Уфа</div>
                        <div class="text__value">ООО "Меги"</div>
                        <div class="text__value">Давлетшина 30</div>
                        <div class="text__value">{{ this.pacientCount }}</div>
                        <div class="text__value">Стоматолог,Хуелог</div>
                        <div class="text__value">{{ this.dateObj.date }}</div>
                        <div class="text__value">{{ this.dateObj.time }}</div>
                        <div class="text__value">ОООООООчень много</div>
                    </div>
                </div>
                
                <button class="form-total__button">Записаться на прием</button>
            </div>

        </div>
    </div>
</template>
<script>
export default {
    name: "Frame-sixth",
    props: {
        user: {type: Object},
        pacientCount: {type: Number},
        dateObj: {type: Object},
    }
}
</script>


<style>
.frame-total-wrapper{
    display: flex;
    flex-direction: column;
    align-items: center;
}
.total-wrapper{
    width: 80%;
    border: 3px solid #26A69A;
    border-radius: 50px;
    padding: 20px 40px;
    margin: 0 auto;
}
.text__key,.text__value{
    font-family: 'Roboto';
    font-size: 20px;
    line-height: 24px;
    color: #004D45;
}
.text__value{
    margin-left: 5vw;
}
.form-total__button{
    width: 80%;
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
    margin-top: 20px;
}
.form-total__button:hover{
    background: #004D45;
}
</style>