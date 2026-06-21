# gst-calculator-digital-heroes
A simple and responsive GST Calculator built using HTML, CSS, and JavaScript. Created for the Digital Heroes Developer Trial Task.
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>GST Calculator</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial, sans-serif;
}

body{
    background:#f4f7fc;
    display:flex;
    justify-content:center;
    align-items:center;
    min-height:100vh;
    padding:20px;
}

.container{
    width:100%;
    max-width:450px;
    background:white;
    padding:25px;
    border-radius:15px;
    box-shadow:0 5px 20px rgba(0,0,0,0.15);
}

h1{
    text-align:center;
    color:#2563eb;
    margin-bottom:20px;
}

label{
    display:block;
    margin-top:12px;
    margin-bottom:5px;
    font-weight:bold;
}

input,select{
    width:100%;
    padding:12px;
    border:1px solid #ccc;
    border-radius:8px;
    font-size:16px;
}

button{
    width:100%;
    padding:12px;
    margin-top:18px;
    border:none;
    border-radius:8px;
    cursor:pointer;
    font-size:16px;
}

.calculate{
    background:#2563eb;
    color:white;
}

.calculate:hover{
    background:#1d4ed8;
}

.result{
    margin-top:20px;
    background:#eef4ff;
    padding:15px;
    border-radius:10px;
}

.result p{
    margin:8px 0;
    font-size:16px;
}

.digital-btn{
    display:block;
    text-align:center;
    text-decoration:none;
    background:#16a34a;
    color:white;
    padding:12px;
    border-radius:8px;
    margin-top:20px;
}

.footer{
    margin-top:20px;
    text-align:center;
    font-size:14px;
    color:#555;
}
</style>
</head>

<body>

<div class="container">

<h1>GST Calculator</h1>

<label>Enter Amount (₹)</label>
<input type="number" id="amount" placeholder="Enter amount">

<label>Select GST Rate</label>
<select id="gst">
    <option value="5">5%</option>
    <option value="12">12%</option>
    <option value="18">18%</option>
    <option value="28">28%</option>
</select>

<button class="calculate" onclick="calculateGST()">
Calculate GST
</button>

<div class="result" id="result">
    <p>GST Amount: ₹0</p>
    <p>Total Amount: ₹0</p>
</div>

<a href="https://digitalheroesco.com"
target="_blank"
class="digital-btn">
Built for Digital Heroes
</a>

<div class="footer">
    <strong>Vimarsha Bhardwaj</strong><br>
    vimarsha2947@gmail.com
</div>

</div>

<script>
function calculateGST(){

let amount = parseFloat(document.getElementById("amount").value);
let gstRate = parseFloat(document.getElementById("gst").value);

if(isNaN(amount) || amount <= 0){
    alert("Please enter a valid amount.");
    return;
}

let gstAmount = (amount * gstRate) / 100;
let totalAmount = amount + gstAmount;

document.getElementById("result").innerHTML = `
<p><strong>GST Amount:</strong> ₹${gstAmount.toFixed(2)}</p>
<p><strong>Total Amount:</strong> ₹${totalAmount.toFixed(2)}</p>
`;
}
</script>

</body>
</html>
