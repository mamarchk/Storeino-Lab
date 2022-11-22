<template>
  <div class="container">
    <div class="about">
      <div class="wrapper-wrapper">
        <div class="wrapper">
          <h1>
            <span class="unique">Storeino\LAB</span>
            <span class="comp"
              >Competition de programmation <span class="by">By</span></span
            >
            <div class="imgs-wrapper">
              <img
                class="storeino-logo desktop"
                src="../assets/img/logo-desktop-01.svg"
                alt="storeino"
              />
              <img
                class="storeino-logo mobile"
                src="../assets/img/logo-mobile-01.svg"
                alt="storeino"
              />
            </div>
          </h1>

          <div class="bg-img">
            <img src="../assets/img/Mask-group.png" alt="" />
          </div>

          <a href="#inscrivez-vous" class="about-btn">INSCRIVEZ-VOUS</a>
          <div class="aprp" id="a-propos"></div>
          <div class="about-info">
            <h3>à PROPOS</h3>
            <p>
              Storeino/lab est une compétition de programmation d’apprentissage
              et de concurrence ,c'est une opportunité pour les étudiants
              passionnés par la programmation afin de tester leurs capacités et
              découvrir les nouvelles technologies dans une atmosphère créative
              et bénéficier d'un encadrement par des professionnels dans le
              domaine.
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="apropos-section-bg">
    <div class="container">
      <div class="wrapper-desktop">
        <h3>à PROPOS</h3>
        <p class="about-info-desktop">
          Storeino/lab est une compétition de programmation d’apprentissage et
          de concurrence ,c'est une opportunité pour les étudiants passionnés
          par la programmation afin de tester leurs capacités et découvrir les
          nouvelles technologies dans une atmosphère créative et bénéficier d'un
          encadrement par des professionnels dans le domaine.
        </p>
      </div>
      <img src="../assets/img/Frame.png" alt="" />
    </div>
  </div>
</template>

<style scoped>
.about {
  margin-top: 60px;
  text-align: center;
}

.aprp {
  margin-top: 20px;
}

.about h1 {
  margin-bottom: 0;
}

.about .comp {
  text-transform: uppercase;
}

.unique {
  display: block;
  font-size: 1.5rem;
  color: var(--cyanColor);
}

.comp {
  font-size: 1.8rem;
  color: var(--blueColor);
}

.by {
  display: block;
}

.storeino-logo {
  width: 150px;
  padding-bottom: 15px;
}

.about-info {
  text-align: center;
  font-size: 14px;
  width: 100%;
  max-width: 500px;
  margin-left: auto;
  margin-right: auto;
}

.about-info h3 {
  margin-bottom: 10px;
  font-size: 2.2rem;
  color: var(--cyanColor);
  text-transform: uppercase;
  text-align: center;
}

.about-info p {
  font-size: 16px;
  font-weight: 400;
  text-align: center;
  line-height: 30px;
}

.about-btn {
  /* margin-top: 20px;
  margin-bottom: 20px; */
  border: none;
  color: #fff;
  font-weight: 500;
  letter-spacing: 1.1px;
  text-decoration: none;
  cursor: pointer;
  background-color: var(--cyanColor);
  padding: 15px 20px;
  border-radius: 30px;
  font-size: 14px;
  transition: 0.5s ease all;
}

.about-btn:hover {
  color: #f5f5f5;
  background-color: var(--blueColor);
}

.desktop {
  display: none;
}
.bg-img {
  display: none;
}

.apropos-section-bg {
  display: none;
}

@media (min-width: 1200px) {
  .container {
    position: relative;
  }

  .about {
    height: 470px;
    margin-top: 0;
    text-align: left;
  }

  .wrapper-wrapper {
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: flex-start;
    align-items: center;
    text-align: center;
  }

  .about h1 {
    width: 500px;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
  }

  .imgs-wrapper {
    display: flex;
    justify-content: center;
  }

  .about-info {
    display: none;
  }

  .desktop {
    display: block;
    width: 200px;
    padding-bottom: 15px;
  }

  .mobile {
    display: none;
  }
  .comp {
    font-size: 2.8rem;
    color: var(--blueColor);
  }

  .unique {
    font-size: 2.6rem;
    color: var(--cyanColor);
  }

  .by {
    display: block;
  }

  .bg-img {
    display: block;
    position: absolute;
    top: -130px;
    right: -5px;
    z-index: -999;
  }

  .bg-img img {
    height: 600px;
    width: 100%;
  }

  .apropos-section-bg {
    display: block;
    background-color: #1e2e72;
  }

  .apropos-section-bg .container {
    display: flex;
    justify-content: space-around;
    align-items: center;
    padding: 20px;
    color: #fff;
  }
  .apropos-section-bg .container .wrapper-desktop {
    width: 450px;
    padding: 20px 0;
  }

  .apropos-section-bg .container .wrapper-desktop h3 {
    font-size: 2.6rem;
    text-transform: uppercase;
    text-align: center;
  }

  .apropos-section-bg .container .wrapper-desktop p {
    font-size: 20px;
    font-weight: 300;
    text-align: center;
    line-height: 30px;
  }

  .apropos-section-bg .container img {
    width: 300px;
  }

  .storeino-logo.desktop {
    margin-bottom: 20px;
  }
}
</style>
