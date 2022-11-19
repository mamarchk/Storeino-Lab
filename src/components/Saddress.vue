<template>
  <div id="saddress" class="container">
    <div class="saddress-sect">
      <h1>À QUI S'ADRESSE</h1>
      <p class="desc">
        La Compétition <span class="special">STOREINO\LAB</span> est ouverte à
        tous les étudiants de L’université CADI AYYAD et Les établissements
        Privés reconnus par le ministère de L’Enseignement supérieur à
        Marrakech.
      </p>
      <p class="condition">
        Les candidats doivent être en mesure de faire une proposition à forte
        valeur ajoutée et avoir l’habilité à travailler en équipe en phase avec
        la thématique choisi dans le respect des délais de chaque phase du
        programme ,La participation est gratuite, il suffit de s’enregistrer.
      </p>
    </div>
  </div>
</template>

<style scoped>
.container {
  margin-top: 60px;
  margin-bottom: 60px;
}

.saddress-sect {
  text-align: center;
  width: 100%;
  max-width: 600px;
  margin: 0 auto;
}

.saddress-sect h1 {
  font-size: 2.2rem;
  color: var(--cyanColor);
}

.saddress-sect .desc {
  font-weight: bold;
}

.special {
  font-size: 18px;
  padding: 0 2px;
  color: var(--cyanColor);
}

.saddress-sect .condition {
  font-size: 16px;
  font-weight: 400;
  line-height: 30px;
}

@media (min-width: 920px) {
  .saddress-sect {
    max-width: 1000px;
  }

  .saddress-sect h1 {
    font-size: 2.6rem;
  }
  .saddress-sect .desc {
    font-size: 22px;
    max-width: 905px;
    margin-left: auto;
    margin-right: auto;
  }

  .special {
    font-size: 23px;
  }

  .saddress-sect .condition {
    font-size: 20px;
    max-width: 750px;
    margin-left: auto;
    margin-right: auto;
  }
}
</style>
