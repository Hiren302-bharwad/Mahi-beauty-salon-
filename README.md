<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Mahi Beauty Parlour</title>
  <style>
    /* Reset & basics */
    * {
      box-sizing: border-box;
    }
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      margin: 0;
      padding: 0;
      background: #fff8f0;
      color: #333;
      scroll-behavior: smooth;
    }
    a {
      color: #a64100;
      text-decoration: none;
    }
    a:hover,
    a:focus {
      text-decoration: underline;
      color: #c04e01;
      outline: none;
    }

    /* Header navigation */
    header {
      background-color: #f3b26a;
      padding: 1rem 0;
      position: sticky;
      top: 0;
      z-index: 1000;
      box-shadow: 0 4px 6px rgba(177, 78, 1, 0.3);
    }
    nav {
      max-width: 900px;
      margin: 0 auto;
      display: flex;
      justify-content: center;
      gap: 2rem;
      font-weight: 600;
      font-size: 1.1rem;
      flex-wrap: wrap;
    }
    nav a {
      padding: 0.4em 0.8em;
      border-radius: 5px;
      transition: background-color 0.3s ease, color 0.3s ease;
    }
    nav a:hover,
    nav a:focus {
      background-color: #c04e01;
      color: white;
    }

    /* Main container */
    main {
      max-width: 900px;
      margin: 2rem auto 4rem;
      padding: 0 1rem;
    }

    /* Page title */
    h1 {
      text-align: center;
      font-size: 2.8rem;
      letter-spacing: 2px;
      margin-top: 1rem;
      margin-bottom: 0.5rem;
      color: #a64100;
    }

    /* Section headings */
    h2 {
      color: #a64100;
      border-bottom: 3px solid #c04e01;
      padding-bottom: 0.3em;
      margin-bottom: 1rem;
    }

    /* About Section */
    #about p {
      font-size: 1.1rem;
      line-height: 1.6;
      margin-bottom: 1.5rem;
    }
    #about p.owner-name {
      font-style: italic;
      font-weight: 600;
      color: #8b2c00;
      margin-top: -1rem;
    }

    /* Services */
    .services-list {
      list-style: none;
      padding-left: 0;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
      gap: 1rem;
      margin-bottom: 2rem;
    }
    .services-list li {
      background: #fce6d0;
      border: 2px solid #f0a55a;
      border-radius: 10px;
      padding: 1em;
      text-align: center;
      font-weight: 600;
      color: #a04100;
      box-shadow: 0 2px 5px rgba(160, 65, 0, 0.15);
      transition: transform 0.3s ease, box-shadow 0.3s ease;
      cursor: default;
    }
    .services-list li:hover {
      transform: translateY(-6px);
      box-shadow: 0 8px 15px rgba(160, 65, 0, 0.3);
    }

    /* Offers */
    #offers ul {
      list-style-type: disc;
      padding-left: 1.5rem;
      font-weight: 600;
      color: #8b2c00;
      margin-bottom: 2rem;
    }
    #offers li {
      margin-bottom: 0.7em;
      transition: color 0.3s ease;
    }
    #offers li:hover {
      color: #b14a00;
    }

    /* Testimonials */
    .testimonials {
      margin-bottom: 2rem;
    }
    .testimonial {
      background: #fff3e6;
      border-left: 5px solid #c04e01;
      padding: 1em 1.5em;
      margin-bottom: 1.5rem;
      border-radius: 8px;
      box-shadow: 0 2px 6px rgba(192, 78, 1, 0.2);
    }
    .testimonial h4 {
      margin-bottom: 0.3em;
      color: #a64100;
      font-weight: 700;
    }
    .testimonial p {
      font-style: italic;
      font-size: 1rem;
      line-height: 1.4;
      margin: 0;
    }

    /* Contact Info */
    .contact-info p {
      font-weight: 600;
      margin-bottom: 0.8rem;
      font-size: 1rem;
    }
    .contact-info strong {
      color: #b14000;
    }

    /* Appointment Form */
    form.appointment-form {
      background: #fce6d0;
      padding: 1.5rem;
      border-radius: 10px;
      box-shadow: 0 4px 8px rgba(160, 65, 0, 0.2);
      max-width: 450px;
      margin: 0 auto 2rem;
      display: flex;
      flex-direction: column;
      gap: 1rem;
    }
    form.appointment-form label {
      font-weight: 600;
      margin-bottom: 0.3rem;
    }
    form.appointment-form input,
    form.appointment-form select {
      padding: 0.5rem;
      border-radius: 5px;
      border: 1.5px solid #d18f40;
      font-size: 1rem;
      transition: border-color 0.3s ease;
    }
    form.appointment-form input:focus,
    form.appointment-form select:focus {
      outline: none;
      border-color: #c04e01;
      box-shadow: 0 0 5px #c04e01;
    }
    form.appointment-form button {
      background-color: #c04e01;
      color: white;
      font-weight: 700;
      padding: 0.7rem;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      font-size: 1.1rem;
      transition: background-color 0.3s ease;
    }
    form.appointment-form button:hover,
    form.appointment-form button:focus {
      background-color: #a04100;
      outline: none;
    }

    /* Festival popup */
    #festival-popup {
      position: fixed;
      bottom: 20px;
      right: 20px;
      background: #f3b26a;
      padding: 1rem 1.5rem;
      border-radius: 12px;
      box-shadow: 0 4px 10px rgba(177, 78, 1, 0.4);
      font-weight: 700;
      color: #6c2200;
      cursor: pointer;
      display: flex;
      align-items: center;
      gap: 1rem;
      z-index: 1100;
    }
    #festival-popup button {
      background: transparent;
      border: none;
      font-weight: 700;
      color: #6c2200;
      font-size: 1.2rem;
      cursor: pointer;
    }

    /* Floating WhatsApp and Call buttons */
    .floating-buttons {
      position: fixed;
      bottom: 80px;
      right: 20px;
      display: flex;
      flex-direction: column;
      gap: 15px;
      z-index: 1100;
    }
    .floating-buttons a {
      background-color: #25d366;
      color: white;
      width: 50px;
      height: 50px;
      border-radius: 50%;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 24px;
      box-shadow: 0 3px 8px rgba(0,0,0,0.3);
      transition: background-color 0.3s ease;
    }
    .floating-buttons a.call {
      background-color: #4a90e2;
    }
    .floating-buttons a:hover,
    .floating-buttons a:focus {
      filter: brightness(0.9);
      outline: none;
    }

    /* Scroll to top button */
    #scrollTopBtn {
      position: fixed;
      bottom: 20px;
      left: 20px;
      background-color: #a04100;
      color: white;
      border: none;
      padding: 0.6rem 1rem;
      border-radius: 8px;
      font-weight: 700;
      font-size: 1.2rem;
      cursor: pointer;
      box-shadow: 0 3px 6px rgba(160, 65, 0, 0.4);
      display: none;
      z-index: 1100;
      transition: background-color 0.3s ease;
    }
    #scrollTopBtn:hover,
    #scrollTopBtn:focus {
      background-color: #c04e01;
      outline: none;
    }

    /* Footer */
    footer {
      text-align: center;
      padding: 1rem;
      background-color: #f3b26a;
      color: #6c2200;
      font-weight: 600;
      box-shadow: inset 0 1px 4px rgba(177, 78, 1, 0.3);
    }

    /* Responsive adjustments */
    @media (max-width: 480px) {
      nav {
        gap: 1rem;
        font-size: 1rem;
      }
      form.appointment-form {
        max-width: 100%;
      }
      .services-list {
        grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
      }
    }
  </style>
