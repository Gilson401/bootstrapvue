<template>
  <div class="content">
    <div class="right align-self-center">
      <p class="text-white">/Projetos</p>
      <p class="text-gray-300 font-size-030">/Cases Games</p>
      <b-row>

        <b-col v-for="index in 4" :key="index"
        cols="12" md="3"
        >
          <div class="card">
            <img class="card-img mb-3" src="https://picsum.photos/280/180/?image=25" alt="" />

            <div class="card-text">
            <button class="card-button mb-3 text-uppercase"> <span> sit amet  </span> </button>
            
            <p class="text-gray-300 font-size-020"> Lorem Dolor </p>

            <p class="text-white  font-size-075">
              Lorem <strong> ipsum dolor </strong>  sit amet consectetur adipisicing elit. Esse
              tempora vel
            </p>  
            <a class="text-decoration-none text-left ml-auto" href="#">
                <span class="text-gray-300 "> Saiba mais </span> <span class="text-white"> &#129134; </span>  
                </a>  
                </div>
          </div>
        </b-col>
      </b-row>
    </div>
  </div>
</template>

<script>
export default {
  name: "CaseGames",
  props: {
    msg: String,
  },
};
</script>

<style scoped>
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
  margin-bottom: 30px;
  background-color: rgb(41,41,41);
}

.card-img {
  aspect-ratio: 1.5;
  width: 100%;
}

.card-button {
  background-color: rgb(147,149,152);
color:black;
text-transform: uppercase;
display: inline-block;
width: fit-content;
padding: 1px 2px 1px 2px;
}

.card-text{
    margin: 10px 20px 0 20px;
    padding-bottom: 20px;
}

</style>
