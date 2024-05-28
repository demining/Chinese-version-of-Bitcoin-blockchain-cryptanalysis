<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/BYd-cuFRZmM","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/BYd-cuFRZmM
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p><a href="https://github.com/tcatm" target="_blank" rel="noreferrer noopener"><strong>在</strong></a>本文中，我們將討論從比特幣區塊鏈中提取簽名值&nbsp;，但首先，讓我們記住由<a href="https://github.com/tcatm" target="_blank" rel="noreferrer noopener">Niels Schneider</a>&nbsp;&nbsp;（<em>又名</em>&nbsp;tcatm&nbsp;&nbsp;）<code>ECDSA R, S, Z</code>&nbsp;發現的區塊鏈交易中的第一個嚴重漏洞&nbsp;<a href="https://github.com/tcatm" target="_blank" rel="noreferrer noopener"></a><code>Nils Schneider</code>&nbsp;<em></em><a href="https://github.com/tcatm" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>比特幣開發商和&nbsp;<em>“BitcoinWatch”</em>&nbsp;和&nbsp;<em>“BitcoinCharts”的所有者。</em></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/20d/674/8c4/20d6748c4bdd5e28ada4e9d06b9e8d35.png" alt="4.1 比特幣危險隨機攻擊的歷史" title="4.1 比特幣危險隨機攻擊的歷史"/><figcaption class="wp-element-caption">4.1 比特幣危險隨機攻擊的歷史</figcaption></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>文檔&nbsp;<code>[PDF]</code>：<a href="https://eprint.iacr.org/2014/848.pdf" target="_blank" rel="noreferrer noopener"><em>私鑰恢復組合攻擊：在存在不良 RNG 事件的情況下流行的比特幣密鑰管理、錢包和冷存儲解決方案的極端脆弱性</em></a><a href="https://eprint.iacr.org/2014/848.pdf" target="_blank" rel="noreferrer noopener">&nbsp;<em></em></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><em>2012 年 12 月 25 日，</em>&nbsp;&nbsp;Nils 發現了一些比特幣區塊鏈交易的潛在弱點。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>看看這個交易：</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>transaction:</code>&nbsp;<a href="https://www.blockchain.com/btc/tx/9ec4bc49e828d924af1d1029cacf709431abbde46d59554b62bc270e3b29c4b1" target="_blank" rel="noreferrer noopener">9ec4bc49e828d924af1d1029cacf709431abbde46d59554b62bc270e3b29c4b1</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/cc3/2e2/94a/cc32e294aa0e77019d1581ce61893349.png" alt="區塊鏈中的第一個嚴重漏洞以及如何從 RawTX 文件中獲取公鑰比特幣 ECDSA RSZ 值"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>input script 1:
30440220d47ce4c025c35ec440bc81d99834a624875161a26bf56ef7fdc0f5d52f843ad1022044e1ff2dfd8102cf7a47c21d5c9fd5701610d04953c6836596b4fe9dd2f53e3e0104dbd0c61532279cf72981c3584fc32216e0127699635c2789f549e0730c059b81ae133016a69c21e23f1859a95f06d52b7bf149a8f2fe4e8535c8a829b449c5ff

input script 2:
30440220d47ce4c025c35ec440bc81d99834a624875161a26bf56ef7fdc0f5d52f843ad102209a5f1c75e461d7ceb1cf3cab9013eb2dc85b6d0da8c3c6e27e3a5a5b3faa5bab0104dbd0c61532279cf72981c3584fc32216e0127699635c2789f549e0730c059b81ae133016a69c21e23f1859a95f06d52b7bf149a8f2fe4e8535c8a829b449c5ff</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>該交易有兩個輸入和一個輸出。<br>如果仔細觀察這兩個輸入腳本，您會注意到在開頭和結尾有相當多的相同字節。<br>末尾的那些字節是硬幣所花地址的十六進制編碼公鑰，所以這沒有錯。<br>但是，腳本的前半部分是實際簽名&nbsp;<code>(r, s)</code>：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>r1: d47ce4c025c35ec440bc81d99834a624875161a26bf56ef7fdc0f5d52f843ad1
r2: d47ce4c025c35ec440bc81d99834a624875161a26bf56ef7fdc0f5d52f843ad1

