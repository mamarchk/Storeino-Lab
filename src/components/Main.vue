<template>
  <div class="container">
    <!-- About Section  -->
    <div id="about" class="hero">
      <div class="part">
        <h1>
          Storeino/lab
          <span class="storeino">Competition de Programmation</span>
          <span> By Storeino</span>
        </h1>
        <p class="part-info">
          Storeino/lab est une compétition de programmation d’apprentissage et
          de concurrence ,c'est une opportunité pour les étudiants passionnés
          par la programmation afin de tester leurs capacités et découvrir les
          nouvelles technologies dans une atmosphère créative et bénéficier d'un
          encadrement par des professionnels dans le domaine.
        </p>
      </div>
      <button class="btn-about">INSCRIVEZ-VOUS</button>
    </div>
    <!-- address Section  -->
    <div id="sadress" class="conntent-wrapper">
      <div class="contentsadress">
        <h1>À QUI S ADRESSE Storeino/lab ?</h1>
      </div>
      <h4>
        la compétition STOREINOLAB est ouverte à tous les étudiants de l
        université CADI AYYAD et les établissements privés reconnus par le
        ministère de l'Enseignement supérieur à Marrakech .
      </h4>
      <p class="adressspr">
        Les candidats doivent être en mesure de faire une proposition à forte
        valeur ajoutée et avoir l’habilité à travailler en équipe en phase avec
        la thématique choisi dans le respect des délais de chaque phase du
        programme ,La participation est gratuite, il suffit de s’enregistrer.
      </p>
    </div>
    <!-- prq services -->
    <div id="prq" class="conntent-wrapper">
      <div class="conntent-prq">
        <h3>POURQUOI PARTICIPER à Storeino/lab ?</h3>
        <p>3 RAISONS POUR PARTICIPER à cette compétition :</p>
      </div>
      <!-- card - prq services  -->
      <div class="card-wrapper">
        <div class="card" style="width: 18rem">
          <img class="card-img-top" src="..." alt="Card image cap" />
          <div class="card-body">
            <h4>Concrétiser vos idées</h4>
            <p class="card-text">
              Storeino/lab est une opportunité pour vous participer à concevoir
              et surtout proposer des solutions créatives.
            </p>
          </div>
        </div>
        <div class="card" style="width: 18rem">
          <img class="card-img-top" src="..." alt="Card image cap" />
          <div class="card-body">
            <h4>ACCÉDER au marketplace application de storeino</h4>
            <p class="card-text">
              pour développer vos applications et plugins afin de les exposer et
              les rendre accessibles aux e-commerçants.
            </p>
          </div>
        </div>
        <div class="card" style="width: 18rem">
          <img class="card-img-top" src="..." alt="Card image cap" />
          <div class="card-body">
            <h4>
              faire profiter d’un encadrement par des experts dans le domaine IT
            </h4>
            <p class="card-text">
              Améliorer vos compétences par l’encadrement de nos experts plus de
              15 ans dans le domaine de développement informatique .
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container {
  padding: 20px;
}

.part {
  width: 400px;
}

.part h1 {
  color: #33ccfc;
  font-family: "TT Norms";
  text-align: center;
  font-size: 30px;
  font-weight: 700;
  line-height: 1.071;
}
.part .storeino {
  font-size: 30px;
  font-weight: 500;
  color: #00536d;
  text-transform: uppercase;
  font-family: "TT Norms";
}

.part-info {
  text-align: center;
}
.conntent-wrapper {
  text-align: center;
}

.card {
  text-align: center;
}
</style>
