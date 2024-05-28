<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/YP4Xj6gUcf4","type":"rich","providerNameSlug":"","responsive":true,"align":"center","className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed aligncenter is-type-rich wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/YP4Xj6gUcf4
</div></figure>
<!-- /wp:embed -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>我們對網格攻擊了解多少？</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>首先，&nbsp;<em>橢圓曲線數字簽名算法</em>&nbsp;<code>(ECDSA)</code>&nbsp;是我們在許多代碼審查中看到的一種常見數字簽名方案。它具有一些理想的特性，但也可能非常脆弱，無法通過側信道攻擊來恢復私鑰，這種攻擊會洩露不到一位的秘密隨機數。</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>ECDSA</code>&nbsp;是一種特殊形式的數字簽名算法&nbsp;<code>(DSA)</code>。&nbsp;<code>DSA</code>&nbsp;是一種相當常見的數字簽名方案，它由三種算法定義：密鑰生成、簽名和驗證。&nbsp;<em>密鑰生成算法生成私鑰和公鑰；</em>&nbsp;<em>私鑰負責創建簽名；</em>&nbsp;<em>公鑰負責驗證簽名。</em>&nbsp;簽名算法將消息和私鑰作為輸入並生成簽名。驗證算法以消息、簽名和公鑰為輸入，返回&nbsp;<code>true</code>&nbsp;或&nbsp;的值<code>false</code>，表示簽名是否有效。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><code>DSA</code>&nbsp;是為任何數學群定義的，只要離散對數問題對那個群來說是困難的，這個方案就是安全的。一個常用的組是整數模素數 p。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>與這個組一起，我們將有一個組生成器 g 和一些加密安全的&nbsp;<em>哈希</em>&nbsp;函數&nbsp;<code>H</code>。我們可以假設這&nbsp;<code>p , g</code>&nbsp;將&nbsp;<code>H</code>&nbsp;是常識。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>密鑰生成首先從&nbsp;<code>x</code>&nbsp;模整數中&nbsp;隨機選擇一個值<code>p</code>&nbsp;。然後計算值&nbsp;<code>y = g^x mod p</code></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>簽名的私鑰為&nbsp;<code>x</code>&nbsp;，公鑰為&nbsp;<code>y</code>&nbsp;。簽名密鑰必須保密，因為它允許進行簽名。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><code>m</code>&nbsp;簽名算法根據消息和密鑰 x創建簽名&nbsp;。首先，隨機生成一個群元素&nbsp;<code>k</code>&nbsp;。這被稱為隨機數，這在攻擊時很重要。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>然後計算值&nbsp;<code>r = g^k mod p</code>&nbsp;並&nbsp;<code>s = ( k^-1 ( H ( m ) + xr )) mod p</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>這裡&nbsp;<code>k^- 1</code>&nbsp;, 是逆群，&nbsp;<code>H ( m )</code>&nbsp;是計算散列 m 並將結果解釋為整數模 p 的結果。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>簽名定義為一對&nbsp;<code>( r , s )</code>.&nbsp;<code>r</code>&nbsp;（注意：如果or&nbsp;值之一&nbsp;<code>s</code>等於&nbsp;<code>0</code>，則算法以 的新值重新開始&nbsp;<code>k</code>&nbsp;）。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>( r , s )</code>驗證算法接收簽名、消息&nbsp;和公鑰 y作為輸入&nbsp;<code>m</code>&nbsp;。讓&nbsp;<code>ŝ = s^-1</code>&nbsp;，則算法返回 true 當且僅當&nbsp;<code>r , s ≠ 0 и r = ( g H ( m ) y r ) ŝ</code>&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>此驗證檢查有效，因為&nbsp;<code>g^H( m ) y^r = g^H(m)+ xr = g^ks</code>，因此&nbsp;<code>(g^H(m)y^r)^ŝ = g^k = r</code></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>如果無法偽造數字簽名方案，則認為它是安全的。</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>不變性具有正式的密碼學含義，但在較高層次上，它意味著您無法在不知道密鑰的情況下創建簽名（除非您已經復制了從密鑰創建的現有簽名）。<code>DSA</code>在離散日誌的假設下被證明是&nbsp;不可能偽造的。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>數字簽名是在數學組上定義的。當&nbsp;<code>DSA</code>&nbsp;與橢圓曲線群一起用作這個數學群時，我們稱它為&nbsp;<code>ECDSA</code>。&nbsp;<em>橢圓曲線群</em>&nbsp;由橢圓曲線點組成，這些點是 的對&nbsp;，滿足&nbsp;一些 的&nbsp;<code>( x , y )</code>方程&nbsp;&nbsp;。對於這篇博文，你需要知道的是使用橢圓曲線你可以定義一個有限群，這意味著你得到群生成器，（橢圓曲線點），加法和點&nbsp;<em>乘</em>操作&nbsp;<em><u>與</u></em><em><u>你</u></em>&nbsp;完全&nbsp;&nbsp;一樣可以用整數。因為它們形成一個有限群，生成器，<code>y^2 = x^3 + ax + b</code><code>a , b</code><code>g</code>&nbsp;<em></em><em><u></u></em><em><u></u></em><code>g</code>&nbsp;, 將有一個有限的順序，&nbsp;&nbsp;<code>p</code>。這篇博文不會解釋或要求您了解這些&nbsp;<em>橢圓曲線</em>運算的工作原理。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>密鑰</em>&nbsp;<code>x</code>&nbsp;仍然是一個隨機值模整數&nbsp;<code>p</code>&nbsp;。<code>ECDSA</code>&nbsp;工作方式與 相同&nbsp;<code>DSA</code>，但使用不同的組。現在公鑰&nbsp;<code>y</code>&nbsp;仍然計算為&nbsp;<code>y = g^x</code>&nbsp;，只是 g 現在是橢圓曲線上的一個點。這意味著 y 也將是橢圓曲線上的一個點（以前 y 是整數模 p ）。另一個區別是我們如何計算 r 的值。我們仍然像以前一樣生成隨機數 k 作為整數模 p。我們將計算&nbsp;<code>g^k</code>&nbsp;，但同樣，<code>g</code>&nbsp;是橢圓曲線的一個點，因此&nbsp;<code>g^k</code>&nbsp;也是。因此，我們可以計算&nbsp;<code>( x^k , y^k ) = g^k</code>&nbsp;並設置&nbsp;<code>r = x^k</code>&nbsp;。現在的意思&nbsp;<code>s</code>&nbsp;可以像以前一樣計算，我們得到我們的簽名&nbsp;<code>( r , s )</code>，它仍然是一個整數模&nbsp;<code>p</code>&nbsp;，和以前一樣。<code>r</code>&nbsp;為了檢查，我們需要糾正我們計算的稍微不同的事實&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>因此，和以前一樣，我們&nbsp;<em>計算</em>&nbsp;的值&nbsp;<code>( g^H(m)y^r)^ŝ</code>&nbsp;，但現在該值是橢圓曲線上的一個點，因此我們採用&nbsp;<code>x</code>該點的坐標並將其與我們的值進行比較&nbsp;<code>r</code>&nbsp;。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><em>&nbsp;從重複使用的隨機數中&nbsp;恢復&nbsp;<u>秘密密鑰</u></em><code>NONCES</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>現在我們了解了它是什麼&nbsp;<code>ECDSA</code>&nbsp;以及它是如何工作的，讓我們來證明它的&nbsp;<em><u>脆弱性</u></em>。同樣，由於這是一個數字簽名方案，因此絕不能將&nbsp;<em>密鑰</em>&nbsp;洩露給除簽名消息的人以外的任何人。</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>但是，如果簽名者曾經簽發過簽名並且還簽發過使用過的隨機數，那麼&nbsp;<em>攻擊者</em>&nbsp;可以立即恢復&nbsp;<em><u>密鑰</u></em>。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>假設我發布了&nbsp;<code>( r , s )</code>&nbsp;一條消息的&nbsp;簽名<code>m</code>&nbsp;，無意中發現我使用了 nonce&nbsp;&nbsp;<code>k</code>&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>由於&nbsp;<code>s = ( k^-1 ( H ( m ) + xr )),</code>&nbsp;我們可以很容易地計算出密鑰：</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>s = (k^-1(H(m) + xr))</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>ks = H(m) + xr</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>ks – H(m) = xr</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>x = r^-1(ks – H(m))</code></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>因此，簽名者不僅要保密他們的&nbsp;<em><u>私鑰</u></em>，而且他們曾經生成的所有隨機數都是保密的。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>即使簽名者對每個&nbsp;<em><u>nonce&nbsp;</u></em><code>NONCES</code>保密，如果他不小心重複了一個&nbsp;<em><u>nonce</u></em>&nbsp;<code>NONCES</code>&nbsp;&nbsp;（即使是針對不同的消息），&nbsp;&nbsp;也可以&nbsp;立即<strong>恢復</strong><em><u>秘密密鑰</u></em>。<strong></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>讓&nbsp;<code>( r , s 1 )</code>&nbsp;和&nbsp;<code>( r , s 2 )</code>&nbsp;成為在消息上創建的兩個簽名&nbsp;<code>m 1</code>&nbsp;並且&nbsp;<code>m 2</code>&nbsp;（分別）來自同一個隨機數——&nbsp;<code>k</code>&nbsp;因為它們具有相同的隨機數，所以 r 值將相同，所以這很容易被攻擊者檢測到：</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>s1 = k^-1(H(m1) + xr) and s2 = k^-1(H(m2) + xr)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>s1 – s2 = k^-1(H(m1) – H(m2))</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>k(s1 – s2) = H(m1) – H(m2)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>k = (s1 – s2)^-1(H(m1) – H(m2))</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>一旦我們使用上述公式恢復了隨機數&nbsp;<code>k</code>&nbsp;，我們就可以通過執行前面描述的攻擊來恢復私鑰。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 class="wp-block-heading">讓我們消化一下。</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>如果&nbsp;簽名的<em><u>nonce&nbsp;</u></em><code>NONCES</code>&nbsp;被洩露，&nbsp;可以立即&nbsp;<em><u>恢復</u></em><em>密鑰</em>，這&nbsp;<strong><u>會破壞我們的整個簽名方案</u></strong>。<em><u></u></em><strong><u></u></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>此外，如果兩個 nonce 重複，無論消息是什麼，&nbsp;<em>攻擊者都</em>&nbsp;可以輕鬆檢測到這一點並立即&nbsp;<strong>恢復密鑰</strong>，再次破壞我們的整個方案。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>它非常脆弱，而且只有&nbsp;<em>輕攻擊</em>！</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>但是有&nbsp;<em>一個新的</em>&nbsp;<strong><a href="https://youtu.be/YP4Xj6gUcf4" target="_blank" rel="noreferrer noopener">Lattice&nbsp;</a></strong><a href="https://youtu.be/YP4Xj6gUcf4"><strong>Attack</strong></a>&nbsp;已經被詳細描述&nbsp;<a href="https://youtu.be/YP4Xj6gUcf4" target="_blank" rel="noreferrer noopener"><em>（Joachim Breitner 和 Nadia Heninger）</em></a><code>Йоахим Брайтнер и Надя Хенингер</code><a href="https://youtu.be/YP4Xj6gUcf4" target="_blank" rel="noreferrer noopener">&nbsp;<em></em></a></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>文檔&nbsp;<a href="https://eprint.iacr.org/2019/023.pdf" target="_blank" rel="noreferrer noopener">[PDF]</a>：&nbsp;<em>有偏差的 Nonce Sense：針對加密貨幣中弱 ECDSA 簽名的格攻擊</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading -->
<h2 class="wp-block-heading">在比特幣區塊鏈中，我們發現了一筆交易：</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>交易：&nbsp;&nbsp;<a href="https://www.blockchain.com/btc/tx/08d917f0fee48b0d765006fa52d62dd3d704563200f2817046973e3bf6d11f1f" target="_blank" rel="noreferrer noopener">08d917f0fee48b0d765006fa52d62dd3d704563200f2817046973e3bf6d11f1f</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>比特幣地址：&nbsp;&nbsp;<a href="https://www.blockchain.com/btc/address/15N1KY5ohztgCXtEe13BbGRk85x2FPgW8E" target="_blank" rel="noreferrer noopener">15N1KY5ohztgCXtEe13BbGRk85x2FPgW8E</a></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>我們設法將假簽名相乘並應用網格</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><strong>在GOOGLE COLAB</strong>&nbsp;中安裝包&nbsp;時使用&nbsp;<em>Python 腳本</em>&nbsp;<a href="https://youtu.be/YP4Xj6gUcf4" target="_blank" rel="noreferrer noopener">algorithmLLL.py</a><strong></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>安裝 &gt;&gt; SAGE + ECDSA + BITCOIN + 算法 LLL</strong></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>我們&nbsp;&nbsp;設法擺脫&nbsp;<code>Private Key</code>&nbsp;了&nbsp;.<code>Bitcoin Wallet</code><code>ECDSA</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/777/37e/84b/77737e84bb453449fd6956a39c4eb195.png" alt="安裝" title="安裝"/><figcaption class="wp-element-caption">安裝</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/ae2/0b3/747/ae20b37475bfff1ce38f81cc206a93f3.png" alt="運行 Bash 腳本：lattice.sh" title="運行 Bash 腳本：lattice.sh"/><figcaption class="wp-element-caption">運行 Bash 腳本：lattice.sh</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/722/89e/9da/72289e9dab54d5aa568438a94a4c90a6.png" alt="十六進制格式的結果找到私鑰！" title="十六進制格式的結果找到私鑰！"/><figcaption class="wp-element-caption">十六進制格式的結果找到私鑰！</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/469/217/84b/46921784bb73f1218ded9e16bc0f8abd.png" alt="文件：ONESIGN.txt（ECDSA 簽名 R、S、Z 值）" title="文件：ONESIGN.txt（ECDSA 簽名 R、S、Z 值）"/><figcaption class="wp-element-caption">文件：ONESIGN.txt（ECDSA 簽名 R、S、Z 值）</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/8cb/e22/f9c/8cbe22f9cd364064a8e005ac8ea4e99e.png" alt="我們為 Python 腳本 algorithmLLL.py 傳播了假簽名" title="我們為 Python 腳本 algorithmLLL.py 傳播了假簽名"/><figcaption class="wp-element-caption">我們為 Python 腳本 algorithmLLL.py 傳播了假簽名</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/83f/750/d81/83f750d81ba83309039189495a10680a.png" alt="文件：PRIVATEKEY.txt" title="文件：PRIVATEKEY.txt"/><figcaption class="wp-element-caption">文件：PRIVATEKEY.txt</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/202/982/105/2029821051232d8a95744863eaa65049.png" alt="文件：ADDRESS.txt" title="文件：ADDRESS.txt"/><figcaption class="wp-element-caption">文件：ADDRESS.txt</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><strong>讓我們打開&nbsp;<a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">bitaddress</a>&nbsp;並檢查：</strong></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/4ce/93f/dd1/4ce93fdd168a7acc734929d342c8949c.png" alt="在bitaddress網站上查看私鑰" title="在bitaddress網站上查看私鑰"/><figcaption class="wp-element-caption">在bitaddress網站上查看私鑰</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><em><u>找到私鑰！</u></em></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.blockchain.com/btc/address/15N1KY5ohztgCXtEe13BbGRk85x2FPgW8E"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/btc/address/15N1KY5ohztgCXtEe13BbGRk85x2FPgW8E
</div></figure>
<!-- /wp:embed -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/00c/be7/072/00cbe70723846c402c4da47bcb6d47b3.png" alt="0.001比特幣" title="0.001比特幣"/><figcaption class="wp-element-caption">0.001比特幣</figcaption></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 15N1KY5ohztgCXtEe13BbGRk85x2FPgW8E
WIF:  5JCAmNLXeSwi2SCgNH7wRL5qSQhPa7sZvj8eDwxisY5hJm8Uh92
HEX:  31AFD65CAD430D276E3360B1C762808D1D051154724B6FC15ED978FA9D06B1C1 </code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/lattice-attack" target="_blank" rel="noreferrer noopener"><strong>該視頻是為CRYPTO DEEP TECH</strong></a>門戶網站創建的&nbsp;&nbsp;，以確保數據和 secp256k1 橢圓曲線密碼學的財務安全，以防止 BITCOIN 加密貨幣中的弱 ECDSA 簽名</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>&nbsp;<a href="https://youtu.be/YP4Xj6gUcf4" target="_blank" rel="noreferrer noopener">https://youtu.be/YP4Xj6gUcf4</a></strong>&nbsp;–<strong>視頻素材</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>cryptodeeptech@gmail.com – 所有問題的電子郵件</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://t.me/cryptodeep_tech" target="_blank" rel="noreferrer noopener">https://t.me/cryptodeep_tech</a>&nbsp;– 通過 Telegram 提供技術支持</strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/YP4Xj6gUcf4","type":"rich","providerNameSlug":"","responsive":true,"align":"center","className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed aligncenter is-type-rich wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/YP4Xj6gUcf4
</div></figure>
<!-- /wp:embed -->