</head>
<body>

<header>
  <nav aria-label="Primary navigation">
    <a href="#about">About</a>
    <a href="#services">Services</a>
    <a href="#offers">Offers</a>
    <a href="#testimonials">Reviews</a>
    <a href="#contact">Contact</a>
    <a href="#appointment">Book Appointment</a>
  </nav>
</header>

<main>
  <h1>Mahi Beauty Parlour</h1>

  <section id="about" tabindex="-1">
    <h2>Glow With Confidence</h2>
    <p>Welcome to <strong>Mahi Beauty Parlour</strong>, your destination for professional beauty care in Rajkot. We offer a range of services with care, experience, and a personal touch.</p>
    <p><strong>Serving beauty with passion and care since 2017, Mahi Beauty Parlour has been trusted by hundreds of happy clients in Rajkot.</strong></p>
    <p class="owner-name">Owner: Shital Bharwad</p>
  </section>

  <section id="services" tabindex="-1">
    <h2>Our Services</h2>
    <ul class="services-list">
      <li>Eyebrows</li>
      <li>Wax</li>
      <li>Haircut</li>
      <li>Hairstyle</li>
      <li>Makeup</li>
      <li>Facial</li>
      <li>Manicure</li>
      <li>Pedicure</li>
      <li>Bodycare</li>
      <li>Skincare</li>
      <li>And more...</li>
    </ul>
  </section>

  <section id="offers" tabindex="-1">
    <h2>Festival Offers</h2>
    <ul>
      <li>Flat 20% off on all bridal makeup packages</li>
      <li>Buy 2 get 1 free on facials and skincare treatments</li>
      <li>Special discount on manicure and pedicure combo</li>
      <li>Free waxing session with every haircut</li>
      <li>Exclusive gift hampers on bookings above ₹3000</li>
    </ul>
  </section>

  <section id="testimonials" class="testimonials" tabindex="-1">
    <h2>What Our Clients Say</h2>
    <div class="testimonial" tabindex="0">
      <h4>Rina Patel</h4>
      <p>“Absolutely love the service! Very professional and friendly staff.”</p>
    </div>
    <div class="testimonial" tabindex="0">
      <h4>Krishna Mehta</h4>
      <p>“Best parlour in Rajkot. Their makeup and hairstyle work is top-notch!”</p>
    </div>
    <div class="testimonial" tabindex="0">
      <h4>Sheetal Joshi</h4>
      <p>“I always feel relaxed and beautiful after a facial here. Highly recommended.”</p>
    </div>
  </section>

  <section id="contact" class="contact-info" tabindex="-1">
    <h2>Contact Us</h2>
    <p><strong>Address:</strong> Mahi Beauty Saloon, Nr. Primary School, Street No.1, University Road, Munjka, Rajkot-360005</p>
    <p><strong>Phone:</strong> <a href="tel:+919316471580">+91 9316471580</a></p>
    <p><strong>Email:</strong> <a href="mailto:mahibeautysalon47@gmail.com">mahibeautysalon47@gmail.com</a></p>
    <p><strong>Instagram:</strong> <a href="https://instagram.com/mahi_beauty_salon_7" target="_blank" rel="noopener noreferrer">@mahi_beauty_salon_7</a></p>
    <p><strong>Location Map:</strong> <a href="https://www.google.com/maps/place/Mahi+Beauty+Saloon" target="_blank" rel="noopener noreferrer">View on Google Maps</a></p>
  </section>

  <section id="appointment" tabindex="-1">
    <h2>Book an Appointment</h2>
    <form class="appointment-form" onsubmit="alert('Thank you for booking! We will contact you shortly.'); return false;">
      <label for="name">Name:</label>
      <input type="text" id="name" name="name" required placeholder="Enter your name" />

      <label for="date">Date:</label>
      <input type="date" id="date" name="date" required />

      <label for="service">Service:</label>
      <select id="service" name="service" required>
        <option value="">Select Service</option>
        <option>Eyebrows</option>
        <option>Wax</option>
        <option>Haircut</option>
        <option>Hairstyle</option>
        <option>Makeup</option>
        <option>Facial</option>
        <option>Manicure</option>
        <option>Pedicure</option>
        <option>Bodycare</option>
        <option>Skincare</option>
      </select>

      <button type="submit">Book Now</button>
    </form>
  </section>
