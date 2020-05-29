# Exercícios Santander Coders by Digital House

## **Exercício 1**

Vamos criar uma função `perimetro` que nos diga o perímetro de um círculo quando damos a ele o `raio` como parâmetro.
Também a função `area` que nos dá a `área` de um círculo quando recebe o `raio` como parâmetro.<p><p>

Aqui estão as fórmulas necessárias para as funções, além disso, para este exercício iremos considerar que o valor de π é 3.14.

_perimetro = π * raio * 2;<br>_
_area = π * raio * raio;_

<br>

> #### Dica:
>
> _Lembre-se de usar o valor de 3.14 no lugar do π_

<br>

**Solução:**

```Javascript
function perimetro(raio) {
  let c = 2 * 3.14 * raio;
  return c
}
console.log(perimetro(2));

function area(raio) {
  let a = 3.14 * raio * raio;
  return a;
}
console.log(area(2));
```

<br>

---

<br>

## **Exercício 2**

Escreva a função `eNumeroDaSorte` que, recebendo um número, diz a se é um número da sorte. <br>
Lembre-se de que o número deve obedecer às três condições mencionadas.<p>

<br>

> Seu desafio adicional será: **NÃO use o if.**

<br>

**Solução:**

```Javascript
function eNumeroDaSorte(num) {
    return num > 0 && num % 2 == 0 || num % 3 == 0 && num != 15;
}

eNumeroDaSorte(14)
```

<br>

---

<br>

## **Exercício 3**

Defina a função `possoIrAoBanco` que, receba dois parâmetros, o primeiro é `diaDaSemana` (string) e o segundo `horaAtual` (numero), a função deve retornar `true`, apenas se o banco estiver aberto.

<br>

**Exemplo:**

```Javascript
$ possoIrAoBanco("segunda-feira", 10);
true  // é um dia da semana e está no horário bancário, 10hs
$ possoIrAoBanco("terça-feira", 18);
false // é dia da semana e NÃO está no horário bancário, 18hs
$ possoIrAoBanco("Sábado", 11);
false // é fim de semana
```

<br>

**Solução:**

```Javascript
function possoIrAoBanco(diaDaSemana, horaAtual) {
    return diaDaSemana != 'Sábado' && diaDaSemana != 'Domingo' && horaAtual >= 9 && horaAtual <= 15;
}

possoIrAoBanco("segunda-feira", 8)
possoIrAoBanco("Sábado", 10)
possoIrAoBanco("terça-feira", 12)
```

<br>

---

<br>

## **Exercício 4**

Escreva a função `podeSeAposentar` que recebe por parâmetro a `idade`, o `sexo` e os `anos de contribuição previdenciária` que uma pessoa tem.

<br>

**Exemplo:**

```Javascript
$ podeSeAposentar(62, "F", 34)
true
```

<br>

> #### Dica:
>
> _Tenha em mente que a idade mínima para se aposentar para mulheres é 60 anos, >enquanto que para homens é 65. Em ambos os casos, você deve ter pelo menos 30 >anos de contribuição._

<br>

**Solução:**

```Javascript
function podeSeAposentar(idade, sexo, anosContribuicao) {
  return (idade >= 65 && sexo == "M" || idade >= 60 && sexo == "F") && anosContribuicao >= 30;
}

console.log(podeSeAposentar(68, "M", 26));
```

<br>

---

<br>

## **Exercício 5**

Defina a função `podeSubir`, recebendo 3 parâmetros: `alturaPessoa` (numero), `vemComCompania` (booleano), `temProblemaCardiaco` (booleano), retorne `true` ou `false` conforme o caso.<br>
Levar em conta as condições necessárias mencionadas acima.

<br>

**Exemplo:**

```Javascript
$ podeSubir(1.7, false, true)
false // não pode subir
       // porque embora seja maior do que 1.5m,
       // tem um problema cardíaco
```

<br>

> #### Regras:
>
> - Atingir a altura mínima de 1,5 m (ou 1,2 m, se acompanhada por um adulto)
> - Não ter qualquer problema cardíaco

<br>

**Solução:**

```Javascript
function podeSubir(alturaPessoa, vemComCompania, temProblemaCardiaco) {
  return (
    alturaPessoa >= 1.2 &&
    vemComCompania ||
    alturaPessoa >= 1.5 &&
    !vemComCompania &&
    !temProblemaCardiaco
  )
}
```

<br>

---

<br>

## **Exercício 6**

Defina a função `medalhaSegundoOPosto` que recebe o posto como parâmetro e retorna um texto de acordo com o parâmetro.

<br>

> #### Dica:
>
> _Nessa função você pode usar vários if._

<br>

**Exemplo:**

```Javascript
$ medalhaSegundoOPosto(1)
"ouro"
$ medalhaSegundoOPosto(2)
"prata"
$ medalhaSegundoOPosto(3)
"bronze"
$ medalhaSegundoOPosto(5)
"Continue participando"
```

<br>

> #### Regras:
>
> - primeiro lugar: corresponde "ouro"
> - segundo lugar: corresponde "prata"
> - terceiro lugar: corresponde "bronze"
> - outros lugares: corresponde "Continue participando"

<br>

**Solução:**

```Javascript
function medalhaSegundoOPosto(posto) {
if (posto === 1) {
  return 'ouro';
}
if (posto === 2) {
  return 'prata';
}
if (posto === 3) {
  return 'bronze';
}
return 'Continue participando';
}
```

<br>

---

<br>

## **Exercício 7**

Execute uma função chamada `passandoPelosPares()` que mostra pelo console **aqui eu tenho o valor de x** para cada valor **PAR** que percorra i de 0 até e inclusive 6.<br>
Lembre-se que como vamos passar apenas pelos pares a repetição deve ocorrer 4 vezes, pois o objetivo é imprimir apenas os números pares.

<br>

> #### Dica:
> _Para saber se um número é par, usamos o operador % (módulo) que me retorna o resto da divisão de um número por outro. Por exemplo: 11% 5 -> retorna o resto da divisão 11 por 5. Neste caso retorna 1._

<br>

```Javascript
function passandoPelosPares() {
    for (var i = 0; i <= 6; i++) {
        if (i % 2 === 0) {
            console.log("aqui eu tenho o valor de" + " " + i)
        }
    }
}
```