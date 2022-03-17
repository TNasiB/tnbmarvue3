<template>
    <ul class="spec-list">
        <li class="spec-face">
            <div class="spec-title-wrapper flex">
                <p class="spec-type">{{ this.specialist.title }}</p>
                <button 
                class="radio"
                :class="{active: isActive}"
                @click="openSideSpecs"
                ></button>
            </div>
            <ul class="spec-list-name"
            :class="{open: isActive}">
                <DoctorComponent
                v-for="doctor in specialist.doctors"
                @add-doctor="addDoctor"
                :key="doctor.id"
                :doctor="doctor"
                :specialist="specialist"
                />
            </ul>
        </li>
    </ul>
    
</template>

<script>
import DoctorComponent from "./DoctorComponent.vue"

export default {
    data() {
        return {
            isActive: false,
            specAactive: false,            
        }
    },
    name: "Specialist-card",
    props: {
        specialist: {type: Object},
    },
    methods: {
        openSideSpecs() {
            this.isActive = !this.isActive
        },
        addDoctor(doctor) {
            this.$emit("add-doctor", doctor)
        }
    },
    components: {
        DoctorComponent
    }
}
</script>

<style>
.spec-list + .spec-list {
    margin-top: 20px;
}
.spec-item-name + .spec-item-name {
    margin-top: 20px;
}
.spec-item-name .radio{
    margin-right: 40px;
}
.spec-left {
    align-items: center;
}
.one-spec {
    align-items: center;
    justify-content: space-between;
}
.one-spec-info {
    color: #004D45;
    font-size: 16px;
    margin-left: 30px;
}
.spec-list-name {
    border: 2px solid #26A69A;
    padding: 15px;
    border-radius: 40px;
    margin-top: 10px;
    display: none;
}
.spec-list-name.open {
    display: block;
}
.spec-title-wrapper {
    color: #fff;
    font-size: 30px;
    padding: 15px;
    border-radius: 70px;
    background-color: #26A69A;
    align-items: center;
    justify-content: space-between;
}
</style>