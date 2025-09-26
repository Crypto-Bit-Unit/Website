<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Julian Figurine Shop - Anime Collection</title>
    <!-- Bootstrap CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">
    <!-- Font Awesome for icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #f8f9fa;
        }

        .navbar-brand {
            font-weight: bold;
            font-size: 1.5rem;
            color: #007bff 
        }

        .card {
            transition: transform 0.2s ease, box-shadow 0.2s ease;
            border: none;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }

        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
        }

        .card-img-top {
            height: 250px;
            object-fit: cover;
            transition: transform 0.3s ease;
        }

        .card:hover .card-img-top {
            transform: scale(1.05);
        }

        .card-title {
            font-weight: bold;
            color: #333;
        }

        .card-text {
            font-size: 1.25rem;
            font-weight: bold;
            color: #28a745;
        }

        .btn-primary {
            background-color: #007bff;
            border: none;
            border-radius: 25px;
            padding: 10px 20px;
            transition: all 0.3s ease;
            font-weight: bold;
        }

        .btn-primary:hover {
            background-color: #0056b3;
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(0, 123, 255, 0.3);
        }

        .btn-success {
            background-color: #28a745;
            border: none;
        }

        .btn-success:hover {
            background-color: #218838;
        }

        .cart-badge {
            background-color: #dc3545;
            color: white;
            border-radius: 50%;
            padding: 2px 6px;
            font-size: 0.75rem;
            position: relative;
            top: -10px;
            left: -10px;
        }

        footer {
            background-color: #f8f9fa;
            border-top: 1px solid #dee2e6;
            margin-top: auto;
        }

        .hero-section {
            background: linear-gradient(135deg, #007bff, #0056b3);
            color: white;
            padding: 60px 0;
            text-align: center;
            margin-bottom: 50px;
        }

        .hero-section h1 {
            font-size: 2.5rem;
            font-weight: bold;
            margin-bottom: 10px;
        }

        .hero-section p {
            font-size: 1.2rem;
        }

        .cart-modal .modal-header {
            background-color: #007bff;
            color: white;
        }

        .cart-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 10px 0;
            border-bottom: 1px solid #dee2e6;
        }

        .total-price {
            font-size: 1.5rem;
            font-weight: bold;
            color: #28a745;
        }

        /* Responsive adjustments */
        @media (max-width: 768px) {
            .hero-section h1 {
                font-size: 2rem;
            }
            .card-img-top {
                height: 200px;
            }
        }
    </style>
