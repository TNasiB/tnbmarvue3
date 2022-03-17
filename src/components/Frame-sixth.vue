<template>
    <div class="frame-total">
        <div class="container">
            <h2 class="title">Общая информация</h2>
            <div class="frame-total-wrapper frame-wrapper">
                <div class="total-wrapper flex">
                   <table class="total-wrapper">
                        <tr>
                            <td class="text__key">ФИО</td>
                            <td class="text__value">{{user.name}}</td>
                        </tr>
                        <tr>
                            <td class="text__key">Номер телефона</td>
                            <td class="text__value">{{user.number}}</td>
                            
                        </tr>
                        <tr>
                            <td class="text__key">E-mail</td>
                            <td class="text__value">{{user.mail}}</td>

                        </tr>
                        <tr>
                            <td class="text__key">Город</td>
                            <td class="text__value">Уфа</td>
                        </tr>
                        <tr>
                            <td class="text__key">Организация</td>
                            <td class="text__value">ООО "Меги"</td>
                        </tr>
                        <tr>
                            <td class="text__key">Адрес</td>
                            <td class="text__value">Давлетшина 30</td>
                        </tr>
                        <tr>
                            <td class="text__key">Количество пациентов</td>
                            <td class="text__value">{{this.pacientCount}}</td>
                        </tr>
                        <tr>
                            <td class="text__key">Специалист</td>
                            <td class="text__value">Стоматолог,Хуелог</td>

                        </tr>
                        <tr>
                            <td class="text__key">Дата приема</td>
                            <td class="text__value">{{ this.dateObj.time }}</td>
                        </tr>
                        <tr>
                            <td class="text__key">Время приема</td>
                            <td class="text__value">{{ this.dateObj.date }}</td>
                        </tr>
                        <tr>
                            <td class="text__key">Стоимость</td>
                            <td class="text__value">ОООООООчень много</td>
                        </tr>
                    </table>
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
        pacientCount: {type: Number}
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