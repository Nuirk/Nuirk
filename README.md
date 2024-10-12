<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Викторина по бизнесу</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            padding: 20px;
        }
        h1 {
            text-align: center;
        }
        .quiz-container {
            background-color: #fff;
            border-radius: 10px;
            padding: 20px;
            max-width: 600px;
            margin: auto;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .question {
            margin: 20px 0;
            font-weight: bold;
        }
        .answers label {
            display: block;
            margin-bottom: 10px;
        }
        .submit-btn {
            display: block;
            width: 100%;
            padding: 10px;
            margin-top: 20px;
            background-color: #28a745;
            color: white;
            border: none;
            border-radius: 5px;
            font-size: 16px;
            cursor: pointer;
        }
        .submit-btn:hover {
            background-color: #218838;
        }
        .result {
            margin-top: 20px;
            font-size: 18px;
            font-weight: bold;
            text-align: center;
        }
    </style>
</head>
<body>

<h1>Викторина по бизнесу</h1>

<div class="quiz-container">
    <div class="question">
        1. Что такое предпринимательство?
    </div>
    <div class="answers">
        <label><input type="radio" name="q1" value="A"> A) Процесс создания и управления бизнесом для получения прибыли.</label>
        <label><input type="radio" name="q1" value="B"> B) Работа по найму на крупное предприятие.</label>
        <label><input type="radio" name="q1" value="C"> C) Государственное регулирование бизнеса.</label>
        <label><input type="radio" name="q1" value="D"> D) Инвестирование в акции компаний.</label>
    </div>

    <div class="question">
        2. Какая из этих форм бизнеса имеет неограниченную ответственность?
    </div>
    <div class="answers">
        <label><input type="radio" name="q2" value="A"> A) Акционерное общество.</label>
        <label><input type="radio" name="q2" value="B"> B) Индивидуальный предприниматель.</label>
        <label><input type="radio" name="q2" value="C"> C) Общество с ограниченной ответственностью (ООО).</label>
        <label><input type="radio" name="q2" value="D"> D) Корпорация.</label>
    </div>

    <div class="question">
        3. Что такое доход?
    </div>
    <div class="answers">
        <label><input type="radio" name="q3" value="A"> A) Общая стоимость всех активов компании.</label>
        <label><input type="radio" name="q3" value="B"> B) Разница между выручкой и расходами компании.</label>
        <label><input type="radio" name="q3" value="C"> C) Сумма, которую компания получает от продажи товаров или услуг.</label>
        <label><input type="radio" name="q3" value="D"> D) Сумма налогов, уплачиваемых компанией.</label>
    </div>

    <button class="submit-btn" onclick="checkAnswers()">Проверить ответы</button>

    <div class="result" id="result"></div>
</div>

<script>
    function checkAnswers() {
        const correctAnswers = {
            q1: 'A',
            q2: 'B',
            q3: 'B'
        };

        let score = 0;

        const userAnswers = {
            q1: document.querySelector('input[name="q1"]:checked')?.value,
            q2: document.querySelector('input[name="q2"]:checked')?.value,
            q3: document.querySelector('input[name="q3"]:checked')?.value
        };

        for (let question in correctAnswers) {
            if (correctAnswers[question] === userAnswers[question]) {
                score++;
            }
        }

        document.getElementById('result').innerText = `Вы ответили правильно на ${score} из 3 вопросов.`;
    }
</script>

</body>
</html>
