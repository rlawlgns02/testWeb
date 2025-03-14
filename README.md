<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>테스트 페이지</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }
        header {
            background-color: #333;
            color: #fff;
            padding: 1rem 0;
            text-align: center;
        }
        main {
            padding: 2rem;
            max-width: 800px;
            margin: 0 auto;
            background-color: #fff;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        footer {
            background-color: #333;
            color: #fff;
            text-align: center;
            padding: 1rem 0;
            position: fixed;
            width: 100%;
            bottom: 0;
        }
    </style>
</head>
<body>
    <header>
        <h1>안녕하세요</h1>
    </header>
    <main>
        <h2>소개</h2>
        <p>저는 IT인공지능 학부생 김지훈 입니다. </p>
        
        <h2>미니게임</h2>
        <div id="game" style="display: grid; grid-template-columns: repeat(5, 1fr); gap: 10px;">
        </div>
        <p>점수: <span id="score">0</span></p>
        <script>
            const game = document.getElementById('game');
            const scoreDisplay = document.getElementById('score');
            let score = 0;

            function generateBlocks() {
            game.innerHTML = '';
            const randomIndex = Math.floor(Math.random() * 25);
            for (let i = 0; i < 25; i++) {
                const block = document.createElement('div');
                block.style.width = '100px';
                block.style.height = '100px';
                block.style.backgroundColor = i === randomIndex ? getRandomColor() : '#ccc';
                block.addEventListener('click', () => {
                if (i === randomIndex) {
                    score++;
                    scoreDisplay.textContent = score;
                    generateBlocks();
                }
                });
                game.appendChild(block);
            }
            }

            function getRandomColor() {
            const letters = '0123456789ABCDEF';
            let color = '#';
            for (let i = 0; i < 6; i++) {
                color += letters[Math.floor(Math.random() * 16)];
            }
            return color;
            }

            generateBlocks();
        </script>
   
    <div style="padding: 1rem; background-color: #fff; box-shadow: 0 0 10px rgba(0, 0, 0, 0.1); padding-left: 2rem; padding-right: 2rem;"></div>
        <footer>
            <p>자세한 문의는 010-xxxx.xxxx로 연락 주세요</p>
        </footer>
    </div> 
    </main>
</body>
</html>
