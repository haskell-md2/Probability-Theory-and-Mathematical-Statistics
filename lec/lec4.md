<span style="color: red;">Статья незаконченна и всё ещё дополняется</span>

# Лекция 4, 23.09.2025*

>*Петропавлы осенние (день Святителей Петра и Павела). С этого дня «солнце умирает», тьма подбирается к людям, а во тьме обитают чудовища. На Петропавлов день крестьяне развешивали веткаи рябины, чтобы отгонять нечисть: заложных мертвецов, леших и ведьм. 

Эта лекция будет содержать довольно много формальной математической теории, которая понадобится нам в будущем. Начнем мы с обсуждения вопроса о построении вероятностного пространства, если нам дано только множество $\Omega$.

## Как построить вероятностное пространство на данном множестве $\Omega$?
Ответ на этот вопрос будет зависеть от самого множества $\Omega$.

**I**. Рассмотрим первый случай: множество $\Omega $ - конечно. Тогда пусть оно состоит из $n$ элементов: 
$$|\Omega| = n$$ 
Чтобы построить вероятностное пространство надо задать $\sigma$-алгебру $\mathcal{A}$ и вероятностную меру $\mathbb{P}$:

* В качестве $\sigma$-алгебры $\mathcal{A}$ можно взять булеан множества $\Omega$:
$$\mathcal{A} = \mathcal{F}_{\text{max}}=2^\Omega$$
* Вероятностную меру $\mathbb{P}$ можно задать только на элементарных исходах:
$$\mathbb{P} (\{\omega_j\} ) = p_j,\ \sum\limits_{j=1}^{n} p_j = 1 $$ 

**II**. Что делать, если $\Omega$ - бесконечное и к тому же не дискретное множество? 

Понятно, что в качестве $\mathcal{A}$ можно также взять булеан $\mathcal{F}_{\text{max}}$. Но тогда не всегда ясно как определить меру. Вообще, этот вариант универсален, но совсем не всегда он хорош. Поэтому булеан не используют на практике. А что обычно используют мы и будем обсуждать на этой лекции.   

## Тогда я позволю себе – просто 30 секунд или одну минуту – маленькую Математическую справку дать. Вы не против?

Начнем с рассмотрения нескольких технических утверждений. В дальнейшем они потребуются нам для ответа на вопрос этой лекции. Отметим, что не все эти утверждения мы будем доказывать, потому что такой материал выходит за границы данного курса. Большая часть результатов относится к Теории Меры и доказывается в соответствующих источниках. Читатели могут обратиться к учебнику Ширяева и узнать интересующие их доказательства. 

> Теорема

Пусть $\Omega$ - множество, $\mathcal{A}$ - алгебра, $\mathbb{P}$ - (конечно) аддитивная мера, $\mathbb{P}(\Omega) = 1$. Тогда следующие утверждения  эквивалентны: 

1. $\mathbb{P}$ - $\sigma$-аддитивна
2. $\mathbb{P}$ - непрерывна сверху: 
    $$A_n \subset A_{n+1}\ \ \& \ \ \bigcup_{n = 1 }^\infty  A_n \in \mathcal{A} \ \Longrightarrow \ \mathbb{P}\left(\bigcup_{n = 1 }^\infty  A_n \right) = \lim\limits_{n\rightarrow \infty } \mathbb{P}(A_n)$$    Заметим, что условие $A_n \subset A_{n+1}$ значит, что последовательность $A_n$ монотонно возрастает: $A_n \nearrow$
3. $\mathbb{P}$ - непрерывна сверху:
    $$A_{n+1} \subset A_{n}\ \ \& \ \ \bigcap_{n = 1 }^\infty  A_n \in \mathcal{A} \ \Longrightarrow \ \mathbb{P}\left(\bigcap_{n = 1 }^\infty  A_n \right) = \lim\limits_{n\rightarrow \infty } \mathbb{P}(A_n)$$
    Аналогично, условие $A_{n+1} \subset A_{n}$ значит, что последовательность $A_n$ монотонно убывает: $A_n \searrow$
4. $\mathbb{P}$ - непрерывна в нуле:
    $$A_{n+1} \subset A_{n}\ \ \& \ \ \bigcap_{n = 1 }^\infty  A_n = \emptyset \ \Longrightarrow \ \lim\limits_{n\rightarrow \infty } \mathbb{P}(A_n) = 0$$ 

> Доказательство 

Будем доказывать кольцом: из первого выведем второе, из второго третье, из третьего четвертое и из четвертого первое.

