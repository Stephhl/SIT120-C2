<template>
  <div id="app">
    <div class="content">
      <h1>Weather App</h1>
      <select v-model="selectedCity">
        <option value="Melbourne">Melbourne</option>
        <option value="Sydney">Sydney</option>
        <option value="Canberra">Canberra</option>
        <option value="Perth">Perth</option>
        <option value="Queensland">Queensland</option>
      </select>
      <input v-model.number="userTemperature" type="number" placeholder="Test: Enter Temperature" />
      <div v-if="userTemperature !== null" class="weather-info">
        <h2>Weather in {{ selectedCity }}</h2>
        <p>Temperature: {{ userTemperature }}°C</p>
        <p>Weather: {{ userTemperature > 20 ? "Sunny" : "Cold" }}</p>
        <img :src="userTemperature > 20 ? sunnyImage : coldImage" alt="Weather Image" />
      </div>
      <div class="feedback">
        <button @click="feedbackForm">Give Feedback</button>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  data() {
    return {
      selectedCity: "Melbourne",
      userTemperature: null,
      sunnyImage: "https://creazilla-store.fra1.digitaloceanspaces.com/cliparts/1723080/sun-clipart-xl.png",
      coldImage: "https://i.pinimg.com/originals/c1/64/5e/c1645e0627093fd4539c5e9992b65659.png",
    };
  },
  methods: {
    feedbackForm() {
      alert("Coming soon!")
    }
  }
};
</script>

<style scoped>
#app {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background-color: #f0f0f0;
  background-image: url('https://media.istockphoto.com/id/926497236/photo/tropical-sea-in-summer.jpg?s=612x612&w=0&k=20&c=SgT--E-a5_UF4GPVnpC6r1IDtThuDiUHmtTbhHg5zJA=');
  background-size: cover;
  background-position: center;
}

.content {
  text-align: center;
  padding: 15px;
  border-radius: 10px;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
  max-width: 500px;
  width: 90%;
}

img {
  max-width: 100%;
  height: auto;
  margin: 20px 0;
}

select,
input {
  padding: 5px;
  font-size: 16px;
  width: 100%;
  color: black;
  font-weight: bold;
}

button {
  padding: 5px 10px;
  font-size: 16px;
  color: black;
  font-weight: bold;
}

h1,
h2,
p {
  color: black;
  font-weight: bold;
  font-size: 1.5rem;
}
</style>
