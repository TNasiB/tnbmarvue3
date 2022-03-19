<template>
<header>
    <div class="container">
        <div class="header flex">
            <div class="logo flex">
                <div class="logo-img"></div>
                <p class="logo-name">Медицинское обследование</p>
            </div>
            
            <a href="" class="tel">+7(917)739-11-29</a>
        </div>        
    </div>
</header>
</template>

<script>
export default {
    name: "HeaderNav"
}
</script>

<style scoped lang="sass">
    header
        background-color: #26A69A
    .header 
        height: 100px
        color: #fff
        align-items: center
        justify-content: space-between
    .logo
        align-items: center
    .logo-img
        background-image: url(../assets/img/logo.png)
        background-size: contain
        background-repeat: no-repeat
        width: 50px
        height: 50px
    .logo-name 
        max-width: 165px
        margin-left: 20px
        font-size: 30px
    .tel 
        text-decoration: underline
        text-decoration-skip-ink: none
        font-size: 30px
</style>