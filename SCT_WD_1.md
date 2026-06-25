

# SKILLCRAFT-TECHNOLOGY-

                                                TASK-1(LANDING PAGE): CLOCKIT
My first task as a web-developer intern at skillcraft-technology and I am very excited and full of motivation for learning new things and improvments in my skills and codings too. As a web developer I think you should have a good prompt skills to create an idea from AI and exicute it, But I also think that the creation and exicution still pending without our final touch. So with this enthusiasm and motive I completed my first task to make a beautiful and presentable landing page for wall clocks as CLOCKIT...

                                                          QUESTION:
Create an interactive navigation
menu that changes color or style
when scrolled or when hovering
over a menu item. 
The navigation menu should
have a fixed position and be
visible on all pages.

                                                      CODE AND EXICUTION:
FILE:  [index.html](https://github.com/user-attachments/files/29337172/index.html)

FOR PHONES AND LIVE VIEW: https://clockitgg.netlify.app/


CODE:  title > CLOCKIT | Celestial Chronology & Space-Time Loops</title>
<!-- Glowing Background Elements for Luxury Ambience -->
<div class="glow-bg-container" aria-hidden="true">
    <div class="ambient-glow glow-1"></div>
    <div class="ambient-glow glow-2"></div>
    <!-- Time Loops & Clocks Background Animation -->
    <div class="bg-time-loops" id="bg-time-loops"></div>
</div>

<!-- Header / Scroll-Morphing Navigation Bar -->
<header class="navbar" id="navbar">
    <div class="nav-container">
        <a href="#" class="logo">
            <svg class="logo-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <circle cx="12" cy="12" r="10"></circle>
                <polyline points="12 6 12 12 16 14"></polyline>
            </svg>
            <span class="logo-text">CLOCK<span>IT</span></span>
        </a>

        <nav class="nav-links" id="nav-links">
            <a href="#home" class="nav-item active">Home</a>
            <a href="#collection" class="nav-item">Collection</a>
            <a href="#customizer" class="nav-item">Customizer</a>
            <a href="#world-time" class="nav-item">Global Loops</a>
            <a href="#philosophy" class="nav-item">Craftsmanship</a>
            <a href="#testimonials" class="nav-item">Reviews</a>
            <a href="#contact" class="nav-item">Contact</a>
        </nav>

        <div class="nav-actions">
            <button class="tracking-btn" id="tracking-drawer-btn" aria-label="Track Orders" style="background:transparent; border:none; color:var(--text-primary); cursor:pointer; font-family:var(--font-heading); display:flex; align-items:center; gap:6px; margin-right:12px; transition:var(--transition-quick);">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="icon" style="width:20px; height:20px;">
                    <circle cx="12" cy="12" r="10"></circle>
                    <polyline points="12 6 12 12 16 14"></polyline>
                </svg>
                <span class="tracking-label" style="font-size:0.9rem; font-weight:600;">My Orders</span>
            </button>
            <button class="cart-btn" aria-label="Shopping Cart">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="icon">
                    <circle cx="9" cy="21" r="1"></circle>
                    <circle cx="20" cy="21" r="1"></circle>
                    <path d="M1 1h4l2.68 13.39a2 2 0 0 0 2 1.61h9.72a2 2 0 0 0 2-1.61L23 6H6"></path>
                </svg>
                <span class="cart-badge" id="cart-badge">0</span>
            </button>
            <button class="menu-toggle" id="menu-toggle" aria-label="Toggle Menu">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="icon open-icon">
                    <line x1="3" y1="12" x2="21" y2="12"></line>
                    <line x1="3" y1="6" x2="21" y2="6"></line>
                    <line x1="3" y1="18" x2="21" y2="18"></line>
                </svg>
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="icon close-icon">
                    <line x1="18" y1="6" x2="6" y2="18"></line>
                    <line x1="6" y1="6" x2="18" y2="18"></line>
                </svg>
            </button>
        </div>
    </div>
</header>

<!-- Home / Hero Section -->
<section class="hero-section" id="home">
    <div class="hero-bg-glow"></div>
    <div class="hero-container">
        <div class="hero-content">
            <span class="badge-accent">SKILLCRAFT LUXURY TIMEPIECES</span>
            <h1 class="hero-title">Crafting Time <br><span class="gradient-text">Into Pure Art</span></h1>
            <p class="hero-subtitle">
                Experience the silent sweep of precision-crafted luxury. Our wall clocks merge advanced technology with natural finishes to redefine modern spaces.
            </p>
            <div class="hero-buttons">
                <a href="#collection" class="btn btn-primary">
                    <span>Explore Collection</span>
                    <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="btn-icon">
                        <line x1="5" y1="12" x2="19" y2="12"></line>
                        <polyline points="12 5 19 12 12 19"></polyline>
                    </svg>
                </a>
                <a href="#customizer" class="btn btn-secondary">
                    <span>Customize Clock</span>
                </a>
            </div>
            <div class="hero-stats">
                <div class="stat-item">
                    <span class="stat-num">0 dB</span>
                    <span class="stat-label">Silent Sweep</span>
                </div>
                <div class="stat-divider"></div>
                <div class="stat-item">
                    <span class="stat-num">100%</span>
                    <span class="stat-label">Premium Materials</span>
                </div>
                <div class="stat-divider"></div>
                <div class="stat-item">
                    <span class="stat-num">5 Yr</span>
                    <span class="stat-label">Warranty</span>
                </div>
            </div>
        </div>
        
        <div class="hero-visual">
            <div class="clock-display-card">
                <!-- Real ticking clock synced to system time -->
                <div class="interactive-clock" id="hero-clock">
                    <div class="clock-face">
                        <div class="glow-ring"></div>
                        <div class="center-pin"></div>
                        <!-- Dial hour indicators -->
                        <div class="indicator ind-12"></div>
                        <div class="indicator ind-3"></div>
                        <div class="indicator ind-6"></div>
                        <div class="indicator ind-9"></div>
                        <!-- Hands -->
                        <div class="hand hour-hand" id="hero-hour"></div>
                        <div class="hand minute-hand" id="hero-min"></div>
                        <div class="hand second-hand" id="hero-sec"></div>
                    </div>
                </div>
                <div class="clock-meta">
                    <div class="meta-title">The Horizon Pro</div>
                    <div class="meta-desc">Live Virtual Showcase (Ticking Active)</div>
                    <div class="meta-time" id="digital-clock">00:00:00 PM</div>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- Product Collection (16 Designs & Prices) -->
<section class="collection-section" id="collection">
    <div class="section-container">
        <div class="section-header">
            <span class="section-tag">OUR CATALOG</span>
            <h2 class="section-title">The Masterpiece Collection</h2>
            <p class="section-subtitle">Exquisite wall clock designs curated for minimalist, industrial, classic, and futuristic architectures.</p>
        </div>

        <div class="collection-grid">
            <!-- Card 1: Minimalist Aura -->
            <div class="product-card" data-id="1">
                <div class="product-img-box">
                    <span class="product-badge badge-sale">Best Seller</span>
                    <img src="assets/nordic_clock.png" alt="Minimalist Aura Wall Clock" class="product-img">
                    <div class="card-overlay">
                        <button class="btn-quickview">Quick View</button>
                    </div>
                </div>
                <div class="product-info">
                    <span class="product-cat">Scandinavian Series</span>
                    <h3 class="product-title">Minimalist Aura</h3>
                    <div class="product-rating">
                        <span class="stars">★★★★★</span>
                        <span class="rating-count">(48)</span>
                    </div>
                    <div class="product-price-row">
                        <div class="price-box">
                            <span class="old-price">$199.00</span>
                            <span class="current-price">$149.00</span>
                        </div>
                        <button class="btn-add-cart" aria-label="Add to cart">
                            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="cart-icon">
                                <path d="M12 5v14M5 12h14"></path>
                            </svg>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Card 2: Chrono Gear -->
            <div class="product-card" data-id="2">
                <div class="product-img-box">
                    <span class="product-badge badge-new">New Release</span>
                    <img src="assets/gear_clock.png" alt="Chrono Gear Wall Clock" class="product-img">
                    <div class="card-overlay">
                        <button class="btn-quickview">Quick View</button>
                    </div>
                </div>
                <div class="product-info">
                    <span class="product-cat">Industrial Series</span>
                    <h3 class="product-title">Chrono Gear</h3>
                    <div class="product-rating">
                        <span class="stars">★★★★★</span>
                        <span class="rating-count">(35)</span>
                    </div>
                    <div class="product-price-row">
                        <div class="price-box">
                            <span class="old-price">$349.00</span>
                            <span class="current-price">$289.00</span>
                        </div>
                        <button class="btn-add-cart" aria-label="Add to cart">
                            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="cart-icon">
                                <path d="M12 5v14M5 12h14"></path>
                            </svg>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Card 3: Roman Marble -->
            <div class="product-card" data-id="3">
                <div class="product-img-box">
                    <img src="assets/marble_clock.png" alt="Roman Marble Wall Clock" class="product-img">
                    <div class="card-overlay">
                        <button class="btn-quickview">Quick View</button>
                    </div>
                </div>
                <div class="product-info">
                    <span class="product-cat">Classic Series</span>
                    <h3 class="product-title">Roman Marble</h3>
                    <div class="product-rating">
                        <span class="stars">★★★★★</span>
                        <span class="rating-count">(61)</span>
                    </div>
                    <div class="product-price-row">
                        <div class="price-box">
                            <span class="old-price">$299.00</span>
                            <span class="current-price">$229.00</span>
                        </div>
                        <button class="btn-add-cart" aria-label="Add to cart">
                            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="cart-icon">
                                <path d="M12 5v14M5 12h14"></path>
                            </svg>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Card 4: Nebula Eclipse -->
            <div class="product-card" data-id="4">
                <div class="product-img-box">
                    <span class="product-badge badge-sale">25% OFF</span>
                    <img src="assets/nebula_clock.png" alt="Nebula Eclipse Wall Clock" class="product-img">
                    <div class="card-overlay">
                        <button class="btn-quickview">Quick View</button>
                    </div>
                </div>
                <div class="product-info">
                    <span class="product-cat">Cosmic Series</span>
                    <h3 class="product-title">Nebula Eclipse</h3>
                    <div class="product-rating">
                        <span class="stars">★★★★★</span>
                        <span class="rating-count">(19)</span>
                    </div>
                    <div class="product-price-row">
                        <div class="price-box">
                            <span class="old-price">$249.00</span>
                            <span class="current-price">$189.00</span>
                        </div>
                        <button class="btn-add-cart" aria-label="Add to cart">
                            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="cart-icon">
                                <path d="M12 5v14M5 12h14"></path>
                            </svg>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Card 5: Smart Horizon -->
            <div class="product-card" data-id="5">
                <div class="product-img-box">
                    <span class="product-badge badge-new">Exclusive</span>
                    <img src="assets/led_clock.png" alt="Smart Horizon Wall Clock" class="product-img">
                    <div class="card-overlay">
                        <button class="btn-quickview">Quick View</button>
                    </div>
                </div>
                <div class="product-info">
                    <span class="product-cat">Futuristic Series</span>
                    <h3 class="product-title">Smart Horizon</h3>
                    <div class="product-rating">
                        <span class="stars">★★★★★</span>
                        <span class="rating-count">(42)</span>
                    </div>
                    <div class="product-price-row">
                        <div class="price-box">
                            <span class="old-price">$399.00</span>
                            <span class="current-price">$329.00</span>
                        </div>
                        <button class="btn-add-cart" aria-label="Add to cart">
                            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="cart-icon">
                                <path d="M12 5v14M5 12h14"></path>
                            </svg>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Card 6: Abstract Geo -->
            <div class="product-card" data-id="6">
                <div class="product-img-box">
                    <img src="assets/abstract_clock.png" alt="Abstract Geo Wall Clock" class="product-img">
                    <div class="card-overlay">
                        <button class="btn-quickview">Quick View</button>
                    </div>
                </div>
                <div class="product-info">
                    <span class="product-cat">Art Gallery Series</span>
                    <h3 class="product-title">Abstract Geo</h3>
                    <div class="product-rating">
                        <span class="stars">★★★★★</span>
                        <span class="rating-count">(27)</span>
                    </div>
                    <div class="product-price-row">
                        <div class="price-box">
                            <span class="old-price">$319.00</span>
                            <span class="current-price">$259.00</span>
                        </div>
                        <button class="btn-add-cart" aria-label="Add to cart">
                            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="cart-icon">
                                <path d="M12 5v14M5 12h14"></path>
                            </svg>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Card 7: Carrara Gold -->
            <div class="product-card" data-id="7">
                <div class="product-img-box">
                    <span class="product-badge badge-new">Carrara Gold</span>
                    <img src="assets/luxury_marble_clock.png" alt="Carrara Gold Wall Clock" class="product-img">
                    <div class="card-overlay">
                        <button class="btn-quickview">Quick View</button>
                    </div>
                </div>
                <div class="product-info">
                    <span class="product-cat">Marble Series</span>
                    <h3 class="product-title">Carrara Gold</h3>
                    <div class="product-rating">
                        <span class="stars">★★★★★</span>
                        <span class="rating-count">(31)</span>
                    </div>
                    <div class="product-price-row">
                        <div class="price-box">
                            <span class="old-price">$399.00</span>
                            <span class="current-price">$349.00</span>
                        </div>
                        <button class="btn-add-cart" aria-label="Add to cart">
                            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="cart-icon">
                                <path d="M12 5v14M5 12h14"></path>
                            </svg>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Card 8: Monstera Brass -->
            <div class="product-card" data-id="8">
                <div class="product-img-box">
                    <img src="assets/umbrella_clock.svg" alt="Monstera Brass Wall Clock" class="product-img">
                    <div class="card-overlay">
                        <button class="btn-quickview">Quick View</button>
                    </div>
                </div>
                <div class="product-info">
                    <span class="product-cat">Botanical Series</span>
                    <h3 class="product-title">Monstera Brass</h3>
                    <div class="product-rating">
                        <span class="stars">★★★★★</span>
                        <span class="rating-count">(37)</span>
                    </div>
                    <div class="product-price-row">
                        <div class="price-box">
                            <span class="old-price">$219.00</span>
                            <span class="current-price">$169.00</span>
                        </div>
                        <button class="btn-add-cart" aria-label="Add to cart">
                            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="cart-icon">
                                <path d="M12 5v14M5 12h14"></path>
                            </svg>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Card 9: Zen Slate -->
            <div class="product-card" data-id="9">
                <div class="product-img-box">
                    <span class="product-badge badge-sale">Slate Stone</span>
                    <img src="assets/radish_clock.svg" alt="Zen Slate Wall Clock" class="product-img">
                    <div class="card-overlay">
                        <button class="btn-quickview">Quick View</button>
                    </div>
                </div>
                <div class="product-info">
                    <span class="product-cat">Minimalist Series</span>
                    <h3 class="product-title">Zen Slate</h3>
                    <div class="product-rating">
                        <span class="stars">★★★★★</span>
                        <span class="rating-count">(29)</span>
                    </div>
                    <div class="product-price-row">
                        <div class="price-box">
                            <span class="old-price">$279.00</span>
                            <span class="current-price">$219.00</span>
                        </div>
                        <button class="btn-add-cart" aria-label="Add to cart">
                            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="cart-icon">
                                <path d="M12 5v14M5 12h14"></path>
                            </svg>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Card 10: Stardust Matrix -->
            <div class="product-card" data-id="10">
                <div class="product-img-box">
                    <span class="product-badge badge-new">Matrix Glow</span>
                    <img src="assets/candy_clock.svg" alt="Stardust Matrix Wall Clock" class="product-img">
                    <div class="card-overlay">
                        <button class="btn-quickview">Quick View</button>
                    </div>
                </div>
                <div class="product-info">
                    <span class="product-cat">Cyber Series</span>
                    <h3 class="product-title">Stardust Matrix</h3>
                    <div class="product-rating">
                        <span class="stars">★★★★★</span>
                        <span class="rating-count">(49)</span>
                    </div>
                    <div class="product-price-row">
                        <div class="price-box">
                            <span class="old-price">$179.00</span>
                            <span class="current-price">$129.00</span>
                        </div>
                        <button class="btn-add-cart" aria-label="Add to cart">
                            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="cart-icon">
                                <path d="M12 5v14M5 12h14"></path>
                            </svg>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Card 11: Chrono Horizon -->
            <div class="product-card" data-id="11">
                <div class="product-img-box">
                    <img src="assets/portal_clock.svg" alt="Chrono Horizon Wall Clock" class="product-img">
                    <div class="card-overlay">
                        <button class="btn-quickview">Quick View</button>
                    </div>
                </div>
                <div class="product-info">
                    <span class="product-cat">Horology Series</span>
                    <h3 class="product-title">Chrono Horizon</h3>
                    <div class="product-rating">
                        <span class="stars">★★★★★</span>
                        <span class="rating-count">(46)</span>
                    </div>
                    <div class="product-price-row">
                        <div class="price-box">
                            <span class="old-price">$389.00</span>
                            <span class="current-price">$319.00</span>
                        </div>
                        <button class="btn-add-cart" aria-label="Add to cart">
                            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="cart-icon">
                                <path d="M12 5v14M5 12h14"></path>
                            </svg>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Card 12: Titanium Guardian -->
            <div class="product-card" data-id="12">
                <div class="product-img-box">
                    <span class="product-badge badge-sale">Titanium</span>
                    <img src="assets/robot_clock.svg" alt="Titanium Guardian Wall Clock" class="product-img">
                    <div class="card-overlay">
                        <button class="btn-quickview">Quick View</button>
                    </div>
                </div>
                <div class="product-info">
                    <span class="product-cat">Futuristic Series</span>
                    <h3 class="product-title">Titanium Guardian</h3>
                    <div class="product-rating">
                        <span class="stars">★★★★★</span>
                        <span class="rating-count">(53)</span>
                    </div>
                    <div class="product-price-row">
                        <div class="price-box">
                            <span class="old-price">$399.00</span>
                            <span class="current-price">$349.00</span>
                        </div>
                        <button class="btn-add-cart" aria-label="Add to cart">
                            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="cart-icon">
                                <path d="M12 5v14M5 12h14"></path>
                            </svg>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Card 13: Obsidian Eclipse -->
            <div class="product-card" data-id="13">
                <div class="product-img-box">
                    <img src="assets/obsidian_eclipse.svg" alt="Obsidian Eclipse Wall Clock" class="product-img">
                    <div class="card-overlay">
                        <button class="btn-quickview">Quick View</button>
                    </div>
                </div>
                <div class="product-info">
                    <span class="product-cat">Lunar Series</span>
                    <h3 class="product-title">Obsidian Eclipse</h3>
                    <div class="product-rating">
                        <span class="stars">★★★★★</span>
                        <span class="rating-count">(41)</span>
                    </div>
                    <div class="product-price-row">
                        <div class="price-box">
                            <span class="old-price">$269.00</span>
                            <span class="current-price">$199.00</span>
                        </div>
                        <button class="btn-add-cart" aria-label="Add to cart">
                            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="cart-icon">
                                <path d="M12 5v14M5 12h14"></path>
                            </svg>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Card 14: Terrazzo Minimal -->
            <div class="product-card" data-id="14">
                <div class="product-img-box">
                    <img src="assets/terrazzo_minimal.svg" alt="Terrazzo Minimal Wall Clock" class="product-img">
                    <div class="card-overlay">
                        <button class="btn-quickview">Quick View</button>
                    </div>
                </div>
                <div class="product-info">
                    <span class="product-cat">Minimalist Series</span>
                    <h3 class="product-title">Terrazzo Minimal</h3>
                    <div class="product-rating">
                        <span class="stars">★★★★★</span>
                        <span class="rating-count">(14)</span>
                    </div>
                    <div class="product-price-row">
                        <div class="price-box">
                            <span class="old-price">$279.00</span>
                            <span class="current-price">$219.00</span>
                        </div>
                        <button class="btn-add-cart" aria-label="Add to cart">
                            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="cart-icon">
                                <path d="M12 5v14M5 12h14"></path>
                            </svg>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Card 15: Midnight Sunburst -->
            <div class="product-card" data-id="15">
                <div class="product-img-box">
                    <img src="assets/midnight_sunburst.svg" alt="Midnight Sunburst Wall Clock" class="product-img">
                    <div class="card-overlay">
                        <button class="btn-quickview">Quick View</button>
                    </div>
                </div>
                <div class="product-info">
                    <span class="product-cat">Cosmic Series</span>
                    <h3 class="product-title">Midnight Sunburst</h3>
                    <div class="product-rating">
                        <span class="stars">★★★★★</span>
                        <span class="rating-count">(22)</span>
                    </div>
                    <div class="product-price-row">
                        <div class="price-box">
                            <span class="old-price">$319.00</span>
                            <span class="current-price">$249.00</span>
                        </div>
                        <button class="btn-add-cart" aria-label="Add to cart">
                            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="cart-icon">
                                <path d="M12 5v14M5 12h14"></path>
                            </svg>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Card 16: Cyber Guardian -->
            <div class="product-card" data-id="16">
                <div class="product-img-box">
                    <span class="product-badge badge-sale">Malachite</span>
                    <img src="assets/verde_imperial.svg" alt="Verde Malachite Wall Clock" class="product-img">
                    <div class="card-overlay">
                        <button class="btn-quickview">Quick View</button>
                    </div>
                </div>
                <div class="product-info">
                    <span class="product-cat">Classic Series</span>
                    <h3 class="product-title">Verde Malachite</h3>
                    <div class="product-rating">
                        <span class="stars">★★★★★</span>
                        <span class="rating-count">(54)</span>
                    </div>
                    <div class="product-price-row">
                        <div class="price-box">
                            <span class="old-price">$399.00</span>
                            <span class="current-price">$329.00</span>
                        </div>
                        <button class="btn-add-cart" aria-label="Add to cart">
                            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="cart-icon">
                                <path d="M12 5v14M5 12h14"></path>
                            </svg>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Card 17: Aetheric Hourglass -->
            <div class="product-card" data-id="17">
                <div class="product-img-box">
                    <span class="product-badge badge-new">Cosmic</span>
                    <img src="assets/hourglass_clock.svg" alt="Aetheric Hourglass Wall Clock" class="product-img">
                    <div class="card-overlay">
                        <button class="btn-quickview">Quick View</button>
                    </div>
                </div>
                <div class="product-info">
                    <span class="product-cat">Celestial Loop Series</span>
                    <h3 class="product-title">Aetheric Hourglass</h3>
                    <div class="product-rating">
                        <span class="stars">★★★★★</span>
                        <span class="rating-count">(28)</span>
                    </div>
                    <div class="product-price-row">
                        <div class="price-box">
                            <span class="old-price">$329.00</span>
                            <span class="current-price">$269.00</span>
                        </div>
                        <button class="btn-add-cart" aria-label="Add to cart">
                            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="cart-icon">
                                <path d="M12 5v14M5 12h14"></path>
                            </svg>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Card 18: Steampunk Astrolabe -->
            <div class="product-card" data-id="18">
                <div class="product-img-box">
                    <span class="product-badge badge-new">Exclusive</span>
                    <img src="assets/astrolabe_clock.svg" alt="Steampunk Astrolabe Wall Clock" class="product-img">
                    <div class="card-overlay">
                        <button class="btn-quickview">Quick View</button>
                    </div>
                </div>
                <div class="product-info">
                    <span class="product-cat">Vintage Mechanism Series</span>
                    <h3 class="product-title">Steampunk Astrolabe</h3>
                    <div class="product-rating">
                        <span class="stars">★★★★★</span>
                        <span class="rating-count">(41)</span>
                    </div>
                    <div class="product-price-row">
                        <div class="price-box">
                            <span class="old-price">$429.00</span>
                            <span class="current-price">$359.00</span>
                        </div>
                        <button class="btn-add-cart" aria-label="Add to cart">
                            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="cart-icon">
                                <path d="M12 5v14M5 12h14"></path>
                            </svg>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Card 19: Quantum Chronometer -->
            <div class="product-card" data-id="19">
                <div class="product-img-box">
                    <span class="product-badge badge-new">Wormhole</span>
                    <img src="assets/quantum_clock.svg" alt="Quantum Chronometer Wall Clock" class="product-img">
                    <div class="card-overlay">
                        <button class="btn-quickview">Quick View</button>
                    </div>
                </div>
                <div class="product-info">
                    <span class="product-cat">Stellar Matrix Series</span>
                    <h3 class="product-title">Quantum Chronometer</h3>
                    <div class="product-rating">
                        <span class="stars">★★★★★</span>
                        <span class="rating-count">(16)</span>
                    </div>
                    <div class="product-price-row">
                        <div class="price-box">
                            <span class="old-price">$359.00</span>
                            <span class="current-price">$299.00</span>
                        </div>
                        <button class="btn-add-cart" aria-label="Add to cart">
                            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="cart-icon">
                                <path d="M12 5v14M5 12h14"></path>
                            </svg>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Card 20: Vintage Pulsar -->
            <div class="product-card" data-id="20">
                <div class="product-img-box">
                    <img src="assets/pulsar_clock.svg" alt="Vintage Pulsar Wall Clock" class="product-img">
                    <div class="card-overlay">
                        <button class="btn-quickview">Quick View</button>
                    </div>
                </div>
                <div class="product-info">
                    <span class="product-cat">Cosmic Antique Series</span>
                    <h3 class="product-title">Vintage Pulsar</h3>
                    <div class="product-rating">
                        <span class="stars">★★★★★</span>
                        <span class="rating-count">(23)</span>
                    </div>
                    <div class="product-price-row">
                        <div class="price-box">
                            <span class="old-price">$299.00</span>
                            <span class="current-price">$249.00</span>
                        </div>
                        <button class="btn-add-cart" aria-label="Add to cart">
                            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="cart-icon">
                                <path d="M12 5v14M5 12h14"></path>
                            </svg>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Card 21: Eclipse Singularity -->
            <div class="product-card" data-id="21">
                <div class="product-img-box">
                    <span class="product-badge badge-sale">Premium</span>
                    <img src="assets/eclipse_singularity.svg" alt="Eclipse Singularity Wall Clock" class="product-img">
                    <div class="card-overlay">
                        <button class="btn-quickview">Quick View</button>
                    </div>
                </div>
                <div class="product-info">
                    <span class="product-cat">Stellar Matrix Series</span>
                    <h3 class="product-title">Eclipse Singularity</h3>
                    <div class="product-rating">
                        <span class="stars">★★★★★</span>
                        <span class="rating-count">(47)</span>
                    </div>
                    <div class="product-price-row">
                        <div class="price-box">
                            <span class="old-price">$459.00</span>
                            <span class="current-price">$389.00</span>
                        </div>
                        <button class="btn-add-cart" aria-label="Add to cart">
                            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="cart-icon">
                                <path d="M12 5v14M5 12h14"></path>
                            </svg>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Card 22: Chronos Infinity -->
            <div class="product-card" data-id="22">
                <div class="product-img-box">
                    <span class="product-badge badge-sale">Infinite</span>
                    <img src="assets/chronos_infinity.svg" alt="Chronos Infinity Wall Clock" class="product-img">
                    <div class="card-overlay">
                        <button class="btn-quickview">Quick View</button>
                    </div>
                </div>
                <div class="product-info">
                    <span class="product-cat">Celestial Loop Series</span>
                    <h3 class="product-title">Chronos Infinity</h3>
                    <div class="product-rating">
                        <span class="stars">★★★★★</span>
                        <span class="rating-count">(34)</span>
                    </div>
                    <div class="product-price-row">
                        <div class="price-box">
                            <span class="old-price">$389.00</span>
                            <span class="current-price">$319.00</span>
                        </div>
                        <button class="btn-add-cart" aria-label="Add to cart">
                            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="cart-icon">
                                <path d="M12 5v14M5 12h14"></path>
                            </svg>
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- Customizer Studio -->
<section class="customizer-section" id="customizer">
    <div class="section-container">
        <div class="customizer-grid">
            <div class="customizer-preview">
                <div class="customizer-glow-bg"></div>
                <div class="custom-clock-container">
                    <div class="custom-clock-outer led-cyan" id="custom-clock-outer">
                        <div class="custom-clock" id="custom-clock">
                            <div class="custom-clock-face" id="custom-clock-face">
                                <div class="custom-center-pin"></div>
                                <!-- Dial indicators -->
                                <div class="c-ind c-ind-12"></div>
                                <div class="c-ind c-ind-3"></div>
                                <div class="c-ind c-ind-6"></div>
                                <div class="c-ind c-ind-9"></div>
                                <!-- Hands -->
                                <div class="c-hand c-hour" id="c-hour"></div>
                                <div class="c-hand c-min" id="c-min"></div>
                                <div class="c-hand c-sec" id="c-sec"></div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <div class="customizer-controls">
                <span class="control-tag">INTERACTIVE STUDIO</span>
                <h2 class="control-title">Visualize Your Aura</h2>
                <p class="control-desc">Customize the clock in real-time. Match the colors and textures to your space before ordering.</p>
                
                <div class="control-group">
                    <label class="control-label">Dial Background Color</label>
                    <div class="options-row">
                        <button class="option-btn color-opt active" data-type="bg" data-val="dark-slate" style="background: #111827;" title="Charcoal Dark"></button>
                        <button class="option-btn color-opt" data-type="bg" data-val="navy-gold" style="background: #0f172a; border: 2px solid #e2b855;" title="Midnight Blue"></button>
                        <button class="option-btn color-opt" data-type="bg" data-val="forest-green" style="background: #064e3b;" title="Forest Green"></button>
                        <button class="option-btn color-opt" data-type="bg" data-val="rose-gold" style="background: #f43f5e;" title="Rose Ember"></button>
                        <button class="option-btn color-opt" data-type="bg" data-val="emerald-pulse" style="background: #059669;" title="Emerald"></button>
                    </div>
                </div>

                <div class="control-group">
                    <label class="control-label">Hands Styling</label>
                    <div class="options-row">
                        <button class="option-btn text-opt active" data-type="hands" data-val="minimalist">Minimalist</button>
                        <button class="option-btn text-opt" data-type="hands" data-val="classic">Classic Lancet</button>
                        <button class="option-btn text-opt" data-type="hands" data-val="glowing">Neon Pulse</button>
                    </div>
                </div>

                <div class="control-group">
                    <label class="control-label">Accent Outer Ring LED</label>
                    <div class="options-row">
                        <button class="option-btn text-opt active" data-type="led" data-val="cyan">Cyan Glow</button>
                        <button class="option-btn text-opt" data-type="led" data-val="amber">Amber Warm</button>
                        <button class="option-btn text-opt" data-type="led" data-val="off">LED Off</button>
                    </div>
                </div>

                <div class="control-group">
                    <label class="control-label">Acoustics & Movement</label>
                    <div class="options-row" style="display:flex; align-items:center; gap:16px;">
                        <button class="option-btn text-opt active" data-type="acoustics" data-val="sweep">Silent Sweep</button>
                        <button class="option-btn text-opt" data-type="acoustics" data-val="tick">Mechanical Tick</button>
                        <div class="volume-container" style="display:flex; align-items:center; gap:8px;">
                            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="icon" style="width:18px; height:18px; color:var(--text-secondary);">
                                <polygon points="11 5 6 9 2 9 2 15 6 15 11 19 11 5"></polygon>
                                <path d="M19.07 4.93a10 10 0 0 1 0 14.14M15.54 8.46a5 5 0 0 1 0 7.07"></path>
                            </svg>
                            <input type="range" id="volume-slider" min="0" max="1" step="0.1" value="0.5" style="width:70px; height:4px; accent-color:var(--pencil-blue); background:rgba(255,255,255,0.1); border:none; outline:none; cursor:pointer;" aria-label="Volume">
                        </div>
                    </div>
                </div>

                <div class="customizer-footer">
                    <div class="customizer-price-box">
                        <span class="custom-price-label">Estimated Price</span>
                        <span class="custom-price">$269.00</span>
                    </div>
                    <button class="btn btn-primary btn-add-custom">
                        <span>Order Custom Design</span>
                    </button>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- Live World Time-Zone Dashboard -->
<section class="world-timezone-section" id="world-time">
    <div class="section-container">
        <div class="section-header">
            <span class="section-tag">GLOBAL TIME LOOPS</span>
            <h2 class="section-title">Celestial World Dashboard</h2>
            <p class="section-subtitle">Track the cosmic rotation across global hubs. Beautiful mechanical space-glass dials synchronized to local solar loops.</p>
        </div>
        
        <div class="world-clocks-grid">
            <!-- London Clock -->
            <div class="world-clock-card">
                <div class="world-clock-dial">
                    <div class="world-clock-face">
                        <div class="w-ring"></div>
                        <div class="w-center"></div>
                        <div class="w-hand w-hour" id="london-hour"></div>
                        <div class="w-hand w-min" id="london-min"></div>
                        <div class="w-hand w-sec" id="london-sec"></div>
                        <span class="w-label-12">XII</span>
                        <span class="w-label-6">VI</span>
                    </div>
                </div>
                <div class="world-clock-info">
                    <h3>London</h3>
                    <div class="world-time-digital" id="london-digital">00:00:00 GMT</div>
                    <span class="world-time-offset">UTC +0:00</span>
                </div>
            </div>

            <!-- New York Clock -->
            <div class="world-clock-card">
                <div class="world-clock-dial">
                    <div class="world-clock-face">
                        <div class="w-ring"></div>
                        <div class="w-center"></div>
                        <div class="w-hand w-hour" id="newyork-hour"></div>
                        <div class="w-hand w-min" id="newyork-min"></div>
                        <div class="w-hand w-sec" id="newyork-sec"></div>
                        <span class="w-label-12">XII</span>
                        <span class="w-label-6">VI</span>
                    </div>
                </div>
                <div class="world-clock-info">
                    <h3>New York</h3>
                    <div class="world-time-digital" id="newyork-digital">00:00:00 EST</div>
                    <span class="world-time-offset">UTC -5:00</span>
                </div>
            </div>

            <!-- New Delhi Clock -->
            <div class="world-clock-card">
                <div class="world-clock-dial">
                    <div class="world-clock-face">
                        <div class="w-ring"></div>
                        <div class="w-center"></div>
                        <div class="w-hand w-hour" id="delhi-hour"></div>
                        <div class="w-hand w-min" id="delhi-min"></div>
                        <div class="w-hand w-sec" id="delhi-sec"></div>
                        <span class="w-label-12">XII</span>
                        <span class="w-label-6">VI</span>
                    </div>
                </div>
                <div class="world-clock-info">
                    <h3>New Delhi</h3>
                    <div class="world-time-digital" id="delhi-digital">00:00:00 IST</div>
                    <span class="world-time-offset">UTC +5:30</span>
                </div>
            </div>

            <!-- Tokyo Clock -->
            <div class="world-clock-card">
                <div class="world-clock-dial">
                    <div class="world-clock-face">
                        <div class="w-ring"></div>
                        <div class="w-center"></div>
                        <div class="w-hand w-hour" id="tokyo-hour"></div>
                        <div class="w-hand w-min" id="tokyo-min"></div>
                        <div class="w-hand w-sec" id="tokyo-sec"></div>
                        <span class="w-label-12">XII</span>
                        <span class="w-label-6">VI</span>
                    </div>
                </div>
                <div class="world-clock-info">
                    <h3>Tokyo</h3>
                    <div class="world-time-digital" id="tokyo-digital">00:00:00 JST</div>
                    <span class="world-time-offset">UTC +9:00</span>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- Philosophy & Craftsmanship Section -->
<section class="philosophy-section" id="philosophy">
    <div class="section-container">
        <div class="section-header">
            <span class="section-tag">OUR PHILOSOPHY</span>
            <h2 class="section-title">Engineered to Perfection</h2>
            <p class="section-subtitle">We believe a wall clock shouldn't just count the hours, but define the visual aura of the room. Every detail is meticulously calculated.</p>
        </div>
        <div class="philosophy-grid">
            <div class="phi-card">
                <div class="phi-icon-box">
                    <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                        <path d="M12 2v2M12 20v2M4.93 4.93l1.41 1.41M17.66 17.66l1.41 1.41M2 12h2M20 12h2M6.34 17.66l-1.41 1.41M19.07 4.93l-1.41 1.41"></path>
                        <circle cx="12" cy="12" r="7"></circle>
                    </svg>
                </div>
                <h3>Silent Sweep Technology</h3>
                <p>Powered by high-torque silent quartz movements. No ticking noises. Perfect for bedrooms, offices, and quiet studio spaces.</p>
            </div>
            <div class="phi-card">
                <div class="phi-icon-box">
                    <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                        <path d="M22 12h-4l-3 9L9 3l-3 9H2"></path>
                    </svg>
                </div>
                <h3>Sustainable Premium Materials</h3>
                <p>Sourced from sustainable FSC-certified oak woods, authentic Italian marble, brushed aircraft-grade aluminum, and mineral crystal glass.</p>
            </div>
            <div class="phi-card">
                <div class="phi-icon-box">
                    <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                        <path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"></path>
                    </svg>
                </div>
                <h3>German Movement Calibre</h3>
                <p>Engineered with UTS quartz calibres, maintaining accuracy within +/- 15 seconds per month for years of maintenance-free service.</p>
            </div>
        </div>
    </div>
</section>

<!-- Testimonials -->
<section class="testimonials-section" id="testimonials">
    <div class="section-container">
        <div class="section-header">
            <span class="section-tag">TESTIMONIALS</span>
            <h2 class="section-title">Loved by Interior Designers</h2>
            <p class="section-subtitle">Read how our wall clocks transformed living spaces, luxury offices, and architectural blueprints.</p>
        </div>
        
        <div class="testimonials-grid">
            <div class="testi-card">
                <div class="stars">★★★★★</div>
                <p class="testi-text">"CLOCKIT wall clocks are the perfect finishing touch. The Minimalist Aura matches our oak-themed living room. It's completely silent, which is crucial for my concentration."</p>
                <div class="user-info">
                    <div class="user-avatar" style="background: #a21caf;">AW</div>
                    <div>
                        <h4 class="user-name">Aniket Walia</h4>
                        <span class="user-role">Creative Director, ArtDeco</span>
                    </div>
                </div>
            </div>

            <div class="testi-card">
                <div class="stars">★★★★★</div>
                <p class="testi-text">"The Roman Marble clock is absolute luxury. The gold metallic veins catch the morning light beautifully. It feels heavy, robust, and represents state-of-the-art craft."</p>
                <div class="user-info">
                    <div class="user-avatar" style="background: #0ea5e9;">MS</div>
                    <div>
                        <h4 class="user-name">Marcus Sterling</h4>
                        <span class="user-role">Lead Architect, Sterling Spaces</span>
                    </div>
                </div>
            </div>

            <div class="testi-card">
                <div class="stars">★★★★★</div>
                <p class="testi-text">"I ordered the Smart Horizon with the outer teal glow. In the evenings, it casts a beautiful ambient light in the studio. It acts as both a clock and a stunning design sculpture."</p>
                <div class="user-info">
                    <div class="user-avatar" style="background: #10b981;">EL</div>
                    <div>
                        <h4 class="user-name">Elena Rostova</h4>
                        <span class="user-role">Tech Reviewer & Designer</span>
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- Contact & Newsletter -->
<section class="contact-section" id="contact">
    <div class="section-container">
        <div class="contact-box">
            <div class="contact-glow"></div>
            <div class="contact-content">
                <h2>Stay in Sync with CLOCKIT</h2>
                <p>Subscribe to receive product drop alerts, customization catalog updates, and exclusive discount coupons up to 30% off.</p>
                <form class="subscribe-form" id="subscribe-form" onsubmit="event.preventDefault(); alert('Thank you for subscribing! Check your inbox for your 15% discount code.'); this.reset();">
                    <input type="email" placeholder="Enter your email address" required aria-label="Email Address">
                    <button type="submit" class="btn btn-primary">
                        <span>Join the Club</span>
                    </button>
                </form>
            </div>
        </div>
    </div>
</section>

<!-- Footer -->
<footer class="footer">
    <div class="footer-container">
        <div class="footer-brand">
            <a href="#" class="logo">
                <svg class="logo-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <circle cx="12" cy="12" r="10"></circle>
                    <polyline points="12 6 12 12 16 14"></polyline>
                </svg>
                <span class="logo-text">CLOCK<span>IT</span></span>
            </a>
            <p class="footer-desc">Redefining modern spaces with statement horological timepieces. Merging silent mechanics with artistic excellence.</p>
        </div>
        
        <div class="footer-links-group">
            <div class="footer-col">
                <h4>Collections</h4>
                <ul>
                    <li><a href="#collection">Minimalist</a></li>
                    <li><a href="#collection">Industrial</a></li>
                    <li><a href="#collection">Marble Classic</a></li>
                    <li><a href="#collection">Smart Horizon</a></li>
                </ul>
            </div>
            <div class="footer-col">
                <h4>Custom Studio</h4>
                <ul>
                    <li><a href="#customizer">Virtual Customizer</a></li>
                    <li><a href="#philosophy">Engineering Specs</a></li>
                    <li><a href="#philosophy">Warranty Information</a></li>
                </ul>
            </div>
            <div class="footer-col">
                <h4>Contact Us</h4>
                <ul>
                    <li>support@clockit.com</li>
                    <li>1-800-CLOCK-IT</li>
                    <li>SkillCraft Tech Hub, India</li>
                </ul>
            </div>
        </div>
    </div>
    <div class="footer-bottom">
        <p>&copy; 2026 CLOCKIT. Crafted by SkillCraft Technology. All rights reserved.</p>
    </div>
</footer>

<!-- Quick View Details Modal -->
<div class="modal-overlay" id="quickview-modal">
    <div class="modal-box">
        <button class="modal-close" id="modal-close" aria-label="Close details">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <line x1="18" y1="6" x2="6" y2="18"></line>
                <line x1="6" y1="6" x2="18" y2="18"></line>
            </svg>
        </button>
        <div class="modal-grid">
            <div class="modal-gallery">
                <img src="" alt="Clock Detail Image" id="modal-img" class="modal-img">
            </div>
            <div class="modal-details">
                <span class="modal-cat" id="modal-cat">Collection Category</span>
                <h2 class="modal-title" id="modal-title">Product Title</h2>
                <div class="product-rating">
                    <span class="stars" id="modal-stars">★★★★★</span>
                    <span class="rating-count" id="modal-reviews">(0 reviews)</span>
                </div>
                <div class="modal-prices">
                    <span class="old-price" id="modal-old-price">$0.00</span>
                    <span class="current-price" id="modal-current-price">$0.00</span>
                </div>
                <div class="modal-tabs-container">
                    <div class="modal-tabs-header">
                        <button class="modal-tab-btn active" data-tab="overview">Overview</button>
                        <button class="modal-tab-btn" data-tab="specs">Specs Sheet</button>
                        <button class="modal-tab-btn" data-tab="story">Vintage Story</button>
                    </div>
                    <div class="modal-tabs-content">
                        <!-- Tab 1: Overview -->
                        <div class="modal-tab-pane active" id="pane-overview">
                            <p class="modal-desc" id="modal-desc">Detailed descriptions about craftsmanship, silent quartz sweep movement, and aesthetic design values go here.</p>
                        </div>
                        <!-- Tab 2: Specs Sheet -->
                        <div class="modal-tab-pane" id="pane-specs">
                            <div class="modal-specs">
                                <ul>
                                    <li><strong>Diameter:</strong> <span id="spec-diameter">30 cm (11.8 inches)</span></li>
                                    <li><strong>Movement:</strong> <span id="spec-movement">UTS German Quartz (Silent Sweep)</span></li>
                                    <li><strong>Materials:</strong> <span id="spec-materials">Varies by design</span></li>
                                    <li><strong>Power:</strong> 1x AA Battery (included)</li>
                                </ul>
                            </div>
                        </div>
                        <!-- Tab 3: Vintage Story -->
                        <div class="modal-tab-pane" id="pane-story">
                            <p class="modal-story" id="modal-story">Every clock has a story. Hand-assembled in our German watchmaking workshop, this piece represents decades of precision manufacturing.</p>
                        </div>
                    </div>
                </div>

                <button class="btn btn-primary modal-add-cart-btn" id="modal-add-cart-btn">
                    <span>Add to Cart</span>
                </button>
            </div>
        </div>
    </div>
</div>

<!-- Shopping Cart Drawer -->
<div class="cart-drawer" id="cart-drawer" aria-hidden="true">
    <div class="cart-drawer-overlay" id="cart-drawer-overlay"></div>
    <div class="cart-drawer-content">
        <div class="cart-drawer-header">
            <h3>Shopping Cart (<span id="cart-count-title">0</span>)</h3>
            <button class="cart-drawer-close" id="cart-drawer-close" aria-label="Close Cart">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" style="width:20px; height:20px;">
                    <line x1="18" y1="6" x2="6" y2="18"></line>
                    <line x1="6" y1="6" x2="18" y2="18"></line>
                </svg>
            </button>
        </div>
        
        <div class="cart-drawer-items" id="cart-drawer-items">
            <!-- Dynamically injected cart items go here -->
            <div class="cart-empty-message">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="empty-icon" style="width:48px; height:48px; margin-bottom:16px; opacity:0.4;">
                    <circle cx="9" cy="21" r="1"></circle>
                    <circle cx="20" cy="21" r="1"></circle>
                    <path d="M1 1h4l2.68 13.39a2 2 0 0 0 2 1.61h9.72a2 2 0 0 0 2-1.61L23 6H6"></path>
                </svg>
                <p>Your cart is empty.</p>
            </div>
        </div>
        
        <div class="cart-drawer-footer" id="cart-drawer-footer">
            <div class="cart-subtotal-row">
                <span>Subtotal</span>
                <span class="cart-subtotal-price" id="cart-subtotal-price">$0.00</span>
            </div>
            <div class="cart-action-buttons">
                <button class="btn btn-secondary" id="cart-clear-btn" style="flex:1; padding: 12px;">Clear All</button>
                <button class="btn btn-primary" id="cart-checkout-btn" style="flex:2; padding: 12px;">Checkout</button>
            </div>
        </div>
    </div>
</div>

<!-- Order History / Tracking Drawer -->
<div class="cart-drawer" id="tracking-drawer" aria-hidden="true">
    <div class="cart-drawer-overlay" id="tracking-drawer-overlay"></div>
    <div class="cart-drawer-content">
        <div class="cart-drawer-header">
            <h3>Order History &amp; Loops</h3>
            <button class="cart-drawer-close" id="tracking-drawer-close" aria-label="Close Order History">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" style="width:20px; height:20px;">
                    <line x1="18" y1="6" x2="6" y2="18"></line>
                    <line x1="6" y1="6" x2="18" y2="18"></line>
                </svg>
            </button>
        </div>
        
        <div class="cart-drawer-items" id="tracking-drawer-items" style="gap:24px;">
            <!-- Dynamically injected tracking loops go here -->
            <div class="cart-empty-message">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="empty-icon" style="width:48px; height:48px; margin-bottom:16px; opacity:0.4;">
                    <circle cx="12" cy="12" r="10"></circle>
                    <polyline points="12 6 12 12 16 14"></polyline>
                </svg>
                <p>No active time loops found.</p>
            </div>
        </div>
    </div>
</div>

<!-- Checkout Modal -->
<div class="modal-overlay" id="checkout-modal">
    <div class="modal-box checkout-modal-box">
        <button class="modal-close" id="checkout-modal-close" aria-label="Close checkout">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <line x1="18" y1="6" x2="6" y2="18"></line>
                <line x1="6" y1="6" x2="18" y2="18"></line>
            </svg>
        </button>
        
        <div class="checkout-grid" id="checkout-grid-content">
            <!-- Checkout Form -->
            <div class="checkout-form-container">
                <h2 class="checkout-section-title">Shipping &amp; Payment</h2>
                <form id="checkout-form" class="checkout-form">
                    <div class="form-row" style="display:grid; grid-template-columns: 1fr 1fr; gap:16px; margin-bottom:16px;">
                        <div class="form-group" style="display:flex; flex-direction:column; gap:6px;">
                            <label for="c-name" style="font-size:0.8rem; font-weight:600; text-transform:uppercase; color:var(--text-secondary);">Full Name</label>
                            <input type="text" id="c-name" placeholder="John Doe" required style="padding:12px; background:rgba(255,255,255,0.03); border:1px solid var(--border-color); border-radius:8px; color:var(--text-primary); outline:none;">
                        </div>
                        <div class="form-group" style="display:flex; flex-direction:column; gap:6px;">
                            <label for="c-email" style="font-size:0.8rem; font-weight:600; text-transform:uppercase; color:var(--text-secondary);">Email Address</label>
                            <input type="email" id="c-email" placeholder="john@example.com" required style="padding:12px; background:rgba(255,255,255,0.03); border:1px solid var(--border-color); border-radius:8px; color:var(--text-primary); outline:none;">
                        </div>
                    </div>
                    <div class="form-group" style="display:flex; flex-direction:column; gap:6px; margin-bottom:16px;">
                        <label for="c-address" style="font-size:0.8rem; font-weight:600; text-transform:uppercase; color:var(--text-secondary);">Shipping Address</label>
                        <input type="text" id="c-address" placeholder="123 Luxury Lane" required style="padding:12px; background:rgba(255,255,255,0.03); border:1px solid var(--border-color); border-radius:8px; color:var(--text-primary); outline:none;">
                    </div>
                    <div class="form-row" style="display:grid; grid-template-columns: 1.5fr 1fr; gap:16px; margin-bottom:16px;">
                        <div class="form-group" style="display:flex; flex-direction:column; gap:6px;">
                            <label for="c-city" style="font-size:0.8rem; font-weight:600; text-transform:uppercase; color:var(--text-secondary);">City</label>
                            <input type="text" id="c-city" placeholder="New York" required style="padding:12px; background:rgba(255,255,255,0.03); border:1px solid var(--border-color); border-radius:8px; color:var(--text-primary); outline:none;">
                        </div>
                        <div class="form-group" style="display:flex; flex-direction:column; gap:6px;">
                            <label for="c-zip" style="font-size:0.8rem; font-weight:600; text-transform:uppercase; color:var(--text-secondary);">ZIP Code</label>
                            <input type="text" id="c-zip" placeholder="10001" required style="padding:12px; background:rgba(255,255,255,0.03); border:1px solid var(--border-color); border-radius:8px; color:var(--text-primary); outline:none;">
                        </div>
                    </div>
                    <div class="form-group" style="display:flex; flex-direction:column; gap:6px; margin-bottom:16px;">
                        <label for="c-card" style="font-size:0.8rem; font-weight:600; text-transform:uppercase; color:var(--text-secondary);">Card Number</label>
                        <input type="text" id="c-card" placeholder="4111222233334444" required pattern="\d{16}" title="16 digit card number" style="padding:12px; background:rgba(255,255,255,0.03); border:1px solid var(--border-color); border-radius:8px; color:var(--text-primary); outline:none;">
                    </div>
                    <div class="form-row" style="display:grid; grid-template-columns: 1fr 1fr; gap:16px; margin-bottom:24px;">
                        <div class="form-group" style="display:flex; flex-direction:column; gap:6px;">
                            <label for="c-exp" style="font-size:0.8rem; font-weight:600; text-transform:uppercase; color:var(--text-secondary);">Expiry Date</label>
                            <input type="text" id="c-exp" placeholder="MM/YY" required pattern="\d{2}/\d{2}" style="padding:12px; background:rgba(255,255,255,0.03); border:1px solid var(--border-color); border-radius:8px; color:var(--text-primary); outline:none;">
                        </div>
                        <div class="form-group" style="display:flex; flex-direction:column; gap:6px;">
                            <label for="c-cvv" style="font-size:0.8rem; font-weight:600; text-transform:uppercase; color:var(--text-secondary);">CVV</label>
                            <input type="password" id="c-cvv" placeholder="***" required pattern="\d{3}" style="padding:12px; background:rgba(255,255,255,0.03); border:1px solid var(--border-color); border-radius:8px; color:var(--text-primary); outline:none;">
                        </div>
                    </div>
                    <button type="submit" class="btn btn-primary checkout-submit-btn" style="width:100%;">
                        <span>Place Secure Order</span>
                    </button>
                </form>
            </div>
            
            <!-- Order Summary -->
            <div class="checkout-summary-container" style="background:rgba(255,255,255,0.02); border:1px solid var(--border-color); border-radius:16px; padding:24px; display:flex; flex-direction:column;">
                <h2 class="checkout-section-title" style="font-size:1.2rem; font-weight:700; margin-bottom:20px; border-bottom:1px solid var(--border-color); padding-bottom:12px;">Order Summary</h2>
                <div class="checkout-summary-items" id="checkout-summary-items" style="flex-grow:1; max-height:220px; overflow-y:auto; margin-bottom:20px; display:flex; flex-direction:column; gap:16px;">
                    <!-- Dynamically injected items -->
                </div>
                <div class="checkout-summary-footer" style="border-top:1px solid var(--border-color); padding-top:16px; display:flex; flex-direction:column; gap:10px;">
                    <div class="summary-line" style="display:flex; justify-content: space-between; font-size:0.95rem; color:var(--text-secondary);">
                        <span>Subtotal</span>
                        <span id="summary-subtotal">$0.00</span>
                    </div>
                    <div class="summary-line" style="display:flex; justify-content: space-between; font-size:0.95rem; color:var(--text-secondary);">
                        <span>Shipping</span>
                        <span style="color:var(--color-emerald); font-weight:600;">FREE</span>
                    </div>
                    <div class="summary-line total-line" style="display:flex; justify-content: space-between; font-size:1.25rem; font-weight:800; color:var(--text-primary); border-top:1px dashed var(--border-color); padding-top:12px; margin-top:4px;">
                        <span>Total</span>
                        <span id="summary-total">$0.00</span>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Success screen state inside same modal -->
        <div class="checkout-success-container" id="checkout-success" style="display:none; text-align:center; padding:20px;">
            <div class="success-icon-box" style="width:70px; height:70px; border-radius:50%; background:rgba(16, 185, 129, 0.1); border:2px solid var(--color-emerald); color:var(--color-emerald); display:inline-flex; align-items:center; justify-content:center; margin-bottom:24px;">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" style="width:36px; height:36px;">
                    <polyline points="20 6 9 17 4 12"></polyline>
                </svg>
            </div>
            <h2 style="font-size:2rem; font-weight:700; margin-bottom:12px;">Order Confirmed!</h2>
            <p style="color:var(--text-secondary); margin-bottom:30px;">Thank you for choosing CLOCKIT, <strong id="success-buyer-name" style="color:var(--text-primary);">Customer</strong>. Your luxury timepiece order has been placed successfully. A receipt and cosmic tracking details have been sent to <span id="success-email" style="color:var(--text-primary); font-weight:600;">customer@example.com</span>.</p>
            <div class="order-details-box" style="background:rgba(255,255,255,0.02); border:1px solid var(--border-color); border-radius:12px; padding:20px; text-align:left; max-width:400px; margin:0 auto 30px; display:flex; flex-direction:column; gap:8px; font-size:0.95rem; color:var(--text-secondary);">
                <p style="display:flex; justify-content:space-between;"><strong>Order ID:</strong> <span id="success-order-id" style="color:var(--text-primary); font-family:monospace; font-weight:600;">CLK-892A2-X</span></p>
                <p style="display:flex; justify-content:space-between;"><strong>Shipping:</strong> <span style="color:var(--text-primary);">Standard Courier (Free)</span></p>
                <p style="display:flex; justify-content:space-between;"><strong>Delivery Estimate:</strong> <span style="color:var(--text-primary);">3 - 5 Business Days</span></p>
            </div>
            <button class="btn btn-primary" id="success-continue-btn" style="padding:12px 30px;">Continue Shopping</button>
        </div>
    </div>
</div>

<!-- Active Script -->
<script src="script.js"></script>

                                                
