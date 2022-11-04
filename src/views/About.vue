<template>
  <div class="about">
    <h1>This is an about page</h1>
    <p>
      This Vue app uses fetch API to get data from the Messari Crypto website.
    </p>
    <p>It uses routing to send data from components to different routes</p>
    <p>
      The data from the Messari Crypto website is displayed on the
      screen.Flexbox is used to generate a Responsive web page
    </p>
  </div>
</template>
<style scoped>
* {
  margin: 0;
  padding: 0;
}
div.about {
  display: flex;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  color: green;
}
p {
  color: rgb(239, 120, 120);
  padding: 30px;
}
</style>