s1: 44e1ff2dfd8102cf7a47c21d5c9fd5701610d04953c6836596b4fe9dd2f53e3e
s2: 9a5f1c75e461d7ceb1cf3cab9013eb2dc85b6d0da8c3c6e27e3a5a5b3faa5bab</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>正如你所看到的，&nbsp;<code>r1</code>&nbsp;它是一樣的&nbsp;<code>r2</code>。&nbsp;<em>這是&nbsp;</em><strong><em><u>一個巨大的問題</u></em></strong><em>。</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>我們可以將&nbsp;<strong><u>私鑰</u></strong>還原&nbsp;為這個公鑰：</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>04dbd0c61532279cf72981c3584fc32216e0127699635c2789f549e0730c059b81ae133016a69c21e23f1859a95f06d52b7bf149a8f2fe4e8535c8a829b449c5ff</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>為此，我們可以使用學校代數中的一個簡單公式😉</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>private key = (<strong>z1*s2</strong> - z2*s1)/(<strong>r*</strong>(<strong>s1-s2</strong>))</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>我們只需要找到&nbsp;<code>z1</code>&nbsp;並&nbsp;<code>z2</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>這些是&nbsp;<code>хэши</code>&nbsp;需要簽名的輸出。讓我們獲取輸出交易並對它們進行計數（由 計算&nbsp;<code>OP_CHECKSIG</code>）：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>z1: c0e2d0a89a348de88fda08211c70d1d7e52ccef2eb9459911bf977d587784c6e
z2: 17b0f41c8c337ac1e18c98759e83a8cccbc368dd9d89e5f03cb633c265fd0ddc</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>接下來，讓我們將所有這些值打包到一個&nbsp;<em>Python</em>腳本中<em>：</em>&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/vulnerabilityR.py" target="_blank" rel="noreferrer noopener">vulnerabilityR.py</a></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/c5f/301/358/c5f301358b79c833d7701b7c883235a7.png" alt="Python腳本：vulnerabilityR.py" title="Python腳本：vulnerabilityR.py"/><figcaption class="wp-element-caption">Python腳本：vulnerabilityR.py</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>p</code>&nbsp;只是一個數量級&nbsp;，是比特幣使用的<code>G</code>曲線參數&nbsp;。<code>secp256k1</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>讓我們為計算創建一個字段：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>K = GF(<strong>p</strong>)</code></pre>
<!-- /wp:code -->

