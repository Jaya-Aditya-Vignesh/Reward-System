# Reward-System
## Overview
This project is a reward-based engagement system built with Flask and MySQL. It allows users to earn Kyn Coins for activities like daily logins and redeem accumulated KYN coins for coupons. The system tracks coupon availability, redemption status, and expiration. The frontend is built with Bootstrap for a modern, responsive interface, while Flask manages backend logic, and MySQL handles data storage.

## Define measurable engagement metrics and Point - Based Rewards
Measurable engagement metrics track user activities on the platform, which are used to determine the rewards they earn. Below are some engagement activities and their respective metrics:

Referrals: First Referral = 1000 Kyn coins nd subsequent 500 Kyn coins
Event Bookings:each Booking = 300 Kyn coins.
Daily Activity: Daily tasks that users must complete (e.g., posting, commenting, etc.). 5 Kyn coins for each
__New Users:__
Content Creation: 20 Kyn coins
Interactions (Likes, Comments, Shares): 15 kyn coins for each
Logins: 10 Kyn coins
Live Stream Participation: 20 kyn coins

## Redemption Process ##
1.Kyn Coins can be redeemed for any Other promotional Brand coupons.
2. for higher value of kyn coins, it can be redeemed with cashback to wallet, discount of event booking , converted to wallet money.
Sample:
Get 10% off on your next Booking.
Earn 20% cashback to your wallet.
500 kyn coins= 10 wallet amount.





## Features
Daily Rewards: Users earn coins for logging in daily.
Coupon Redemption: Redeem Kyn coins for available coupons, with validation for expiry and status.
Responsive UI: A clean and intuitive interface designed with HTML and Bootstrap.
Database Integration: MySQL stores user data, reward points, and coupon details.

## Execution Process
1. Install Prerequisites:
Python (3.8 or above)
MySQL database

2.Set Up a Virtual Environment:

Create and activate a virtual environment:
python -m venv venv
venv\Scripts\activate

3. Required Python libraries:
pip install flask flask_sqlalchemy flask_migrate flask_wtf flask_bootstrap

4.Configure Environment Variables:

*Set environment variables for the Flask app and secret key:*

set FLASK_APP=app.py
set FLASK_SECRET_KEY='kn'

4.Set Up the Database:

*Open MySQL and create a database:*

CREATE DATABASE reward_system;
__Update the config.py file with your MySQL credentials.__


5. Run Database Migrations:
**Initialize and migrate the database:*
flask db init
flask db migrate
flask db upgrade

6. Add Initial Data:

Use MySQL or Flask admin to add sample coupons for testing.
Sample:
INSERT INTO coupon (code, description, points_required, expiry_date)
VALUES
('SAVE10', 'Get 10% off on your next Booking.', 100, DATE_ADD(NOW(), INTERVAL 30 DAY)),
('15off', '15 off o Event Booking for more than 2 people.', 150, DATE_ADD(NOW(), INTERVAL 60 DAY)),
('CASHBACK20', 'Earn 20% cashback to your wallet.', 200, DATE_ADD(NOW(), INTERVAL 90 DAY));

7.Run the Application:

**Start the Flask application:*

flask run
Access the app at http://127.0.0.1:5000/.

Using the Application:

Earn daily login points automatically by visiting the application.
View available coupons and redeem them on the "Rewards" page.

## Additional Tasks ##
1. Add a Kyn wallet to store nd use Cashback amount
2. Use Brand Coupons for redemption of Kyn Coins
