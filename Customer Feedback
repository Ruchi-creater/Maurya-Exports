<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Customer Feedback Form</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 600px;
            margin: 20px auto;
            padding: 0;
            background-color: #f5f5f5;
        }

        .form-container {
            background-color: white;
            border-radius: 5px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        .header {
            background-color: #1a73e8;
            padding: 15px;
            text-align: center;
            border-radius: 5px 5px 0 0;
        }

        .company-logo {
            max-width: 180px;
            height: auto;
            margin-bottom: 10px;
            padding: 5px;
            background: white;
            border-radius: 4px;
        }

        h2 {
            color: white;
            margin: 5px 0;
            font-size: 1.5em;
        }

        form {
            padding: 20px;
        }

        .form-group {
            margin-bottom: 15px;
        }

        label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
            color: #333;
        }

        input[type="text"],
        input[type="date"],
        textarea {
            width: 100%;
            padding: 8px;
            border: 1px solid #ddd;
            border-radius: 4px;
            box-sizing: border-box;
        }

        textarea {
            height: 100px;
            resize: vertical;
        }

        .rating {
            display: flex;
            gap: 5px;
            margin: 10px 0;
        }

        .star {
            color: #ddd;
            font-size: 24px;
            cursor: pointer;
        }

        .star:hover,
        .star.active {
            color: #ffd700;
        }

        .submit-btn {
            background-color: #1a73e8;
            color: white;
            padding: 12px;
            border: none;
            border-radius: 5px;
            width: 100%;
            cursor: pointer;
            font-size: 16px;
            font-weight: bold;
            margin-top: 10px;
        }

        .submit-btn:hover {
            background-color: #1557b0;
        }

        .rating-section {
            margin-bottom: 20px;
        }

        .rating-row {
            display: flex;
            justify-content: space-between;
            margin-bottom: 15px;
            flex-wrap: wrap;
        }

        .rating-column {
            flex: 1;
            min-width: 150px;
            margin: 0 10px 10px 0;
        }

        @media (max-width: 480px) {
            .rating-column {
                flex: 100%;
            }
        }
    </style>
</head>
<body>
    <div class="form-container">
        <div class="header">
            <img src="/api/placeholder/180/60" alt="Maurya Exports" class="company-logo">
            <h2>Customer Feedback Form</h2>
        </div>
        
        <form id="feedbackForm">
            <div class="form-group">
                <label for="reference">Reference Number:</label>
                <input type="text" id="reference" name="reference" required>
            </div>

            <div class="form-group">
                <label for="serviceDate">Service Date:</label>
                <input type="date" id="serviceDate" name="serviceDate" required>
            </div>

            <div class="rating-row">
                <div class="rating-column">
                    <label>Overall Rating:</label>
                    <div class="rating" id="overallRating">
                        <span class="star">★</span>
                        <span class="star">★</span>
                        <span class="star">★</span>
                        <span class="star">★</span>
                        <span class="star">★</span>
                    </div>
                </div>

                <div class="rating-column">
                    <label>Delivery Rating:</label>
                    <div class="rating" id="deliveryRating">
                        <span class="star">★</span>
                        <span class="star">★</span>
                        <span class="star">★</span>
                        <span class="star">★</span>
                        <span class="star">★</span>
                    </div>
                </div>

                <div class="rating-column">
                    <label>Communication Rating:</label>
                    <div class="rating" id="communicationRating">
                        <span class="star">★</span>
                        <span class="star">★</span>
                        <span class="star">★</span>
                        <span class="star">★</span>
                        <span class="star">★</span>
                    </div>
                </div>
            </div>

            <div class="form-group">
                <label>Value Rating:</label>
                <div class="rating" id="valueRating">
                    <span class="star">★</span>
                    <span class="star">★</span>
                    <span class="star">★</span>
                    <span class="star">★</span>
                    <span class="star">★</span>
                </div>
            </div>

            <div class="form-group">
                <label for="improvement">Areas for Improvement:</label>
                <textarea id="improvement" name="improvement" placeholder="Please share any suggestions for improvement..."></textarea>
            </div>

            <div class="form-group">
                <label for="positive">Positive Aspects:</label>
                <textarea id="positive" name="positive" placeholder="Please share what went well..."></textarea>
            </div>

            <div class="form-group">
                <label>Effort Score:</label>
                <div class="rating" id="effortScore">
                    <span class="star">★</span>
                    <span class="star">★</span>
                    <span class="star">★</span>
                    <span class="star">★</span>
                    <span class="star">★</span>
                </div>
            </div>

            <button type="submit" class="submit-btn">Submit Feedback</button>
        </form>
    </div>

    <script>
        // Rating functionality
        document.querySelectorAll('.rating').forEach(rating => {
            rating.addEventListener('click', (e) => {
                if (e.target.classList.contains('star')) {
                    const stars = e.target.parentElement.children;
                    const clickedIndex = Array.from(stars).indexOf(e.target);
                    
                    Array.from(stars).forEach((star, index) => {
                        if (index <= clickedIndex) {
                            star.classList.add('active');
                        } else {
                            star.classList.remove('active');
                        }
                    });
                }
            });
        });

        // Function to get rating value
        function getRatingValue(ratingId) {
            const activeStars = document.querySelector(`#${ratingId}`).querySelectorAll('.star.active');
            return activeStars.length;
        }

        // Form submission handling
        const form = document.getElementById('feedbackForm');
        const scriptURL = 'https://script.google.com/macros/s/AKfycbyYQ3Es2P8dEIbT9q6iRlfQmxIF40EeFPDqVlmRBSOP2vHYoRIt7swuP48wb8e5bFYW/exec'; // Replace with your Google Script URL

        form.addEventListener('submit', e => {
            e.preventDefault();
            
            // Create FormData object
            const formData = new FormData();
            
            // Add basic form fields
            formData.append('reference', document.getElementById('reference').value);
            formData.append('serviceDate', document.getElementById('serviceDate').value);
            formData.append('improvements', document.getElementById('improvement').value);
            formData.append('positives', document.getElementById('positive').value);
            
            // Add ratings
            formData.append('overallRating', getRatingValue('overallRating'));
            formData.append('deliveryRating', getRatingValue('deliveryRating'));
            formData.append('communicationRating', getRatingValue('communicationRating'));
            formData.append('valueRating', getRatingValue('valueRating'));
            formData.append('effortScore', getRatingValue('effortScore'));
            
            // Add timestamp
            formData.append('timestamp', new Date().toISOString());
            
            // Disable submit button
            const submitBtn = form.querySelector('.submit-btn');
            submitBtn.disabled = true;
            submitBtn.textContent = 'Submitting...';
            
            // Submit to Google Sheets
            fetch(scriptURL, { method: 'POST', body: formData })
                .then(response => response.text())
                .then(() => {
                    alert('Thank you for your feedback!');
                    form.reset();
                    // Reset all star ratings
                    document.querySelectorAll('.star').forEach(star => {
                        star.classList.remove('active');
                    });
                    submitBtn.disabled = false;
                    submitBtn.textContent = 'Submit Feedback';
                })
                .catch(error => {
                    console.error('Error!', error.message);
                    alert('Error submitting feedback. Please try again.');
                    submitBtn.disabled = false;
                    submitBtn.textContent = 'Submit Feedback';
                });
        });
    </script>
</body>
</html>
