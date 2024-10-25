# QR-Generator
Generate Multiple QR Codes, by providing ULS. Additionally get url+timestamp in the file name of png image

## What it does?
This project is a terminal-based QR code generator with URL logging features, making it easy to create unique QR codes for multiple URLs, **store them with identifiable filenames**, and maintain a **record of all URLs entered.** The app leverages modular packages for input (inquirer), QR generation (qr-image), and file handling (fs).

## What's special in this?
- The application prompts the user to enter a URL, using inquirer.
- The qr-image library generates the QR code as a .png file, making it easy to share and scan.
- The QR code image is saved to the local file system with a unique name, ensuring each QR code generated in each run is preserved.
- URLs entered by users are appended to a text file (urls_entered.txt) so that a record of all processed URLs is maintained.
- fs.appendFile ensures that each new URL entry is added to the end of the file, avoiding overwrites.

## Steps to Create a QR Code Generator
## 1. Setup Project Environment:
Create a new directory for your project & Navigate to the directory in your terminal.
## 2. Initialize Node.js Project:
Run npm init -y to create a package.json file.

## 3. Install Required Packages:
npm install inquirer qr-image fs

## 4. Create Main Script:
Create a new JavaScript file, e.g., index.js.

## 5. Import Required Modules:
Import inquirer for user prompts, qr-image for QR code generation, and fs for file system operations.

## 6. Prompt User for URL:
Use inquirer to prompt the user to enter a URL.
"message":"Enter Your URL, to generate QR: "
Here, "message" is what will be displayed to get input, and stored as "name" variable

## 7. Generate QR Code & save:
- Use the qr-image library to create a QR code from the provided URL.
- Create a unique filename (e.g., using a timestamp) and save the QR code as a PNG file.
- `qr_img_${URL}_${timestamp}.png` : here backticks (`) are used to incorporate template literal ${variable}
  
## 8. Log URLs to a File:
Append the entered URL to a text file (urls_entered.txt), using **appendFile** to keep a record of all URLs.
We could have used **writeFile** also, but it would have over written the file, and only the recent url would have been saved.

## 9. Handle Errors:
Implement basic error handling for file operations and prompts.

## 10. Finally: Run the Application!
Execute the script using **node index.js** and test the functionality.
