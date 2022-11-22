<template>
  <div class="container">
    <div id="programme" class="programme-sect">
      <h1>le programme de la compétition</h1>
      <div class="prog-content">
        <div class="stars-container">
          <div class="star">
            <img src="../assets/img/programme/Star.png" alt="star" />
            <p>
              l’inscription à la compétition du 24 novembre jusqu’au 30 novembre
              2022
            </p>
          </div>
          <div class="star">
            <img src="../assets/img/programme/Star.png" alt="star" />
            <p>
              la présélection des candidats du 01 décembre jusqu'au 31 décembre
              2022
            </p>
          </div>
          <div class="star">
            <img src="../assets/img/programme/Star.png" alt="star" />
            <p>
              la formation sur marketplace STOREINO et les thématiques du 2
              janvier jusqu'au 8 janvier 2022
            </p>
          </div>
          <div class="star">
            <img src="../assets/img/programme/Star.png" alt="star" />
            <p>
              la répartition des groupes et thématiques du 9 janvier jusqu’au 15
              janvier 2022
            </p>
          </div>
          <div class="star">
            <img src="../assets/img/programme/Star.png" alt="star" />
            <p>
              le suivi du 16 janvier jusqu’au 16 mars Announcement des résultats
              le 17 mars 2022
            </p>
          </div>
        </div>
        <img class="dev" src="../assets/img/programme/dev.png" alt="dev" />
      </div>
    </div>
  </div>
</template>

<style scoped>
.container {
  margin-top: 60px;
  margin-bottom: 60px;
}

.programme-sect {
  text-align: center;
  width: 100%;
  max-width: 600px;
  margin: 0 auto;
}

.programme-sect h1 {
  font-size: 2rem;
  text-transform: uppercase;
  color: var(--cyanColor);
  margin-bottom: 60px;
}

.star {
  display: flex;
  align-items: center;
  gap: 15px;
}

.star p {
  font-size: 16px;
  font-weight: 400;
  line-height: 30px;
}

.dev {
  display: none;
}

@media (min-width: 920px) {
  .programme-sect {
    text-align: center;
    width: 100%;
    max-width: 100%;
  }
  .prog-content {
    display: flex;
    justify-content: space-around;
    align-items: center;
    gap: 20px;
  }

  .stars-container {
    width: 600px;
  }

  .programme-sect h1 {
    font-size: 2.6rem;
  }

  .star {
    gap: 20px;
  }

  .star p {
    font-size: 20px;
  }

  .dev {
    display: block;
    width: 400px;
  }
}
</style>
