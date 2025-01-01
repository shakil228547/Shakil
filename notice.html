<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Notice Board - Chindhukuria Digital Coaching</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: #f7f7f7;
            color: #333;
        }
        header {
            background-color: #4CAF50;
            color: white;
            padding: 15px;
            text-align: center;
        }
        .notice-board {
            margin: 20px;
        }
        .notice {
            background: #ffffff;
            padding: 20px;
            border-radius: 5px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            margin-bottom: 10px;
        }
        .notice h3 {
            margin-top: 0;
        }
        .post-notice-btn, .delete-btn {
            background-color: #4CAF50;
            color: white;
            padding: 10px 20px;
            border: none;
            cursor: pointer;
            border-radius: 5px;
            margin: 10px 0;
        }
        .post-notice-btn:hover, .delete-btn:hover {
            background-color: #45a049;
        }
        .delete-btn {
            background-color: red;
        }
        .delete-btn:hover {
            background-color: darkred;
        }
        .notice input, .notice textarea {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border-radius: 5px;
            border: 1px solid #ccc;
        }
    </style>
</head>
<body>

<header>
    <h1>Welcome to Chindhukuria Digital Coaching Notice Board</h1>
</header>

<div class="notice-board">
    <!-- Display Notices -->
    <div id="notices-list">
        <!-- Notices will appear here -->
    </div>

    <!-- Post Notice Button -->
    <button class="post-notice-btn" onclick="togglePostForm()">Post a Notice</button>

    <!-- Post Notice Form (Hidden by default) -->
    <div id="notice-form" style="display:none;">
        <div class="notice">
            <h3>Post a New Notice</h3>
            <input type="password" id="admin-password" placeholder="Enter Admin Password" />
            <input type="text" id="notice-title" placeholder="Notice Title" />
            <textarea id="notice-content" placeholder="Enter the notice details..."></textarea>
            <button class="post-notice-btn" onclick="postNotice()">Post Notice</button>
        </div>
    </div>
</div>

<script>
    var correctPassword = "shakil00"; // Admin password

    // Toggle visibility of the notice form
    function togglePostForm() {
        var form = document.getElementById('notice-form');
        form.style.display = form.style.display === 'none' ? 'block' : 'none';
    }

    // Function to post a new notice
    function postNotice() {
        var password = document.getElementById('admin-password').value;
        var title = document.getElementById('notice-title').value;
        var content = document.getElementById('notice-content').value;

        if (password !== correctPassword) {
            alert('Incorrect Password! You do not have access to post notices.');
            return;
        }

        if (title && content) {
            var noticeList = document.getElementById('notices-list');
            var newNotice = document.createElement('div');
            newNotice.classList.add('notice');
            newNotice.innerHTML = `<h3>${title}</h3><p>${content}</p>`;

            // Add delete button for admin
            var deleteBtn = document.createElement('button');
            deleteBtn.classList.add('delete-btn');
            deleteBtn.innerHTML = "Delete Notice";
            deleteBtn.onclick = function() {
                if (prompt("Enter Admin Password to Delete:") === correctPassword) {
                    noticeList.removeChild(newNotice);
                    alert("Notice deleted successfully!");
                } else {
                    alert("Incorrect password! You cannot delete this notice.");
                }
            };
            newNotice.appendChild(deleteBtn);

            noticeList.appendChild(newNotice);

            // Clear form fields after posting
            document.getElementById('notice-title').value = '';
            document.getElementById('notice-content').value = '';
            document.getElementById('admin-password').value = '';

            alert('Notice posted successfully!');
            togglePostForm(); // Hide the form after posting
        } else {
            alert('Please fill in both title and content.');
        }
    }
</script>

</body>
</html>
