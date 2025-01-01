<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>নোটিশ</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            padding: 20px;
        }
        .notice-board {
            background-color: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }
        h2 {
            text-align: center;
        }
        .notice-list {
            margin-top: 20px;
        }
        .notice {
            background-color: #e8f5e9;
            padding: 10px;
            border-radius: 4px;
            margin-bottom: 10px;
            border-left: 5px solid #4caf50;
            position: relative;
        }
        .form-container {
            margin-top: 20px;
        }
        input, textarea {
            width: 100%;
            padding: 10px;
            margin: 5px 0;
            border: 1px solid #ddd;
            border-radius: 4px;
        }
        button {
            background-color: #4caf50;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 4px;
            cursor: pointer;
        }
        .login-container {
            margin-top: 20px;
        }
        .message {
            color: red;
        }
        .delete-btn {
            position: absolute;
            top: 10px;
            right: 10px;
            background-color: red;
            color: white;
            border: none;
            padding: 5px 10px;
            cursor: pointer;
            border-radius: 4px;
        }
    </style>
</head>
<body>

<div class="notice-board">
    <h2>নোটিশ বোর্ড</h2>
    
    <div class="notice-list" id="noticeList">
        <!-- নোটিশগুলো এখানে দেখানো হবে -->
    </div>

    <!-- লগইন সেকশন -->
    <div id="loginSection" class="login-container">
        <h3>অ্যাডমিন লগইন করুন</h3>
        <input type="password" id="adminPassword" placeholder="পাসওয়ার্ড লিখুন" required>
        <button onclick="login()">লগইন</button>
        <p class="message" id="errorMessage"></p>
    </div>

    <!-- নোটিশ পোস্ট করার ফর্ম -->
    <div id="noticeForm" class="form-container" style="display:none;">
        <h3>নতুন নোটিশ পোস্ট করুন</h3>
        <input type="text" id="noticeTitle" placeholder="নোটিশের শিরোনাম" required>
        <textarea id="noticeContent" rows="4" placeholder="নোটিশের বিস্তারিত" required></textarea>
        <button onclick="postNotice()">পোস্ট করুন</button>
    </div>
</div>

<script>
    // পাসওয়ার্ড যাচাই করার জন্য
    const adminPassword = "Shakil00"; // পাসওয়ার্ড এখানে সেট করা হলো

    // নোটিশগুলি সেভ করার জন্য স্থানীয় স্টোরেজ ব্যবহার করা হচ্ছে
    function loadNotices() {
        let notices = JSON.parse(localStorage.getItem("notices")) || [];
        let noticeList = document.getElementById("noticeList");
        noticeList.innerHTML = ""; // আগের নোটিশগুলো ক্লিয়ার করা
        notices.forEach(function(notice, index) {
            let noticeElement = document.createElement("div");
            noticeElement.classList.add("notice");
            noticeElement.innerHTML = `<strong>${notice.title}</strong><p>${notice.content}</p><button class="delete-btn" onclick="deleteNotice(${index})">মুছুন</button>`;
            noticeList.appendChild(noticeElement);
        });
    }

    // লগইন ফাংশন
    function login() {
        let password = document.getElementById("adminPassword").value;
        if(password === adminPassword) {
            document.getElementById("loginSection").style.display = "none";
            document.getElementById("noticeForm").style.display = "block";
            loadNotices(); // লগইন করার পর নোটিশ লোড করা
        } else {
            document.getElementById("errorMessage").textContent = "ভুল পাসওয়ার্ড!";
        }
    }

    // নতুন নোটিশ পোস্ট করার ফাংশন
    function postNotice() {
        let title = document.getElementById("noticeTitle").value;
        let content = document.getElementById("noticeContent").value;

        if(title && content) {
            let notices = JSON.parse(localStorage.getItem("notices")) || [];
            notices.push({title: title, content: content});
            localStorage.setItem("notices", JSON.stringify(notices));

            document.getElementById("noticeTitle").value = "";
            document.getElementById("noticeContent").value = "";
            loadNotices(); // নতুন নোটিশ দেখানো
        } else {
            alert("দয়া করে সব তথ্য পূর্ণ করুন!");
        }
    }

    // পাসওয়ার্ড যাচাই করে নোটিশ মুছার ফাংশন
    function deleteNotice(index) {
        let password = prompt("নোটিশ মুছতে পাসওয়ার্ড দিন:");

        if(password === adminPassword) {
            let notices = JSON.parse(localStorage.getItem("notices")) || [];
            notices.splice(index, 1); // মুছে দেওয়া হচ্ছে নির্বাচিত নোটিশটি
            localStorage.setItem("notices", JSON.stringify(notices));
            loadNotices(); // নতুন তালিকা লোড করা
        } else {
            alert("ভুল পাসওয়ার্ড!");
        }
    }

    // প্রথমে নোটিশ লোড করানো
    loadNotices();
</script>

</body>
</html>
