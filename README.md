# Useful and efficient algorithms for secp256k1 elliptic curve

<p>In this article, we will consider several useful and efficient algorithms for an elliptic curve&nbsp;&nbsp;<strong><em>E</em></strong>&nbsp;&nbsp;over a field&nbsp;&nbsp;<strong><em>GF(p)</em></strong>&nbsp;&nbsp;given by the short Weierstrass equation</p>
<p><code>у^2&nbsp;= х^3&nbsp;+ Ах + В</code></p>
<ul>
<li>&nbsp;<strong>Algorithm for generating a point on curve&nbsp;&nbsp;<em>E</em></strong></li>
<li>&nbsp;<strong>Algorithm for adding points</strong></li>
<li>&nbsp;<strong>Doubling Point Algorithm</strong></li>
<li>&nbsp;<strong>Algorithm for finding an integer multiple point</strong></li>
<li>&nbsp;<strong>Algorithm for finding an integer multiple point (scalar multiplication)</strong></li>
<li>&nbsp;<strong>Algorithm for constructing a divisor&nbsp;&nbsp;<em>D</em>&nbsp;&nbsp;over a curve&nbsp;&nbsp;<em>E</em>&nbsp;&nbsp;with support&nbsp;&nbsp;<em>supp(D)</em>&nbsp;&nbsp;of a given size&nbsp;&nbsp;<em>d</em></strong></li>
<li>&nbsp;<strong>Miller’s algorithm for calculating the value of the Weyl function&nbsp;&nbsp;<em>f&nbsp;&nbsp;<sub>n, P</sub></em>&nbsp;&nbsp;from a divisor&nbsp;&nbsp;<em>D</em>&nbsp;&nbsp;such that&nbsp;&nbsp;</strong><em>supp(D)</em>&nbsp;&nbsp;∩ {P, O} = ∅</li>
<li>&nbsp;<strong>Pairing&nbsp;</strong>&nbsp;<em>Weil</em></li>
</ul>
<h4>Modular operations (integers) on a finite field (or Galois field)</h4>
<ol>
<li><em>x mod n</em>&nbsp;&nbsp;means «the remainder of n after dividing x».&nbsp;In other words, if&nbsp;&nbsp;<em>x = an + b</em>&nbsp;&nbsp;and a, b ∈ integer, and also 0 ≤ b ≤ n − 1, then&nbsp;&nbsp;<em>x mod n = b</em>&nbsp;&nbsp;.</li>
<li><strong>Reverse</strong>&nbsp;&nbsp;: if&nbsp;&nbsp;<em>ax = 1 mod n</em>&nbsp;&nbsp;, then&nbsp;&nbsp;<em>a</em>&nbsp;&nbsp;is the reciprocal of&nbsp;&nbsp;<em>x mod n</em>&nbsp;&nbsp;.&nbsp;There are two popular&nbsp;&nbsp;<em>solution</em>&nbsp;methods &nbsp;: •&nbsp;&nbsp;<strong><em>Method 1</em></strong>&nbsp;&nbsp;: Try each value for&nbsp;&nbsp;<em>a &lt; n as</em>&nbsp;&nbsp;long as&nbsp;&nbsp;<em>xa mod n = 1</em>&nbsp;&nbsp;.•&nbsp;&nbsp;<strong><em>Method 2</em></strong>&nbsp;&nbsp;: Euclidean method which is usually used to solve the inverse problem of large integers, so it is recommended to use method 1 to solve inverse problem of small integers.</li>
</ol>
<h4>Elliptic Curve Point Operation</h4>
<p>The point&nbsp;&nbsp;<em>P(x&nbsp;&nbsp;<sub>0</sub>&nbsp;&nbsp;, y&nbsp;&nbsp;<sub>0</sub>&nbsp;&nbsp;)</em>&nbsp;&nbsp;on the elliptic curve&nbsp;&nbsp;<em>E</em>&nbsp;&nbsp;means: its coordinates&nbsp;&nbsp;<em>x&nbsp;&nbsp;<sub>0</sub></em>&nbsp;&nbsp;and&nbsp;&nbsp;<em>y&nbsp;&nbsp;<sub>0</sub></em>&nbsp;&nbsp;are elements of the field, and the coordinates&nbsp;&nbsp;<em>x&nbsp;&nbsp;<sub>0</sub></em>&nbsp;&nbsp;and&nbsp;&nbsp;<em>y&nbsp;&nbsp;<sub>0</sub></em>&nbsp;&nbsp;satisfy the equation.</p>
<ol>
<li><strong>Adding points on an elliptic curve</strong>&nbsp;&nbsp;: Let&nbsp;&nbsp;<em>P, Q</em>&nbsp;&nbsp;and&nbsp;&nbsp;<em>R</em>&nbsp;&nbsp;be three points on an elliptic curve.&nbsp;Adding points P + Q = R.</li>
<li><strong>Doubling points on an elliptic curve</strong>&nbsp;&nbsp;: Let&nbsp;&nbsp;<em>P, Q</em>&nbsp;&nbsp;be two points on an elliptic curve.&nbsp;Doubling Points P + P = 2P = Q</li>
<li><strong>Dot multiplication</strong>&nbsp;&nbsp;: let&nbsp;&nbsp;<em>P</em>&nbsp;&nbsp;be a point on the curve&nbsp;&nbsp;<em>E</em>&nbsp;&nbsp;, defined in the equation
<ul>
<li>Dot multiplication&nbsp;&nbsp;<em>nP</em>&nbsp;&nbsp;is defined as&nbsp;&nbsp;<em>nP = P + P + P + … + P</em>&nbsp;&nbsp;(&nbsp;&nbsp;<em>n</em>&nbsp;&nbsp;times), where&nbsp;&nbsp;<em>n</em>&nbsp;&nbsp;is an integer;&nbsp;<em>nP</em>&nbsp;&nbsp;is also a point on the same&nbsp;&nbsp;<em>E</em>&nbsp;curve &nbsp;.</li>
<li>The minimal natural number a with&nbsp;&nbsp;<em>aP = O</em>&nbsp;&nbsp;is called&nbsp; the&nbsp;<strong>order&nbsp; of&nbsp;<em>P</em></strong>&nbsp;&nbsp;.</li>
<li>Dot multiplication is widely required in elliptic curve cryptosystems.</li>
</ul>
</li>
</ol>
<h4>Divider</h4>
<p><strong>Divisor</strong>&nbsp;&nbsp;(Divisor)&nbsp;&nbsp;<em>D</em>&nbsp;&nbsp;on a curve&nbsp;&nbsp;<em>E</em>&nbsp;&nbsp;is a convenient way to denote a&nbsp;&nbsp;<strong>multiset of points on&nbsp;&nbsp;<em>E</em></strong>&nbsp;&nbsp;, written as a formal sum</p>
<figure class="wp-block-image"><img title="" src="./Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»_files/0b13e2fbec01a2ea5635bbcb1a36ade1.png" alt="Useful and efficient algorithms for secp256k1 elliptic curve"></figure>
<ul>
<li>The set of all divisors on&nbsp;&nbsp;<em>E</em>&nbsp;&nbsp;is denoted&nbsp; by&nbsp;<em>Div&nbsp;&nbsp;<sub>F q</sub>&nbsp;&nbsp;(E)</em>&nbsp;&nbsp;and forms a group in which the addition of divisors is natural.</li>
<li>Zero Divisor: This is the divisor for all n&nbsp;&nbsp;<sub>P</sub>&nbsp;&nbsp;= 0, the zero divisor is&nbsp;&nbsp;<em>0 ∈ Div&nbsp;&nbsp;<sub>F q</sub>&nbsp;&nbsp;(E)</em>&nbsp;&nbsp;.</li>
<li>If the field&nbsp;&nbsp;<em>F&nbsp;&nbsp;<sub>q</sub></em>&nbsp;&nbsp;is not specific, it can be omitted and simply written as&nbsp;&nbsp;<em>Div(E)</em>&nbsp;&nbsp;to denote the divisor group.</li>
</ul>
<h4>Function f divided by E</h4>
<p>The divisor of a function&nbsp;&nbsp;<em>f</em>&nbsp;&nbsp;by&nbsp;&nbsp;<em>E</em>&nbsp;&nbsp;is used to denote the intersection points (and their multiplicities) of the functions&nbsp;&nbsp;<em>f</em>&nbsp;&nbsp;and&nbsp;&nbsp;<em>E</em>&nbsp;&nbsp;.</p>
<h4>Pairing Weil</h4>
<p>The Weil pairing, which is denoted&nbsp; by&nbsp;<em>e&nbsp;&nbsp;<sub>m</sub></em>&nbsp;&nbsp;, takes as input a pair of points&nbsp;&nbsp;<em>P, Q ∈ E[m] and&nbsp;&nbsp;<sub>produces</sub></em>&nbsp;&nbsp;as output a root _m of unity&nbsp;&nbsp;<em><sup>e&nbsp;&nbsp;<sub>m</sub></sup><sub>&nbsp;(</sub>&nbsp;&nbsp;P , Q)</em>&nbsp;&nbsp;.&nbsp;The bilinearity of the Weyl pairing is expressed by the equations</p>
<p><em>e&nbsp;&nbsp;<sub>m</sub>&nbsp;&nbsp;(P&nbsp;&nbsp;<sub>1</sub>&nbsp;&nbsp;+ P&nbsp;&nbsp;<sub>2</sub>&nbsp;&nbsp;, Q) \u003d e&nbsp;&nbsp;<sub>m</sub>&nbsp;&nbsp;(P&nbsp;&nbsp;<sub>1</sub>&nbsp;&nbsp;, Q) * e&nbsp;&nbsp;<sub>m</sub>&nbsp;&nbsp;(P2, B),</em></p>
<p><em>e&nbsp;&nbsp;<sub>m</sub>&nbsp;&nbsp;(P, Q&nbsp;&nbsp;<sub>1</sub>&nbsp;&nbsp;+ Q&nbsp;&nbsp;<sub>2</sub>&nbsp;&nbsp;) = e&nbsp;&nbsp;<sub>m</sub>&nbsp;&nbsp;(P, Q&nbsp;&nbsp;<sub>1</sub>&nbsp;&nbsp;) * e&nbsp;&nbsp;<sub>m</sub>&nbsp;&nbsp;(P, Q&nbsp;&nbsp;<sub>2</sub>&nbsp;&nbsp;).</em></p>
<p><strong>The Weil&nbsp;</strong>&nbsp;pair&nbsp;&nbsp;<em>P</em>&nbsp;&nbsp;and&nbsp;&nbsp;<em>Q</em>&nbsp;&nbsp;is the number</p>
<figure class="wp-block-image"><img title="" src="./Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»_files/5ebb8530fd881d89d3f396460464af79.png" alt="Useful and efficient algorithms for secp256k1 elliptic curve"></figure>
<p>where&nbsp;&nbsp;<em>S ∈ E</em>&nbsp;&nbsp;is any point satisfying the condition&nbsp;&nbsp;<em>S ∉ {O, P, −Q, P − Q}</em>&nbsp;&nbsp;.&nbsp;(This ensures that all quantities on the right hand side are defined and non-zero.) One can check that the value of&nbsp;&nbsp;<em>e&nbsp;&nbsp;<sub>m</sub>&nbsp;&nbsp;(P,Q)</em>&nbsp;&nbsp;does not depend on the choice of&nbsp;&nbsp;<em>f&nbsp;&nbsp;<sub>P</sub></em>&nbsp;&nbsp;,&nbsp;&nbsp;<em>f&nbsp;&nbsp;<sub>Q</sub></em>&nbsp;&nbsp;and&nbsp;&nbsp;<em>S</em>&nbsp;&nbsp;.</p>
<h4>An Efficient Weil Pairing Computation Algorithm</h4>
<p>Let&nbsp;&nbsp;<em>E</em>&nbsp;&nbsp;be an elliptic curve and let P = (x&nbsp;&nbsp;<sub>P</sub>&nbsp;&nbsp;,y&nbsp;&nbsp;<sub>P</sub>&nbsp;&nbsp;) and Q = (x&nbsp;&nbsp;<sub>Q</sub>&nbsp;&nbsp;, y&nbsp;&nbsp;<sub>Q</sub>&nbsp;&nbsp;) be nonzero points on&nbsp;&nbsp;<em>E</em>&nbsp;&nbsp;.</p>
<p>Let&nbsp;&nbsp;<em>λ</em>&nbsp;&nbsp;be the slope of the line connecting&nbsp;&nbsp;<em>P</em>&nbsp;&nbsp;and&nbsp;&nbsp;<em>Q</em>&nbsp;&nbsp;, or the slope of the tangent to&nbsp;&nbsp;<em>E</em>&nbsp;&nbsp;at P if&nbsp;&nbsp;<em>P =</em>&nbsp;&nbsp;Q. (If the line is vertical, we set&nbsp;&nbsp;<em>λ</em>&nbsp;&nbsp;= ∞.) Define a function g&nbsp;&nbsp;<sub>P, Q</sub>&nbsp;&nbsp;on&nbsp;&nbsp;<em>E</em>&nbsp;&nbsp;as follows:</p>
<figure class="wp-block-image"><img title="" src="./Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»_files/dbc8cdefc33de28911b8e41530a16687.png" alt="Useful and efficient algorithms for secp256k1 elliptic curve"></figure>
<p>then</p>
<p>div(g&nbsp;&nbsp;<sub>P, Q</sub>&nbsp;&nbsp;) = [P] + [Q] — [P + Q] — [&nbsp;&nbsp;<em>O</em>&nbsp;&nbsp;].</p>
<p><strong>Miller’s algorithm</strong></p>
<p>Let&nbsp;&nbsp;<em>m ≥</em>&nbsp;&nbsp;and write the binary extension of&nbsp;&nbsp;<em>m</em>&nbsp;&nbsp;as</p>
<p><em>m \u003d m&nbsp;&nbsp;<sub>0</sub>&nbsp;&nbsp;+ m&nbsp;&nbsp;<sub>1</sub>&nbsp;&nbsp;* 2 + m&nbsp;&nbsp;<sub>2</sub>&nbsp;&nbsp;* 2&nbsp;&nbsp;<sup>2</sup>&nbsp;&nbsp;+ + m&nbsp;&nbsp;<sub>n — 1</sub>&nbsp;&nbsp;2&nbsp;&nbsp;<sup>n — 1</sup></em></p>
<p>for&nbsp;&nbsp;<em>m&nbsp;&nbsp;<sub>i</sub>&nbsp;&nbsp;∈ {0, 1}</em>&nbsp;&nbsp;and&nbsp;&nbsp;<em>m&nbsp;&nbsp;<sub>n — 1</sub>&nbsp;&nbsp;≠ 0</em>&nbsp;&nbsp;.&nbsp;The following algorithm returns a function&nbsp;&nbsp;<em>f&nbsp;&nbsp;<sub>P</sub></em>&nbsp;&nbsp;whose divisor satisfies the condition</p>
<p>div(&nbsp;&nbsp;<em>f&nbsp;&nbsp;<sub>P</sub></em>&nbsp;&nbsp;) =&nbsp;&nbsp;<em>m</em>&nbsp;&nbsp;[&nbsp;&nbsp;<em>P</em>&nbsp;&nbsp;] — [&nbsp;&nbsp;<em>mP</em>&nbsp;&nbsp;] — (&nbsp;&nbsp;<em>m — 1</em>&nbsp;&nbsp;) [&nbsp;&nbsp;<em>O</em>&nbsp;&nbsp;],</p>
<p>where the functions&nbsp;&nbsp;<em>g&nbsp;&nbsp;<sub>T, T</sub></em>&nbsp;&nbsp;and&nbsp;&nbsp;<em>g&nbsp;&nbsp;<sub>T, P</sub></em>&nbsp;&nbsp;used by the algorithm are defined in (a).</p>
<figure class="wp-block-image"><img title="" src="./Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»_files/bc1d75c6060123845b0b7f4b153096b0.png" alt="Useful and efficient algorithms for secp256k1 elliptic curve"></figure>
<p>In particular, if&nbsp;&nbsp;<em>P ∈ E[m]</em>&nbsp;&nbsp;, then div(&nbsp;&nbsp;<em>f&nbsp;&nbsp;<sub>P</sub></em>&nbsp;&nbsp;) =&nbsp;&nbsp;<em>m</em>&nbsp;&nbsp;[&nbsp;&nbsp;<em>P</em>&nbsp;&nbsp;] −&nbsp;&nbsp;<em>m</em>&nbsp;&nbsp;[&nbsp;&nbsp;<em>O</em>&nbsp;&nbsp;].</p>
<h3>Requirement</h3>
<ul>
<li><code>Python 3.5</code></li>
<li><code>numpy</code></li>
</ul>
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/04AlgorithmsForSecp256k/

