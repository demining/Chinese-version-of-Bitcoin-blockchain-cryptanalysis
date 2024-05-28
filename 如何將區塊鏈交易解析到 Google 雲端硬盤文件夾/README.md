<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/ECAPypsmMQs","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/ECAPypsmMQs
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>在本文中，我們將分析比特幣交易並學習如何從區塊鍊網絡快速解析 RawTX 到 Google Drive 文件夾，所有這些將幫助我們更好地了解比特幣交易的工作原理以及區塊鍊網絡上的所有內容。<br>首先，我們需要知道所有的比特幣交易都存儲在 [txid] 中。</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>txid</strong>&nbsp;是存儲在比特幣區塊鏈上的交易 ID，RawTX 以雙哈希的形式存儲。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>這意味著 RawTX 兩次通過 SHA256 算法以獲得我們在區塊鏈上看到的交易哈希。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>例如，具有此哈希的事務：&nbsp;&nbsp;<a href="https://www.blockchain.com/btc/tx/d76641afb4d0cc648a2f74db09f86ea264498341c49434a933ba8eef9352ab6f" target="_blank" rel="noreferrer noopener">d76641afb4d0cc648a2f74db09f86ea264498341c49434a933ba8eef9352ab6f</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>比特幣區塊鏈上的交易以雙哈希的形式存儲：</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>SHA256(SHA256(0100000001f2068914e2fea859cacd8df990daf4008f11296b3cb953794051147a265d850a000000008b483045022043784344e1e0cb498c1d73b4cee970fb0f9adf38b7891d0b1310fdb9cbc23929022100a734f4e97a05bd169a9f0eb296fc841fa57f8753db09869f8f6f8cc1232616d4014104d6597d465408e6e11264c116dd98b539740e802dc756d7eb88741696e20dfe7d3588695d2e7ad23cbf0aa056d42afada63036d66a1d9b97070dd6bc0c87ceb0dffffffff0100b864d9450000001976a9142df31a60b02cce392822c9a87198753578ef7de888ac00000000) = d76641afb4d0cc648a2f74db09f86ea264498341c49434a933ba8eef9352ab6f</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>要獲取 RawTX，我們只需要輸入交易 ID [txid]，</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://blockchain.info/rawtx/[txid]?format=hex">https://blockchain.info/rawtx/[txid]?format=hex</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>此外，我們將收到 HEX 格式的信息，這是我們珍愛的 RawTX。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://blockchain.info/rawtx/d76641afb4d0cc648a2f74db09f86ea264498341c49434a933ba8eef9352ab6f?format=hex">https://blockchain.info/rawtx/d76641afb4d0cc648a2f74db09f86ea264498341c49434a933ba8eef9352ab6f?format=hex</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>但正如我們所知，一個比特幣地址中可能有很多交易 [txid]，這是主要問題，它需要花費大量時間來查找、加載我們的 PC 並佔用大量磁盤空間。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>要解決此問題，只需使用&nbsp;<code>API</code>&nbsp;網站&nbsp;<strong><a href="https://chain.so/api/" target="_blank" rel="noreferrer noopener">https://chain.so/api/</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>因此，我們在 bash 腳本中指定一個比特幣地址：&nbsp;<code>getrawtx.sh «address»</code>&nbsp;然後我們提取整個先前的輸出哈希值——所有輸入都參考輸出&nbsp;<code>(UTXO)</code></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>UTXO</strong>&nbsp;是&nbsp;&nbsp;將用於新輸入的&nbsp;<em>（未花費的交易輸出） 。</em><em>其哈希值&nbsp;</em><code>UTXO</code><em>&nbsp;倒序存儲。</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>結果，所有未花費的交易輸出將存儲在一個文件中：&nbsp;<code>«RawTX.json»</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>要獲取&nbsp;<code>RawTX</code>&nbsp;比特幣地址，請使用&nbsp;<strong><a href="https://github.com/demining/CryptoDeepTools/blob/main/01BlockchainGoogleDrive/getrawtx.sh" target="_blank" rel="noreferrer noopener">Bash 腳本：getrawtx.sh</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/7e4/268/a3a/7e4268a3ab7e36fc45020c6b222b7611.png" alt="在 Google Drive 中解析區塊鏈" title="在 Google Drive 中解析區塊鏈"/><figcaption class="wp-element-caption">在 Google Drive 中解析區塊鏈</figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3>如何解析到 Google Drive 文件夾？</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>為此，您可以使用 Google Colab 終端&nbsp;<strong><a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener">[TerminalGoogleColab]</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>早些時候我錄製了一個視頻教程：&nbsp;&nbsp;<a href="https://www.youtube.com/watch?v=S2D7PI6dK08" target="_blank" rel="noreferrer noopener">“Google Colab 中的 TERMINAL 為在 GITHUB 中工作創造了所有便利”</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>讓我們仔細看看 Bash 腳本是如何工作的：getrawtx.sh</h2>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/060/833/01b/06083301bd4339d46a9a62e3d8bd606c.png" alt="Bash 腳本：getrawtx.sh" title="Bash 腳本：getrawtx.sh"/><figcaption class="wp-element-caption">Bash 腳本：getrawtx.sh</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>./getrawtx.sh 12ib7dApVFvg82TXKycWBNpN8kFyiAN1dr</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>Bitcoin 我們為實用</em>命令指定的地址&nbsp;<em></em>&nbsp;<code>wget</code></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/b68/785/9f6/b687859f62fd52efdfe6b536cf3040be.png" alt="如何將區塊鏈交易解析到 Google 雲端硬盤文件夾"/></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/338/b5b/10e/338b5b10ebb67a28ce79bcabb7ed4925.png" alt="所有內容都保存到文件：index.json" title="所有內容都保存到文件：index.json"/><figcaption class="wp-element-caption">所有內容都保存到文件：index.json</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://chain.so/api/v2/get_tx_spent/BTC/12ib7dApVFvg82TXKycWBNpN8kFyiAN1dr">https://chain.so/api/v2/get_tx_spent/BTC/12ib7dApVFvg82TXKycWBNpN8kFyiAN1dr</a></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/073/505/252/07350525294fb491a864ca1d19c4c0f5.png" alt="grep 實用程序將所有“txid”交易 ID 保存到一個通用的 index2.json 文件中  " title="grep 實用程序將所有“txid”交易 ID 保存到一個通用的 index2.json 文件中  "/><figcaption class="wp-element-caption">grep 實用程序將所有交易 ID“txid”保存到一個公共文件 index2.json 中</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/b0e/fa6/edb/b0efa6edbf242f2f6f70bc1cc8b87640.png" alt="所有內容都保存到文件：index2.json" title="所有內容都保存到文件：index2.json"/><figcaption class="wp-element-caption">所有內容都保存到文件：index2.json</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/4cb/904/b7a/4cb904b7a36460710dd6d51679c8317f.png" alt="刪除 index.json" title="刪除 index.json"/><figcaption class="wp-element-caption">刪除 index.json</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/395/b95/c44/395b95c44bc13e60cbc0abb38c38108b.png" alt="使用 sed 實用程序，刪除“txid”前綴和引號逗號" title="使用 sed 實用程序，刪除“txid”前綴和引號逗號"/><figcaption class="wp-element-caption">使用 sed 實用程序，刪除“txid”前綴和引號逗號</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/951/b67/986/951b6798689d0b357259abf07e711b5a.png" alt="文件中的最終結果：index2.json" title="文件中的最終結果：index2.json"/><figcaption class="wp-element-caption">文件中的最終結果：index2.json</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/375/856/5cf/3758565cfb656de3fcc0069574fbd93c.png" alt="使用 Echo 實用程序創建 Python 腳本" title="使用 Echo 實用程序創建 Python 腳本"/><figcaption class="wp-element-caption">使用 Echo 實用程序創建 Python 腳本</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/9f0/a0f/a55/9f0a0fa556623a5c9e436c0f0c118161.png" alt="運行 Python 腳本文件 open.py" title="運行 Python 腳本文件 open.py"/><figcaption class="wp-element-caption">運行 Python 腳本文件 open.py</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/8cf/23f/c9c/8cf23fc9ce47c1fc907eb723b13c7c23.png" alt="運行 Python 腳本文件 open.py 後，創建 Bash 腳本 rawscript.sh" title="運行 Python 腳本文件 open.py 後，創建 Bash 腳本 rawscript.sh"/><figcaption class="wp-element-caption">運行 Python 腳本文件 open.py 後，創建 Bash 腳本 rawscript.sh</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/35a/f1b/200/35af1b20063d6255c73c95b6628cd111.png" alt="刪除 index2.json" title="刪除 index2.json"/><figcaption class="wp-element-caption">刪除 index2.json</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/e63/b09/091/e63b090910e9e2e08d47b61d0ceb065c.png" alt="我們獲得了 Bash 腳本 rawscript.sh 的權限並成功運行了它！" title="我們獲得了 Bash 腳本 rawscript.sh 的權限並成功運行了它！"/><figcaption class="wp-element-caption">我們獲得了 Bash 腳本 rawscript.sh 的權限並成功運行了它！</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/f03/a8d/9c2/f03a8d9c2ecb1e3576e388c59bf33374.png" alt="刪除腳本 fileopen.py // rawscript.sh" title="刪除腳本 fileopen.py // rawscript.sh"/><figcaption class="wp-element-caption">刪除腳本 fileopen.py // rawscript.sh</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/e91/ddd/baa/e91dddbaa475462a42032e3b0f87cbc5.png" alt="所有交易都保存在文件中：“RawTX.json”" title="所有交易都保存在文件中：“RawTX.json”"/><figcaption class="wp-element-caption">所有交易都保存在文件中：“RawTX.json”</figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>結果我們得到什麼優勢：</h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>RawTX 解析速度很快，所有內容都保存在 Google 雲端硬盤文件夾中的一個文件中</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>不像getrawtransaction命令&nbsp;<code>«txid»</code>，在控制台&nbsp;<code>Bitcoin Сore</code>&nbsp;我們不需要輸入，&nbsp;<code>«txid»</code>&nbsp;直接輸入比特幣地址&nbsp;<a href="https://github.com/demining/CryptoDeepTools/tree/main/01BlockchainGoogleDrive" target="_blank" rel="noreferrer noopener">getrawtx.sh "address"</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>bash 腳本：&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/tree/main/01BlockchainGoogleDrive" target="_blank" rel="noreferrer noopener">getrawtx.sh</a>&nbsp;通過&nbsp;站點&nbsp;<a href="https://chain.so/api/" target="_blank" rel="noreferrer noopener">API&nbsp;</a><a href="https://chain.so/api/" target="_blank" rel="noreferrer noopener">https://chain.so/api/</a>&nbsp;找到未花費的交易輸出&nbsp;<a href="https://chain.so/api/">&nbsp;</a><a href="https://chain.so/api/" target="_blank" rel="noreferrer noopener"></a><code>(UTXO)</code></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><strong>源代碼：&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/tree/main/01BlockchainGoogleDrive" target="_blank" rel="noreferrer noopener">https://github.com/demining/CryptoDeepTools/tree/main/01BlockchainGoogleDrive</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>電報：&nbsp; https:&nbsp;<a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">//t.me/cryptodeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>視頻素材：&nbsp; https:&nbsp;<a href="https://youtu.be/ECAPypsmMQs" target="_blank" rel="noreferrer noopener">//youtu.be/ECAPypsmMQs</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/ECAPypsmMQs","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/ECAPypsmMQs
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">密碼分析</a></p>
<!-- /wp:paragraph -->