* $\underline{1\Rightarrow2}:$ $\mathbb{P}$ - $\sigma$-аддитивна мера. Тогда для любой счётной последовательности непересекающихся множеств $B_n$: 
$$ B_i\cap B_j = \emptyset \ (i\neq j) \ \ \& \ \ \bigcup_{n = 1 }^\infty B_n \in \mathcal{A}$$
Будет выполняться свойство аддитивности: 
$$\mathbb{P}\left(\bigcup_{n = 1 }^\infty B_n \right) = \sum\limits_{n = 1 }^\infty  \mathbb{P}(B_n)$$
Рассмотрим произвольную возрастающую последовательность $A_n \nearrow$. По ней построим следующую последовательность $B_n$:
$$B_1 = A_1,\ B_n = A_n\setminus A_{n-1} \ \forall n \geq 2 $$
Последовательность $B_n$ состоит из непересекающихся множеств. С другой стороны:
$$\bigcup_{n = 1 }^\infty  A_n = A_1 \cup (A_2 \setminus A_1) \cup (A_3 \setminus A_2) \cup \ldots = \bigcup_{n = 1 }^\infty  B_n \Rightarrow \bigcup_{n = 1 }^\infty  B_n \in \mathcal{A}$$
Тогда последовательность $B_n$ удовлетворяет условиям $\sigma$-аддитивности. Поэтому имеем:
$$
\mathbb{P}\left(\bigcup_{n = 1 }^\infty  A_n \right) =
\mathbb{P}\left(\bigcup_{n = 1 }^\infty  B_n \right) \xlongequal{\sigma\text{-адд-ть}}
\sum\limits_{n = 1 }^\infty  \mathbb{P}(B_n) = 
$$
$$=
\mathbb{P}(B_1) + \sum_{n=2}^{\infty}\mathbb{P}(B_{n})=
\mathbb{P}(A_1) + \sum_{n=2}^\infty \mathbb{P}(A_{n} \setminus A_{n-1}) \xlongequal{A_{n} \supset A_{n-1}}
$$
$$\xlongequal{A_{n} \supset A_{n-1}}
\mathbb{P}(A_1) + \sum_{n=2}^{\infty}\left(\mathbb{P}(A_{n}) - \mathbb{P}(A_{n-1})\right)=
$$
$$
=
\underbrace{\left[\mathbb{P}(A_1) + \sum_{k=2}^{m}\left(\mathbb{P}(A_{k}) - \mathbb{P}(A_{k-1})\right) \right]}_{=\mathbb{P}(A_m)} + \underbrace{\sum_{k=m+1}^{\infty}\left(\mathbb{P}(A_{k}) - \mathbb{P}(A_{k-1})\right)}_{=\alpha_m\xrightarrow[]{m \to \infty} 0 , \text{ т.к. ряд сходится}} = \mathbb{P}(A_m) + \alpha_m$$
Получили: 
$$\mathbb{P}\left(\bigcup_{n = 1 }^\infty  A_n \right)= \mathbb{P}(A_m) + \alpha_m$$
Тогда, переходя к пределу при $m\to \infty$, имеем:
$$
\boxed{
\mathbb{P}\left(\bigcup_{n = 1 }^\infty  A_n \right)=
\lim\limits_{m \to \infty} \mathbb{P}(A_m)=
\lim\limits_{n \to \infty} \mathbb{P}(A_n)}
$$


* $\underline{2\Rightarrow3}:$ Рассмотрим убывающую последовательность $A_n\searrow$:
$$A_{n+1}\subset A_n \ \Longrightarrow \ \forall j\in \mathbb{N}\ \  A_j \subset A_1 $$
Рассмотрим теперь последовательность $B_1 =A_1\setminus A_n$. Она будет возрастающей:
$$B_n = A_1 \setminus A_n \subset B_{n+1} = A_1 \setminus A_{n+1}$$
Тогда по предположению второго пункта имеем: 
$$\lim\limits_{n\rightarrow \infty } \mathbb{P}(A_1\setminus A_n) = \mathbb{P}\left(\bigcup_{n = 1 }^\infty  (A_1\setminus A_n) \right) $$
Теперь преобразуем: 
$$
\lim\limits_{n\rightarrow \infty } \mathbb{P}(A_1\setminus A_n) = 
\mathbb{P}\left(\bigcup_{n = 1 }^\infty  (A_1\setminus A_n) \right) =
\mathbb{P}\left(A_1 \setminus \bigcap_{n = 1 }^\infty  A_n \right)
\xRightarrow{A_{1} \supset A_{j}}
$$
$$
\xRightarrow{A_{1} \supset A_{j}}
\lim\limits_{n\rightarrow \infty } (\mathbb{P}(A_1) -  \mathbb{P}(A_n)) = \mathbb{P}(A_1 ) -  \mathbb{P}\left(\bigcap_{n = 1 }^\infty  A_n \right)
\Rightarrow
$$
$$
\Rightarrow 
\mathbb{P}(A_1) - \lim\limits_{n\rightarrow \infty } \mathbb{P}(A_n) = \mathbb{P}(A_1 ) -  \mathbb{P}\left(\bigcap_{n = 1 }^\infty  A_n \right)
\Rightarrow 
$$
$$
\Rightarrow 
\boxed{\lim\limits_{n\rightarrow \infty } \mathbb{P}(A_n) =\mathbb{P}\left(\bigcap_{n = 1 }^\infty  A_n \right)}
$$

