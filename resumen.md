# Resumen Inferencia Estadística en Markdown + $\LaTeX$

## Introducción

Resumen de la materia de inferencia estadística de la Licenciatura en Tecnología Digital en la Universidad Torcuato Di Tella.

## Contenido

<!-- @import "[TOC]" {cmd="toc" depthFrom=1 depthTo=6 orderedList=false} -->

<!-- code_chunk_output -->

- [Resumen Inferencia Estadística](#resumen-inferencia-estadística)
  - [Introducción](#introducción)
  - [Contenido](#contenido)
  - [Esperanza](#esperanza)
  - [Varianza](#varianza)
    - [Desvío Estándar](#desvío-estándar)
    - [Covarianza](#covarianza)
    - [Correlación](#correlación)
  - [Continuas](#continuas)
    - [Distribución Normal](#distribución-normal)
      - [Función acumulada](#función-acumulada)
    - [Distribución Uniforme](#distribución-uniforme)
    - [Distribución Exponencial](#distribución-exponencial)
  - [Discretas](#discretas)
    - [Distribución Bernoulli](#distribución-bernoulli)
    - [Distribución Binomial](#distribución-binomial)
    - [Distribución Poisson](#distribución-poisson)
  - [Convergencia en Probabilidad](#convergencia-en-probabilidad)
    - [Propiedades](#propiedades)
  - [Estimación por LGN](#estimación-por-lgn)
    - [Estimación Esperanza](#estimación-esperanza)
    - [Estimación Varianza](#estimación-varianza)
    - [Estimación Proporción](#estimación-proporción)
    - [Estimación de Probabilidad](#estimación-de-probabilidad)
  - [Formulas Consistencia](#formulas-consistencia)
    - [Sesgo](#sesgo)
      - [Asintóticamente Insesgado](#asintóticamente-insesgado)
    - [Error Estándar](#error-estándar)
    - [Error Cuadrático Medio](#error-cuadrático-medio)
  - [Desigualdad de Chebyshev](#desigualdad-de-chebyshev)
  - [Desigualdad de Markov](#desigualdad-de-markov)
  - [Momentos](#momentos)
    - [Momentos de una variable aleatoria](#momentos-de-una-variable-aleatoria)
      - [Discreta](#discreta)
      - [Continua](#continua)
  - [Estimación por Máxima Verosimilitud (Likelihood)](#estimación-por-máxima-verosimilitud-likelihood)
    - [Log-likelihood](#log-likelihood)
  - [Intervalos de Confianza](#intervalos-de-confianza)
    - [Intervalo de Confianza para $\mu$](#intervalo-de-confianza-para-mu)
    - [T-Student](#t-student)

<!-- /code_chunk_output -->

## Esperanza

$
    {\operatorname {E} (X)=\sum _{i=1}^{n}x_{i}\operatorname {F_x}(x_i)} \\
    \operatorname {E} (\overline{X}_n) = \frac{1}{n} \times \sum_{i=1}^{n}{\operatorname {E} (X_i)}
$

Si $X$ y $Y$ son variables aleatorias con esperanza finita y ${a,b,c \in \mathbb {R} }$ son constantes entonces

- ${\operatorname {E} [c]=c}$
- ${\operatorname {E} [cX]=c\operatorname {E} [X]}$
- ${\operatorname {E} [X+Y]=\operatorname {E} [X]+\operatorname {E} [Y]}$
- Si ${X\geq 0}$ entonces ${\operatorname {E} [X]\geq 0}$
- Si ${X\leq Y}$ entonces ${\operatorname {E} [X]\leq \operatorname {E} [Y]}$
- Si $X$ está delimitada por dos números reales, $a$ y $b$, esto es ${a<X<b}$ entonces también lo está su media, es decir, ${a<\operatorname {E} [X]<b}$
- Si ${Y=a+bX}$, entonces ${\operatorname {E} [Y]=\operatorname {E} [a+bX]=a+b\operatorname {E} [X]}$
- Si $X$ y $Y$ son variables aleatorias independientes entonces ${\operatorname {E} [XY]=\operatorname {E} [X]\operatorname {E} [Y]}$

## Varianza

$\operatorname {Var}[X]=\operatorname {E} [X^{2}]-\operatorname {E} [X]^{2} ⟹ \operatorname {E} [X^{2}] = \operatorname {Var}[X] + \operatorname {E} [X]^{2}$

Sean $X$ y $Y$ dos variables aleatorias con varianza finita y ${a\in \mathbb {R} }$

- ${\operatorname {Var} (X)\geq 0}$
- ${\operatorname {Var} (a)=0}$
- ${\operatorname {Var} (aX)=a^{2}\operatorname {Var} (X)}$
- ${\operatorname {Var} (X+Y)=\operatorname {Var} (X)+\operatorname {Var} (Y)+2\operatorname {Cov} (X,Y)}$, donde ${\operatorname {Cov} (X,Y)}$ denota la covarianza de $X$ e $Y$
- ${\operatorname {Var} (X+Y)=\operatorname {Var} (X)+\operatorname {Var} (Y)}$ si $X$ y $Y$ son variables aleatorias independientes.
- ${\operatorname {Var} (Y)=\operatorname {E} (\operatorname {Var} (Y|X))+\operatorname {Var} (\operatorname {E} (Y|X))}$ cálculo de la Varianza por Pitágoras, dónde ${Y|X}$ es la variable aleatoria condicional $Y$ dado $X$.

### Desvío Estándar

${\operatorname{SD}(X) =  \sigma ={\sqrt {{\text{Var}}(X)}}} \implies{\sigma ^{2}={\text{Var}}(X)}$

### Covarianza

${\operatorname {Cov} (X,Y)=\operatorname {E} \left[XY\right]-\operatorname {E} \left[X\right]\operatorname {E} \left[Y\right]}$

### Correlación

$ρ_{xy} = {\frac{\operatorname{cov}_{xy}}{\sigma_x\sigma_y}} = {\frac{\operatorname{cov}_{xy}}{\operatorname{SD}(x)\operatorname{SD}(y)}}$

## Continuas

$$
{\operatorname{F_x}(x) = \int_{-\infty}^{x}{f_X(u)du}} \\
f_X(x) = \frac{d}{dx}{\operatorname{F_x}(x)} \\
$$

$${\operatorname{P}(a < X < b) = \int_a^b{f(x)dx} = \operatorname{F_x}(b) -\operatorname{F_x}(a)} $$

$${\operatorname{P}(a < X < b) = \operatorname{P}(a < X \leq b) = \operatorname{P}(a \leq X < b)= \operatorname{P}(a \leq X \leq b)}$$

### Distribución Normal

Si ${X\sim N(\mu ,\sigma ^{2})}$ y ${a,b\in \mathbb {R} }$, entonces ${aX+b\sim N(a\mu +b,a^{2}\sigma ^{2})}$

Si ${X\,\sim N(\mu ,\sigma ^{2})\,}$, entonces ${Z={\frac {X-\mu }{\sigma }}\!}$ es una variable aleatoria normal estándar: $Z$ ~ $N(0,1)$.

$${X\,\sim N(\mu, \sigma ^{2}) ⟹ Z={\frac {X-\mu }{\sigma }} \sim N(0,1)}$$

$${Z\sim N(0,1) ⟹ X = \sigma Z + \mu \sim N(\mu, \sigma ^{2})}$$

$$
    X \sim N(\mu, \sigma^2) \\
    X+b \sim N(\mu+b, \sigma^2) \\
    aX \sim N(a \times \mu, a^2 \times \sigma^2) \\
    \frac{X - \mu}{\sigma} \sim N(0, 1) \\
    \overline{X}_n \sim N(\mu, \sigma^2/n) \text{, si } X_i \text{ son i.i.d}\\
    \frac{\overline{X}_n - \mu}{\sigma/\sqrt{n}} \sim N(0, 1) \text{, si } X_i \text{ son i.i.d} \\
$$

#### Función acumulada

$
    \operatorname{f}(x) = \operatorname{\phi}(x) = \frac{1}{\sqrt{2 \times \pi \times \sigma^2}} \times e^{-\frac{(x-\mu)^2}{2 \times \sigma^2}}
$

### Distribución Uniforme

$
    \operatorname{P} (a<X<b)=\frac {1}{b-a} \\\
    \operatorname{E}(X) = \frac{a+b}{2} \\
    \operatorname{Var}(X) = \frac{(b-a)^2}{12}
$

### Distribución Exponencial

$
    \operatorname{f_X}(X) = \lambda e^{-\lambda X} \text{, para } X \geq 0 \\
    \operatorname{F_X}(x) = \operatorname{P} (X>x)=1-e^{-\lambda x} \\\
    \operatorname{E}(X) = \frac{1}{\lambda} \\
    \operatorname{Var}(X) = \frac{1}{\lambda^2}
$

## Discretas

### Distribución Bernoulli

$
    \operatorname{P}(X=1) = p \\
    \operatorname{P}(X=0) = 1-p \\
    \operatorname{E}(X) = p \\
    \operatorname{Var}(X) = p(1-p)
$

### Distribución Binomial

$
    {\operatorname {P} (X=k)=\binom {n}{k}p^{k}(1-p)^{n-k}} \\
    {\operatorname {E} (X)=np} \\
    {\operatorname {Var} (X)=np(1-p)}
$

### Distribución Poisson

$
    \operatorname{P}(X=k) = \frac{\lambda^k e^{-\lambda}}{k!} \\
    \operatorname{E}(X) = \lambda \\
    \operatorname{Var}(X) = \lambda
$

## Convergencia en Probabilidad

Sean $X_{n}$ una secuencia de variables aleatorias, $X_{n}\xrightarrow{p} X$ si $\forall \epsilon > 0$

$\lim _{n\rightarrow \infty }\operatorname {P} \left( |\overline{X}_{n} - \operatorname{E}(X) | > \epsilon \right) =0$, por Ley de los Grandes Números.

### Propiedades

Si $X_{n}\xrightarrow{p} a$ y $Y_{n}\xrightarrow{p} b$, entonces:

- $X_{n}+Y_{n}\xrightarrow{p} a+b$
- $X_{n}Y_{n}\xrightarrow{p} a \cdot b$
- $\frac{X_{n}}{Y_{n}}\xrightarrow{p} \frac{a}{b}$ si $b \neq 0$
- $\operatorname{g}(X_{n})\xrightarrow{p} \operatorname{g}(a)$ si $\operatorname{g}$ es una función continua

## Estimación por LGN

Sean $X_{1},X_{2},\dots ,X_{n}$ variables aleatorias independientes e idénticamente distribuidas (i.i.d.) con esperanza $\mu$ y varianza $\sigma^{2}$. Entonces, la media muestral $\overline{X}_{n} \xrightarrow{p} \mu$ por LGN. El estimador $\hat{\mu}_{n}=\overline{X}_{n}$ es consistente.

### Estimación Esperanza

$
\text{parámetro de interés: } \mu = \operatorname{E}(X) \\
\text{muestra aleatoria: } X_1, \dots, X_n \sim f \text{, i.i.d}\\
\text{estimador: } \hat{\mu}_n = \overline{X}_n = \frac{1}{n} \sum_{i=1}^n X_i \\
\text{estimador consistente: } \hat{\mu}_n = \overline{X}_{n}\xrightarrow{p} \mu
$

### Estimación Varianza

$
\text{parámetro de interés: } \sigma^2 = \operatorname{Var}(X) \\
\text{muestra aleatoria: } X_1, \dots, X_n \sim f \text{, i.i.d}\\
\text{estimador: } \hat{\sigma}^2_n = \frac{1}{n} \sum_{i=1}^n (X_i - \overline{X}_n)^2 \\
\text{estimador: } \hat{s}^2_n = \frac{1}{n-1} \sum_{i=1}^n (X_i - \overline{X}_n)^2 \\
$

### Estimación Proporción

$
\text{parámetro de interés: } p = \operatorname{P}(X=1) \\
\text{muestra aleatoria: } X_1, \dots, X_n \sim f \text{, i.i.d}\\
\text{estimador: } \hat{p}_n = \frac{1}{n} \sum_{i=1}^n X_i \\
\text{estimador consistente: } \overline{X}_{n}\xrightarrow{p} p \text{, por LGN}
$

### Estimación de Probabilidad

$
\text{parámetro de interés: } p = \operatorname{F}(x) = \operatorname{P}(X \leq x) \\
\text{muestra aleatoria: } X_1, \dots, X_n \sim f \text{, i.i.d} \\
\text{definimos } Y_i \sim \operatorname{Bernoulli}(p) \\
Y_i = X_i \leq x = \{1 \text{ si } X_i \leq x \text{, } 0 \text{ si } X_i > x \\
\text{estimador: } \hat{F}_n(x) = \overline{Y}_{n} = \frac{1}{n} \sum_{i=1}^n \mathbb{1}_{X_i \leq x} \\
\text{estimador consistente: }\hat{F}_n(x) = \overline{Y}_{n} \xrightarrow{p} \operatorname{F}(x)
$

## Formulas Consistencia

### Sesgo

$\operatorname{Sesgo}(\hat{\theta}_n) = \operatorname{E}(\hat{\theta}_n) - \theta \\
$

Si $\operatorname{Sesgo}(\hat{\theta}_n) = 0 \implies
    \operatorname{E}(\hat{\theta}_n) = \theta$
entonces $\hat{\theta}_n$ es insesgado.

#### Asintóticamente Insesgado

$
    \operatorname{Sesgo}(\hat{\theta}_n) = \operatorname{E}(\hat{\theta}_n) - \theta \xrightarrow{p} 0
$

### Error Estándar

$
    \operatorname{SE}(\hat{\theta}_n) = \sqrt{\operatorname{Var}(\hat{\theta}_n)}\\
    \operatorname{Var}(\hat{\theta}_n) = \operatorname{E}[(\hat{\theta}_n - \operatorname{E}(\hat{\theta}_n))^2]
$

### Error Cuadrático Medio

$
    \operatorname{ECME}(\hat{\theta}_n) = \operatorname{Sesgo}(\hat{\theta}_n)^2 + \operatorname{Var}(\hat{\theta}_n) \\
    \operatorname{ECME}(\hat{\theta}_n) = \operatorname{E}[(\hat{\theta}_n - \theta)^2]
$

## Desigualdad de Chebyshev

$
    \operatorname{P}(|X - \mu| \geq \epsilon) \leq \frac{\operatorname{Var}(X)}{\epsilon^2}
$

## Desigualdad de Markov

$
    \operatorname{P}(X > \epsilon) \leq \frac{\operatorname{E}(X)}{\epsilon}
$

## Momentos

### Momentos de una variable aleatoria

#### Discreta

$
    m_{k} = \operatorname{E}(X^{k}) = \sum_{i=1}^{n}{(x_i - \overline{x}) ^ k}
$

#### Continua

$
    m_{k} = \int_{\mathbb{R}} x^k f(x) dx
$

$
    \operatorname{E}(X) = \mu \\
    \operatorname{E}(X^2) = \mu^2 + \sigma^2 \\
    \operatorname{E}(X^3) = \mu^3 + 3\mu\sigma^2 \\
    \operatorname{E}(X^4) = \mu^4 + 6\mu^2\sigma^2 + 3\sigma^4
$

## Estimación por Máxima Verosimilitud (Likelihood)

$
    \mathcal{L}(\theta; \underline{X}) = \prod_{i=1}^n f(\theta; x_i)
$

### Log-likelihood

$
    \mathcal{l}(\theta; \underline{X}) = \ln(\mathcal{L}(\theta; \underline{X})) = \sum_{i=1}^n \ln(f(\theta; x_i))
$

$
    \frac{d\mathcal{l}(\theta; \underline{X})}{d\theta} = \frac{d\ln(\mathcal{L}(\theta; \underline{X}))}{d\theta} = \sum_{i=1}^n \frac{d\ln(f(\theta; x_i))}{d\theta} = 0
$

## Intervalos de Confianza

### Intervalo de Confianza para $\mu$

Sea la Variable Aleatoria $X_i \sim \operatorname{N}(\mu, \sigma^2)$, nuestro parámetro de interés es $\mu$.
$\overline{X}_n \sim \operatorname{N}(\mu, \sigma^2/n)$.
Si $\sigma^2$ es conocido, entonces $\overline{X}_n$ es insesgado y su varianza es $\sigma^2/n$.

Sea $Z = \frac{\overline{X}_{n} - \mu}{\sigma/\sqrt{n}} \sim \operatorname{N}(0, 1)$, $\hat{\mu}_n = \overline{X}_{n} $

El intervalo de confianza $1-\alpha$ es:

$
    \operatorname{P}(-z \leq Z \leq z) = 1 - \alpha \\
    \phi(z) =  \operatorname{P}(Z \leq z) = 1 - \alpha/2 \\
    \operatorname{P}(-z_{\alpha/2} \leq \frac{\overline{X}_{n} - \mu}{\sigma/\sqrt{n}} \leq z_{\alpha/2}) = 1 - \alpha \\
    P(\hat{\mu}_n - z_{\alpha/2} \frac{\hat{\sigma}}{\sqrt{n}} \leq \mu \leq \hat{\mu}_n + z_{\alpha/2} \frac{\hat{\sigma}}{\sqrt{n}}) = 1 - \alpha \\
    \text{IC = }(\hat{\mu}_n - z_{\alpha/2} \frac{\hat{\sigma}}{\sqrt{n}} \text{, } \hat{\mu}_n + z_{\alpha/2} \frac{\hat{\sigma}}{\sqrt{n}}) \\
    \overline{X}_{n} \pm z_{\alpha/2} \frac{\hat{\sigma}}{\sqrt{n}}
$

### T-Student

Si $\sigma^2$ es desconocido, entonces $\overline{X}_n$ es insesgado y su varianza es $s^2/n$

Sea $T = \frac{\overline{X}_{n} - \mu}{\sqrt{\frac{s^2}{n}}} = \frac{\overline{X}_{n} - \mu}{s/\sqrt{n}} \sim \operatorname{t}_{n-1}$, $\hat{\mu}_n = \overline{X}_{n} $

El intervalo de confianza $1-\alpha$ es:

$
    \operatorname{P}(-t_{n-1,\alpha/2} \leq T \leq t_{n-1,\alpha/2}) = 1 - \alpha \\
    \operatorname{P}(\hat{\mu}_n - t_{n-1,\alpha/2} \sqrt{\frac{s^2}{n}} \leq \mu \leq \hat{\mu}_n + t_{n-1,\alpha/2} \sqrt{\frac{s^2}{n}}) = 1 - \alpha \\
    \operatorname{P}(\hat{\mu}_n - t_{n-1,\alpha/2} \frac{s}{\sqrt{n}} \leq \mu \leq \hat{\mu}_n + t_{n-1,\alpha/2} \frac{s}{\sqrt{n}}) = 1 - \alpha \\
    \text{IC = }(\hat{\mu}_n - t_{n-1,\alpha/2} \frac{s}{\sqrt{n}} \text{, } \hat{\mu}_n + t_{n-1,\alpha/2} \frac{s}{\sqrt{n}}) \\
    \overline{X}_{n} \pm t_{n-1,\alpha/2} \frac{s}{\sqrt{n}}
$