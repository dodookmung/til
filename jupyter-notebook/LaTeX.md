# LaTeX

LaTeX(/ˈleɪtɛk/ 레이텍 또는 라텍)은 문서 작성 도구로, 
여러 분야의 과학 문서를 전달하고 출판하기 위해 학계 에서 널리 사용된다.<br>
마크다운에서 LaTeX 문법을 사용하면 수식 표현을 할 수 있다.

<br>

## 왼쪽 정렬(기본)

```$```로 수식의 앞 뒤를 감싸면 되며, 일반 문장 사이에 수식을 넣는 것도 가능하다.

```
$y = Wx + b$

입력(x)과 출력(y)은 $y = Wx + b$의 형태로 나타낼 수 있음
```

$y = Wx + b$

입력(x)과 출력(y)은 $y = Wx + b$의 형태로 나타낼 수 있음

## 중앙 정렬

```$$``` 사이에 수식을 넣으면 중앙 정렬이 된다.

반드시 여는 ```$$```와 닫는 ```$$```이 있어야 하며, 방식은 ```$```와 동일하다.
```
$$
y = Wx + b$$

$$y = Wx + b
$$

$$
y = Wx + b
$$
```

$$
y = Wx + b$$

$$y = Wx + b
$$

$$
y = Wx + b
$$

## 수식 내에서의 줄 바꿈

```\\```를 입력하여 줄 바꿈을 할 수 있다.

```
$
x + y = 3 \\
-x + 3y = 2
$
```

$
x + y = 3 \\
-x + 3y = 2
$

## 수식 내에서의 띄어쓰기

수식 안에서 띄어쓰기를 해도 적용되지 않으며, 다음과 같은 심볼을 사용해야 한다.

```
$local minimum$(띄어쓰기 적용 X)
$local\,minimum$(띄어쓰기 한 번)
$local\;minimum$(띄어쓰기 두 번)
$local\quad minimum$(띄어쓰기 네 번)
```

$local minimum$

$local\,minimum$

$local\;minimum$

$local\quad minimum$

## 곱셈 기호

```
y = A \times x + B
```

$y = A \times x + B$

## 첨자

윗 첨자는 ```^```기호로, 아랫 첨자는 ```_```기호로 적는다. <br>
오른쪽의 한 글자가 자동으로 첨자로 들어가게 되고, 두 글자 이상을 적용하려면 ```{ }```(중괄호)로 감싸면 된다.

```
$$a_1, a^2, a_1^2$$

$$y_i=x_i^3+x_{i-1}^2+x_{i-2}$$
```

$$a_1, a^2, a_1^2$$

$$y_i=x_i^3+x_{i-1}^2+x_{i-2}$$

## 분수 표기법

분수 표기법에는 두 가지 방법이 있다.

1. ```\over```를 사용하면 \over를 기준으로 왼쪽에 있는 수식은 모두 분자, 오른쪽에 있는 수식은 모두 분모로 들어가게 된다.<br>
2. ```\frac```을 사용하게 되면 첫 번째 문자는 분자, 두 번째 문자는 분모로 들어가게 된다. 두 문자 이상이라면 
중괄호 ```{ }```를 통하여 묶어주면 된다.

```
$$s^2+2s+s\over s+\sqrt s+1$$

$$\frac{1+s}{s(s+2)}$$
```

$$s^2+2s+s\over s+\sqrt s+1$$

$$\frac{1+s}{s(s+2)}$$

## 절대값 표기법

일반적으로 절대값을 표기할 때는 ```|```문자를 사용하게 된다.<br>
하지만 이렇게 하면 분수와 같이 큰 객체에 맞게 resizable한 기호를 사용할 수 없다.<br>
그럴 땐 ```\vert```와 ```\left```, ```\right```를 통하여 좌우 기호를 명시해주면 된다.

```
$$\vert x \vert$$

$4\left\lvert \frac{s^2+1}{s^3+2s^2+3s+1} \right\rvert$$
```

$$\vert x \vert$$

$$\left\lvert \frac{s^2+1}{s^3+2s^2+3s+1} \right\rvert$$

# sin, log와 같은 기호를 세워서 표기

단어 앞에 ```\```를 붙이게 되면 텍스트 모드로 쓸 수 있다.<br>
Markdown에서 명시 되어 있지 않은 수학 단어라면 오류가 발생한다.

```
$$log_{10}{(x+1)}$$
$$asin(bx+c)$$

