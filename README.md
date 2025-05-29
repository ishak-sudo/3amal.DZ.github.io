<!DOCTYPE html>
<html lang="ar">
<head>
  <meta charset="UTF-8">
  <title>3amal.Dz - اتصل بنا</title>
  <script src="https://cdn.emailjs.com/dist/email.min.js"></script>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f2f2f2;
      direction: rtl;
    }
    form {
      max-width: 500px;
      margin: 50px auto;
      padding: 20px;
      background: #fff;
      border-radius: 8px;
    }
    input, textarea {
      width: 100%;
      margin-bottom: 15px;
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 4px;
    }
    button {
      padding: 10px;
      width: 100%;
      background-color: #28a745;
      color: white;
      border: none;
      border-radius: 4px;
      font-size: 16px;
    }
    #status {
      text-align: center;
      margin-top: 15px;
      font-weight: bold;
    }
  </style>
</head>
<body>

  <form id="contact-form">
    <h2>اتصل بنا</h2>
    <input type="text" name="from_name" placeholder="الاسم الكامل" required>
    <input type="email" name="from_email" placeholder="البريد الإلكتروني" required>
    <textarea name="message" placeholder="رسالتك" required></textarea>
    <button type="submit">إرسال</button>
  </form>

  <div id="status"></div>

  <script>
    (function() {
      emailjs.init("jaMzle3s7TrSK5Fnj"); // استبدل بـ Public Key الخاص بك
    })();

    document.getElementById('contact-form').addEventListener('submit', function(e) {
      e.preventDefault();

      emailjs.sendForm('service_bvua4m7', 'template_xyth2fj', this)
        .then(function() {
          document.getElementById('status').innerText = "✅ تم إرسال الرسالة بنجاح!";
        }, function(error) {
          document.getElementById('status').innerText = "❌ حدث خطأ أثناء الإرسال.";
          console.error('Error:', error);
        });
    });
  </script>

</body>
</html>