</main>

<!-- Festival Popup -->
<div id="festival-popup" role="alert" aria-live="assertive">
  Celebrate the Festival with 20% OFF on all Bridal Makeup Packages! Book Now!
  <button aria-label="Close festival offer" onclick="document.getElementById('festival-popup').style.display='none'">×</button>
</div>

<!-- Floating buttons -->
<div class="floating-buttons" aria-label="Contact options">
  <a href="https://wa.me/919316471580" target="_blank" rel="noopener noreferrer" aria-label="Contact on WhatsApp" title="WhatsApp">
    &#x1F4AC;
  </a>
  <a href="tel:+919316471580" class="call" aria-label="Call us" title="Call">
    &#x260E;
  </a>
</div>

<!-- Scroll to top button -->
<button id="scrollTopBtn" aria-label="Scroll to top" title="Scroll to top" onclick="window.scrollTo({top: 0, behavior: 'smooth'});">↑</button>

<footer>
  &copy; 2025 Mahi Beauty Parlour. All rights reserved.
</footer>

<script>
  // Show scroll button when scrolled down
  const scrollBtn = document.getElementById('scrollTopBtn');
  window.addEventListener('scroll', () => {
    if (window.scrollY > 200) {
      scrollBtn.style.display = 'block';
    } else {
      scrollBtn.style.display = 'none';
    }
  });
</script>

</body>
</html>