<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Today's Breaking News</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            background-color: #f4f4f4;
        }

        header {
            background-color: #d10000;
            color: white;
            padding: 15px;
            text-align: center;
            font-size: 24px;
            font-weight: bold;
        }

        .container {
            padding: 20px;
        }

        .news-card {
            background: white;
            padding: 15px;
            margin-bottom: 15px;
            border-left: 5px solid red;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }

        .news-card h2 {
            margin: 0 0 10px;
            color: #333;
        }

        .news-card p {
            color: #555;
        }

        .date {
            font-size: 14px;
            color: gray;
        }

        footer {
            text-align: center;
            padding: 15px;
            background-color: #222;
            color: white;
            margin-top: 20px;
        }

        .upload-section {
            background: #fff;
            padding: 15px;
            margin-bottom: 20px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }

        input, textarea {
            width: 100%;
            padding: 8px;
            margin: 8px 0;
        }

        button {
            background: red;
            color: white;
            border: none;
            padding: 10px 15px;
            cursor: pointer;
        }

        button:hover {
            background: darkred;
        }
    </style>
</head>

<body>

<header>
    🔴 Today's All Breaking News
</header>

<div class="container">

    <!-- Upload News Section -->
    <div class="upload-section">
        <h3>Upload Breaking News</h3>
        <input type="text" id="title" placeholder="Enter News Title">
        <textarea id="content" rows="4" placeholder="Enter News Description"></textarea>
        <button onclick="addNews()">Publish News</button>
    </div>

    <!-- News Display Area -->
    <div id="news-container"></div>

</div>

<footer>
    © 2026 Breaking News Portal | All Rights Reserved
</footer>

<script>
    function addNews() {
        var title = document.getElementById("title").value;
        var content = document.getElementById("content").value;

        if (title === "" || content === "") {
            alert("Please fill all fields!");
            return;
        }

        var newsContainer = document.getElementById("news-container");

        var newsCard = document.createElement("div");
        newsCard.className = "news-card";

        var today = new Date().toLocaleDateString();

        newsCard.innerHTML = `
            <h2>${title}</h2>
            <p class="date">${today}</p>
            <p>${content}</p>
        `;

        newsContainer.prepend(newsCard);

        document.getElementById("title").value = "";
        document.getElementById("content").value = "";
    }
</script>

</body>
</html>