* $\underline{3\Rightarrow4}:$ Заметим, что $4$ - это частный случай $3$, если пересечение $\bigcap\limits_{n = 1 }^\infty  A_n$ - пусто.

* $\underline{4\Rightarrow1}:$ Рассмотрим последовательность непересекающихся множеств $\{A_j\}_{j=1}^{\infty}$, объединение которых не выходит за пределы $\mathcal{A}$:
$$A_i \cap A_j = \emptyset\ (i\neq j) \ \ \& \ \  \bigcup_{j=1}^\infty A_j \subset \mathcal{A} $$
Рассмотрим объединение этих множеств. Его можно представить в виде: 
$$\bigcup_{n = 1 }^\infty  A_n = \left( \bigcup_{j = 1 }^n  A_j \right) \cup \left( \bigcup_{j = n+1 }^\infty  A_j \right)$$
В качестве последовательности $B_n$ рассмотрим хвосты этого объединения: 
$$B_n = \bigcup_{j = n }^\infty  A_j$$
Эта последовательность удовлетворяет условиям 4-го пункта: 
$$B_{n+1 } =  \bigcup_{j = n+1 }^\infty  A_j \subset B_n=  \bigcup_{j = n }^\infty A_j \ \ \& \ \ \bigcap_{n = 1}^\infty  B_n = \bigcap_{n = 1}^\infty \left(\bigcup_{j = n }^\infty A_j \right) = \emptyset, \ \text{т.к. } A_i\cap A_j = \emptyset$$
Тогда по 4-ому пункту:
$$\lim\limits_{n\rightarrow \infty } \mathbb{P}(B_n) = \lim\limits_{n\rightarrow \infty } \mathbb{P}\left( \bigcup_{j = n }^\infty  A_j\right)  = 0$$
Теперь вернемся к доказательству $\sigma$-аддитивности. Мы хотим показать, что:
$$\sum\limits_{n = 1 }^\infty  \mathbb{P}(A_n) = \mathbb{P}\left(\bigcup_{n = 1 }^\infty  A_n \right) $$
Но $\mathbb{P}$ - это конечно аддитивная мера, тогда:
$$\sum_{j=1}^n \mathbb{P}(A_j) = \mathbb{P}\left( \bigcup_{j=1}^n A_j\right) $$
Значит, имеем:
$$\sum\limits_{n = 1 }^\infty  \mathbb{P}(A_n) =
\lim\limits_{n\to \infty } \left(\sum\limits_{j = 1 }^n  \mathbb{P}(A_j) \right)  \xlongequal{\text{конеч. адд.}}
\lim\limits_{n\to \infty } \left(\mathbb{P}\left(\bigcup_{j = 1 }^n  A_j \right) \right) = $$
$$=
\lim\limits_{n\to \infty } \left(\mathbb{P}\left(\bigcup_{j = 1 }^\infty   A_j \setminus \bigcup_{j = n+1}^\infty A_j \right) \right)  \xlongequal{B_1 \supset B_{n+1}}
\lim\limits_{n\to \infty } \left(\mathbb{P}\left(\bigcup_{j = 1 }^\infty   A_j \right) - \underbrace{\mathbb{P}\left( \bigcup_{j = n+1}^\infty A_j \right)}_{=\mathbb{P}(B_{n+1})\xrightarrow{n\to \infty}0} \right)=$$
$$=
\lim\limits_{n\to \infty } \left(\mathbb{P}\left(\bigcup_{j = 1 }^\infty   A_j \right)  \right) = 
\mathbb{P}\left(\bigcup_{n = 1 }^\infty   A_n \right) 
$$
Получили:
$$\boxed{
\sum\limits_{n = 1 }^\infty  \mathbb{P}(A_n) = 
\mathbb{P}\left(\bigcup_{n = 1 }^\infty   A_n \right) }
$$

