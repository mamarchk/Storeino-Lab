<template>
  <div class="bg-wrapper">
    <div class="container">
      <div id="prix" class="prix-sect">
        <h1>les Prix de la compétition</h1>
        <p class="desc">Le prix pour le premier groupe gagnant :</p>
        <div class="prix-content">
          <div class="stars-container">
            <div class="star">
              <img src="../assets/img/Prix/star.png" alt="star" />
              <p>Intégration de l'application réalisée</p>
            </div>
            <div class="star">
              <img src="../assets/img/Prix/star.png" alt="star" />
              <p>
                Vidéo promotionnelle pour promouvoir l'application sur nos
                canaux, la partager avec nos clients et la mettre en Dashboard
                interne de la plateforme Storeino
              </p>
            </div>
            <div class="star">
              <img src="../assets/img/Prix/star.png" alt="star" />
              <p>Intégration de libellé recommandé pour l'application</p>
            </div>
          </div>
          <img
            class="trophy"
            src="../assets/img/Prix/trophy-removebg-preview.png"
            alt="dev"
          />
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
  padding-top: 30px;
  padding-bottom: 50px;
}

.prix-sect {
  text-align: center;
  width: 100%;
  max-width: 600px;
  margin: 0 auto;
  color: #fff;
}

.prix-sect h1 {
  font-size: 2rem;
  text-transform: uppercase;
  color: #fff;
  margin-bottom: 20px;
}

.desc {
  font-size: 17px;
  font-weight: 300;
  margin-bottom: 30px;
}

.star {
  display: flex;
  align-items: center;
  gap: 15px;
  text-align: left;
}

.star img {
  width: 25px;
}

.star p {
  font-size: 16px;
  font-weight: 400;
  line-height: 30px;
}

.trophy {
  display: none;
}

@media (min-width: 920px) {
  .prix-sect {
    text-align: center;
    width: 100%;
    max-width: 100%;
  }
  .prix-content {
    display: flex;
    justify-content: space-around;
    align-items: center;
    gap: 20px;
  }

  .stars-container {
    width: 600px;
  }

  .prix-sect h1 {
    font-size: 2.6rem;
  }

  .desc {
    font-size: 18px;
    font-weight: 400;
    margin-bottom: 35px;
  }

  .star {
    gap: 20px;
  }

  .star p {
    font-size: 20px;
  }

  .trophy {
    display: block;
    width: 500px;
  }
}
</style>