<!-- wp:code -->
<pre class="wp-block-code"><code>K((<strong>z1*s2</strong> - z2*s1)/(<strong>r*</strong>(<strong>s1-s2</strong>)))</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>讓我們運行腳​​本：&nbsp;<code>python3 vulnerabilityR.py</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>接下來，我們的腳本：&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/vulnerabilityR.py" target="_blank" rel="noreferrer noopener">vulnerabilityR.py</a>&nbsp;將計算&nbsp;該字段中的<strong><u>私鑰</u></strong>&nbsp;：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 1BFhrfTTZP3Nw4BNy4eX4KFLsn9ZeijcMm
WIF:  5KJp7KEffR7HHFWSFYjiCUAntRSTY69LAQEX1AUzaSBHHFdKEpQ
hex:  c477f9f65c22cce20657faa5b2d1d8122336f851a508a1ed04e479c34985bf96</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/a69/992/dcf/a69992dcf93bacd0324c9a06722be9b5.png" alt="在bitaddress網站上查看私鑰" title="在bitaddress網站上查看私鑰"/><figcaption class="wp-element-caption">在bitaddress網站上查看私鑰</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><em><u>找到私鑰！</u></em></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.blockchain.com/btc/address/1BFhrfTTZP3Nw4BNy4eX4KFLsn9ZeijcMm"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/btc/address/1BFhrfTTZP3Nw4BNy4eX4KFLsn9ZeijcMm
</div></figure>
<!-- /wp:embed -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/049/126/899/049126899d0dc2b84a30b18fc496c258.png" alt="
0.1638109比特幣" title="
0.1638109比特幣"/><figcaption class="wp-element-caption">0.1638109比特幣</figcaption></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>當然，比特幣的開發者通過引入確定性函數修復了這個漏洞。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>此功能&nbsp;<code>RFC 6979</code>&nbsp;在比特幣簽名中引入了隨機性元素，從而增強了交易的加密強度。&nbsp;<code>ECDSA</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>文檔&nbsp;<code>[PDF]</code>：<a href="https://datatracker.ietf.org/doc/html/rfc6979" target="_blank" rel="noreferrer noopener"><em>RFC 6979：數字簽名算法 (DSA) 和橢圓曲線數字簽名算法 (ECDSA) 的確定性使用</em></a><a href="https://eprint.iacr.org/2014/848.pdf">&nbsp;</a><a href="https://datatracker.ietf.org/doc/html/rfc6979" target="_blank" rel="noreferrer noopener"><em></em></a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>正如我們在實踐中所知，比特幣區塊鏈中存在完全不同的易受攻擊的交易。</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>我們之前發布過&nbsp;<code>статью</code>：&nbsp;&nbsp;<a href="https://cryptodeep.ru/lattice-attack/" target="_blank" rel="noreferrer noopener"><em>“比特幣區塊鏈上 ECDSA 中的一次弱交易，在 Lattice Attack 的幫助下，我們收到了 BTC 硬幣的私鑰”</em></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://cryptodeep.ru/lattice-attack/" target="_blank" rel="noreferrer noopener"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/6b8/723/07d/6b872307d4a4dc3a74386c2b83d133a2.png" alt="https://habr.com/ru/post/671932/" title="https://habr.com/ru/post/671932/"/></a></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>現在讓我們從&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/RawTX.json" target="_blank" rel="noreferrer noopener">“RawTX.json”</a>文件&nbsp;（我們在&nbsp;<a href="https://github.com/demining/CryptoDeepTools/tree/main/01BlockchainGoogleDrive" target="_blank" rel="noreferrer noopener"><strong>01BlockchainGoogleDrive</strong></a>中獲得&nbsp;）中獲取公鑰&nbsp;<code>Bitcoin</code>&nbsp;<code>ECDSA</code>&nbsp;和價值&nbsp;<code>R, S, Z</code><a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/RawTX.json" target="_blank" rel="noreferrer noopener"></a><a href="https://github.com/demining/CryptoDeepTools/tree/main/01BlockchainGoogleDrive" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>為此，請使用 Google Colab 的終端&nbsp;<a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener">[&nbsp;<strong>TerminalGoogleColab]</strong></a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>早些時候我錄製了一個視頻：&nbsp;&nbsp;<a href="https://www.youtube.com/watch?v=S2D7PI6dK08" target="_blank" rel="noreferrer noopener"><strong>“Google Colab 中的 TERMINAL 為在 GITHUB 中工作創造了所有便利”</strong></a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>讓我們通過&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography" target="_blank" rel="noreferrer noopener"><strong>“CryptoDeepTools”</strong></a>存儲庫&nbsp;進行詳細的密碼分析，並仔細研究&nbsp;<em>Bash 腳本</em>的工作原理：&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/getsign.sh" target="_blank" rel="noreferrer noopener">getsign.sh</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>團隊：</strong></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:code -->
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/02BreakECDSAcryptography/

sudo apt install python2-minimal

wget https://bootstrap.pypa.io/pip/2.7/get-pip.py

sudo python2 get-pip.py

pip2 install -r requirements.txt

chmod +x getsign.sh

