<!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>Countdown Timer</title>
       <style>
  
   body {
       display: flex;
       align-items: center;
       justify-content: center;
       height: 100vh;
       margin: 0;
       background-color: orangered;
   }

   #countdown {
       font-size: 2em;
   }
</style>

   </head>
   <body>
       <div id="countdown"></div>
       <script>
   document.addEventListener('DOMContentLoaded', function () {
       // Set the date we're counting down to
       const countDownDate = new Date("Dec 31, 2023 00:00:00").getTime();

       // Update the countdown every 1 second
       const x = setInterval(function () {
           // Get the current date and time
           const now = new Date().getTime();

           // Calculate the remaining time
           const distance = countDownDate - now;

           // Calculate days, hours, minutes, and seconds
           const days = Math.floor(distance / (1000 * 60 * 60 * 24));
           const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
           const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
           const seconds = Math.floor((distance % (1000 * 60)) / 1000);

           // Display the countdown
           document.getElementById('countdown').innerHTML = ${days}d ${hours}h ${minutes}m ${seconds}s;

           // If the countdown is over, display a message
           if (distance < 0) {
               clearInterval(x);
               document.getElementById('countdown').innerHTML = "EXPIRED";
           }
       }, 1000);
   });
</script>
   </body>
   </html>