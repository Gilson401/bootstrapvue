<template>
  <div class="content">
    <div class="left align-self-center">
      <p class="text-white">/Quem somos.</p>
      <p class="text-gray-300 font-size-030">/We Do Games</p>
      <p class="text-gray-300 font-size-020">Desenvolvimento de games digitais</p>
      <p class="text-gray-300 font-size-012">
        Empresa especializada em desenvolvimento de games e digitais e 
        gamificação
      </p>
      <p class="text-white font-size-012">
        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Enim, officiis
        facere dicta natus vitae, minus excepturi cum assumenda delectus soluta
        voluptatibus inventore harum! Obcaecati ratione sint odit laudantium
        inventore dolor.
      </p>
    </div>

    <div class="right align-self-center">
      <b-row cols="4">
        <b-col v-for="index in 3" :key="index">
          <div>
            <img class="card-img mb-3" src="https://picsum.photos/200/200/?image=25" alt="" />

            <p class="text-white  font-size-075">
              Lorem <strong> ipsum dolor </strong>  sit amet consectetur adipisicing elit. Esse
              tempora vel
            </p>    
          </div>
        </b-col>

        <b-col>
          <div>
              
            <img class="card-img mb-3" src="../assets/joystick.png" alt="" />

            <p class="text-white">
              Experimente inovar com a  <strong> YourBusiness </strong>  para <strong> desenvolver os seus jogos digitais </strong> 
            </p>    

            <p class="text-uppercase font-size-010"> 

                <a class="text-decoration-none" href="#">
                <span class="text-gray-300 "> Entre em contato agora mesmo  </span> <span class="text-white"> &#129134; </span>  
                </a>
            </p>
          </div>
        </b-col>
      </b-row>
    </div>
  </div>
</template>

<script>
export default {
  name: "QuemSomos",
  props: {
    msg: String,
  },
};
</script>

<style scoped>
.content {
  grid-area: content;
  display: grid;
  grid-template-areas: "left right";
  grid-template-columns: 50% 50%;
  grid-gap: 10px;
  height: 100vh;
  padding: 0 30px 0 30px;
}

p {
  text-align: left;
} 
.left {
  grid-area: left;

}

.right {
  grid-area: right;
}

.card {
  width: auto;
  height: 60vh;
}

.card-img {
  aspect-ratio: 1;
  width: 100%;
}
</style>
