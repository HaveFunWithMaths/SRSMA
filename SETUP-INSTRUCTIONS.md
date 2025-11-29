# SRSMA Talk to Us Form - Setup Guide

## 📋 Overview
This custom form collects student inquiry data and automatically:
- Saves responses to Google Sheets
- Sends email notifications to nayakgopal1998@gmail.com
- Provides conditional dropdowns based on course selection

## 🚀 Setup Instructions

### Step 1: Set Up Google Apps Script

1. **Open Your Google Sheet**
   - Go to: https://docs.google.com/spreadsheets/d/1PRgrDDG1CEDbI63JlbVGkOYlqjzGxu0Z4-JQ0HCDlr4/edit

2. **Access Apps Script Editor**
   - Click on `Extensions` menu
   - Select `Apps Script`

3. **Add the Script**
   - Delete any existing code in the editor
   - Open the file `google-apps-script.js` from your website folder
   - Copy ALL the code from that file
   - Paste it into the Apps Script editor

4. **Save the Script**
   - Click the disk icon or press `Ctrl+S` (Windows) or `Cmd+S` (Mac)
   - Give it a name like "SRSMA Form Handler"

5. **Deploy as Web App**
   - Click on `Deploy` button (top right)
   - Select `New deployment`
   - Click the gear icon ⚙️ next to "Select type"
   - Choose `Web app`

6. **Configure Deployment Settings**
   - Description: "SRSMA Talk to Us Form Handler"
   - Execute as: **Me** (your email)
   - Who has access: **Anyone**
   - Click `Deploy`

7. **Authorize the App**
   - Click `Authorize access`
   - Choose your Google account
   - Click `Advanced` if you see a warning
   - Click `Go to [Project Name] (unsafe)` 
   - Click `Allow`

8. **Copy the Web App URL**
   - After authorization, you'll see a "Web app URL"
   - It looks like: `https://script.google.com/macros/s/AKfycb.../exec`
   - **COPY THIS URL** - you'll need it in the next step

### Step 2: Update the Form HTML

1. **Open the Form File**
   - Open `talk-to-us.html` in a text editor

2. **Find the Script URL Line**
   - Search for (around line 370):
   ```javascript
   const scriptURL = 'https://script.google.com/macros/s/AKfycbwYOUR_SCRIPT_ID_HERE/exec';
   ```

3. **Replace with Your URL**
   - Replace the entire URL with the one you copied in Step 1.8
   - Save the file

### Step 3: Test the Form

1. **Open the Form**
   - Open `talk-to-us.html` in your web browser
   - Or navigate to it from your website

2. **Fill Out Test Data**
   - Student Name: Test Student
   - Parent Phone: +91 9876543210
   - Select a course and fill other fields

3. **Submit the Form**
   - Click the Submit button
   - Wait for the success message

4. **Verify Data**
   - Check your Google Sheet - the data should appear
   - Check the email at nayakgopal1998@gmail.com - you should receive a notification

## 📝 Form Fields & Logic

### Conditional Fields:

**For JEE/NEET:**
- Class options: Class XI, Class XII, Long Term
- Mode options: Offline only

**For Foundation:**
- Class options: Class VIII, Class IX, Class X
- Mode options: Online, Offline

## 🎨 Form Features

- ✅ Beautiful gradient design matching your main website
- ✅ Real-time validation
- ✅ Conditional dropdowns
- ✅ Success/Error messages
- ✅ Automatic email notifications with HTML formatting
- ✅ Direct Google Sheets integration
- ✅ Mobile responsive design
- ✅ Back to home link

## 📧 Email Notification

Each form submission sends a formatted email to **nayakgopal1998@gmail.com** containing:
- All form data in a professional table format
- Timestamp of submission
- Direct link to view all inquiries in Google Sheet
- Action reminder to follow up

## 🔧 Troubleshooting

### Form shows error message:
1. Make sure you've replaced the scriptURL in talk-to-us.html
2. Verify the Google Apps Script is deployed as "Anyone" access
3. Check browser console (F12) for error messages

### No email received:
1. Check spam folder
2. Verify the email address in google-apps-script.js is correct
3. Test the email function directly in Apps Script editor

### Data not appearing in sheet:
1. Make sure the Sheet ID in the script matches your sheet
2. Verify the script has permission to access the sheet
3. Check the Apps Script execution logs for errors

## 🔗 Important URLs

- **Google Sheet**: https://docs.google.com/spreadsheets/d/1PRgrDDG1CEDbI63JlbVGkOYlqjzGxu0Z4-JQ0HCDlr4/edit
- **Email Recipient**: nayakgopal1998@gmail.com
- **Form Page**: talk-to-us.html

## 💡 Notes

- The form automatically records timestamp in IST (Indian Standard Time)
- All fields are required
- Phone number validation accepts international format (+91...)
- The sheet will automatically create headers on first submission
- You can customize email content by editing the Google Apps Script

---

Need help? Contact your web developer or refer to Google Apps Script documentation.
