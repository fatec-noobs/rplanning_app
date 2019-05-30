<template>
  <div class="app">
    <header class="app__header">
      <navbar/>
    </header>
    <main class="app__content">
      <nuxt />
    </main>
    <footer class="footer">
      <div class="footer__container">
        <div class="container">
          <ul class="main-list">
            <li>Reparos, Reformas em instalações Elétrica e Industrial</li>
            <li>Manutenção preventiva em equipamentos elétricos</li>
            <li>Desenvolvimento de Projetos Elétricos</li>
          </ul>
        </div>
        <h3 class="title">Contate-nos agora e solicite uma visita técnica sem compromisso!</h3>
        <div class="footer__footer container">
          <ul class="brand-list">
            <li><i class="fab fa-instagram fa-2x"></i></li>
            <li><i class="fab fa-facebook-square fa-2x"></i></li>
            <li><i class="fab fa-twitter-square fa-2x"></i></li>
            <li><i class="fab fa-linkedin fa-2x"></i></li>
            <li><span>@rplanningservices</span></li>
          </ul>
          <a class="site" href="http://www.rplanning.com.br">www.rplanning.com.br</a>
          <ul class="contact-list">
            <li>
              <i class="fas fa-phone-square fa-2x"></i>
              <span>(12) 98141-9644</span>
            </li>
            <li>
              <i class="fab fa-whatsapp fa-2x"></i>
              <span>(12) 98119-7172</span>
            </li>
            <li>
              <i class="fas fa-envelope fa-2x"></i>
              <span>contato@rplanning.com.br</span>
            </li>
          </ul>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
import Navbar from '~/components/Navbar.vue'
import '@fortawesome/fontawesome-free/css/all.css'

export default {
  components: {
    Navbar
  }
}
</script>

<style>
html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
  Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  box-sizing: border-box;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

.app {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  justify-content: space-between;
}

.app__header {
  margin-bottom: 32px;
  box-shadow: 0 4px 8px 0 rgba(31, 45, 48, 0.24);
}

.app__content {
  flex-grow: 1;
}

.footer {
  background-color: #f8f9fa;
  margin-top: 16px;
}

.footer__container {
  padding: 16px 0;
}

.main-list {
  line-height: 2;
}

.title {
  background-color: #feb809;
  color: white;
  font-size: 1.8rem;
  padding: 16px;
  text-align: center;
}

.footer__footer {
  align-items: center;
  display: flex;
  justify-content: space-between;
  padding: 0 32px;
}

.brand-list {
  list-style: none;
  display: flex;
  padding-left: 0;
  margin-bottom: 0;
}

.brand-list li {
  align-items: center;
  display: flex;
  margin: 0 8px;
}

.brand-list span {
}

.contact-list {
  list-style: none;
  padding-left: 0;
  margin-bottom: 0;
}

.contact-list li {
  align-items: center;
  display: flex;
}

.contact-list i {
  margin-right: 8px;
}

.contact-list span {
}

.site {
  color: inherit;
  font-size: 1.3rem;
}
</style>
