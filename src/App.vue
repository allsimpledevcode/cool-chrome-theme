<template>
  <div class="date-time-wrapper">
    <h1 class="time">{{time}}</h1>
    <h3 class="greet">{{greeting}}</h3>
  </div>
</template>

<script>
export default {
  name: 'App',
  setup() {
    const dateObject = new Date();
    const hour = dateObject.getHours();
    let greet = "Good";
    
    if(hour <= 11) {
      greet += " morning";
    }else if(hour <= 18) {
      greet += " afternoon";
    }else {
      greet += " evening";
    }
    return {
      greeting: greet,
      time: `${hour +":"+dateObject.getMinutes()}`
    }
  }
}
</script>

<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  .date-time-wrapper {
    text-align: center;
    margin: auto;
    display: block;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    color: white;
  }
  .time {
    font-size: 8rem;
    font-weight: 600;
    margin-bottom: 4px;
  }
  .greet {
    font-size: 3.5rem;
    font-weight: 400;
  }
  body {
    font-family: -apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Oxygen-Sans,Ubuntu,Cantarell,"Helvetica Neue",sans-serif;
    background-image: url(https://source.unsplash.com/random);
    background-size: cover;
    background-color: auto;
  }
</style>
