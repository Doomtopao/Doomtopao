<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Botões Divertidos</title>
    <style>
        .moving-button {
            position: absolute;
            padding: 10px 20px;
            cursor: pointer;
        }
        .hidden {
            display: none;
        }
    </style>
    <script>
        let moveCount = 0;
        function moveButton(button) {
            if (moveCount < 9) {
                button.style.top = Math.random() * (window.innerHeight - button.offsetHeight) + 'px';
                button.style.left = Math.random() * (window.innerWidth - button.offsetWidth) + 'px';
                moveCount++;
            } else if (moveCount === 9) {
                button.innerText = "cansei dessa poha kkkkkk";
                moveCount++;
            }
        }

        function hideButton(button) {
            if (moveCount === 10) {
                button.classList.add('hidden');
                document.getElementById('bitcoin-button').classList.remove('hidden');
            }
        }

        function redirectToLink() {
            window.location.href = "https://www.youtube.com/watch?v=UQ68kNYEXcg";
        }
    </script>
</head>
<body>
    <button class="moving-button" onmouseover="moveButton(this); hideButton(this)">Passe o mouse aqui</button>
    <button id="bitcoin-button" class="hidden" onclick="redirectToLink()">Clique aqui para conseguir 50 bitcoins</button>
</body>
</html>
