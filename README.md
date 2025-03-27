<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>AI SmartShop</title>
<style>

        body {

            font-family: Arial, sans-serif;

            text-align: center;

            margin: 0;

            padding: 20px;

            background-color: #f4f4f4;

        }

        .container {

            background: white;

            padding: 20px;

            border-radius: 10px;

            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);

            max-width: 600px;

            margin: auto;

        }

        img {

            width: 100%;

            max-width: 300px;

            margin-top: 20px;

        }

        .tabs {

            display: flex;

            justify-content: center;

            margin-bottom: 20px;

        }

        .tab {

            padding: 10px 20px;

            cursor: pointer;

            background: #007bff;

            color: white;

            border: none;

            margin: 0 5px;

            border-radius: 5px;

        }

        .tab:hover {

            background: #0056b3;

        }

        .tab-content {

            display: none;

            margin-top: 20px;

        }

        .active {

            display: block;

        }

        ul {

            list-style-type: none;

            padding: 0;

        }

        ul li {

            padding: 10px;

            background: #eee;

            margin: 5px 0;

            border-radius: 5px;

            cursor: pointer;

        }

        ul li:hover {

            background: #ddd;

        }

        .booking-section {

            display: none;

            margin-top: 20px;

            padding: 10px;

            background: #d4edda;

            color: #155724;

            border-radius: 5px;

        }

        .book-btn {

            padding: 8px 15px;

            background: #28a745;

            color: white;

            border: none;

            border-radius: 5px;

            cursor: pointer;

        }

        .book-btn:hover {

            background: #218838;

        }
</style>
</head>
<body>
 <div class="container">
<h1>Welcome to AI SmartShop</h1>
<p>Your one-stop destination for AI-powered shopping!</p>
 
        <!-- Tabs -->
<div class="tabs">
<button class="tab" onclick="openTab('phones')">Phones</button>
<button class="tab" onclick="openTab('laptops')">Laptops</button>
</div>
 
        <!-- Phones Tab Content -->
<div id="phones" class="tab-content">
<h2>Available Phones</h2>
<ul>
<li onclick="showBooking('iPhone 15 Pro')">iPhone 15 Pro</li>
<li onclick="showBooking('Samsung Galaxy S23 Ultra')">Samsung Galaxy S23 Ultra</li>
<li onclick="showBooking('Google Pixel 8')">Google Pixel 8</li>
<li onclick="showBooking('OnePlus 11')">OnePlus 11</li>
</ul>
</div>
 
        <!-- Laptops Tab Content -->
<div id="laptops" class="tab-content">
<h2>Available Laptops</h2>
<ul>
<li onclick="showBooking('MacBook Pro M2')">MacBook Pro M2</li>
<li onclick="showBooking('Dell XPS 15')">Dell XPS 15</li>
<li onclick="showBooking('HP Spectre x360')">HP Spectre x360</li>
<li onclick="showBooking('Lenovo ThinkPad X1 Carbon')">Lenovo ThinkPad X1 Carbon</li>
</ul>
</div>
 <!-- Booking Section -->
<div id="booking-section" class="booking-section">
<h3 id="selected-item">Product Name</h3>
<button class="book-btn" onclick="confirmBooking()">Book Now</button>
</div>
 
        <!-- Einstein AI Image -->
<img src="data:image/jpeg;base64,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" alt="AI SmartShop">
</div>
 
    <!-- JavaScript for Tabs and Booking -->
<script>

        function openTab(tabName) {

            var contents = document.getElementsByClassName("tab-content");

            for (var i = 0; i < contents.length; i++) {

                contents[i].style.display = "none";

            }

            document.getElementById(tabName).style.display = "block";

        }
 
        function showBooking(productName) {

            document.getElementById("selected-item").innerText = "Booking: " + productName;

            document.getElementById("booking-section").style.display = "block";

        }
 
        function confirmBooking() {

            alert("Your booking has been confirmed!");

            document.getElementById("booking-section").style.display = "none";

        }
</script>
 
    <!-- Salesforce Chatbot -->
<script>

        window.addEventListener('load', function() {

            window.embedded_svc = window.embedded_svc || {};

            window.embedded_svc.settings = {

                displayHelpButton: true,

                language: 'en-US',

                defaultMinimizedText: 'Chat with us',

                enabledFeatures: ['LiveAgent'],

                storageDomain: 'yourdomain.com'

            };
 
            var script = document.createElement('script');

            script.src = 'https://ORG_ID.salesforceliveagent.com/chat';

            script.onload = function() {

                embedded_svc.init('https://ORG_ID.my.salesforce.com', 'DEPLOYMENT_ID', 'your_deployment_path');

            };

            document.body.appendChild(script);

        });
</script>
 
</body>
</html>

 
