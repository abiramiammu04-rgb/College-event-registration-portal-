
<!DOCTYPE html>
<html>
<head>
    <title>College Event Registration</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <h1>College Event Registration Portal</h1>
    <p>Register for your favourite college event</p>

    <form id="eventForm">
        <input type="text" id="name"
               placeholder="Student Name" required>

        <input type="text" id="regno"
               placeholder="Register Number" required>

        <input type="text" id="department"
               placeholder="Department" required>

        <input type="email" id="email"
               placeholder="Email Address" required>

        <select id="event" required>
            <option value="">Select an Event</option>
            <option value="Cultural Fest">Cultural Fest</option>
            <option value="Workshop">Workshop</option>
            <option value="Sports Day">Sports Day</option>
            <option value="Seminar">Seminar</option>
        </select>

        <button type="submit">Register Now</button>
    </form>

    <p id="message"></p>

    <script src="script.js"></script>
</body>
</html>

body {
    font-family: Arial, sans-serif;
    background-color: #eaf4ff;
    text-align: center;
    padding: 20px;
}

h1 {
    color: #174a8b;
}

form {
    background-color: white;
    max-width: 350px;
    margin: 20px auto;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 2px 8px #cccccc;
}

input, select, button {
    width: 100%;
    padding: 10px;
    margin: 8px 0;
    box-sizing: border-box;
}

button {
    background-color: #1769aa;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background-color: #104b7b;
}

#message {
    color: green;
    font-weight: bold;
}

document.getElementById("eventForm")
.addEventListener("submit", function(event) {
    event.preventDefault();

    const name = document.getElementById("name").value.trim();
    const regno = document.getElementById("regno").value.trim();
    const department = document.getElementById("department").value.trim();
    const email = document.getElementById("email").value.trim();
    const selectedEvent = document.getElementById("event").value;

    if (!name || !regno || !department || !email || !selectedEvent) {
        document.getElementById("message").textContent =
            "Please fill in all fields.";
        return;
    }

    document.getElementById("message").textContent =
        "Registration successful! " + name +
        ", you registered for " + selectedEvent + ".";

    document.getElementById("eventForm").reset();
});

