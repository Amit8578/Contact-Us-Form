<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.16.0/umd/popper.min.js"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>
    <title>Responsive Form</title>
</head>
<body>
    <div class="container mt-5">
        <h1>Contact us Form</h1>
        <p>Fill out the form below:</p>
        <form id="myForm">
            <div class="form-group">
                <label for="fullName">Full Name:</label>
                <input type="text" class="form-control" id="fullName" name="fullName" required>
            </div>
            <div class="form-group">
                <label for="contactNo">Contact No.:</label>
                <input type="tel" class="form-control" id="contactNo" name="contactNo" required>
            </div>
            <div class="form-group">
                <label for="email">Email:</label>
                <input type="email" class="form-control" id="email" name="email" required>
            </div>
            <div class="form-group">
                <label for="address">Address:</label>
                <textarea class="form-control" id="address" name="address" required></textarea>
            </div>
            <button type="submit" class="btn btn-primary">Submit</button>
        </form>
    </div>
</body>
</html>
<script>
    document.getElementById("myForm").addEventListener("submit", function (event) {
        event.preventDefault();
        
        // Validation for Full Name (minimum length 3 characters)
        const fullName = document.getElementById("fullName").value;
        if (fullName.length < 3) {
            alert("Full Name must be at least 3 characters long.");
            return;
        }

        // Validation for Contact No. (must be a valid phone number format)
        const contactNo = document.getElementById("contactNo").value;
        const contactNoPattern = /^\d{10}$/;
        if (!contactNo.match(contactNoPattern)) {
            alert("Contact No. must be a 10-digit number.");
            return;
        }

        // Validation for Email (must be a valid email address)
        const email = document.getElementById("email").value;
        const emailPattern = /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
        if (!email.match(emailPattern)) {
            alert("Please enter a valid email address.");
            return;
        }

        // Validation for Address (minimum length 5 characters)
        const address = document.getElementById("address").value;
        if (address.length < 5) {
            alert("Address must be at least 5 characters long.");
            return;
        }

        // If all validations pass, you can submit the form or perform other actions here
        alert("Form submitted successfully!");
    });
</script>
