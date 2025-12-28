<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TechStore - Tu tienda online de tecnología</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* Variables de color y estilo */
        :root {
            --primary-color: #0366d6;
            --secondary-color: #24292e;
            --accent-color: #f9826c;
            --light-color: #f6f8fa;
            --dark-color: #1a1a1a;
            --success-color: #28a745;
            --warning-color: #ffc107;
            --danger-color: #dc3545;
            --gray-light: #e1e4e8;
            --gray-medium: #959da5;
            --gray-dark: #586069;
            --shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            --border-radius: 8px;
            --transition: all 0.3s ease;
        }
        
        /* Reset y estilos base */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: var(--dark-color);
            background-color: var(--light-color);
        }
        
        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Header y navegación */
        header {
            background-color: var(--secondary-color);
            color: white;
            padding: 15px 0;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: var(--shadow);
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 1.8rem;
            font-weight: 700;
            color: white;
            text-decoration: none;
        }
        
        .logo i {
            color: var(--accent-color);
        }
        
        .logo span {
            color: var(--primary-color);
        }
        
        .nav-links {
            display: flex;
            list-style: none;
            gap: 25px;
        }
        
        .nav-links a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: var(--transition);
            display: flex;
            align-items: center;
            gap: 5px;
        }
        
        .nav-links a:hover {
            color: var(--accent-color);
        }
        
        .cart-icon {
            position: relative;
        }
        
        .cart-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background-color: var(--accent-color);
            color: white;
            border-radius: 50%;
            width: 20px;
            height: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.7rem;
            font-weight: bold;
        }
        
        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
        }
        
        /* Hero section */
        .hero {
            background: linear-gradient(rgba(36, 41, 46, 0.9), rgba(36, 41, 46, 0.9)), url('https://images.unsplash.com/photo-1550745165-9bc0b252726f?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80');
            background-size: cover;
            background-position: center;
            color: white;
            padding: 80px 0;
            text-align: center;
        }
        
        .hero h1 {
            font-size: 3rem;
            margin-bottom: 20px;
        }
        
        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 30px;
            color: var(--gray-light);
        }
        
        .btn {
            display: inline-block;
            background-color: var(--primary-color);
            color: white;
            padding: 12px 30px;
            border-radius: var(--border-radius);
            text-decoration: none;
            font-weight: 600;
            border: none;
            cursor: pointer;
            transition: var(--transition);
        }
        
        .btn:hover {
            background-color: #0250b9;
            transform: translateY(-2px);
        }
        
        .btn-accent {
            background-color: var(--accent-color);
        }
        
        .btn-accent:hover {
            background-color: #f76847;
        }
        
        /* Sección de productos */
        .section-title {
            text-align: center;
            margin: 60px 0 40px;
            font-size: 2.2rem;
            color: var(--secondary-color);
        }
        
        .section-title span {
            color: var(--primary-color);
        }
        
        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 30px;
            margin-bottom: 60px;
        }
        
        .product-card {
            background-color: white;
            border-radius: var(--border-radius);
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }
        
        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.15);
        }
        
        .product-img {
            height: 200px;
            width: 100%;
            object-fit: cover;
        }
        
        .product-info {
            padding: 20px;
        }
        
        .product-title {
            font-size: 1.3rem;
            margin-bottom: 10px;
            color: var(--secondary-color);
        }
        
        .product-description {
            color: var(--gray-dark);
            margin-bottom: 15px;
            font-size: 0.95rem;
        }
        
        .product-price {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary-color);
            margin-bottom: 15px;
        }
        
        .product-rating {
            color: var(--warning-color);
            margin-bottom: 15px;
        }
        
        .add-to-cart {
            width: 100%;
            padding: 10px;
            background-color: var(--secondary-color);
            color: white;
            border: none;
            border-radius: var(--border-radius);
            cursor: pointer;
            font-weight: 600;
            transition: var(--transition);
        }
        
        .add-to-cart:hover {
            background-color: var(--primary-color);
        }
        
        /* Carrito de compras */
        .cart-modal {
            position: fixed;
            top: 0;
            right: -400px;
            width: 100%;
            max-width: 400px;
            height: 100%;
            background-color: white;
            box-shadow: -5px 0 15px rgba(0, 0, 0, 0.1);
            transition: var(--transition);
            z-index: 2000;
            display: flex;
            flex-direction: column;
        }
        
        .cart-modal.active {
            right: 0;
        }
        
        .cart-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px;
            border-bottom: 1px solid var(--gray-light);
        }
        
        .close-cart {
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--gray-dark);
        }
        
        .cart-items {
            flex: 1;
            overflow-y: auto;
            padding: 20px;
        }
        
        .cart-item {
            display: flex;
            margin-bottom: 20px;
            padding-bottom: 20px;
            border-bottom: 1px solid var(--gray-light);
        }
        
        .cart-item-img {
            width: 80px;
            height: 80px;
            object-fit: cover;
            border-radius: var(--border-radius);
            margin-right: 15px;
        }
        
        .cart-item-details {
            flex: 1;
        }
        
        .cart-item-title {
            font-weight: 600;
            margin-bottom: 5px;
        }
        
        .cart-item-price {
            color: var(--primary-color);
            font-weight: 600;
        }
        
        .cart-item-actions {
            display: flex;
            align-items: center;
            margin-top: 10px;
        }
        
        .quantity-btn {
            width: 30px;
            height: 30px;
            border-radius: 50%;
            border: 1px solid var(--gray-light);
            background-color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
        }
        
        .quantity {
            margin: 0 10px;
            font-weight: 600;
        }
        
        .remove-item {
            margin-left: auto;
            color: var(--danger-color);
            background: none;
            border: none;
            cursor: pointer;
        }
        
        .cart-footer {
            padding: 20px;
            border-top: 1px solid var(--gray-light);
        }
        
        .cart-total {
            display: flex;
            justify-content: space-between;
            font-size: 1.3rem;
            font-weight: 700;
            margin-bottom: 20px;
        }
        
        .checkout-btn {
            width: 100%;
            padding: 15px;
            background-color: var(--success-color);
            color: white;
            border: none;
            border-radius: var(--border-radius);
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
        }
        
        .checkout-btn:hover {
            background-color: #218838;
        }
        
        .overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            z-index: 1500;
            opacity: 0;
            visibility: hidden;
            transition: var(--transition);
        }
        
        .overlay.active {
            opacity: 1;
            visibility: visible;
        }
        
        /* Footer */
        footer {
            background-color: var(--secondary-color);
            color: white;
            padding: 50px 0 20px;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }
        
        .footer-column h3 {
            font-size: 1.3rem;
            margin-bottom: 20px;
            color: var(--accent-color);
        }
        
        .footer-links {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 10px;
        }
        
        .footer-links a {
            color: var(--gray-light);
            text-decoration: none;
            transition: var(--transition);
        }
        
        .footer-links a:hover {
            color: var(--accent-color);
            padding-left: 5px;
        }
        
        .social-icons {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }
        
        .social-icons a {
            color: white;
            font-size: 1.2rem;
            transition: var(--transition);
        }
        
        .social-icons a:hover {
            color: var(--accent-color);
        }
        
        .copyright {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: var(--gray-medium);
            font-size: 0.9rem;
        }
        
        /* Responsive */
        @media (max-width: 992px) {
            .hero h1 {
                font-size: 2.5rem;
            }
        }
        
        @media (max-width: 768px) {
            .nav-links {
                display: none;
                position: absolute;
                top: 100%;
                left: 0;
                width: 100%;
                background-color: var(--secondary-color);
                flex-direction: column;
                padding: 20px;
                box-shadow: 0 10px 15px rgba(0, 0, 0, 0.1);
            }
            
            .nav-links.active {
                display: flex;
            }
            
            .mobile-menu-btn {
                display: block;
            }
            
            .hero h1 {
                font-size: 2rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
            
            .cart-modal {
                max-width: 100%;
            }
        }
        
        @media (max-width: 480px) {
            .hero h1 {
                font-size: 1.8rem;
            }
            
            .section-title {
                font-size: 1.8rem;
            }
            
            .product-card {
                margin: 0 auto;
                max-width: 100%;
            }
        }
    </style>
</head>
<body>
    <!-- Header y navegación -->
    <header>
        <div class="container header-content">
            <a href="#" class="logo">
                <i class="fas fa-laptop-code"></i>
                Tech<span>Store</span>
            </a>
            
            <button class="mobile-menu-btn" id="mobileMenuBtn">
                <i class="fas fa-bars"></i>
            </button>
            
            <ul class="nav-links" id="navLinks">
                <li><a href="#"><i class="fas fa-home"></i> Inicio</a></li>
                <li><a href="#products"><i class="fas fa-box"></i> Productos</a></li>
                <li><a href="#"><i class="fas fa-tags"></i> Ofertas</a></li>
                <li><a href="#"><i class="fas fa-info-circle"></i> Nosotros</a></li>
                <li><a href="#"><i class="fas fa-envelope"></i> Contacto</a></li>
                <li>
                    <a href="#" class="cart-icon" id="cartIcon">
                        <i class="fas fa-shopping-cart"></i>
                        <span class="cart-count" id="cartCount">0</span>
                    </a>
                </li>
            </ul>
        </div>
    </header>

    <!-- Hero section -->
    <section class="hero">
        <div class="container">
            <h1>Los mejores productos tecnológicos</h1>
            <p>Descubre nuestra selección de laptops, accesorios, componentes y más. Envío gratis en pedidos superiores a $100.</p>
            <a href="#products" class="btn">Ver productos</a>
            <a href="#" class="btn btn-accent">Ofertas especiales</a>
        </div>
    </section>

    <!-- Sección de productos -->
    <section class="container">
        <h2 class="section-title">Nuestros <span>Productos</span></h2>
        
        <div class="products-grid" id="products">
            <!-- Los productos se cargarán dinámicamente con JavaScript -->
        </div>
    </section>

    <!-- Carrito de compras -->
    <div class="cart-modal" id="cartModal">
        <div class="cart-header">
            <h2>Tu Carrito</h2>
            <button class="close-cart" id="closeCart">
                <i class="fas fa-times"></i>
            </button>
        </div>
        
        <div class="cart-items" id="cartItems">
            <!-- Los productos del carrito se cargarán dinámicamente -->
            <p class="empty-cart-message" id="emptyCartMessage">Tu carrito está vacío</p>
        </div>
        
        <div class="cart-footer">
            <div class="cart-total">
                <span>Total:</span>
                <span id="cartTotal">$0.00</span>
            </div>
            <button class="checkout-btn" id="checkoutBtn">Proceder al pago</button>
        </div>
    </div>
    
    <div class="overlay" id="overlay"></div>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>TechStore</h3>
                    <p>Tu tienda online de confianza para productos tecnológicos. Calidad garantizada y envíos rápidos.</p>
                    <div class="social-icons">
                        <a href="#"><i class="fab fa-facebook"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-github"></i></a>
                    </div>
                </div>
                
                <div class="footer-column">
                    <h3>Enlaces rápidos</h3>
                    <ul class="footer-links">
                        <li><a href="#">Inicio</a></li>
                        <li><a href="#products">Productos</a></li>
                        <li><a href="#">Ofertas</a></li>
                        <li><a href="#">Sobre nosotros</a></li>
                        <li><a href="#">Contacto</a></li>
                    </ul>
                </div>
                
                <div class="footer-column">
                    <h3>Categorías</h3>
                    <ul class="footer-links">
                        <li><a href="#">Laptops</a></li>
                        <li><a href="#">Teclados</a></li>
                        <li><a href="#">Mouse</a></li>
                        <li><a href="#">Monitores</a></li>
                        <li><a href="#">Accesorios</a></li>
                    </ul>
                </div>
                
                <div class="footer-column">
                    <h3>Contacto</h3>
                    <ul class="footer-links">
                        <li><i class="fas fa-map-marker-alt"></i> Calle Tecnología 123, Ciudad Digital</li>
                        <li><i class="fas fa-phone"></i> +1 (555) 123-4567</li>
                        <li><i class="fas fa-envelope"></i> info@techstore.com</li>
                    </ul>
                </div>
            </div>
            
            <div class="copyright">
                <p>&copy; 2023 TechStore. Todos los derechos reservados. Este es un proyecto para GitHub.</p>
            </div>
        </div>
    </footer>

    <script>
        // Datos de productos
        const products = [
            {
                id: 1,
                name: "Laptop Gaming Pro",
                description: "Laptop de alto rendimiento para gaming y trabajo con procesador i7 y RTX 3060.",
                price: 1299.99,
                image: "https://images.unsplash.com/photo-1603302576837-37561b2e2302?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80",
                rating: 4,
                category: "Laptops"
            },
            {
                id: 2,
                name: "Teclado Mecánico RGB",
                description: "Teclado mecánico con switches azules y retroiluminación RGB personalizable.",
                price: 89.99,
                image: "https://images.unsplash.com/photo-1541140532154-b024d705b90a?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80",
                rating: 5,
                category: "Teclados"
            },
            {
                id: 3,
                name: "Mouse Inalámbrico",
                description: "Mouse ergonómico inalámbrico con sensor de alta precisión y batería de larga duración.",
                price: 49.99,
                image: "https://images.unsplash.com/photo-1527814050087-3793815479db?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80",
                rating: 4,
                category: "Mouse"
            },
            {
                id: 4,
                name: "Monitor 4K Ultra HD",
                description: "Monitor de 27 pulgadas con resolución 4K, panel IPS y frecuencia de actualización de 144Hz.",
                price: 449.99,
                image: "https://images.unsplash.com/photo-1593359677879-a4bb92f829d1?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80",
                rating: 5,
                category: "Monitores"
            },
            {
                id: 5,
                name: "Auriculares Gaming",
                description: "Auriculares con sonido envolvente 7.1, micrófono retráctil y almohadillas de memoria.",
                price: 79.99,
                image: "https://images.unsplash.com/photo-1585298723687-abc6f8a8a214?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80",
                rating: 4,
                category: "Accesorios"
            },
            {
                id: 6,
                name: "Webcam 4K",
                description: "Cámara web con resolución 4K, autofocus y micrófono integrado para videollamadas profesionales.",
                price: 129.99,
                image: "https://images.unsplash.com/photo-1556656793-08538906a9f8?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80",
                rating: 4,
                category: "Accesorios"
            },
            {
                id: 7,
                name: "Tablet Pro",
                description: "Tablet de 10.5 pulgadas con lápiz digital incluido, perfecta para diseñadores y estudiantes.",
                price: 599.99,
                image: "https://images.unsplash.com/photo-1544244015-0df4b3ffc6b0?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80",
                rating: 5,
                category: "Tablets"
            },
            {
                id: 8,
                name: "Disco Duro Externo 2TB",
                description: "Disco duro externo portátil de 2TB, USB 3.0, compatible con PC, Mac y consolas.",
                price: 89.99,
                image: "https://images.unsplash.com/photo-1581344987931-8d8e6c7dc9fb?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80",
                rating: 4,
                category: "Almacenamiento"
            }
        ];

        // Carrito de compras
        let cart = [];
        
        // Elementos del DOM
        const productsGrid = document.getElementById('products');
        const cartModal = document.getElementById('cartModal');
        const cartIcon = document.getElementById('cartIcon');
        const closeCart = document.getElementById('closeCart');
        const cartItems = document.getElementById('cartItems');
        const cartCount = document.getElementById('cartCount');
        const cartTotal = document.getElementById('cartTotal');
        const checkoutBtn = document.getElementById('checkoutBtn');
        const overlay = document.getElementById('overlay');
        const mobileMenuBtn = document.getElementById('mobileMenuBtn');
        const navLinks = document.getElementById('navLinks');
        const emptyCartMessage = document.getElementById('emptyCartMessage');

        // Cargar productos en la página
        function loadProducts() {
            productsGrid.innerHTML = '';
            
            products.forEach(product => {
                const productCard = document.createElement('div');
                productCard.className = 'product-card';
                
                // Crear estrellas de valoración
                let stars = '';
                for (let i = 1; i <= 5; i++) {
                    stars += `<i class="fas fa-star${i > product.rating ? '-half-alt' : ''}"></i>`;
                }
                
                productCard.innerHTML = `
                    <img src="${product.image}" alt="${product.name}" class="product-img">
                    <div class="product-info">
                        <h3 class="product-title">${product.name}</h3>
                        <p class="product-description">${product.description}</p>
                        <div class="product-rating">${stars}</div>
                        <div class="product-price">$${product.price.toFixed(2)}</div>
                        <button class="add-to-cart" data-id="${product.id}">Añadir al carrito</button>
                    </div>
                `;
                
                productsGrid.appendChild(productCard);
            });
            
            // Añadir event listeners a los botones de añadir al carrito
            document.querySelectorAll('.add-to-cart').forEach(button => {
                button.addEventListener('click', (e) => {
                    const productId = parseInt(e.target.getAttribute('data-id'));
                    addToCart(productId);
                });
            });
        }

        // Añadir producto al carrito
        function addToCart(productId) {
            const product = products.find(p => p.id === productId);
            const existingItem = cart.find(item => item.id === productId);
            
            if (existingItem) {
                existingItem.quantity += 1;
            } else {
                cart.push({
                    ...product,
                    quantity: 1
                });
            }
            
            updateCart();
            showNotification(`${product.name} añadido al carrito`);
        }

        // Eliminar producto del carrito
        function removeFromCart(productId) {
            cart = cart.filter(item => item.id !== productId);
            updateCart();
        }

        // Actualizar cantidad de producto en el carrito
        function updateQuantity(productId, newQuantity) {
            const item = cart.find(item => item.id === productId);
            
            if (item) {
                if (newQuantity < 1) {
                    removeFromCart(productId);
                } else {
                    item.quantity = newQuantity;
                }
            }
            
            updateCart();
        }

        // Actualizar la visualización del carrito
        function updateCart() {
            // Actualizar contador del carrito
            const totalItems = cart.reduce((sum, item) => sum + item.quantity, 0);
            cartCount.textContent = totalItems;
            
            // Actualizar lista de productos en el carrito
            cartItems.innerHTML = '';
            
            if (cart.length === 0) {
                emptyCartMessage.style.display = 'block';
            } else {
                emptyCartMessage.style.display = 'none';
                
                cart.forEach(item => {
                    const cartItem = document.createElement('div');
                    cartItem.className = 'cart-item';
                    
                    cartItem.innerHTML = `
                        <img src="${item.image}" alt="${item.name}" class="cart-item-img">
                        <div class="cart-item-details">
                            <h4 class="cart-item-title">${item.name}</h4>
                            <div class="cart-item-price">$${item.price.toFixed(2)}</div>
                            <div class="cart-item-actions">
                                <button class="quantity-btn decrease" data-id="${item.id}">-</button>
                                <span class="quantity">${item.quantity}</span>
                                <button class="quantity-btn increase" data-id="${item.id}">+</button>
                                <button class="remove-item" data-id="${item.id}">
                                    <i class="fas fa-trash"></i>
                                </button>
                            </div>
                        </div>
                    `;
                    
                    cartItems.appendChild(cartItem);
                });
                
                // Añadir event listeners a los botones del carrito
                document.querySelectorAll('.decrease').forEach(button => {
                    button.addEventListener('click', (e) => {
                        const productId = parseInt(e.target.getAttribute('data-id'));
                        const item = cart.find(item => item.id === productId);
                        updateQuantity(productId, item.quantity - 1);
                    });
                });
                
                document.querySelectorAll('.increase').forEach(button => {
                    button.addEventListener('click', (e) => {
                        const productId = parseInt(e.target.getAttribute('data-id'));
                        const item = cart.find(item => item.id === productId);
                        updateQuantity(productId, item.quantity + 1);
                    });
                });
                
                document.querySelectorAll('.remove-item').forEach(button => {
                    button.addEventListener('click', (e) => {
                        const productId = parseInt(e.target.closest('button').getAttribute('data-id'));
                        removeFromCart(productId);
                    });
                });
            }
            
            // Actualizar total
            const total = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            cartTotal.textContent = `$${total.toFixed(2)}`;
        }

        // Mostrar notificación
        function showNotification(message) {
            const notification = document.createElement('div');
            notification.style.cssText = `
                position: fixed;
                bottom: 20px;
                right: 20px;
                background-color: var(--success-color);
                color: white;
                padding: 15px 20px;
                border-radius: var(--border-radius);
                box-shadow: var(--shadow);
                z-index: 3000;
                transition: var(--transition);
                transform: translateY(100px);
                opacity: 0;
            `;
            
            notification.textContent = message;
            document.body.appendChild(notification);
            
            // Animación de entrada
            setTimeout(() => {
                notification.style.transform = 'translateY(0)';
                notification.style.opacity = '1';
            }, 10);
            
            // Eliminar notificación después de 3 segundos
            setTimeout(() => {
                notification.style.transform = 'translateY(100px)';
                notification.style.opacity = '0';
                setTimeout(() => {
                    document.body.removeChild(notification);
                }, 300);
            }, 3000);
        }

        // Abrir/cerrar carrito
        cartIcon.addEventListener('click', () => {
            cartModal.classList.add('active');
            overlay.classList.add('active');
            document.body.style.overflow = 'hidden';
        });

        closeCart.addEventListener('click', () => {
            cartModal.classList.remove('active');
            overlay.classList.remove('active');
            document.body.style.overflow = 'auto';
        });

        overlay.addEventListener('click', () => {
            cartModal.classList.remove('active');
            overlay.classList.remove('active');
            document.body.style.overflow = 'auto';
        });

        // Procesar compra
        checkoutBtn.addEventListener('click', () => {
            if (cart.length === 0) {
                showNotification('Tu carrito está vacío');
                return;
            }
            
            const total = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            showNotification(`¡Compra realizada por $${total.toFixed(2)}! Gracias por tu pedido.`);
            
            // Vaciar carrito
            cart = [];
            updateCart();
            
            // Cerrar carrito
            cartModal.classList.remove('active');
            overlay.classList.remove('active');
            document.body.style.overflow = 'auto';
        });

        // Menú móvil
        mobileMenuBtn.addEventListener('click', () => {
            navLinks.classList.toggle('active');
        });

        // Cerrar menú móvil al hacer clic en un enlace
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                navLinks.classList.remove('active');
            });
        });

        // Inicializar la página
        document.addEventListener('DOMContentLoaded', () => {
            loadProducts();
            updateCart();
        });
    </script>
</body>
</html>
