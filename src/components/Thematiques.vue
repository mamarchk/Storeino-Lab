<template>
  <div class="bg-wrapper">
    <div class="container">
      <div id="thematiques" class="thematiques-sect">
        <h1>les thématiques de la compétition</h1>
        <div class="thematiques-container">
          <div class="thematique">
            <p>Solutions d’automatisation des flow</p>
            <img
              class="number left"
              src="../assets/img/thematiques/thematique-1.png"
              alt="number"
            />
          </div>
          <div class="thematique">
            <p>Solutions CRM</p>
            <img
              class="number right"
              src="../assets/img/thematiques/thematique-2.png"
              alt="number"
            />
          </div>
          <div class="thematique">
            <p>solutions Marketing et prospection</p>
            <img
              class="number left"
              src="../assets/img/thematiques/thematique-3.png"
              alt="number"
            />
          </div>
          <div class="thematique">
            <p>Solutions de fidélisation des clients</p>
            <img
              class="number right"
              src="../assets/img/thematiques/thematique-4.png"
              alt="number"
            />
          </div>
          <div class="thematique">
            <p>Tracking and analytics tools</p>
            <img
              class="number left"
              src="../assets/img/thematiques/thematique-5.png"
              alt="number"
            />
          </div>
          <div class="thematique">
            <p>Reporting tools</p>
            <img
              class="number right"
              src="../assets/img/thematiques/thematique-6.png"
              alt="number"
            />
          </div>
          <div class="thematique">
            <p>Shipping and delivery Solutions</p>
            <img
              class="number left"
              src="../assets/img/thematiques/thematique-7.png"
              alt="number"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.bg-wrapper {
  background-color: #1e2e72;
}

.container {
  margin-top: 60px;
  margin-bottom: 60px;
  padding-top: 40px;
  padding-bottom: 40px;
}

.thematiques-sect {
  text-align: center;
  width: 100%;
  max-width: 600px;
  margin: 0 auto;
}

.thematiques-sect h1 {
  margin-bottom: 45px;
  text-transform: uppercase;
  font-size: 2rem;
  color: #fff;
}

.thematique {
  background: #eee;
  padding: 20px 10px;
  position: relative;
  margin-top: 50px;
  margin-bottom: 50px;
}

.thematique p {
  margin: 0;
  margin-top: 20px;
}

.number {
  position: absolute;
  top: 0%;
  left: 50%;
  transform: translate(-50%, -50%);
}

@media (min-width: 920px) {
  .thematiques-sect h1 {
    font-size: 2.6rem;
  }

  .thematique p {
    font-size: 20px;
  }

  .number {
    top: 50%;
  }

  .number.left {
    left: 8.5px;
  }

  .number.right {
    left: 592px;
  }
  .thematique p {
    margin: 0;
  }
}
</style>
