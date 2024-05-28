<!-- wp:embed {"url":"https://www.youtube.com/embed/DH6FyNY-Gh0","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/DH6FyNY-Gh0
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p><code>secp256k1</code>&nbsp;在本文中，我們將研究有助於優化比特幣加密貨幣驗證的自同態&nbsp;加速函數&nbsp;<code>ECDSA</code>&nbsp;，但首先要了解一點歷史。</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>12 января 2009 года</code>&nbsp;<a href="https://ru.wikipedia.org/wiki/%D0%A1%D0%B0%D1%82%D0%BE%D1%81%D0%B8_%D0%9D%D0%B0%D0%BA%D0%B0%D0%BC%D0%BE%D1%82%D0%BE" target="_blank" rel="noreferrer noopener">中本聰</a>&nbsp;在最早的比特幣交易中&nbsp;派出了<a href="https://ru.wikipedia.org/wiki/%D0%93%D0%B0%D1%80%D0%BE%D0%BB%D1%8C%D0%B4_%D0%A2%D0%BE%D0%BC%D0%B0%D1%81_%D0%A4%D0%B8%D0%BD%D0%BD%D0%B8_II" target="_blank" rel="noreferrer noopener">哈爾芬尼</a>&nbsp;<code>10 BTC</code>。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>中本聰選擇 Hal 作為比特幣的第一個接收者並不奇怪。中本聰非常尊重 Hal，他通過開發&nbsp;<a href="https://ru.wikipedia.org/wiki/PGP" target="_blank" rel="noreferrer noopener">PGP</a>加密系統確立了自己作為世界上最聰明的程序員和密碼學家之一的地位。Hal 還為中本聰在比特幣開發中使用的可重用工作量證明奠定了重要基礎。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>作為世界上最好的密碼學家之一，哈爾在偶然發現比特幣後立即意識到比特幣是一個巨大的突破。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>他還&nbsp;<code>2008 году</code>&nbsp;稱比特幣為&nbsp;<strong><em>“一個非常有前途的想法”</em></strong>。</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w780/getpro/habr/upload_files/e90/c19/48e/e90c1948ecdd67427ca6fd6eb0fe7b24.jpg" alt="用自同態加速secp256k1"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>由 發布的&nbsp;這條&nbsp;<em>推文</em><code>11 января 2009 года</code>足以證明哈爾&nbsp;&nbsp;甚至在許多人知道比特幣是什麼之前就<em><u>預測到了比特幣的成功。</u></em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>兩年過去了，&nbsp;<code>2011 году</code>&nbsp;作為開發者和比特幣愛好者的 Hal Finney 在&nbsp;<a href="https://bitcointalk.org/index.php?topic=3238.msg45565#msg45565" target="_blank" rel="noreferrer noopener"><strong>Bitcointalk</strong></a>論壇上寫道，&nbsp;&nbsp;<em><u>secp256k1 自同態函數可用於加速 ECDSA 簽名驗證</u></em></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>LAMBDA和BETA是secp256k1曲線上的值，其中：</h2>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/9a4/ce6/3af/9a4ce63afa2c39ded280bea637d2ba70.svg" alt="λ^3 (mod n) = 1  "/></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/df4/4d7/5ce/df44d75ceb126764e40606ad336f26e3.svg" alt="b ^ 3 (mod p) = 1"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3>secp256k1 使用以下質數作為其 x 和 y 坐標：</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>p = 0xffffffffffffffffffffffffffffffffffffffffffffffffffffffffffffffffc2f</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>和曲線的順序：</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>n = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>第一步是計算&nbsp;<code>LAMBDA</code>&nbsp;和&nbsp;的值<code>BETA</code>，這樣對於曲線上的任意點&nbsp;<code>Q = (x, y)</code>：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>LAMBDA * Q = (BETA*х mod р, у)</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>這就是所謂的有效可計算&nbsp;<em><u>自同態</u></em>，它意味著您可以通過一次乘法&nbsp;非常快速地將曲線上的任何點乘以&nbsp;<code>secp256k1</code>&nbsp;這個特殊值&nbsp;。<code>LAMBDA</code><code>mod p</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading -->
<h2>Hal Finney發現並發表的意義：</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>LAMBDA = 0x5363ad4cc05c30e0a5261c028812645a122e22ea20816678df02967c1b23bd72

BETA = 0x7ae96a2b657c07106e64479eac3434e99cf0497512f58995c1396c28719501ee</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>鑑於我們可以快速相乘，&nbsp;<code>LAMBDA,</code>&nbsp;訣竅是計算&nbsp;<code>kQ</code><em>。&nbsp;</em>先用計算吧。然後&nbsp;&nbsp;你需要分成兩部分&nbsp;&nbsp;和&nbsp;，每部分大約是 寬度的一半&nbsp;，這樣：<em>&nbsp;</em><code>Q' = lambdaQ</code><code>k</code><code>k1</code><code>k2</code><code>n</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>k = k1 + k2*LAMBDA  mod  n</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>然後</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>k*Q = (k1 + k2*LAMBDA)*Q = k1*Q + k2*LAMBDA*Q = k1*Q + k2*Q'</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>最後一個表達式可以使用雙倍乘法算法高效地計算，並且由於&nbsp;<code>k1</code>&nbsp;和&nbsp;<code>k2</code>&nbsp;是長度的一半，我們得到了加速。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>缺少的部分拆分&nbsp;<code>k</code>&nbsp;為&nbsp;<code>k1</code>&nbsp;和&nbsp;<code>k2</code>。<em><u>以下4 個值</u></em>用於此&nbsp;：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>а1 = 0x3086d221a7d46bcde86c90e49284eb15
b1 = -0xe4437ed6010e88286f547fa90abfe4c3
а2 = 0x114ca50f7a8e2f3f657c1108d9d44cfd8
b2 = 0x3086d221a7d46bcde86c90e49284eb15</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>（沒關係，a1 = b2）</em></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4>我們按如下方式使用它們來劃分 k：</h4>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>c1 = RoundToNearestInteger(b2*k/n)
c2 = RoundToNearestInteger(-b1*k/n)

k1 = k - c1*a1 - c2*a2
k2 = -c1*b1 - c2*b2</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>20%-е</code>&nbsp;由於加倍次數減半，我們最終得到了大致的&nbsp;加速。這為許多可以在多個點上分組的算法提供了它們在使用兩倍數量的公鑰時所具有的性能。<br><em>這種在同等優化水平上的加速使其成為&nbsp;</em><code>secp256k1</code><em>&nbsp;所有常用曲線中測試速度最快的曲線。</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading {"level":3} -->
<h3>我們從開發人員和研究員 Jean Luc Pons 那裡對存儲庫進行了更詳細的研究，了解了自同態的存在</h3>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/53a/a41/46a/53aa4146a4d43ac9279e96b8e403216d.png" alt="用自同態加速secp256k1"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>我們之前發表過一篇文章：&nbsp;&nbsp;<a href="https://cryptodeep.ru/kangaroo/" target="_blank" rel="noreferrer noopener"><strong><em>“Pollard's Kangaroo find solutions to the discrete logarithm of secp256k1 PRIVATE KEY + NONCES in a known range”，</em></strong></a><strong><em>&nbsp;其中&nbsp;</em></strong><a href="https://cryptodeep.ru/kangaroo/" target="_blank" rel="noreferrer noopener">我們使用了Jean Luc Pons</a>構建&nbsp;<a href="https://cryptodeep.ru/kangaroo/" target="_blank" rel="noreferrer noopener">Kangaroo</a>&nbsp;的&nbsp;源代碼。<a href="https://cryptodeep.ru/kangaroo/" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>基於加速機制 Jean Luc Pons 指出 VanitySearch</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>打開&nbsp;<a href="https://github.com/JeanLucPons/VanitySearch/blob/c8d48ce5f03f5357c0e87cbdb3e1e93cd50af88b/main.cpp#L255" target="_blank" rel="noreferrer noopener"><strong>main.cpp</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/605/fca/301/605fca301a5eef1f215250562ff4e039.png" alt="主.cpp" title="主.cpp"/><figcaption class="wp-element-caption">主.cpp</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://github.com/JeanLucPons/VanitySearch/blob/c8d48ce5f03f5357c0e87cbdb3e1e93cd50af88b/main.cpp#L255" target="_blank" rel="noreferrer noopener">在第 255</a>&nbsp;和&nbsp;<a href="https://github.com/JeanLucPons/VanitySearch/blob/c8d48ce5f03f5357c0e87cbdb3e1e93cd50af88b/main.cpp#L256" target="_blank" rel="noreferrer noopener">256</a>行中，&nbsp;&nbsp;我們看到 Jean Luc Pons&nbsp;<code>secp256k1</code>&nbsp;使用&nbsp;<em><u>自同態</u></em>應用了橢圓曲線加速函數。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>  lambda.SetBase16("5363ad4cc05c30e0a5261c028812645a122e22ea20816678df02967c1b23bd72");
  lambda2.SetBase16("ac9c52b33fa3cf1f5ad9e3fd77ed9ba4a880b9fc8ec739c2e0cfc810b51283ce");</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>讓我們繼續進行實驗部分：</h2>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/7df/255/c08/7df255c08ea1fb0e498b76bf4a431873.png" alt="用自同態加速secp256k1"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>正如我們在&nbsp;<a href="https://cryptodeep.ru/kangaroo/" target="_blank" rel="noreferrer noopener">文章</a>中所記得的&nbsp;，我們分析了比特幣富豪榜中比特幣地址 14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE 的交易&nbsp;總額&nbsp;<a href="https://bitinfocharts.com/top-100-richest-bitcoin-addresses.html" target="_blank" rel="noreferrer noopener"><strong>超過</strong></a><a href="https://www.blockchain.com/ru/btc/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE" target="_blank" rel="noreferrer noopener"><strong>1000</strong></a>&nbsp;萬&nbsp;<a href="https://bitinfocharts.com/top-100-richest-bitcoin-addresses.html" target="_blank" rel="noreferrer noopener"><strong>美元</strong></a>，以該比特幣地址為例<a href="https://bitinfocharts.com/top-100-richest-bitcoin-addresses.html" target="_blank" rel="noreferrer noopener"><strong></strong></a><a href="https://bitinfocharts.com/top-100-richest-bitcoin-addresses.html" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>在終端中打開 Google Colab&nbsp;&nbsp;<a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener"><strong>[TerminalGoogleColab]</strong></a>&nbsp;並使用存儲庫&nbsp;<a href="https://github.com/demining/CryptoDeepTools/tree/main/07EndomorphismSecp256k1" target="_blank" rel="noreferrer noopener">“07EndomorphismSecp256k1”</a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/07EndomorphismSecp256k1/

pip3 install base58</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/928/66f/34b/92866f34b1dcfbce80b23fd56a913744.png" alt="用自同態加速secp256k1"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/9dfd594126117e07fc51a77a7c613180eb662f18/07EndomorphismSecp256k1/endomorphism.py#L145" target="_blank" rel="noreferrer noopener">145</a><em>行</em>打開代碼&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/9dfd594126117e07fc51a77a7c613180eb662f18/07EndomorphismSecp256k1/endomorphism.py#L145" target="_blank" rel="noreferrer noopener">endomorphism.py我們使用</a>&nbsp;<em>所有</em>&nbsp;的short值來加速&nbsp;&nbsp;endomorphism&nbsp;<em></em>&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/9dfd594126117e07fc51a77a7c613180eb662f18/07EndomorphismSecp256k1/endomorphism.py#L145" target="_blank" rel="noreferrer noopener"></a><code>secp256k1</code><em></em></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>def</strong> <strong>split_scalar_endo</strong>(k):
    n = N
    a1 = 0x3086d221a7d46bcde86c90e49284eb15
    b1 = -0xe4437ed6010e88286f547fa90abfe4c3
    a2 = 0x114ca50f7a8e2f3f657c1108d9d44cfd8
    b2 = a1
    c1 = div_nearest(b2 * k, n)
    c2 = div_nearest(-b1 * k, n)
    k1 = mod(k - c1 * a1 - c2 * a2, n)
    k2 = mod(-c1 * b1 - c2 * b2, n)
    k1neg = k1 &gt; POW_2_128
    k2neg = k2 &gt; POW_2_128
    <strong>if</strong> k1neg:
        k1 = n - k1
    <strong>if</strong> k2neg:
        k2 = n - k2
    <strong>return</strong> (k1neg, k1, k2neg, k2)</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/kangaroo/" target="_blank" rel="noreferrer noopener">以我們在文章</a><code>HEX</code>中發布的格式複制&nbsp;私鑰&nbsp;<a href="https://cryptodeep.ru/kangaroo/" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>HEX:  23d4a09295be678b21a5f1dceae1f634a69c1b41775f680ebf8165266471401b</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":4} -->
<h4>讓我們運行指定私鑰的 Python 腳本 endomorphism.py：</h4>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 endomorphism.py 23d4a09295be678b21a5f1dceae1f634a69c1b41775f680ebf8165266471401b &gt; pubkey.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/3c5/6f1/3d7/3c56f13d77ef80024a8cfb16f80943fc.png" alt="用自同態加速secp256k1"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":4} -->
<h4>公鑰的結果將保存到文件：pubkey.txt</h4>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Откроем файл: pubkey.txt и проверим:

