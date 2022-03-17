<template>

<li class="spec-item-name">
    <div class="one-spec flex">
        <div class="flex spec-left">
            <img src="../assets/img/spec.png" alt="">
            <div class="one-spec-info">
                <p class="spec-name">{{ doctor.name }}</p>
                <p class="spec-exp">Стаж: {{ doctor.experience }} лет</p>
                <p class="spec-cost">{{ doctor.cost }} рублей</p>
            </div>
        </div>
        <label>
            <input 
            class="radio-original" 
            type="radio" 
            :name="specialist.title"
            @click="addDoctor"
            >
            <span class="radio-fake"></span>
        </label>
    </div>
</li>

</template>

<script>
export default {
    name: "DoctorComponent",
    props: {
        doctor: {type: Object},
        specialist: {type: Object},
    },
    methods: {
        addDoctor() {
            this.$emit("add-doctor", this.doctor)
        }
    }
}
</script>

<style scoped>
.radio-original {
    display: none;
}
.radio-fake {
    display: block;
    border-radius: 50%;
    width: 36px;
    height: 36px;
    border: 5px solid #fff;
    background-color: #fff;
    box-shadow: 0px 0px 3px #000;
    cursor: pointer;
    position: relative;
}
.radio-fake::before {
    content: "";
    position: absolute;
    background-color: #75D7CD;
    width: 27px;
    height: 27px;
    border-radius: 50%;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    opacity: 0;
    transition: opacity .2s;
}
.radio-original:checked + .radio-fake::before {
    opacity: 1;
}
</style>