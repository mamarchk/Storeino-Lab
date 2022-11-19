<script setup>
import { ref } from "vue";

const nom = ref("");
const prenom = ref("");
const sexe = ref("");
const adresseMail = ref("");
const age = ref("");
const anneeScolaire = ref("");
const langageMaitrise = ref("");
const techStack = ref("");
const specialite = ref([]);
const softSkills = ref("");

const formErrors = ref([]);
const maxChars = ref(15);

const validateForm = (e) => {
  formErrors.value = [];

  if (!sexe.value) {
    formErrors.value.push("sexe field cant be empty");
  } else if (!nom.value) {
    formErrors.value.push("Nom field cant be empty");
  } else if (nom.value.length > maxChars.value) {
    formErrors.value.push(`nom should be less than ${maxChars.value} char`);
  } else if (!prenom.value) {
    formErrors.value.push("Prenom field cant be empty");
  } else if (prenom.value.length > maxChars.value) {
    formErrors.value.push(`Prenom should be less than ${maxChars.value} char`);
  } else if (!adresseMail.value) {
    formErrors.value.push("Adresse mail field cant be empty");
  } else if (!age.value) {
    formErrors.value.push("Age field cant be empty");
  } else if (age.value > 60) {
    formErrors.value.push("Age should be less than 60");
  } else if (age.value < 17) {
    formErrors.value.push("Age should be atleast 17");
  } else if (!anneeScolaire.value) {
    formErrors.value.push("Année Scolaire field cant be empty");
  } else if (!langageMaitrise.value) {
    formErrors.value.push("Langage maîtrisée field cant be empty");
  } else if (!techStack.value) {
    formErrors.value.push("Tech stack maîtrisée field cant be empty");
  } else if (!specialite.value.length) {
    formErrors.value.push("Spécialité field cant be empty");
  } else if (!softSkills.value) {
    formErrors.value.push("Soft Skills field cant be empty");
  }

  if (!formErrors.value.length) {
    // submited();
    return true;
  }

  e.preventDefault();
};

/* submite */
function submited() {
  console.log("nom : " + nom.value);
  console.log("prenom : " + prenom.value);
  console.log("sexe : " + sexe.value);
  console.log("email : " + adresseMail.value);
  console.log("age : " + age.value);
  console.log("annee scolaire : " + anneeScolaire.value);
  console.log("langage maitrisee : " + langageMaitrise.value);
  console.log("tech stack : " + techStack.value);
  console.log("specialite : " + specialite.value);
  console.log("soft skills : " + softSkills.value);
  nom.value = "";
  prenom.value = "";
  sexe.value = "";
  adresseMail.value = "";
  age.value = "";
  anneeScolaire.value = "";
  langageMaitrise.value = "";
  techStack.value = [];
  specialite.value = [];
  softSkills.value = "";
}
</script>

<template>
  <div class="container">
    <div id="inscrivez-vous" class="formulaire-sect">
      <h1 class="title">INSCRIVEZ-VOUS</h1>
      <p class="desc">Formulaire d’inscription :</p>
      <form @submit="validateForm" action="./db.sql" method="post">
        <!-- errors -->
        <div v-if="formErrors" class="errors-list">
          <div class="error" v-for="(error, index) in formErrors" :key="index">
            {{ error }}
          </div>
        </div>

        <!-- form-container -->
        <div class="form-group">
          <!-- sexe -->
          <div class="sexe sect">
            <label class="sexe-title label-title req">Sexe</label>
            <div class="sexe-wrapper">
              <div class="homme">
                <input
                  type="radio"
                  name="sexe"
                  id="homme"
                  v-model="sexe"
                  value="homme"
                />
                <label for="homme">Homme</label>
              </div>
              <div class="femme">
                <input
                  type="radio"
                  name="sexe"
                  id="femme"
                  v-model="sexe"
                  value="femme"
                />
                <label for="femme">Femme</label>
              </div>
            </div>
          </div>

          <!-- nom -->
          <div class="nom sect">
            <label class="nom-title label-title req" for="nom">Nom</label>
            <input v-model.trim="nom" type="text" id="nom" placeholder="Nom" />
          </div>

          <!-- prenom -->
          <div class="prenom sect">
            <label for="prenom" class="req label-title">Prenom</label>
            <input
              v-model.trim="prenom"
              type="text"
              id="prenom"
              placeholder="Prenom"
            />
          </div>

          <!-- adresse mail -->
          <div class="mail sect">
            <label for="mail" class="req label-title">Adresse mail</label>
            <input
              v-model.trim="adresseMail"
              type="email"
              id="mail"
              placeholder="Adresse mail"
            />
          </div>

          <!-- age -->
          <div class="age sect">
            <label for="age" class="req">Age</label>
            <input v-model="age" class="age-inp" type="number" id="age" />
            ans
          </div>

          <!-- annee scolaire -->
          <div class="annee-scolaire sect">
            <label for="annee-scolaire" class="req">Année</label>
            <select
              class="annee-inp"
              name="annne-scolaire"
              id="anne-scolaire"
              v-model="anneeScolaire"
            >
              <option value="2021">2021</option>
              <option value="2022">2022</option>
              <option value="2023">2023</option>
              <option value="2024">2024</option>
              <option value="2025">2025</option>
              <option value="2026">2026</option>
            </select>
          </div>

          <!-- Langage maîtrisée -->
          <div class="langage-maitrise sect">
            <label for="langage" class="label-title req"
              >Langage maîtrisée</label
            >
            <input
              v-model.trim="langageMaitrise"
              type="text"
              id="langage"
              placeholder="Langage maîtrisée"
            />
          </div>

          <!-- Tech stack maîtrisée -->
          <div class="tech-stack sect">
            <label for="stack" class="label-title req"
              >Tech stack maîtrisée</label
            >
            <input
              v-model.trim="techStack"
              type="text"
              id="stack"
              placeholder="Tech stack maîtrisée"
            />
          </div>

          <!-- Spécialité -->
          <div class="specialite sect">
            <label class="label-title req">Spécialité</label>
            <div class="sps">
              <div class="front-end">
                <input
                  v-model="specialite"
                  type="checkbox"
                  value="front-end"
                  name="front-end"
                  id="front-end"
                />
                <label class="front-end-label" for="front-end">Front-End</label>
              </div>
              <div class="back-end">
                <input
                  v-model="specialite"
                  type="checkbox"
                  value="back-end"
                  name="back-end"
                  id="back-end"
                />
                <label class="back-end-label" for="back-end">Back-End</label>
              </div>
              <div class="data-base">
                <input
                  v-model="specialite"
                  type="checkbox"
                  value="database"
                  name="data-base"
                  id="data-base"
                />
                <label class="data-base-label" for="data-base">DataBase</label>
              </div>
            </div>
          </div>

          <!-- soft skills -->
          <div class="soft-skills sect">
            <label for="soft-skills " class="label-title req"
              >Soft Skills</label
            >
            <textarea
              v-model.trim="softSkills"
              class="soft-skills-inp"
              id="soft-skills"
              placeholder="ex: Probleme-Solving, self-learning, ... "
            />
          </div>
        </div>
        <div class="btn-container">
          <input class="btn" type="submit" value="s'inscrire" />
        </div>
      </form>
    </div>
  </div>
