<!DOCTYPE html>
<html lang="pt-BR">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Quiz de Análise Combinatória e Probabilidade - Acessível</title>
    <style>
        /* Estilos CSS (inalterados, focando em contraste e legibilidade) */
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            background-color: #f4f4f4;
            color: #333;
            /* Bom contraste */
        }

        .quiz-container {
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            max-width: 700px;
            margin: auto;
        }

        h1 {
            text-align: center;
            color: #004085;
            /* Cor para título */
        }

        .pergunta {
            margin-bottom: 20px;
            padding: 15px;
            border: 1px solid #ddd;
            border-radius: 5px;
        }

        .pergunta h3 {
            margin-top: 0;
            color: #333;
        }

        label {
            display: block;
            margin: 5px 0;
            padding: 5px;
            border-radius: 3px;
            cursor: pointer;
            transition: background-color 0.2s;
        }

        label:hover {
            background-color: #e9ecef;
        }

        button {
            display: block;
            width: 100%;
            padding: 12px;
            background-color: #28a745;
            /* Cor de sucesso para o botão */
            color: white;
            border: none;
            border-radius: 5px;
            font-size: 18px;
            cursor: pointer;
            margin-top: 20px;
            font-weight: bold;
        }

        button:hover {
            background-color: #1e7e34;
        }

        /* Foco para navegação por teclado (A11Y) */
        button:focus,
        input[type="radio"]:focus+label {
            outline: 2px solid #007bff;
            outline-offset: 2px;
        }

        #resultado {
            margin-top: 30px;
            padding: 20px;
            border: 2px solid #28a745;
            border-radius: 5px;
            background-color: #e2f0e8;
            font-weight: bold;
            text-align: center;
            display: none;
        }
    </style>
</head>

<body>

    <main class="quiz-container">
        <header>
            <h1>Quiz: Análise Combinatória e Probabilidade</h1>
            <p>Marque a alternativa correta para cada uma das 6 perguntas e clique em "Finalizar" para ver sua
                pontuação.</p>
        </header>

        <form id="quizForm" aria-labelledby="quiz-titulo">

            <section class="pergunta" role="group" aria-labelledby="q1-titulo">
                <h3 id="q1-titulo">1. De quantas maneiras distintas podemos formar um pódio (1º, 2º e 3º
                    lugar) com 5 atletas?</h3>
                <label><input type="radio" name="p1" value="a" required> 15</label>
                <label><input type="radio" name="p1" value="b" required> 60</label>
                <label><input type="radio" name="p1" value="c" required> 120</label>
                <label><input type="radio" name="p1" value="d" required> 5</label>
            </section>

            <section class="pergunta" role="group" aria-labelledby="q2-titulo">
                <h3 id="q2-titulo">2. Quantos anagramas diferentes podem ser formados com as letras da
                    palavra 'ROMA'?</h3>
                <label><input type="radio" name="p2" value="a" required> 12</label>
                <label><input type="radio" name="p2" value="b" required> 24</label>
                <label><input type="radio" name="p2" value="c" required> 48</label>
                <label><input type="radio" name="p2" value="d" required> 4</label>
            </section>

            <section class="pergunta" role="group" aria-labelledby="q3-titulo">
                <h3 id="q3-titulo">3. Em uma turma de 8 alunos, quantos grupos diferentes de 3 alunos
                    podem ser formados para um trabalho?</h3>
                <label><input type="radio" name="p3" value="a" required> 56</label>
                <label><input type="radio" name="p3" value="b" required> 24</label>
                <label><input type="radio" name="p3" value="c" required> 336</label>
                <label><input type="radio" name="p3" value="d" required> 120</label>
            </section>

            <section class="pergunta" role="group" aria-labelledby="q4-titulo">
                <h3 id="q4-titulo">4. Qual é a probabilidade de lançar um dado honesto (6 faces) e obter
                    um número par?</h3>
                <label><input type="radio" name="p4" value="a" required> 1/6</label>
                <label><input type="radio" name="p4" value="b" required> 1/3</label>
                <label><input type="radio" name="p4" value="c" required> 1/2</label>
                <label><input type="radio" name="p4" value="d" required> 2/3</label>
            </section>

            <section class="pergunta" role="group" aria-labelledby="q5-titulo">
                <h3 id="q5-titulo">5. Em uma caixa há 5 bolas azuis e 5 bolas vermelhas. Ao retirar uma
                    bola aleatoriamente, qual a probabilidade de ela ser azul?</h3>
                <label><input type="radio" name="p5" value="a" required> 1/10</label>
                <label><input type="radio" name="p5" value="b" required> 1/5</label>
                <label><input type="radio" name="p5" value="c" required> 1/4</label>
                <label><input type="radio" name="p5" value="d" required> 1/2</label>
            </section>

            <section class="pergunta" role="group" aria-labelledby="q6-titulo">
                <h3 id="q6-titulo">6. Qual a probabilidade de, ao lançar uma moeda honesta duas vezes,
                    obter 'cara' nas duas vezes?</h3>
                <label><input type="radio" name="p6" value="a" required> 1/2</label>
                <label><input type="radio" name="p6" value="b" required> 1/4</label>
                <label><input type="radio" name="p6" value="c" required> 1/8</label>
                <label><input type="radio" name="p6" value="d" required> 1/16</label>
            </section>

            <button type="submit" id="finalizar-btn">Finalizar Questionário</button>
        </form>

        <div id="resultado" role="status" aria-live="polite"></div>
    </main>

    <script>
        document.getElementById('quizForm').addEventListener('submit', function (event) {
            event.preventDefault();

            const respostasCorretas = {
                p1: 'b', p2: 'b', p3: 'a',
                p4: 'c', p5: 'd', p6: 'b'
            };

            let pontuacao = 0;
            const totalPerguntas = 6;
            const form = event.target;

            for (const pergunta in respostasCorretas) {
                const respostaSelecionada = form.elements[pergunta].value;
                if (respostaSelecionada === respostasCorretas[pergunta]) {
                    pontuacao++;
                }
            }

            const resultadoDiv = document.getElementById('resultado');
            resultadoDiv.style.display = 'block';

            let mensagem = `Você acertou **${pontuacao}** de **${totalPerguntas}** perguntas.`;
            let corBorda = '#28a745';
            let corFundo = '#e2f0e8';

            if (pontuacao === totalPerguntas) {
                mensagem += `<br>Parabéns! Você gabaritou o questionário! 🎉`;
            } else if (pontuacao >= totalPerguntas / 2) {
                mensagem += `<br>Bom desempenho! Continue praticando!`;
                corBorda = '#ffc107';
                corFundo = '#fff3cd';
            } else {
                mensagem += `<br>Você pode melhorar. Reveja os conceitos!`;
                corBorda = '#dc3545';
                corFundo = '#f8d7da';
            }

            resultadoDiv.style.borderColor = corBorda;
            resultadoDiv.style.backgroundColor = corFundo;

            resultadoDiv.innerHTML = `<h2>Resultado</h2>${mensagem.replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>')}`;

            // Move o foco para a área de resultado para usuários de teclado/leitores de tela
            resultadoDiv.tabIndex = -1;
            resultadoDiv.focus();
        });
    </script>

</body>

</html>
