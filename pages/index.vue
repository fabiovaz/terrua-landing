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
        </div>
      </div>
    </main>

    <footer>
      <div class="container">
        <div class="row">
          <div class="col-md-6">
            <h6>ola@agenciaterrua.com.br</h6>
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
          <div class="col-6">
            <div class="social">social</div>
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
    #parallax {
      min-height: 460px;
      position: relative;
      overflow: hidden;
      .layer {
        width: 100%;
        height: 100%;
        @media screen and (max-width: 768px) {
          img {
            max-width: 600px;
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
    font-weight: bold;
  }
  p {
    font-size: 0.8rem;
    font-weight: regular;
  }
}
</style>
