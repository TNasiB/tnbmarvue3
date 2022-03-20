<template>
    <div class="frame-date">
        <div class="container">
            <div class="title">Выберите дату и время приема</div>
            <div class="frame-date-inner frame-wrapper">
                <div class="frame-date-wrapper">
                    <div class="frame-date-entry-wrapper flex">
                        <input 
                        type="date" 
                        data-placeholder="Дата" c
                        class="entry__date" 
                        value="----"
                        @input="setDate"
                        >

                        <input 
                        type="time" 
                        placeholder="Время" 
                        class="entry__time"
                        value="--:--"
                        @input="setDate">
                    </div>
                    <ul class="frame-date-list-price flex-column">
                        <div class="title price__title">Расчет стоимости:</div>
                        <li class="text__price">Количество пациентов: {{ pacientCount }}</li>
                        <li class="text__price">Количество специалистов: {{ activeSpecs.length }}</li>
                        <li 
                        class="text__price small"
                        v-for="doctor in activeSpecs"
                        :key="doctor.id"
                        > {{ doctor.title }} {{ doctor.cost * pacientCount }}₽</li>

                        <li class="text__price large">Итоговая стоимость: {{ cost }}₽</li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</template>


<script>
export default {
    name: "Frame-fiveth",
    methods: {
        setDate() {
            let date = document.querySelector(".entry__date"),
                time = document.querySelector(".entry__time"),
                dateObj = {
                    date: date.value,
                    time: time.value
                }
            this.$emit("set-time", dateObj)
        },
    },
    props: {
        pacientCount: {type: Number},
        activeSpecs: {type: Array},
        cost: {type: Number}
    }
}
</script>


<style>
.frame-date-entry-wrapper{
    justify-content: center;
}
.entry__date,.entry__time{
    width: 35%;
    height: 7vh;
    border: 3px solid #26A69A;
    box-sizing: border-box;
    border-radius: 50px;
    padding-left: 15px;
    font-family: 'Roboto';
    font-style: normal;
    font-weight: 700;
    font-size: 20px;
    line-height: 28px;
    color: #004D45;
}
.entry__date{
    margin-right: 10vw;
}
::-webkit-calendar-picker-indicator {
  background-image: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="16" height="15" viewBox="0 0 24 24"><path fill="%23004D45" d="M20 3h-1V1h-2v2H7V1H5v2H4c-1.1 0-2 .9-2 2v16c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zm0 18H4V8h16v13z"/></svg>');
}
input[type="date"]::-webkit-calendar-picker-indicator {
    margin-right: 10px !important; }
input[type="time"]::-webkit-calendar-picker-indicator {
    margin-right: 10px !important; }
.text__price{
    font-family: 'Roboto';
    list-style: disc;
    font-size: 24px;
    line-height: 46px;
    color: #004D45;
    margin-left: 3vw;

}
.text__price.small{
    font-size: 20px;
    margin-left: 6vw;
}
.text__price.large{
    font-size: 30px;
}
@media (max-width: 700px){
    .text__price.small{
        font-size: 18px;
    }
    .text__price.large{
        font-size: 23px;
    }
    .text__price{
        font-size: 20px;
    }
    .price__title{
        margin-bottom: 30px !important;
    }
    .frame-date-list-price{
        margin-top: 40px;
    }
    .entry__date,.entry__time{
        width: 300px;
    }
}

</style>