 <!DOCTYPE html>
<html>
<head>
<title>J. Gailah Venture</title>
<style>
body { font-family: Arial; text-align: center; background:#eef; }
.box { background:white; padding:20px; margin:20px; border-radius:10px; }
button { padding:10px; background:green; color:white; border:none; }
</style>
</head>

<body>

<h1>J. Gailah Venture</h1>
<p>Earn Money Online Easily</p>

<div class="box">
<h2>Register</h2>
<input id="name" placeholder="Name"><br><br>
<input id="phone" placeholder="Phone Number"><br><br>
<input id="ref" placeholder="Referral Code (optional)"><br><br>
<button onclick="register()">Register</button>
</div>

<div class="box">
<h2>Dashboard</h2>
<p id="user">User: Not logged in</p>
<p id="balance">Balance: $0</p>
<button onclick="earn()">Complete Task (+$1)</button><br><br>
<button onclick="withdraw()">Withdraw</button>
</div>

<script>
let balance = 0;
let currentUser = "";

function register(){
    currentUser = document.getElementById("name").value;
    document.getElementById("user").innerText = "User: " + currentUser;
    alert("Registered successfully!");
}

function earn(){
    balance += 1;
    updateBalance();
}

function withdraw(){
    let fee = balance * 0.30;
    let payout = balance - fee;

    alert("Withdrawal Summary:\nTotal: $" + balance +
          "\nPlatform Fee (30%): $" + fee +
          "\nYou Receive: $" + payout);

    balance = 0;
    updateBalance();
}

function updateBalance(){
    document.getElementById("balance").innerText = "Balance: $" + balance;
}
</script>

</body>
</html>
