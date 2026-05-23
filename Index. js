import React, { useState, useEffect } from 'react';
import { Menu, X, ShoppingBag, MessageCircle, MapPin, Phone, Instagram, Facebook, Heart, Star } from 'lucide-react';

export default function WaremboGiftShop() {
  const [menuOpen, setMenuOpen] = useState(false);
  const [activeCategory, setActiveCategory] = useState('all');
  const [currentSection, setCurrentSection] = useState('home');
  const [scrolled, setScrolled] = useState(false);

  useEffect(() => {
    const handleScroll = () => {
      setScrolled(window.scrollY > 50);
    };
    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  }, []);

  const products = [
    {
      id: 1,
      name: 'Luxury Rose Gift Box',
      price: 'KES 2,500',
      category: 'romantic',
      description: 'Beautiful arrangement of fresh roses with chocolates',
      rating: 5,
      gradient: 'from-rose-300 via-pink-200 to-red-200'
    },
    {
      id: 2,
      name: 'Premium Perfume Combo',
      price: 'KES 3,200',
      category: 'luxury',
      description: 'Exclusive collection of three premium fragrances',
      rating: 5,
      gradient: 'from-amber-200 via-yellow-100 to-orange-100'
    },
    {
      id: 3,
      name: 'Birthday Surprise Box',
      price: 'KES 1,800',
      category: 'birthday',
      description: 'Curated gift set with decorations and treats',
      rating: 5,
      gradient: 'from-blue-200 via-purple-200 to-pink-200'
    },
    {
      id: 4,
      name: 'Anniversary Celebration Set',
      price: 'KES 4,500',
      category: 'romantic',
      description: 'Premium wine, chocolates, and candles',
      rating: 5,
      gradient: 'from-red-200 via-rose-200 to-pink-100'
    },
    {
      id: 5,
      name: 'Corporate Gift Basket',
      price: 'KES 3,500',
      category: 'corporate',
      description: 'Professional gift selection for businesses',
      rating: 5,
      gradient: 'from-slate-200 via-gray-200 to-blue-100'
    },
    {
      id: 6,
      name: 'Custom Gift Hamper',
      price: 'KES 2,800',
      category: 'custom',
      description: 'Personalized gift package with your choices',
      rating: 5,
      gradient: 'from-pink-200 via-purple-200 to-indigo-200'
    },
    {
      id: 7,
      name: 'Spa & Wellness Bundle',
      price: 'KES 2,200',
      category: 'luxury',
      description: 'Relaxation package with premium products',
      rating: 5,
      gradient: 'from-cyan-200 via-teal-200 to-green-200'
    },
    {
      id: 8,
      name: 'Gourmet Chocolate Gift',
      price: 'KES 1,500',
      category: 'birthday',
      description: 'Artisan chocolates in elegant packaging',
      rating: 5,
      gradient: 'from-amber-300 via-orange-200 to-brown-100'
    }
  ];

  const categories = [
    { id: 'all', label: '✨ All Products' },
    { id: 'romantic', label: '💕 Romantic' },
    { id: 'birthday', label: '🎂 Birthday' },
    { id: 'corporate', label: '💼 Corporate' },
    { id: 'luxury', label: '👑 Luxury' },
    { id: 'custom', label: '🎀 Custom' }
  ];

  const filteredProducts = activeCategory === 'all' 
    ? products 
    : products.filter(p => p.category === activeCategory);

  const whatsappLink = (productName) => {
    const phone = '254743471232';
    const message = `Hello Warembo Gift Shop, I want to order ${productName}`;
    const encoded = encodeURIComponent(message);
    return `https://wa.me/${phone}?text=${encoded}`;
  };

  const Header = () => (
    <header className={`fixed w-full top-0 z-50 transition-all duration-500 ${
      scrolled 
        ? 'bg-white/95 backdrop-blur-md shadow-lg' 
        : 'bg-gradient-to-b from-white to-white/80'
    }`}>
      <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div className="flex justify-between items-center h-16">
          <button 
            onClick={() => setCurrentSection('home')}
            className="flex items-center space-x-2 group cursor-pointer"
          >
            <div className="w-10 h-10 bg-gradient-to-br from-pink-400 to-rose-400 rounded-full flex items-center justify-center transform group-hover:scale-110 transition-transform">
              <ShoppingBag className="w-5 h-5 text-white" />
            </div>
            <span className="font-bold text-lg bg-gradient-to-r from-pink-500 to-rose-500 bg-clip-text text-transparent hidden sm:inline">
              Warembo
            </span>
          </button>

          {/* Desktop Menu */}
          <nav className="hidden md:flex space-x-8">
            {[
              { label: 'Home', id: 'home' },
              { label: 'Products', id: 'products' },
              { label: 'About', id: 'about' },
              { label: 'Contact', id: 'contact' }
            ].map(item => (
              <button
                key={item.id}
                onClick={() => setCurrentSection(item.id)}
                className={`text-sm font-semibold transition-all duration-300 relative after:absolute after:bottom-0 after:left-0 after:w-0 after:h-0.5 after:bg-gradient-to-r after:from-pink-400 after:to-rose-400 after:hover:w-full after:transition-all ${
                  currentSection === item.id
                    ? 'text-rose-500 after:w-full'
                    : 'text-gray-700 hover:text-rose-500'
                }`}
              >
                {item.label}
              </button>
            ))}
          </nav>

          {/* Mobile Menu Button */}
          <button
            onClick={() => setMenuOpen(!menuOpen)}
            className="md:hidden text-gray-700 hover:text-rose-500 transition-colors"
          >
            {menuOpen ? <X size={24} /> : <Menu size={24} />}
          </button>
        </div>

        {/* Mobile Menu */}
        {menuOpen && (
          <nav className="md:hidden pb-6 space-y-3 animate-in fade-in slide-in-from-top-4">
            {[
              { label: 'Home', id: 'home' },
              { label: 'Products', id: 'products' },
              { label: 'About', id: 'about' },
              { label: 'Contact', id: 'contact' }
            ].map(item => (
              <button
                key={item.id}
                onClick={() => {
                  setCurrentSection(item.id);
                  setMenuOpen(false);
                }}
                className={`block w-full text-left px-4 py-2 rounded-lg transition-all ${
                  currentSection === item.id
                    ? 'bg-gradient-to-r from-pink-400 to-rose-400 text-white'
                    : 'text-gray-700 hover:bg-pink-50'
                }`}
              >
                {item.label}
              </button>
            ))}
          </nav>
        )}
      </div>
    </header>
  );

  const HomePage = () => (
    <div className="pt-16">
      {/* Hero Section */}
      <section className="relative min-h-screen flex items-center justify-center overflow-hidden bg-gradient-to-br from-white via-pink-50 to-rose-50">
        {/* Decorative elements */}
        <div className="absolute top-10 right-10 w-72 h-72 bg-pink-200 rounded-full mix-blend-multiply filter blur-3xl opacity-20 animate-pulse"></div>
        <div className="absolute -bottom-8 -left-8 w-72 h-72 bg-rose-200 rounded-full mix-blend-multiply filter blur-3xl opacity-20 animate-pulse" style={{animationDelay: '2s'}}></div>

        <div className="relative z-10 max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
          <div className="space-y-8 animate-in fade-in slide-in-from-bottom-8 duration-1000">
            <div className="inline-block">
              <span className="px-4 py-2 bg-gradient-to-r from-pink-100 to-rose-100 rounded-full text-pink-600 font-semibold text-sm">
                ✨ Perfect Gifts Delivered Fast
              </span>
            </div>

            <h1 className="text-5xl md:text-7xl font-black leading-tight">
              <span className="bg-gradient-to-r from-pink-500 via-rose-500 to-red-500 bg-clip-text text-transparent">
                Perfect Gifts
              </span>
              <br />
              <span className="text-gray-800">for Every Occasion 🎁</span>
            </h1>

            <p className="text-lg md:text-xl text-gray-600 max-w-2xl mx-auto leading-relaxed">
              Order easily via WhatsApp and get your gifts delivered fast. Beautifully curated, carefully packaged, and delivered with love.
            </p>

            <div className="flex flex-col sm:flex-row justify-center gap-4 pt-8">
              <button
                onClick={() => setCurrentSection('products')}
                className="px-8 py-4 bg-gradient-to-r from-pink-500 to-rose-500 text-white font-bold rounded-full transition-all duration-300 transform hover:scale-105 hover:shadow-lg hover:shadow-pink-300/50 flex items-center justify-center gap-2 group"
              >
                Shop Now <ShoppingBag className="w-5 h-5 group-hover:translate-x-1 transition-transform" />
              </button>
              <a
                href="https://wa.me/254743471232?text=Hi%20Warembo%20Gift%20Shop!%20I%20want%20to%20know%20more%20about%20your%20gifts"
                className="px-8 py-4 border-2 border-pink-500 text-pink-500 hover:bg-pink-50 font-bold rounded-full transition-all duration-300 flex items-center justify-center gap-2"
              >
                Chat on WhatsApp <MessageCircle className="w-5 h-5" />
              </a>
            </div>

            {/* Trust badges */}
            <div className="grid grid-cols-3 gap-6 pt-12 max-w-2xl mx-auto">
              <div className="text-center">
                <p className="text-2xl font-bold text-rose-500">500+</p>
                <p className="text-sm text-gray-600">Happy Customers</p>
              </div>
              <div className="text-center">
                <p className="text-2xl font-bold text-rose-500">⭐⭐⭐⭐⭐</p>
                <p className="text-sm text-gray-600">5-Star Rated</p>
              </div>
              <div className="text-center">
                <p className="text-2xl font-bold text-rose-500">24hrs</p>
                <p className="text-sm text-gray-600">Fast Delivery</p>
              </div>
            </div>
          </div>
        </div>
      </section>
    </div>
  );

  const ProductsPage = () => (
    <div className="pt-20 min-h-screen bg-gradient-to-b from-white to-pink-50 pb-20">
      <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div className="text-center mb-12 animate-in fade-in slide-in-from-top-4">
          <h2 className="text-4xl md:text-5xl font-black mb-4">
            <span className="bg-gradient-to-r from-pink-500 to-rose-500 bg-clip-text text-transparent">
              Our Collection
            </span>
          </h2>
          <p className="text-gray-600 text-lg max-w-2xl mx-auto">
            Handpicked gifts for every moment that matters
          </p>
        </div>

        {/* Category Filter */}
        <div className="mb-12 flex flex-wrap justify-center gap-2 md:gap-4">
          {categories.map(cat => (
            <button
              key={cat.id}
              onClick={() => setActiveCategory(cat.id)}
              className={`px-4 md:px-6 py-2 md:py-3 rounded-full font-semibold transition-all duration-300 transform hover:scale-105 ${
                activeCategory === cat.id
                  ? 'bg-gradient-to-r from-pink-500 to-rose-500 text-white shadow-lg shadow-pink-300/50'
                  : 'bg-white text-gray-700 border border-pink-200 hover:border-pink-400'
              }`}
            >
              {cat.label}
            </button>
          ))}
        </div>

        {/* Products Grid */}
        <div className="grid md:grid-cols-2 lg:grid-cols-4 gap-6 md:gap-8">
          {filteredProducts.map((product, idx) => (
            <div
              key={product.id}
              className="group animate-in fade-in slide-in-from-bottom-4"
              style={{animationDelay: `${idx * 50}ms`}}
            >
              <div className="bg-white rounded-2xl overflow-hidden shadow-md hover:shadow-2xl transition-all duration-500 transform hover:-translate-y-2">
                {/* Product Image */}
                <div className={`h-48 md:h-56 bg-gradient-to-br ${product.gradient} relative overflow-hidden`}>
                  <div className="absolute inset-0 opacity-0 group-hover:opacity-100 transition-opacity duration-300 bg-black/5"></div>
                  <div className="absolute top-4 right-4 w-10 h-10 bg-white rounded-full flex items-center justify-center shadow-lg group-hover:scale-110 transition-transform">
                    <Heart className="w-5 h-5 text-pink-400" />
                  </div>
                </div>

                {/* Product Info */}
                <div className="p-5 md:p-6">
                  <div className="flex items-start justify-between mb-2">
                    <h3 className="font-bold text-gray-800 group-hover:text-rose-500 transition-colors flex-1">
                      {product.name}
                    </h3>
                  </div>

                  <p className="text-sm text-gray-600 mb-3 line-clamp-2">
                    {product.description}
                  </p>

                  <div className="flex items-center gap-1 mb-4">
                    {[...Array(5)].map((_, i) => (
                      <Star key={i} className="w-3 h-3 fill-amber-400 text-amber-400" />
                    ))}
                    <span className="text-xs text-gray-500 ml-1">(5)</span>
                  </div>

                  <div className="flex items-center justify-between mb-4">
                    <p className="text-2xl font-black bg-gradient-to-r from-pink-500 to-rose-500 bg-clip-text text-transparent">
                      {product.price}
                    </p>
                  </div>

                  <a
                    href={whatsappLink(product.name)}
                    target="_blank"
                    rel="noopener noreferrer"
                    className="w-full py-3 bg-gradient-to-r from-pink-500 to-rose-500 text-white font-bold rounded-xl hover:shadow-lg hover:shadow-pink-300/50 transition-all duration-300 flex items-center justify-center gap-2 group/btn"
                  >
                    <MessageCircle className="w-5 h-5" />
                    <span>Order on WhatsApp</span>
                  </a>
                </div>
              </div>
            </div>
          ))}
        </div>
      </div>
    </div>
  );

  const AboutPage = () => (
    <div className="pt-20 min-h-screen bg-gradient-to-b from-white to-pink-50 pb-20">
      <div className="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
        <div className="text-center mb-12 animate-in fade-in slide-in-from-top-4">
          <h2 className="text-4xl md:text-5xl font-black mb-4">
            <span className="bg-gradient-to-r from-pink-500 to-rose-500 bg-clip-text text-transparent">
              About Warembo
            </span>
          </h2>
        </div>

        <div className="grid md:grid-cols-2 gap-12 items-center">
          <div className="space-y-6">
            <div className="bg-gradient-to-br from-pink-200 to-rose-200 rounded-2xl p-12 text-center h-64 flex items-center justify-center">
              <p className="text-6xl">🎁</p>
            </div>
          </div>

          <div className="space-y-6">
            <p className="text-lg text-gray-700 leading-relaxed">
              Warembo Gift Shop specializes in <span className="font-bold bg-gradient-to-r from-pink-500 to-rose-500 bg-clip-text text-transparent">curated gift packages</span> for birthdays, anniversaries, and special occasions.
            </p>

            <p className="text-lg text-gray-700 leading-relaxed">
              Every gift is carefully selected and beautifully packaged with attention to detail. We believe every moment deserves to be celebrated with thoughtful, elegant gifts.
            </p>

            <div className="space-y-4 pt-4">
              <div className="flex gap-4">
                <div className="text-2xl">💝</div>
                <div>
                  <h4 className="font-bold text-gray-800">Handpicked Selection</h4>
                  <p className="text-gray-600">Each gift is personally selected for quality and elegance</p>
                </div>
              </div>
              <div className="flex gap-4">
                <div className="text-2xl">🚚</div>
                <div>
                  <h4 className="font-bold text-gray-800">Fast Delivery</h4>
                  <p className="text-gray-600">Quick delivery within 24 hours in Eldoret</p>
                </div>
              </div>
              <div className="flex gap-4">
                <div className="text-2xl">💬</div>
                <div>
                  <h4 className="font-bold text-gray-800">Easy Ordering</h4>
                  <p className="text-gray-600">Simply message us on WhatsApp to place your order</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  );

  const ContactPage = () => (
    <div className="pt-20 min-h-screen bg-gradient-to-b from-white to-pink-50 pb-20">
      <div className="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
        <div className="text-center mb-12 animate-in fade-in slide-in-from-top-4">
          <h2 className="text-4xl md:text-5xl font-black mb-4">
            <span className="bg-gradient-to-r from-pink-500 to-rose-500 bg-clip-text text-transparent">
              Get in Touch
            </span>
          </h2>
          <p className="text-gray-600 text-lg">We'd love to hear from you!</p>
        </div>

        <div className="grid md:grid-cols-3 gap-6 mb-12">
          {[
            {
              icon: MessageCircle,
              label: 'WhatsApp',
              value: '+254 743 471232',
              color: 'from-green-400 to-green-500',
              link: 'https://wa.me/254743471232'
            },
            {
              icon: Phone,
              label: 'Phone',
              value: '0743 471232',
              color: 'from-blue-400 to-blue-500',
              link: 'tel:+254743471232'
            },
            {
              icon: MapPin,
              label: 'Location',
              value: 'Eldoret, Kenya',
              color: 'from-pink-400 to-rose-500',
              link: '#'
            }
          ].map((contact, idx) => (
            <a
              key={idx}
              href={contact.link}
              className="bg-white rounded-2xl p-8 text-center shadow-md hover:shadow-xl transition-all duration-300 transform hover:-translate-y-2 group"
            >
              <div className={`w-16 h-16 mx-auto mb-4 bg-gradient-to-br ${contact.color} rounded-full flex items-center justify-center group-hover:scale-110 transition-transform`}>
                <contact.icon className="w-8 h-8 text-white" />
              </div>
              <h3 className="font-bold text-gray-800 mb-2">{contact.label}</h3>
              <p className="text-gray-600">{contact.value}</p>
            </a>
          ))}
        </div>

        {/* Social Media */}
        <div className="bg-white rounded-2xl p-12 text-center shadow-md">
          <h3 className="text-2xl font-bold text-gray-800 mb-6">Follow Us</h3>
          <div className="flex justify-center gap-6">
            {[
              { icon: MessageCircle, name: 'WhatsApp', color: 'text-green-500', link: 'https://wa.me/254743471232' },
              { icon: Instagram, name: 'Instagram', color: 'text-pink-500', link: '#' },
              { icon: Facebook, name: 'Facebook', color: 'text-blue-600', link: '#' }
            ].map((social, idx) => (
              <a
                key={idx}
                href={social.link}
                target="_blank"
                rel="noopener noreferrer"
                className={`${social.color} hover:scale-125 transition-transform duration-300`}
                title={social.name}
              >
                <social.icon className="w-10 h-10" />
              </a>
            ))}
          </div>
        </div>
      </div>
    </div>
  );

  const Footer = () => (
    <footer className="bg-gradient-to-r from-gray-900 to-gray-800 text-white py-12">
      <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div className="grid md:grid-cols-3 gap-12 mb-8">
          <div>
            <div className="flex items-center space-x-2 mb-4">
              <div className="w-10 h-10 bg-gradient-to-br from-pink-400 to-rose-400 rounded-full flex items-center justify-center">
                <ShoppingBag className="w-5 h-5 text-white" />
              </div>
              <span className="font-bold text-lg">Warembo Gift Shop</span>
            </div>
            <p className="text-gray-400">Perfect gifts for every occasion</p>
          </div>

          <div>
            <h4 className="font-bold mb-4">Quick Links</h4>
            <ul className="space-y-2 text-gray-400">
              {['Home', 'Products', 'About', 'Contact'].map(link => (
                <li key={link}>
                  <button
                    onClick={() => setCurrentSection(link.toLowerCase())}
                    className="hover:text-pink-400 transition-colors"
                  >
                    {link}
                  </button>
                </li>
              ))}
            </ul>
          </div>

          <div>
            <h4 className="font-bold mb-4">Contact</h4>
            <div className="space-y-2 text-gray-400">
              <p>📞 +254 743 471232</p>
              <p>📍 Eldoret, Kenya</p>
              <p>💬 Order on WhatsApp</p>
            </div>
          </div>
        </div>

        <div className="border-t border-gray-700 pt-8 text-center text-gray-400">
          <p>&copy; 2024 Warembo Gift Shop. All rights reserved. Made with 💝</p>
        </div>
      </div>
    </footer>
  );

  const StickyWhatsAppButton = () => (
    <a
      href="https://wa.me/254743471232?text=Hi%20Warembo%20Gift%20Shop!%20I%20have%20a%20question%20about%20your%20gifts"
      target="_blank"
      rel="noopener noreferrer"
      className="fixed bottom-6 right-6 w-16 h-16 bg-gradient-to-r from-green-400 to-green-500 rounded-full flex items-center justify-center text-white shadow-lg hover:shadow-2xl transform hover:scale-110 transition-all duration-300 z-40 animate-pulse hover:animate-none"
      title="Chat with us on WhatsApp"
    >
      <MessageCircle className="w-8 h-8" />
    </a>
  );

  return (
    <div className="bg-white min-h-screen font-sans overflow-x-hidden">
      <Header />

      {currentSection === 'home' && <HomePage />}
      {currentSection === 'products' && <ProductsPage />}
      {currentSection === 'about' && <AboutPage />}
      {currentSection === 'contact' && <ContactPage />}

      <Footer />
      <StickyWhatsAppButton />
    </div>
  );
}
