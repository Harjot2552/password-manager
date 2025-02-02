# 🔐 PassX - Your Personal Password Manager

A lightweight and secure **Password Manager** built with **HTML**, **CSS**, and **JavaScript**. PassX helps you store and manage your passwords conveniently and securely in your browser using **localStorage**.

## 🛠️ Features
- Add and manage passwords for multiple websites.
- Copy website names, usernames, and passwords with a click.
- Masked password display for better security.
- Delete specific passwords.
- Data persistence using `localStorage`.

## 🕒 Preview
![PassX Preview](https://harjotrocks.com/javascript/password-manager/)

## 🔗 How to Use
1. Open the `index.html` file in any modern web browser.
2. Use the input fields to add your website, username, and password.
3. Click **Submit** to save the password.
4. Copy credentials by clicking the copy icons.
5. Delete saved passwords using the **Delete** button.

## 📚 Code Breakdown
### Password Masking
Passwords are masked using this simple function:
```javascript
function maskPassword(pass) {
  let str = "";
  for (let index = 0; index < pass.length; index++) {
    str += "*";
  }
  return str;
}
```

### Copying to Clipboard
Copy any text by clicking a copy icon:
```javascript
function copyText(txt) {
  navigator.clipboard.writeText(txt).then(() => {
    document.getElementById("alert").style.display = "inline";
    setTimeout(() => {
      document.getElementById("alert").style.display = "none";
    }, 2000);
  }, () => {
    alert("Clipboard copying failed");
  });
}
```

### Deleting Passwords
Passwords can be removed from localStorage using:
```javascript
const deletePassword = (website) => {
  let data = localStorage.getItem("passwords");
  let arr = JSON.parse(data);
  let arrUpdated = arr.filter((e) => e.website != website);
  localStorage.setItem("passwords", JSON.stringify(arrUpdated));
  alert(`Successfully deleted ${website}'s password`);
  showPasswords();
};
```

## 🌐 Technologies Used
- HTML5
- CSS3
- JavaScript ES6

## 🛠️ Setup Instructions
1. Clone the repository:
   ```bash
   git clone https://github.com/Harjot2552/passx-password-manager.git
   ```
2. Navigate to the project directory and open `index.html`.

## ❤️ Contribution
Feel free to submit issues or pull requests to improve this project.


