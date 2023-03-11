**Nama:** Juan Christian
**NIM:** 2501994771

1. Pada gambar dibawah, sebuah kawat melingkar berbentuk persegi panjang memiliki panjang $a = 2.2 cm$ dan lebar $b = 0.8 cm$, serta hambatan $R = 0.4 m\ohm$. Kawat persegi panjang ini diletakkan di dekat kawat lurus dengan panjang tak hingga yang dialiri arus $i = 4.7 A$. Kawat persegi panjang ini kemudian digerakkan menjauhi kawat lurus dengan kecepatan konstan sebesar $\vec{v} = 3.2 mm/s$. Pusat dari kawat persegi panjang tersebut berada sejauh $r = 1.5b$. Berapa arus induksi yang mengalir pada kawat persegi panjang, dan kemana arahnya?

![[Pasted image 20221219231236.png]]

![[Pasted image 20221219235008.png]]

Dengan menggunakan *Right hand rule*, dapat diketahui bahwa arah arus induksi adalah ***clockwise*** atau **searah jarum jam**.

![[Pasted image 20221219235259.png]]

$$
\begin{align}
\Phi_b &= \int \vec{B}\cdot d\vec{A}=\int_{0}^{a} dy\ \cdot \int_{r-\frac{b}{2}}^{r+\frac{b}{2}} dy\ \cdot B(y) = \frac{\mu_0ia}{2\pi} \int_{r-\frac{b}{2}}^{r+\frac{b}{2}} dy \cdot \frac{1}{y} \\

|\Phi_b| &= \frac{\mu_0ia}{2\pi} \cdot ln \big|\frac{r + \frac{b}{2}}{r-\frac{b}{2}}\big| = \frac{(4\pi \cdot 10^{-7}T\cdot m/A)(4.7A)(0.022m)}{2\pi}ln(2.0) \\

|\Phi_b| &= 1.4 \times 10^{-8}Wb

\end{align}
$$

$$
\begin{align}
I_{loop} &= |\frac{\varepsilon_{ind}}{R}| = -\frac{\mu_0ia}{2\pi}|\frac{d}{dt}ln(\frac{r+\frac{b}{2}}{r-\frac{b}{2}})| \\
&= \frac{\mu_0iabv}{2\pi R[r^2-(b/2)^2]} \\
&= \frac{(4\pi\times10^{-7}T\cdot m/A)(4.7A)(0.022m)(0.0080m)(3.2\times10^{-3}m/s)}{2\pi(4.0\times10^{-4}\ohm)[2(0.0080m)^2]} \\
&= 1.0 \times 10^{-5} A
\end{align}
$$

$\therefore$ Maka, arus induksi pada loop adalah $1.0 \times 10^{-5}A$ dengan arah arus induksi ***clockwise*** atau **searah jarum jam**

2. Pada gambar di bawah ini, terdapat dua buah kawat panjang sejajar $A$ dan $B$ yang terpisah sejauh $0.1m$ yang masing-masing kawat membawa arus sebesar $100 A$. Arah arus di kawat $A$ adalah keluar bidang, dan di kawat $B$ arah arusnya masuk ke dalam bidang. Berapa medan magnet di titik $P$?

![[Pasted image 20221219231246.png]]

![[Pasted image 20221220004009.png]]

$$
\begin{align}
B_A = \frac{\mu_0\cdot I_A}{2\pi d\ \cos\ 45\degree};\ \ \ \ B_B = \frac{\mu_0\cdot I_B}{2\pi d\ \cos\ 45\degree}
\end{align}
$$

Karena masing-masing kawat membawa arus sebesar $100A$ maka $B_A = B_B$

$$
\begin{align}
B_A = B_B &= \frac{\mu_0\cdot I_A}{2\pi d\cos45\degree} \\
&= \frac{4\pi \times 10^{-7} \cdot 100}{2\pi(0.1)\cdot \frac{1}{2}\sqrt{2}} \\
&= \frac{4\cdot 10^{-4}}{\sqrt{2}} \\
&= 2\sqrt{2} \cdot 10^{-4}\ T\ \approx\ 282.842\ \mu T
\end{align}
$$

Lalu untuk mencari medan magnet di titik $P$,

$$
\begin{align}
B &= \sqrt{{B_A}^2 + {B_B}^2} \\
&= \sqrt{(2\sqrt2 \cdot 10^{-4})^2 + (2\sqrt2 \cdot 10^{-4})^2} \\
&= \sqrt{2(2\sqrt2 \cdot 10^{-4})^2} \\
&= \sqrt2 \cdot(2\sqrt2 \cdot 10^{-4}) \\
& = 4\cdot10^{-4}\ T \ \approx\ 400\ \mu T
\end{align}
$$

Untuk mencari sudut antara $\vec{B}$ dan $x$

$$
\begin{align}
\theta &=\tan^{-1}\frac{B_A}{B_B} \\
\theta &=\tan^{-1}\frac{100}{100} \\
\theta &=\tan^{-1}(1) = \arctan(1) \\
\theta &= \arctan(1) = 1 = 45 \degree
\end{align}
$$

Maka sudut antara $\vec{B}$ dan $x$ adalah

$$
\begin{align}
\theta + 45\degree &= 90 \degree \\
45\degree + 45\degree &= 90 \degree
\end{align}
$$

$\therefore$ Maka medan magnet di titik $P$ adalah $4\cdot10^{-4}\ T \ \approx\ 400\ \mu T$ dengan sudut antara $\vec{B}$ dan $x$ yaitu $90 \degree$