# calculadora-simples
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora Simples</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="calculator">
        <input type="text" id="display" disabled>
        <div class="buttons">
            <button>7</button>
            <button>8</button>
            <button>9</button>
            <button>/</button>
            <button>4</button>
            <button>5</button>
            <button>6</button>
            <button>*</button>
            <button>1</button>
            <button>2</button>
            <button>3</button>
            <button>-</button>
            <button>0</button>
            <button>C</button>
            <button>=</button>
            <button>+</button>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background-color: #f5f5f5;
}

.calculator {
    background: #fff;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
}

#display {
    width: 100%;
    height: 50px;
    margin-bottom: 10px;
    font-size: 1.5rem;
    text-align: right;
    padding: 5px;
    border: 1px solid #ccc;
    border-radius: 4px;
}

.buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
}

button {
    font-size: 1.2rem;
    padding: 10px;
    background: #007bff;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

button:hover {
    background: #0056b3;
}
const display = document.getElementById("display");
const buttons = document.querySelectorAll("button");

buttons.forEach(button => {
    button.addEventListener("click", () => {
        const value = button.textContent;

        if (value === "C") {
            display.value = "";
        } else if (value === "=") {
            try {
                display.value = eval(display.value); // Calcula a expressão
            } catch {
                display.value = "Erro";
            }
        } else {
            display.value += value;
        }
    });
});
