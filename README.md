# Node.js.__GB__
## creando una mini consola que escuvha lo que escribes
```bash
 // Output un prompt
  process.stdout.write('prompt > ');
  // El evento stdin 'data' se dispara cuando el user escribe una línea
  process.stdin.on('data', function (data) {
    var cmd = data.toString().trim(); // remueve la nueva línea
    process.stdout.write('You typed: ' + cmd);
    process.stdout.write('\nprompt > ');
  });

```
