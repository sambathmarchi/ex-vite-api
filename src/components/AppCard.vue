<script>
    export default{
        props: ["arrayGenerato"]
    }
</script>

<template>
  <section>
      <div v-for="element in arrayGenerato">
          <h3>{{ element.name }}</h3>
          <h5>{{ element.address_1 }}</h5>
          <p>{{ element.city }}</p>
          
      </div>

  </section>
</template>

<style scoped>
    div{
        width: calc(90% / 5);
        height: 300px;
        background-color: darkcyan;
        padding: 0.5rem;
        margin: 0.5rem;
        text-align: center;
    }
    section{
        margin: 3rem auto;
        display: flex;
        justify-content: space-between;
        align-items: center;
        flex-wrap: wrap;
        padding: 1rem;
    }
    h3{
        margin-bottom: 1rem;

    }
    h5{
        margin-bottom: 1rem;
    }
    p{
        margin-bottom: 1rem;
    }
</style>