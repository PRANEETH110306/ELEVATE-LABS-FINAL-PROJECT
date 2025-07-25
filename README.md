# TrailGuide – Travel SaaS Landing & Signup Flow

## Objective

Build a SaaS-style product landing page with a working sign-up workflow, email verification, and MongoDB lead capture system. The goal was to simulate a real-world travel platform signup flow using modern frontend design and backend services.

## Features

- Beautiful, conversion-optimized landing page with Tailwind CSS
- Responsive design with scrollable sections: Home, About, Contact
- Secure sign-up form with basic validation
- Email verification using Nodemailer (with Gmail 2FA)
- MongoDB integration for lead storage
- Thank-you and verification pages with modern UI
- Fully static frontend with backend in Node.js and Express.js

## Working

1. **Landing Page**: User lands on a scrollable landing page (`index.html`) and clicks **Get Started**.
2. **Signup**: Redirected to a signup form that collects `username`, `email`, and `password`.
3. **Database Storage**: On submission, the data is stored in MongoDB with a unique verification token.
4. **Email Verification**:
   - Nodemailer sends an email using Gmail SMTP.
   - Gmail must have **2-Step Verification enabled**.
   - A special **App Password** (generated from Google Account Security settings) is used in the `.env` file like this:
     ```
     EMAIL_USER=your-email@gmail.com
     EMAIL_PASS=your-app-password
     ```
5. **Verification Page**: User sees a message to check their inbox and verify.
6. **Thank You & Dashboard**: On clicking the email link, the account is marked as verified, and the user is redirected to the dashboard.

## Challenges Faced

- Initially tried integrating MongoDB Cloud, but setup was complex and error-prone — later switched to local MongoDB which worked smoothly.
- Configuring Nodemailer with Gmail was tricky until discovering the **App Password** method required due to 2FA.
- Styling and layout in TailwindCSS was new and slightly hard to debug due to its utility-first nature — preferred traditional CSS for readability.
- Attempted login flow implementation but skipped due to time and integration complexity.

