<!-- # [ zrfisaac ] -->

<!-- # [ about ] -->
<!-- # - author : Isaac Caires -->
<!-- # . - email : zrfisaac@gmail.com -->
<!-- # . - site : zrfisaac.github.io -->
<!-- # - version : zrfisaac.wiki.pt.physis : 25.6.15.1 -->

<!-- # [ markdown ] -->
# Física

## Descrição
Física é a ciência que estuda os fenômenos naturais do universo, investigando as propriedades, comportamentos e interações da matéria, energia, espaço e tempo, buscando entender as leis que regem o funcionamento do mundo ao nosso redor.

---

## Índice
- [Fórmulas](#fórmulas)
  - [Princípio da Incerteza de Heisenberg](#princípio-da-incerteza-de-heisenberg)

---

## [Fórmulas](#índice)

### [Princípio da Incerteza de Heisenberg](#índice)

$$
\Delta x \cdot \Delta p \geq \frac{\hbar}{2}
$$

> * $\hbar = 1.054571817 \times 10^{-34}$ J·s
>   (Constante de Planck reduzida)
> * $\Delta x = 1 \times 10^{-10}$ m
>   (Incerteza na posição)

$$
\Delta p \geq \frac{1.054571817 \times 10^{-34}}{2 \times 1 \times 10^{-10}} = 5.272859085 \times 10^{-25} \, \text{kg} \cdot \text{m/s}
$$

```javascript
// Constante de Planck reduzida (h-bar), em Joules * segundo
const hBar = 1.054571817e-34;

// Função que calcula a incerteza mínima no momento (DeltaP)
// dado um valor de incerteza na posição (DeltaX)
function calcularIncertezaMomento(deltaX) {
  const deltaP = hBar / (2 * deltaX);
  return deltaP;
}

// Exemplo: DeltaX = 1e-10 metros (100 picômetros)
const deltaX = 1e-10;
const deltaP = calcularIncertezaMomento(deltaX);

console.log("DeltaX:", deltaX, "m");
console.log("DeltaP mínimo:", deltaP, "kg·m/s");
```
