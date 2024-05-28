<!-- wp:embed {"url":"https://www.youtube.com/embed/UGUJyxOhBBQ","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/UGUJyxOhBBQ
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>在本文中，我們將從計算數論領域來看 ECDLP 最快的算法，Pollard 的袋鼠算法也稱為 Pollard 的 lambda 算法。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Pollard 的袋鼠法計算&nbsp;任意循環群中的<a href="https://cryptodeep.ru/doc/discretelog.pdf" target="_blank" rel="noreferrer noopener"><strong>離散對數</strong></a>&nbsp;。<code>[ a , b ]</code>如果已知離散對數位於某個範圍內（例如 ） ，然後具有執行批量操作的預期時間，則應用它&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>波拉德的袋鼠優勢：</h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>使用很少的內存</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>可以與線性加速並行</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>可以有效地跟踪內存需求</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>所有這些使得袋鼠法成為解決離散對數問題最強大的方法。</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading -->
<h2>破解 ECDSA 簽名方案的一種方法是解決離散對數問題。</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>在設置中，&nbsp;不使用指數演算法等次指數時間算法，&nbsp;波拉德袋鼠法是<code>ECDSA</code>&nbsp;它們背後最著名的求解方法&nbsp;。<code>DLP</code>我們將盡量不給您增加各種理論方面的負擔。讓我們繼續進行實驗部分。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>正如我們在比特幣區塊鏈中所知，BTC 硬幣的發送者總是會洩露他的&nbsp;<em>公鑰</em>。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>&nbsp;對於&nbsp;Pollard袋鼠法，知道&nbsp;<em>公鑰或者</em><em>簽名</em>&nbsp;&nbsp;值&nbsp;就足夠了<code>R</code>&nbsp;（值&nbsp;<code>R</code>&nbsp;也是一種&nbsp;<em>公鑰</em>，因為它是&nbsp;橢圓曲線平面上的&nbsp;<code>Nonces</code>&nbsp;坐標點&nbsp;）<code>x</code><code>secp256k1</code></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>它仍然只是定義範圍</em>&nbsp;<code>PRIVATE KEY</code>&nbsp;<em>或範圍</em>&nbsp;<code>NONCES</code>。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>碰巧一些<code>ECDSA</code>在比特幣區塊鏈中創建簽名的設備可以部分洩露有關價值的信息字節&nbsp;<code>"K" (NONCES)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>我們認為這是丟失 BTC 硬幣的潛在威脅，並強烈建議每個人始終更新軟件並僅使用經過驗證的設備。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>最近，我們對比特幣區塊鏈進行了密碼分析，發現了幾筆這樣的交易。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>那麼看看這個提款金額為501.06516041 BTC的比特幣地址</h2>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/3d9/756/d50/3d9756d50d09b0584c5967175184dd42.png" alt="Pollard's Kangaroo 在已知範圍內找到離散對數 secp256k1 PRIVATE KEY + NONCES 的解" title=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://btc.exan.tech/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE" target="_blank" rel="noreferrer noopener"><strong>在這個比特幣地址14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE</strong></a>的交易中&nbsp;，部分洩露了有關價值的字節信息&nbsp;<code>"K" (NONCES)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>正如我們從上一篇&nbsp;<a href="https://cryptodeep.ru/lattice-attack/" target="_blank" rel="noreferrer noopener"><strong><u>文章中了解到的</u></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/2f6/78f/d0f/2f678fd0faefca8c25518666490d795f.png" alt="habr.com/ru/post/671932/" title="habr.com/ru/post/671932/"/><figcaption class="wp-element-caption">habr.com/ru/post/671932/</figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>查找密鑰範圍</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>讓我們找到這筆交易並使用Pollard的袋鼠方法&nbsp;<em><u>來恢復私鑰</u></em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>之前，我們錄製了&nbsp;<em>一個視頻教程</em>：&nbsp;&nbsp;<a href="https://cryptodeep.ru/terminal-google-colab/" target="_blank" rel="noreferrer noopener">“Google Colab 中的 TERMINAL 創造了在 GITHUB 中工作的所有便利”</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/TerminalGoogleColab"><strong>在終端[TerminalGoogleColab]</strong></a>中打開 Google Colab&nbsp;<a href="https://github.com/demining/TerminalGoogleColab"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>要搜索 RawTX，我們將使用存儲庫&nbsp;<a href="https://github.com/demining/CryptoDeepTools/tree/main/01BlockchainGoogleDrive" target="_blank" rel="noreferrer noopener">“01BlockchainGoogleDrive”</a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/01BlockchainGoogleDrive/

chmod +x getrawtx.sh

./getrawtx.sh 14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/496/30f/b12/49630fb12d6c1cf64f99f24f530add95.png" alt="運行 Bash 腳本：getrawtx.sh" title="運行 Bash 腳本：getrawtx.sh"/><figcaption class="wp-element-caption">運行 Bash 腳本：getrawtx.sh</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>比特幣地址&nbsp;<a href="https://btc.exan.tech/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE" target="_blank" rel="noreferrer noopener">14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE</a>交易的所有內容都&nbsp;保存到文件中：&nbsp;<code>RawTX.json</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>打開文件：&nbsp;<code>RawTX.json</code>&nbsp;找到這個交易&nbsp;<code>[строка №10]</code></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/2c1/dca/207/2c1dca20782c1e09325836c491aeaaf0.png" alt="Pollard's Kangaroo 在已知範圍內找到離散對數 secp256k1 PRIVATE KEY + NONCES 的解"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>讓我們使用命令&nbsp;<code>export</code>&nbsp;並將這一行&nbsp;<code>№10</code>&nbsp;從&nbsp;<code>RawTX.json</code>單獨保存到&nbsp;<code>RawTX.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>export LINE=10 ; sed -n "${LINE}p" RawTX.json &gt; RawTX.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/b8b/0c2/508/b8b0c25080dfe2ad36c112e2f0015e72.png" alt="Pollard's Kangaroo 在已知範圍內找到離散對數 secp256k1 PRIVATE KEY + NONCES 的解"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat RawTX.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/b1a/a44/976/b1aa44976ad24df74e02246a8747db31.png" alt="Pollard's Kangaroo 在已知範圍內找到離散對數 secp256k1 PRIVATE KEY + NONCES 的解"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>讓我們找出來&nbsp;<code>TxID</code>&nbsp;，打開&nbsp;<a href="https://live.blockcypher.com/btc/decodetx/" target="_blank" rel="noreferrer noopener"><strong>Decode Raw Bitcoin Hexadecimal Transaction</strong></a>網站&nbsp;並插入我們的&nbsp;<code>RawTX</code>結果，我們得到 TxID</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/166/292/2df/1662922df068e4d009f0efcbecc2089d.png" alt="Pollard's Kangaroo 在已知範圍內找到離散對數 secp256k1 PRIVATE KEY + NONCES 的解"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":4} -->
<h4>結果，我們得到 TxID</h4>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/cc2/bf5/146/cc2bf5146ef7a2e6004d79986535255d.png" alt="TxID：b5add54960756c58ebabb332c5ef89098d2c3b8f2107b939ec542178e846108b" title="TxID：b5add54960756c58ebabb332c5ef89098d2c3b8f2107b939ec542178e846108b"/><figcaption class="wp-element-caption">TxID：b5add54960756c58ebabb332c5ef89098d2c3b8f2107b939ec542178e846108b</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>打開鏈接TxID：<br><a href="https://btc.exan.tech/tx/b5add54960756c58ebabb332c5ef89098d2c3b8f2107b939ec542178e846108b" target="_blank" rel="noreferrer noopener">https://btc.exan.tech/tx/b5add54960756c58ebabb332c5ef89098d2c3b8f2107b939ec542178e846108b</a></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/c32/5a8/e40/c325a8e40de9ca6f15431dac1dcfe274.png" alt="Pollard's Kangaroo 在已知範圍內找到離散對數 secp256k1 PRIVATE KEY + NONCES 的解"/></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/3b2/8d1/648/3b28d1648bf0cf157833dbc3b0821fd8.png" alt="檢查 RawTX" title="檢查 RawTX"/><figcaption class="wp-element-caption">檢查 RawTX</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>現在我們發現部分洩露了有關值的字節信息&nbsp;<code>"K" (NONCES)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>為此，我們將使用腳本&nbsp;<code>«RangeNonce»</code></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>«RangeNonce»</code>&nbsp;是查找密鑰範圍的腳本</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>讓我們選擇分發工具包的版本&nbsp;<code>GNU/Linux</code>&nbsp;。&nbsp;<code>Google Colab</code>&nbsp;提供&nbsp;<code>UBUNTU 18.04</code></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/94d/d82/af4/94dd82af4d7155e548aa7241df9b3206.png" alt="RangeNonce" title="RangeNonce"/><figcaption class="wp-element-caption">RangeNonce</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>上傳所有文件到&nbsp;<code>Google Colab</code></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/751/91d/9a2/75191d9a233987a74ed0fa016aa5e2a1.png" alt="RangeNonce + Google Colab" title="RangeNonce + Google Colab"/><figcaption class="wp-element-caption">RangeNonce + Google Colab</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>讓我們允許腳本的權限並運行腳本&nbsp;<code>«RangeNonce»</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>團隊：</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>chmod +x RangeNonce
./RangeNonce
cat Result.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/8ff/546/0c3/8ff5460c3570ebbbb3c7fb0f6a394fd9.png" alt="Pollard's Kangaroo 在已知範圍內找到離散對數 secp256k1 PRIVATE KEY + NONCES 的解"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":4} -->
<h4>所有內容都將保存到文件中：Result.txt</h4>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/2af/471/f7e/2af471f7eb46f84157b402ed67ea9139.png" alt="結果.txt" title="結果.txt"/><figcaption class="wp-element-caption">結果.txt</figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>這是“K”(NONCES) 值的部分信息字節公開</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>所以我們的&nbsp;<u>密鑰</u>&nbsp;在&nbsp;<u>範圍</u>內：</em></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>K = 070239c013e8f40c8c2a0e608ae15a6b00000000000000000000000000000000
K = 070239c013e8f40c8c2a0e608ae15a6bffffffffffffffffffffffffffffffff</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/204/ef7/984/204ef79845ae3d93a9c93d43f81e484b.png" alt="Pollard's Kangaroo 在已知範圍內找到離散對數 secp256k1 PRIVATE KEY + NONCES 的解"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>注意</strong>格式開頭的&nbsp;<code>32</code>&nbsp;數字和字母&nbsp;<code>HEX</code>&nbsp;，簽名的值&nbsp;<code>Z</code>&nbsp;匹配&nbsp;<em><u>秘鑰的範圍，</u></em>&nbsp;即值&nbsp;<code>"K" (NONCES)</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading -->
<h2>這是一個非常嚴重的 ECDSA 簽名錯誤</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>上面我們說了，對於Pollard袋鼠法來說，知道&nbsp;<em>公鑰</em>&nbsp;或者<em>&nbsp;簽名</em>&nbsp;<code>R</code>值就足夠了&nbsp;（該值&nbsp;<code>R</code>&nbsp;也是一種&nbsp;<em>公鑰</em>，&nbsp;因為&nbsp;它是&nbsp;橢圓曲線平面上的&nbsp;<code>Nonces</code>&nbsp;一個坐標點&nbsp;）<code>x</code><code>secp256k1</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>我們案例中的簽名</em>&nbsp;值&nbsp;<code>R</code>&nbsp;：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 83fe1c06236449b69a7bee5be422c067d02c4ce3f4fa3756bd92c632f971de06</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>該腳本&nbsp;&nbsp;通過創建&nbsp;<em>壓縮公鑰</em><code>RangeNonce</code>添加了&nbsp;我們需要的&nbsp;<em>前綴</em>&nbsp;<code>02</code><em></em></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>K_PUBKEY = 0283fe1c06236449b69a7bee5be422c067d02c4ce3f4fa3756bd92c632f971de06</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>現在我們有信息：</h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><em>密鑰範圍</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em>壓縮公鑰</em></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>&nbsp;讓我們使用來自法國開發人員 Jean-Luc PONS 的源代碼來構建&nbsp;<a href="https://github.com/demining/CryptoDeepTools/tree/main/06KangarooJeanLucPons" target="_blank" rel="noreferrer noopener"><strong>Pollard 的袋鼠程序</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>請注意，您可以自己組裝&nbsp;<code>CUDA</code>&nbsp;以&nbsp;<code>GPU</code>&nbsp;提高&nbsp;<strong><em><u>計算速度。</u></em></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/afc/280/ae8/afc280ae86d3febb27f1008e8927ae89.png" alt="Pollard's Kangaroo 在已知範圍內找到離散對數 secp256k1 PRIVATE KEY + NONCES 的解"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>我們將對 CPU 進行正常組裝</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>團隊：</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cd /

cd content/CryptoDeepTools/06KangarooJeanLucPons/

ls</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/394/ece/ecf/394eceecf11f26952a6fc87a10be2dbc.png" alt="Pollard's Kangaroo 在已知範圍內找到離散對數 secp256k1 PRIVATE KEY + NONCES 的解"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sudo apt-get update</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/2bc/e90/cd5/2bce90cd55b48787511363f9976adbd6.png" alt="Pollard's Kangaroo 在已知範圍內找到離散對數 secp256k1 PRIVATE KEY + NONCES 的解"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sudo apt-get install g++ -y
sudo apt-get install libgmp3-dev libmpfr-dev -y</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/707/e19/0da/707e190da23fd6b83eead65bce771b5b.png" alt="Pollard's Kangaroo 在已知範圍內找到離散對數 secp256k1 PRIVATE KEY + NONCES 的解"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><em>安裝完所有包後，我們將通過運行一個簡單的命令來構建：</em></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>make</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/663/476/ae3/663476ae36f13e98d23f8ee3e879b545.png" alt="Pollard's Kangaroo 在已知範圍內找到離散對數 secp256k1 PRIVATE KEY + NONCES 的解"/></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/1ea/932/dd2/1ea932dd2bd751c24fa95821c6833523.png" alt="Pollard's Kangaroo 在已知範圍內找到離散對數 secp256k1 PRIVATE KEY + NONCES 的解"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>組裝成功！</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Проверим версию:

./kangaroo -v</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/76d/f52/532/76df5253202c44d068af867a812d11db.png" alt="Pollard's Kangaroo 在已知範圍內找到離散對數 secp256k1 PRIVATE KEY + NONCES 的解"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":4} -->
<h4>因此，我們創建了“Kangaroo v2.2”版本</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>為了演示性能，&nbsp;<code>«Kangaroo v2.2»</code>&nbsp;讓&nbsp;我們<code>CPU</code>提高範圍並將所有內容保存到文件中：&nbsp;<code>rangepubkey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4>打開一個文本文件：rangepubkey.txt</h4>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/8ac/477/f4c/8ac477f4c2423dc5ff4cce2407481540.png" alt="Pollard's Kangaroo 在已知範圍內找到離散對數 secp256k1 PRIVATE KEY + NONCES 的解"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>070239c013e8f40c8c2a0e608ae15a6b23d4a09295be678b2100000000000000
070239c013e8f40c8c2a0e608ae15a6b23d4a09295be678b21ffffffffffffff
0283fe1c06236449b69a7bee5be422c067d02c4ce3f4fa3756bd92c632f971de06</code></pre>
<!-- /wp:code -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Очистим терминал командой:

clear</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>運行&nbsp;<code>«Kangaroo v2.2»</code>&nbsp;結果會&nbsp;<em>自動保存</em>&nbsp;到文件中：&nbsp;<code>savenonce.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./kangaroo -ws -w save.work -wi 30 -o savenonce.txt rangepubkey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/ae8/77a/6f4/ae877a6f49f7781d70cf6a986deea751.png" alt="Pollard's Kangaroo 在已知範圍內找到離散對數 secp256k1 PRIVATE KEY + NONCES 的解"/></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/5eb/0b2/2e3/5eb0b22e395bd62b5a577a37ba2bebef.png" alt="Pollard's Kangaroo 在已知範圍內找到離散對數 secp256k1 PRIVATE KEY + NONCES 的解"/></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/e2d/6a1/e3a/e2d6a1e3ab4cd4bb5be0c58eed1ca6f7.png" alt="Pollard's Kangaroo 在已知範圍內找到離散對數 secp256k1 PRIVATE KEY + NONCES 的解"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>搜索時間用了 1 分鐘。18 秒。</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>文件中的結果：</em>&nbsp;<code>savenonce.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/76b/fb1/f4e/76bfb1f4e28f14cebba9b68c31e510ec.png" alt="Pollard's Kangaroo 在已知範圍內找到離散對數 secp256k1 PRIVATE KEY + NONCES 的解"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><em>讓我們打開</em>&nbsp;文件：&nbsp;<code>savenonce.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/50d/1fd/7ae/50d1fd7aecc8ea69cdb12d8f73830d8b.png" alt="Pollard's Kangaroo 在已知範圍內找到離散對數 secp256k1 PRIVATE KEY + NONCES 的解"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3>我們得到了秘鑰，這是“K”的值（隨機數）</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Key# 0 &#91;1S]Pub:  0x0283FE1C06236449B69A7BEE5BE422C067D02C4CE3F4FA3756BD92C632F971DE06 
       Priv: 0x70239C013E8F40C8C2A0E608AE15A6B23D4A09295BE678B21A5F1DCEAE1F634 


070239C013E8F40C8C2A0E608AE15A6B23D4A09295BE678B21A5F1DCEAE1F634

K = 070239c013e8f40c8c2a0e608ae15a6b00000000000000000000000000000000 # RangeNonce
K = 070239C013E8F40C8C2A0E608AE15A6B23D4A09295BE678B21A5F1DCEAE1F634 # NONCES
K = 070239c013e8f40c8c2a0e608ae15a6bffffffffffffffffffffffffffffffff # RangeNonce</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>私鑰</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>現在知道了價值，&nbsp;<code>"K" (NONCES)</code>&nbsp;我們&nbsp;<em><u>將把私鑰恢復</u></em>&nbsp;到比特幣地址：&nbsp;&nbsp;<a href="https://btc.exan.tech/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE" target="_blank" rel="noreferrer noopener"><strong>14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>讓我們回到開頭，正如我們所記得的那樣，腳本&nbsp;<code>«RangeNonce»</code>&nbsp;向我們揭示了&nbsp;有關值範圍的&nbsp;<em>信息</em><code>"K" (NONCES)</code>，以及&nbsp;<em>信息</em>&nbsp;<code>SIGNATURES</code></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/d71/0d3/fa1/d710d3fa1cf97ab16e33f7f824c2fb87.png" alt="簽名" title="簽名"/><figcaption class="wp-element-caption">簽名</figcaption></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 83fe1c06236449b69a7bee5be422c067d02c4ce3f4fa3756bd92c632f971de06
S = 7405249d2aa9184b688f5307006fddc3bd4a7eb89294e3be3438636384d64ce7
Z = 070239c013e8f40c8c2a0e608ae15a6b1bb4b8fbcab3cff151a6e4e8e05e10b7</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>使用 Python腳本</em>中的公式獲取私鑰：&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/calculate.py" target="_blank" rel="noreferrer noopener">calculate.py</a></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/b40/7d2/80e/b407d280edbe126f6ec21ac1c1ffa539.svg" alt="PRIVKEY = ((((S * K) - Z) *​​ modinv(R,N)) % N)"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>def</strong> <strong>h</strong>(n):
    <strong>return</strong> hex(n).replace("0x","")

<strong>def</strong> <strong>extended_gcd</strong>(aa, bb):
    lastremainder, remainder = abs(aa), abs(bb)
    x, lastx, y, lasty = 0, 1, 1, 0
    <strong>while</strong> remainder:
        lastremainder, (quotient, remainder) = remainder, divmod(lastremainder, remainder)
        x, lastx = lastx - quotient*x, x
        y, lasty = lasty - quotient*y, y
    <strong>return</strong> lastremainder, lastx * (-1 <strong>if</strong> aa &lt; 0 <strong>else</strong> 1), lasty * (-1 <strong>if</strong> bb &lt; 0 <strong>else</strong> 1)

<strong>def</strong> <strong>modinv</strong>(a, m):
    g, x, y = extended_gcd(a, m)
    <strong>if</strong> g != 1:
        <strong>raise</strong> ValueError
    <strong>return</strong> x % m
    
N = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141
R = 0x83fe1c06236449b69a7bee5be422c067d02c4ce3f4fa3756bd92c632f971de06
S = 0x7405249d2aa9184b688f5307006fddc3bd4a7eb89294e3be3438636384d64ce7
Z = 0x070239c013e8f40c8c2a0e608ae15a6b1bb4b8fbcab3cff151a6e4e8e05e10b7
K = 0x070239C013E8F40C8C2A0E608AE15A6B23D4A09295BE678B21A5F1DCEAE1F634

<strong>print</strong> (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>團隊：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>wget https://raw.githubusercontent.com/demining/CryptoDeepTools/main/02BreakECDSAcryptography/calculate.py

python3 calculate.py
</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/803/1f1/189/8031f11893dbb7de1d90858ae8ba634a.png" alt="PRIVKEY=23d4a09295be678b21a5f1dceae1f634a69c1b41775f680ebf81652664714​​01b" title="PRIVKEY=23d4a09295be678b21a5f1dceae1f634a69c1b41775f680ebf81652664714​​01b"/><figcaption class="wp-element-caption">PRIVKEY=23d4a09295be678b21a5f1dceae1f634a69c1b41775f680ebf81652664714​​01b</figcaption></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE
WIF:  5J64pq77XjeacCezwmAr2V1s7snvvJkuAz8sENxw7xCkikceV6e
HEX:  23d4a09295be678b21a5f1dceae1f634a69c1b41775f680ebf8165266471401b</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/d8c/78d/8eb/d8c78d8eb14e5246b495e09f59631e44.png" alt="在bitaddress網站上查看私鑰" title="在bitaddress網站上查看私鑰"/><figcaption class="wp-element-caption">在bitaddress網站上查看私鑰</figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>找到私鑰！</h2>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/ed9/7da/c1d/ed97dac1dc07e2bce09fe0951d9f64de.png" alt="www.blockchain.com/btc/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE" title="www.blockchain.com/btc/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE"/><figcaption class="wp-element-caption">www.blockchain.com/btc/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>該視頻是為&nbsp;<a href="https://cryptodeep.ru/" target="_blank" rel="noreferrer noopener"><strong>CRYPTO DEEP TECH</strong></a>門戶網站創建的&nbsp;，以確保橢圓曲線上的數據和密碼學的金融安全性&nbsp;免受&nbsp;加密貨幣中&nbsp;<code>secp256k1</code>&nbsp;弱簽名的影響&nbsp;<code>ECDSA</code><code>BITCOIN</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/tree/main/06KangarooJeanLucPons" target="_blank" rel="noreferrer noopener"><strong><u>來源</u></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>電報：&nbsp; https:&nbsp;</strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener"><strong>//t.me/cryptodeeptech</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>視頻素材：&nbsp; https:&nbsp;<a href="https://youtu.be/UGUJyxOhBBQ" target="_blank" rel="noreferrer noopener">//youtu.be/UGUJyxOhBBQ</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>來源：&nbsp;&nbsp;</strong><a href="https://cryptodeep.ru/kangaroo" target="_blank" rel="noreferrer noopener"><strong>https ://cryptodeep.ru/kangaroo</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">密碼分析</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2402} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/03/010-1024x576.png" alt="Pollard's Kangaroo находим решения дискретного логарифма secp256k1 PRIVATE KEY + NONCES в известном диапазоне" class="wp-image-2402"/></figure>
<!-- /wp:image -->
