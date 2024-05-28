<!-- wp:embed {"url":"https://www.youtube.com/embed/gFbiBCNPsFk","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/gFbiBCNPsFk
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>在本文中，我們將考慮幾種有用且有效的算法，用於&nbsp;在&nbsp;由短 Weierstrass 方程給出的&nbsp;域&nbsp;<strong><em>GF(p)上的橢圓曲線</em></strong><strong><em>E</em></strong><strong><em></em></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>у^2&nbsp;= х^3&nbsp;+ Ах + В</code>&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>&nbsp;<strong><em>生成曲線E</em>上的點的算法&nbsp;<em></em></strong></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>&nbsp;<strong>加分算法</strong></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>&nbsp;<strong>倍增點算法</strong></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>&nbsp;<strong>尋找整數倍點的算法</strong></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>&nbsp;<strong>尋找整數倍點的算法（標量乘法）</strong></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>&nbsp;<strong>&nbsp;在具有給定大小 d 的&nbsp;<em>支持</em>&nbsp;supp&nbsp;&nbsp;<em>(D)的曲線</em><em>E</em>&nbsp;上&nbsp;構造除數&nbsp;<em>D的算法</em><em></em><em></em><em></em></strong></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>&nbsp;<strong>&nbsp;Miller 算法用於從除數&nbsp;<em>D計算 Weil 函數</em><em>f&nbsp;&nbsp;<sub>n, P</sub></em>的值&nbsp;&nbsp;，滿足&nbsp;<em></em></strong><em>supp(D)</em>&nbsp;&nbsp;∩ {P, O} = ∅</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>&nbsp;<strong>配對</strong>&nbsp;<em>威爾</em></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":4} -->
<h4>有限域（或 Galois 域）上的模運算（整數）</h4>
<!-- /wp:heading -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li><em>x mod n</em>&nbsp;表示“除以 x 後的餘數 n”。換言之，如果&nbsp;<em>x = an + b</em>&nbsp;且 a, b ∈ 整數，且 0 ≤ b ≤ n − 1，則&nbsp;<em>x mod n = b</em>&nbsp;&nbsp;。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>反向</strong>&nbsp;：如果&nbsp;<em>ax = 1 mod n</em>&nbsp;&nbsp;，則&nbsp;<em>a是</em><em>x mod n</em>&nbsp;的倒數&nbsp;&nbsp;。<em>有兩種流行的解決</em>方法&nbsp;&nbsp;： •&nbsp;<strong><em>方法一</em></strong>&nbsp;：嘗試&nbsp;<em>a &lt; n</em>的每個值&nbsp;，只要&nbsp;<em>xa mod n = 1。</em>&nbsp;&nbsp;•&nbsp;<strong><em>方法二</em></strong>&nbsp;：歐幾里德方法，通常用於解決大整數的逆問題，因此推薦使用使用方法1解決小整數反問題。</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:heading {"level":4} -->
<h4>橢圓曲線點運算</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>&nbsp;橢圓曲線&nbsp;<em>E</em>上的點&nbsp;<em>P(x&nbsp;&nbsp;<sub>0</sub>&nbsp;&nbsp;,y&nbsp;&nbsp;<sub>0</sub>&nbsp;&nbsp;)</em>&nbsp;表示其&nbsp;<em>x&nbsp;&nbsp;</em><em><sub>0</sub></em>&nbsp;和&nbsp;<em>y&nbsp;&nbsp;</em><em><sub>0</sub></em>坐標&nbsp;為域元素，&nbsp;&nbsp;<em>x&nbsp;&nbsp;</em><em><sub>0</sub></em>&nbsp;和&nbsp;<em>y&nbsp;&nbsp;</em><em><sub>0</sub></em>坐標&nbsp;滿足方程。<em></em><em><sub></sub></em><em><sub></sub></em><em><sub></sub></em><em><sub></sub></em></p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li><strong>在橢圓曲線上加點</strong>&nbsp;：令&nbsp;<em>P、Q</em>&nbsp;和&nbsp;<em>R</em>&nbsp;為橢圓曲線上的三個點。添加點 P + Q = R。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>橢圓曲線上的雙點</strong>&nbsp;：令&nbsp;<em>P、Q</em>&nbsp;為橢圓曲線上的兩點。倍增點 P + P = 2P = Q</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>點乘法</strong> ：令 <em>P</em> 為曲線 <em>E</em>上的一個點 ，定義在等式中<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>點乘&nbsp;<em>nP</em>&nbsp;定義為&nbsp;<em>nP = P + P + P + ... + P</em>&nbsp;&nbsp;（&nbsp;&nbsp;<em>n</em>&nbsp;次），其中&nbsp;<em>n</em>&nbsp;為整數；&nbsp;<em>nP</em>&nbsp;也是同一條&nbsp;<em>E</em>曲線上的一個點&nbsp;。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em>aP = O</em>的最小自然數 a&nbsp;&nbsp;稱為&nbsp;<strong><em>P</em></strong><strong>的階&nbsp;<em></em></strong>&nbsp;。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>橢圓曲線密碼系統中廣泛需要點乘法。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:heading {"level":4} -->
<h4>分頻器</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong></strong>&nbsp;曲線&nbsp;<em>E上的</em><strong>除數</strong>&nbsp;(Divisor)&nbsp;&nbsp;<em>D</em>&nbsp;是表示&nbsp;<strong><em>E</em></strong><strong>上點的多重集的&nbsp;</strong>便捷方式&nbsp;，寫為形式和<em></em><strong><em></em></strong></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/0b1/3e2/fbe/0b13e2fbec01a2ea5635bbcb1a36ade1.png" alt="secp256k1 橢圓曲線的有用且高效的算法" title=""/></figure>
<!-- /wp:image -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><em>E</em>上所有除數的集合&nbsp;用<em>Div&nbsp;&nbsp;<sub>F q</sub>&nbsp;&nbsp;(E)</em>&nbsp;表示&nbsp;&nbsp;，並形成一個群，其中除數的加法是自然的。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>零因子：這是所有 n&nbsp;&nbsp;<sub>P</sub>&nbsp;&nbsp;= 0 的因子，零因子&nbsp;<em>是 0 ∈ Div&nbsp;&nbsp;<sub>F q</sub>&nbsp;&nbsp;(E)</em>&nbsp;&nbsp;。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>如果域&nbsp;<em>F&nbsp;&nbsp;<sub>q</sub></em>&nbsp;不具體，可以省略，簡單寫成&nbsp;<em>Div(E)</em>&nbsp;表示除數群。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":4} -->
<h4>函數 f 除以 E</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>函數&nbsp;<em>f</em>&nbsp;被&nbsp;<em>E的除數用於表示函數</em><em>f</em>&nbsp;和&nbsp;<em>E</em>&nbsp;的交點（及其重數）&nbsp;&nbsp;&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4>配對威爾</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>由e&nbsp;&nbsp;<sub>m</sub></em>表示的 Weyl 配對&nbsp;&nbsp;以一對點 P, Q ∈ E[m] 作為輸入&nbsp;<em>，並&nbsp;<sub>產生單位根 _m&nbsp;</sub></em><em><sup>e&nbsp;&nbsp;<sub>m</sub></sup><sub>&nbsp;(</sub>&nbsp;&nbsp;P , Q)</em>&nbsp;作為輸出&nbsp;&nbsp;。Weyl 對的雙線性由方程表示</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>e&nbsp;&nbsp;<sub>m</sub>&nbsp;&nbsp;(P&nbsp;&nbsp;<sub>1</sub>&nbsp;&nbsp;+ P&nbsp;&nbsp;<sub>2</sub>&nbsp;&nbsp;, Q) = e&nbsp;&nbsp;<sub>m</sub>&nbsp;&nbsp;(P&nbsp;&nbsp;<sub>1</sub>&nbsp;&nbsp;, Q) * e&nbsp;&nbsp;<sub>m</sub>&nbsp;&nbsp;(P2, В),</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>e&nbsp;&nbsp;<sub>m</sub>&nbsp;&nbsp;(P, Q&nbsp;&nbsp;<sub>1</sub>&nbsp;&nbsp;+ Q&nbsp;&nbsp;<sub>2</sub>&nbsp;&nbsp;) = e&nbsp;&nbsp;<sub>m</sub>&nbsp;&nbsp;(P, Q&nbsp;&nbsp;<sub>1</sub>&nbsp;&nbsp;) * e&nbsp;&nbsp;<sub>m</sub>&nbsp;&nbsp;(P, Q&nbsp;&nbsp;<sub>2</sub>&nbsp;&nbsp;)。</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>Weil&nbsp;</strong>對&nbsp;<em>P</em>&nbsp;和&nbsp;<em>Q</em>&nbsp;是數</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/5eb/b85/30f/5ebb8530fd881d89d3f396460464af79.png" alt="secp256k1 橢圓曲線的有用且高效的算法" title=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>其中&nbsp;<em>S ∈ E</em>&nbsp;是滿足條件&nbsp;<em>S ∉ {O, P, −Q, P − Q} 的任意</em>點&nbsp;。（這確保右側的所有量都已定義且非零。）可以檢查&nbsp;<em>e&nbsp;&nbsp;<sub>m</sub>&nbsp;&nbsp;(P,Q)的值不取決於</em><em>f&nbsp;&nbsp;<sub>P</sub></em>&nbsp;&nbsp;、&nbsp;&nbsp;<em>f&nbsp;&nbsp;<sub>Q</sub></em>&nbsp;和&nbsp;<em>S</em>&nbsp;的選擇&nbsp;&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4>一種高效的Weil配對計算算法</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>令&nbsp;<em>E</em>&nbsp;為橢圓曲線，令 P = (x&nbsp;&nbsp;<sub>P</sub>&nbsp;&nbsp;,y&nbsp;&nbsp;<sub>P</sub>&nbsp;&nbsp;) 和 Q = (x&nbsp;&nbsp;<sub>Q</sub>&nbsp;&nbsp;, y&nbsp;&nbsp;<sub>Q ) 為</sub><em>E</em>&nbsp;上的非零點&nbsp;&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>令&nbsp;<em>λ為連接</em><em>P</em>&nbsp;和&nbsp;<em>Q</em>&nbsp;的直線的斜率&nbsp;，或者如果<em>P = Q 則</em><em>E</em>&nbsp;在 P 處的&nbsp;&nbsp;切線的斜率&nbsp;&nbsp;。（如果直線是垂直的，我們設置&nbsp;<em>λ</em>&nbsp;&nbsp;= ∞。）定義函數 g&nbsp;&nbsp;<sub>P, Q</sub>&nbsp;&nbsp;on&nbsp;&nbsp;<em>E</em>&nbsp;如下：<em></em><em></em><sub></sub><em></em></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/dbc/8cd/efc/dbc8cdefc33de28911b8e41530a16687.png" alt="secp256k1 橢圓曲線的有用且高效的算法" title=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>然後</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>div(g&nbsp;&nbsp;<sub>P, Q</sub>&nbsp;&nbsp;) = [P] + [Q] — [P + Q] —&nbsp;&nbsp;&nbsp;[&nbsp;<em>O</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>米勒算法</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>令&nbsp;<em>m ≥並將</em><em>m</em>&nbsp;的二進制擴展寫&nbsp;&nbsp;為</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>m = m&nbsp;&nbsp;<sub>0</sub>&nbsp;&nbsp;+ m&nbsp;&nbsp;<sub>1</sub>&nbsp;&nbsp;* 2 + m&nbsp;&nbsp;<sub>2</sub>&nbsp;&nbsp;* 2&nbsp;&nbsp;<sup>2</sup>&nbsp;&nbsp;+···+ m&nbsp;&nbsp;<sub>n — 1</sub>&nbsp;&nbsp;2&nbsp;&nbsp;<sup>n — 1</sup></em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>因為&nbsp;<em>m&nbsp;&nbsp;<sub>i</sub>&nbsp;&nbsp;∈ {0, 1}</em>&nbsp;且&nbsp;<em>m&nbsp;&nbsp;<sub>n — 1</sub>&nbsp;&nbsp;≠ 0</em>&nbsp;&nbsp;。以下算法返回一個函數&nbsp;<em>f&nbsp;&nbsp;<sub>P</sub></em>&nbsp;其除數滿足條件</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>div(&nbsp;&nbsp;<em>f&nbsp;&nbsp;<sub>P</sub></em>&nbsp;&nbsp;) =&nbsp;&nbsp;<em>m</em>&nbsp;&nbsp;[&nbsp;&nbsp;<em>P</em>&nbsp;&nbsp;] — [&nbsp;&nbsp;<em>mP</em>&nbsp;&nbsp;] — (&nbsp;&nbsp;<em>m — 1</em>&nbsp;&nbsp;) [&nbsp;&nbsp;<em>O</em>&nbsp;&nbsp;],</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>&nbsp;其中算法使用的函數&nbsp;<em>g&nbsp;&nbsp;<sub>T, T</sub></em>&nbsp;和&nbsp;<em>g&nbsp;&nbsp;<sub>T, P在 (a) 中定義。</sub></em></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/bc1/d75/c60/bc1d75c6060123845b0b7f4b153096b0.png" alt="secp256k1 橢圓曲線的有用且高效的算法" title=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>特別地，如果&nbsp;<em>P ∈ E[m]</em>&nbsp;&nbsp;，則 div(&nbsp;&nbsp;<em>f&nbsp;&nbsp;<sub>P</sub></em>&nbsp;&nbsp;) =&nbsp;&nbsp;<em>m</em>&nbsp;&nbsp;[&nbsp;&nbsp;<em>P</em>&nbsp;&nbsp;] −&nbsp;&nbsp;<em>m</em>&nbsp;&nbsp;[&nbsp;&nbsp;<em>O</em>&nbsp;&nbsp;]。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>要求</h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>Python 3.5</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>numpy</code></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:code -->
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/04AlgorithmsForSecp256k/

pip3 install numpy</code></pre>
<!-- /wp:code -->

<!-- wp:code -->
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
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3></h3>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/04AlgorithmsForSecp256k" target="_blank" rel="noreferrer noopener">來源</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>電報：&nbsp; https:&nbsp;<a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">//t.me/cryptodeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>視頻素材：&nbsp; https:&nbsp;<a href="https://youtu.be/gFbiBCNPsFk" target="_blank" rel="noreferrer noopener">//youtu.be/gFbiBCNPsFk</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/gFbiBCNPsFk","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/gFbiBCNPsFk
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">密碼分析</a></p>
<!-- /wp:paragraph -->
