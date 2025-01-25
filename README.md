## Calculadora com HTML, CSS, e JavaScript

# Calculadora Simples

Este é um projeto de uma calculadora simples desenvolvida com HTML, CSS e JavaScript. A calculadora possui uma interface estilizada e funcionalidade para realizar operações matemáticas básicas.

---

## Código Completo

Abaixo está o código completo do projeto.

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }
        .fundo {
            background-image: linear-gradient(45deg, black, #95DB7F);
            height: 100vh;
            color: #fff;
            font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
            text-align: center;
        }
        .Calculadora {
            position: absolute;
            background-color: rgba(0, 0, 0, 0.8);
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            border-radius: 15px;
            padding: 15px;
        }
        .bota {
           width: 50px;
           height: 50px;
           font-size: 25px;
           cursor: pointer;
           background: rgb(31, 31, 31);
           border: none;
           color: #fff;
           margin: 3px;
        }
        .bota:hover {
            background-color: black;
        }
        #resultado {
          background-color: #fff;
          width: 207px;
          height: 30px;
          margin: 5px;
          font-size: 25px;
          color: #000;
          text-align: right;
          padding: 5px;
        }
    </style>
</head>
<body>
    <div class="fundo">
        <h1>Dayana Nascimento</h1>
        <div class="Calculadora">
            <h1>Calculadora</h1>
            <p id="resultado"></p>
            <table>
                <tr>
                    <td><button class="bota" onclick="clean()">C</button></td>
                    <td><button class="bota" onclick="back()"><</button></td>
                    <td><button class="bota" onclick="insert('/')">/</button></td>
                    <td><button class="bota" onclick="insert('*')">*</button></td>
                </tr>
                <tr>
                    <td><button class="bota" onclick="insert('7')">7</button></td>
                    <td><button class="bota" onclick="insert('8')">8</button></td>
                    <td><button class="bota" onclick="insert('9')">9</button></td>
                    <td><button class="bota" onclick="insert('-')">-</button></td>
                </tr>
                <tr>
                    <td><button class="bota" onclick="insert('4')">4</button></td>
                    <td><button class="bota" onclick="insert('5')">5</button></td>
                    <td><button class="bota" onclick="insert('6')">6</button></td>
                    <td><button class="bota" onclick="insert('+')">+</button></td>
                </tr>
                <tr>
                    <td><button class="bota" onclick="insert('1')">1</button></td>
                    <td><button class="bota" onclick="insert('2')">2</button></td>
                    <td><button class="bota" onclick="insert('3')">3</button></td>
                    <td rowspan="2"><button class="bota" style="height: 106px;" onclick="calcular()">=</button></td>
                </tr>
                <tr>
                    <td colspan="2"><button class="bota" style="width: 106px;" onclick="insert('0')">0</button></td>
                    <td><button class="bota" onclick="insert(',')">,</button></td>
                </tr>
            </table>
        </div>
    </div>
    <script>
        function insert(num) {
          var numero = document.getElementById('resultado').innerHTML;
          document.getElementById('resultado').innerHTML = numero + num;
        }
        function clean() {
            document.getElementById('resultado').innerHTML = "";
        }
        function back() {
          var resultado = document.getElementById('resultado').innerHTML;
          document.getElementById('resultado').innerHTML = resultado.substring(0, resultado.length - 1);
        }
        function calcular() {
            var resultado = document.getElementById('resultado').innerHTML;
            if (resultado) {
                document.getElementById('resultado').innerHTML = eval(resultado);
            } else {
                document.getElementById('resultado').innerHTML = "Nada...";
            }
        }
    </script>
</body>
</html>