./getsign.sh</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/9bf/c35/0c7/9bfc350c715272db79f6bd5c6039e924.png" alt="文件" title="文件"/><figcaption class="wp-element-caption">文件</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/5f0/cf5/6f0/5f0cf56f00c897f69fab24e8a3073588.png" alt="我們的 Bash 腳本代碼：getsign.sh" title="我們的 Bash 腳本代碼：getsign.sh"/><figcaption class="wp-element-caption">我們的 Bash 腳本代碼：getsign.sh</figcaption></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>因此，讓我們詳細了解一下&nbsp;<em>Bash 腳本</em>的全部工作：&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/getsign.sh" target="_blank" rel="noreferrer noopener">getsign.sh</a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat RawTX.json &gt; index.json</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>將文件複製&nbsp;<code>RawTX.json</code>&nbsp;到新文件中&nbsp;<code>index.json</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>for</strong> run <strong>in</strong> {1..4}; <strong>do</strong></code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>我們打開它是&nbsp;<code>ЦИКЛ</code>&nbsp;因為&nbsp;&nbsp;我們在文件中取了&nbsp;<code>index.json</code>&nbsp;<em>4 行</em><code>{1..4}</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>export LINE=1 ; sed -n "${LINE}p" index.json &gt; index2.json</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>該實用程序&nbsp;<code>export</code>&nbsp;採用&nbsp;<em>第 1 行</em>&nbsp;並將其保存在新文件中&nbsp;<code>index2.json</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sed -i '1d' index.json</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>該實用程序&nbsp;從文件中&nbsp;<code>sed</code>&nbsp;刪除&nbsp;<em>第 1 行&nbsp;</em><code>index.json</code></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/972/d1b/555/972d1b5554e84191da57b16415061198.png" alt="echo 實用程序為我們創建一個 Python 腳本 fileopen.py" title="echo 實用程序為我們創建一個 Python 腳本 fileopen.py"/><figcaption class="wp-element-caption">echo 實用程序為我們創建一個 Python 腳本 fileopen.py</figcaption></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 fileopen.py</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>我們運行&nbsp;<em>Python 腳本</em>&nbsp;<code>fileopen.py</code>&nbsp;並成功創建了一個新的&nbsp;<em>Bash 腳本</em>：&nbsp;<code>signscript.sh</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>chmod +x signscript.sh
./signscript.sh</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>我們獲得了Bash 腳本</em>的權限&nbsp;：signscript.sh</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>結果，&nbsp;啟動了<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/breakECDSA.py" target="_blank" rel="noreferrer noopener">breakECDSA.py&nbsp;</a><em>Python 腳本</em>&nbsp;&nbsp;，最終從中提取了&nbsp;比特幣的價值&nbsp;&nbsp;和公鑰。<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/breakECDSA.py" target="_blank" rel="noreferrer noopener"></a><code>RawTX</code><code>R, S, Z</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>所有這些都保存到一個文件中：&nbsp;<code>"signatures.json"</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/2e1/9df/c27/2e19dfc270a6f0bc6bd2ea9123215442.png" alt="文件：“signatures.json”比特幣公鑰和R、S、Z值" title="文件：“signatures.json”比特幣公鑰和R、S、Z值"/><figcaption class="wp-element-caption">文件：“signatures.json” 比特幣公鑰和 R、S、Z 值</figcaption></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>rm</strong> <strong>signscript</strong>.sh
<strong>rm</strong> <strong>fileopen</strong>.py</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>該實用程序&nbsp;<code>rm</code>&nbsp;刪除了&nbsp;<em>Python 腳本</em>&nbsp;<code>fileopen.py</code>&nbsp;並成功創建了一個新的&nbsp;<em>Bash 腳本</em>：&nbsp;<code>signscript.sh</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>done</strong></code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>結果，<em>&nbsp;4個週期後一切結束</em></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>rm <strong>index</strong>.json</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>循環結束，實用程序&nbsp;<code>rm</code>&nbsp;刪除&nbsp;<code>index.json</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>Bash 腳本</em>：&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/getsign.sh" target="_blank" rel="noreferrer noopener">getsign.sh</a>&nbsp;<code>Завершает работу!</code></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>現在我們了解到：</h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>Bitcoin&nbsp;</code>從中獲取公鑰&nbsp;<code>&nbsp;ECDSA</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>R, S, Z</code>&nbsp;從中獲取價值&nbsp;<code>&nbsp;ECDSA</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>申請它&nbsp;<code>криптоанализа</code></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><strong>源代碼：&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography" target="_blank" rel="noreferrer noopener">https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>電報：&nbsp; https:&nbsp;<a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">//t.me/cryptodeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>視頻素材：&nbsp; https:&nbsp;<a href="https://youtu.be/BYd-cuFRZmM" target="_blank" rel="noreferrer noopener">//youtu.be/BYd-cuFRZmM</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/BYd-cuFRZmM","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/BYd-cuFRZmM
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">密碼分析</a></p>
<!-- /wp:paragraph -->
