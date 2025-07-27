<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Golden Nest Hotel - Abandze, Ghana</title>
  <style>
    /* Reset and base */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }

    body {
      background: #fff;
      color: #333;
      line-height: 1.6;
      scroll-behavior: smooth;
      padding-bottom: 60px;
    }

    a {
      color: #d4af37;
      text-decoration: none;
      transition: color 0.3s;
    }

    a:hover,
    a:focus {
      color: #8b6c00;
      outline: none;
    }

    /* Header */
    header {
      background: #d4af37;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 10px 20px;
      box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
      position: sticky;
      top: 0;
      z-index: 1000;
    }

    header img {
      height: 50px;
    }

    /* Hero Banner */
    .hero {
      position: relative;
      background: url('https://i.postimg.cc/tRdYgrCP/e630db9e931df9ea09a6090cf5dbfa89.jpg')
        center/cover no-repeat;
      height: 500px;
      display: flex;
      justify-content: center;
      align-items: center;
      color: white;
      text-align: center;
      padding: 0 20px;
      overflow: hidden;
    }

    .hero::after {
      content: '';
      position: absolute;
      inset: 0;
      background-color: rgba(0, 0, 0, 0.4);
      z-index: 0;
    }

    .hero-content {
      position: relative;
      z-index: 1;
      max-width: 700px;
    }

    /* --- ANIMATIONS for hero text --- */
    .hero-content h1,
    .hero-content p {
      opacity: 0;
      transform: translateY(20px);
      animation-fill-mode: forwards;
      animation-duration: 1s;
      animation-timing-function: ease-out;
    }

    .hero-content h1 {
      animation-name: fadeSlideIn;
      animation-delay: 0.3s;
    }

    .hero-content p {
      animation-name: fadeSlideIn;
      animation-delay: 0.8s;
    }

    @keyframes fadeSlideIn {
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    .hero-content h1 {
      font-size: 3rem;
      margin-bottom: 15px;
      text-shadow: 2px 2px 6px rgba(0, 0, 0, 0.7);
    }

    .hero-content p {
      font-size: 1.2rem;
      margin-bottom: 25px;
      text-shadow: 1px 1px 6px rgba(0, 0, 0, 0.5);
    }

    .hero-content a.btn {
      background-color: #d4af37;
      color: #222;
      padding: 15px 30px;
      border-radius: 30px;
      font-weight: 700;
      font-size: 1.1rem;
      text-decoration: none;
      box-shadow: 0 4px 15px rgba(212, 175, 55, 0.6);
      transition: background-color 0.3s, color 0.3s, transform 0.2s ease;
      display: inline-block;
      cursor: pointer;
    }

    /* Button hover scale and color effect */
    .hero-content a.btn:hover,
    .hero-content a.btn:focus {
      background-color: #b38e04;
      color: white;
      outline: none;
      transform: scale(1.05);
    }

    /* Main content */
    main {
      max-width: 1200px;
      margin: 40px auto;
      padding: 0 20px 60px;
    }

    h2 {
      color: #d4af37;
      margin-bottom: 20px;
      font-size: 2.5rem;
      border-bottom: 4px solid #d4af37;
      padding-bottom: 8px;
      font-weight: 700;
      letter-spacing: 1px;
    }

    p {
      margin-bottom: 20px;
      font-size: 1.1rem;
    }

    /* Slideshow */
    .slideshow {
      position: relative;
      max-width: 100%;
      width: 100%;
      height: 400px;
      overflow: hidden;
      border-radius: 12px;
      box-shadow: 0 6px 20px rgba(0, 0, 0, 0.2);
      margin-bottom: 50px;
    }

    .slides {
      display: flex;
      transition: transform 0.6s cubic-bezier(.8, .01, .27, 1);
      height: 100%;
    }

    .slides img {
      width: 100%;
      height: 400px;
      object-fit: cover;
      flex-shrink: 0;
      border-radius: 12px;
    }

    /* Hide images after the first four */
    .slides img:nth-child(n+5) {
      display: none;
    }

    .slide-buttons {
      position: absolute;
      bottom: 20px;
      left: 50%;
      transform: translateX(-50%);
      z-index: 2;
      display: flex;
      gap: 8px;
    }

    .slide-buttons button {
      border: none;
      background: #d4af37;
      margin: 0 3px;
      width: 16px;
      height: 16px;
      border-radius: 50%;
      cursor: pointer;
      opacity: 0.6;
      transition: opacity 0.3s;
    }

    .slide-buttons button.active,
    .slide-buttons button:hover,
    .slide-buttons button:focus {
      opacity: 1;
      outline: none;
    }

    /* Section Styles */
    section {
      margin-bottom: 60px;
    }

    /* Rooms */
    .rooms {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
      gap: 30px;
    }

    .room-card {
      border: 1px solid #ccc;
      border-radius: 12px;
      overflow: hidden;
      box-shadow: 0 3px 12px rgba(0, 0, 0, 0.12);
      background: #fff;
      transition: box-shadow 0.4s ease, transform 0.3s ease;
      display: flex;
      flex-direction: column;
      cursor: default;
    }

    /* Room card hover lift */
    .room-card:hover {
      transform: translateY(-8px);
      box-shadow: 0 12px 30px rgba(0, 0, 0, 0.35);
    }

    .room-card img {
      width: 100%;
      height: 220px;
      object-fit: cover;
    }

    .room-info {
      padding: 18px 20px;
      flex-grow: 1;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }

    .room-info h3 {
      margin-bottom: 12px;
      color: #8b6c00;
      font-weight: 700;
      font-size: 1.6rem;
      letter-spacing: 0.03em;
    }

    .room-info p {
      font-size: 1rem;
      color: #555;
      flex-grow: 1;
      margin-bottom: 12px;
    }

    .room-price {
      color: #d4af37;
      font-weight: 700;
      font-size: 1.2rem;
    }

    /* Amenities with icons */
    .amenities-list {
      list-style: none;
      display: flex;
      flex-wrap: wrap;
      gap: 20px;
      font-size: 1.1rem;
      padding-left: 0;
    }

    .amenities-list li {
      background: #d4af37;
      color: white;
      padding: 12px 22px;
      border-radius: 25px;
      font-weight: 700;
      box-shadow: 0 3px 8px rgba(212, 175, 55, 0.6);
      display: flex;
      align-items: center;
      gap: 10px;
      flex-basis: calc(33.333% - 20px);
      max-width: calc(33.333% - 20px);
      opacity: 0;
      transform: translateY(15px);
      transition: opacity 0.6s ease, transform 0.6s ease;
    }

    /* Amenities visible on scroll */
    .amenities-list li.visible {
      opacity: 1;
      transform: translateY(0);
    }

    /* Booking Form */
    form {
      max-width: 600px;
      background: #f9f9f9;
      padding: 25px 30px;
      border-radius: 12px;
      box-shadow: 0 3px 15px rgba(0, 0, 0, 0.1);
      font-size: 1rem;
    }

    form label {
      display: block;
      margin-bottom: 6px;
      font-weight: 700;
      font-size: 1rem;
      color: #444;
    }

    form input,
    form select,
    form textarea {
      width: 100%;
      padding: 10px 12px;
      margin-bottom: 20px;
      border: 1px solid #ccc;
      border-radius: 6px;
      font-size: 1rem;
      transition: border-color 0.3s;
      font-family: inherit;
      resize: vertical;
      box-sizing: border-box;
    }

    form input:focus,
    form select:focus,
    form textarea:focus {
      border-color: #d4af37;
      outline: none;
      box-shadow: 0 0 5px #d4af37;
    }

    form button {
      background: #d4af37;
      color: #222;
      font-weight: 800;
      border: none;
      padding: 15px 32px;
      border-radius: 30px;
      cursor: pointer;
      font-size: 1.2rem;
      letter-spacing: 0.05em;
      box-shadow: 0 5px 15px rgba(212, 175, 55, 0.6);
      transition: background-color 0.3s, color 0.3s, transform 0.2s ease;
      display: inline-block;
    }

    form button:hover,
    form button:focus {
      background: #b38e04;
      color: white;
      outline: none;
      transform: scale(1.05);
    }

    /* WhatsApp Button */
    .whatsapp-btn {
      display: inline-block;
      background: #25d366;
      color: white;
      padding: 14px 24px;
      border-radius: 30px;
      font-weight: 700;
      font-size: 1.1rem;
      text-decoration: none;
      margin-top: 15px;
      box-shadow: 0 5px 15px rgba(37, 211, 102, 0.7);
      transition: background 0.3s;
    }

    .whatsapp-btn:hover,
    .whatsapp-btn:focus {
      background: #1ebe57;
      outline: none;
    }

    /* Video Container */
    .video-container {
      position: relative;
      padding-bottom: 56.25%;
      height: 0;
      overflow: hidden;
      max-width: 100%;
      border-radius: 12px;
      box-shadow: 0 6px 20px rgba(0, 0, 0, 0.25);
    }

    .video-container iframe,
    .video-container video {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      border-radius: 12px;
    }

    /* Testimonials Section */
    .testimonials {
      background-color: #f9f7f1;
      padding: 40px 20px;
      border-radius: 12px;
      box-shadow: 0 6px 20px rgba(0, 0, 0, 0.1);
    }

    .testimonials h2 {
      margin-bottom: 30px;
      text-align: center;
      letter-spacing: 1.5px;
    }

    .testimonial-cards {
      display: flex;
      gap: 25px;
      flex-wrap: wrap;
      justify-content: center;
    }

    .testimonial-card {
      background: white;
      border-radius: 12px;
      box-shadow: 0 2px 10px rgba(0, 0, 0, 0.12);
      padding: 25px;
      max-width: 350px;
      display: flex;
      flex-direction: column;
      align-items: center;
      font-style: italic;
      font-size: 1.1rem;
      color: #555;
      position: relative;
    }

    .testimonial-card::before {
      content: "“";
      font-size: 3rem;
      color: #d4af37;
      position: absolute;
      top: 10px;
      left: 20px;
      opacity: 0.3;
      font-family: serif;
      font-weight: bold;
    }

    .testimonial-author {
      margin-top: 14px;
      font-weight: 700;
      font-style: normal;
      color: #8b6c00;
      font-size: 1rem;
      text-align: center;
    }

    /* FAQ Section */
    .faq-item {
      margin-bottom: 20px;
    }

    .faq-question {
      font-weight: 700;
      font-size: 1.1rem;
      cursor: pointer;
      padding: 16px 20px;
      background: #d4af37;
      color: white;
      border-radius: 10px;
      box-shadow: 0 4px 15px rgba(212, 175, 55, 0.7);
      user-select: none;
      position: relative;
      transition: background 0.3s ease;
    }

    .faq-question:hover,
    .faq-question:focus {
      background: #b38e04;
      outline: none;
    }

    /* Toggle icon '+' and '-' */
    .faq-question::after {
      content: '+';
      position: absolute;
      right: 25px;
      font-size: 1.5rem;
      line-height: 1;
      transition: transform 0.3s ease;
    }

    .faq-question.active::after {
      content: "-";
      transform: rotate(180deg);
    }

    .faq-answer {
      max-height: 0;
      overflow: hidden;
      transition: max-height 0.4s ease, padding 0.4s ease;
      background: #f9f7f1;
      padding: 0 20px;
      border-radius: 0 0 10px 10px;
      box-shadow: inset 0 1px 3px rgba(0, 0, 0, 0.1);
      font-size: 1rem;
      color: #444;
    }

    .faq-answer p {
      padding: 15px 0;
      margin: 0;
    }

    .faq-answer.visible {
      padding: 15px 20px;
    }

    /* Gallery */
    .gallery {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 20px;
      border-radius: 12px;
    }

    .gallery img {
      width: 100%;
      height: 190px;
      object-fit: cover;
      border-radius: 12px;
      box-shadow: 0 4px 15px rgba(0, 0, 0, 0.15);
      transition: transform 0.3s ease;
      cursor: pointer;
    }

    .gallery img:hover,
    .gallery img:focus {
      transform: scale(1.05);
      outline: none;
    }

    /* Offers */
    .offers {
      background: #f8f4e8;
      border-radius: 12px;
      padding: 30px 25px;
      box-shadow: 0 4px 15px rgba(212, 175, 55, 0.4);
      text-align: center;
    }

    .offer-item {
      margin-bottom: 25px;
    }

    .offer-title {
      font-size: 1.5rem;
      font-weight: 700;
      color: #8b6c00;
      margin-bottom: 8px;
    }

    .offer-description {
      font-size: 1.1rem;
      color: #444;
    }

    /* Footer */
    footer {
      background: #222;
      color: #eee;
      text-align: center;
      padding: 40px 20px 20px;
      margin-top: 80px;
      font-size: 0.95rem;
      line-height: 1.5;
      position: relative;
      z-index: 10;
    }

    footer a {
      color: #d4af37;
      font-weight: 600;
      transition: text-decoration 0.3s;
    }

    footer a:hover,
    footer a:focus {
      text-decoration: underline;
      outline: none;
    }

    .social-links {
      margin-top: 18px;
      display: flex;
      justify-content: center;
      gap: 25px;
    }

    .social-links a {
      color: #d4af37;
      font-size: 1.8rem;
      transition: color 0.3s;
    }

    .social-links a:hover,
    .social-links a:focus {
      color: #b38e04;
      outline: none;
    }

    /* Newsletter form */
    .newsletter {
      margin-top: 25px;
      font-size: 1rem;
      color: #eee;
    }

    .newsletter form {
      margin-top: 12px;
    }

    .newsletter input[type="email"] {
      padding: 10px 14px;
      border-radius: 30px 0 0 30px;
      border: none;
      width: 250px;
      font-size: 1rem;
      outline: none;
      border: 1px solid #d4af37;
      border-right: none;
      box-sizing: border-box;
    }

    .newsletter button {
      padding: 10px 24px;
      border-radius: 0 30px 30px 0;
      border: none;
      background: #d4af37;
      color: #222;
      font-weight: 700;
      cursor: pointer;
      transition: background-color 0.3s;
      font-size: 1rem;
    }

    .newsletter button:hover,
    .newsletter button:focus {
      background: #b38e04;
      outline: none;
    }

    /* Responsive Adjustments */
    @media (max-width: 900px) {
      .amenities-list li {
        flex-basis: calc(50% - 20px);
        max-width: calc(50% - 20px);
      }

      .testimonials {
        padding: 30px 10px;
      }

      .testimonial-cards {
        flex-direction: column;
        align-items: center;
      }

      .room-info p {
        font-size: 0.95rem;
      }

      form {
        padding: 20px;
      }
    }

    @media (max-width: 600px) {
      header {
        flex-direction: column;
        align-items: flex-start;
        gap: 15px;
      }

      nav {
        justify-content: flex-start;
      }

      nav a {
        margin-left: 0;
        padding: 6px 10px;
        font-size: 0.95rem;
      }

      h2 {
        font-size: 2rem;
      }

      .slideshow {
        height: 220px;
        border-radius: 10px;
      }

      .slides img {
        height: 220px;
        border-radius: 10px;
      }

      nav a:hover,
      nav a:focus {
        background-color: #b38e04;
        color: white;
      }

      .amenities-list li {
        flex-basis: 100%;
        max-width: 100%;
        justify-content: center;
      }
    }

    /* Bottom Navigation */
    .bottom-nav {
      background: #d4af37;
      display: flex;
      justify-content: center;
      gap: 15px;
      position: fixed;
      bottom: 0;
      width: 100%;
      padding: 10px 0;
      z-index: 10000;
      box-shadow: 0 -2px 8px rgba(0, 0, 0, 0.15);
    }

    .bottom-nav a {
      color: #333;
      font-weight: 600;
      padding: 8px 12px;
      border-radius: 4px;
      text-decoration: none;
      transition: background-color 0.3s, color 0.3s, transform 0.2s ease;
      cursor: pointer;
    }

    .bottom-nav a:hover,
    .bottom-nav a:focus {
      background-color: #b38e04;
      color: #fff;
      outline: none;
      transform: scale(1.05);
    }
  </style>
</head>

<body>

  <header>
    <img src="https://i.postimg.cc/pL5vmTY7/4e67064c30d0cb1c0a2772351d283d94.jpg" alt="Golden Nest Hotel Logo" loading="lazy" />
  </header>

  <!-- Hero Banner -->
  <section class="hero" id="home" aria-label="Welcome banner">
    <div class="hero-content">
      <h1>Welcome to Golden Nest Hotel</h1>
      <p>Your perfect coastal retreat in Abandze, Ghana — where luxury meets warm hospitality by the sea.</p>
      <a href="#booking" class="btn" role="button" aria-label="Book Your Stay">Book Your Stay</a>
    </div>
  </section>

  <main>

    <!-- Slideshow -->
    <section aria-label="Hotel slideshow">
      <div class="slideshow">
        <div class="slides" id="slides">
          <img src="https://i.postimg.cc/tRdYgrCP/e630db9e931df9ea09a6090cf5dbfa89.jpg" alt="Hotel Exterior" loading="lazy" />
          <img src="https://i.postimg.cc/8ckDcmtB/260f88be8da5579ee837606bd93c256b.jpg" alt="Lobby" loading="lazy" />
          <img src="https://i.postimg.cc/pL5vmTY7/4e67064c30d0cb1c0a2772351d283d94.jpg" alt="Hotel Logo" loading="lazy" />
          <img src="https://i.postimg.cc/MHrkT2cq/dc87a8f8ebb246fcc5a7e811e7629de9.jpg" alt="Deluxe Room" loading="lazy" />
          <!-- The following images will be hidden via CSS -->
          <img src="https://i.postimg.cc/Y0GWyKJQ/spa-wellness.jpg" alt="Spa and Wellness Center" loading="lazy" />
          <img src="https://i.postimg.cc/d1CnLZ1L/restaurant-bar.jpg" alt="Restaurant and Bar" loading="lazy" />
        </div>
        <div class="slide-buttons" id="slide-buttons" role="tablist" aria-label="Slideshow navigation"></div>
      </div>
    </section>

    <!-- About -->
    <section id="about" aria-labelledby="about-title">
      <h2 id="about-title">About Golden Nest Hotel</h2>
      <p>Golden Nest Hotel in Abandze is a premier destination for travelers seeking both comfort and authenticity in Ghana. Established in 2005, our philosophy revolves around blending traditional Ghanaian warmth with modern luxury to provide an unparalleled guest experience.</p>
      <p>Located just steps away from the pristine beach, our hotel invites you to indulge in a serene environment, premium amenities, and personalized service — whether you're here for business meetings, romantic getaways, or family vacations.</p>
    </section>

    <!-- Rooms -->
    <section id="rooms" aria-labelledby="rooms-title">
      <h2 id="rooms-title">Our Rooms</h2>
      <div class="rooms">
        <article class="room-card" aria-label="Deluxe Room">
          <img src="https://i.postimg.cc/MHrkT2cq/dc87a8f8ebb246fcc5a7e811e7629de9.jpg" alt="Deluxe Room interior with queen bed" loading="lazy" />
          <div class="room-info">
            <h3>Deluxe Room</h3>
            <p>Spacious room with queen bed, ensuite bathroom, free Wi-Fi, air conditioning, and sea view balcony.</p>
            <p><strong>Amenities:</strong> Flat-screen TV, minibar, coffee machine, 24/7 room service</p>
            <p class="room-price">From $120 per night</p>
          </div>
        </article>
        <article class="room-card" aria-label="Executive Suite">
          <img src="https://i.postimg.cc/8ckDcmtB/260f88be8da5579ee837606bd93c256b.jpg" alt="Executive Suite with separate living room" loading="lazy" />
          <div class="room-info">
            <h3>Executive Suite</h3>
            <p>Luxurious suite featuring separate living area, king-sized bed, walk-in closet, premium bathroom with jacuzzi, and balcony.</p>
            <p><strong>Amenities:</strong> Smart TV, minibar, Nespresso machine, 24/7 concierge</p>
            <p class="room-price">From $220 per night</p>
          </div>
        </article>
        <article class="room-card" aria-label="Standard Room">
          <img src="https://i.postimg.cc/tRdYgrCP/e630db9e931df9ea09a6090cf5dbfa89.jpg" alt="Standard room with twin beds" loading="lazy" />
          <div class="room-info">
            <h3>Standard Room</h3>
            <p>Cozy and comfortable room equipped with essentials, ideal for solo travelers or couples.</p>
            <p><strong>Amenities:</strong> Free Wi-Fi, television, air conditioning, private bathroom</p>
            <p class="room-price">From $80 per night</p>
          </div>
        </article>
      </div>
    </section>

    <!-- Amenities -->
    <section id="amenities" aria-labelledby="amenities-title">
      <h2 id="amenities-title">Amenities</h2>
      <ul class="amenities-list">
        <li>Free Wi-Fi</li>
        <li>Beachfront Pool</li>
        <li>Spa & Wellness Center</li>
        <li>Fine Dining Restaurant</li>
        <li>24/7 Room Service</li>
        <li>Airport Shuttle</li>
      </ul>
    </section>

    <!-- Booking Section -->
    <section id="booking" aria-labelledby="booking-title">
      <h2 id="booking-title">Book Your Room</h2>
      <form id="booking-form" aria-describedby="booking-instructions" novalidate>
        <p id="booking-instructions">Please fill in your details and select your room.</p>

        <label for="fullName">Full Name</label>
        <input type="text" id="fullName" name="fullName" required autocomplete="name" />

        <label for="email">Email Address</label>
        <input type="email" id="email" name="email" required autocomplete="email" />

        <label for="roomType">Room Type</label>
        <select id="roomType" name="roomType" required>
          <option value="" disabled selected>Select a room</option>
          <option value="Standard Room">Standard Room - $80/night</option>
          <option value="Deluxe Room">Deluxe Room - $120/night</option>
          <option value="Executive Suite">Executive Suite - $220/night</option>
        </select>

        <label for="checkin">Check-in Date</label>
        <input type="date" id="checkin" name="checkin" required />

        <label for="checkout">Check-out Date</label>
        <input type="date" id="checkout" name="checkout" required />

        <button type="submit" aria-live="polite">Submit Booking</button>
      </form>
      <p id="booking-message" role="alert" style="color:green; display:none; margin-top:10px;"></p>
    </section>

    <!-- FAQ -->
    <section id="faq" aria-labelledby="faq-title">
      <h2 id="faq-title">Frequently Asked Questions</h2>

      <article class="faq-item">
        <button class="faq-question" aria-expanded="false" aria-controls="faq1" id="faq1-btn">What is the check-in and check-out time?</button>
        <div id="faq1" class="faq-answer" hidden>
          <p>Check-in starts at 2 PM, and check-out is by 12 PM noon.</p>
        </div>
      </article>

      <article class="faq-item">
        <button class="faq-question" aria-expanded="false" aria-controls="faq2" id="faq2-btn">Do you offer airport transfers?</button>
        <div id="faq2" class="faq-answer" hidden>
          <p>Yes, airport shuttle service is available on request at an additional charge.</p>
        </div>
      </article>
      <!-- You can add more FAQ items below similarly -->
    </section>

  </main>

  <!-- Bottom Navigation -->
  <nav aria-label="Primary navigation" class="bottom-nav">
    <a href="#home">Home</a>
    <a href="#about">About</a>
    <a href="#rooms">Rooms</a>
    <a href="#amenities">Amenities</a>
    <a href="#booking">Booking</a>
    <a href="#faq">FAQ</a>
  </nav>

  <footer>
    <p>© 2025 Golden Nest Hotel, Abandze, Ghana</p>
    <p>Contact us: <a href="mailto:appiahnicholas2004@gmail.com">appiahnicholas2004@gmail.com</a> |
      Phone: <a href="tel:+233257441614">+233 257 441 614</a></p>
    <div class="social-links" role="list" aria-label="Social media links">
      <a href="https://facebook.com" target="_blank" rel="noopener noreferrer" aria-label="Facebook">📷</a>
      <a href="https://instagram.com" target="_blank" rel="noopener noreferrer" aria-label="Instagram">📸</a>
      <a href="https://twitter.com" target="_blank" rel="noopener noreferrer" aria-label="Twitter">🐦</a>
      <a href="https://linkedin.com" target="_blank" rel="noopener noreferrer" aria-label="LinkedIn">👥</a>
    </div>
    <div class="newsletter" aria-label="Newsletter subscription">
      <p>Subscribe for exclusive offers & updates</p>
      <form>
        <label for="newsletter-email" class="visually-hidden">Email address</label>
        <input type="email" id="newsletter-email" name="newsletter-email" placeholder="Your email" required />
        <button type="submit">Subscribe</button>
      </form>
    </div>
  </footer>

  <script>
    // Slideshow functionality with limit to first 4 images
    const slides = document.getElementById('slides');
    const slideButtons = document.getElementById('slide-buttons');
    const maxSlides = 4; // Limit to first 4 slides only
    const totalSlides = Math.min(slides.children.length, maxSlides);
    let currentIndex = 0;
    let intervalId = null;

    function showSlide(index) {
      if (index < 0) index = totalSlides - 1;
      if (index >= totalSlides) index = 0;
      slides.style.transition = "transform 0.6s ease";
      slides.style.transform = `translateX(${-index * 100}%)`;
      currentIndex = index;
      updateButtons();
    }

    function updateButtons() {
      const buttons = slideButtons.querySelectorAll('button');
      buttons.forEach((btn, idx) => {
        btn.classList.toggle('active', idx === currentIndex);
        btn.setAttribute('aria-label', `Go to slide ${idx + 1}`);
      });
    }

    // Create buttons only for first 4 slides
    slideButtons.innerHTML = '';
    for (let i = 0; i < totalSlides; i++) {
      const btn = document.createElement('button');
      btn.setAttribute('aria-label', `Go to slide ${i + 1}`);
      btn.addEventListener('click', () => {
        clearInterval(intervalId); // Stop auto-slide on manual
        showSlide(i);
        intervalId = setInterval(() => showSlide(currentIndex + 1), 5000); // Restart auto-slide
      });
      slideButtons.appendChild(btn);
    }

    showSlide(0);

    intervalId = setInterval(() => {
      showSlide(currentIndex + 1);
    }, 5000);

    window.addEventListener('beforeunload', () => {
      clearInterval(intervalId);
    });

    // FAQ Accordion Interactivity with animation
    const faqButtons = document.querySelectorAll('.faq-question');
    faqButtons.forEach(button => {
      const answer = document.getElementById(button.getAttribute('aria-controls'));

      button.addEventListener('click', () => {
        const expanded = button.getAttribute('aria-expanded') === 'true';
        button.setAttribute('aria-expanded', !expanded);
        button.classList.toggle('active');

        if (!expanded) {
          answer.removeAttribute('hidden');
          answer.classList.add('visible');
          answer.style.maxHeight = answer.scrollHeight + "px";
        } else {
          answer.setAttribute('hidden', '');
          answer.classList.remove('visible');
          answer.style.maxHeight = null;
        }
      });

      // Keyboard accessibility
      button.addEventListener('keydown', e => {
        if (e.key === 'Enter' || e.key === ' ') {
          e.preventDefault();
          button.click();
        }
      });
    });

    // Set min attribute for check-in and check-out dates dynamically (today and next day)
    const checkin = document.getElementById('checkin');
    const checkout = document.getElementById('checkout');
    if (checkin && checkout) {
      const today = new Date().toISOString().split('T')[0];
      checkin.min = today;
      checkout.min = today;

      checkin.addEventListener('change', () => {
        if (checkin.value >= checkout.value) {
          const nextDay = new Date(new Date(checkin.value).getTime() + 86400000).toISOString().split('T')[0];
          checkout.value = nextDay;
          checkout.min = nextDay;
        }
      });
    }

    // Booking form submission handler (demo only)
    document.getElementById('booking-form').addEventListener('submit', function (e) {
      e.preventDefault();
      const fullName = e.target.fullName.value.trim();
      const email = e.target.email.value.trim();
      const roomType = e.target.roomType.value;
      const checkinVal = e.target.checkin.value;
      const checkoutVal = e.target.checkout.value;

      // Additional simple validation
      if (!fullName || !email || !roomType || !checkinVal || !checkoutVal) {
        alert('Please fill out all required fields.');
        return;
      }

      // Simple date validation
      if (checkinVal >= checkoutVal) {
        alert('Check-out date must be after check-in date.');
        return;
      }

      const messageEl = document.getElementById('booking-message');
      messageEl.textContent = `Thank you, ${fullName}! Your booking request for a ${roomType} from ${checkinVal} to ${checkoutVal} has been received. We will contact you shortly at ${email}.`;
      messageEl.style.display = 'block';

      e.target.reset();
      checkin.min = new Date().toISOString().split('T')[0];
      checkout.min = checkin.min;
    });

    // Animate amenities items on scroll into view using IntersectionObserver
    const amenitiesItems = document.querySelectorAll('.amenities-list li');
    const observer = new IntersectionObserver(entries => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
          observer.unobserve(entry.target);
        }
      });
    }, { threshold: 0.1 });

    amenitiesItems.forEach(item => observer.observe(item));

    // Smooth scroll fallback for all anchor links (bottom nav + hero btn)
    document.querySelectorAll('.bottom-nav a, .hero-content a.btn').forEach(anchor => {
      anchor.addEventListener('click', function (e) {
        const href = this.getAttribute('href');
        if (!href.startsWith('#')) return; // Skip external if any

        const targetId = href.slice(1);
        const targetEl = document.getElementById(targetId);
        if (targetEl) {
          e.preventDefault();
          targetEl.scrollIntoView({ behavior: 'smooth' });
          // Optionally update the URL hash without default jump:
          history.pushState(null, '', href);
        }
      });
    });
  </script>
</body>

</html>
