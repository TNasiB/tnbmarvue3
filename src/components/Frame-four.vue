<template>
    <div class="specialists">
        <div class="container">
            <div class="specialists__inner">
                <h2 class="title">Выберите специалистов</h2>
                
                <ul class="spec-list">
                    <li class="spec-face">
                        <div class="spec-title-wrapper flex">
                            <p class="spec-type">Стоматолог</p>
                            <button class="radio active"></button>
                        </div>
                        <ul class="spec-list-name">
                            <!-- Компонент -->
                            <li class="spec-item-name">
                                <div class="one-spec flex">
                                    <div class="flex spec-left">
                                        <img src="../assets/img/spec.png" alt="">
                                        <div class="one-spec-info">
                                            <p class="spec-name">Алексей Резенко</p>
                                            <p class="spec-exp">Стаж: 15 лет</p>
                                            <p class="spec-cost">40 гривен</p>
                                        </div>
                                    </div>
                                    <button class="radio"></button>
                                </div>
                            </li>
                            
                            <li class="spec-item-name">
                                <div class="one-spec flex">
                                    <div class="flex spec-left">
                                        <img src="../assets/img/spec.png" alt="">
                                        <div class="one-spec-info">
                                            <p class="spec-name">Алексей Резенко</p>
                                            <p class="spec-exp">Стаж: 15 лет</p>
                                            <p class="spec-cost">40 гривен</p>
                                        </div>
                                    </div>
                                    <button class="radio"></button>
                                </div>
                            </li>

                        </ul>
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<style scoped>
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
