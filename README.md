# MATIN
<!DOCTYPE html>
<html lang="fa">
<head>
  <meta charset="UTF-8">
  <title>رزرو نوبت آرایشگاه</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>رزرو نوبت آرایشگاه</h1>
  <form id="appointmentForm">
    <input type="text" id="name" placeholder="Matin" required>
    <input type="date" id="date" required>
    <input type="time" id="time" required>
    <button type="submit">رزرو نوبت</button>
  </form>

  <h2>نوبت‌های رزرو شده</h2>
  <ul id="appointmentsList"></ul>

  <script src="script.js"></script>
</body>
</html>
body {
  font-family: sans-serif;
  direction: rtl;
  padding: 20px;
  background: #f9f9f9;
}

form {
  margin-bottom: 20px;
}

input, button {
  margin: 5px 0;
  padding: 10px;
  display: block;
  width: 100%;
}
const form = document.getElementById('appointmentForm');
const list = document.getElementById('appointmentsList');

form.addEventListener('submit', function(e) {
  e.preventDefault();
  const name = document.getElementById('name').value;
  const date = document.getElementById('date').value;
  const time = document.getElementById('time').value;

  const appointment = `${name} - ${date} - ${time}`;
  const li = document.createElement('li');
  li.textContent = appointment;
  list.appendChild(li);

  form.reset();
});
