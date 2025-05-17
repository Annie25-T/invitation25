> <!DOCTYPE html>
> <html lang="hy">
> <head>
>   <meta charset="UTF-8">
>   <title>Անիի Հրավիրտոմսը</title>
>   <style>
>     body {
>       margin: 0;
>       font-family: 'Segoe UI', sans-serif;
>       text-align: center;
>       background: linear-gradient(to right, #fceabb, #f8b500);
>       color: #333;
>       padding: 20px;
>     }
>
>     h1 {
>       font-size: 36px;
>       margin-top: 20px;
>     }
>
>     .date, .location {
>       font-size: 18px;
>       margin: 10px 0;
>     }
>
>     .countdown {
>       font-size: 24px;
>       margin: 20px 0;
>       font-weight: bold;
>     }
>
>     .rsvp {
>       margin-top: 30px;
>     }
>
>     .rsvp button {
>       font-size: 18px;
>       padding: 10px 20px;
>       margin: 5px;
>       background-color: #ffffff;
>       border: 2px solid #333;
>       border-radius: 8px;
>       cursor: pointer;
>       transition: 0.3s;
>     }
>
>     .rsvp button:hover {
>       background-color: #f8b500;
>       color: white;
>     }
>
>     .response {
>       margin-top: 15px;
>       font-weight: bold;
>       color: green;
>     }
>
>     @media (max-width: 600px) {
>       h1 { font-size: 28px; }
>       .countdown { font-size: 20px; }
>     }
>   </style>
> </head>
> <body>
>
>   <h1>✨ Հրավիրվում եք Անիի տոնակատարությանը ✨</h1>
>
>   <div class="date">📅 Ամսաթիվ՝ 2025 թ. հուլիսի 20</div>
>   <div class="location">📍 Վայրը՝ <strong>Բյուրական, Լուսնային Քոթեջ</strong></div>
>
>   <div class="countdown" id="countdown">Հետհաշվարկ…</div>
>
>   <div class="rsvp">
>     <p>Հասկացա՞ք՝ գալո՞ւ եք 😊</p>
>     <button onclick="respond(true)">Այո, գալիս եմ ✅</button>
>     <button onclick="respond(false)">Չեմ կարող գալ ❌</button>
>     <div class="response" id="response"></div>
>   </div>
>
>   <script>
>     // Հետհաշվարկ
>     const targetDate = new Date("July 20, 2025 18:00:00").getTime();
>
>     function updateCountdown() {
>       const now = new Date().getTime();
>       const distance = targetDate - now;
>
>       if (distance < 0) {
>         document.getElementById("countdown").innerHTML = "Միջոցառումը սկսվել է 🎉";
>         return;
>       }
>
>       const days = Math.floor(distance / (1000 * 60 * 60 * 24));
>       const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
>       const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
>       const seconds = Math.floor((distance % (1000 * 60)) / 1000);
>
>       document.getElementById("countdown").innerHTML =
>         `${days} օր ${hours} ժ ${minutes} ր ${seconds} վ`;
>     }
>
>     setInterval(updateCountdown, 1000);
>     updateCountdown();
>
>     // RSVP պատասխան
>     function respond(isComing) {
>       const response = document.getElementById("response");
>       if (isComing) {
>         response.innerHTML = "Ուրախ ենք, որ գալու եք 🥳";
>       } else {
>         response.innerHTML = "Ցավում ենք, որ չեք կարող գալ 😔";
>       }
>     }
>   </script>
>
> </body>
> </html>
