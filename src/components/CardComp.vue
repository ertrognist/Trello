<template>
    <input
      class="input-card"
      type="text"
      placeholder="Create a Card"
      v-model="cardName"
      @keyup.enter="createCard"
    />
</template>
  
  <script>
  export default {
    props: ["listId"],
    methods: {
      createCard() {
        if (this.cardName !== "") {
          const card = {
            listId: this.listId,
            name: this.cardName,
          };
          this.$store.dispatch("createCard", card);
          this.cardName = "";
        }
      },
    },
  };
  </script>
  
  <style>
  .input-card {
    position: relative;
    background-color: white;
    min-height: 30px;
    width: 100%;
    display: flex;
    align-items: center;
    border-radius: 5px;
    padding: 10px;
    word-break: break-all;
    font-size: 16px;
  }
  </style>
  