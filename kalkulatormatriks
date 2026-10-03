<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kalkulator Matriks</title>

<style>
body {
    font-family: Arial, sans-serif;
    background: #f2f2f2;
    text-align: center;
    padding: 20px;
}

.container {
    max-width: 700px;
    margin: auto;
    background: white;
    padding: 25px;
    border-radius: 15px;
}

input {
    width: 55px;
    padding: 8px;
    margin: 4px;
    text-align: center;
}

button {
    padding: 10px 15px;
    margin: 8px;
    cursor: pointer;
}

#hasil {
    margin-top: 20px;
    font-size: 18px;
}
</style>
</head>

<body>

<div class="container">

<h1>Kalkulator Matriks</h1>

<h3>Matriks A</h3>

<div>
<input id="a11" value="1">
<input id="a12" value="2">
<br>
<input id="a21" value="3">
<input id="a22" value="4">
</div>

<h3>Matriks B</h3>

<div>
<input id="b11" value="5">
<input id="b12" value="6">
<br>
<input id="b21" value="7">
<input id="b22" value="8">
</div>

<br>

<button onclick="tambah()">A + B</button>
<button onclick="kali()">A × B</button>
<button onclick="gaussJordan()">Gauss-Jordan</button>

<div id="hasil"></div>

</div>

<script>

function nilai(id) {
    return Number(document.getElementById(id).value);
}

function tambah() {

    let A = [
        [nilai("a11"), nilai("a12")],
        [nilai("a21"), nilai("a22")]
    ];

    let B = [
        [nilai("b11"), nilai("b12")],
        [nilai("b21"), nilai("b22")]
    ];

    let C = [
        [A[0][0] + B[0][0], A[0][1] + B[0][1]],
        [A[1][0] + B[1][0], A[1][1] + B[1][1]]
    ];

    tampil(C);
}

function kali() {

    let A = [
        [nilai("a11"), nilai("a12")],
        [nilai("a21"), nilai("a22")]
    ];

    let B = [
        [nilai("b11"), nilai("b12")],
        [nilai("b21"), nilai("b22")]
    ];

    let C = [
        [
            A[0][0]*B[0][0] + A[0][1]*B[1][0],
            A[0][0]*B[0][1] + A[0][1]*B[1][1]
        ],
        [
            A[1][0]*B[0][0] + A[1][1]*B[1][0],
            A[1][0]*B[0][1] + A[1][1]*B[1][1]
        ]
    ];

    tampil(C);
}

function tampil(M) {

    let teks = "<h3>Hasil:</h3>";

    for(let i=0; i<M.length; i++) {
        teks += M[i].join(" &nbsp;&nbsp; ") + "<br>";
    }

    document.getElementById("hasil").innerHTML = teks;
}

function gaussJordan() {

    let A = [
        [nilai("a11"), nilai("a12")],
        [nilai("a21"), nilai("a22")]
    ];

    let aug = [
        [A[0][0], A[0][1], 1, 0],
        [A[1][0], A[1][1], 0, 1]
    ];

    for(let i=0; i<2; i++) {

        let pivot = aug[i][i];

        if(pivot === 0) {
            document.getElementById("hasil").innerHTML =
            "Tidak dapat dilakukan karena pivot = 0.";
            return;
        }

        for(let j=0; j<4; j++) {
            aug[i][j] /= pivot;
        }

        for(let k=0; k<2; k++) {

            if(k !== i) {

                let faktor = aug[k][i];

                for(let j=0; j<4; j++) {
                    aug[k][j] -= faktor * aug[i][j];
                }
            }
        }
    }

    document.getElementById("hasil").innerHTML =
    "<h3>Gauss-Jordan / Matriks Invers:</h3>" +
    aug[0].map(x => x.toFixed(3)).join(" &nbsp; ") +
    "<br>" +
    aug[1].map(x => x.toFixed(3)).join(" &nbsp; ");
}

</script>

</body>
</html>
