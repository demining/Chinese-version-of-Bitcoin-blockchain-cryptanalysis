<!-- wp:embed {"url":"https://www.youtube.com/embed/xBgjWE5tA7Y","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/xBgjWE5tA7Y
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>我們都知道，ECDSA 簽名中的秘鑰洩露可以導致比特幣錢包的完全恢復。在我們之前的文章中，我們研究了區塊鏈交易中的<a href="https://cryptodeep.ru/lattice-attack/" target="_blank" rel="noreferrer noopener">弱點和漏洞</a>，但也有 ECDSA 短簽名也導致比特幣錢包的完全恢復。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>為什麼這些 ECDSA 簽名被稱為短簽名？</h3>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>你可以從討論的話題中得到這個問題的答案：<a href="https://bitcoin.stackexchange.com/questions/38513/the-shortest-ecdsa-signature" target="_blank" rel="noreferrer noopener"><strong>“最短的ECDSA簽名”【The shortest ECDSA signature】</strong></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>在我們的上一篇文章：<a href="https://cryptodeep.ru/reduce-private-key/" target="_blank" rel="noreferrer noopener"><em>“使用 ECPy + Google Colab 庫通過標量乘法減少私鑰”中，</em></a>我們創建了一個<em>Python</em>腳本：<a href="https://github.com/demining/CryptoDeepTools/blob/main/08ReducePrivateKey/maxwell.py" target="_blank" rel="noreferrer noopener">maxwell.py</a>，它為我們生成了一個相當有趣的公鑰</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/69a/7a0/b32/69a7a0b324ac3b1f3e0dc27f0f4130bf.png" alt="通過 ECDSA 短簽名恢復比特幣錢包"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>(0x3b78ce563f89a0ed9414f5aa28ad0d96d6795f9c63 , 0xc0c686408d517dfd67c2367651380d00d126e4229631fd03f8ff35eef1a61e3c)</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>我們知道簽名的值，<code>"R"</code>這是從私鑰到公鑰<code>(Nonce)</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>看看區塊鏈交易：<a href="https://btc.exan.tech/tx/11e6b169701a9047f3ddbb9bc4d4ab1a148c430ba4a5929764e97e76031f4ee3" target="_blank" rel="noreferrer noopener"><strong>11e6b169701a9047f3ddbb9bc4d4ab1a148c430ba4a5929764e97e76031f4ee3</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>原始TX：</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>0100000001afddd5c9f05bd937b24a761606581c0cddd6696e05a25871279f75b7f6cf891f250000005f3c303902153b78ce563f89a0ed9414f5aa28ad0d96d6795f9c6302200a963d693c008f0f8016cfc7861c7f5d8c4e11e11725f8be747bb77d8755f1b8012103151033d660dc0ef657f379065cab49932ce4fb626d92e50d4194e026328af853ffffffff010000000000000000016a00000000
</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>本次交易的規模僅為：<code>156 байт</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading {"level":3} -->
<h3>如何通過 ECDSA 短簽名恢復比特幣錢包？</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>在比特幣區塊鏈的密碼分析中，我們使用自己的<em>Bas</em>&nbsp;h腳本：<code>btcrecover.sh</code></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/299/fa2/616/299fa2616cbdb8e6df9304862f441ba2.gif" alt="比特幣錢包恢復過程" title="比特幣錢包恢復過程"/><figcaption class="wp-element-caption">比特幣錢包恢復過程</figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3>Bash 腳本：btcrecover.sh</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sudo apt install python2-minimal

wget https://bootstrap.pypa.io/pip/2.7/get-pip.py

sudo python2 get-pip.py

pip2 install -r requirements.txt

chmod +x btcrecover.sh


 ./btcrecover.sh 12yysAMhagEm67QCX85p3WQnTUrqcvYVuk


 ./btcrecover.sh 15HvLBX9auG2bJdLCTxSvjvWvdgsW7BvAT
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>結果：</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><code>| privkey : addr |</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>讓我們打開&nbsp;<a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">bitaddress</a>&nbsp;並檢查：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ac8d0abda1d32aaabff56cb72bc39a998a98779632d7fee83ff452a86a849bc1:12yysAMhagEm67QCX85p3WQnTUrqcvYVuk
b6c1238de89e9defea3ea0712e08726e338928ac657c3409ebb93d9a0873797f:15HvLBX9auG2bJdLCTxSvjvWvdgsW7BvAT</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>讓我們繼續實驗部分，更詳細地分析用於恢復比特幣錢包的所有腳本</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>打開&nbsp;<a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener"><strong>[TerminalGoogleColab]</strong></a>。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/tree/main/09BitcoinWalletRecovery" target="_blank" rel="noreferrer noopener"><strong>讓我們使用“09BitcoinWalletRecovery”</strong></a>存儲庫。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/09BitcoinWalletRecovery/

ls</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/4e3/7b8/f6c/4e37b8f6cefc8f8d0553f541a5eb8b98.png" alt="通過 ECDSA 短簽名恢復比特幣錢包"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3>安裝所有必要的模塊：</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>bitcoin
ecdsa
utils
base58</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>pip2 install -r requirements.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/d5f/25e/5b1/d5f25e5b1b966ff43a48aaf0955ecfcd.png" alt="通過 ECDSA 短簽名恢復比特幣錢包"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>使用<a href="https://github.com/demining/CryptoDeepTools/blob/main/09BitcoinWalletRecovery/breakECDSA.py" target="_blank" rel="noreferrer noopener">breakECDSA.py</a>腳本，我們從<code>RawTX</code>簽名 [R, S, Z]</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python2 breakECDSA.py 0100000001afddd5c9f05bd937b24a761606581c0cddd6696e05a25871279f75b7f6cf891f250000005f3c303902153b78ce563f89a0ed9414f5aa28ad0d96d6795f9c6302200a963d693c008f0f8016cfc7861c7f5d8c4e11e11725f8be747bb77d8755f1b8012103151033d660dc0ef657f379065cab49932ce4fb626d92e50d4194e026328af853ffffffff010000000000000000016a00000000 &gt; signatures.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>結果將保存到一個文件中：signatures.txt</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>讓我們打開文件：<code>PublicKeys.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat signatures.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/cd3/2b9/9e3/cd32b99e37cc600ddd3c35965e2a0288.png" alt="通過 ECDSA 短簽名恢復比特幣錢包"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0x00000000000000000000003b78ce563f89a0ed9414f5aa28ad0d96d6795f9c63
S = 0x0a963d693c008f0f8016cfc7861c7f5d8c4e11e11725f8be747bb77d8755f1b8
Z = 0x521a65420faa5386d91b8afcfab68defa02283240b25aeee958b20b36ddcb6de</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>正如我們從上一篇<a href="https://habr.com/ru/post/682220/">文章</a>中了解到的，我們知道生成<em>簽名的</em><em><u>密鑰</u></em><em></em>&nbsp;<code>R</code></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/9df/b17/63d/9dfb1763d978473245abb6cab03e0e48.png" alt="通過 ECDSA 短簽名恢復比特幣錢包"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>在我們的例子中，<em><u>密鑰是</u></em>&nbsp;<code>(Nonce)</code>：</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>0x7fffffffffffffffffffffffffffffff5d576e7357a4501ddfe92f46681b20a0 --&gt; 0x3b78ce563f89a0ed9414f5aa28ad0d96d6795f9c63, 0x3f3979bf72ae8202983dc989aec7f2ff2ed91bdd69ce02fc0700ca100e59ddf3
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>簽名：</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>K = 0x7fffffffffffffffffffffffffffffff5d576e7357a4501ddfe92f46681b20a0
R = 0x00000000000000000000003b78ce563f89a0ed9414f5aa28ad0d96d6795f9c63
S = 0x0a963d693c008f0f8016cfc7861c7f5d8c4e11e11725f8be747bb77d8755f1b8
Z = 0x521a65420faa5386d91b8afcfab68defa02283240b25aeee958b20b36ddcb6de</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>現在我們知道 ] 的值，<code>[K, R, S, Z</code>我們可以使用公式獲取私鑰並恢復比特幣錢包。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/2db/a14/ab5/2dba14ab5cb76228181c68a9403038a7.svg" alt="私鑰 = ((((S * K) - Z) *​​ modinv(R,N)) % N)"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>要獲取私鑰，我們將使用<em>Python</em>腳本：<a href="https://github.com/demining/CryptoDeepTools/blob/main/09BitcoinWalletRecovery/calculate.py" target="_blank" rel="noreferrer noopener">calculate.py</a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>def h(n):
    return hex(n).replace("0x","")

def extended_gcd(aa, bb):
    lastremainder, remainder = abs(aa), abs(bb)
    x, lastx, y, lasty = 0, 1, 1, 0
    while remainder:
        lastremainder, (quotient, remainder) = remainder, divmod(lastremainder, remainder)
        x, lastx = lastx - quotient*x, x
        y, lasty = lasty - quotient*y, y
    return lastremainder, lastx * (-1 if aa &lt; 0 else 1), lasty * (-1 if bb &lt; 0 else 1)

def modinv(a, m):
    g, x, y = extended_gcd(a, m)
    if g != 1:
        raise ValueError
    return x % m
    
N = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141


K = 0x7fffffffffffffffffffffffffffffff5d576e7357a4501ddfe92f46681b20a0
R = 0x00000000000000000000003b78ce563f89a0ed9414f5aa28ad0d96d6795f9c63
S = 0x0a963d693c008f0f8016cfc7861c7f5d8c4e11e11725f8be747bb77d8755f1b8
Z = 0x521a65420faa5386d91b8afcfab68defa02283240b25aeee958b20b36ddcb6de


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>讓我們運行 Python 腳本：calculate.py</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 calculate.py</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/502/645/324/502645324ec5666803f791ea3cc3a109.png" alt="PrivKey = b6c1238de89e9defea3ea0712e08726e338928ac657c3409ebb93d9a0873797f" title="PrivKey = b6c1238de89e9defea3ea0712e08726e338928ac657c3409ebb93d9a0873797f"/><figcaption class="wp-element-caption">PrivKey = b6c1238de89e9defea3ea0712e08726e338928ac657c3409ebb93d9a0873797f</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>讓我們打開&nbsp;<a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">bitaddress</a>&nbsp;並檢查：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 15HvLBX9auG2bJdLCTxSvjvWvdgsW7BvAT
WIF:  L3LxjEnwKQMFYNYmCGzM1TqnwxRDi8UyRzQpVfmDvk96fYN44oFG
HEX:  b6c1238de89e9defea3ea0712e08726e338928ac657c3409ebb93d9a0873797f</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/82b/5e1/157/82b5e115789ac3949bbe28bb975a2826.png" alt="通過 ECDSA 短簽名恢復比特幣錢包"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><strong>找到私鑰！</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>比特幣錢包恢復了！</strong></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/50f/e20/dbc/50fe20dbc6d9d6f4a4dbf43c6eaba268.png" alt="通過 ECDSA 短簽名恢復比特幣錢包"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>Короткие подписи ECDSA</code>是<em>丟失硬幣的潛在威脅</em>&nbsp;<code>BTC</code>，<em>因此我們強烈建議大家始終更新軟件並僅使用經過驗證的設備。</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>該視頻是為&nbsp;<a href="https://cryptodeep.ru/" target="_blank" rel="noreferrer noopener"><strong>CRYPTO DEEP TECH</strong></a>門戶網站創建的&nbsp;，以確保橢圓曲線上的數據和密碼學的金融安全性&nbsp;免受&nbsp;加密貨幣中&nbsp;<code>secp256k1</code>&nbsp;弱簽名的影響&nbsp;<code>ECDSA</code><code>BITCOIN</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/tree/main/09BitcoinWalletRecovery" target="_blank" rel="noreferrer noopener"><strong>來源</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://t.me/cryptodeeptech"><strong>電報</strong></a><strong>：&nbsp; https:&nbsp;</strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener"><strong><u>//t.me/cryptodeeptech</u></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://youtu.be/xBgjWE5tA7Y" target="_blank" rel="noreferrer noopener">視頻素材：https://youtu.be/xBgjWE5tA7Y</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/shortest-ecdsa-signature" target="_blank" rel="noreferrer noopener"><strong>來源：https://cryptodeep.ru/shortest-ecdsa-signature</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">密碼分析</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2408} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/03/013-1024x576.png" alt="Восстановление Биткоин Кошелька через короткие подписи ECDSA" class="wp-image-2408"/></figure>
<!-- /wp:image -->
