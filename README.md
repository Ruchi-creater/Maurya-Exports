<!DOCTYPE html>
<html>
<head>
    <title>Supplier Feedback Form</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css">
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            max-width: 800px;
            margin: 20px auto;
            padding: 20px;
            background-color: #f5f5f5;
        }
        .form-container {
            background-color: white;
            padding: 30px;
            border-radius: 12px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }
        .header {
            background-color: #4a4a4a;
            color: white;
            padding: 20px;
            border-radius: 12px 12px 0 0;
            margin: -30px -30px 30px -30px;
            text-align: center;
        }
        h2 {
            margin: 0;
            font-size: 28px;
            font-weight: 500;
        }
        .form-group {
            margin-bottom: 25px;
        }
        label {
            display: block;
            margin-bottom: 8px;
            color: #34495e;
            font-weight: 500;
            font-size: 16px;
        }
        input, textarea, select {
            width: 100%;
            padding: 12px;
            margin-bottom: 10px;
            border: 2px solid #e0e0e0;
            border-radius: 8px;
            font-size: 15px;
            transition: all 0.3s ease;
            background-color: #f8f9fa;
        }
        input:focus, textarea:focus, select:focus {
            outline: none;
            border-color: #4a4a4a;
            box-shadow: 0 0 0 3px rgba(74, 74, 74, 0.1);
            background-color: white;
        }
        select {
            appearance: none;
            background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='12' fill='%23333' viewBox='0 0 16 16'%3E%3Cpath d='M8 11L3 6h10l-5 5z'/%3E%3C/svg%3E");
            background-repeat: no-repeat;
            background-position: right 12px center;
            background-size: 12px;
            cursor: pointer;
        }
        textarea {
            min-height: 100px;
            resize: vertical;
        }
        button {
            position: relative;
            transition: all 0.3s ease;
            width: 100%;
            padding: 14px 20px;
            background-color: #4a4a4a;
            color: white;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-size: 16px;
            font-weight: 600;
            transition: all 0.3s ease;
        }
        button:disabled {
            background-color: #666;
            cursor: not-allowed;
            transform: none;
        }
        button:hover:not(:disabled) {
            background-color: #333333;
            transform: translateY(-1px);
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }
        .rating {
            display: inline-flex;
            flex-direction: row-reverse;
            gap: 8px;
        }
        .rating input {
            display: none;
        }
        .rating label {
            cursor: pointer;
            font-size: 30px;
            color: #ddd;
            transition: color 0.2s ease;
        }
        .rating input:checked ~ label,
        .rating label:hover,
        .rating label:hover ~ label {
            color: #ffd700;
        }
        .rating-container {
            background-color: #f8f9fa;
            padding: 20px;
            border-radius: 8px;
            margin-bottom: 20px;
            border: 2px solid #e0e0e0;
        }
        .rating-title {
            color: #2c3e50;
            margin-bottom: 15px;
            font-weight: bold;
        }
        select:invalid {
            color: #666;
        }
        option {
            color: #333;
        }
        .success-message {
            display: none;
            background-color: #4CAF50;
            color: white;
            padding: 15px;
            border-radius: 8px;
            margin-top: 20px;
            text-align: center;
        }
        .error-message {
            display: none;
            background-color: #f44336;
            color: white;
            padding: 15px;
            border-radius: 8px;
            margin-top: 20px;
            text-align: center;
        }
    </style>
