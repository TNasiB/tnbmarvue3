<template>
    <div class="specialists">
        <div class="container">
            <h2 class="title">Выберите специалистов</h2>
            <div class="specialists__inner frame-wrapper">
                <SpecialistCard 
                v-for="specialist in specialists"
                :key="specialist.id"
                :specialist="specialist"
                @add-doctor="addDoctor"
                />
            </div>
        </div>
    </div>
</template>

<script>
import SpecialistCard from "./Specialist-card"

export default {
    name: "Frame-four",
    components: {
        SpecialistCard,
    },
    methods: {
        addDoctor(doctor) {
            this.$emit("add-doctor", doctor)
        }
    },
    props: {
        specialists: {type: Array},
    }
}
</script>


<style>

</style>
