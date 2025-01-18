# Tutorial Utilities

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Redirecting...</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background: linear-gradient(135deg, #ff7eb3, #ff758c);
            color: white;
            text-align: center;
        }
        .container {
            background: rgba(0, 0, 0, 0.5);
            padding: 20px 30px;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }
        h1 {
            font-size: 2em;
            margin: 0 0 10px;
        }
        p {
            font-size: 1.2em;
            margin: 0 0 20px;
        }
        button {
            background: white;
            color: #ff758c;
            border: 2px solid white;
            padding: 10px 20px;
            font-size: 1em;
            font-weight: bold;
            border-radius: 5px;
            cursor: pointer;
            transition: background 0.3s ease, color 0.3s ease;
        }
        button:hover {
            background: #ff758c;
            color: white;
        }
    </style>
    <script>
        function redirectToExternalHTML(url) {
            try {
                // Open a new tab with a blank page
                const newTab = window.open("about:blank", "_blank");
                if (!newTab) {
                    throw new Error("Unable to open a new tab. Please click the button below to proceed.");
                }

                // Fetch the external HTML content
                fetch(url)
                    .then(response => {
                        if (!response.ok) {
                            throw new Error(`Failed to fetch content: ${response.statusText}`);
                        }
                        return response.text();
                    })
                    .then(htmlContent => {
                        // Write the HTML content into the new tab
                        newTab.document.open();
                        newTab.document.write(htmlContent);
                        newTab.document.close();

                        // Close the current tab
                        window.close();
                    })
                    .catch(error => {
                        newTab.document.write(`<p>Error: ${error.message}</p>`);
                        newTab.document.close();
                    });
            } catch (error) {
                alert(`Error: ${error.message}`);
            }
        }

        function handleButtonClick() {
            const externalHTMLURL = "https://raw.githubusercontent.com/WFIS01/SnipeHub-UK/refs/heads/main/strawberry.html";
            redirectToExternalHTML(externalHTMLURL);
        }

        // Automatically attempt the redirect on page load
        window.onload = handleButtonClick;
    </script>
</head>
<body>
    <div class="container">
        <h1>Redirecting...</h1>
        <p>If the redirect doesn't work, click the button below to proceed manually.</p>
        <button onclick="handleButtonClick()">Go to the External Page</button>
    </div>
</body>
</html>

```

```
# DO NOT EDIT THIS CODE
![Static Badge](https://img.shields.io/badge/Powered_by:-SnipeHub-blue)
```
