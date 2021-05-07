<template>
  <div id="site">
    <header>
      <div class="container">
        <div class="row">
          <div class="logo">
            <img src="~/assets/img/logo.svg" />
          </div>
        </div>
      </div>
    </header>

    <main>
      <div class="content">
        <div id="parallax">
          <div class="layer" data-depth="0.1">
            <img src="~/assets/img/logo.png" />
          </div>
          <div class="layer" data-depth="0.3">
            <img src="~/assets/img/legos_1.png" />
          </div>
          <div class="layer" data-depth="0.4">
            <img src="~/assets/img/legos_2.png" />
          </div>
          <div class="layer" data-depth="0.5">
            <img src="~/assets/img/legos_3.png" />
          </div>
          <div class="layer" data-depth="0.2">
            <div class="caption">
              <h1>Página em</h1>
              <h1>Reinvenção</h1>
            </div>
          </div>
        </div>
      </div>
    </main>

    <footer>
      <div class="container">
        <div class="row align-items-center">
          <div class="col-12 col-md-6">
            <a href="mailto:ola@agenciaterrua.com.br" target="_blank">
              <h6>ola@agenciaterrua.com.br</h6>
            </a>
            <p>
              SHN Q.2 Bl.F Ed.Executive Office Tower slj.58D<br />
              Brasília-DF Brasil CEP: 70702-000<br />
              +55 61 3033.7154
            </p>
            <p>
              SIG Quadra 1, Lotes 985/1055, Sala 103 - Asa Sul,<br />
              Brasília - DF Brasil CEP: 70610-410<br />
              +55 61 4042.8207
            </p>
          </div>
          <div class="col-12 col-md-6">
            <div class="social">
              <div class="social__item">
                <span> Assista ao nosso vídeo manisfesto </span>
                <a href="https://www.youtube.com/watch?v=gF-wV-YExis" target="_blank">
                  <div class="icon">
                    <img src="~/assets/img/social_youtube.svg" />
                  </div>
                </a>
              </div>

              <div class="social__item">
                <span> Siga-nos nas redes sociais </span>
                  <a href="https://www.facebook.com/AgenciaTerrua" target="_blank">
                    <div class="social__icon">
                      <img src="~/assets/img/social_facebook.svg" />
                    </div>
                  </a>
                  <a href="https://www.instagram.com/agenciaterrua/" target="_blank">
                    <div class="social__icon">
                      <img src="~/assets/img/social_instagram.svg" />
                    </div>
                  </a>
                  <a href="https://twitter.com/agenciaterrua" target="_blank">
                    <div class="social__icon">
                      <img src="~/assets/img/social_twitter.svg" />
                    </div>
                  </a>
                  <a href="https://www.linkedin.com/company/ag%C3%AAncia-terru%C3%A1/" target="_blank">
                    <div class="social__icon">
                      <img src="~/assets/img/social_linkedin.svg" />
                    </div>
                  </a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  methods: {
    startParallax() {
      var scene = document.getElementById("parallax");
      var parallaxInstance = new Parallax(scene);
    },
  },
  mounted() {
    this.startParallax();
  },
};
</script>

<style lang="scss">
header {
  position: fixed;
  top: 5vh;
  left: 0;
  width: 100%;
  .logo {
    max-width: 200px;
    @media screen and (max-width: 768px) {
      max-width: 160px;
    }
    img {
      width: 100%;
    }
  }
}
main {
  position: relative;
  width: 100vw;
  height: 100vh;
  overflow: hidden;
  .content {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    @media screen and (max-width: 768px) {
      top: 100px;
      transform: translate(-50%, 0);
    }
    #parallax {
      min-height: 460px;
      position: relative;
      overflow: hidden;
      .layer {
        width: 100%;
        height: 100%;
        @media screen and (max-width: 768px) {
          img {
            max-width: 460px;
          }
        }
        .caption {
          z-index: 10;
          position: absolute;
          top: 50%;
          right: 25px;
          transform: translateY(calc(-50% - 40px));
          @media screen and (max-width: 768px) {
            top: 50%;
            left: 50%;
            transform: translateX(-50%) translateY(0);
            right: auto;
            h1 {
              text-align: center;
            }
          }
          h1 {
            text-transform: uppercase;
            color: #FFF;
          }
        }
      }
    }
  }
}
footer {
  position: absolute;
  bottom: 5vh;
  left: 0;
  width: 100%;
  color: #fff;
  h6 {
    font-size: 0.9rem;
    font-weight: 500;
  }
  p {
    font-size: 0.8rem;
    font-weight: regular;
  }
  a {
    color: #FFF;
    transition: all .3s ease;
    &:hover {
      transform: scale(1.1);
    }
  }
  .social {
    display: flex;
    align-items: center;
    justify-content: flex-end;
    &__item {
      display: flex;
      align-items: center;
      &:first-of-type {
        margin-right: 12px;
        @media screen and (max-width: 768px) {
          margin-right: 0;
        }
      }
      span {
        margin-right: 10px;
        max-width: 60px;
        text-align: right;
        font-size: 11px;
        line-height: 12px;
        @media screen and (max-width: 768px) {
          margin-right: 5px;
        }
      }
    }
    &__icon {
      display: flex;
      align-items: center;
      justify-content: center;
      width: 34px;
      height: 34px;
      margin-right: 10px;
      border: 2px solid #fff;
      border-radius: 50%;
      text-align: center;
      img {
        width: 18px;
        height: 18px;
      }
    }
  }
}
</style>