### Леммы 

> Лемма 1

Пусть $\varepsilon$ - система подмножеств в $\Omega$. Тогда существует наименьшая $\sigma$-алгебра $\sigma(\varepsilon)$, которая содержит $\varepsilon$: $\sigma(\varepsilon) \supset \varepsilon$ 

> Объяснение 

Такие $\sigma$-алгебры существуют, так как всегда можно привести булеан $\mathcal{F}_\text{max}$. Тогда можно взять и минимальную $\sigma$-алгебру, которая содержит $\varepsilon$.

> Пример 

$A$ - успех, $\overline{A}$ - неудача. Пусть $\varepsilon = \{ A,\ \overline{A}\}$, тогда $\sigma(\varepsilon) = \{\emptyset,\ A,\ \overline{A},\ \Omega\}$.

> Определение  

$M$ - система подмножеств в $\Omega$. $M$ - является монотонным классом, если:
* $A_n\in M,\ A_n\nearrow A\ \Longrightarrow A \in M$
* $A_n\in M,\ A_n\searrow A\ \Longrightarrow A \in M$


> Лемма 2

Алгебра $\mathcal{A}$ - является $\sigma$-алгеброй $\Longleftrightarrow$ $\mathcal{A}$ - является монотонным классом. 

> Доказательство 

* $\underline{\Longrightarrow}:$ По определению $\sigma$-алгебры
* $\underline{\Longleftarrow}:$ Рассмотрим последовательность $A_n\in \mathcal{A}$. По ней построим новую последовательность $B_n$:
$$B_n = \bigcup_{i=1}^n A_i$$ 
Заметим, что:
$$B_n \subset B_{n+1}$$
Тогда последовательность $B_n$ сходится к своему объединению: 
$$B_n\nearrow \bigcup\limits_{i=1}^\infty A_i$$
Но $\mathcal{A}$ - это монотонный класс, тогда он содержит пределы всех монотонных последовательностей с элементами из него самого: 
$$B_n \in \mathcal{A} \Longrightarrow \bigcup\limits_{i=1}^\infty A_i \in \mathcal{A}$$


> Замечание

По любой алгебре $\mathcal{A}$ можно построить монотонный класс $M$, просто пополнив множество $\mathcal{A}$ всеми пределами монотонных последовательностей. Мы будем обозначать такой монотонный класс, полученный из алгебры $\mathcal{A}$, следующим образом: $M(\mathcal{A})$.

> Теорема 

Для любой алгебры $\mathcal{A}$ выполняется равенство: 
$$\sigma(\mathcal{A}) = M (\mathcal{A})$$

> Определение 

$\pi$-система множеств в $\Omega$ - это система подмножеств $\Omega$ замкнутая относительно операции конечного пересечения.

> Определение 

$\lambda$-система множеств в $\Omega$ - это система подмножеств $\Omega$, удовлетворяющая свойствам:
1. $\Omega \in \lambda $
2. $A, B  \in \lambda \ \Rightarrow \ B\setminus A \in \lambda$
3. $A_n \in \lambda, A_n \nearrow A \ \Rightarrow \ A \in \lambda$

> Теорема 

Любая $\pi,\lambda$-система является $\sigma$-алгеброй. 

> Лемма 3 

Пусть $P$ и $Q$ - это две вероятностные меры на вероятностном пространстве $(\Omega,\ \mathcal{A})$, пусть $\varepsilon$ - это $\pi$-система. Тогда: 
$$
\left. P \right|_{\varepsilon} = \left. Q \right|_{\varepsilon} 
\Longrightarrow
\left. P \right|_{\sigma(\varepsilon)} = \left. Q \right|_{\sigma(\varepsilon)}
$$

> Замечание 

Эта теорема является теоремой единственности для меры, заданной на $\varepsilon$. То есть, если меры совпадают на малом множестве $\varepsilon$, то они совпадут и на $\sigma(\varepsilon)$ - минимальной $\sigma$-алгебре, содержащей $\varepsilon$.

> Замечание

Если же множество $\varepsilon$ окажется алгеброй $\mathcal{A}$, то мы сможем заменить минимальную $\sigma$-алгебру $\sigma(\mathcal{A})$ на монотонный класс $M(\mathcal{A})$:

$$
\left. P \right|_{\mathcal{A}} = \left. Q \right|_{\mathcal{A}} 
\Longrightarrow
\left. P \right|_{M(\mathcal{A})} = \left. Q \right|_{M(\mathcal{A})}
$$