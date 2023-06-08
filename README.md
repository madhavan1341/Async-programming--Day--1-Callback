# Async-programming--Day--1-Callback


<!DOCTYPE html>
<html>
  <head>
    <title>Countdown Example</title>
  </head>
  <body>
    <div id="countdown"></div>
    <div id="message"></div>
	<script>const countdown = (num) => {
  return new Promise((resolve, reject) => {
    let currentNum = num;

    const timer = setInterval(() => {
      console.log(currentNum);
      currentNum--;

      if (currentNum === 0) {
        clearInterval(timer);
        resolve();
      }
    }, 1000);
  });
};

// Start the countdown
countdown(10)
  .then(() => {
    return new Promise((resolve) => {
      setTimeout(() => {
        console.log("Happy Independence Day");
        resolve();
      }, 1000);
    });
  })
  .catch((error) => {
    console.log("Error:", error);
  });
</script>
  </body>
</html>
