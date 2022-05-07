<template>
  <div class="content">
    <div class="right align-self-center">
      <p class="text-white">/Contato</p>
      <p class="text-gray-300 font-size-030">/Mensagem</p>
      <b-container>
        <b-row>
          <b-col cols="12" md="6">
            <p class="text-gray-300 font-size-012">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt
              doloremque, praesentium vero, placeat odio ullam, unde dolore nemo
              aspernatur voluptate ab fugit alias pariatur nulla reiciendis
              impedit id corporis quam.
            </p>
            <div>
              <b-form @submit="onSubmit" @reset="onReset" v-if="show">
                <b-form-group
                  id="input-group-2"
                  label="Nome:"
                  label-for="input-2"
                >
                  <b-form-input
                    id="input-2"
                    v-model="form.name"
                    placeholder=""
                    required
                  ></b-form-input>
                </b-form-group>

                <b-form-group
                  id="input-group-1"
                  label="Email:"
                  label-for="input-1"
                  description=""
                  class="mt-4"
                >
                  <b-form-input
                    id="input-1"
                    v-model="form.email"
                    type="email"
                    placeholder=""
                    required
                  ></b-form-input>
                </b-form-group>

                <b-form-group
                  id="input-group-1"
                  label="Mensagem:"
                  label-for="input-2"
                  description=""
                  class="mt-4"
                >
                  <b-form-textarea
                    id="input-2"
                    v-model="form.mensagem"
                    type="textarea"
                    placeholder=""
                    rows="3"
                    max-rows="6"
                    required
                  ></b-form-textarea>
                </b-form-group>

                <div
                  role="button"
                  type="submit"
                  class="text-decoration-none text-left ml-auto text-uppercase mt-4"
                  @click="onSubmit"
                >
                
                  <span class="text-gray-300"> Enviar </span>
                  <span class="text-white"> &#129134; </span>
                </div>
              </b-form>
            </div>
          </b-col>

          <b-col cols="12" md="6">
            <b-row>
              <b-col>
                <contact-card
                  topText="Siga-nos"
                  medium-text="Siga-nos em nossas redes sociais super descoladas."
                  :bottom-link="{ label: 'label', route: 'route' }"
                />
              </b-col>
              <b-col>
                <contact-card
                  topText="Itapema/SC"
                  medium-text="Sed ut perspiciatis unde omnis iste natus error sit voluptatem
                 accusantium doloremque laudantium, totam rem aperiam, eaque ipsa."
                  :bottom-link="{ label: 'label', route: 'route' }"
                />
              </b-col>

              <b-col>
                <contact-card
                  topText="Dubai"
                  medium-text="Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni."
                  :bottom-link="{ label: 'label', route: 'route' }"
                />
              </b-col>
            </b-row>
            <b-row class="mt-4">
              <b-col>
                <contact-card
                  medium-text="Ut enim ad minima veniam, quis nostrum exercitationem ullam corporis suscipit laboriosam."
                  :bottom-link="{ label: 'Conheça', route: '#' }"
                >
                  <template #top>
                    <img
                      class="card-img mb-3"
                      src="https://picsum.photos/200/100/?image=25"
                      alt=""
                    />
                  </template>
                </contact-card>
              </b-col>
              <b-col>
                <contact-card
                  medium-text="Quis autem vel eum iure reprehenderit qui in ea voluptate velit esse quam nihil molestiae consequatur."
                  :bottom-link="{ label: 'Conheça', route: '#' }"
                >
                  <template #top>
                    <img
                      class="card-img mb-3"
                      src="https://picsum.photos/200/100/?image=25"
                      alt=""
                    />
                  </template>
                </contact-card>
              </b-col>
              <b-col>
                <contact-card
                  topText=""
                  medium-text="At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium voluptatum."
                  :bottom-link="{ label: 'Conheça', route: '#' }"
                >
                  <template #top>
                    <img
                      class="card-img mb-3"
                      src="https://picsum.photos/200/100/?image=25"
                      alt=""
                    />
                  </template>
                </contact-card>
              </b-col>
            </b-row>
          </b-col>
        </b-row>
      </b-container>
    </div>
  </div>
</template>

<script>
import ContactCard from "./ContactCard.vue";

export default {
  components: { ContactCard },
  name: "Contact",
  data() {
    return {
      form: {
        email: "",
        name: "",
        message: "",
      },
      show: true,
    };
  },
  props: {
    msg: String,
  },

  methods: {
    onSubmit(event) {
      event.preventDefault();
      alert(JSON.stringify(this.form));
    },
    onReset(event) {
      event.preventDefault();
      this.form.email = "";
      this.form.name = "";
      this.show = false;
      this.$nextTick(() => {
        this.show = true;
      });
    },
  },
};
</script>

<style scoped>

.content {
    padding: 30px 30px 0 30px;
}

@media screen and (min-width: 768px) {
.content {
  grid-area: content;
  display: grid;
  grid-template-areas: "right right";
  grid-template-columns: 50% 50%;
  grid-gap: 10px;
  height: 100vh;
  padding: 30px;
}

p {
  text-align: left;
}
.left {
  grid-area: left;
  padding: 12%;
}

.right {
  grid-area: right;
}

.card {
  width: auto;
  height: auto;

  background-color: rgb(41, 41, 41);
}

.form-control {
  background-color: transparent;
}

textarea::-webkit-scrollbar {
  display: none;
}

/* Esconder scrollbar for IE, Edge and Firefox */
textarea {
  -ms-overflow-style: none; /* IE and Edge */
  scrollbar-width: none; /* Firefox */
}
}
</style>

<style>
label {
  color: rgb(255, 255, 255);
  font-size: 0.75rem;
}
</style>
