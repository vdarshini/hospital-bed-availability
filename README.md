# hospital-bed-availability
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hospital Bed Availability</title>
    <style>
        body { font-family: Arial, sans-serif; text-align: center; }
        .container { width: 300px; margin: auto; padding: 20px; border: 1px solid #ccc; border-radius: 5px; }
        input, button { width: 100%; margin: 5px 0; padding: 10px; }
    </style>
</head>
<body>
    <h2>Login</h2>
    <div class="container">
        <input type="text" id="username" placeholder="Username" required>
        <input type="password" id="password" placeholder="Password" required>
        <button onclick="login()">Login</button>
    </div>
    
    <h2>Hospital Data</h2>
    <div id="hospital-list" class="container"></div>

    <script>
        const hospitals = [
            { name: "City Hospital", totalBeds: 100, availableBeds: 20 },
            { name: "Green Valley Hospital", totalBeds: 50, availableBeds: 5 },
            { name: "Sunrise Care", totalBeds: 80, availableBeds: 30 }
        ];

        function displayHospitals() {
            const list = document.getElementById('hospital-list');
            list.innerHTML = '';
            hospitals.forEach(hospital => {
                list.innerHTML += `<p><strong>${hospital.name}</strong> - Available Beds: ${hospital.availableBeds}/${hospital.totalBeds}</p>`;
            });
        }
        
        function login() {
            const user = document.getElementById('username').value;
            const pass = document.getElementById('password').value;
            if (user === 'admin' && pass === 'password') {
                alert('Login successful!');
                displayHospitals();
            } else {
                alert('Invalid credentials!');
            }
        }
    </script>
</body>
</html>