</template>

<style scoped>
.container {
  margin-top: 100px;
}

.formulaire-sect {
  text-align: left;
  width: 100%;
  max-width: 600px;
  margin: 0 auto;
}

.formulaire-sect .title,
.formulaire-sect .desc {
  text-align: center;
}

.title {
  font-size: 2.2rem;
  color: var(--cyanColor);
}

.desc {
  font-size: 16px;
  font-weight: 500;
  line-height: 30px;
}

.sect {
  margin-bottom: 30px;
  width: 85%;
  margin-left: auto;
  margin-right: auto;
  accent-color: var(--cyanColor);
}

input {
  padding: 10px;
  background: #eee;
  border: none;
  border-radius: 5px;
  font-size: 14px;
  color: var(--blueColor);
  font-family: "Poppins", sans-serif;
}

.label-title {
  margin-bottom: 5px;
  display: block;
}

.req::after {
  content: "*";
  color: red;
}

/* Nom + prenom + mail + langage-maitrise + tech-stack */
.nom,
.prenom,
.mail,
.langage-maitrise,
.tech-stack,
.soft-skills {
  display: flex;
  flex-direction: column;
}

/* sexe */
.sexe .sexe-title {
  margin-bottom: 5px;
  display: block;
}
.sexe .sexe-wrapper {
  display: flex;
  gap: 15px;
}

/* age + annne-scolaire  */
.age-inp,
.annee-inp {
  margin: 0 15px;
  font-weight: bold;
}

/* age-input */
.age-inp {
  text-align: center;
  width: 60px;
}

/* annee-scolaire */
.annee-inp {
  background: #eee;
  color: var(--blueColor);
  font-size: 14px;
  border: none;
  border-radius: 5px;
  padding: 8px;
}

/* specialite */
.front-end-label,
.back-end-label,
.data-base-label {
  margin-left: 10px;
}

/* soft skills */
.soft-skills-inp {
  background: #eee;
  border: none;
  min-height: 100px;
  padding: 5px;
  resize: vertical;
  color: var(--blueColor);
  font-family: "Poppins", sans-serif;
  font-size: 14px;
}

/* submite input */
.btn-container {
  text-align: center;
  margin: 10px 0 15px 0;
}

.btn {
  border: none;
  color: #fff;
  font-size: 0.8;
  font-weight: bold;
  letter-spacing: 1.5px;
  cursor: pointer;
  background-color: var(--cyanColor);
  padding: 10px 20px;
  border-radius: 30px;
  text-transform: uppercase;
  transition: 0.5s ease all;
}

.btn:hover {
  background-color: var(--blueColor);
}

.error {
  background: rgba(250, 0, 0, 0.3);
  color: red;
  font-weight: bold;
  text-align: center;
  border-radius: 5px;
  width: 80%;
  padding: 10px;
  font-size: 12px;
  margin: 0 auto;
  margin-bottom: 20px;
}

@media (min-width: 920px) {
  .formulaire-sect {
    max-width: 100%;
  }

  .title {
    font-size: 2.7rem;
  }

  .desc {
    font-size: 20px;
    margin-bottom: 40px;
  }
  .sect {
    width: 45%;
  }

  .form-group {
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
    font-size: 18px;
  }

  input {
    font-size: 16px;
  }
}
</style>
