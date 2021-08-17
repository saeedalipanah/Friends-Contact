<template>
  <section>
    <header>
      <h1>My Friends</h1>
    </header>
    <ul>
      <new-friend @add-contacts="addContact"></new-friend>
      <friend-contact
        v-for="friend in friends"
        :key="friend.id"
        :id="friend.id"
        :name="friend.name"
        :phone-number="friend.phone"
        :email-address="friend.email"
        @delete-contact="deleteContact"
      ></friend-contact>
    </ul>
  </section>
</template>

<script>
export default {
  data() {
    return {
      friends: [
        {
          id: 1,
          name: "Manuel Lorenz",
          phone: "0123 45678 90",
          email: "manuel@localhost.com",
        },
        {
          id: 2,
          name: "Julie Jones",
          phone: "0987 654421 21",
          email: "julie@localhost.com",
        },
        {
          id: 3,
          name: "Nima Rahimian",
          phone: "0987 654421 21",
          email: "nimarahimian@gmail.com",
        },
        {
          id: 4,
          name: "Soran Khaledy",
          phone: "0987 654421 21",
          email: "sorankhaledy@gmail.com",
        },
      ],
    };
  },
  methods: {
    addContact(na, ph, em) {
      const newFriendContact = {
        id: Math.floor(Math.random()),
        name: na,
        phone: ph,
        email: em,
      };
      this.friends.push(newFriendContact);
    },
    //delete item of array based on property
    deleteContact(ID) {
      this.friends = this.friends.filter(function(friend) {
        return friend.id !== ID;
      });
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}
html {
  font-family: "Jost", sans-serif;
}
body {
  margin: 0;
}
header {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 3rem auto;
  border-radius: 10px;
  padding: 1rem;
  background-color: #58004d;
  color: white;
  text-align: center;
  width: 90%;
  max-width: 40rem;
}
#app ul {
  margin: 0;
  padding: 0;
  list-style: none;
}
#app li {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 1rem auto;
  border-radius: 10px;
  padding: 1rem;
  text-align: center;
  width: 90%;
  max-width: 40rem;
}
#app h2 {
  font-size: 2rem;
  border-bottom: 4px solid #ccc;
  color: #58004d;
  margin: 0 0 1rem 0;
}
#app button {
  font: inherit;
  cursor: pointer;
  border: 1px solid #ff0077;
  background-color: #ff0077;
  color: white;
  padding: 0.05rem 1rem;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
}
#app button:hover,
#app button:active {
  background-color: #ec3169;
  border-color: #ec3169;
  box-shadow: 1px 1px 4px rgba(0, 0, 0, 0.26);
}
</style>
