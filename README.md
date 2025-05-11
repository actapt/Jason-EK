<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Support Baby Jason</title>
  <link href="https://fonts.googleapis.com/css2?family=Fredoka+One&family=Nunito&display=swap" rel="stylesheet">
  <style>
    body {
      background-color: #fefaf6;
      font-family: 'Nunito', sans-serif;
      margin: 0;
      padding: 0;
      text-align: center;
    }

    .container {
      max-width: 600px;
      margin: 0 auto;
      padding: 4rem 2rem;
    }

    h1 {
      font-family: 'Fredoka One', cursive;
      font-size: 2.5rem;
      color: #333;
      margin-bottom: 1rem;
    }

    .baby-jason span {
      font-weight: bold;
      padding: 0 3px;
      text-shadow: 1px 1px 2px rgba(0,0,0,0.2);
      display: inline-block;
    }

    .b { color: #e63946; }
    .a { color: #52b788; }
    .b2 { color: #f4a261; }
    .y { color: #2ec4b6; }
    .j { color: #48cae4; }
    .a2 { color: #80ed99; }
    .s { color: #ff006e; }
    .o { color: #f9c74f; }
    .n { color: #00b4d8; }

    p {
      font-size: 1.1rem;
      color: #555;
      margin-bottom: 2rem;
    }

    form {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 1rem;
    }

    input[type="email"], select, input[type="number"] {
      padding: 0.75rem;
      font-size: 1rem;
      width: 100%;
      max-width: 300px;
      border: 1px solid #ccc;
      border-radius: 8px;
    }

    button {
      background-color: #f04a5b;
      color: white;
      font-size: 1rem;
      padding: 0.75rem 2rem;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      transition: background 0.3s ease;
    }

    button:hover {
      background-color: #d83849;
    }
  </style>
</head>
<body>

  <div class="container">
    <h1>
      Support the Celebration of<br>
      <span class="baby-jason">
        <span class="b">B</span><span class="a">a</span><span class="b2">b</span><span class="y">y</span>
        <span class="j">J</span><span class="a2">a</span><span class="s">s</span><span class="o">o</span><span class="n">n</span>
      </span><br>
      365-Day Anniversary
    </h1>

    <p>
      Make a donation and as a thank you, receive a free <strong>invite</strong> to access <strong>powerful tools </strong>we’re building to help your business <strong>grow</strong> <strong>exponentially</strong>
    </p>

    <form onsubmit="event.preventDefault(); validateDonation();">
      <input type="email" placeholder="Enter your email" required />
      <select id="supportAmountSelect" required>
        <option value="">Select Support Amount</option>
        <option value="500">₦500</option>
        <option value="1000">₦1000</option>
        <option value="2000">₦2000</option>
        <option value="5000">₦5000</option>
      </select>
      <input type="number" id="customAmount" placeholder="Enter custom amount (N500 min)" min="500" />
      <button type="submit">Support Now</button>
    </form>
  </div>

  <script>
    function validateDonation() {
      const email = document.querySelector('input[type="email"]').value;
      const selectedAmount = document.getElementById('supportAmountSelect').value;
      const customAmount = document.getElementById('customAmount').value;

      let amount = selectedAmount ? parseInt(selectedAmount) : parseInt(customAmount);

      if (!email) {
        alert('Please enter your email.');
        return;
      }

      if (amount < 500) {
        alert('Donation amount must be at least ₦500.');
        return;
      }

      // Paystack payment link
      const paystackLink = `https://paystack.com/pay/jason365?amount=${amount * 100}`;  // Paystack link, amount in kobo
      window.location.href = paystackLink;  // Redirect to Paystack payment
    }
  </script>

</body>
</html>
