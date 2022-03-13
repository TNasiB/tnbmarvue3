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
        height: 108px
        color: #fff
        align-items: center
        justify-content: space-between
    .logo-img
        background-image: url(../assets/img/logo.png)
        width: 32px
        height: 32px
        background-size: 32px
    .logo-name 
        max-width: 165px
        margin-left: 20px
    .tel 
        text-decoration: underline
</style>