<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Search Interface</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #ADD8E6; /* Light blue background */

        }

        .search-container {
            display: flex;
            align-items: center;
            position: relative;
        }

        .dropdown {
            position: relative;
            margin-right: 10px;
        }

        .dropdown-button {
            background-color: #f9f9f9;
            border: 1px solid #ccc;
            padding: 10px;
            border-radius: 8px;
            cursor: pointer;
        }

        .dropdown-options {
            display: none;
            position: absolute;
            top: 100%;
            left: 0;
            right: 0;
            background-color: #ffffff;
            border: 1px solid #ccc;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            z-index: 10;
        }

        .dropdown-options.active {
            display: block;
        }

        .dropdown-options div {
            padding: 10px;
            cursor: pointer;
        }

        .dropdown-options div:hover {
            background-color: #f0f0f0;
        }

        .search-input {
            flex: 1;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 8px;
            margin-right: 10px;
            outline: none;
        }

        .search-button {
            background-color: #007bff;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 8px;
            cursor: pointer;
        }

        .search-button:hover {
            background-color: #0056b3;
        }
    </style>
</head>
<body>
    <div class="search-container">
        <div class="dropdown">
            <button class="dropdown-button" id="dropdownButton">Everything</button>
            <div class="dropdown-options" id="dropdownOptions">
                <div>Everything</div>
                <div>Software Development</div>
                <div>Web Development</div>
                <div>Data Analyst</div>
                <div>IT Consultant</div>
                <div>Network Administrator</div>
            </div>
        </div>
        <input type="text" class="search-input" placeholder="Search here...">
        <button class="search-button">Search</button>
    </div>

    <script>
        const dropdownButton = document.getElementById('dropdownButton');
        const dropdownOptions = document.getElementById('dropdownOptions');

        dropdownButton.addEventListener('click', () => {
            dropdownOptions.classList.toggle('active');
        });

        dropdownOptions.addEventListener('click', (e) => {
            if (e.target.tagName === 'DIV') {
                dropdownButton.textContent = e.target.textContent;
                dropdownOptions.classList.remove('active');
            }
        });

        window.addEventListener('click', (e) => {
            if (!dropdownOptions.contains(e.target) && e.target !== dropdownButton) {
                dropdownOptions.classList.remove('active');
            }
        });
    </script>
</body>
</html>
