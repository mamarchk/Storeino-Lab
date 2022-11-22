<template>
  <div class="sect-wrapper">
    <div class="container">
      <ul class="links">
        <li>
          <a href="#a-propos">à PROPOS</a>
        </li>
        <li>
          <a href="#saddress">À QUI S’ADRESSE ? </a>
        </li>
        <li>
          <a href="#pourquoi">POURQUOI PARTICIPER </a>
        </li>
        <li>
          <a href="#thematiques">les thématiques de la compétition </a>
        </li>
        <li>
          <a href="#programme">le programme de la compétition </a>
        </li>
        <li>
          <a href="#prix">les Prix de la compétition </a>
        </li>
        <li>
          <a href="#inscrivez-vous">INSCRIVEZ-VOUS </a>
        </li>
      </ul>
      <div class="img-container">
        <a href="#">
          <img
            class="storeino-lab"
            src="../assets/img/Frame.png"
            alt="storeino\lab"
          />
        </a>
      </div>
    </div>
  </div>
</template>

<style scoped>
.sect-wrapper {
  background-color: #1e2e72;
}

.container {
  margin-top: 60px;
  padding-top: 20px;
}

.links {
  display: flex;
  flex-direction: column;
  text-align: center;
  padding: 0;
}

.links li {
  list-style: none;
  padding: 10px;
}

.links li a {
  color: #fff;
  text-decoration: none;
  text-transform: uppercase;
  font-size: 16px;
  transition: 0.3s ease all;
}

.links li a:hover {
  border-bottom: 1px #fdfdfd solid;
}

.img-container {
  text-align: center;
}
.storeino-lab {
  width: 80px;
  cursor: pointer;
}

@media (min-width: 920px) {
  .container {
    padding: 20px;
    display: flex;
    justify-content: space-around;
    align-items: center;
  }

  .storeino-lab {
    width: 200px;
    cursor: pointer;
  }

  .links li a {
    font-size: 18px;
  }
}
</style>
