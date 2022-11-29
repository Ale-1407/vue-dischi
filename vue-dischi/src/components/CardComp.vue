<template>
    <div class="cards" style="width: 11rem;">
      <img :src="card.poster" class="card-img-top" alt="...">
      <div class="card-body">
         <h5 class="card-title py-2 text-uppercase">{{card.title}}</h5>
         <span class="card-text d-block text-secondary">{{card.author}}</span>
         <span class="card-text text-secondary">{{card.year}}</span>
      </div>
    </div>
</template>

<script>

export default {
    name: "CardComp",
    props: {
      card: Object
    }
}

</script>

<style lang="scss">
.cards{
    padding: 20px;
    background-color: #2e3a46;
    color: white;
    text-align: center;
}

.cards img{
    aspect-ratio: 0.5/0.5;
}

.card-text, 
.card-title{
    font-weight: bold;
}
</style>