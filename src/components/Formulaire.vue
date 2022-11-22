<script setup>
import { ref } from "vue";
import emailjs from "emailjs-com";
import Swal from "sweetalert2";

const nom = ref("");
const prenom = ref("");
const sexe = ref("");
const adresseMail = ref("");
const age = ref("");
const niveauScolaire = ref("");
const etablissement = ref("");

const tempLangage = ref("");
const langageMaitrise = ref([]);

const tempTechStack = ref("");
const techStack = ref([]);

const specialite = ref([]);

const tempSkill = ref("");
const softSkills = ref([]);

const formErrors = ref([]);
const maxChars = ref(15);
const errDiv = ref(null);
const form = ref(null);

function addSoftSkill() {
  if (tempSkill.value) {
    if (!softSkills.value.includes(tempSkill.value)) {
      softSkills.value.push(tempSkill.value);
    }
    tempSkill.value = "";
  }
}
function deleteSoftSkill(skill) {
  softSkills.value = softSkills.value.filter((el) => {
    return skill !== el;
  });
}

function addLangageMaitrise() {
  if (tempLangage.value) {
    if (!langageMaitrise.value.includes(tempLangage.value)) {
      langageMaitrise.value.push(tempLangage.value);
    }
    tempLangage.value = "";
  }
}
function deleteLangageMaitrise(langage) {
  langageMaitrise.value = langageMaitrise.value.filter((el) => {
    return langage !== el;
  });
}

function addTechStack() {
  if (tempTechStack.value) {
    if (!techStack.value.includes(tempTechStack.value)) {
      techStack.value.push(tempTechStack.value);
    }
    tempTechStack.value = "";
  }
}
function deleteTechStack(tech) {
  techStack.value = techStack.value.filter((el) => {
    return tech !== el;
  });
}

const validateForm = () => {
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
  } else if (!niveauScolaire.value) {
    formErrors.value.push("Année Scolaire field cant be empty");
  } else if (!etablissement.value) {
    formErrors.value.push("Etablissement field cant be empty");
  } else if (!langageMaitrise.value.length) {
    formErrors.value.push("Langage maîtrisée field cant be empty");
  } else if (!techStack.value.length) {
    formErrors.value.push("Tech stack maîtrisée field cant be empty");
  } else if (!specialite.value.length) {
    formErrors.value.push("Spécialité field cant be empty");
  } /* else if (!softSkills.value) {
    formErrors.value.push("Soft Skills field cant be empty");
  } */

  if (!formErrors.value.length) {
    sendEmail();
  } else {
    errDiv.value.scrollIntoView();
  }
};

function sendEmail() {
  emailjs
    .sendForm(
      "service_xbunf0l",
      "template_cxf39nb",
      form.value,
      "vmbOVQdTQ_lJe81e9"
    )
    .then(
      (result) => {
        console.log("SUCCESS!", result.text);
        Swal.fire({
          title: "success",
          text: "You are Successfuly Submited",
          icon: "success",
          confirmButtonText: "ok",
        });
      },
      (error) => {
        console.log("FAILED...", error.text);
        Swal.fire({
          title: "Error!",
          text: "Cannot Submit!",
          icon: "error",
          confirmButtonText: "ok",
        });
      }
    );

  // reset form fields
  nom.value = "";
  prenom.value = "";
  sexe.value = "";
  adresseMail.value = "";
  age.value = "";
  niveauScolaire.value = "";
  etablissement.value = "";
  langageMaitrise.value = [];
  techStack.value = [];
  specialite.value = [];
  softSkills.value = [];
}
</script>