$$\log_{10}{(x+1)}$$
$$a\sin(bx+c)$$
```
$$log_{10}{(x+1)}$$

$$asin(bx+c)$$

<br>

$$\log_{10}{(x+1)}$$

$$a\sin(bx+c)$$

## 극한/시그마 표기법

그냥 ```\sum```과 ```\lim``` 심볼을 사용하게 되면 다음과 같이 linear하게 표기 된다.

```
$\lim_{s\rarr\infin}{s^2}$
$\sum_{i=0}^{\infin}{(y_i-t_i)^2}$
```

이럴 땐 ```\displaystyle```을 명시하면 정상적으로 표시된다. 
기본적인 linear 형태는 ```\textstyle```을 명시하면 된다.

$\displaystyle\lim_{s\rarr\infin}{s^2}$
$\displaystyle\sum_{i=0}^{\infin}{(y_i-t_i)^2}$

## 벡터 표기법

```\vec```을 사용하거나 ```overrightarrow``` 심볼을 사용하면 화살표가 조금 더 크게 출력된다.

```
$\vec{a}$

$\overrightarrow{a}$
```

$\vec{a}$

$\overrightarrow{a}$

## 행렬 표기법

```matrix``` 심볼을 통하여<br>
```&```로 열을 구분하고, ```\\```로 행을 구분한다.

```
$$\begin{matrix}1&2\\3&4\\ \end{matrix}$$
$$\begin{pmatrix}1&2\\3&4\\ \end{pmatrix}$$
$$\begin{bmatrix}1&2\\3&4\\ \end{bmatrix}$$
$$\begin{Bmatrix}1&2\\3&4\\ \end{Bmatrix}$$
$$\begin{vmatrix}1&2\\3&4\\ \end{vmatrix}$$
$$\begin{Vmatrix}1&2\\3&4\\ \end{Vmatrix}$$
```

$$\begin{matrix}1&2\\3&4\\ \end{matrix}$$

$$\begin{pmatrix}1&2\\3&4\\ \end{pmatrix}$$

$$\begin{bmatrix}1&2\\3&4\\ \end{bmatrix}$$

$$\begin{Bmatrix}1&2\\3&4\\ \end{Bmatrix}$$

$$\begin{vmatrix}1&2\\3&4\\ \end{vmatrix}$$

$$\begin{Vmatrix}1&2\\3&4\\ \end{Vmatrix}$$

## 조각 함수와 같은 cases 표기법

```cases``` 심볼을 사용하여 연립 방정식을 작성할 수 있다.

```
$
x=
\begin{cases}
-x,\;if\;x<0\\
+x,\;if\;x\geq0
\end{cases}
$
```

$x=
\begin{cases}
-x,\;if\;x<0\\
+x,\;if\;x\geq0
\end{cases}$

# 기호

## 화살표

```
$\larr$
$\rarr$ or $\to$
```

$\larr$

$\rarr$

## 부등호 및 유사 등호

```\coloneq``` 기호는 원래 줄이 하나가 아닌 두 개로 표시된다.

|심볼|기호|심볼|기호|
|-|:-:|-|:-:|
|```$\gt$```|>|```$\lt$```|<|
|```$\geq$```|≥|```$\leq$```|≤|
|```$\approx$```|≈|```$\sim$```|∼|
|```$\cong$```|≅|```$\approxeq$```|≊|
|```$\simeq$```|≃|```$\eqsim$```|≂|
|```$\doteq$```|≐|		
|```$\coloneq$```|:−|```$\eqcolon$```|−:|
|```$\fallingdotseq$```|≒|```$\risingdotseq$```|≓|
|```$\pm$```|±|```$\mp$```|∓|

## 점

|이름|마크다운|기호|
|-|-|-|
|점 문자|```$\dot{a}$```|$\dot{a}$|
|중간 점|```$\cdot$```|⋅abc|
|콜론|```$\colon$```|:abc|
|하단 점|```$\ldotp$```|.abc|
|말줄임표|```$\cdots$```|⋯abc|
|대각 말줄임표|```$\ddots$```|⋱abc|
|수직 말줄임표|```$\vdots$```|⋮abc|
|하단 말줄임표|```$ldots$```|…abc|
|왜냐하면|```$\because$```|∵abc|
|그러므로|```$\therefore$```|∴abc|

## 단위 기호

|이름|마크다운|기호|
|-|-|-|
|도|$\degree$|°|
|옴|$\Omega$|Ω|