</head>
<body>
    <div class="form-container">
        <div class="header">
            <h2>Supplier Feedback Form</h2>
        </div>
        <form id="feedbackForm">
            <div class="form-group">
                <label>Sourcing Merchandiser Name:</label>
                <select id="supplierName" required>
                    <option value="" disabled selected>Select Merchandiser</option>
                    <option value="Rekha">Rekha</option>
                    <option value="Lehak">Lehak</option>
                </select>
            </div>
            <div class="form-group">
                <label>Order No:</label>
                <input type="text" id="orderNo" required>
            </div>
            <div class="form-group">
                <label>Fabric Name:</label>
                <input type="text" id="fabricName" required>
            </div>
            
            <div class="rating-container">
                <div class="form-group">
                    <label class="rating-title">Quality Rating:</label>
                    <div class="rating">
                        <input type="radio" id="quality5" name="quality" value="5">
                        <label for="quality5" class="fas fa-star"></label>
                        <input type="radio" id="quality4" name="quality" value="4">
                        <label for="quality4" class="fas fa-star"></label>
                        <input type="radio" id="quality3" name="quality" value="3">
                        <label for="quality3" class="fas fa-star"></label>
                        <input type="radio" id="quality2" name="quality" value="2">
                        <label for="quality2" class="fas fa-star"></label>
                        <input type="radio" id="quality1" name="quality" value="1">
                        <label for="quality1" class="fas fa-star"></label>
                    </div>
                </div>

                <div class="form-group">
                    <label class="rating-title">Commitment Rating:</label>
                    <div class="rating">
                        <input type="radio" id="commitment5" name="commitment" value="5">
                        <label for="commitment5" class="fas fa-star"></label>
                        <input type="radio" id="commitment4" name="commitment" value="4">
                        <label for="commitment4" class="fas fa-star"></label>
                        <input type="radio" id="commitment3" name="commitment" value="3">
                        <label for="commitment3" class="fas fa-star"></label>
                        <input type="radio" id="commitment2" name="commitment" value="2">
                        <label for="commitment2" class="fas fa-star"></label>
                        <input type="radio" id="commitment1" name="commitment" value="1">
                        <label for="commitment1" class="fas fa-star"></label>
                    </div>
                </div>

                <div class="form-group">
                    <label class="rating-title">Overall Experience:</label>
                    <div class="rating">
                        <input type="radio" id="overall5" name="overallExperience" value="5">
                        <label for="overall5" class="fas fa-star"></label>
                        <input type="radio" id="overall4" name="overallExperience" value="4">
                        <label for="overall4" class="fas fa-star"></label>
                        <input type="radio" id="overall3" name="overallExperience" value="3">
                        <label for="overall3" class="fas fa-star"></label>
                        <input type="radio" id="overall2" name="overallExperience" value="2">
                        <label for="overall2" class="fas fa-star"></label>
                        <input type="radio" id="overall1" name="overallExperience" value="1">
                        <label for="overall1" class="fas fa-star"></label>
                    </div>
                </div>
            </div>

            <div class="form-group">
                <label>Quality Remarks:</label>
                <textarea id="qualityRemarks"></textarea>
            </div>
            <div class="form-group">
                <label>PPC Person Name:</label>
                <select id="ppcPersonName" required>
                    <option value="" disabled selected>Select PPC Person</option>
                    <option value="Suraj">Suraj</option>
                    <option value="Anuj">Anuj</option>
                    <option value="Navpreet">Navpreet</option>
                </select>
            </div>
            <button type="submit" id="submitButton">Submit Feedback</button>
        </form>
        <div id="successMessage" class="success-message">Form submitted successfully!</div>
        <div id="errorMessage" class="error-message">An error occurred. Please try again.</div>
    </div>

    <script>
        document.getElementById('feedbackForm').addEventListener('submit', async function(e) {
            const submitButton = document.getElementById('submitButton');
            submitButton.disabled = true;
            submitButton.innerHTML = 'Submitting...';
            e.preventDefault();
            
            const successMessage = document.getElementById('successMessage');
            const errorMessage = document.getElementById('errorMessage');
            
            const formData = {
                supplierName: document.getElementById('supplierName').value,
                orderNo: document.getElementById('orderNo').value,
                fabricName: document.getElementById('fabricName').value,
                quality: document.querySelector('input[name="quality"]:checked')?.value || "0",
                commitment: document.querySelector('input[name="commitment"]:checked')?.value || "0",
                overallExperience: document.querySelector('input[name="overallExperience"]:checked')?.value || "0",
                qualityRemarks: document.getElementById('qualityRemarks').value,
                ppcPersonName: document.getElementById('ppcPersonName').value
            };

            try {
                const response = await fetch('https://script.google.com/macros/s/AKfycbxgquKpd5QqfZBypw98V95uy7CSTStZDVLoosHFGwHNqCS2Rj949dt6TQFiRI7tVT6E/exec', {
                    method: 'POST',
                    mode: 'no-cors',
                    headers: {
                        'Content-Type': 'application/json'
                    },
                    body: JSON.stringify(formData)
                });

                successMessage.style.display = 'block';
                errorMessage.style.display = 'none';
                this.reset();
                
                setTimeout(() => {
                    successMessage.style.display = 'none';
                }, 3000);
                
            } finally {
                submitButton.disabled = false;
                submitButton.innerHTML = 'Submit Feedback';
            }
            } catch (error) {
                console.error('Error:', error);
                successMessage.style.display = 'none';
                errorMessage.style.display = 'block';
                
                setTimeout(() => {
                    errorMessage.style.display = 'none';
                }, 3000);
            }
        });
    </script>
</body>
</html>
