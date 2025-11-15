# Inventory-management-system
<!DOCTYPE html>
<html lang="en">
<head>
    <style>* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Arial', sans-serif;
}

body {
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 100vh;
    background: #f4f4f9;
    padding: 20px;
}

.container {
    width: 100%;
    max-width: 600px;
    background: #ffe1e1;
    padding: 20px;
    border-radius: 12px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
    text-align: center;
    margin-bottom: 20px;
}

input {
    width: calc(100% - 20px);
    padding: 10px;
    margin: 10px 0;
    border: 1px solid #ccc;
    border-radius: 8px;
    display: block;
}

button {
    width: 100%;
    padding: 12px;
    border: none;
    border-radius: 8px;
    background: #0d36cb;
    color: rgb(255, 255, 255);
    font-size: 16px;
    cursor: pointer;
    transition: background 0.3s;
}

button:hover {
    background: #0f285e;
}

table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 20px;
}

table, th, td {
    border: 1px solid #ffffff;
}

th, td {
    padding: 10px;
    text-align: center;
}

th {
    background: #640886;
    color: rgb(255, 255, 255);
}</style>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Product Inventory Management</title>
    <link rel="stylesheet" href="styles.css">
    <script>function addProduct() {
    let name = document.getElementById("productName").value;
    let stock = document.getElementById("productStock").value;
    if (name.trim() !== "" && stock.trim() !== "") {
        let table = document.getElementById("productTable");
        let row = table.insertRow();
        row.innerHTML = `<td>${name}</td><td>${stock}</td><td><button onclick="removeProduct(this)">Remove</button></td>`;
        document.getElementById("productName").value = "";
        document.getElementById("productStock").value = "";
    }
}

function removeProduct(button) {
    let row = button.parentNode.parentNode;
    row.parentNode.removeChild(row);
}</script>
</head>
<body>
    <div class="container">
        <h2>Product Inventory Management</h2>
        <input type="text" id="productName" placeholder="Enter Product Name">
        <input type="number" id="productStock" placeholder="Enter Stock Quantity">
        <button onclick="addProduct()">Add Product</button>
        <table>
            <thead>
                <tr>
                    <th>Product Name</th>
                    <th>Stock</th>
                    <th>Action</th>
                </tr>
            </thead>
            <tbody id="productTable">
            </tbody>
        </table>
    </div>
    <script src="script.js"></script>
</body>
</html>
