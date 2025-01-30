<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TechnoLine Store</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f1f1f1;
        }
        header {
            background-color: #333;
            color: #fff;
            padding: 10px 0;
            text-align: center;
        }
        header h1, header h2 {
            margin: 10px 0;
        }
        .container {
            max-width: 1200px;
            margin: 20px auto;
            padding: 20px;
            background-color: #fff;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .product {
            display: flex;
            justify-content: space-between;
            border-bottom: 1px solid #ddd;
            padding: 10px 0;
        }
        .product:last-child {
            border-bottom: none;
        }
        .product button {
            padding: 5px 10px;
            background-color: #28a745;
            color: #fff;
            border: none;
            cursor: pointer;
        }
        .product button:hover {
            background-color: #218838;
        }
        .cart {
            margin-top: 20px;
            padding: 10px;
            border: 1px solid #ddd;
        }
        .cart h3 {
            margin: 0 0 10px 0;
        }
    </style>
</head>
<body>
    <header>
        <h1>TechnoLine Store</h1>
        <h2>Best shop for Microsoft products and photocopy/printouts</h2>
    </header>
    <div class="container">
        <div class="product">
            <span>Microsoft Office 2024 Pro Plus</span>
            <span>₹10</span>
            <button onclick="addToCart('Microsoft Office 2024 Pro Plus', 10)">Add to Cart</button>
        </div>
        <div class="product">
            <span>Microsoft Office 2021 Pro Plus</span>
            <span>₹10</span>
            <button onclick="addToCart('Microsoft Office 2021 Pro Plus', 10)">Add to Cart</button>
        </div>
        <div class="product">
            <span>Microsoft Office 2019 Pro Plus</span>
            <span>₹10</span>
            <button onclick="addToCart('Microsoft Office 2019 Pro Plus', 10)">Add to Cart</button>
        </div>
        <div class="product">
            <span>Windows 10 installation</span>
            <span>₹8</span>
            <button onclick="addToCart('Windows 10 installation', 8)">Add to Cart</button>
        </div>
        <div class="product">
            <span>Windows 11 installation</span>
            <span>₹10</span>
            <button onclick="addToCart('Windows 11 installation', 10)">Add to Cart</button>
        </div>
        <div class="product">
            <span>Windows 10 activation</span>
            <span>₹5</span>
            <button onclick="addToCart('Windows 10 activation', 5)">Add to Cart</button>
        </div>
        <div class="product">
            <span>Windows 11 activation</span>
            <span>₹5</span>
            <button onclick="addToCart('Windows 11 activation', 5)">Add to Cart</button>
        </div>
        <div class="product">
            <span>Printout</span>
            <span>₹5</span>
            <button onclick="addToCart('Printout', 5)">Add to Cart</button>
        </div>
        <div class="product">
            <span>Xerox/Photocopy</span>
            <span>₹2</span>
            <button onclick="addToCart('Xerox/Photocopy', 2)">Add to Cart</button>
        </div>
        <div class="cart">
            <h3>Cart</h3>
            <ul id="cart-items"></ul>
            <p>Total: ₹<span id="total">0</span></p>
            <button onclick="checkout()">Checkout</button>
        </div>
    </div>
    <script>
        let cart = [];
        function addToCart(product, price) {
            cart.push({ product, price });
            displayCart();
        }
        function displayCart() {
            const cartItems = document.getElementById('cart-items');
            const total = document.getElementById('total');
            cartItems.innerHTML = '';
            let totalPrice = 0;
            cart.forEach(item => {
                const li = document.createElement('li');
                li.textContent = `${item.product} - ₹${item.price}`;
                cartItems.appendChild(li);
                totalPrice += item.price;
            });
            total.textContent = totalPrice;
        }
        function checkout() {
            const message = cart.map(item => `${item.product} - ₹${item.price}`).join('\n');
            const whatsappUrl = `https://api.whatsapp.com/send?phone=8101582919&text=${encodeURIComponent(message)}`;
            window.open(whatsappUrl, '_blank');
        }
    </script>
</body>
</html>
