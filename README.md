# RsaCalculator



DEMO PAGE : 

https://majidsabzalian.github.io/RsaCalculator/

ALG :
```
let
  p = document.getElementById('p').value || 1,
  plain = document.getElementById('plain').value || 1,
  q = document.getElementById('q').value || 1,
  e = document.getElementById('e').value || 1,
  d = document.getElementById('d').value || 1;

let pw = (num, pow) => {
    let n = p * q;
    let join = (arr, x = (a, b) => { }) => Array(Math.ceil(arr.length / 2)).fill('').map((e, i) => x(arr[i * 2], arr[(i * 2) + 1] || 1));
    let arr = [], dev = (pw) => (num ** pw) % n, px = 0;
    while (px < pow) { arr.push(dev((pow - px < 2) ? (pow - px) : 2)); px += 2; }
    while (arr.length > 2) arr = join(arr, (a, b) => (a * b) % n);
    return (arr.reduce((a, b) => a *= b) % n);
};
let enc = (num) => pw(num, e), dec = (num) => pw(num, d);

// use : enc(111)
```