</head>
<body>
    <!-- Navbar -->
    <nav class="navbar navbar-expand-lg navbar-light bg-white shadow-sm fixed-top">
        <div class="container">
            <a class="navbar-brand" href="#home">
                <i class="fas fa-shopping-bag me-2"></i>Julian Figurine Shop
            </a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNav">
                <ul class="navbar-nav me-auto">
                    <li class="nav-item">
                        <a class="nav-link" href="#home">Home</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#products">Products</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#location">Location</a>
                    </li>
                </ul>
                <ul class="navbar-nav">
                    <li class="nav-item position-relative">
                        <a class="nav-link" href="#" data-bs-toggle="modal" data-bs-target="#cartModal">
                            <i class="fas fa-shopping-cart me-1"></i>Cart
                            <span id="cartCount" class="cart-badge" style="display: none;">0</span>
                        </a>
                    </li>
                </ul>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero-section">
        <div class="container">
            <h1>Welcome to Julian Figurine Shop</h1>
            <p></p>
        </div>
    </section>

    <!-- Products Section -->
    <section id="products" class="container my-5">
        <h2 class="text-center mb-5">Our Collection</h2>
        <div class="row" id="productGrid">
        </div>
    </section>

    <!-- Location Section -->
    <section id="location" class="container my-5">
        <h2 class="text-center mb-4">Our Location</h2>
        <div class="row justify-content-center">
            <div class="col-md-8">
                <div class="card">
                    <div class="card-body text-center">
                        <i class="fas fa-map-marker-alt fa-3x text-primary mb-3"></i>
                        <h5>Julian Figurine Shop</h5>
                        <p class="card-text">123 Anime Street, Manila, Philippines<br>Opening Hours: Mon-Sat 10AM-8PM</p>
                        <a href="https://maps.google.com" target="_blank" class="btn btn-outline-primary">View on Google Maps</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Cart Modal -->
    <div class="modal fade" id="cartModal" tabindex="-1" aria-labelledby="cartModalLabel" aria-hidden="true">
        <div class="modal-dialog modal-lg">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title" id="cartModalLabel">
                        <i class="fas fa-shopping-cart me-2"></i>Shopping Cart
                    </h5>
                    <button type="button" class="btn-close btn-close-white" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>
                <div class="modal-body" id="cartBody">
                    <p class="text-center text-muted" id="emptyCartMsg">Your cart is empty. Start shopping!</p>
                    <div id="cartItems"></div>
                </div>
                <div class="modal-footer">
                    <div class="w-100 d-flex justify-content-between align-items-center">
                        <h5>Total: <span id="totalPrice" class="total-price">₱0</span></h5>
                        <div>
                            <button type="button" class="btn btn-secondary me-2" data-bs-dismiss="modal">Continue Shopping</button>
                            <button type="button" class="btn btn-success" id="checkoutBtn">Checkout</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer class="bg-light text-center py-4 mt-auto">
        <div class="container">
            <p class="mb-0">&copy; 2024 Julian Figurine Shop. All rights reserved. | <a href="#privacy" class="text-decoration-none">Privacy Policy</a></p>
        </div>
    </footer>

    <!-- Bootstrap JS -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz" crossorigin="anonymous"></script>
    <!-- Custom JS -->
    <script>
        const products = [
            {
                id: 1,
                name: 'Itsuki Nakano Figurine',
                price: 1200,
                image: 'https://down-ph.img.susercontent.com/file/b69227515e819a00daae72cb12d4b1a9',
                alt: 'Itsuki Nakano anime figurine'
            },
            {
                id: 2,
                name: 'Miku Nakano Figurine',
                price: 1200,
                image: 'https://i.ebayimg.com/images/g/N94AAOSwf2Vhg4Tm/s-l1200.jpg',
                alt: 'Miku Nakano anime figurine'
            },
            {
                id: 3,
                name: 'Nino Nakano Figurine',
                price: 1200,
                image: 'https://down-ph.img.susercontent.com/file/67ffbb72b8c21bb807ad8c3d73dbfaf3',
                alt: 'Nino Nakano anime figurine'
            },
            {
                id: 4,
                name: 'Yotsuba Nakano Figurine',
                price: 1200,
                image: 'https://down-ph.img.susercontent.com/file/1119aa4639761ca0b8cf485574078463',
                alt: 'Yotsuba Nakano anime figurine'
            },
            {
                id: 5,
                name: 'Ichika Nakano Figurine',
                price: 1200,
                image: 'https://down-ph.img.susercontent.com/file/c86fdbc1d753791beeb1155abb7bfafd',
                alt: 'Ichika Nakano anime figurine'
            },
            {
                id: 6,
                name: 'The Quintessential Quintuplets Manga Set',
                price: 1200,
                image: 'https://images-na.ssl-images-amazon.com/images/S/compressed.photo.goodreads.com/books/1699871819i/131775922.jpg',
                alt: 'Quintessential Quintuplets manga set'
            }
        ];

        // Cart management
        let cart = JSON.parse(localStorage.getItem('cart')) || [];

        // Function to render products
        function renderProducts() {
            const productGrid = document.getElementById('productGrid');
            productGrid.innerHTML = products.map(product => `
                <div class="col-md-4 col-sm-6 mb-4">
                    <div class="card h-100">
                        <img src="${product.image}" class="card-img-top" alt="${product.alt}" loading="lazy">
                        <div class="card-body d-flex flex-column">
                            <h5 class="card-title">${product.name}</h5>
                            <p class="card-text mt-auto">₱${product.price.toLocaleString()}</p>
                            <button class="btn btn-primary w-100 mt-2 add-to-cart-btn" data-id="${product.id}" data-name="${product.name}" data-price="${product.price}">
                                <i class="fas fa-cart-plus me-1"></i>Add to Cart
                            </button>
                        </div>
                    </div>
                </div>
            `).join('');
        }

        // Function to update cart count
        function updateCartCount() {
            const cartCount = document.getElementById('cartCount');
            const count = cart.reduce((total, item) => total + item.quantity, 0);
            cartCount.textContent = count;
            cartCount.style.display = count > 0 ? 'inline' : 'none';
        }

        // Function to add to cart
        function addToCart(id, name, price) {
            const existingItem = cart.find(item => item.id === id);
            if (existingItem) {
                existingItem.quantity += 1;
            } else {
                cart.push({ id, name, price, quantity: 1 });
            }
            localStorage.setItem('cart', JSON.stringify(cart));
            updateCartCount();
            // Show success toast (using Bootstrap toast)
            showToast('Item added to cart!', 'success');
        }

        // Function to render cart modal
        function renderCart() {
            const cartBody = document.getElementById('cartBody');
            const cartItems = document.getElementById('cartItems');
            const emptyCartMsg = document.getElementById('emptyCartMsg');
            const totalPrice = document.getElementById('totalPrice');

            if (cart.length === 0) {
                emptyCartMsg.style.display = 'block';
                cartItems.innerHTML = '';
                totalPrice.textContent = '₱0';
                return;
            }

            emptyCartMsg.style.display = 'none';
            cartItems.innerHTML = cart.map(item => `
                <div class="cart-item">
                    <div>
                        <strong>${item.name}</strong> (x${item.quantity})
                    </div>
                    <div class="d-flex align-items-center">
                        <span>₱${(item.price * item.quantity).toLocaleString()}</span>
                        <button class="btn btn-sm btn-outline-danger ms-2" onclick="removeFromCart(${item.id})">
                            <i class="fas fa-trash"></i>
                        </button>
                    </div>
                </div>
            `).join('');

            const total = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            totalPrice.textContent = `₱${total.toLocaleString()}`;
        }

        // Function to remove from cart
        function removeFromCart(id) {
            cart = cart.filter(item => item.id !== id);
            localStorage.setItem('cart', JSON.stringify(cart));
            renderCart();
            updateCartCount();
            showToast('Item removed from cart!', 'warning');
        }

        // Function to show toast notification (simple alert fallback for demo)
        function showToast(message, type) {
            // For production, use Bootstrap Toast component
            alert(`${message}`);
        }

        // Event listeners
        document.addEventListener('DOMContentLoaded', function() {
            renderProducts();
            updateCartCount();
            renderCart();

            // Delegate add to cart events
            document.addEventListener('click', function(e) {
                if (e.target.classList.contains('add-to-cart-btn')) {
                    const id = parseInt(e.target.dataset.id);
                    const name = e.target.dataset.name;
                    const price = parseInt(e.target.dataset.price);
                    addToCart(id, name, price);
                    e.target.innerHTML = '<i class="fas fa-check me-1"></i>Added!';
                    setTimeout(() => {
                        e.target.innerHTML = '<i class="fas fa-cart-plus me-1"></i>Add to Cart';
                    }, 2000);
                }
            });

            // Checkout button
            document.getElementById('checkoutBtn').addEventListener('click', function() {
                if (cart.length === 0) return;
                showToast('Redirecting to checkout... (Demo)', 'info');
                // In production: Redirect to payment gateway
                cart = [];
                localStorage.removeItem('cart');
                updateCartCount();
                renderCart();
                bootstrap.Modal.getInstance(document.getElementById('cartModal')).hide();
            });

            // Smooth scrolling for nav links
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function (e) {
                    e.preventDefault();
                    const target = document.querySelector(this.getAttribute('href'));
                    if (target) {
                        target.scrollIntoView({ behavior: 'smooth', block: 'start' });
                    }
                });
            });
        });

        document.getElementById('cartModal').addEventListener('show.bs.modal', renderCart);
    </script>
</body>
</html>
