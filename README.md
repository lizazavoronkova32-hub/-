
```html
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Приметы и суеверия</title>
    <style>
        :root {
            --primary-color: #2E8B57;
            --secondary-color: #3CB371;
            --light-color: #90EE90;
            --dark-color: #006400;
            --text-color: #333;
            --background-color: #F5FFFA;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: var(--background-color);
            color: var(--text-color);
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        header {
            background: linear-gradient(to right, var(--primary-color), var(--secondary-color));
            color: white;
            padding: 2rem 0;
            text-align: center;
            border-bottom: 5px solid var(--dark-color);
        }
        
        h1 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }
        
        h2 {
            color: var(--primary-color);
            margin-bottom: 1rem;
        }
        
        section {
            padding: 3rem 0;
        }
        
        .test-section {
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            padding: 2rem;
            margin-bottom: 2rem;
        }
        
        .question {
            margin-bottom: 2rem;
            padding-bottom: 1.5rem;
            border-bottom: 1px solid var(--light-color);
        }
        
        .question:last-child {
            border-bottom: none;
        }
        
        .question p {
            font-size: 1.2rem;
            margin-bottom: 1rem;
        }
        
        .answers {
            display: flex;
            gap: 1rem;
        }
        
        .answer-btn {
            background-color: var(--light-color);
            border: none;
            padding: 0.5rem 1.5rem;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1rem;
            transition: all 0.3s ease;
        }
        
        .answer-btn:hover {
            background-color: var(--secondary-color);
            color: white;
        }
        
        .answer-btn.selected {
            background-color: var(--primary-color);
            color: white;
        }
        
        .submit-btn {
            background-color: var(--primary-color);
            color: white;
            border: none;
            padding: 0.8rem 2rem;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1.2rem;
            display: block;
            margin: 2rem auto 0;
            transition: all 0.3s ease;
        }
        
        .submit-btn:hover {
            background-color: var(--dark-color);
        }
        
        .result-section {
            display: none;
            text-align: center;
            padding: 2rem;
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .info-section {
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            padding: 2rem;
        }
        
        .info-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }
        
        .info-card {
            background-color: var(--light-color);
            padding: 1.5rem;
            border-radius: 8px;
            border-left: 5px solid var(--primary-color);
        }
        
        .qr-section {
            text-align: center;
            margin-top: 2rem;
            padding: 2rem;
            background-color: var(--light-color);
            border-radius: 10px;
        }
        
        .qr-code {
            width: 200px;
            height: 200px;
            background-color: white;
            margin: 1rem auto;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 8px;
            font-weight: bold;
            color: var(--dark-color);
        }
        
        footer {
            background-color: var(--dark-color);
            color: white;
            text-align: center;
            padding: 2rem 0;
            margin-top: 3rem;
        }
        
        .site-link {
            color: var(--light-color);
            text-decoration: none;
            font-weight: bold;
        }
        
        .site-link:hover {
            text-decoration: underline;
        }
        
        @media (max-width: 768px) {
            h1 {
                font-size: 2rem;
            }
            
            .answers {
                flex-direction: column;
            }
            
            .answer-btn {
                width: 100%;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <h1>Приметы и суеверия</h1>
            <p>Исследуйте мир народных примет и проверьте свои знания</p>
        </div>
    </header>
    
    <main class="container">
        <section id="test-section" class="test-section">
            <h2>Тест на знание примет и суеверий</h2>
            <p>Ответьте на 15 вопросов, выбрав "Да" или "Нет"</p>
            
            <div id="questions-container">
                <!-- Вопросы будут добавлены с помощью JavaScript -->
            </div>
            
            <button id="submit-btn" class="submit-btn">Завершить тест</button>
        </section>
        
        <section id="result-section" class="result-section">
            <h2>Результаты теста</h2>
            <p id="result-text">Вы ответили правильно на <span id="correct-answers">0</span> из 15 вопросов.</p>
            <p id="result-message"></p>
            <button id="retry-btn" class="submit-btn">Пройти тест еще раз</button>
        </section>
        
        <section id="info-section" class="info-section">
            <h2>Информация о приметах и суевериях</h2>
            <p>Приметы и суеверия — это часть народной культуры, передаваемая из поколения в поколение. Они отражают веру людей в связь между событиями и их последствиями, часто без научного обоснования.</p>
            
            <div class="info-grid">
                <div class="info-card">
                    <h3>Исторические корни</h3>
                    <p>Многие приметы имеют древние корни и связаны с языческими верованиями, наблюдениями за природой и попытками объяснить непонятные явления.</p>
                </div>
                
                <div class="info-card">
                    <h3>Распространенные приметы</h3>
                    <p>Черная кошка, перебегающая дорогу, разбитое зеркало, рассыпанная соль — эти и многие другие приметы известны практически каждому.</p>
                </div>
                
                <div class="info-card">
                    <h3>Психологический аспект</h3>
                    <p>Следование приметам может давать человеку чувство контроля над непредсказуемыми событиями и снижать тревожность.</p>
                </div>
                
                <div class="info-card">
                    <h3>Культурные различия</h3>
                    <p>Приметы сильно различаются в разных культурах — то, что считается хорошей приметой в одной стране, может быть плохой в другой.</p>
                </div>
            </div>
            
            <div class="qr-section">
                <h3>Поделитесь сайтом с друзьями</h3>
                <p>Отсканируйте QR-код, чтобы перейти на этот сайт</p>
                <div class="qr-code">
                    <!-- В реальном проекте здесь был бы настоящий QR-код -->
                    QR-код сайта
                </div>
                <p>Или перейдите по ссылке: <a href="#" class="site-link">www.primety-i-sueveriya.ru</a></p>
            </div>
        </section>
    </main>
    
    <footer>
        <div class="container">
            <p>Итоговый проект 11 класса по теме "Приметы и суеверия"</p>
            <p>© 2023 Все права защищены</p>
        </div>
    </footer>
    
    <script>
        // Вопросы для теста
        const questions = [
            "Верите ли вы, что черная кошка, перебежавшая дорогу, приносит неудачу?",
            "Считаете ли вы, что разбитое зеркало приносит 7 лет несчастий?",
            "Верите ли вы, что рассыпанная соль приводит к ссоре?",
            "Считаете ли вы, что стучать по дереву можно отогнать неудачу?",
            "Верите ли вы, что нельзя передавать что-либо через порог?",
            "Считаете ли вы, что пустые ведра, встреченные по дороге, - к неудаче?",
            "Верите ли вы, что найти подкову - к удаче?",
            "Считаете ли вы, что нельзя свистеть в доме, чтобы не выдуть деньги?",
            "Верите ли вы, что чешется левая ладонь - к получению денег?",
            "Считаете ли вы, что перебежавшая дорогу женщина с пустыми ведрами - к неудаче?",
            "Верите ли вы, что садиться на углу стола - к безбрачию?",
            "Считаете ли вы, что вернуться с полпути - к неудаче?",
            "Верите ли вы, что встреча с черным котом - к удаче?",
            "Считаете ли вы, что нельзя дарить ножи, чтобы не поссориться?",
            "Верите ли вы, что паук в доме - к добрым вестям?"
        ];
        
        // Правильные ответы (в реальном проекте могут быть другими)
        const correctAnswers = [
            false, // Черная кошка - нет
            false, // Разбитое зеркало - нет
            true,  // Рассыпанная соль - да
            true,  // Стучать по дереву - да
            true,  // Передавать через порог - да
            true,  // Пустые ведра - да
            true,  // Найти подкову - да
            true,  // Нельзя свистеть - да
            true,  // Левая ладонь - да
            true,  // Женщина с пустыми ведрами - да
            true,  // Садиться на углу стола - да
            true,  // Вернуться с полпути - да
            false, // Встреча с черным котом - нет
            true,  // Нельзя дарить ножи - да
            true   // Паук в доме - да
        ];
        
        // Переменные для хранения ответов пользователя
        let userAnswers = new Array(questions.length).fill(null);
        
        // Функция для отображения вопросов
        function renderQuestions() {
            const container = document.getElementById('questions-container');
            container.innerHTML = '';
            
            questions.forEach((question, index) => {
                const questionElement = document.createElement('div');
                questionElement.className = 'question';
                
                const questionText = document.createElement('p');
                questionText.textContent = `${index + 1}. ${question}`;
                questionElement.appendChild(questionText);
                
                const answersContainer = document.createElement('div');
                answersContainer.className = 'answers';
                
                const yesButton = document.createElement('button');
                yesButton.className = 'answer-btn';
                yesButton.textContent = 'Да';
                yesButton.dataset.index = index;
                yesButton.dataset.answer = true;
                yesButton.addEventListener('click', handleAnswerClick);
                
                const noButton = document.createElement('button');
                noButton.className = 'answer-btn';
                noButton.textContent = 'Нет';
                noButton.dataset.index = index;
                noButton.dataset.answer = false;
                noButton.addEventListener('click', handleAnswerClick);
                
                answersContainer.appendChild(yesButton);
                answersContainer.appendChild(noButton);
                questionElement.appendChild(answersContainer);
                
                container.appendChild(questionElement);
            });
        }
        
        // Обработчик клика по ответу
        function handleAnswerClick(event) {
            const index = parseInt(event.target.dataset.index);
            const answer = event.target.dataset.answer === 'true';
            
            // Сбрасываем выделение для всех кнопок этого вопроса
            const questionElement = event.target.closest('.question');
            const answerButtons = questionElement.querySelectorAll('.answer-btn');
            answerButtons.forEach(button => {
                button.classList.remove('selected');
            });
            
            // Выделяем выбранную кнопку
            event.target.classList.add('selected');
            
            // Сохраняем ответ пользователя
            userAnswers[index] = answer;
        }
        
        // Функция для проверки результатов
        function checkResults() {
            let correctCount = 0;
            
            for (let i = 0; i < questions.length; i++) {
                if (userAnswers[i] === correctAnswers[i]) {
                    correctCount++;
                }
            }
            
            return correctCount;
        }
        
        // Функция для отображения результатов
        function showResults() {
            const correctCount = checkResults();
            const resultText = document.getElementById('result-text');
            const resultMessage = document.getElementById('result-message');
            const correctAnswersElement = document.getElementById('correct-answers');
            
            correctAnswersElement.textContent = correctCount;
            
            if (correctCount >= 12) {
                resultMessage.textContent = "Отличный результат! Вы хорошо разбираетесь в приметах и суевериях.";
            } else if (correctCount >= 8) {
                resultMessage.textContent = "Хороший результат! Вы знаете основные приметы и суеверия.";
            } else {
                resultMessage.textContent = "Неплохой результат! Возможно, вы скептически относитесь к приметам.";
            }
            
            document.getElementById('test-section').style.display = 'none';
            document.getElementById('result-section').style.display = 'block';
        }
        
        // Функция для сброса теста
        function resetTest() {
            userAnswers = new Array(questions.length).fill(null);
            document.getElementById('test-section').style.display = 'block';
            document.getElementById('result-section').style.display = 'none';
            renderQuestions();
        }
        
        // Инициализация при загрузке страницы
        document.addEventListener('DOMContentLoaded', function() {
            renderQuestions();
            
            document.getElementById('submit-btn').addEventListener('click', function() {
                // Проверяем, ответил ли пользователь на все вопросы
                if (userAnswers.includes(null)) {
                    alert('Пожалуйста, ответьте на все вопросы перед завершением теста.');
                    return;
                }
                
                showResults();
            });
            
            document.getElementById('retry-btn').addEventListener('click', resetTest);
        });
    </script>
</body>
</html>