<template>
  <div class="container">
    <div id="inscrivez-vous" class="formulaire-sect">
      <h1 ref="errDiv" class="title">INSCRIVEZ-VOUS</h1>
      <p class="desc">Formulaire d’inscription :</p>
      <form @submit.prevent="validateForm" ref="form">
        <!-- errors -->
        <div v-if="formErrors" class="errors-list">
          <div class="error" v-for="(error, index) in formErrors" :key="index">
            {{ error }}
          </div>
        </div>

        <!-- form-container -->
        <div class="form-group">
          <!-- info-presonel -->
          <div class="info-perso">
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
              <input
                v-model.trim="nom"
                name="nom"
                type="text"
                id="nom"
                placeholder="nom"
              />
            </div>

            <!-- prenom -->
            <div class="prenom sect">
              <label for="prenom" class="req label-title">Prenom</label>
              <input
                v-model.trim="prenom"
                name="prenom"
                type="text"
                id="prenom"
                placeholder="prenom"
              />
            </div>

            <!-- adresse mail -->
            <div class="mail sect">
              <label for="mail" class="req label-title">Adresse mail</label>
              <input
                v-model.trim="adresseMail"
                name="email"
                type="email"
                id="mail"
                placeholder="adresse mail"
              />
            </div>

            <!-- age -->
            <div class="age sect">
              <label for="age" class="req">Age</label>
              <input
                v-model="age"
                class="age-inp"
                name="age"
                type="number"
                id="age"
              />
              ans
            </div>

            <!-- niveau scolaire -->
            <div class="niveau-scolaire sect">
              <label for="niveau-scolaire" class="req">Niveau Scolaire</label>
              <select
                class="annee-inp"
                name="niveau_scolaire"
                id="anne-scolaire"
                v-model="niveauScolaire"
              >
                <option value="L1">L1</option>
                <option value="L2">L2</option>
                <option value="L3">L3</option>
                <option value="M1">M1</option>
                <option value="M2">M2</option>
              </select>
            </div>

            <!-- copy of niveau scolaire -->
            <div class="niveau-scolaire sect">
              <label for="niveau-scolaire" class="req">Etablissement</label>
              <select
                class="annee-inp"
                name="etablissement"
                id="anne-scolaire"
                v-model="etablissement"
              >
                <option value="L1">L1</option>
                <option value="L2">L2</option>
                <option value="L3">L3</option>
                <option value="M1">M1</option>
                <option value="M2">M2</option>
              </select>
            </div>
          </div>

          <!-- info-tech -->
          <div class="info-tech">
            <!-- Langage maîtrisée -->
            <div class="langage-maitrise sect">
              <label for="langage" class="label-title req"
                >Langage maîtrisée</label
              >
              <div class="langage-inp-container">
                <input
                  v-model.trim="tempLangage"
                  name="langage_maitraise"
                  type="text"
                  id="langage"
                  placeholder="Langage maîtrisée"
                />
                <input
                  @click="addLangageMaitrise"
                  type="button"
                  class="btn-add"
                  value="add"
                />
              </div>
              <div class="pill-container">
                <div
                  v-for="(langage, index) in langageMaitrise"
                  :key="index"
                  class="pill"
                >
                  <span @click="deleteLangageMaitrise(langage)">
                    {{ langage }}
                  </span>
                </div>
              </div>
            </div>

            <!-- Tech stack maîtrisée -->
            <div class="tech-stack sect">
              <label for="stack" class="label-title req"
                >Tech stack maîtrisée</label
              >

              <div class="techstack-inp-container">
                <input
                  v-model.trim="tempTechStack"
                  name="tech_stack"
                  type="text"
                  id="stack"
                  placeholder="Tech stack maîtrisée"
                />
                <input
                  @click="addTechStack"
                  type="button"
                  class="btn-add"
                  value="add"
                />
              </div>
              <div class="pill-container">
                <div
                  v-for="(tech, index) in techStack"
                  :key="index"
                  class="pill"
                >
                  <span @click="deleteTechStack(tech)"> {{ tech }} </span>
                </div>
              </div>
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
                    name="specialite"
                    id="front-end"
                  />
                  <label class="front-end-label" for="front-end"
                    >Front-End</label
                  >
                </div>
                <div class="back-end">
                  <input
                    v-model="specialite"
                    type="checkbox"
                    value="back-end"
                    name="specialite"
                    id="back-end"
                  />
                  <label class="back-end-label" for="back-end">Back-End</label>
                </div>
                <div class="data-base">
                  <input
                    v-model="specialite"
                    type="checkbox"
                    value="database"
                    name="specialite"
                    id="data-base"
                  />
                  <label class="data-base-label" for="data-base"
                    >DataBase</label
                  >
                </div>
              </div>
            </div>

            <!-- soft skills -->
            <div class="soft-skills sect">
              <label for="soft-skills" class="label-title">Soft Skills</label>
              <div class="skills-inp-container">
                <input
                  v-model.trim="tempSkill"
                  name="soft_skills"
                  type="text"
                  id="soft-skills"
                  placeholder="ex: Probleme-Solving, self-learning, ..."
                />
                <input
                  @click="addSoftSkill"
                  type="button"
                  class="btn-add"
                  value="add"
                />
              </div>
              <div class="pill-container">
                <div
                  v-for="(skill, index) in softSkills"
                  :key="index"
                  class="pill"
                >
                  <span @click="deleteSoftSkill(skill)"> {{ skill }} </span>
                </div>
              </div>
            </div>
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

/* niveau-scolaire */
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

.pill {
  background: #eee;
  color: var(--blueColor);
  font-size: 12px;
  padding: 5px 10px;
  border-radius: 19px;
  margin-top: 5px;
  display: inline-block;
  margin-right: 5px;
  cursor: pointer;
  transition: 0.3s ease all;
}
.pill:hover {
  background: #cdcdcd;
  color: red;
}

.skills-inp-container,
.langage-inp-container,
.techstack-inp-container {
  display: flex;
  justify-content: space-around;
}

.skills-inp-container input,
.langage-inp-container input,
.techstack-inp-container input {
  width: 85%;
  border-radius: 5px 0 0 5px;
}
.skills-inp-container .btn-add,
.langage-inp-container .btn-add,
.techstack-inp-container .btn-add {
  width: 20%;
  border: none;
  background-color: var(--cyanColor);
  color: #fff;
  font-size: 12px;
  text-transform: uppercase;
  cursor: pointer;
  border-radius: 0 5px 5px 0;
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
  /* .sect {
    width: 45%;
  } */

  .info-perso,
  .info-tech {
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
