<script setup>
    import { ref } from 'vue'
    import './style.scss'
</script>
<template>
    <footer class="footer">
        
        <div class="footer-menu">
            <div class="footer-top">
                <div class="nav__logo--footer">
                    <img src="@/assets/Header-img/Logo.png" alt="Image">
                    <p class="footer__text">Радовать людей - это наша работа</p>
                </div>
                <ul class="nav__list nav__list--footer">
                    <li><a href="#!">Политика безопасности</a></li>
                    <li><a href="#!">Контакты</a></li>
                    <li><a href="#!">Партнерам</a></li>
                </ul>
                <div class="footer-pay">
                    <a href="#" class="footer-pay__link">
                        <img src="@/assets/Footer-img/liqpay.svg" alt=""></a>
                    <a href="#" class="footer-pay__link">
                        <img src="@/assets/Footer-img/visa.svg" alt=""></a>
                    <a href="#" class="footer-pay__link">
                        <img src="@/assets/Footer-img/mastercard.svg" alt=""></a>
                </div>
            </div>
            <div class="footer-bottom">
                <div class="footer-socials">
                <a href="#" class="footer-socials__link">
                    <img src="@/assets/Footer-img/instagram.svg" alt=""></a>
                <a href="#" class="footer-socials__link">
                    <img src="@/assets/Footer-img/facebook.svg" alt=""></a>
                <a href="#" class="footer-socials__link">
                    <img src="@/assets/Footer-img/telegram.svg" alt=""></a>
                <a href="#" class="footer-socials__link">
                    <img src="@/assets/Footer-img/youtube.svg" alt=""></a>
                </div>
                <a href="#" class="footer-copyright">Дизайн сайта - Алексей Киселев</a>
        </div>
            
        </div>
    

</footer>
</template>