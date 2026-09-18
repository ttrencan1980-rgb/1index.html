<!DOCTYPE html>
<html lang="sk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Test č. 1 - RT</title>
    <style>
        * { box-sizing: border-box; }
        body { font-family: system-ui, sans-serif; background: #f1f5f9; padding: 16px; margin: 0; display: flex; justify-content: center; }
        .card { background: #fff; max-width: 500px; width: 100%; border-radius: 12px; padding: 20px; box-shadow: 0 1px 3px rgba(0,0,0,0.1); }
        .back-btn { display: inline-block; margin-bottom: 16px; color: #2563eb; text-decoration: none; font-weight: 600; }
        h2 { font-size: 18px; color: #0f172a; margin-top: 0; }
        .option { display: block; width: 100%; padding: 12px; margin: 8px 0; background: #f8fafc; border: 1px solid #cbd5e1; border-radius: 8px; text-align: left; font-size: 15px; cursor: pointer; }
        .option.correct { background: #dcfce7; border-color: #22c55e; color: #14532d; font-weight: 600; }
        .option.incorrect { background: #fee2e2; border-color: #ef4444; color: #7f1d1d; }
        .next-btn { width: 100%; padding: 12px; background: #2563eb; color: white; border: none; border-radius: 8px; font-size: 16px; font-weight: 600; margin-top: 12px; display: none; cursor: pointer; }
    </style>
</head>
<body>

<div class="card">
    <a href="index.html" class="back-btn">← Späť na zoznam testov</a>
    <div id="quiz">
        <h2 id="question">Načítavam otázku...</h2>
        <div id="options"></div>
        <button id="next-btn" class="next-btn" onclick="nextQuestion()">Ďalšia otázka</button>
    </div>
</div>

<script>
    const quizData = [
        {
            question: "1. Aká je podmienka pre odbornú spôsobilosť revízneho technika podľa vyhlášky?",
            options: [
                { text: "A) Osvedčenie vydané oprávnenou právnickou osobou", correct: true },
                { text: "B) Len maturitné vysvedčenie", correct: false },
                { text: "C) Absolvovanie 1-dňového kurzu bez skúšky", correct: false }
            ]
        },
        {
            question: "2. Aká norma rieši ochranu pred bleskom (LPS)?",
            options: [
                { text: "A) STN EN 62305", correct: true },
                { text: "B) STN 33 2000-5-51", correct: false },
                { text: "C) STN 33 1630", correct: false }
            ]
        }
    ];

    let current = 0;

    function loadQuestion() {
        const q = quizData[current];
        document.getElementById("question").innerText = q.question;
        const opts = document.getElementById("options");
        opts.innerHTML = "";
        document.getElementById("next-btn").style.display = "none";

        q.options.forEach(opt => {
            const btn = document.createElement("button");
            btn.className = "option";
            btn.innerText = opt.text;
            btn.onclick = () => {
                document.querySelectorAll(".option").forEach(b => b.disabled = true);
                if (opt.correct) {
                    btn.classList.add("correct");
                } else {
                    btn.classList.add("incorrect");
                }
                document.getElementById("next-btn").style.display = "block";
            };
            opts.appendChild(btn);
        });
    }

    function nextQuestion() {
        current++;
        if (current < quizData.length) {
            loadQuestion();
        } else {
            document.getElementById("quiz").innerHTML = "<h2>Test dokončený!</h2><br><a href='index.html' class='back-btn'>Návrat na hlavné menu</a>";
        }
    }

    loadQuestion();
</script>

</body>
</html>
# 1index.html
Test_RT