cat pubkey.txt

04ca5606a1e820e7a2f6bb3ab090e8ade7b04a7e0b5909a68dda2744ae3b8ecbfa280a47639c811134d648e8ee8096c33b41611be509ebca837fbda10baaa1eb15
</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/448/529/511/4485295113ba74f334a01f4ed2b54bd4.png" alt="用自同態加速secp256k1"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":4} -->
<h4>接下來，通過運行 Python 腳本 pubtoaddr.py 獲取比特幣地址</h4>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 pubtoaddr.py

Откроем файл: BitcoinAddress.txt и проверим:

cat BitcoinAddress.txt

14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE
</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/1a4/805/542/1a480554216e020e1c53a9370661274a.png" alt="用自同態加速secp256k1"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE
WIF:  5J64pq77XjeacCezwmAr2V1s7snvvJkuAz8sENxw7xCkikceV6e
HEX:  23d4a09295be678b21a5f1dceae1f634a69c1b41775f680ebf8165266471401b</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/d8c/78d/8eb/d8c78d8eb14e5246b495e09f59631e44.png" alt="在bitaddress網站上查看私鑰" title="在bitaddress網站上查看私鑰"/><figcaption class="wp-element-caption">在bitaddress網站上查看私鑰</figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3>區塊鏈：</h3>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/ed9/7da/c1d/ed97dac1dc07e2bce09fe0951d9f64de.png" alt="www.blockchain.com/btc/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE" title="www.blockchain.com/btc/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE"/><figcaption class="wp-element-caption">www.blockchain.com/btc/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE</figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>關於這個話題，你可以閱讀文獻：</h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><em>Gallant、Robert P.、Robert J. Lambert 和 Scott A. Wanston。&nbsp;</em><strong><em>“具有有效自同態的橢圓曲線上的更快點乘法”</em></strong><em>。年度國際密碼學會議，第 190-200 頁。斯普林格，柏林，海德堡，(2001)</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em>Hankerson、Darrell、Alfred J. Menezes 和 Scott Wanston。&nbsp;</em><strong><em>“橢圓曲線密碼學指南”</em></strong><em>。計算機評論 46，沒有。1 (2005)</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em>哈爾·芬尼。bitcointalk -&nbsp;&nbsp;</em><strong><em>“加速簽名驗證”</em></strong><em>。(2011)&nbsp;</em>&nbsp;<a href="https://bitcointalk.org/index.php?topic=3238.0" target="_blank" rel="noreferrer noopener">https://bitcointalk.org/index.php?topic=3238.0</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em>Blahut, Richard E.&nbsp;&nbsp;</em><strong><em>“密碼學和安全通信”</em></strong><em>。劍橋大學出版社，（2014）</em></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>該視頻是為&nbsp;<a href="https://cryptodeep.ru/" target="_blank" rel="noreferrer noopener"><strong>CRYPTO DEEP TECH</strong></a>門戶網站創建的&nbsp;，以確保橢圓曲線上的數據和密碼學的金融安全性&nbsp;免受&nbsp;加密貨幣中&nbsp;<code>secp256k1</code>&nbsp;弱簽名的影響&nbsp;<code>ECDSA</code><code>BITCOIN</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/tree/main/07EndomorphismSecp256k1" target="_blank" rel="noreferrer noopener"><strong><u>來源</u></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener"><strong>電報</strong></a><strong>：&nbsp; https:&nbsp;</strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener"><strong><u>//t.me/cryptodeeptech</u></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://youtu.be/DH6FyNY-Gh0" target="_blank" rel="noreferrer noopener"><strong>視頻素材</strong></a><strong>：&nbsp; https:&nbsp;<u><a href="https://youtu.be/DH6FyNY-Gh0" target="_blank" rel="noreferrer noopener">//youtu.be/DH6FyNY-Gh0</a></u></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/endomorphism"><strong>資料來源</strong></a><strong>：&nbsp;&nbsp;</strong><a href="https://cryptodeep.ru/endomorphism" target="_blank" rel="noreferrer noopener"><strong>https ://cryptodeep.ru/endomorphism</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">密碼分析</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2404} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/03/011-1024x576.png" alt="Ускорение secp256k1 с помощью эндоморфизма" class="wp-image-2404"/></figure>
<!-- /wp:image -->
