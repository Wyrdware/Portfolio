---
title: "Contact Me"
type: "page"
layout: "page"
classes: ["contact-page"]

---

{{< social >}}

If you are looking to hire a dynamic and passionate systems-focused programmer with a record of elevating those around them, or just want to know more about me or my projects, please reach out through the contact form below.

<div class="contact-wrapper">

<form action="https://formspree.io/f/xzzvzdje" method="POST">
  <label for="name">Name:</label><br>
  <input type="text" id="name" name="name" required><br>

  <label for="email">Email:</label><br>
  <input type="email" id="email" name="email" required><br>

  <label for="message">Message:</label><br>
  <textarea id="message" name="message" rows="5" required></textarea><br>

  <!-- Honeypot field (spam protection) -->
  <input type="text" name="_honey" style="display:none">

  <!-- Optional redirect -->
  <input type="hidden" name="_redirect" value="https://jaredgoronkin.com/thank-you/">

  <button type="submit">Send</button>
</form>

</div>