pip3 install numpy</code></pre>
<pre class="wp-block-code"><code>├── Curves.py             &lt;- Набор данных эллиптических кривых
├── Divisor.py            &lt;- Создать делитель
├── EllipticCurve.py      &lt;- Классы эллиптической кривой и точки на эллиптической кривой
├── EuclideanAlg.py       &lt;- Расширенный алгоритм Евклида
├── Helper.py             &lt;- Вспомогательные функции (обратные биты, мощность по модулю) 
├── Pairing.py            &lt;- Спаривания Вейля, а так же Алгоритм Миллера
├── Tests.py              &lt;- Модульные тесты для функций
├── Tonelli_ShanksAlg.py  &lt;- Алгоритм Тонелли – Шенкса
├── main.py               &lt;- main
</code></pre>
<h3></h3>
<hr class="wp-block-separator has-alpha-channel-opacity">
<p><strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/04AlgorithmsForSecp256k" target="_blank" rel="noreferrer noopener">Source</a></strong></p>
<p><strong>Telegram:&nbsp;&nbsp;<a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">https://t.me/cryptodeeptech</a></strong></p>
<p><strong>Video:&nbsp;&nbsp;<a href="https://youtu.be/gFbiBCNPsFk" target="_blank" rel="noreferrer noopener">https://youtu.be/gFbiBCNPsFk</a></strong></p>
<p><strong>Source: <a href="https://cryptodeeptech.ru/algorithms-for-secp256k">https://cryptodeeptech.ru/algorithms-for-secp256k</a></strong></p>


---


|  | Donation Address |
| --- | --- |
| ♥ __BTC__ | 1Lw2gTnMpxRUNBU85Hg4ruTwnpUPKdf3nV |
| ♥ __ETH__ | 0xaBd66CF90898517573f19184b3297d651f7b90bf |
