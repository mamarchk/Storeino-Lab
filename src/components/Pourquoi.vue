<template>
  <div id="pourquoi" class="container">
    <div class="pourquoi-sect">
      <h1 class="title">POURQUOI PARTICIPER</h1>
      <p class="raisons">3 RAISONS POUR PARTICIPER à cette compétition :</p>
      <div class="cards-container">
        <div class="card">
          <img src="../assets/img/card1.png" alt="card-img" />
          <div class="card-info">
            <h1 class="card-title">Concrétiser vos idées</h1>
            <p class="card-desc">
              Storeino/lab est une opportunité pour vous participer à concevoir
              et surtout proposer des solutions créatives.
            </p>
          </div>
        </div>
        <div class="card">
          <img src="../assets/img/card2.png" alt="card-img" />
          <div class="card-info">
            <h1 class="card-title">
              ACCÉDER au marketplace application de storeino
            </h1>
            <p class="card-desc">
              applications et plugins afin de les exposer et les rendre
              accessibles aux e-commerçants.
            </p>
          </div>
        </div>
        <div class="card">
          <img src="../assets/img/card3.png" alt="card-img" />
          <div class="card-info">
            <h1 class="card-title">
              Faire profiter d’un encadrement par des experts dans le domaine IT
            </h1>
            <p class="card-desc">
              pour développer vos applications et plugins afin de les exposer et
              les rendre accessibles aux e-commerçants.
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container {
  margin-top: 100px;
  margin-bottom: 60px;
}

.pourquoi-sect {
  text-align: center;
  width: 100%;
  max-width: 600px;
  margin: 0 auto;
}

.pourquoi-sect .title {
  font-size: 2.2rem;
  color: var(--cyanColor);
}

.pourquoi-sect .raisons {
  font-size: 16px;
  font-weight: 400;
  line-height: 30px;
}

.cards-container {
  margin-top: 20px;
  margin-bottom: 20px;
}

.card {
  display: flex;
  justify-content: space-around;
  align-items: center;
  box-shadow: 0px 0px 3px 0px rgba(0, 0, 0, 0.3);
  border-radius: 15px;
  margin-bottom: 15px;
  cursor: pointer;
  transition: 0.3s ease all;
}

.card:hover {
  box-shadow: 0px 0px 6px 0px rgba(0, 0, 0, 0.5);
}

.card img {
  padding: 5px;
  margin: 5px;
}

.card .card-title {
  font-size: 1.2rem;
}

@media (min-width: 920px) {
  .pourquoi-sect {
    max-width: 100%;
  }

  .pourquoi-sect .title {
    font-size: 2.6rem;
  }

  .pourquoi-sect .raisons {
    font-size: 20px;
    font-weight: 500;
  }

  .cards-container {
    display: flex;
    justify-content: space-between;
    gap: 20px;
  }

  .card {
    flex-direction: column;
    width: 400px;
    border-radius: 20px;
    margin-bottom: 0px;
  }
}
</style>
