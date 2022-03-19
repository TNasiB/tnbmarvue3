<template>
    <div class="frame-total">
        <div class="container">
            <h2 class="title" @click="test">Общая информация</h2>
            <div class="frame-total-wrapper frame-wrapper">
                <form class="total-wrapper" ref="form"  @submit.prevent="sendEmail">
                    <tr>
                        <td class="text__key" @click="test">ФИО</td>
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
                        <td class="text__key">Организация</td>
                        <td class="text__value">{{organization.name}}</td>
                    </tr>
                    <tr>
                        <td class="text__key">Адрес</td>
                        <td class="text__value">{{organization.address}}</td>
                    </tr>
                    <tr>
                        <td class="text__key">Количество пациентов</td>
                        <td class="text__value">{{this.pacientCount}}</td>
                    </tr>
                    <tr>
                        <td class="text__key">Специалист</td>
                        <td class="text__value">
                            <span 
                            v-for="activeSpec in activeSpecs"
                            :key="activeSpec.id"
                            >{{ activeSpec.title }}, </span>
                        </td>

                    </tr>
                    <tr>
                        <td class="text__key">Дата приема</td>
                        <td class="text__value">{{ this.dateObj.date }}</td>
                    </tr>
                    <tr>
                        <td class="text__key">Время приема</td>
                        <td class="text__value">{{ this.dateObj.time }}</td>
                    </tr>
                    <tr>
                        <td class="text__key">Стоимость</td>
                        <td class="text__value">{{ cost }}₽</td>
                    </tr>
                </form>
                <button class="form-total__button" @click="sendEmail"  :class="{red:!isCorrect, none:isButton}" >Записаться на прием</button>
                <div class="form-total__button request__button"    :class="{none:!isButton}">Заявка принята</div>
            </div>
        </div>
    </div>
</template>
<script>
import emailjs from '@emailjs/browser';

export default {
    name: "Frame-sixth",
    data(){
        return{
           templateParams:{},
           isCorrect:true,
           isButton:false,
        }
    },
    props: {
        user: {type: Object},
        pacientCount: {type: Number},
        dateObj: {type: Object},
        organization:{type:Object},
        activeSpecs: {type: Array},
        cost: {type: Number},
        
    },
    methods:{ 
        sendEmail() {
                let activeSpecsStr = ""
                for (let i = 0; i < this.activeSpecs.length; i++) {
                    if (activeSpecsStr == "") {
                        activeSpecsStr += this.activeSpecs[i].title
                    } else {
                        activeSpecsStr += `, ${this.activeSpecs[i].title}`
                    }
                }
                if(activeSpecsStr!='' && typeof this.user.name=='string' && typeof this.user.number=='string' && typeof this.user.mail=='string' && 
                    typeof this.organization.name=='string'&& typeof this.organization.address=='string' && typeof this.pacientCount=='number'
                && typeof this.dateObj.date=='string' && typeof this.dateObj.time=='string' && typeof this.cost=='number')
                {
                    let templateParams = {
                    name: this.user.name,
                    email:this.user.mail,
                    number: this.user.number,
                    company_name: this.organization.name,
                    company_address: this.organization.address,
                    pacient_count: this.pacientCount,
                    spec: activeSpecsStr,
                    date: this.dateObj.date,
                    time: this.dateObj.time,
                    price: this.cost,
                    
                    };
                    emailjs.send("service_cw02kwz","template_k987aii",templateParams,'0Rkinjq86HfyK6vb5')
                    .then((result) => {
                        console.log('SUCCESS!', result.text);
                    }, (error) => {
                        console.log('FAILED...', error.text);
                    });
                    this.isCorrect=true
                    this.isButton=true
                   
                }    

                else{

                this.isCorrect=false

                }
              
              
        }
    }
}
</script>


<style>
.request__button{
    line-height: 7vh !important;
    background-color:#004D45 !important;
}
.none{
    display: none;
}
.red{
    background: red !important;
}
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