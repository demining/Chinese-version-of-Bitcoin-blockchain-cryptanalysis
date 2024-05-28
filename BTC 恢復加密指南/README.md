# BTC 恢復加密指南

<!-- wp:embed {"url":"https://www.youtube.com/embed/imTXE4rGqHw","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/imTXE4rGqHw
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>在這篇文章中，我們將詳細了解<a href="https://github.com/demining/CryptoDeepTools/tree/main/17BTCRecoverCryptoGuide" target="_blank" rel="noreferrer noopener">Crypto Deep Tools</a>存儲庫中的開源密碼恢復工具和錢包助記詞，並討論您不小心丟失或忘記部分助記詞或在使用時出現錯誤的情況。解密它。（所以你要么看到一個空的錢包，要么得到一個錯誤，表明你的種子無效）對於錢包密碼或密碼短語恢復，如果你對你的密碼可能是什麼有一個合理的想法，它主要有用。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>BTCRecover</em>&nbsp;是一個開源的錢包密碼和種子恢復工具。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/" target="_blank" rel="noreferrer noopener">最好的辦法是按照安裝 BTCRecover 指南進行操作，然後閱讀“快速入門”以了解所需的恢復類型。（或者看一些使用例子）</a></em></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="usage-examples">使用示例</h1>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>此頁面提供了一些示例的鏈接，這些示例演示瞭如何在許多不同的恢復場景中使用 BTCRecover 的設置和語法。（一般帶有相應的YouTube視頻）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>給出的命令幾乎可以按原樣複製/粘貼，以允許您重新創建 YouTube 視頻中給出的示例。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>注意：</strong>&nbsp;根據您的平台，可能需要進行一些更改，通常是使用“python”與“python3”之類的簡單操作。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>Python 版本：</strong>&nbsp;其中許多視頻是使用 BTCRecover 的不同分支創建的。此處的資源和命令可能略有不同，但旨在與 Python3 下的此分支一起使用。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="seed-recovery">種子回收</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>基本種子恢復（演示用於恢復各種類型錢包的基本命令）</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":1} -->
<h1 id="basic-passwordpassphrase-recoveries">基本密碼/密碼恢復</h1>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>這個想法是，如果你在 Windows 上運行這個工具，你可以直接複製/粘貼這些示例中的任何一個。（它們都使用自動測試中的相同種子和地址）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>他們幾乎都會立即找到結果。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="seed-based-recovery-notes">基於種子的恢復筆記</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>註釋</strong>&nbsp;Seedrecover.py 已經設置好，因此默認值應該得到大多數簡單的“無效 menmonic”或“無效種子”類型錯誤的結果。（例如：你有一個完整的種子備份，但裡面有錯字）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>它將在所有常見的派生路徑上搜索所有帳戶類型以查找受支持的加密貨幣。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>它將自動運行四個搜索階段，最多需要幾個小時。1. 一個錯別字 2. 兩個錯別字，其中一個可能是完全不同的 BIP39 詞 3. 三個錯別字，其中一個可能是完全不同的 BIP39 詞 4. 兩個錯別字可能是完全不同的詞。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>完全支持的錢包</strong>&nbsp;（對於支持的加密貨幣）</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>硬件錢包<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Ledger Nano X 和 S</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Trezor One 和 T</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>保管鑰匙</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>安全寶</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>冷卡</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Bitbox02</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>梯形校正</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Cobo金庫</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>橢圓形</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>CoolWallet S（您需要將種子編號轉換為 BIP39 種子詞，並為比特幣和萊特幣使用 –force-p2sh 參數……）</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>軟件錢包<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Electrum——V1 和 V2 種子（包括 Electrum-LTC、Electron-Cash 等分叉）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>科諾米</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>芥末</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>邊緣錢包</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>菌絲體</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>出埃及記</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>信託錢包</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Metamask（包括像 Binance Chain Wallet Extension 這樣的克隆）</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><strong>存在兼容性問題的錢包</strong>（由於不遵循推導標準……）</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>原子錢包。（ETH（以及所有 ERC20 代幣）的非標準衍生，需要與&nbsp;<code>--checksinglexpubaddress</code>XRP 一起使用）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>阿布拉錢包。（非標準種子格式，第一個詞是非 BIP39“at”，後 12 個是 BIP39（和校驗和）但無法重現推導）</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 id="examples">讓我們繼續進行實驗部分：</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>讓我們打開<a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener"><strong>[TerminalGoogleColab]</strong></a>。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>讓我們使用存儲庫<strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/17BTCRecoverCryptoGuide" target="_blank" rel="noreferrer noopener">«17BTCRecoverCryptoGuide»</a></strong>。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/17BTCRecoverCryptoGuide/

ls</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1301} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/image-1024x561.png" alt="BTC 恢復加密指南" class="wp-image-1301"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>安裝我們需要的所有包、模塊和庫</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>pip3 install -r requirements.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1304} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/image-1-1024x474.png" alt="BTC 恢復加密指南" class="wp-image-1304"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":1305} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/image-2-1024x375.png" alt="BTC 恢復加密指南" class="wp-image-1305"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>使用 lscpu 命令找出 Google Colab 的處理器架構</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>lscpu</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1325} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/image-7-1024x403.png" alt="BTC 恢復加密指南" class="wp-image-1325"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>Linux 的 PyOpenCL 安裝</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sudo apt install python3-pyopencl</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1308} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/image-3-1024x491.png" alt="BTC 恢復加密指南" class="wp-image-1308"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>測試您的系統</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 -m btcrecover.test.test_passwords -v GPUTests</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1311} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/image-4-1024x359.png" alt="BTC 恢復加密指南" class="wp-image-1311"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3 id="basic-bitoin-recoveries">基本的比妥因恢復</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>注意：</strong>&nbsp;大多數情況下，您只需運行 seedrecover.py，甚至只需雙擊它並按照圖形界面操作即可。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>使用本地 Segwit 地址 – 一個單詞丟失，地址生成限制為 5。（因此地址需要在該帳戶的前 5 個地址中）</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_1" class="wp-block-code"><code>python3 seedrecover.py --wallet-type bip39 --addrs bc1qv87qf7prhjf2ld8vgm7l0mj59jggm6ae5jdkx2 --mnemonic "element entire sniff tired miracle solve shadow scatter hello never tank side sight isolate sister uniform advice pen praise soap lizard festival connect" --addr-limit 5
</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1312} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/image-5-1024x487.png" alt="BTC 恢復加密指南" class="wp-image-1312"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>使用 P2SH Segwit 地址 – 缺少一個字，地址生成限制為 5。（因此地址需要在該帳戶的前 5 個地址中）</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>python3 seedrecover.py --wallet-type bip39 --addrs 3NiRFNztVLMZF21gx6eE1nL3Q57GMGuunG --mnemonic "element entire sniff tired miracle solve shadow scatter hello never tank side sight isolate sister uniform advice pen praise soap lizard festival connect" --addr-limit 5
</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1313} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/image-6-1024x488.png" alt="BTC 恢復加密指南" class="wp-image-1313"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3 id="basic-cardano-recoveries">基本卡爾達諾恢復</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>對於 Cardano 恢復，請參閱此處的註釋。您可以使用任何雪萊時代的基地址或權益地址。（不支持拜倫時代）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>來自 Ledger Nano 的種子，缺少一個詞，使用標準基地址。（地址生成限制不適用於 Cardano）</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>python3 seedrecover.py --wallet-type cardano --addrs addr1qyr2c43g33hgwzyufdd6fztpvn5uq5lwc74j0kuqr7gdrq5dgrztddqtl8qhw93ay8r3g8kw67xs097u6gdspyfcrx5qfv739l --mnemonic "wood blame garbage one federal jaguar slogan movie thunder seed apology trigger spoon basket fine culture boil render special enforce dish middle antique"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>來自 Trezor 的種子，缺少一個詞，使用標準基地址。（地址生成限制不適用於 Cardano）</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_4" class="wp-block-code"><code>python3 seedrecover.py --wallet-type cardano --addrs addr1q8k0u70k6sxkcl6x539k84ntldh32de47ac8tn4us9q7hufv7g4xxwuezu9q6xqnx7mr3ejhg0jdlczkyv3fs6p477fqxwz930 --mnemonic "ocean kidney famous rich season gloom husband spring convince attitude boy"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>來自 Yoroi、Adalite 或 Daedalus（用作軟件錢包）的種子，使用標準權益地址</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_5" class="wp-block-code"><code>python3 seedrecover.py --wallet-type cardano --addrs stake1uxztdzzm4ljw9a0qmgregc8efgg56p2h3kj75kc6vmhfj2cyg0jmy --mnemonic "cave table seven there limit fat decorate middle gold ten battle trigger luggage demand"
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="basic-tron-recoveries">基本 Tron 恢復</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>少一個字，地址生成限制為1。（所以地址需要在第一個賬號）</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_6" class="wp-block-code"><code>python3 seedrecover.py --wallet-type tron --addrs TLxkYzNpMCEz5KThVuZzoyjde1UfsJKof6 --mnemonic "have hint welcome skate cinnamon rabbit cable payment gift uncover column duck scissors wedding decorate under marine hurry scrub rapid change roast print arch" --addr-limit 1
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="basic-helium-recoveries">基本氦氣回收</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>少了一個字</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_7" class="wp-block-code"><code>python3 seedrecover.py --wallet-type helium --addrs 13hP2Vb1XVcMYrVNdwUW4pF3ZDj8CnET92zzUHqYp7DxxzVASbB --mnemonic "arm hundred female steel describe tip physical weapon peace write advice"
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="basic-polkadotsubstrate-recoveries">基本 Polkadot（底物）恢復</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>少了一個字，空白的秘密推導路徑</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_8" class="wp-block-code"><code>python3 seedrecover.py --wallet-type polkadotsubstrate --addrs 13SsWBQSN6Se72PCaMa6huPXEosRNUXN3316yAycS6rpy3tK --mnemonic "toilet assume drama keen dust warrior stick quote palace imitate music disease"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>少了一個字，“//hard/soft///btcr-test-password”的秘密推導路徑軟/硬推導路徑通過-substrate-path參數傳遞給程序，密碼與密碼一樣處理密碼（沒有領先的///）</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_9" class="wp-block-code"><code>python3 seedrecover.py --wallet-type polkadotsubstrate --addrs 12uMBgecqfkHTYZE4GFRx847CwR7sfs2bTdPbPLpzeMDGFwC --mnemonic "toilet assume drama keen dust warrior stick quote palace imitate music disease" --passphrase-arg btcr-test-password --substrate-path //hard/soft
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="basic-stacks-recoveries">基本堆棧恢復</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>缺少一個單詞，地址生成限制為 10。（因此將檢查給定種子的前 10 個“帳戶”）</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_10" class="wp-block-code"><code>python3 seedrecover.py --wallet-type stacks --addrs SP11KHP08F4KQ06MWESBY48VMXRBK5NB0FSCRP779 --mnemonic "hidden kidney famous rich season gloom husband spring convince attitude boy" --addr-limit 10
</code></pre>
<!-- /wp:code -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>解擾 12 字 BIP39 種子（演示使用 TokenList 為 Electrum Legacy、Electrum Segwit、BIP39 比特幣和 BIP39 以太坊解擾種子）</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="descrambling-12-word-seeds">解擾12字種子</h1>
<!-- /wp:heading -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/ruSF8OKwBRk","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/ruSF8OKwBRk
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>為這些測試提供了三種類型的令牌文件。將在第一次檢查時找到結果的令牌文件、將找到結果作為最後可能組合的令牌文件以及將在兩者之間的某個點找到結果的令牌文件。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>這個想法是，這些可以讓你快速驗證事情是否正常（找到第一個結果），了解完整運行可能需要多長時間（最後結果），並嘗試一些代表現實世界情況的東西。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果您只是解擾一個 12 字的種子，那麼在沒有 –no-eta 的情況下運行沒有多大意義，因為可以輕鬆計算出要測試的種子數量，並且種子生成器可以輕鬆跟上至少 48 個線程。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>注意：</strong>&nbsp;&nbsp;YouTube 視頻和示例是在將 OpenCL 加速添加到 Blockchain.com 錢包之前製作的，可以提供 2 倍的性能提升。（有關更多信息，請參閱 GPU 加速）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>表現</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>在 48 核 Linode 上，您可以期望…… * 在不到 15 分鐘的時間內解擾一個 12 字的 Electrum 種子…… * 在不到 50 分鐘的時間內解擾一個 12 字的 BIP39 種子……</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>在當前（2020 年年中）的中檔 CPU 上，您可以預計事情需要大約 5 倍的時間。</em></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="electrum">金銀合金</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="legacy-wallet-last-result">遺留錢包（最後結果）</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>使用令牌列表 lastcombination_electrum.txt</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9 10 11 12</td><td><code>book fit fly ketchup also elevator scout mind edit fatal where rookie</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p><strong>命令</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>python3 seedrecover.py --no-dupchecks --mnemonic-length 12 --language EN --dsw --addr-limit 1 --addrs 1CU62HPowYSxhHiiNu1ukSbMjrkGj4x52i --tokenlist ./docs/Usage_Examples/2020-05-02_Descrambling_a_12_word_seed/lastcombination_electrum.txt --wallet-type electrum2
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="segwit-wallet">隔離見證錢包</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>使用令牌列表 randomcombination_electrum.txt</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9 10 11 12</td><td><code>social shoe spin enlist sponsor resource result coffee ocean gas file paddle</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p><strong>命令</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_4" class="wp-block-code"><code>python3 seedrecover.py --no-dupchecks --mnemonic-length 12 --language EN --dsw --wallet-type electrum2 --addr-limit 1 --addrs bc1qtylwmarke39nysxepdx5xzfatvrlel5z8m0jx2 --tokenlist ./docs/Usage_Examples/2020-05-02_Descrambling_a_12_word_seed/randomcombination_electrum.txt --bip32-path "m/0'/0"
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="bip39">BIP39</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="ethereum-address-default-derivation-path-for-trezor-mew">以太坊地址（Trezor、MEW 的默認推導路徑）</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>使用令牌列表 randomcombination_bip39.txt</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9 10 11 12</td><td><code>boy hidden kidney famous spring convince rich season gloom ocean husband attitude</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p><strong>命令</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_6" class="wp-block-code"><code>python3 seedrecover.py --no-dupchecks --mnemonic-length 12 --language EN --dsw --wallet-type ethereum --addr-limit 1 --addrs 0x66F9C09118B1C726BC24811a611baf60af42070A --tokenlist ./docs/Usage_Examples/2020-05-02_Descrambling_a_12_word_seed/randomcombination_bip39.txt --bip32-path "m/44'/60'/0'/0"
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="legacy-btc-address-first-result">遺留 BTC 地址（第一個結果）</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>使用 Tokenlist firstcombination_bip39.txt</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9 10 11 12</td><td><code>boy attitude convince spring husband gloom season rich famous kidney hidden ocean</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p><strong>命令</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_8" class="wp-block-code"><code>python3 seedrecover.py --no-dupchecks --mnemonic-length 12 --language EN --dsw --wallet-type BIP39 --addr-limit 1 --addrs 17GR7xWtWrfYm6y3xoZy8cXioVqBbSYcpU --tokenlist ./docs/Usage_Examples/2020-05-02_Descrambling_a_12_word_seed/firstcombination_bip39.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="legacy-btc-address-last-result">遺留 BTC 地址（最後結果）</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>使用令牌列表 lastcombination_bip39.txt</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9 10 11 12</td><td><code>ocean hidden kidney famous rich season gloom husband spring convince attitude boy</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p><strong>命令</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_10" class="wp-block-code"><code>python3 seedrecover.py --no-dupchecks --mnemonic-length 12 --language EN --dsw --wallet-type BIP39 --addr-limit 1 --addrs 17GR7xWtWrfYm6y3xoZy8cXioVqBbSYcpU --tokenlist ./docs/Usage_Examples/2020-05-02_Descrambling_a_12_word_seed/lastcombination_bip39.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="litecoin-native-segwit-address-seed-with-positional-anchors-for-known-words-last-word-as-any-valid-bip39-word-starting-with-b">Litecoin Native Segwit 地址（帶有已知詞位置錨的種子，最後一個詞是任何以“B”開頭的有效 BIP39 詞）</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>使用令牌列表 fixedwords_bip39.txt</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9 10 11 12</td><td><code>^1^ocean ^2^ocean ^3^ocean ^1^hidden ^2^hidden ^3^hidden ^1^kidney ^2^kidney ^3^kidney ^4^famous ^5^rich ^6^season gloom husband spring convince attitude baby bachelor bacon badge bag balance balcony ball bamboo banana banner bar barely bargain barrel base basic basket battle beach bean beauty because become beef before begin behave behind believe below belt bench benefit best betray better between beyond bicycle bid bike bind biology bird birth bitter black blade blame blanket blast bleak bless blind blood blossom blouse blue blur blush board boat body boil bomb bone bonus book boost border boring borrow boss bottom bounce box boy bracket brain brand brass brave bread breeze brick bridge brief bright bring brisk broccoli broken bronze broom brother brown brush bubble buddy budget buffalo build bulb bulk bullet bundle bunker burden burger burst bus business busy butter buyer buzz</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p><strong>命令</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_12" class="wp-block-code"><code>python3 seedrecover.py --no-dupchecks --mnemonic-length 12 --language EN --dsw --wallet-type BIP39 --addr-limit 1 --addrs ltc1q9srpp39hev6dpsxjjp8t5g0m3z7509vc9llalv --tokenlist ./docs/Usage_Examples/2020-05-02_Descrambling_a_12_word_seed/fixedwords_bip39.txt --bip32-path "m/84'/2'/0'/0"
</code></pre>
<!-- /wp:code -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>多設備解擾帶有額外單詞的 12 單詞種子（演示“必需”錨點、“位置”錨點和跨多個設備傳播工作）</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="required-anchors-positional-anchors-and-spreading-work-accross-multiple-devices">“必需”錨點、“位置”錨點和跨多個設備傳播工作</h1>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>YouTube 視頻可以在這裡找到：TBC</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="background"><strong>背景</strong></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>除了能夠使用潛在詞的標記列表簡單地解密 BIP39 種子之外，BTCRecover 還可以用於您可能知道&nbsp;<em>某些</em>&nbsp;詞的位置同時在種子短語中還有其他誘餌詞的情況。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>使用中的示例令牌列表：tokenlist.txt</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17</td><td><code>+ ^1^ocean + ^2^hidden + ^3^kidney famous + ^5^rich + ^6^season + ^7^gloom husband spring + ^10^convince + ^11^attitude + ^12^boy glove section chunk brick sauce</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>對於更大的恢復作業，BTCRecover 還允許您將工作負載分散到多個設備上。重要的是要了解 BTCRecover 使用的過程是&nbsp;<strong>確定性的</strong>&nbsp;，簡單來說，這意味著每次運行 BTCRecover 時，它都會以完全相同的順序搜索潛在的密碼/密碼，每次。這意味著在不使用 –workers 命令的情況下，簡單地同時在兩個設備上運行它，只會做兩次相同的工作……</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>幸運的是，您可以將搜索拆分成片並將這些片分配給不同的設備。這個機制非常簡單，基本上是以“循環”調度方式分配密碼。（例如：如果工作被分成三個設備的三個時間片，每個設備將處理每 3 個密碼）在一個設備可能比另一個設備快數倍的情況下，還可以將多個時間片分配給單個設備其他的。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>因此，讓我們考慮兩個設備 PC1 和 PC2 的示例。在此示例中，PC1 的功能是 PC2 的兩倍，因此將分配 2/3 的工作，而 PC2 將分配 1/3。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="practical-limits">實際限制</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>在這種情況下計算出有多少個潛在密碼是非常簡單的。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>例如，如果您有一個包含 20 個單詞的列表並且知道其中 3 個單詞在 12 個單詞種子中的位置，那麼將會有：</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>17 * 16 * 15 * 14 * 13 * 12 * 11 * 10 * 9 = 8,821,612,800 個可能的種子（根據您可用的 CPU 能力，幾天內就可以完成）</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="running-btcrecover">運行 BTCRecover</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>兩台 PC 都需要安裝 BTCRecover，並且都使用相同的命令，但每台 PC 的 –worker 命令不同。（我們可以忽略這個 tokenlist 只產生一個非常小的集合來測試的事實）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>這些設備不需要運行相同的操作系統，也不需要以任何方式相互通信……</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="command-on-pc-1">PC 1 上的命令</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>所以我們要將工作片1和2分配給PC1</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>命令</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>python3 seedrecover.py --no-dupchecks --mnemonic-length 12 --language EN --dsw --wallet-type BIP39 --addr-limit 1 --addrs 17GR7xWtWrfYm6y3xoZy8cXioVqBbSYcpU --tokenlist ./docs/Usage_Examples/2020-05-23_multi_device_descrambling_12_word_seed_with_extras/tokenlist.txt
 --no-eta --worker 1,2/3
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="command-on-pc-2">PC 2 上的命令</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>並將切片 3 工作到 PC2</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>命令</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>python3 seedrecover.py --no-dupchecks --mnemonic-length 12 --language EN --dsw --wallet-type BIP39 --addr-limit 1 --addrs 17GR7xWtWrfYm6y3xoZy8cXioVqBbSYcpU --tokenlist ./docs/Usage_Examples/2020-05-23_multi_device_descrambling_12_word_seed_with_extras/tokenlist.txt
 --no-eta --worker 3/3
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="the-outcome">結果…</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>在此示例中，PC2 找到了正確的種子短語。由於設備之間沒有通信，PC1 將繼續搜索，直到耗盡搜索空間。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>這也凸顯了您在使用此命令時需要特別注意您在做什麼。如果您不小心忘記將工作共享分配給一台 PC，或者將相同的共享分配兩次，BTCrecover 將無法知道發生了這種情況，如果正確的密碼出現在未經測試的共享中，也不會找到任何結果。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="closing-thoughts">結束語</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>在這種情況下使用 –no-eta 命令會很有用，因為它會顯示設備檢查密碼的當前速度。它也會立即開始。（如果您為雲服務器時間付費，這可能會很好）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>使用此命令的一種有用方法是，如果您已經在您的 PC 上開始密碼搜索並且知道需要檢查多少個密碼，它可以加快速度以使用 –no-eta 運行並且只需手動工作事情需要多長時間。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果您已經開始在單個設備上進行種子恢復並希望移動到多設備設置，但不想重新檢查已經在單個設備上測試過的密碼，您可以記下有多少個密碼單個設備已測試，在跨多個設備重新啟動測試時只需使用 –skip 命令。</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>在基於標記列表的種子恢復中將單詞組合在一起（演示解擾一個 24 個單詞的種子，其中有幾組已知的單詞彼此跟隨，但這些組在種子中的位置未知）</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="grouping-words-together-in-tokenlist-based-seed-recoveries">在基於令牌列表的種子恢復中將單詞分組在一起</h1>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2 id="background">背景</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>有時在恢復過程中，有人可能以不確定順序的方式寫入種子，或者將備份分成多個部分。無論哪種方式，這都可能意味著單詞以一種已知其相對順序的方式組合在一起，但這些單詞在較大種子中的位置卻未知。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>在這種情況下，您可以對標記列表中的單詞使用單個逗號字符&nbsp;<code>,</code>&nbsp;（沒有空格，只有一個逗號），以指示單詞必須按照提供的順序一起使用。這類似於“相對錨點”功能，但效率更高，並且還允許多個單詞分組。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>分組詞標記也可以與其他類型的錨點、位置等結合使用。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>使用這些標記還意味著標記的數量將不再等於助記符長度（因為它通常對單個單詞標記進行解擾）因此您還可以使用 和 參數來指定應該嘗試的最小&nbsp;<code>--min-tokens</code>&nbsp;標記&nbsp;<code>--max-tokens</code>&nbsp;數對於任何給定的種子猜測。（以逗號分隔的一組單詞算作一個標記）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>與種子解擾一樣，這種恢復的上限是基於令牌的數量，通常（沒有位置錨）會有最大令牌！(max-tokens factorial) 要檢查的可能種子。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="example">例子</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>以下示例使用以下令牌列表：</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9 10 11 12</td><td><code>^basic,dawn,renew,punch,arch,situate arrest,question,armor hole,lounge,practice resist zoo,zoo,zoo indicate,call lens,group,empty zoo husband verify,eternal,injury battle,satoshi brother,damp,this</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>您可以在這個標記列表中看到，我們確定有幾個標記塊的順序是正確的（包括一組種子詞的位置錨點）以及一些額外的/單個單詞。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>並使用以下命令運行（將在幾秒鐘內找到結果）</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>python3 seedrecover.py --tokenlist ./docs/Usage_Examples/2022-04-02_Seed_Tokenlist_TokenBlocks/tokengroups_tokenlist.txt --mnemonic-length 24 --language en --wallet-type bip39 --addrs 1PTcESpqrmWePYB5h18Ni11QTKNfMkdSYJ --dsw --addr-limit 10 --max-tokens 9 --min-tokens 8
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>正確的種子是：&nbsp;<code>basic dawn renew punch arch situate resist indicate call lens group empty brother damp this verify eternal injury arrest question armor hole lounge practice</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如您所見，它由上面的令牌列表文件中包含的一些令牌組組成。</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 id="password-recovery">找回密碼</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>基本密碼恢復（演示用於恢復各種類型錢包的基本命令）</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="basic-passwordpassphrase-recoveries">基本密碼/密碼恢復</h1>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>這些示例都不涉及您將用於不同類型的拼寫錯誤、標記列表等的參數。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>這個想法是，如果你在 Windows 上運行這個工具，你可以直接複製/粘貼這些示例中的任何一個。（它們都使用自動測試中的相同種子和地址）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>他們幾乎都會立即找到結果。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>下面基本示例中使用的基本密碼列表</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5</td><td><code>btcr-test-password btcr-test-password:p2pkh btcr-test-password:p2wpkh btcr-test-password:p2wpkh-p2sh btcrtestpassword2022</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:heading -->
<h2 id="bip38-encrypted-paper-wallet-recovery">BIP38 加密紙錢包恢復。</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>注意</strong>&nbsp;BIP38 錢包是通過 sCrypt 加密的，因此暴力破解的速度非常慢。這些錢包的 GPU 加速可用，但不會提供太多性能提升，除非你有多個 GPU 或相對於你的 CPU 特別強大的 GPU……（或某種專用的 OpenCL 加速器）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>支持的錢包</strong></p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://www.bitaddress.org/">比特地址.org</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://liteaddress.org/">liteaddress.org</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://paper.dash.org/">paper.dash.org 網站</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>以及幾乎任何其他 BIP38 加密私鑰。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>命令</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>對於比特幣（無需指定幣種，默認勾選比特幣）</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>python3 btcrecover.py --bip38-enc-privkey 6PnM7h9sBC9EMZxLVsKzpafvBN8zjKp8MZj6h9mfvYEQRMkKBTPTyWZHHx --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>對於萊特幣</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>python3 btcrecover.py --bip38-enc-privkey 6PfVHSTbgRNDaSwddBNgx2vMhMuNdiwRWjFgMGcJPb6J2pCG32SuL3vo6q --bip38-currency litecoin --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>對於破折號</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_4" class="wp-block-code"><code>python3 btcrecover.py --bip38-enc-privkey 6PnZC9Snn1DHyvfEq9UKUmZwonqpfaWav6vRiSVNXXLUEDAuikZTxBUTEA --bip38-currency dash --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="bip39-passphrase-protected-wallets-electrum-extra-words">BIP39 密碼短語保護的錢包和 Electrum“Extra Words”</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>備註</strong>&nbsp;用於引用 BIP39 密碼的語言可能因供應商而異。有時它被稱為“第 25 個詞”，有時是“似是而非的可否認性密碼”或有時只是“密碼”。請注意，這與您的錢包密碼或 PIN 不同。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>BIP39 密碼錯誤的最常見症狀是您的種子+密碼將產生一組完全空的賬戶，沒有餘額或交易歷史。（每個 BIP39 密碼都是有效的，所以你不會收到任何錯誤信息）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>雖然 BIP39 種子恢復可以受益於 GPU 加速，但目前恢復 BIP39 密碼短語並非如此。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>下面的所有示例命令都將地址生成限制設置為 10，因此它們搜索的地址需要在錢包中的前 10 個地址內。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>支持的錢包</strong></p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>大多數支持 BIP39/44 的硬件錢包<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Trezor（一和 T）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Ledger Nano（S 和 X）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>保管鑰匙</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>冷卡</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Bitbox02</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Cobo金庫專業版</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>大多數支持 BIP39/44 的軟件錢包<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Wasabi 錢包（Wasabi 將此稱為您的錢包密碼）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>武士錢包</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>科諾米</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>菌絲體</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Zillet（將 BIP39 密碼短語稱為“基於密碼”的錢包類型）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>金銀合金</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>出埃及記</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><strong>命令</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>基本比特幣命令，因此無需指定&nbsp;<code>--wallet-type</code>&nbsp;這將支持所有比特幣地址類型（傳統、隔離見證或原生隔離見證），無需添加任何額外參數。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_5" class="wp-block-code"><code>python3 btcrecover.py --bip39 --addrs 1AmugMgC6pBbJGYuYmuRrEpQVB9BBMvCCn --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "certain come keen collect slab gauge photo inside mechanic deny leader drop"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本比特幣 Electrum 錢包命令。這些不是 BIP39，因此需要使用&nbsp;<code>--wallet-type electrum2</code>&nbsp;這將同時支持 Legacy 和 Segwit Electrum 錢包，無需任何其他參數。（它也適用於大多數 Electrum 山寨幣克隆）</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_6" class="wp-block-code"><code>python3 btcrecover.py --wallet-type electrum2 --addrs bc1q6n3u9aar3vgydfr6q23fzcfadh4zlp2ns2ljp6 --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "quote voice evidence aspect warfare hire system black rate wing ask rug"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本的以太坊命令，所以需要指定&nbsp;<code>--wallet-type</code>&nbsp;（但可以省略&nbsp;<code>--bip39</code>&nbsp;參數，因為它是暗示的）</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_7" class="wp-block-code"><code>python3 btcrecover.py --wallet-type ethereum --addrs 0x4daE22510CE2fE1BC81B97b31350Faf07c0A80D2 --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本 Zilliqa 命令，因此需要指定&nbsp;<code>--wallet-type</code>&nbsp;（但可以省略&nbsp;<code>--bip39</code>&nbsp;參數，因為它是暗示的）這將支持所有地址類型（Base16 和 Bech32），而無需添加任何額外參數。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>注意：Zilliqa 種子恢復目前不能用作恢復 Ledger Nano 種子/密碼的基礎。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_8" class="wp-block-code"><code>python3 btcrecover.py --wallet-type zilliqa --addrs zil1dcsu2uz0yczmunyk90e8g9sr5400c892yeh8fp --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本的比特幣現金命令，因此需要指定&nbsp;<code>--wallet-type</code>&nbsp;（但可以省略&nbsp;<code>--bip39</code>&nbsp;參數，因為它是暗示的）這將接受 Cashaddres 或 Legacy 樣式地址......這也適用於像 BSV 這樣的 BCH 分叉......</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_9" class="wp-block-code"><code>python3 btcrecover.py --wallet-type bch --addrs bitcoincash:qqv8669jcauslc88ty5v0p7xj6p6gpmlgv04ejjq97 --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>Basic Cardano，因此需要具體說明&nbsp;<code>--wallet-type</code>&nbsp;（但可以省略&nbsp;<code>--bip39</code>&nbsp;參數，因為它是暗示的）對於 Cardano 恢復，&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/bip39-accounts-and-altcoins/">也請參閱此處的註釋。</a>&nbsp;這將接受基地址或權益地址……（不支持拜倫時代的地址））</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_10" class="wp-block-code"><code>python3 btcrecover.py --wallet-type cardano --addrs addr1q90kk6lsmk3fdy54mqfr50hy025ymnmn5hhj8ztthcv3qlzh5aynphrad3d26hzxg7xzzf8hnmdpxwtwums4nmryj3jqk8kvak --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "ocean hidden kidney famous rich season gloom husband spring convince attitude boy"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本 Dash 命令，因此需要指定&nbsp;<code>--wallet-type</code>&nbsp;（但可以省略&nbsp;<code>--bip39</code>&nbsp;參數，因為它是隱含的）</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_11" class="wp-block-code"><code>python3 btcrecover.py --wallet-type dash --addrs XuTTeMZjUJuZGotrtTPRCmHCaxnX44a2aP --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本的狗狗幣命令，所以需要指定&nbsp;<code>--wallet-type</code>&nbsp;（但可以省略&nbsp;<code>--bip39</code>&nbsp;參數，因為它是暗示的）</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_12" class="wp-block-code"><code>python3 btcrecover.py --wallet-type dogecoin --addrs DSTy3eptg18QWm6pCJGG4BvodSkj3KWvHx --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本的 Vertcoin 命令，因此需要指定&nbsp;<code>--wallet-type</code>&nbsp;（但可以省略參數&nbsp;<code>--bip39</code>&nbsp;，因為它是暗示的）這將支持所有地址類型（舊版、Segwit 或本機 Segwit），而無需添加任何額外參數。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_13" class="wp-block-code"><code>python3 btcrecover.py --wallet-type vertcoin --addrs Vwodj33bXcT7K1uWbTqtk9UKymYSMeaXc3 --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本的 Litecoin 命令，因此需要指定&nbsp;<code>--wallet-type</code>&nbsp;（但可以省略&nbsp;<code>--bip39</code>&nbsp;參數，因為它是暗示的）這將支持所有地址類型（Legacy、Segwit 或 Native Segwit），而無需添加任何額外參數。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_14" class="wp-block-code"><code>python3 btcrecover.py --wallet-type litecoin --addrs LdxLVMdt49CXcrnQRVJFRs8Yftu9dE8xxP --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本的 Monacoin 命令，因此需要指定&nbsp;<code>--wallet-type</code>&nbsp;（但可以省略&nbsp;<code>--bip39</code>&nbsp;參數，因為它是暗示的）這將支持所有地址類型（舊版、Segwit 或本機 Segwit），而無需添加任何額外參數。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_15" class="wp-block-code"><code>python3 btcrecover.py --wallet-type monacoin --addrs MHLW7WdRKE1XBkLFS6oaTJE1nPCkD6acUd --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本 DigiByte 命令，因此需要指定&nbsp;<code>--wallet-type</code>&nbsp;（但可以省略&nbsp;<code>--bip39</code>&nbsp;參數，因為它是隱含的）這將支持所有地址類型（Legacy、Segwit 或 Native Segwit），而無需添加任何額外參數。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_16" class="wp-block-code"><code>python3 btcrecover.py --wallet-type digibyte --addrs DNGbPa9QMbLgeVspu9jb6EEnXjJASMvA5r --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本 GroestleCoin 命令，因此需要指定&nbsp;<code>--wallet-type</code>&nbsp;（但可以省略&nbsp;<code>--bip39</code>&nbsp;參數，因為它是隱含的）這將支持所有地址類型（舊版、隔離見證或原生隔離見證），無需添加任何額外參數。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>注意：這需要安裝 groestlecoin_hash 模塊……</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_17" class="wp-block-code"><code>python3 btcrecover.py --wallet-type groestlecoin --addrs FWzSMhK2TkotZodkApNxi4c6tvLUo7MBWk --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本 Ripple 命令，因此需要指定&nbsp;<code>--wallet-type</code>&nbsp;（但可以省略&nbsp;<code>--bip39</code>&nbsp;參數，因為它是暗示的）</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_18" class="wp-block-code"><code>python3 btcrecover.py --wallet-type ripple --addrs rwv2s1wPjaCxmEFRm4j724yQ5Lh161mzwK --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本 Tron 命令，因此需要指定&nbsp;<code>--wallet-type</code>&nbsp;（但可以省略&nbsp;<code>--bip39</code>&nbsp;參數，因為它是暗示的）</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_19" class="wp-block-code"><code>python3 btcrecover.py --wallet-type tron --addrs TGvJrj5D8qdzhcppg9RoLdfbEjDYCne8xc --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "have hint welcome skate cinnamon rabbit cable payment gift uncover column duck scissors wedding decorate under marine hurry scrub rapid change roast print arch" 
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本的 Polkadot(Substrate) 命令，因此需要指定&nbsp;<code>--wallet-type</code>&nbsp;（但可以省略&nbsp;<code>--bip39</code>&nbsp;參數，因為它是隱含的）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>該命令將搜索正確的“秘密推導路徑”</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_20" class="wp-block-code"><code>python3 btcrecover.py --wallet-type polkadotsubstrate --addrs 12uMBgecqfkHTYZE4GFRx847CwR7sfs2bTdPbPLpzeMDGFwC --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "toilet assume drama keen dust warrior stick quote palace imitate music disease" --substrate-path "//hard/soft"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本堆棧命令，因此需要指定&nbsp;<code>--wallet-type</code>&nbsp;（但可以省略&nbsp;<code>--bip39</code>&nbsp;參數，因為它是隱含的）此示例還將地址生成限制設置為 10，因此將檢查給定種子+密碼的前 10 個“帳戶”。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_21" class="wp-block-code"><code>python3 btcrecover.py --wallet-type stacks --addrs SP2KJB4F9C91R3N5XSNQE0Z3G34DNJWQYTP3PBJTH --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "ocean hidden kidney famous rich season gloom husband spring convince attitude boy" --addr-limit 10
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="brainwallets">腦錢包</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>注意</strong>&nbsp;Brainwallets 是一種非常古老（<strong>而且非常不安全</strong>）的錢包類型。鑑於此，他們中的大多數仍然根據“未壓縮”生成地址</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>支持的錢包</strong></p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Sha256（密碼）錢包<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://www.bitaddress.org/">比特地址.org</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://segwitaddress.org/">隔離見證地址.org</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://liteaddress.org/">liteaddress.org</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://paper.dash.org/">paper.dash.org 網站</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Warpwallet 錢包<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://keybase.io/warp/">錢包</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://dvdbng.github.io/memwallet/">內存錢包</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://patcito.github.io/mindwallet/">心靈錢包</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 id="sha256passphrase-wallets">Sha256（密碼）錢包</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>命令</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>基本比特幣命令（將檢查壓縮和未壓縮地址類型，即使在本例中這是一個壓縮地址）</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_22" class="wp-block-code"><code>python3 btcrecover.py --brainwallet --addrs 1BBRWFHjFhEQc1iS6WTQCtPu2GtZvrRcwy --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>比特幣錢包，但設置為僅檢查未壓縮的地址。（僅將此用於您確定不是壓縮地址的非常舊的錢包，但也要考慮未壓縮是默認設置……只會提供小幅速度提升）</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_23" class="wp-block-code"><code>python3 btcrecover.py --brainwallet --addrs 1MHoPPuGJyunUB5LZQF5dXTrLboEdxTmUm --skip-compressed --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>P2SH 比特幣錢包（就像你從 segwitaddress.org 得到的那種，截至 2021 年，這些都是壓縮類型的地址，所以可以跳過檢查未壓縮的地址......）</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_24" class="wp-block-code"><code>python3 btcrecover.py --brainwallet --addrs 3C4dEdngg4wnmwDYSwiDLCweYawMGg8dVN --skip-uncompressed --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>Bech32 比特幣錢包。（來自 segwitaddress.org）</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_25" class="wp-block-code"><code>python3 btcrecover.py --brainwallet --addrs bc1qth4w90jmh0a6ug6pwsuyuk045fmtwzreg03gvj --skip-uncompressed --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>萊特幣錢包（來自 liteaddress.org – 這些都是未壓縮的，沒有使用壓縮的選項）這些類型的錢包不需要額外的參數。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_26" class="wp-block-code"><code>python3 btcrecover.py --brainwallet --addrs LfWkecD6Pe9qiymVjYENuYXcYpAWjU3mXw --skip-compressed --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>Dash Wallet（來自 paper.dash.org）——沒有指定壓縮參數，所以它只會檢查兩者</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_27" class="wp-block-code"><code>python3 btcrecover.py --brainwallet --addrs XvyeDeZAGh8Nd7fvRHZJV49eAwNvfCubvB --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>Dash 錢包（來自 paper.dash.org – 或者如果你知道你使用的是壓縮錢包……（儘管默認是未壓縮）</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_28" class="wp-block-code"><code>python3 btcrecover.py --brainwallet --addrs XksGLVwdDQSzkxK1xPmd4R5grcUFyB3ouY --skip-uncompressed --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="warpwallets">錢包</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>注意：目前只支持比特幣和萊特幣……（可以輕鬆添加Eth）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>命令</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>以“btcr-test-password”作為鹽的基本比特幣錢包。（Warpwallet 建議使用您的電子郵件地址）這些錢包都是“未壓縮”類型的，但與 sCrypt 操作所需的時間相比，這樣做的性能提升是如此之小，不值得檢查這兩種類型……</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_29" class="wp-block-code"><code>python3 btcrecover.py --warpwallet --warpwallet-salt btcr-test-password --addrs 1FThrDFjhSf8s1Aw2ed5U2sTrMz7HicZun --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>以“btcr-test-password”作為鹽的基本萊特幣錢包。（就像 memwallet 或 mindwallet 產生的一樣，所以你需要添加 –crypto 參數並指定 litecoin）這些錢包都是“未壓縮”類型，但與 sCrypt 操作所花費的時間相比，這樣做的性能增益是如此之小，它是不值得檢查這兩種類型……</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_30" class="wp-block-code"><code>python3 btcrecover.py --warpwallet --warpwallet-salt btcr-test-password --crypto litecoin --addrs LeBzGzZFxRUzzRAtm8EB2Dw74jRfQqUZeq --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="blockio-wallets">Block.io 錢包</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>您將首先使用文檔的提取腳本部分中的說明下載錢包文件。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>然後，您將使用如下命令進行基本恢復。（此命令使用與 BTCRecover 捆綁在一起的示例錢包文件）</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_31" class="wp-block-code"><code>python3 btcrecover.py --wallet ./btcrecover/test/test-wallets/block.io.request.json --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="dogechaininfo-wallets">Dogechain.info 錢包</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>您將首先使用文檔的提取腳本部分中的說明下載錢包文件。您還可以使用提取腳本在租用的硬件上安全地運行 dogechain.info 錢包。有關提取腳本的更多信息，請參見此處……</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>然後，您將使用如下命令進行基本恢復。（此命令使用與 BTCRecover 捆綁在一起的示例錢包文件）</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_32" class="wp-block-code"><code>python3 btcrecover.py --wallet ./btcrecover/test/test-wallets/dogechain.wallet.aes.json --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="ethereum-keystores">以太坊密鑰庫</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>使用如下命令執行基本恢復。（此命令使用與 BTCRecover 捆綁在一起的示例錢包文件）</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_33" class="wp-block-code"><code>python3 btcrecover.py --wallet ./btcrecover/test/test-wallets/utc-keystore-v3-scrypt-myetherwallet.json --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="slip39-passphrases">SLIP39 密碼短語</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>這使用與恢復 BIP39 密碼短語相同的語法。BTCRecover 目前支持 Trezor T 支持的大部分硬幣。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>主要區別在於，您可以通過命令行輸入 SLIP39 共享，而不是輸入單個助記符，如下所示，否則係統會提示您輸入它們。您需要有一定數量的 SLIP39 共享才能進行密碼恢復……</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>基本比特幣命令，因此無需指定&nbsp;<code>--wallet-type</code>&nbsp;這將支持所有比特幣地址類型（傳統、隔離見證或原生隔離見證），無需添加任何額外參數。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_34" class="wp-block-code"><code>python3 btcrecover.py --slip39 --addrs bc1q76szkxz4cta5p5s66muskvads0nhwe5m5w07pq --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --slip39-shares "hearing echo academic acid deny bracelet playoff exact fancy various evidence standard adjust muscle parcel sled crucial amazing mansion losing" "hearing echo academic agency deliver join grant laden index depart deadline starting duration loud crystal bulge gasoline injury tofu together"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>基本的以太坊命令，所以需要指定&nbsp;<code>--wallet-type</code>&nbsp;（但可以省略&nbsp;<code>--bip39</code>&nbsp;參數，因為它是暗示的）</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_35" class="wp-block-code"><code>python3 btcrecover.py --slip39 --wallet-type ethereum --addrs 0x0Ef61684B1E671dcBee4D51646cA6247487Ef91a --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --slip39-shares "hearing echo academic acid deny bracelet playoff exact fancy various evidence standard adjust muscle parcel sled crucial amazing mansion losing" "hearing echo academic agency deliver join grant laden index depart deadline starting duration loud crystal bulge gasoline injury tofu together"
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="raw-private-keys">原始私鑰</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>BTCRecover 也可用於從您的私鑰損壞的情況中恢復。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>這是以類似於密碼恢復的方式處理的，因此您的私鑰猜測進入令牌列表，使用 %h 通配符替換十六進製字符或 %b 替換 base58 字符。您可以使用令牌列表或密碼列表，具體取決於您的情況以及標準拼寫錯誤。如果您使用的是令牌列表，您只需要確保生成的私鑰與私鑰所需的長度和字符相匹配……</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果您知道私鑰對應的地址，您可以提供該地址，或者您可以使用 AddressDB。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="raw-eth-private-keys">原始 Eth 私鑰</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>您還會注意到需要從私鑰中刪除前導“0x”。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>示例令牌列表</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1個</td><td><code>5db77aa7aea5%2h7d6b4c64dab21%h972cf4763d4937d3e6e17f580436dcb10%3h</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>上面的令牌列表是一個標準的 Eth 私鑰（刪除了前導 0x）的示例，其中有三個損壞的部分。一個單字符 (%h)、一個兩個字符 (%2h) 和一個三個字符 (%3h) 運行大約需要 20 分鐘……</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_37" class="wp-block-code"><code>python3 btcrecover.py --rawprivatekey --addrs 0xB9644424F9E639D1D0F27C4897e696CC324948BB --wallet-type ethereum --tokenlist ./docs/Usage_Examples/eth_privkey_tokenlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="raw-bitcoin-private-keys">原始比特幣私鑰</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>比特幣私鑰在 Base58 中的壓縮和未壓縮格式以及原始十六進制密鑰中均受支持。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果您使用帶有多個私鑰的令牌列表（如下例所示），每行一個，您還需要指定“–max-tokens 1”參數。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>示例令牌列表</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1個</td><td><code>5db77aa7aea5%2h7d6b4c64dab21%h972cf4763d4937d3e6e17f580436dcb10%3h</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>下面的命令將嘗試使用包含三個可能的私鑰的令牌列表來恢復一個缺少一個字符的舊式未壓縮私鑰。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_39" class="wp-block-code"><code>python3 btcrecover.py --rawprivatekey --addrs 1EDrqbJMVwjQ2K5avN3627NcAXyWbkpGBL --wallet-type bitcoin --max-tokens 1 --tokenlist ./docs/Usage_Examples/btc_privkey_tokenlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>下面的命令將嘗試使用包含三個可能的私鑰的令牌列表來恢復一個缺少一個字符的更現代的（壓縮的、本地隔離驗證地址）私鑰。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_40" class="wp-block-code"><code>python3 btcrecover.py --rawprivatekey --addrs bc1qafy0ftpk5teeayjaqukyd244un8gxvdk8hl5j6 --wallet-type bitcoin --max-tokens 1 --tokenlist ./docs/Usage_Examples/btc_privkey_tokenlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>您還可以通過使用 AddressDB 進行原始私鑰修復，即使您沒有相應地址的記錄。（也適用於 Eth、BCH 等……）</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_41" class="wp-block-code"><code>python3 btcrecover.py --rawprivatekey --addressdb ./btcrecover/test/test-addressdbs/addresses-BTC-Test.db --wallet-type bitcoin --max-tokens 1 --tokenlist ./docs/Usage_Examples/btc_privkey_tokenlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>恢復 Blockchain.com 錢包密碼（演示恢復 Blockchain.com 錢包，使用提取腳本、tokenLists、密碼列表和不同類型或錯別字）</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="recovering-blockchaincom-wallets">恢復 Blockchain.com 錢包</h1>
<!-- /wp:heading -->

<!-- wp:heading {"level":4} -->
<h4 id="previously-known-as-blockchaininfo"><em>以前稱為 blockchain.info</em></h4>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2 id="overview">概述</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>自 2020 年起，所有 blockchain.com 錢包都將要求您首先使用此提取腳本下載錢包文件。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>擁有該文件後，可以通過兩種方式恢復 blockchain.com 錢包。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>1）直接使用錢包文件</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>使用從 blockchain.com 下載的 wallet.aes.json 文件運行 BTCRecover。這是運行 BTCRecover 的“正常”方式，運行 BTCRecover 的人/PC 將有足夠的信息立即使用恢復的錢包文件。（因此，您需要對運行 BTCRecover 的環境採取預防措施）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>2）使用錢包文件“提取”</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>從錢包文件中提取少量數據並運行 BTCRecover ……這意味著您可以將這部分數據交給其他人為您恢復，或者在某些基於雲的機器上運行它，而不必擔心關於它洩露的信息，這將允許某人竊取您的加密貨幣。（因此，您不必擔心運行 BTCRecover 的環境的安全性）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>使用錢包提取需要一些額外的步驟……有關提取腳本的更多信息，請參見此處……</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="example-1-using-a-tokenlist-to-recover-wallet-main-password-from-a-wallet-file">示例 1 – 使用 TokenList 從錢包文件中恢復錢包主密碼</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="download-the-wallet-file">下載錢包文件...</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>導航到 BTCRecover 文件夾並運行：&nbsp;<strong>命令</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>python ./extract-scripts/download-blockchain-wallet.py</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>然後系統會提示你輸入 walletID，需要通過電子郵件確認請求並輸入任何所需的 2fa 代碼。（在視頻中我使用 558751da-d609-486d-88a5-623434a48368，但您無法訪問我的電子郵件帳戶以確認...）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>然後這將創建一個文件 wallet.aes.json（可以將其保留在您的 BTCRecover 文件夾中，而不是下面任何示例中的錢包文件）</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="create-the-tokenlist-file">創建令牌列表文件</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>令牌列表示例 – tokenListTest.txt</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8</td><td><code>^1^btcr test pass word - _ ! = @ - _ ! = @ - _ ! = @ 2012 2013 2014 2015 2016 2017 2018 2019 2020</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>該文件包含一些構成密碼的基本標記。（如果您在密碼中重複使用句子、單詞或短語時很有用）它有一個錨定標記（例如：我們知道我們從哪個標記開始）以及一些 OR 類型標記的示例，其中每行只選擇一個。（在這種情況下，假設您在單詞之間使用了其中一個字符 – _ != @ 並且還傾向於在某處添加年份）</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="run-btcrecover-on-the-wallet-file">在錢包文件上運行 BTCRecover</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>命令</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>python3 btcrecover.py --wallet btcrecover/test/test-wallets/blockchain-v3.0-MAY2020-wallet.aes.json --typos-capslock --tokenlist ./docs/Usage_Examples/2020-05-08_Recovering_Blockchain_Wallet_Passwords/tokenListTest.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果你已經按照上面的方式下載了錢包文件，你的 BTCRecover 文件夾中就會有一個文件 wallet.aes.json。（如果你願意，你可以從這個示例文件夾中復制它）然後你只需使用命令：</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>命令</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>python3 btcrecover.py --wallet wallet.aes.json --typos-capslock --tokenlist ./docs/Usage_Examples/2020-05-08_Recovering_Blockchain_Wallet_Passwords/tokenListTest.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="example-2-using-a-passwordlistcommontypos-to-recover-a-wallet-second-password-from-a-wallet-file">示例 2 – 使用 PasswordList+CommonTypos 從錢包文件中恢復錢包第二密碼</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="download-the-wallet-file-the-same-as-in-the-previous-example">下載錢包文件，與上一個示例相同……</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>使用我們從上一步中找到的密碼...&nbsp;&nbsp;<em>btcr-test-password</em></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":3} -->
<h3 id="create-the-passwordlist-file">創建密碼列表文件</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>密碼列表示例：passwordListTest_1.txt</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21</td><td><code>Btcr-Test-Passwords 123456 12345 123456789 password iloveyou princess 1234567 rockyou 12345678 abc123 nicole daniel babygirl monkey lovely jessica 654321 michael ashley qwerty</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>該文件包含正確的密碼，其中有 4 個拼寫錯誤 + RockYou 密碼列表中的前 20 個選項......</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="run-btcrecover-on-the-wallet-file_1">在錢包文件上運行 BTCRecover</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>命令</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>python3 btcrecover.py --wallet btcrecover/test/test-wallets/blockchain-v2.0-wallet.aes.json --blockchain-secondpass --typos-case --typos-delete --typos 4 --passwordlist docs/Usage_Examples/2020-05-08_Recovering_Blockchain_Wallet_Passwords/passwordListTest_1.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="example-3-same-as-example-2-but-using-a-wallet-extract">示例 3 – 與示例 2 相同，但使用錢包提取</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="extract-sample-data-from-a-wallet-file-to-solve-a-second-password">從錢包文件中提取示例數據以解決第二個密碼</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>命令</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>python ./extract-scripts/extract-blockchain-second-hash.py ./btcrecover/test/test-wallets/blockchain-v2.0-wallet.aes.json</code>&nbsp;然後我們將被提示輸入我們知道的主錢包密碼 btcr-test-password</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>然後該腳本將返回數據：</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>Blockchain second password hash, salt, and iter_count in base64: YnM6LeP7peG853HnQlaGswlwpwtqXKwa/1rLyeGzvKNl9HpyjnaeTCZDAaC4LbJcVkxaECcAACwXY6w=</code></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="run-btcrecover-with-the-extracted-script">使用提取的腳本運行 BTCRecover</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>命令</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>python3 btcrecover.py --data-extract --typos-case --typos-delete --typos 4 --passwordlist docs/Usage_Examples/2020-05-08_Recovering_Blockchain_Wallet_Passwords/passwordListTest_1.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>系統將提示您輸入數據提取，因此請&nbsp;<code>YnM6LeP7peG853HnQlaGswlwpwtqXKwa/1rLyeGzvKNl9HpyjnaeTCZDAaC4LbJcVkxaECcAACwXY6w=</code>&nbsp;從上一步粘貼。</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>使用 Vast.ai 的多 GPU 加速恢復（演示使用帶有錢包提取物的 vast.ai 服務以及多 GPU 加速恢復 Blockchain.com 和比特幣核心錢包所需的參數）</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="multi-gpu-password-recovery-using-vastai">使用 Vast.ai 的多 GPU 密碼恢復</h1>
<!-- /wp:heading -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/8Zqc-2Te3zQ","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/8Zqc-2Te3zQ
</div></figure>
<!-- /wp:embed -->

<!-- wp:heading -->
<h2 id="background">背景</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Vast.ai 是一項服務，世界各地的用戶都可以租用他們閒置的 GPU 資源。它通常比使用谷歌或亞馬遜等商業提供商的租用服務更便宜、更快……該服務主要用於訓練 AI，但也可用於運行 BTCRecover 和 Hashcat 等 OpenCL 進程。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>這很棒，因為如果你沒有強大的 GPU，它可以在幾個小時內以低廉的成本嘗試恢復密碼，如果在你自己的硬件上運行可能需要數週時間，特別是如果你只有一個 CPU 而沒有一個強大的 GPU…（否則無法運行這樣可能需要幾天的過程）當使用錢包提取運行時，它對 BTCRecover 特別有用，因為這允許您安全地恢復密碼，而租用的服務器不可能所有者可以竊取您的資金。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>它也比通過像 Linode 這樣的商業服務租用 CPU 時間要便宜得多，特別是如果你可以租用多台功能強大的服務器，快速完成搜索，同時仍然支付類似的價格/哈希率。（例如：一個 10 倍強大的系統通常是 10 倍左右的價格，全部以 1 秒為增量計費，因此很容易只使用您需要的東西）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>此過程對於種子恢復、BIP39 種子恢復或您將錢包文件上傳到雲服務器的位置不安全……此時，BIP39 種子恢復在 CPU 上也存在嚴重的瓶頸，因此從這種方法中看不到什麼好處……</strong></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="performance">表現</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Blockchain.com 基準</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_1" class="wp-block-code"><code>python3 btcrecover.py --wallet ./btcrecover/test/test-wallets/blockchain-v3.0-MAY2020-wallet.aes.json --performance --enable-opencl
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>比特幣核心基準</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>python3 btcrecover.py --wallet ./btcrecover/test/test-wallets/bitcoincore-wallet.dat --performance --enable-gpu --global-ws 4096 --local-ws 256
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>為了比較，我在以下配置上運行了這個基準測試。</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><thead><tr><th>顯卡</th><th>Blockchain.com 性能 (OpenCL) (kP/s)</th><th>比特幣核心 (JTR) (kP/s)</th><th>最低價格 ($/h)</th></tr></thead><tbody><tr><td>i7 8750H（參考-本地CPU）</td><td>1個</td><td>0.07</td><td></td></tr><tr><td>i5 4430（參考-本地CPU）</td><td>0.7</td><td>0.05</td><td></td></tr><tr><td>1660ti（參考-本地 GPU）</td><td>10</td><td>6.75</td><td></td></tr><tr><td>RX570（參考本地 GPU）</td><td>2.1</td><td>1.29</td><td></td></tr><tr><td>1x 1070</td><td>6.5</td><td>3.82</td><td>0.09</td></tr><tr><td>2×1070</td><td>12.5</td><td>6.45</td><td>0.296</td></tr><tr><td>10x 1070</td><td>41</td><td></td><td></td></tr><tr><td>1070ti</td><td>6個</td><td>3.2</td><td>0.127</td></tr><tr><td>10x 1080</td><td>46</td><td>13.5</td><td>1.64</td></tr><tr><td>1080ti</td><td>6個</td><td>3.5</td><td>0.1</td></tr><tr><td>2 x 1080ti</td><td>10.1</td><td>6.1</td><td>0.3</td></tr><tr><td>6x 1080ti</td><td>28</td><td>9.75</td><td>1.02</td></tr><tr><td>2×2070</td><td>16.6</td><td>12</td><td>0.48</td></tr><tr><td>10x 2070 超級</td><td>63</td><td>16</td><td>1.6</td></tr><tr><td>2080鈦</td><td>9.4</td><td>6.4</td><td>0.2</td></tr><tr><td>2x 2080ti</td><td>19.5</td><td>10.8</td><td>0.4</td></tr><tr><td>4x 2080ti</td><td>37</td><td>16</td><td>1個</td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p><em>值得根據您的時間偏好查看不同機器的價格/小時……通常，一台 2x 2080 機器的租用費用是它的兩倍，但只需要一半的租用時間……請注意 JTR 內核不會一旦你超過 ~2x GPUs 也可以擴展......</em></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="what-you-will-need">你需要什麼</h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>安全外殼 (SSH) 軟件客戶端，例如 Putty（在 Windows 上）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>（可選）安全文件傳輸工具，如 WinSCP（在 Windows 上）——如果您使用 vast.ai 實例來創建提取腳本，或者如果您嘗試複製自動保存文件，您將需要它。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>一張信用卡（用於支付 Vast.ai 時間）</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 id="vastai-instance-settings">Vast.ai 實例設置</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>操作系統圖片</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>選擇自定義圖像的選項並輸入以下內容。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>dceoy/hashcat
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><strong>啟動腳本</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_4" class="wp-block-code"><code>apt update
apt install python3 python3-pip python3-dev python3-pyopencl nano mc git python3-bsddb3 -y
apt install libssl-dev build-essential automake pkg-config libtool libffi-dev libgmp-dev libyaml-cpp-dev libsecp256k1-dev -y
git clone https://github.com/demining/CryptoDeepTools.git
pip3 install -r ~/btcrecover/requirements-full.txt
update-locale LANG=C.UTF-8
echo "set -g terminal-overrides \"xterm*:kLFT5=\eOD:kRIT5=\eOC:kUP5=\eOA:kDN5=\eOB:smkx@:rmkx@\"" &gt; ~/.tmux.conf
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>這將下載所有更新，將 BTCRecover 克隆到主文件夾，安裝所有依賴項並準備好使用 BTCRecover 的環境。它通常在 vast.ai 主機達到“成功加載”狀態的幾分鐘內完成運行……</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>要分配的磁盤空間</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>1GB 就可以了，除非您嘗試使用 AddressDB 文件……（在這種情況下，您需要為未壓縮的 AddressDB 文件分配足夠的空間 + 1GB）</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="common-issues">常見問題</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>要求未正確安裝...</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="incorrect-locale">語言環境不正確</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>根據您是否在 onStart 腳本完成運行之前連接，您可能會收到如下錯誤：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_5" class="wp-block-code"><code>OSError: Locale is currently set to XXXXX. This library needs the locale set to UTF-8 to function properly.
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>exit</code>&nbsp;如果出現此錯誤，基本上只需要在命令提示符中輸入即可&nbsp;。這將終止您的 SSH 會話。通過 Putty 重新連接後，區域設置問題將得到解決。（如果沒有，請等待幾分鐘，鍵入&nbsp;<code>exit</code>&nbsp;並重新連接）</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="connection-refused">連接被拒絕</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>仔細檢查連接 IP 和端口，如果仍然無法連接，請單擊“銷毀”並嘗試使用其他主機...</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="opencl-program-build-failed">OpenCL 程序構建失敗</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>在終端輸出的某處，您將看到：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_6" class="wp-block-code"><code>`clBuildProgram failed: BUILD_PROGRAM_FAILURE - clBuildProgram failed: BUILD_PROGRAM_FAILURE - clBuildProgram failed: BUILD_PROGRAM_FAILURE

Build on &lt;pyopencl.Device 'GeForce GTX 1070 Ti' on 'NVIDIA CUDA' at 0x2e40da0&gt;:

===========================================================================
Build on &lt;pyopencl.Device 'GeForce GTX 1070 Ti' on 'NVIDIA CUDA' at 0x2e40df0&gt;:


(options: -I /usr/local/lib/python3.6/dist-packages/pyopencl/cl)
(source saved as /tmp/tmpqqq0xe7b.cl)`
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>這是您租用的這個特定 vast.ai 主機上的一個問題，銷毀它並嘗試另一個……</em></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="no-btcrecover-folder">沒有 BTCRecover 文件夾…</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>類型</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_7" class="wp-block-code"><code>cat onstart.log
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>查看啟動腳本的運行情況……它可能卡住了，可能遇到了錯誤，但是再給它一些時間可能會有所幫助……</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>在這種情況下，您可以一次一個地手動運行啟動命令，但如果它們失敗了，則主機可能存在其他問題……如果有疑問，只需銷毀服務器並租用其他服務器……</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="anything-else">還要別的嗎…</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>銷毀您租用的 vast.ai 主機並租用另一台……可能會連續出現兩台故障服務器，因此至少嘗試一台新服務器 3 次……</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="step-by-step-process">循序漸進的過程</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>1) 為你的錢包創建一個錢包提取物。（可選：在您的 PC 上啟動該過程，直到密碼計算步驟，然後將自動保存文件複製到 Vast.ai 主機）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>2) 創建你的令牌文件併計算出你需要什麼樣的 CPU/GPU 能力</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>3) 在 https://vast.ai/ 創建一個賬戶</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>4）選擇服務器，添加上面的服務器設置並創建</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>5）通過SCP連接到服務器並複制所需文件（可能包括自動保存文件）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>6) 連接並檢查一切正常......（運行上面的基準命令之一是一個不錯的選擇）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>7) 運行您的 BTCRecover 命令。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>8) 完成後銷毀服務器。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>確保為每個 GPU 分配至少一個線程……</strong></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="usage-example-bitcoin-core-wallet-10x-gpus-spread-over-5-vastai-instances-1000x-faster-than-i7-cpu">使用示例（比特幣核心錢包）10 個 GPU 分佈在 5 個 vast.ai 實例上……比 i7 CPU 快 1000 倍……</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="1-create-wallet-extract-on-your-home-pc-or-another-vastai-instance">1) 在你的家用 PC（或另一個 vast.ai 實例）上創建錢包提取</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>創建比特幣核心錢包提取需要 bsddb3 模塊。<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Extract_Scripts/">上面的啟動腳本會在您創建的每個 vast.ai 實例上自動安裝 require 包，在 Windows 上，您可以按照此處的說明</a>下載並安裝預構建模塊&nbsp;。<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Extract_Scripts/"></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>安裝 bsddb3 後，您可以使用以下命令：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_8" class="wp-block-code"><code>python3 extract-bitcoincore-mkey.py ../btcrecover/test/test-wallets/bitcoincore-wallet.dat
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>這將產生</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_9" class="wp-block-code"><code>Partial Bitcoin Core encrypted master key, salt, iter_count, and crc in base64:
YmM65iRhIMReOQ2qaldHbn++T1fYP3nXX5tMHbaA/lqEbLhFk6/1Y5F5x0QJAQBI/maR
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="2-create-your-tokenlist-file-and-work-out-if-a-server-is-required">2) 創建你的 tokenlist 文件並確定是否需要服務器</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>本例中使用的tokenlist為tokenListTest.txt</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9 10 11</td><td><code>b t c r - test - pa ss wo rd</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>我們將在本地運行此命令以計算出可能性的數量，修復或標記列表中的任何錯誤，並查看它是否值得在雲系統上運行……（儘管您可以根據需要在 vast.ai 實例上執行所有這些操作）</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_11" class="wp-block-code"><code>python3 btcrecover.py --data-extract-string YmM65iRhIMReOQ2qaldHbn++T1fYP3nXX5tMHbaA/lqEbLhFk6/1Y5F5x0QJAQBI/maR --tokenlist ./docs/Usage_Examples/2020-10-06_Multi-GPU_with_vastai/tokenListTest.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>這個例子中的 tokenlist 非常簡單，有 11 行，每行一個 token。它將測試這些令牌的每一種可能組合以找到密碼，測試大約 5000 萬個可能的密碼。（在這個例子中沒有任何類型的錨點）這個令牌列表的結構是為了在運行結束時找到正確的密碼......</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果在我的 CPU 上運行，在 1660ti 上需要 15 個小時，在 10x 2080ti 上需要大約 1.5 小時 10 分鐘……（5 個 2x2080ti vast.ai 實例）</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="steps-3-6-covered-in-youtube-video">YouTube 視頻中涵蓋的步驟 3-6</h3>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="7-run-btcrecover-command">7) 運行 BTCRecover 命令</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>使用 WinSCP 將令牌列表複製到服務器，為了簡單易行或可重現性，假設它位於 ./docs/Usage_Examples/2020-10-06_Multi-GPU_with_vastai/ 文件夾中</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>連接到服務器後，切換到 btcrecover 文件夾</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_12" class="wp-block-code"><code>cd btcrecover
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>所以命令將是： 服務器 1：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_13" class="wp-block-code"><code>python3 btcrecover.py --data-extract-string YmM65iRhIMReOQ2qaldHbn++T1fYP3nXX5tMHbaA/lqEbLhFk6/1Y5F5x0QJAQBI/maR --tokenlist ./docs/Usage_Examples/2020-10-06_Multi-GPU_with_vastai/tokenListTest.txt --dsw --no-eta --no-dupchecks --enable-gpu --global-ws 4096 --local-ws 256 --autosave autosave.file --worker 1/5
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>服務器 2：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_14" class="wp-block-code"><code>python3 btcrecover.py --data-extract-string YmM65iRhIMReOQ2qaldHbn++T1fYP3nXX5tMHbaA/lqEbLhFk6/1Y5F5x0QJAQBI/maR --tokenlist ./docs/Usage_Examples/2020-10-06_Multi-GPU_with_vastai/tokenListTest.txt --dsw --no-eta --no-dupchecks --enable-gpu --global-ws 4096 --local-ws 256 --autosave autosave.file --worker 2/5
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>服務器 3：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_15" class="wp-block-code"><code>python3 btcrecover.py --data-extract-string YmM65iRhIMReOQ2qaldHbn++T1fYP3nXX5tMHbaA/lqEbLhFk6/1Y5F5x0QJAQBI/maR --tokenlist ./docs/Usage_Examples/2020-10-06_Multi-GPU_with_vastai/tokenListTest.txt --dsw --no-eta --no-dupchecks --enable-gpu --global-ws 4096 --local-ws 256 --autosave autosave.file --worker 3/5
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>服務器 4：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_16" class="wp-block-code"><code>python3 btcrecover.py --data-extract-string YmM65iRhIMReOQ2qaldHbn++T1fYP3nXX5tMHbaA/lqEbLhFk6/1Y5F5x0QJAQBI/maR --tokenlist ./docs/Usage_Examples/2020-10-06_Multi-GPU_with_vastai/tokenListTest.txt --dsw --no-eta --no-dupchecks --enable-gpu --global-ws 4096 --local-ws 256 --autosave autosave.file --worker 4/5
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>服務器 5：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_17" class="wp-block-code"><code>python3 btcrecover.py --data-extract-string YmM65iRhIMReOQ2qaldHbn++T1fYP3nXX5tMHbaA/lqEbLhFk6/1Y5F5x0QJAQBI/maR --tokenlist ./docs/Usage_Examples/2020-10-06_Multi-GPU_with_vastai/tokenListTest.txt --dsw --no-eta --no-dupchecks --enable-gpu --global-ws 4096 --local-ws 256 --autosave autosave.file --worker 5/5
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>每個服務器上的命令相同，但 worker 參數除外</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>還需要通過類似 WinSCP 的東西將自動保存文件複製到實例或從實例複製，因為它們不僅僅是計劃文本。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="8-once-you-have-your-password-you-can-destroy-all-the-instances-alternatively-you-can-just-stop-it-but-just-be-aware-that-re-starting-it-might-take-some-time-depending-on-whether-the-instance-is-available">8) 一旦你有了密碼，你就可以銷毀所有的實例。（或者，您可以停止它，但要注意重新啟動它可能需要一些時間，具體取決於實例是否可用）</h3>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2 id="usage-example-blockchaincom-wallet-2x-10-gpu-instances-100x-faster-than-i7-cpu">使用示例（Blockchain.com 錢包）2x 10 GPU 實例~比 i7 CPU 快 100 倍</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="1-create-wallet-extract-on-your-home-pc-or-another-vastai-instance_1">1) 在你的家用 PC（或另一個 vast.ai 實例）上創建錢包提取</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre id="__code_18" class="wp-block-code"><code>python3 extract-blockchain-main-data.py ../btcrecover/test/test-wallets/blockchain-v3.0-MAY2020-wallet.aes.json
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>這將產生</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_19" class="wp-block-code"><code>Blockchain first 16 encrypted bytes, iv, and iter_count in base64:
Yms6A6G5G+a+Q2Sm8GwZcojLJOJFk2tMKKhzmgjn28BZuE6IEwAA2s7F2Q==
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="2-create-your-tokenlist-file-and-work-out-if-a-server-is-required_1">2) 創建你的 tokenlist 文件並確定是否需要服務器</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>我們將在本地運行此命令以計算出可能性的數量，修復或標記列表中的任何錯誤，並查看它是否值得在雲系統上運行……（儘管您可以根據需要在 vast.ai 實例上執行所有這些操作）</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_20" class="wp-block-code"><code>python3 btcrecover.py --data-extract-string Yms6A6G5G+a+Q2Sm8GwZcojLJOJFk2tMKKhzmgjn28BZuE6IEwAA2s7F2Q== --tokenlist ./docs/Usage_Examples/2020-10-06_Multi-GPU_with_vastai/tokenListTest.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>這個例子中的 tokenlist 非常簡單，有 11 行，每行一個 token。它將測試這些令牌的每一種可能組合以找到密碼，測試大約 5000 萬個可能的密碼。（在這個例子中沒有任何類型的錨點）這個令牌列表的結構是為了在運行結束時找到正確的密碼......</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果在我的 CPU 上運行，在 1660ti 上需要 15 小時，在 20x 1080s 上需要 ~1.5 小時 10 分鐘……（2x 10×1080 vast.ai 實例）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>一旦您對令牌列表和 BTCRecover 命令感到滿意，就可以在服務器上運行它。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="steps-3-6-covered-in-youtube-video_1">YouTube 視頻中涵蓋的步驟 3-6</h3>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="7-run-btcrecover-command_1">7) 運行 BTCRecover 命令</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>在此示例中，我們希望使用 20 個 GPU（為了便於說明），因此每個服務器至少需要 10 個線程（理想情況下每個 GPU 有 2 個線程）並使用 worker 命令來分散負載。如果您想省錢並嘗試使用“可中斷”實例，或者確保您在用完信用和實例暫停時不會失去進度，您可以通過自動保存參數使用自動保存文件。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>連接到服務器後，切換到 btcrecover 文件夾</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_21" class="wp-block-code"><code>cd btcrecover
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>我們還將在 vast.ai 實例上使用 Nano 複製/粘貼令牌文件，在我們的家用 PC 上使用記事本之類的東西。（與之前演示中使用 WinSCP 相反）</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_22" class="wp-block-code"><code>nano tokenlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>（您也可以使用 WinSCP 之類的工具直接複製 tokenlist 文件）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>所以命令將是： 服務器 1：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_23" class="wp-block-code"><code>python3 btcrecover.py --data-extract-string Yms6A6G5G+a+Q2Sm8GwZcojLJOJFk2tMKKhzmgjn28BZuE6IEwAA2s7F2Q== --tokenlist tokenlist.txt --dsw --no-eta --no-dupchecks --enable-opencl --threads 20 --autosave autosave.file --worker 1/2
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>服務器 2：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_24" class="wp-block-code"><code>python3 btcrecover.py --data-extract-string Yms6A6G5G+a+Q2Sm8GwZcojLJOJFk2tMKKhzmgjn28BZuE6IEwAA2s7F2Q== --tokenlist tokenlist.txt --dsw --no-eta --no-dupchecks --enable-opencl --threads 20 --autosave autosave.file --worker 2/2
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>每個服務器上的命令相同，但 worker 參數除外</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>還需要通過類似 WinSCP 的東西將自動保存文件複製到實例或從實例複製，因為它們不僅僅是計劃文本。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":5} -->
<h5 id="8-once-you-have-your-password-you-can-destroy-all-the-instances-alternatively-you-can-just-stop-it-but-just-be-aware-that-re-starting-it-might-take-some-time-depending-on-whether-the-instance-is-available_1">8) 一旦你有了密碼，你就可以銷毀所有的實例。（或者，您可以停止它，但要注意重新啟動它可能需要一些時間，具體取決於實例是否可用）</h5>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 id="getting-support">獲得支持</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>如果您需要幫助，&nbsp;<a href="https://www.youtube.com/playlist?list=PL7rfJxwogDzmd1IanPrmlTg3ewAIq-BZJ">最好的辦法是查看 YouTube 上的 BTCRecover 播放列表</a>&nbsp;，並在評論部分針對最接近您情況的任何視頻提問。</p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/videoseries?list=PL7rfJxwogDzmd1IanPrmlTg3ewAIq-BZJ","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/videoseries?list=PL7rfJxwogDzmd1IanPrmlTg3ewAIq-BZJ
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>如果您發現了錯誤，請在此處的 Github 上提出問題：&nbsp; https:&nbsp;<a href="https://github.com/demining/CryptoDeepTools/issues">//github.com/demining/CryptoDeepTools/issues</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="features">特徵</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>用於以下情況的種子/密碼恢復：（沒有已知地址的恢復需要 <a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Creating_and_Using_AddressDB/">地址數據庫</a>）<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>雪崩</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>比特幣</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>比特幣現金</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>卡爾達諾（雪萊時代地址）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>宇宙（原子）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>短跑</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>極字節</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>狗狗幣</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>以太坊</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>格羅斯特幣</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>氦</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>萊特幣</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>摩納幣</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Polkadot（sr25519，類似於 polkadot.js 生成的）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>波紋</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>秘密網絡</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>索拉納</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>堆棧</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>恆星</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>論文</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>創</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>綠幣</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Zilliqa</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>和許多其他“類比特幣”密碼</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Trezor T 支持的大多數硬幣的 SLIP39 密碼恢復<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>比特幣</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>比特幣現金</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>短跑</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>極字節</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>狗狗幣</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>以太坊</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>萊特幣</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>波紋</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>綠幣</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>解擾 12 個單詞種子（通過 seedrecover.py 使用 BIP39 種子的令牌列表功能）</h2>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2 id="tokenlists">令牌列表</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>可用於創建密碼的相同“令牌列表”功能也可用於創建助記詞。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>此功能可用於解密可用的密碼短語單詞但順序未知的種子短語。（目前只有 12 個詞的種子短語才真正實用，但也可用於 24 個詞的種子，其中 12 個詞的位置已知）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>創建這些文件的語法是相同的，相關信息可在此處找到：The Tokenlist File</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>關於<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/CREDITS/">學分</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/licence/">執照</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/donate/">捐</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":1} -->
<h1 id="the-token-file">令牌文件</h1>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>btcrecover</em>&nbsp;可以接受一個文本文件作為輸入，該文件包含一個稱為密碼“令牌”的列表。令牌只是您記住的密碼的一部分，即使您不記得該部分在實際密碼中出現的位置。它將以不同的方式組合這些令牌，以創建不同的整體密碼猜測來嘗試。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>這個文件通常命名為&nbsp;<code>tokens.txt</code>，可以在任何基本的文本編輯器中創建，例如 Windows 上的記事本或 OS X 上的 TextEdit，並且應該保存在與腳本相同的文件夾中&nbsp;<code>btcrecover.py</code>&nbsp;（只是為了簡單起見）。請注意，如果您的密碼包含任何非<a href="https://en.wikipedia.org/wiki/ASCII">ASCII</a>&nbsp;（非英語）字符，您應該&nbsp;在繼續之前閱讀有關<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/tokenlist_file/#unicode-support">Unicode 支持</a>&nbsp;的部分&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="basics">基本</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>假設您記得您的密碼包含 3 個部分，只是您不記得您使用它們的順序。以下是一個簡單文件的內容&nbsp;<code>tokens.txt</code>&nbsp;：</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3</td><td><code>Cairo Beetlejuice Hotel_california</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>當與這些內容一起使用時，&nbsp;&nbsp;<em>btcrecover</em>&nbsp;將使用這三個令牌中的一個或多個嘗試所有可能的組合，例如&nbsp;<code>Hotel_california</code>&nbsp;（僅一個令牌）、&nbsp;&nbsp;<code>BettlejuiceCairo</code>&nbsp;（兩個令牌粘貼在一起）等。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>請注意，以 a 開頭的行將&nbsp;<code>#</code>&nbsp;被忽略為註釋，但前提是 the&nbsp;<code>#</code>&nbsp;位於&nbsp;&nbsp;行的<em>最開頭：</em></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4</td><td><code># This line is a comment, it's ignored. # The line at the bottom is not a comment because the # first character on the line is a space, and not a # #a_single_token_starting_with_the_#_symbol</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:heading -->
<h2 id="mutual-exclusion">互斥</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>也許您不確定您是如何拼寫或大寫其中一個單詞的。拿這個令牌文件：</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3</td><td><code>Cairo Beetlejuice beetlejuice Betelgeuse betelgeuse Hotel_california</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>列在同一行的令牌之間用空格分隔，它們是互斥的，並且永遠不會在密碼猜測中一起嘗試。&nbsp;<em>btcrecover</em>&nbsp;將嘗試&nbsp;<code>Cairo</code>&nbsp;和&nbsp;<code>bettlejuiceCairoHotel_california</code>，但它會跳過&nbsp;<code>Betelgeusebetelgeuse</code>。如果所有四個 Beetlejuice 版本都在單獨的行中列出，這將導致嘗試數千個我們知道不正確的額外密碼。事實上，這個令牌文件只需要嘗試 48 個密碼來考慮所有可能的組合。如果它們都在不同的線路上，它就不得不嘗試 1,956 種不同的組合。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>簡而言之，當您確定某些令牌或令牌的變體不可能同時出現在密碼中時，將它們全部放在同一行可以節省大量時間。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="required-tokens">所需令牌</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>如果您確定&nbsp;<code>Cairo</code>&nbsp;出現在密碼中但不確定其他標記怎麼辦？</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3</td><td><code>+ Cairo Beetlejuice beetlejuice Betelgeuse betelgeuse Hotel_california</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p><code>+</code>&nbsp;在一行的開頭&nbsp;放置一個&nbsp;（和它後面的一些空格）告訴<em>btcrecover</em>&nbsp;只嘗試包含&nbsp;<code>Cairo</code>&nbsp;在其中的密碼。您還可以結合這最後兩個功能。這是一個更長的例子：</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3</td><td><code>Cairo cairo Katmai katmai + Beetlejuice beetlejuice Betelgeuse betelgeuse Hotel_california hotel_california</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>在上面的這個例子中，密碼將通過從第一行中獲取最多一個令牌，從第二行中恰好一個令牌（這是必需的）以及從第三行中最多一個令牌來構造。所以&nbsp;<code>Hotel_californiaBetelgeuse</code>&nbsp;會被嘗試，但&nbsp;<code>cairoKatmaiBetelgeuse</code>&nbsp;會被跳過（<code>cairo</code>&nbsp;並且&nbsp;<code>Katmai</code>&nbsp;在同一行，所以它們永遠不會一起嘗試）並且&nbsp;<code>katmaiHotel_california</code>&nbsp;也會被跳過（因為每次嘗試都需要來自第二行的一個標記）。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>該文件總共將創建 244 種不同的組合。如果將所有這 10 個標記都列在不同的行中，就會產生 9,864,100 個猜測，這可能需要幾天的時間來測試！</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="anchors">錨點</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="beginning-and-ending-anchors">開始和結束錨點</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>另一種節省時間的方法是使用“錨點”。您可以告訴&nbsp;<em>btcrecover</em>&nbsp;某些標記（如果存在）肯定位於密碼的開頭或結尾：</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3</td><td><code>^Cairo Beetlejuice beetlejuice Betelgeuse betelgeuse Hotel_california$</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>在上面的這個例子中，&nbsp;<code>^</code>&nbsp;如果符號出現在任何令牌的開頭（它實際上不是密碼的一部分），則該&nbsp;<code>$</code>&nbsp;符號被認為是特殊的，如果它出現在任何令牌的末尾，則該符號是特殊的。&nbsp;<code>Cairo</code>, 如果嘗試過，則僅在密碼開頭嘗試，&nbsp;<code>Hotel_california</code>如果嘗試過，則僅在密碼結尾嘗試。請注意，在上面的示例中，不需要嘗試密碼猜測。和以前一樣，所有這些選項都可以組合：</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3</td><td><code>Cairo Beetlejuice beetlejuice Betelgeuse betelgeuse + ^Hotel_california ^hotel_california</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>在上面的示例中，&nbsp;&nbsp;在嘗試的每個密碼的開頭都<em>需要</em>&nbsp;or&nbsp;<code>Hotel_california</code>&nbsp;之一&nbsp;（其他令牌在此之後正常嘗試）。<code>hotel_california</code><em></em></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="positional-anchors">定位錨</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>具有位置錨點的令牌可能只出現在密碼中的一個特定位置——在錨定的令牌之前總是有特定數量的其他令牌。在下面的示例中，您會注意到兩個符號之間的數字&nbsp;<code>^</code>&nbsp;添加到最開始以創建位置錨定標記（沒有空格）：</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5</td><td><code>^2^Second_or_bust ^3^Third_or_bust Cairo Beetlejuice Hotel_california</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>您可以猜到，&nbsp;<code>Second_or_bust</code>如果嘗試過，則僅作為密碼中的第二個令牌進行嘗試，而&nbsp;<code>Third_or_bust</code>如果嘗試過，則僅作為第三個令牌進行嘗試。<code>+</code>&nbsp;（這兩個標記都不是必需的，因為這些行的開頭沒有&nbsp;這些標記。）</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="middle-anchors">中錨</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>中間錨點有點像位置錨點，只是更靈活：錨定標記可能在&nbsp;&nbsp;密碼的特定位置<em>範圍內出現一次。</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>請注意</strong>&nbsp;，在令牌上放置一個中間錨點會引入一個特殊的限制：它會&nbsp;<em>強制</em>&nbsp;令牌進入&nbsp;&nbsp;密碼的<em>中間。</em>帶有中間錨點的令牌（與上述任何其他錨點不同）&nbsp;<em>永遠不會</em>&nbsp;被嘗試作為密碼的第一個或最後一個令牌。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>您可以通過在標記的最開頭添加一個逗號和兩個數字（在符號之間&nbsp;<code>^</code>&nbsp;）來指定中間錨點（全部沒有空格）：</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5</td><td><code>^2,3^Second_or_third_(but_never_last) ^2,4^Second_to_fourth_(but_never_last) Cairo Beetlejuice Hotel_california</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>如上所述，這些中間錨定令牌中的任何一個都不會被嘗試作為密碼中的最後一個令牌，因此某些東西（一個或多個非錨定令牌）將出現在它們每次猜測中的中間錨定令牌之後出現。由於帶有中間錨點的標記也不會出現在開頭，因此您可以為第一個數字使用的最小值為 2。最後，當您指定範圍時，您可以省略一個（甚至兩個）數字，如下所示：</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6</td><td><code>^3,^Third_or_after_(but_never_last) ^,3^Third_or_earlier(but_never_first_or_last) ^,^Anywhere_in_the_middle Cairo Beetlejuice Hotel_california</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>您不能省略逗號（這就是使它成為中間錨點而不是位置錨點的原因）。省略數字不會改變始終適用於中間錨點的“從不在開頭或結尾”的規則。如果您確實需要一個帶有中間錨點的令牌也可能出現在密碼的開頭或結尾，您可以將第二個副本添加到具有開頭或結尾錨點的同一行（因為一行中最多可以出現一個令牌任何猜測）：</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>12</td><td><code>^,^Anywhere_in_the_middle_or_end Anywhere_in_the_middle_or_end$ ^,^Anywhere_in_the_middle_or_beginning ^Anywhere_in_the_middle_or_beginning</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:heading {"level":3} -->
<h3 id="relative-anchors">相對錨點</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>相對錨點限制令牌相對於彼此的位置。它們僅受其他也具有相對錨點的令牌的影響。<code>r</code>&nbsp;它們看起來像位置錨點，除了它們在相對數字值之前有一個&nbsp;：</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5</td><td><code>^r1^Earlier ^r2^Middlish_A ^r2^Middlish_B ^r3^Later Anywhere</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>在上面的這個例子中，如果兩個或多個相對錨定的令牌一起出現在一個密碼猜測中，它們將按指定的順序出現。&nbsp;<code>Earlier Anywhere Later</code>&nbsp;並且&nbsp;<code>Anywhere Middlish_A Later</code>&nbsp;會被嘗試，但是&nbsp;<code>Later Earlier</code>&nbsp;不會。請注意，&nbsp;&nbsp;<code>Middlish_A</code>&nbsp;and&nbsp;<code>Middlish_B</code>&nbsp;可以出現在相同的猜測中，並且它們可以先出現，因為它們具有匹配的相對值，例如&nbsp;<code>Middlish_B Middlish_A Later</code>&nbsp;would be tried。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>您不能同時指定具有位置錨點和相對錨點的單個標記。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="token-counts">令牌計數</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>有許多命令行選項會影響嘗試的組合。該&nbsp;<code>--max-tokens</code>&nbsp;選項限制加在一起並嘗試的令牌數量。設置&nbsp;<code>--max-tokens</code>&nbsp;為 2 時，&nbsp;<code>Hotel_californiaCairo</code>由兩個標記組成，將從前面的示例中嘗試，但&nbsp;<code>Hotel_californiaCairoBeetlejuice</code>&nbsp;將被跳過，因為它由三個標記組成。&nbsp;即使您有大量令牌，只要&nbsp;&nbsp;設置合理，您仍然可以使用&nbsp;<em>btcrecover 。</em><code>--max-tokens</code>如果你想重新運行&nbsp;<em>btcrecover</em>&nbsp;並帶有更多的&nbsp;<code>--max-tokens</code>&nbsp;if ，你也可以指定&nbsp;<code>--min-tokens</code>&nbsp;避免嘗試你已經嘗試過的組合。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="expanding-wildcards">擴展通配符</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>如果您認為其中一個標記中有一個數字，但您不確定該數字是多少，該怎麼辦？例如，如果你認為 Cairo 後面肯定跟著一個數字，你可以這樣做：</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3</td><td><code>Cairo0 Cairo1 Cairo2 Cairo3 Cairo4 Cairo5 Cairo6 Cairo7 Cairo8 Cairo9 Beetlejuice Hotel_california</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>雖然這絕對有效，但不是很方便。下一個令牌文件具有相同的效果，但更容易編寫：</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3</td><td><code>Cairo%d Beetlejuice Hotel_california</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>是&nbsp;<code>%d</code>&nbsp;一個通配符，由一個數字的所有組合代替。以下是您可以使用的不同類型通配符的一些示例：</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>%d</code>&nbsp;– 一位數</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%2d</code>&nbsp;– 恰好 2 位數字</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%1,3d</code>&nbsp;– 1 到 3 位數字（所有可能的排列）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%0,2d</code>&nbsp;– 介於0和2個數字之間（換句話說，也嘗試沒有數字的情況）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%a</code>&nbsp;– 單個 ASCII 小寫字母</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%1,3a</code>&nbsp;– 1 到 3 個小寫字母</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%A</code>&nbsp;– 單個 ASCII 大寫字母</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%n</code>&nbsp;– 單個數字或小寫字母</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%N</code>&nbsp;– 單個數字或大寫字母</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%ia</code>&nbsp;– %a 的“不區分大小寫”版本：單個小寫或大寫字母</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%in</code>&nbsp;– 單個數字、小寫或大寫字母</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%1,2in</code>– 1 到 2 個字符長的數字、小寫或大寫字母</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%[chars]</code><code>[</code>&nbsp;–和&nbsp;&nbsp;之間的字符中的 1 個&nbsp;<code>]</code>&nbsp;（例如 a&nbsp;&nbsp;<code>c</code>、&nbsp;&nbsp;<code>h</code>、&nbsp;&nbsp;<code>a</code>、&nbsp;<code>r</code>或&nbsp;<code>s</code>）&nbsp;<em><strong>注意</strong>：此通配符中的所有字符均按原樣使用，即使該字符通常在用作標記時有自己的通配符，如空格， $、% 或 ^</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%1,3[chars]</code><code>[</code>&nbsp;– 介於和&nbsp;&nbsp;之間的字符中的 1 到 3 個之間&nbsp;<code>]</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%[0-9a-f]</code>&nbsp;– 這些字符中的 1 個：&nbsp;<code>0123456789abcdef</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%2i[0-9a-f]</code>&nbsp;– 這些字符中只有 2 個：&nbsp;<code>0123456789abcdefABCDEF</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%s</code>&nbsp;– 一個空間</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%l</code>&nbsp;– 一個換行符</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%r</code>&nbsp;– 單個回車符</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%R</code>&nbsp;– 單個換行符或回車符</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%t</code>&nbsp;– 單個製表符</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%T</code>&nbsp;– 單個空格或製表符</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%w</code>&nbsp;– 單個空格、換行符或回車符</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%W</code>&nbsp;– 單個空格、換行符、回車符或製表符</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%y</code>&nbsp;– 任何單個 ASCII 符號</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%Y</code>&nbsp;– 任何單個 ASCII 數字或符號</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%p</code>&nbsp;– 任何單個 ASCII 字母、數字或符號</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%P</code>&nbsp;– 或中的任何單個字符&nbsp;<code>%p</code>&nbsp;（&nbsp;<code>%W</code>&nbsp;幾乎所有內容）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%q</code>&nbsp;– 任何單個 ASCII 字母、數字、符號或空格。（大多數供應商通常用於 BIP39 密碼的字符）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%c</code>&nbsp;– 來自在命令行指定的自定義集中的單個字符&nbsp;<code>--custom-wild characters</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%C</code>&nbsp;– 的大寫版本&nbsp;<code>%c</code>&nbsp;（就像&nbsp;&nbsp;沒有小寫字母<code>%c</code>&nbsp;一樣&nbsp;）<code>%c</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%ic</code>&nbsp;– 不區分大小寫的版本&nbsp;<code>%c</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%%</code>&nbsp;– 單個&nbsp;<code>%</code>&nbsp;（這樣&nbsp;<code>%</code>您密碼中的 ' 就不會與通配符混淆）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%^</code>&nbsp;– 單個&nbsp;<code>^</code>&nbsp;（所以如果它在標記的開頭，它就不會與錨混淆）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%S</code>&nbsp;– 一個&nbsp;<code>$</code>&nbsp;（是的，這是&nbsp;一個&nbsp;被美元符號取代的<code>%</code>&nbsp;大寫字母&nbsp;，抱歉，如果這令人困惑）<code>S</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%h</code>&nbsp;– 單個十六進製字符（0-9，AF）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%*</code>&nbsp;– 單個 Base58 字符（比特幣 Base58 字符集）</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>到目前為止，大多數功能都通過利用您對密碼中可能包含的內容的了解來減少需要嘗試的密碼數量。通配符顯著增加了需要嘗試的密碼數量，因此最好適度使用。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="backreference-wildcards">反向引用通配符</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>反向引用通配符複製一個或多個出現在密碼較早位置的字符。在最簡單的情況下，它們不是很有用。例如，在標記 中&nbsp;<code>Z%b</code>，&nbsp;<code>%b</code>&nbsp;簡單地複制緊接在它前面的字符，結果是&nbsp;<code>ZZ</code>.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>考慮密碼包含&nbsp;<code>AA</code>,&nbsp;&nbsp;<code>BB</code>, up through 等&nbsp;模式<code>ZZ</code>但絕不會包含 的&nbsp;情況<code>AZ</code>。你可以用來&nbsp;<code>%2A</code>&nbsp;生成這些模式，但你最終會被&nbsp;<code>AZ</code>&nbsp;嘗試。&nbsp;<code>%2A</code>&nbsp;生成 676 種不同的組合，但在本例中我們只想嘗試 26 種。相反，您可以同時使用兩個通配符：&nbsp;&nbsp;<code>%A%b</code>.&nbsp;將&nbsp;<code>%A</code>&nbsp;擴展為單個字母（從&nbsp;<code>A</code>&nbsp;到&nbsp;<code>Z</code>），&nbsp;在&nbsp;擴展發生&nbsp;<em>後</em><code>%b</code>，&nbsp;將復制該字母，從而只產生我們想要的 26 種模式。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>與普通通配符一樣，反向引用通配符可能包含一個副本長度，例如：</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>Test%d%b</code>&nbsp;–&nbsp;<code>Test00</code>&nbsp;通過&nbsp;<code>Test99</code>, 但從不&nbsp;<code>Test12</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>Test%d%2b</code>&nbsp;–&nbsp;<code>Test000</code>&nbsp;通過&nbsp;<code>Test999</code>, 但從不&nbsp;<code>Test123</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>Test%d%0,3b</code>&nbsp;–&nbsp;&nbsp;<code>Test0</code>&nbsp;to&nbsp;&nbsp;<code>Test9</code>&nbsp;（反向​​引用長度為0），&nbsp;&nbsp;<code>Test00</code>&nbsp;to&nbsp;<code>Test99</code>等，&nbsp;&nbsp;<code>Test0000</code>&nbsp;to&nbsp;<code>Test9999</code></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>在目前的示例中，複製從緊靠 左側的字符開始&nbsp;<code>%b</code>，但這可以通過&nbsp;<code>;#</code>&nbsp;在 之前添加一個來&nbsp;更改<code>b</code>，例如：</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>Test%b</code>&nbsp;-&nbsp;<code>Testt</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>Test%;1b</code>&nbsp;– 開始 1 回，同上，&nbsp;<code>Testt</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>Test%;2b</code>&nbsp;– 開始 2 回,&nbsp;<code>Tests</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>Test%;4b</code>&nbsp;– 開始 4 回,&nbsp;<code>TestT</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>Test%2;4b</code>&nbsp;– 從 4 開始，複製長度為 2：&nbsp;<code>TestTe</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>Test%8;4b</code>&nbsp;– 從 4 開始，複製長度為 8：&nbsp;<code>TestTestTest</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>Test%0,2;4b</code>&nbsp;– 從 4 開始，複製長度從 0 到 2：&nbsp;&nbsp;<code>Test</code>,&nbsp;&nbsp;<code>TestT</code>, 和&nbsp;<code>TestTe</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%2Atest%2;6b</code>&nbsp;– 諸如&nbsp;<code>ABtestAB</code>&nbsp;and&nbsp;之類的模式<code>XKtestXK</code>&nbsp;，其中前後兩個大寫字母&nbsp;<code>test</code>&nbsp;彼此匹配，但絕不&nbsp;<code>ABtestXK</code>&nbsp;會不匹配</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>總而言之，首先擴展 a 左側的通配符&nbsp;<code>%b</code>&nbsp;，然後&nbsp;<code>%b</code>&nbsp;通過從左側複製一個或多個字符來替換 the，然後檢查右側的通配符（如果有）。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="contracting-wildcards">承包通配符</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>收縮通配符不是在密碼猜測中添加新字符，而是刪除一個或多個字符。這是一個例子：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_15" class="wp-block-code"><code>Start%0,2-End
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>收縮&nbsp;<code>%0,2-</code>&nbsp;通配符將從任一側刪除 0 到 2 個相鄰字符，因此每個&nbsp;<code>StartEnd</code>&nbsp;（刪除 0），&nbsp;&nbsp;<code>StarEnd</code>&nbsp;（從左側刪除 1），&nbsp;&nbsp;<code>StaEnd</code>&nbsp;（從左側刪除 2），&nbsp;&nbsp;<code>Starnd</code>&nbsp;（從左側刪除 1，從右側刪除 1），&nbsp;&nbsp;<code>Startnd</code>&nbsp;（從右邊移除 1) 和&nbsp;<code>Startd</code>&nbsp;(從右邊移除 2) 將被嘗試。這在考慮複製粘貼錯誤時很有用，例如：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_16" class="wp-block-code"><code>%0,20-A/Long/Password/with/symbols/that/maybe/was/partially/copy/pasted%0,20-
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>將嘗試使用此密碼的不同版本從兩端刪除最多 20 個字符。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>以下是三種類型的合同通配符：</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>%0,5-</code>&nbsp;– 刪除從通配符兩側獲取的 0 到 5 個相鄰字符（總計）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%0,5&lt;</code>&nbsp;– 僅從通配符左側刪除 0 到 5 個相鄰字符</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%0,5&gt;</code>&nbsp;– 僅從通配符右側刪除 0 到 5 個相鄰字符</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>您可能需要注意，一個令牌中的收縮通配符可能會從其他令牌中刪除字符，但它永遠不會刪除或跨越另一個通配符。這是一個充分說明這一點的示例（如果您對這些具體細節不感興趣，請隨時跳到下一節）：</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>12</td><td><code>AAAA%0,10&gt;BBBB xxxx%dyyyy</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>這兩個標記各有八個普通字母。第一個標記有一個收縮通配符，它​​從右邊最多刪除 10 個字符，第二個標記有一個擴展通配符，它​​擴展到一個數字。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>從這些令牌生成的密碼之一是&nbsp;<code>AAAABBxxxx5yyyy</code>，它來自選擇第一個令牌和第二個令牌，然後應用通配符，收縮通配符刪除兩個字符。另一個&nbsp;<code>AAAAxx5yyyy</code>&nbsp;來自相同的令牌，但合同通配符現在正在刪除六個字符，其中兩個來自第二個令牌。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>數字和 the&nbsp;<code>yyyy</code>&nbsp;永遠不會被收縮通配符刪除，因為其他通配符永遠不會被刪除或交叉。即使合同通配符設置為刪除最多 10 個字符，&nbsp;<code>AAAAyyy</code>&nbsp;也永遠不會生成，因為它&nbsp;<code>%d</code>&nbsp;會阻止它。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="keyboard-walking-backreference-wildcards-revisited">鍵盤漫遊——反向引用通配符，再訪</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>此功能將反向引用通配符和拼寫錯誤映射的特徵組合到一個函數中。如果您還沒有閱讀下面的拼寫錯誤地圖（或上面的反向引用通配符），您可能應該暫時跳過本節，稍後再回來。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>考慮一個複雜的密碼模式，例如：&nbsp;&nbsp;<code>00test11</code>、&nbsp;<code>11test22</code>等，直到&nbsp;<code>88test99</code>。換句話說，模式是通過組合這 5 個字符串生成的：&nbsp;&nbsp;<code>#</code>&nbsp;<code>#</code>&nbsp;<code>test</code>&nbsp;<code>#+1</code>&nbsp;<code>#+1</code>。使用簡單的反向引用通配符，我們幾乎可以用這個標記生成這樣的模式：&nbsp;&nbsp;<code>%d%btest%d%b</code>。這產生了我們列表中的所有東西，但它也產生了更多我們不想要的東西，例如即使&nbsp;<code>33test55</code>&nbsp;它不匹配模式也會產生，因為 3+1 不是 5。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>相反，反向引用通配符需要一種方法來做更多的事情，而不是簡單地複制前一個字符，它必須能夠創建&nbsp;前一個字符的<em>修改副本</em>&nbsp;。它可以通過使用單獨的地圖文件來確定替換，以與拼寫錯誤地圖替換字符相同的方式來執行此操作。所以要繼續這個例子，需要一個新的地圖文件&nbsp;<code>nextdigit.txt</code>：</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9</td><td><code>0 1 1 2 2 3 3 4 4 5 5 6 6 7 7 8 8 9</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>最後，這是一個使用這個映射文件來生成我們正在尋找的模式的標記：&nbsp;&nbsp;<code>%d%btest%2;nextdigit.txt;6b</code>。這很複雜，所以讓我們分解一下：</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>%d</code>&nbsp;– 擴展到&nbsp;<code>0</code>&nbsp;通過&nbsp;<code>9</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%b</code>&nbsp;– 複製前一個字符，所以我們沒有&nbsp;<code>00</code>&nbsp;通過&nbsp;<code>99</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>test</code>&nbsp;– 現在我們已經&nbsp;<code>00test</code>&nbsp;通過了&nbsp;<code>99test</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%2;nextdigit.txt;6b</code>&nbsp;– 單個反向引用通配符，由以下部分組成：<ul><li><code>2</code>&nbsp;– 複製長度（擴展後結果的長度）</li><li><code>nextdigit.txt</code>&nbsp;– 使用的映射文件決定瞭如何修改字符</li><li><code>6</code>&nbsp;– 從通配符左邊多遠開始復制；從末尾向左數6個字符&nbsp;<code>00test</code>&nbsp;是第一個&nbsp;<code>0</code></li></ul>當令牌以 開頭時擴展此通配符的結果&nbsp;<code>00test</code>&nbsp;是&nbsp;<code>00test11</code>。它擴展為&nbsp;<em>兩個</em>&nbsp;<code>1</code>，因為複制長度為 2，它擴展為修改後的，&nbsp;<code>1</code>而不是僅僅複製，&nbsp;<code>0</code>因為文件將 a&nbsp;&nbsp;<code>0</code>&nbsp;（在其第一列中）映射到 a&nbsp;&nbsp;<code>1</code>&nbsp;（在第二列中）。同樣，a&nbsp;<code>77test</code>&nbsp;被展開為&nbsp;<code>77test88</code>。&nbsp;<code>99test</code>&nbsp;被擴展為&nbsp;<code>99test99</code>&nbsp;因為查找字符 a&nbsp;<code>9</code>不存在於映射文件（的第一列）中，因此它被原封不動地複制。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><code>;</code>請注意，當您在反向引用通配符內使用映射文件時，文件名的兩邊始終帶有分號 ( )。這些都是有效的反向引用通配符（但它們都是不同的，因為它們具有不同的副本長度和起始位置）&nbsp;&nbsp;<code>%;file.txt;b</code>：,&nbsp;&nbsp;<code>%2;file.txt;b</code>,&nbsp;&nbsp;<code>%;file.txt;6b</code>,&nbsp;&nbsp;<code>%2;file.txt;6b</code>.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>最後一個例子涉及到一種叫做鍵盤行走的東西。考慮一個密碼模式，其中打字員以任何字母開頭，然後通過使用特定模式移動手指來選擇下一個字符，例如始終向右上方傾斜或向右下方傾斜，然後重複直到結果是一定的長度。使用映射文件的單個反向引用通配符可以創建此模式。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>下面是此模式的映射文件的開頭，&nbsp;&nbsp;<code>pattern.txt</code>，看起來像：</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6</td><td><code>q 2a a wz z s 2 w w 3s ...</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>因此，如果最後一個字母是 a&nbsp;&nbsp;<code>q</code>，則模式中的下一個字母是 a&nbsp;<code>2</code>&nbsp;或 an&nbsp;&nbsp;<code>a</code>&nbsp;（用於右上角或右下角）。如果最後一個字母是&nbsp;<code>z</code>，下一個字母只有一個方向可用，從右上角到&nbsp;<code>s</code>。使用此映射文件和以下標記，將嘗試所有遵循此模式的 4 到 6 個字符長的組合：&nbsp;<code>%a%3,5;pattern.txt;b</code></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="delimiters-spaces-and-special-symbols-in-passwords">密碼中的分隔符、空格和特殊符號</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>默認情況下，&nbsp;&nbsp;<em>btcrecover</em>&nbsp;使用一個或多個空格來分隔 tokenlist 文件中的標記，並將要替換的字符與其在 typos-map 文件中的替換字符分隔開。它還會忽略這些文件中的任何額外空格。這使得很難測試包含空格和某些其他符號的密碼。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>一種僅適用於令牌列表文件的解決方法是使用&nbsp;<code>%s</code>&nbsp;將由單個空格替換的通配符。另一個對令牌列表文件和拼寫錯誤映射文件都有效的選項是使用&nbsp;<code>--delimiter</code>&nbsp;允許您更改此行為的選項。如果使用，則不再忽略空格，也不會刪除多餘的空格。<em>相反，必須完全按照指定的方式</em><code>--delimiter</code>&nbsp;使用&nbsp;新&nbsp;字符串&nbsp;來分隔標記或錯別字映射列。任何空格都會成為標記的一部分，因此您必須注意不要在這些文件中添加任何無意的空格。<em></em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>此外，&nbsp;&nbsp;<em>btcrecover</em>&nbsp;認為以下符號在 tokenlist 文件中的某些特定情況下是特殊的（對於符號&nbsp;<code>#</code>&nbsp;，也在 typos-map 文件中）。特殊符號是語法的一部分，而不是密碼的一部分。</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>%</code>&nbsp;– 總是被認為是特殊的（除非&nbsp;在 -style&nbsp;通配符&nbsp;<em>中</em><code>%[...]</code>，請參閱&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#expanding-wildcards">通配符</a>&nbsp;部分）；&nbsp;<code>%%</code>&nbsp;在令牌中將在&nbsp;<code>%</code>&nbsp;搜索期間被替換</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>^</code>&nbsp;– 僅當它是令牌的第一個字符時才是特殊的；&nbsp;&nbsp;在搜索期間<code>%^</code>&nbsp;將被替換&nbsp;<code>^</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>$</code>&nbsp;– 僅當它是令牌的最後一個字符時才是特殊的；&nbsp;<code>%S</code>&nbsp;（注意大寫&nbsp;）將&nbsp;在搜索期間<code>S</code>被替換&nbsp;<code>$</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>#</code>&nbsp;– 只有當它是&nbsp;&nbsp;一行中的&nbsp;<em>第一個字符時才特別，請</em><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#basics">在此處查看有關註釋的註釋</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>+</code>&nbsp;– 只有當它是一行中的第一個（不包括任何空格）字符，緊接著是一個空格（或定界符），然後是一些標記時才特殊（參見互斥部分）；如果您需要單個&nbsp;<code>+</code>&nbsp;字符作為標記，請確保它不是該行的第一個標記，或者它單獨在一行中</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>]</code><code>%[</code>&nbsp;– 僅當它跟在令牌中以標記 -style 通配符的結尾&nbsp;&nbsp;時才特殊&nbsp;<code>%[...]</code>。<em>如果它緊接在 之後</em>&nbsp;出現&nbsp;，&nbsp;<code>%[</code>則它是替換集的一部分，&nbsp;<em>下</em>&nbsp;<code>]</code>一個&nbsp;實際上結束通配符，例如通配符&nbsp;<code>%[]x]</code>&nbsp;包含兩個替換字符，&nbsp;<code>]</code>&nbsp;和&nbsp;<code>x</code>。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>這些都不適用於密碼列表文件，它們總是逐字處理空格和符號（回車符和換行符除外），將它們視為密碼的一部分。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>可以在此處找到具有 6 個已知位置字符和 6 個未知字符的文件示例：Sample TokenList</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>將使用此令牌列表的示例命令是：&nbsp;<code>python3 seedrecover.py --no-dupchecks --mnemonic-length 12 --language EN --dsw --wallet-type BIP39 --addr-limit 1 --addrs 17GR7xWtWrfYm6y3xoZy8cXioVqBbSYcpU --tokenlist ./btcrecover/test/test-listfiles/SeedTokenListTest.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>需要注意的是，使用該方法時需要指定助記詞長度和語言</strong>&nbsp;支持的語言可以在這裡找到</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>BTCRecover 還可以打印將通過命令測試的種子&nbsp;<code>--listpass</code>&nbsp;，這對於調試令牌列表很有用。有關令牌列表中種子列表的更多信息，請參見此處……（如果您將生成大量種子短語，這也很有用，儘管目前只是轉儲會變得非常大，非常快的文本文件......將來會對此進行一些優化）</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="the-passwordlist">密碼列表</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>如果您已經有了要測試的完整密碼的簡單列表，並且不需要上述任何功能，則可以使用命令行選項（而不是稍後在運行 btcrecover&nbsp;<code>--passwordlist</code>&nbsp;中&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/passwordlist_file/#running-btcrecover">描述&nbsp;</a><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/passwordlist_file/#running-btcrecover"><em>的</em></a><code>--tokenlist</code>&nbsp;選項&nbsp;&nbsp;部分）。如果您的密碼包含任何非<a href="https://en.wikipedia.org/wiki/ASCII">ASCII</a>&nbsp;（非英語）字符，您應該&nbsp;在繼續之前閱讀有關<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/passwordlist_file/#unicode-support">Unicode 支持</a>&nbsp;的部分&nbsp;。<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/passwordlist_file/#running-btcrecover"><em></em></a><a href="https://en.wikipedia.org/wiki/ASCII"></a><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/passwordlist_file/#unicode-support"></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果您指定&nbsp;<code>--passwordlist</code>&nbsp;沒有文件，&nbsp;&nbsp;<em>btcrecover</em>&nbsp;將提示您在命令提示符窗口中輸入密碼列表，每行一個。如果您已經有一個包含密碼的文本文件，則可以改用&nbsp;<code>--passwordlist FILE</code>&nbsp;（替換&nbsp;<code>FILE</code>&nbsp;為文件名）。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>確保不要添加任何額外的空格，除非這些空格實際上是密碼的一部分。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>使用該&nbsp;<code>--passwordlist</code>&nbsp;選項時，每一行都被逐字用作單個密碼（並且沒有應用上面的任何功能）。但是，您可以使用下面描述的任何拼寫錯誤功能來嘗試密碼列表中密碼的不同變體。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="seedlists">種子列表</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>“密碼列表”（參見&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/passwordlist_file/">此處</a>）功能也可以通過參數與種子短語一起使用&nbsp;<code>--seedlist</code>&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>與密碼列表的主要區別在於，雖然您仍然只是每行列出一個助記詞，但您還需要將它們格式化為通過命令導出的相同樣式&nbsp;<code>--listpass</code>&nbsp;。這是為了讓這個工具的 tokenlst 步驟的輸出可以直接被 passwordlist 步驟使用。查看&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/btcrecover/test/test-listfiles/SeedListTest.txt">示例種子列表</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>SeedList 的示例用法（使用 listseeds 創建的 Seedlist 作為上面令牌列表命令的輸出）：&nbsp;<code>python3 seedrecover.py --no-dupchecks --mnemonic-length 12 --language EN --dsw --wallet-type BIP39 --addr-limit 1 --addrs 17GR7xWtWrfYm6y3xoZy8cXioVqBbSYcpU --seedlist ./btcrecover/test/test-listfiles/SeedListTest.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>一系列錢包的錢包文件密碼恢復</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>以下錢包的助記詞恢復<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://electrum.org/">Electrum</a>&nbsp;&nbsp;(1.x, 2.x, 3.x and 4.x) (For Legacy and Segwit Wallets. Set –bip32-path “m/0'/0” for a Segwit wallet, leave bip32-path blank for Legacy ……不支持 2fa 錢包……）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.electroncash.org/">電子現金</a>&nbsp;（2.x、3.x 和 4.x）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>BIP-32/39 兼容錢包 ( <a href="https://bitcoinj.github.io/">bitcoinj</a> )，包括：<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://multibit.org/">多位高清</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://play.google.com/store/apps/details?id=de.schildbach.wallet">適用於 Android/BlackBerry 的比特幣錢包（帶有先前由</a><a href="https://github.com/gurnec/decrypt_bitcoinj_seed">decrypt_bitcoinj_seeds</a>&nbsp;提取的種子&nbsp;）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://play.google.com/store/apps/details?id=com.hivewallet.hive.cordova">Hive for Android</a>&nbsp;,&nbsp;&nbsp;<a href="https://github.com/hivewallet/hive-ios">for iOS</a>&nbsp;, and&nbsp;&nbsp;<a href="https://hivewallet.com/">Hive Web</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://brd.com/">麵包錢包</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>BIP-32/39/44 比特幣和以太坊兼容錢包，包括：<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://wallet.mycelium.com/">Android版菌絲體</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.bitcointrezor.com/">安全的</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.ledgerwallet.com/">賬本</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://shapeshift.io/keepkey/">保管鑰匙</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://jaxx.io/">賈克斯</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.coinomi.com/">科諾米</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.exodus.io/">出埃及記</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.myetherwallet.com/">我的以太錢包</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://bither.net/">比瑟</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://blockchain.com/wallet">區塊鍊網</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://bitaddress.org/">加密 (BIP-38) 紙錢包支持（例如：來自 Bitaddress.org）</a>&nbsp;也適用於 altcoin 分叉，如 liteaddress.org、paper.dash.org 等……</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>腦錢包<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Sha256（密碼）腦錢包（例如：Bitaddress.org、liteaddress.org、paper.dash.org）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>sCrypt 安全腦錢包（例如：Warpwallet、Memwallet）</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>比特幣錢包密碼恢復支持：<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://bitcoincore.org/">比特幣核心</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://multibit.org/">多比特高清</a>&nbsp;和&nbsp;<a href="https://multibit.org/help/v0.5/help_contents.html">多比特經典</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://electrum.org/">Electrum</a>&nbsp;&nbsp;(1.x, 2.x, 3.x and 4.x) (For Legacy and Segwit Wallets. Set –bip32-path “m/0'/0” for a Segwit wallet, leave bip32-path blank for Legacy ……不支持 2fa 錢包……）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>大多數基於&nbsp;<a href="https://bitcoinj.github.io/">bitcoinj</a>的錢包，包括&nbsp;<a href="https://github.com/hivewallet/hive-mac/wiki/FAQ">Hive for OS X</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>BIP-39 密碼（還支持所有支持種子恢復的密碼，以及恢復 Electrum 種子的“額外單詞”）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://ciphrex.com/products/">mSIGNA（CoinVault）</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://blockchain.com/wallet">區塊鍊網</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://block.io/">block.io</a>&nbsp;&nbsp;（恢復錢包“Secret PIN”）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://github.com/jackjack-jj/pywallet">pywallet –</a>&nbsp;&nbsp;Bitcoin Unlimited/Classic/XT/Core 錢包的轉儲錢包</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://play.google.com/store/apps/details?id=de.schildbach.wallet">用於 Android/BlackBerry</a>&nbsp;消費 PIN 和加密備份的比特幣錢包</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://github.com/kncgroup/bitcoin-wallet">KnC Wallet for Android</a>&nbsp;加密備份</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://bither.net/">比瑟</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>山寨幣密碼恢復支持來自上述其中一個的大多數錢包，包括：<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://www.coinomi.com/en/">Coinomi</a>&nbsp;&nbsp;（僅支持受密碼保護的錢包）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://metamask.io/">Metamask</a>&nbsp;&nbsp;（以及 Metamask 的克隆版，如 Binance Chain Wallet、Ronin Wallet 等）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://litecoin.org/">萊特幣核心</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://electrum-ltc.org/">Electrum-LTC</a>&nbsp;&nbsp;（對於舊版和 Segwit 錢包。設置 –bip32-path “m/0'/0” 用於 Segwit 錢包，將 bip32-path 留空用於舊版……不支持 2fa 錢包……）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.electroncash.org/">電子現金</a>&nbsp;（2.x、3.x 和 4.x）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://litecoin.org/">用於 Android</a>&nbsp;加密備份的萊特幣錢包</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="http://dogecoin.com/">狗狗幣核心</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="http://multidoge.org/">多狗</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://dogechain.info/">狗狗鏈.info</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="http://dogecoin.com/">用於 Android</a>&nbsp;加密備份的狗狗幣錢包</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://yoroi-wallet.com/#/">Yoroi Wallet for Cardano</a>&nbsp;&nbsp;Master_從錢包數據中提取的密碼（在瀏覽器中或在 root/越獄手機上）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/">Damaged Raw Eth Private Keys</a>&nbsp;缺少字符的個人私鑰。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://myetherwallet.com/">Ethereum UTC Keystore Files</a>&nbsp;&nbsp;Ethereum Keystore 文件，通常由 MyEtherWallet、MyCrypto 等錢包使用（也經常被 Theta 等 Eth 克隆使用）</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="http://en.wikipedia.org/wiki/Free_and_open-source_software">免費和開源</a>&nbsp;——任何人都可以下載、檢查、使用和重新分發該軟件</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>在 Windows、Linux 和 OS X 上受支持</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>支持 Unicode 密碼和種子</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>多線程搜索，用戶可選擇線程數</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>能夠將搜索工作負載分散到多個設備上</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/GPU_Acceleration/"></a>&nbsp;比特幣核心密碼、Blockchain.com（主密碼和第二密碼）、Electrum 密碼 + BIP39 和 Electrum 種子的<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/GPU_Acceleration/">GPU 加速</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>密碼的通配符擴展</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>密碼和種子的錯字模擬</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>進度條和 ETA 顯示（在命令行）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>可選的自動保存 - 中斷並繼續密碼恢復而不會丟失進度</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>使用簡單的圖形用戶界面自動恢復種子</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>能夠通過 –pathlist 命令同時搜索給定種子的多個派生路徑（示例路徑列表文件在 ）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>幾乎所有受支持錢包的“離線”模式——使用其中一個&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Extract_Scripts/">提取腳本（單擊以獲取更多信息）</a>&nbsp;來提取足夠的信息來嘗試恢復密碼，而不給&nbsp;<em>btcrecover</em>&nbsp;或任何運行它的人訪問&nbsp;你的<em>任何</em>&nbsp;地址或私鑰的權限比特幣錢包。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>如果您希望該工具支持上面未列出的加密貨幣/錢包，請測試它是否有效並提交 PR，其中包括對該硬幣的單元測試以及接受地址格式所需的任何代碼。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":1} -->
<h1 id="btcrecover-extract-scripts"><em>btcrecover</em>&nbsp;提取腳本</h1>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>有時，不希望&nbsp;&nbsp;直接在存儲目標錢包文件的計算機上運行<em>btcrecover 。</em>例如：</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><em>具有更快 CPU 或 GPU 的計算機或基於雲的虛擬機可能是運行btcrecover 的</em>更好位置&nbsp;。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>配置&nbsp;<em>btcrecover</em>&nbsp;以正確搜索您的密碼可能很棘手；您可能有興趣找到可以在他們的計算機上為您配置和運行&nbsp;<em>btcrecover</em>的人&nbsp;。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>您可能不相信&nbsp;<em>btcrecover</em>&nbsp;沒有有害錯誤或其他惡意行為。&nbsp;<em>btcrecover</em>&nbsp;是開源的，不需要安裝不可靠的二進製文件。然而，它也是一個相當長且複雜的 Python 腳本，這使得即使是其他 Python 程序員也很難確定它不包含任何有害代碼（無論是故意惡意的還是偶然的）。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>此目錄中的提取腳本是相對較短且簡單的腳本，它們從錢包文件中提取足夠的信息以允許&nbsp;<em>btcrecover</em>&nbsp;執行密碼搜索。這些腳本永遠不會提取足夠的信息來使你的任何比特幣資金面臨風險，即使在找到密碼之後也是如此。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>有關&nbsp;<em>btcrecover的更多信息</em></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/CREDITS/">學分</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/licence/">執照</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":1} -->
<h1 id="btcrecoverpy-tutorial">btcrecover.py 教程</h1>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>btcrecover.py</em>&nbsp;是一款免費開源的多線程錢包密碼恢復工具，支持 Bitcoin Core、MultiBit（Classic 和 HD）、Electrum（1.x 和 2.x）、mSIGNA (CoinVault)、Hive for OS X、Blockchain。 com（v1-v3 錢包格式，主密碼和第二密碼）、Bither 以及適用於 Android 的比特幣和 KNC 錢包。它專為您已經知道大部分密碼但在嘗試不同的可能組合時需要幫助的情況而設計。本教程將指導您完成它所提供的功能。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="installation">安裝 BTCRecover</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>安裝 BTCRecover 有幾個基本步驟。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>1) 下載並解壓BTCRecover腳本</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>2）下載並安裝Python3</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>3）通過Python PIP安裝所需的包</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>4）（可選）安裝用於GPU加速的PyOpenCL模塊</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>5) 測試你的安裝（可選，但一個好主意）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>這些步驟也包含在下面針對每個支持的操作系統的視頻中。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>注意：根據您的操作系統和 python 環境，您可能需要將&nbsp;<code>python</code>&nbsp;命令替換為&nbsp;<code>python3</code>.&nbsp;（默認情況下，要使用的命令將&nbsp;<code>python</code>&nbsp;在 Windows 和&nbsp;<code>python3</code>&nbsp;Linux 中使用）大多數非技術用戶使用 Windows，因此所有示例命令都將用於&nbsp;<code>python</code>&nbsp;匹配該平台的默認值</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>視頻教程</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>視窗：&nbsp;</strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/8q65eqpf4gE","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/8q65eqpf4gE
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong>Ubuntu 操作系統：</strong>&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/Met3NbxcZTU","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/Met3NbxcZTU
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong>蘋果系統：&nbsp;</strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/Qzc3oHzbcAo","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/Qzc3oHzbcAo
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 id="1-downloading-btcrecover">1) 下載&nbsp;<em>btcrecover</em></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/archive/master.zip">只需從https://github.com/demining/CryptoDeepTools/archive/master.zip</a>下載最新版本&nbsp;&nbsp;並將其解壓縮到您選擇的位置。<em>btcrecover</em>本身沒有安裝程序&nbsp;&nbsp;，但根據您的操作系統和您嘗試恢復的錢包類型，還有以下額外要求。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="2-install-python">2）安裝Python</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>注意：</strong>&nbsp;官方僅支持 Python 3.7 及更高版本……BTCRecover 在所有受支持的環境（Windows、Linux、Mac）上自動測試了所有受支持的 Python 版本（3.7、3.8、3.9、3.10），因此您可以確定 BTCRecover 和所有必需的包都將正常工作。BTCRecover 的某些功能可能適用於早期版本的 Python，最好的辦法是使用 run-all-tests.py 來查看哪些有效，哪些無效……</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="windows">視窗</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>在 Windows 中安裝 BTCRecover 的視頻演示：&nbsp;&nbsp;<a href="https://youtu.be/8q65eqpf4gE">https://youtu.be/8q65eqpf4gE</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>在此處訪問 Python 下載頁面：&nbsp; https:&nbsp;<a href="https://www.python.org/downloads/windows/">//www.python.org/downloads/windows/ ，然後單擊最新</a><strong>Python 3.9</strong>版本的鏈接&nbsp;&nbsp;（Python 3.10 等可以使用，但 Python 3.9 所需模塊的安裝更簡單) 在<em>Python Releases for Windows</em>標題下的頁面頂部附近發布&nbsp;。下載並運行適用&nbsp;<code>Windows x86 MSI installer</code>&nbsp;於 32 位版本的 Python 或&nbsp;<code>Windows x86-64 MSI installer</code>&nbsp;適用於 64 位版本的 Python。現代 PC 應該使用 64 位版本，但是如果您不確定哪個版本與您的 PC 兼容，請選擇 32 位版本。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em><strong>在 Windows 中安裝 Python 時，請確保在安裝程序的第一個屏幕上選擇“將 Python 3.9 添加到 PATH”……</strong></em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>大型多 CPU 系統注意事項：</strong>&nbsp;&nbsp;Windows 將可能的線程數限制為 64。如果您的系統具有比這更多的邏輯/物理內核，最好的辦法是在 Linux 中運行該工具。（Ubuntu 是一個簡單的起點）</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="linux">Linux</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>在 Ubuntu Live USB 中安裝 BTCRecover 的視頻演示：&nbsp;&nbsp;<a href="https://youtu.be/Met3NbxcZTU">https://youtu.be/Met3NbxcZTU</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>大多數現代發行版都預裝了 Python 3。較舊的 Linux 發行版將包含 Python2，因此您需要安裝 python3。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果您正在使用 SeedRecover，如果您想使用默認的 GUI 彈出窗口進行 seedrecover，您還需要安裝 tkinter (python3-tk)。（命令行使用可以在沒有這個包的情況下找到）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>某些 Linux 發行版會將其與 Python3 捆綁在一起，但對於其他發行版（如 Ubuntu），您將需要手動安裝 tkinter 模塊。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>您可以使用以下命令安裝它：&nbsp;<code>sudo apt install python3-tk</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果下面的任何“pip3”命令失敗，您可能還需要通過以下命令安裝 PIP：&nbsp;<code>sudo apt install python3-pip</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果您收到一條消息，指出沒有 Python3-pip 的安裝候選者，您將需要使用以下命令啟用“universe”存儲庫：&nbsp;<code>sudo add-apt-repository universe</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>然後您可以重新運行命令以從上面安裝 python3-pip。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4 id="enabling-native-ripemd160-support">啟用本機 RIPEMD160 支持</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>從 OpenSSL v3（2021 年末）開始，ripemd160 不再默認啟用，現在是“舊版”哈希函數集的一部分。在 Linux/MacOS 環境中，Python 中的 hashlib 模塊依賴於用於 ripemd160 的 OpenSSL，因此如果您希望在這些環境中發揮全部性能，您可能需要修改 OpenSSL 設置以啟用舊版提供程序。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>截至 2022 年 7 月，BTCRecover 確實包含了 RIPEMD160 的“純 Python”實現，但與通過 hashlib 的本機實現相比，它只提供了大約 1/3 的性能。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>可以在此處找到此應用修復程序的視頻演示：&nbsp;&nbsp;<a href="https://youtu.be/S3DWKp0i4i0">https://youtu.be/S3DWKp0i4i0</a></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/S3DWKp0i4i0","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/S3DWKp0i4i0
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>可以在此處找到修改後的配置文件的示例：&nbsp; https:&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/master/docs/example_openssl.cnf">//github.com/demining/CryptoDeepTools/blob/master/docs/example_openssl.cnf</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>有關詳細信息，請參閱 OpenSSL Github 存儲庫上的相關問題：&nbsp; https:&nbsp;<a href="https://github.com/openssl/openssl/issues/16994">//github.com/openssl/openssl/issues/16994</a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1265} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/11/image-191.png" alt="BTC 恢復加密指南" class="wp-image-1265"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3 id="macos">蘋果系統</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>在 MacOS 中安裝 BTCRecover 的視頻演示：&nbsp;&nbsp;<a href="https://youtu.be/Qzc3oHzbcAo">https://youtu.be/Qzc3oHzbcAo</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>1)&nbsp;<a href="https://brew.sh/">按照 brew.sh 上的說明安裝 brew</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>安裝命令是：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_1" class="wp-block-code"><code>/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>請務必按照說明將 brew 添加到您的路徑中……</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>2）&nbsp;<a href="https://ofek.dev/coincurve/install/">安裝coincurve構建要求</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>安裝命令是：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>brew install autoconf automake libffi libtool pkg-config python
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>如果你想使用圖形界面，一定要按照說明安裝 tkinter。</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>通過 Brew 安裝 Python 後，您將需要使用包含完整版本號的命令來運行 Python 和 PIP。（例如：python3.9 和 pip3.9）</strong></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="3-install-requirements-via-python-pip">3）通過Python Pip安裝需求</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>安裝 Python3 和 PIP 後，您可以使用以下命令自動安裝 BTCRecover 所有功能的所有要求：</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>pip3 install -r requirements.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>如果您是高級用戶，您可以選擇僅安裝您正在嘗試的特定恢復所需的那些附加包。有關哪些錢包需要哪些軟件包的更多信息，請參閱本指南的底部。</em></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="4-install-pyopencl-for-gpu-acceleration">4) 安裝用於GPU加速的PyOpenCL</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>GPU 支持將需要安裝上述命令未涵蓋的其他 OpenCL 庫……</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>有關更多信息和說明，請參閱此處的 GPU 加速頁面</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1>顯卡加速</h1>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2 id="btcrecover-gpu-acceleration-guide">BTCRecover GPU 加速指南</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="performance-notes">性能說明</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>BTCRecover 支持使用一個或多個圖形卡或專用加速卡來提高搜索性能。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>這提供的性能提升取決於您嘗試恢復的錢包類型、您的 CPU 和 GPU。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>為了進行比較，對於各種錢包，i7-8750 與 NVidia 1660ti 的 CPU 與 GPU 性能通常為：</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><thead><tr><th>恢復類型</th><th>CPU 性能 (kp/s)</th><th>GPU 性能 (kp/s)</th><th>GPU 速度提升與 CPU</th></tr></thead><tbody><tr><td>比特幣核心（JTR 內核）</td><td>0.07</td><td>6.75</td><td>96x</td></tr><tr><td>比特幣核心 (OpenCL_Brute)</td><td>0.07</td><td>0.95</td><td>14倍</td></tr><tr><td>Blockchain.com主密碼</td><td>1個</td><td>10</td><td>10倍</td></tr><tr><td>Blockchain.com 二級密碼</td><td>0.39</td><td>15.5</td><td>40倍</td></tr><tr><td>狗狗鏈.info</td><td>1.3</td><td>11.3</td><td>10倍</td></tr><tr><td>Electrum 2 錢包密碼</td><td>4.5</td><td>21</td><td>4.5倍</td></tr><tr><td>BIP39 密碼（或 Electrum 'Extra Words'</td><td>2.3</td><td>10.4</td><td>4.5</td></tr><tr><td>BIP39 12 字種子</td><td>33</td><td>134</td><td>4.3倍</td></tr><tr><td>BIP39 12 字種子（令牌列表）</td><td>33</td><td>130</td><td>4倍</td></tr><tr><td>BIP39 24 字種子</td><td>160</td><td>180</td><td>1.15倍</td></tr><tr><td>BIP39 24 字種子（令牌列表）</td><td>140</td><td>160</td><td>1.15倍</td></tr><tr><td>金銀花種子</td><td>200</td><td>366</td><td>1.8倍</td></tr><tr><td>BIP38加密密鑰</td><td>0.02</td><td>0.02</td><td>1x（但可以很好地擴展到多個 GPU）</td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p><strong>不要簡單地假設此時啟用 GPU/OpenCL 會提高速度，特別是如果您有非常高端的 CPU 和低端 GPU……使用和不使用 OpenCL/GPU 測試您的命令並使用 –no-eta和 – 用於評估性能的性能參數</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>這種巨大的性能差異主要是由於進程的不同部分受到不同程度的 CPU 限制，特別是對於 BIP39 和 Electrum 種子恢復。因此，將更多處理轉移到 OpenCL 並創建更高效的種子生成器將是未來的工作領域。</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Usage_Examples/2020-10-06_Multi-GPU_with_vastai/Example_Multi-GPU_with_vastai/">您還可以在此處的本文中找到各種 GPU 的性能信息，尤其是多 GPU 情況</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="pyopencl-installation">PyOpenCL 安裝</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>GPU/OpenCL 加速取決於您是否安裝了適用於 OpenCL 1.2 的 PyOpenCL。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>為了使用此功能，您必須擁有支持 OpenCL 的卡和驅動程序（大多數 AMD 和 NVIDIA 卡和驅動程序已經在 Windows 上支持 OpenCL），並且您必須安裝所需的 Python 庫，如下所述。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>GPU 加速也應該適用於 MacOS，但是本教程目前不包含安裝所需 Python 庫的說明。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="pyopencl-installation-for-windows">適用於 Windows 的 PyOpenCL 安裝</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>這將在安裝 OpenCL 之前手動安裝預編譯的 numpy 工作版本。</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>為您的 GPU 安裝驅動程序包……如果沒有這個，其他任何東西都無法工作……</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>從這裡下載適用於 OpenCL 1.2 和 Python 3 的最新版本的 PyOpenCL，32 位版本或 64 位版本以匹配您安裝的 Python 版本：http:&nbsp;&nbsp;<a href="http://www.lfd.uci.edu/~gohlke/pythonlibs/#pyopencl">//www.lfd.uci.edu/~ gohlke/pythonlibs/#pyopencl</a>。為獲得最佳兼容性，請務必選擇 OpenCL 1.2 版本，&nbsp;<em>不要更高</em>&nbsp;（在文件名中查找“cl12”，並查找數字以匹配您的 python 版本（例如：“38”以匹配 Python 3.8）。 （OpenCL 2.0 版本可能適用於您的系統，因此如果 OpenCL 1.2 的 PyOpenCL 不可用，請嘗試一下）在撰寫本文時，用於 OpenCL 1.2 和 Python 3.9 的 32 位和 64 位版本被命名為分別：<code>pyopencl‑2021.1.4+cl12‑cp39‑cp39‑win_amd64.whl pyopencl‑2021.1.4+cl12‑cp39‑cp39‑win32.whl</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>打開命令提示符窗口，導航到您下載步驟 1 中下載的文件的位置，然後鍵入以下內容以安裝 PyOpenCL 及其依賴項：（假設 Python3.8 在 64 位環境中）<code>pip3 install "pyopencl-2021.1.4+cl12-cp39-cp39-win_amd64.whl</code></li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 id="pyopencl-installation-for-linux">Linux 的 PyOpenCL 安裝</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>與 Ubuntu 20.04 一起使用</strong>&nbsp;1. 對於 NVidia GPU，為您的系統安裝 Nvidia 二進制驅動程序。（在 Ubuntu 中，這是直截了當的，並在此處進行了解釋：https://help.ubuntu.com/community/BinaryDriverHowto/Nvidia#NVIDIA_driver_from_the_Ubuntu_repositories 440 版本的驅動程序元數據包已經過測試並且工作正常）——我沒有當前的 AMD要測試的系統，但只要您安裝了 AMD 驅動程序，這應該可以正常工作…… 2. 為您的系統安裝 pyOpenCL 庫。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>    sudo apt install python3-pyopencl
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>根據您的 Linux 環境，通過 APT 可用的 Python 庫可能已經過時並且可能無法正常工作。在這種情況下，您可能需要通過 Pip 安裝和構建 PyOpenCL。（並且特定版本的 PyOpenCL 是否會在您的系統上構建可能會有所不同，因此嘗試使用較舊的 PyOpenCL 包版本可能會有所幫助，例如：pyopencl==2019.1.1）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>除此之外，除了最新的 Ubuntu LTS 版本之外，不會為任何發行版提供額外的支持。</strong>&nbsp;一般來說，安裝和配置 Hashcat 環境的說明將涵蓋設置和運行環境所需的內容……</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="testing-your-system">測試您的系統</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>要檢查您的 PyOpenCL 安裝是否正常工作，您可以運行與您要運行的 GPU 加速恢復類型相關的單元測試：</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>比特幣核心約翰開膛手內核 (JTR)</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_4" class="wp-block-code"><code>python3 -m btcrecover.test.test_passwords -v GPUTests
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>假設測試沒有失敗，可以通過將選項添加&nbsp;<code>--enable-gpu</code>&nbsp;到命令行來啟用 GPU 支持。還有其他附加選項，特別是&nbsp;<code>--global-ws</code>&nbsp;和&nbsp;<code>--local-ws</code>，它們也應與特定值一起提供以提高搜索性能。不幸的是，這些選項的確切值只能通過反複試驗來確定，如下所述。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>Blockchain.com、Electrum 錢包和 BIP39 密碼（或 Electrum“額外詞”）通過 OpenCL_Brute 內核（也支持比特幣核心，但比 JTR 慢）</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_5" class="wp-block-code"><code>python3 -m btcrecover.test.test_passwords -v OpenCL_Tests
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>如果所有測試都通過，那麼您只需將 –enable-opencl 添加到命令行參數即可。OpenCL 平台選擇和工作組大小的默認值應該會產生良好的結果。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>BIP39 或 Electrum 種子恢復</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_6" class="wp-block-code"><code>python3 -m btcrecover.test.test_seeds -v OpenCL_Tests
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>如果所有測試都通過，那麼您只需將 –enable-opencl 添加到命令行參數即可。OpenCL 平台選擇和工作組大小的默認值應該會產生良好的結果。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="performance-tuning-background">性能調整：背景</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>談到 OpenCL 性能調整時，需要了解的關鍵是 CPU 處理指令的方式與 GPU 之間存在根本區別。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>CPU 可以非常快速地處理命令，但基本上每個 CPU 內核一次只能執行一次任務。另一方面，GPU 在執行相同任務時實際上可能會更慢，但不同之處在於它們可能能夠同時並行執行一批 1000 個任務，而不是像 CPU 那樣一個接一個地執行。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>這意味著 GPU 處理可能存在顯著的性能差異，具體取決於您加載到 GPU 的工作批次的大小。（並且做一些事情，比如只填充潛在批量大小的一半會讓你的性能減半）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>因此，設置全局和本地工作大小參數可以對 JTR 內核產生巨大的影響，而使用 workgroup-size 命令可以在使用 OpenCL_Brute 內核時產生很大的不同（儘管 OpenCL_Brute 內核的默認值應該自動工作為您的系統找出接近最佳的東西）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>這也意味著在 CPU 處理中不是問題的性能瓶頸在使用 GPU 處理時會成為問題。（這正是為什麼 24 字種子的令牌列表無法像使用 BIP39 12 字種子的標準恢復那樣獲得幾乎一樣多的性能提升）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>這也是為什麼您可能會發現在一台 PC 上創建校驗和種子列表並使用 –savevalidseeds、–savevalidseeds-filesize、–multi-file-seedlist 和 –skip-worker-checksum 參數將其加載到另一台電腦上有一些好處.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="multi-gpu-systems">多 GPU 系統</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>默認情況下，兩個 OpenCL 內核都將使用系統中可用的所有 GPU，但它們的使用方式會有所不同。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>JohnTheRipper 內核（當使用 –enable-gpu 參數時由比特幣核心使用）</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>將只使用一個 CPU 線程並使用所有 GPU，儘管它確實需要 GPU 在性能方面相同。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>OpenCL_Brute 內核（通過 –enable-opencl 參數啟用）</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>將以循環方式將 GPU 分配給線程。（例如，如果你有 3 個 GPU 和 3 個 CPU 核心，它會分配一個 GPU1-&gt;CPU1、GPU2-&gt;CPU2、GPU3-&gt;CPU3，等等）鑑於此，你通常希望至少擁有與你一樣多的線程有GPU。（雖然我還沒有看到除了前加密採礦設備以外的任何系統，其中你的 GPU 比 CPU 多）BTCRecover 將默認使用與邏輯 CPU 內核一樣多的線程，但如果你的系統的內核少於 GPU，你始終可以使用 –threads 參數手動指定線程數。&nbsp;<strong><em>一般來說，我建議每個 GPU 2 個線程可能是你最好的性能起點......</em></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>您還可以通過 –opencl-devices 參數手動指定要使用的 OpenCL 設備。您還可以在此處列出兩次 GPU，如果一個 GPU 的性能是其他 GPU 的兩倍，這可能會有用，因此您希望它分配更大的份額。（例如：指定 GPU 0 0 1 會將 GPU0 分配給兩倍於 GPU1 的線程）如上所述，這些 GPU 以循環方式分配，因此您基本上可以指定與線程一樣多的設備。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="gpu-performance-tuning-for-bitcoin-core-and-derived-altcoin-wallets-with-the-jtr-kernel">使用 JTR 內核對比特幣核心和衍生山寨幣錢包進行 GPU 性能調優</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>這些錢包的一個很好的起點是：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_7" class="wp-block-code"><code>python3 btcrecover.py --wallet ./btcrecover/test/test-wallets/bitcoincore-wallet.dat --performance --enable-gpu --global-ws 4096 --local-ws 256
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>該&nbsp;<code>--performance</code>&nbsp;選項告訴&nbsp;<em>btcrecover</em>&nbsp;在按下 Ctrl-C 之前簡單地測量性能，而不是嘗試測試任何特定的密碼。您仍然需要一個錢包文件（或一個&nbsp;<code>--extract-data</code>&nbsp;選項）來進行性能測試。從這個初始測試中獲得基線後，您可以嘗試不同的值，&nbsp;<code>--global-ws</code>&nbsp;看看&nbsp;<code>--local-ws</code>&nbsp;它們是提高還是降低了性能。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>--global-ws</code>&nbsp;為和&nbsp;找到正確的值&nbsp;<code>--local-ws</code>&nbsp;可以實現 10 倍的改進，因此通常值得付出努力。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>一般在測試的時候，應該將這兩個值按2的次方增減，比如一次增減128或256。重要的是要注意&nbsp;<code>--global-ws</code>&nbsp;必須始終被 整除&nbsp;<code>--local-ws</code>，否則&nbsp;<em>btcrecover</em>&nbsp;將退出並顯示錯誤消息。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>儘管此過程可能很乏味，但對於較大的令牌列表或密碼列表，它可能會產生重大影響。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="opencl-performance-tuning-for-other-wallets">其他錢包的 OpenCL 性能調整</h3>
<!-- /wp:heading -->

<!-- wp:heading {"level":4} -->
<h4 id="limiting-derivation-paths-searched-for-seed-based-wallets">限制搜索基於種子的錢包的派生路徑</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>默認情況下，BTCRecover 現在將自動搜索給定加密貨幣的所有常見派生路徑。（例如：比特幣 BIP44、49 和 84）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>對於基於 CPU 的恢復，這不會顯著降低性能，但根據您的 CPU，這可能會使&nbsp;&nbsp;您的 OpenCL 性能<strong>減半。</strong>因此，如果您知道要搜索的派生路徑，則應通過 –bip32-path 命令手動指定它。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4 id="address-generation-limit-for-seed-based-wallets">基於種子的錢包的地址生成限制</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>每次您選擇“接收”時，比特幣等加密貨幣通常會生成一個新地址。地址生成限制（–addr-limit 參數）告訴 BTCRecover 它應該為每個種子生成和搜索多少個地址。（這就是為什麼您想使用錢包中最早的地址）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>對於基於 CPU 的恢復，將地址生成限制設置為 10 之類的值不會對性能產生巨大影響，而對於基於 OpenCL 的恢復，地址生成限制只要 10 就會使搜索性能&nbsp;&nbsp;減半<strong>。</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>也就是說，如果您正在對以太坊或 Ripple 錢包之類的東西進行恢復，您通常可以將地址生成限制保留為 1，因為這些基於帳戶的加密貨幣傾向於使用固定的接收地址。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>還應該注意的是，如果您使用的是地址數據庫，通常可以將地址生成限制保留為 1 ...</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4 id="work-group-size">工作組規模</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>如果您使用 –opencl-info 命令，您將看到一個 OpenCL 設備列表及其相應的最大工作組大小。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>然後您可以使用 –opencl-workgroup-size 命令嘗試手動設置工作組大小。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>對於密碼恢復：</strong>&nbsp;您應該嘗試將工作組命令設置為最大工作組大小的精確倍數。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>對於種子恢復</strong>&nbsp;您會注意到種子恢復會自動將工作組大小設置為更大的值。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>這是因為生成的大多數種子只是校驗和，從未完全散列。生成的種子的比率：散列因不同的錢包類型和種子長度而異。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>一般來說是： * BIP39 12 Word: 16:1 * BIP39 18 Word: 64:1 * BIP39 24 Word: 256:1 * Electrum : 125:1</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>這意味著為了填充 GPU 的最大工作組大小，seedgenerator 需要將比最大工作組大小大很多倍的可能種子塊傳遞給它。（例如：對於 1024 的工作組大小，BIP39 24 字種子將需要 262,144 個潛在種子）</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 id="5-testing-your-installation">5) 測試你的安裝</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>下載並解壓縮 BTCRecover、安裝 Python 和所有必需的庫後，您可以使用以下命令測試程序：</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>python3 run-all-tests.py -vv</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>此命令將需要幾分鐘的時間來運行並且應該沒有錯誤地完成，表明您的系統已準備好使用 BTCRecover 的所有功能。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="wallet-python-package-requirements">錢包 Python 包要求</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>如果你想安裝所有錢包類型的所有要求，你可以簡單地使用命令&nbsp;<code>pip3 install -r requirements-full.txt</code></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>在下面的列表中找到您的錢包類型，然後僅按照錢包旁邊列出的部分的說明進行操作。</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>比特幣核心——可選：&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>MultiBit Classic——推薦：&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>MultiBit HD – 可選：&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Electrum（1.x 或 2.x）——推薦：&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Electrum 2.8+ 完全加密錢包 –&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Seedrecover_Quick_Start_Guide/#installation">coincurve</a>，可選：&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>BIP-39 比特幣密碼（例如 TREZOR）——&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Seedrecover_Quick_Start_Guide/#installation">coincurve</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>BIP-39 以太坊密碼（例如 TREZOR）——&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome&nbsp;</a>&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Seedrecover_Quick_Start_Guide/#installation">coincurve</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Hive for OS X –&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#google-protocol-buffers">Google protobuf</a>，可選：&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>mSIGNA (CoinVault) – 推薦：&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Blockchain.info——推薦：&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>用於 Android/BlackBerry 備份的比特幣錢包——推薦：&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>用於 Android/BlackBerry 支出 PIN 的比特幣錢包 –&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#scrypt">scrypt</a>&nbsp;,&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#google-protocol-buffers">Google protobuf</a>&nbsp;, 可選：&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>KnC 錢包用於 Android 備份——推薦：&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Bither –&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Seedrecover_Quick_Start_Guide/#installation">coincurve</a>，可選：&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Litecoin-Qt – 可選：&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Electrum-LTC——推薦：&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>適用於 Android 的萊特幣錢包 – 推薦：&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>狗狗幣核心——可選：&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>MultiDoge——推薦：&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>適用於 Android 的狗狗幣錢包 – 推薦：&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>SLIP39 錢包：&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#shamir-mnemonic">shamir-助記符</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>基於 Py_Crypto_HD_Wallet 的 BIP39 錢包：  <a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#py_crypto_hd_wallet">py_crypto_hd_wallet</a><!-- wp:list -->
<ul><!-- wp:list-item -->
<li>雪崩</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>宇宙（原子）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>波爾卡圓點</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>秘密網絡</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>索拉納</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>恆星</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>論文</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>創</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Helium BIP39 錢包：&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pynacl">pynacl</a>&nbsp;和&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#bitstring">位串</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Eth 密鑰庫文件：&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#eth-keyfile">eth-keyfile</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Groestlecoin BIP39 錢包：&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#groestlcoin_hash">groestlcoin_hash</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>BIP38 加密私鑰：&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#ecdsa">ecdsa</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":3} -->
<h3 id="pycryptodome">PyCryptoDome</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>除了以太坊錢包之外，PyCryptoDome 並不是任何錢包都嚴格要求的，但是它為上面列表中推薦的標記它的錢包提供了 20 倍的速度提升。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="py_crypto_hd_wallet">Py_Crypto_HD_Wallet</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>許多不同的錢包類型都需要此模塊。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>對於 Windows 用戶，您還需要安裝 Microsoft Visual C++ 構建工具，然後才能成功安裝該模塊。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>可以在此處找到涵蓋此內容的視頻教程：&nbsp;&nbsp;<a href="https://youtu.be/0LMUf0R9Pi4">https ://youtu.be/0LMUf0R9Pi4</a></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/0LMUf0R9Pi4","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/0LMUf0R9Pi4
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>對於 MacOS 和 Linux 用戶，如果您按照本頁上適用於您的平台的安裝說明進行操作，模塊應該可以很好地構建/安裝。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 id="running-btcrecoverpy">運行&nbsp;<em>btcrecover.py</em></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>本教程很長……您不必閱讀全部內容。這裡有一些地方可以開始。</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>如果您已經有一個&nbsp;<code>btcrecover-tokens-auto.txt</code>&nbsp;文件，請直接跳到第 6 步。如果沒有，並且您需要幫助根據您記得的較小部分的不同組合創建密碼，請從第 4 步開始。如果您認為您的密碼有錯字，或者如果您大多數人都知道你的整個密碼是什麼，只需要嘗試它的不同變體，閱讀第 5 步。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em>閱讀令牌文件部分（至少是開頭部分），它描述了btcrecover</em>如何&nbsp;&nbsp;從您記得的較小部分構建您不記得的完整密碼。完成後，您將知道如何創建&nbsp;<code>tokens.txt</code>&nbsp;稍後需要的文件。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>閱讀拼寫錯誤部分，它描述了 <em>btcrecover</em>如何 對整個密碼進行變體以創建不同的密碼猜測。完成後，您將獲得一個命令行選項列表，這些選項將創建您要測試的變體。<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>如果您跳過了上面的第 4 步，請改為閱讀簡單的&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#token-Lists-and-password-or-seed-lists">密碼列表</a>&nbsp;部分。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>閱讀 <a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#running-btcrecover">運行&nbsp;<em>btcrecover</em></a> 部分，了解如何將這些部分組合在一起以及如何  在命令提示符窗口中 運行<em>btcrecover 。</em><!-- wp:list -->
<ul><!-- wp:list-item -->
<li>（可選）閱讀&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#testing-your-config">測試您的配置</a>&nbsp;部分以查看將要測試的密碼。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>（可選）如果您要測試大量需要很長時間的組合，請使用&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#autosave">自動保存</a>&nbsp;功能來防止丟失您的進度。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>（可選，但強烈推薦）找到密碼後，向捐贈地址捐贈大量比特幣。</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 id="bip3944-wallets-with-addressdb">帶 AddressDB 的 BIP39/44 錢包</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>如果您正在從 BIP39/44 錢包中恢復密碼，您可以在不知道或不知道您要查找的地址的情況下執行此操作，請參閱使用地址數據庫恢復以獲取更多信息。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="recovery-with-an-address-database">使用地址數據庫恢復</h1>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2 id="background">背景</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>當嘗試恢復 BIP39/44 錢包時，&nbsp;&nbsp;<em>seedrecover.py</em>&nbsp;和&nbsp;<em>btcrecover.py</em>&nbsp;會根據您輸入的種子嘗試不同的猜測，它需要一種方法來確定哪個種子猜測是正確的。通常它使用每個種子猜測來創建一個主公鑰（一個&nbsp;<em>mpk</em>）並將其與您輸入的 mpk 進行比較，或者創建比特幣地址並將它們與您輸入的地址進行比較。如果您既沒有 mpk 也沒有任何地址，仍然可以使用&nbsp;<em>seedrecover.py</em>&nbsp;&nbsp;，但它更複雜且更耗時。&nbsp;<strong>這個過程的主要時間成本是下載區塊鍊和生成 AddressDB，無論是針對單個地址還是針對其中包含 600,000 個地址的 addressDB 進行測試，該過程的實際檢查部分都以大致相同的速度運行……所以如果你對你的錢包使用的地址有一點不確定，一個 AddressDB 是非常值得的</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>這通過生成地址來實現，就像上面一樣，然後在整個區塊鏈中查找每個生成的地址。為此，您必須首先創建一個基於區塊鏈的地址數據庫。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>可以通過兩種方式生成 AddressDB，一種是直接解析原始區塊鏈數據，另一種是處理包含地址列表的文件。（這個地址列表可以包括 BTCRecover 支持的任何地址類型，包括來自多種硬幣類型的地址）</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="pre-made-addressdb-files">預製地址數據庫文件</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>注意：AddressDB 文件在 BTCRecover 的 Python2 和 Python3 分支之間不兼容。確保下載正確的。（這個Github的master分支現在全是Python3了。。。）</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>我已經為一些支持的鏈創建並上傳了 AddressDatabases，並將定期更新它們。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptoguide.tips/btcrecover-addressdbs/">您可以從我的網站下載它們……</a></strong>&nbsp;&nbsp;（然後您可以解壓縮它們並使用 –addressdb 包含完整路徑和文件名以告訴 seedrecover.py 或 btcrecover.py 在哪裡查找）</p>
<!-- /wp:paragraph -->

<!-- wp:image {"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://cryptoguide.tips/btcrecover-addressdbs/AddressDBs%20include%20transactions%20up%20until%20approximately%20the%20file%20modified%20date.txt"><img src="https://cryptoguide.tips/icons/text.gif" alt="[TXT]"/></a></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2 id="parameters-to-manage-addressdb-size">管理 AddressDB 大小的參數</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>長度</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>此工具會創建一個數據庫文件，您需要在其中預先指定其最大大小。這個最大地址數以 2 的冪給出，例如：-dblength 30 為 2^30 個地址留出空間，不到十億……基本上，如果區塊鏈中的地址多於文件中的空間，程序只會崩潰，因此您可能需要重新運行它並將 –dblength 增加一。它默認為 30，這會創建一個約 8GB 的​​文件，足以用於 2018 年 11 月的比特幣區塊鏈。（我計劃更改此行為，以便默認情況下它會從小開始，並在 Python3 移動後根據需要重試幾次&nbsp;<strong>）問題是 AddressDB 文件大小取決於它可以容納的最大地址數，而不是使用了多少。</strong>&nbsp;這意味著如果您正在為 Vertcoin 等較小的區塊鏈生成地址數據庫，您可以指定較小的 dblength 以節省空間。如果您將其保留為默認值，那麼當 ~30mb 文件可以工作時，您最終會得到一個 8GB 文件。&nbsp;<strong>不過如果你有足夠的硬盤空間，那就沒關係了</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>截至 2021 年 1 月，區塊鏈、AddressDB 大小和最佳參數的粗略指南是：</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><thead><tr><th>硬幣</th><th>區塊鏈大小</th><th>地址數據庫大小</th><th>必需的 DBLength</th></tr></thead><tbody><tr><td>比特幣</td><td>324GB</td><td>16 GB</td><td>31</td></tr><tr><td>比特幣現金</td><td>155GB</td><td>4GB</td><td>29</td></tr><tr><td>萊特幣</td><td>90GB</td><td>2GB</td><td>28</td></tr><tr><td>綠幣</td><td>5GB</td><td>32MB</td><td>22</td></tr><tr><td>摩納幣</td><td>2.5GB</td><td>32MB</td><td>22</td></tr><tr><td>以太坊</td><td>N/A（來自 BigQuery 的 AddressList 約有 1.2 億個地址）</td><td>4GB</td><td>29</td></tr><tr><td>狗狗幣</td><td>N/A（來自 BigQuery 的地址列表，包含約 6000 萬個地址）</td><td>1GB</td><td>27</td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p><em>如果有疑問，只需下載完整的區塊鏈並在其中解析它......默認就可以了......</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>限制 AddressDB 創建的日期範圍</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>可以創建一個地址數據庫，其中僅包含特定日期之間發生的交易的地址。這很有用，因為它需要更少的額外空間用於 AddressDB 文件，並且使用的 ram 也少得多。（例如：您可以選擇僅考慮在您訂購硬件錢包後使用的地址）這是通過 –blocks-startdate BLOCKS_STARTDATE 和 –blocks-enddate BLOCKS_ENDDATE 參數完成的，日期格式為 YYYY-MM-DD</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>在 AddressDB 創建中跳過 X 個塊文件</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>也可以告訴 AddressDB 創建腳本從某個塊文件開始處理。這有助於加快處理更大的區塊鏈。（例如：如果您只想要 2018 年使用的比特幣地址）這是通過 –first-block-file FIRST_BLOCK_FILE 完成的，其中 FIRST_BLOCK_FILE 是塊文件的編號。&nbsp;<strong>如果與 –blocks-startdate 一起使用，如果您告訴它在開始日期之後開始計算塊，則此功能不會警告您</strong></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="creating-an-addressdb-from-blockchain-data">從區塊鏈數據創建 AddressDB</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>您可以通過解析來自以下來源的原始區塊鏈數據來生成地址數據庫：*比特幣*比特幣現金*萊特幣*Vertcoin*Monacoin</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>它也可以通過嘗試通過 –dbyolo 標誌來強制它與其他“類似比特幣”的區塊鏈一起工作。（如果你看到發現的地址數量在處理過程中增加，你就會知道它正在成功解析區塊鏈）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>我已經對其進行了測試並確認它&nbsp;<strong>不適</strong>&nbsp;用於 * Dogecoin * Verge * Zcash 和 Zencash * Monero * Ethereum</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>對於這些區塊鏈，您需要獲取地址列表（通過類似 Google BigQuery 的方式）並從該列表生成地址數據庫。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>山寨幣區塊鏈</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>該工具經過測試可與上述指定的區塊鏈一起使用。默認情況下，它將掃描默認的比特幣安裝目錄並使用它。如果你在其他地方安裝了比特幣，或者你想從另一個區塊鏈創建一個 AddressDB，你將需要使用 –datadir 參數手動指定它的位置。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>您要使用哪個區塊鏈的問題取決於您的個人情況。也就是說，如果你有一個 BIP39 錢包，你知道你曾經在某個時候存儲萊特幣或 Vertcoin，那麼你可能更願意從下載和使用這些鏈之一開始，而不是下載完整的 BTC 區塊鏈。您的 BIP39/44 錢包將對所有貨幣使用相同的種子，因此您使用哪一個來恢復種子並不重要。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>重現的例子</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果您想針對 AddressDB 運行一些測試，可以在&nbsp;該項目的<a href="https://github.com/demining/CryptoDeepTools/tree/master/btcrecover/test/test-addressdbs">./btcrecover/test/test-addressdbs</a>&nbsp;文件夾中找到測試數據庫。基本上它們很小，因為它們只包含每個區塊 24 小時的地址。（它們是使用 –blocks-startdate 和 enddate 參數創建的）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>您可以使用以下命令使用這些數據庫之一運行測試：</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>python3 seedrecover.py --no-dupchecks --addr-limit 2 --bip32-path "m/44'/28'/1'/0" --big-typos 1 --addressdb ./btcrecover/test/test-addressdbs/addresses-VTC-Test.db --wallet-type bip39</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>以及帶有數字 1 而不是第一個單詞的種子......</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>1 entire sniff tired miracle solve shadow scatter hello never tank side sight isolate sister uniform advice pen praise soap lizard festival connect baby</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/master/btcrecover/test/test_seeds.py">您可以在test_seeds.py</a>中涵蓋的單元測試中找到更多使用小型 AddressDB 的測試示例&nbsp;&nbsp;，只需搜索以“test_addressdb_”開頭的方法，參數將列出 addressDB 限制、測試短語、派生路徑和使用的 AddressDB。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>從區塊鏈數據創建 AddressDb 的步驟：</strong>&nbsp;&nbsp;1. 您必須使用一台具有足夠空間的計算機來處理您要處理的完整區塊鏈，並且 RAM 等於您最終將擁有的 AddressDB 大小的兩倍（這是一個非常慷慨的估計，你可能會少一些，但幾乎需要至少與你想要創建的 AddressDB 一樣多）。您必須安裝 64 位版本的 Python。（其他較小的區塊鏈需要更少的空間和 RAM）</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>為您選擇的區塊鏈安裝全節點客戶端，例如&nbsp;<a href="https://bitcoincore.org/">Bitcoin Core</a>、&nbsp;&nbsp;<a href="https://bitcoinabc.org/">Bitcoin ABC</a>、&nbsp;&nbsp;<a href="https://litecoin.org/">Litecoin Core</a>、&nbsp;&nbsp;<a href="https://vertcoin.org/download-wallet/">Vertcoin</a>、&nbsp;&nbsp;<a href="https://monacoin.org/">Monacoin Core</a>。（像 Electrum 等這樣的精簡版客戶端將不適用於此……）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>啟動你的全節點客戶端並讓它完全同步。根據您的 Internet 連接和您的計算機，完全同步節點可能需要一天或幾天的時間。以選項開頭&nbsp;<code>bitcoin-qt</code>&nbsp;（或&nbsp;<code>bitcoind</code>）&nbsp;<code>-dbcache #</code>&nbsp;會有所幫助：這&nbsp;<code>#</code>&nbsp;是用於數據庫緩存的 RAM 量（以 MB 為單位）。如果您的計算機至少有 8 GB 的 RAM，則放棄最多&nbsp;<code>4000</code>&nbsp;MB 的&nbsp;<code>-dbcache</code>&nbsp;內存會加快速度。在帶有 SSD 的計算機上安裝比特幣也有幫助。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>同步全節點客戶端后，關閉全節點客戶端軟件。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>（在 OS X 上，將&nbsp;<code>create-address-db.py</code>&nbsp;腳本文件重命名為&nbsp;<code>create-address-db.command</code>。）雙擊腳本&nbsp;<code>create-address-db.py</code>&nbsp;（在與 相同的文件夾中&nbsp;<code>seedrecover.py</code>）以使用完全同步的區塊鏈構建地址數據庫（它將保存到與&nbsp;<code>create-address-db.py</code>&nbsp;名稱&nbsp;相同的目錄中<code>addresses.db</code>） .&nbsp;此過程大約需要一個小時，並使用大約 4 GB 的 RAM 和驅動器空間。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Creating_and_Using_AddressDB/#running-seedrecoverpy">按照運行&nbsp;<em>seedrecover.py</em></a>部分中列出的步驟進行操作&nbsp;&nbsp;，不同之處在於當您在第 4 步中到達地址輸入窗口時，單擊&nbsp;<code>Cancel</code>。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>下一步，您仍然需要選擇一個地址生成限制。這應該是您懷疑在您使用過的第一個地址之前您錢包開頭的未使用地址的數量。如果你確定你使用了錢包中的第一個地址，你可以&nbsp;<code>1</code>&nbsp;在這裡使用，但如果你不太確定，你應該選擇一個更高的估計值（儘管&nbsp;&nbsp;運行<em>seedrecover.py可能需要更長的時間）。</em></li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>請注意，與地址數據庫一起運行時，與 AddressDB 一起運行將使用與 AddressDB 文件大小大致相同的 RAM。（例如：截至 2019 年 11 月，完整的比特幣地址數據庫將需要大約 8.5gb 的內存）</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="creating-an-addressdb-from-an-address-list">從地址列表創建 AddressDB</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>創建地址數據庫的另一種方法是使用地址列表。（例如：來自 Google BigQuery 之類的所有 Eth 地址的列表）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>您只需使用 –inputlist 參數指定輸入列表以及指定要使用的 dblength。（否則它將默認為 30，創建一個 8gb 文件）您可能還需要 –multifileinputlist 以便您可以自動包含在將數據從 bigquery 導出到 Google Cloud Storage 時自動創建的文件列表。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果你想合併來自多個列表的地址，或者將地址列表添加到現有的區塊鏈生成的 addressDB，你可以使用 –update 參數來實現。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>添加一個包含大約 1000 萬個地址的文件大約需要一分鐘……（基於 BigQuery Eth 數據的性能）</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="generating-address-lists-from-google-bigquery">從 Google BigQuery 生成地址列表</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em><strong>注意：</strong>&nbsp;&nbsp;Google BigQuery 上的數據僅每 1-2 個月更新一次，有時更新頻率較低，因此請務必查看您用於生成 AddressDB 的數據集的“上次修改”信息，以確保其中包含與交易相關的交易到您的錢包……（例如：您在“最後修改”日期之前至少進行了一筆交易）</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>有用的 Google BigQuery 查詢</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://console.cloud.google.com/bigquery?sq=871259226971:05c3cbf256dd43a898f5168b94bc66cc">所有比特幣地址</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://console.cloud.google.com/bigquery?sq=871259226971:c6370cf863224be1942ecfdf03e0f0ca">所有 Eth 地址</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://console.cloud.google.com/bigquery?sq=871259226971:c130730990e94212bf20b3dea5c4c815">所有總督地址</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://console.cloud.google.com/bigquery?sq=871259226971:1cb1a218b17d4498bb3d9103e5b2fb3a">所有 BCH 地址</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://console.cloud.google.com/bigquery?sq=871259226971:13e998b9bf864df8b7c0772f4913b28d">所有 LTC 地址</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="generating-address-lists-using-ethereum-etl">使用 Ethereum-ETL 生成地址列表</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>已確認適用於：* Binance 智能鏈，安裝了 Geth 節點，按照：&nbsp; https:&nbsp;<a href="https://docs.bnbchain.org/docs/validator/fullnode">//docs.bnbchain.org/docs/validator/fullnode</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>對於 EVM 類型的鏈（例如：幣安智能鏈），另一種選擇是使用 Ethereum-ETL 工具。這允許您查詢完整節點（運行 Geth 或 Parity，或它們的分支）並檢索表示交易的人類可讀 CSV 數據。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>一旦運行了 Geth-Like 節點，就可以使用如下命令檢索 ETL 數據：</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>ethereumetl export_blocks_and_transactions --start-block STARTBLOCKNUMBER --end-block ENDBLOCKNUMBER --provider-uri http://FULLNODEIP:8545 --blocks-output LOCAL_BLOCKS_CSV_FILE --transactions-output LOCAL_TRANSACTIONS_CSV_FILE</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>導出交易後，您可以使用&nbsp;此存儲庫中<code>addrListsFromETLTransactions.py</code>&nbsp;文件&nbsp;<code>utilities</code>&nbsp;夾中的文件來生成包含地址列表的文件。然後可以使用這些地址列表使用前面介紹的相同過程創建地址數據庫。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>使用這種方法要理解的關鍵是，您將需要數 TB 的磁盤空間來存儲/運行，並且需要數 TB 的額外空間來存儲完整的以太坊 ETL 輸出。（所以您可能需要大約 10TB 的空間……）</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="checkingvalidating-addressdbs">檢查/驗證地址數據庫</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>您可以使用 check-address-db.py 文件來測試任何地址列表文件是否包含任何給定地址。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>例如，您可以使用以下命令驗證 Dogecoin AddressDB（可在上方下載）是否包含一些特定地址：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_1" class="wp-block-code"><code>python3 check-address-db.py --dbfilename "E:\CryptoGuide\OneDrive\AddressDBs (Mega)\addresses-DOGE.db" --checkaddresses DMQ6uuLAtNoe5y6DCpxk2Hy83nYSPDwb5T DFgLZmxFnzv2wR4GAGS3GeHvoEeSkz9ubU DKTHYZwd81xT7qJF33YRi7ftDkvouGdxxN
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>這將產生以下輸出</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>Starting CheckAddressDB 1.9.0-CryptoGuide
Loading address database ...
Loaded 60750752 addresses from database ...
DMQ6uuLAtNoe5y6DCpxk2Hy83nYSPDwb5T Found!
DFgLZmxFnzv2wR4GAGS3GeHvoEeSkz9ubU Found!
DKTHYZwd81xT7qJF33YRi7ftDkvouGdxxN Found!
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><strong>清單文件</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>BTCRecover 存儲庫捆綁了一些基本的地址列表，可用於檢查 addressDB 是否包含在特定時間間隔內首次播種的地址。這些地址是從區塊鏈中隨機選擇的，間隔大約 6 個月。（因此可用於確保給定的 addressDB 大致涵蓋您需要的日期）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>例如，您可以使用命令驗證 Dogecoin AddressDB（可在上面下載）包含到 2021 年 2 月的地址。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>python3 check-address-db.py --dbfilename addresses-DOGE.db --checkaddresslist ./addressdb-checklists/DOGE.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>這將產生以下輸出</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_4" class="wp-block-code"><code>Starting CheckAddressDB 1.9.0-CryptoGuide
Loading address database ...
Loaded 60750752 addresses from database ...
Loading:  ./addressdb-checklists/DOGE.txt
DMQ6uuLAtNoe5y6DCpxk2Hy83nYSPDwb5T Found! First Seen 2021-01-31
DFgLZmxFnzv2wR4GAGS3GeHvoEeSkz9ubU Found! First seen 2020-06-29
DKTHYZwd81xT7qJF33YRi7ftDkvouGdxxN Found! First seen 2019-12-30
DPPg5BVqn7Ck5YVf6ei7NbXGVPDSzXnCBL Found! First seen 2019-05-17
DBbTFW9PZJj9EsXu5Ji59Tp6ZdKNrTZmWq Found! First seen 2018-12-05
DFJRDVzjk7NPbApWsLDreML7RDawp8UmoF Found! First seen 2018-05-16
D9dWXJjYb4HDrXpdef234GHDDggrnGsfxm Found! First seen 2017-11-05
D6A894uLhQjwSRpEroPMop4MPpUL4BZZHc Found! First seen 2017-05-19
DGVxem7KdNBCJWygpRcypS5pMJgJVRZEXD Found! First seen 2016-12-25
DMPHyer3WdKrSmwmFarXtXCxbbp4BMwo9J Found! First seen 2016-05-22
DRusoAd1Q9PJq3KpkhXjpZAoCqdQzGS6AH Found! First seen 2015-12-29
D6sxvQRSriU4pkozdYxDVRKRmoRYCVmqKv Found! First seen 2015-05-10
DNULsd2gbojENHtRRx45PUWvPgkrbL2vjE Found! First seen 2014-12-15
D5mrYgNeLwVXFyy9t9NhBpTqVaa58gUYAC Found! First seen 2014-04-29
DLAznsPDLDRgsVcTFWRMYMG5uH6GddDtv8 Found! First seen 2013-12-07
</code></pre>
<!-- /wp:code -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 id="token-lists-and-password-or-seed-lists">令牌列表和密碼或種子列表</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>密碼和種子恢復方法都允許使用令牌文件和密碼/種子列表文件。對於密碼恢復，至少需要其中之一。（並且可能需要某些類型的種子恢復，例如：解讀種子短語）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>密碼/種子列表文件還允許將生成密碼的任務和測試密碼的任務分成兩個單獨的步驟，使用戶能夠利用 PYPY 為密碼生成提供的速度提升，提高測試速度在 cpython 中，同時也使得跨多個服務器拆分測試大量密碼的任務變得微不足道。（或者單獨執行創建密碼列表的單線程操作，以在更強大/更昂貴的系統上測試它的任務）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>密碼列表文件和令牌文件在下面都有自己的文檔……</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/passwordlist_file/">密碼/種子列表文件</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/tokenlist_file/">令牌列表文件</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="typos">錯別字</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>btcrecover</em>&nbsp;可以生成不同的密碼變體，以查找您在輸入密碼或寫下密碼時可能無意中犯下的拼寫錯誤或錯誤。通過在運行&nbsp;<em>btcrecover</em>時包含一個或多個命令行選項來啟用此功能。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果您只是喜歡可以添加的命令行選項的一些具體示例，請參閱&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Typos_Quick_Start_Guide/">Typos Quick Start Guide</a>。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>使用&nbsp;<code>--typos #</code>&nbsp;命令行選項（替換&nbsp;<code>#</code>&nbsp;為打字錯誤計數），您可以告訴&nbsp;<em>btcrecover</em>&nbsp;您希望它向每個密碼添加多少打字錯誤（從令牌文件生成或從密碼列表中獲取為如上所述）。您還必須指定您希望它生成的拼寫錯誤類型，它會為您檢查所有可能的組合（包括不存在拼寫錯誤的可能性）。以下是基本拼寫錯誤類型的摘要以及啟用每種拼寫錯誤的命令行選項：</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>--typos-capslock</code>&nbsp;– 在大寫鎖定打開的情況下嘗試整個密碼</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>--typos-swap</code>&nbsp;– 交換兩個相鄰的字符</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>--typos-repeat</code>&nbsp;– 重複（加倍）一個字符</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>--typos-delete</code>&nbsp;– 刪除一個字符</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>--typos-case</code>&nbsp;– 更改單個字母的大小寫（大寫/小寫）</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>例如，使用&nbsp;<code>--typos 2 --typos-capslock --typos-repeat</code>&nbsp;在命令行上指定的選項，將嘗試包含最多兩個拼寫錯誤的所有組合，例如&nbsp;<code>Cairo</code>&nbsp;（沒有拼寫錯誤）、&nbsp;&nbsp;<code>cAIRO</code>&nbsp;（一個拼寫錯誤：caps lock）、&nbsp;&nbsp;<code>CCairoo</code>&nbsp;（兩個拼寫錯誤：兩個重複）和&nbsp;<code>cAIROO</code>&nbsp;（兩個拼寫錯誤：一個每種類型）將被嘗試。在命令行中添加大量拼寫錯誤類型會顯著增加組合的數量，並且增加計數&nbsp;<code>--typos</code>&nbsp;可能會更加顯著，因此在使用此功能時最好小心謹慎，除非您的令牌文件或密碼列表很小。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>以下是一些需要更多解釋的其他類型的拼寫錯誤：</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>--typos-closecase</code>&nbsp;– 喜歡&nbsp;<code>--typos-case</code>，但它只會嘗試更改字母的大小寫，前提是該字母與另一個大小寫不同的字母相鄰，或者它位於開頭或結尾。這會產生更少的組合來嘗試，因此它會運行得更快，並且它仍然會捕捉到更有可能有人按住 shift 鍵的時間過長或時間不夠長的情況。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>--typos-replace s</code>&nbsp;– 這會嘗試用指定的字符串（在示例中為 an&nbsp;&nbsp;<code>s</code>）替換每個單個字符。字符串可以是單個字符，也可以是某個更長的字符串（在這種情況下，每個單個字符都被整個字符串替換），甚至是一個帶有一個或多個&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#expanding-wildcards">擴展通配符的</a>字符串&nbsp;。例如，&nbsp;<code>--typos 1 --typos-replace %a</code>&nbsp;嘗試用小寫字母替換每個字符（一次一個），嘗試所有可能的組合。使用通配符可以大大增加組合的總數。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>--typos-insert s</code>&nbsp;– 就像&nbsp;<code>--typos-replace</code>，但不是替換字符，而是嘗試在每對字符之間以及開頭和結尾插入字符串的單個副本（或通配符替換）。即使大於 1&nbsp;&nbsp;<code>--typos</code>&nbsp;，&nbsp;<code>--typos-insert</code>&nbsp;通常不會嘗試在同一位置插入字符串的多個副本。例如，對於&nbsp;<code>--typos 2 --typos-insert Z</code>&nbsp;指定的、諸如&nbsp;<code>CaiZro</code>&nbsp;和 之&nbsp;類的猜測<code>CZairoZ</code>&nbsp;已嘗試，但未&nbsp;<code>CaiZZro</code>&nbsp;嘗試。您可以使用&nbsp;<code>--max-adjacent-inserts #</code>&nbsp;大於 1 的數字來更改此設置。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":4} -->
<h4 id="typos-map">錯別字地圖</h4>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>--typos-map typos.txt</code>&nbsp;– 這是一種相對複雜但也很靈活的錯字類型。它嘗試用其他特定字符替換某些特定字符，使用單獨的文件（在本例中名為&nbsp;<code>typos.txt</code>）拼寫詳細信息。例如，如果您知道自己經常在標點符號上犯錯，您可以創建一個錯別字映射文件，其中包含以下兩行： 在本<code>. ,/; ; [‘/.&nbsp;</code>例中，&nbsp;&nbsp;<em>btcrecover</em>&nbsp;將嘗試用&nbsp;<code>.</code>&nbsp;空格後面的三個標點符號之一替換每一個在同一行上，它會嘗試用&nbsp;<code>;</code>&nbsp;後面的四個標點符號之一替換每個標點符號。此功能不僅可用於拼寫錯誤。例如，如果您是“1337”（leet）的粉絲，請在您的密碼中說話，您可以按照以下行創建拼寫錯誤圖：<code>aA @ sS $5 oO 0&nbsp;</code>這將嘗試將&nbsp;<code>a</code>&nbsp;or&nbsp;的實例替換<code>A</code>&nbsp;為&nbsp;or 的<code>@</code>實例，將&nbsp;<code>s</code>&nbsp;or&nbsp;的實例替換<code>S</code>&nbsp;為 a&nbsp;<code>$</code>&nbsp;或 a&nbsp;<code>5</code>等，直到選項指定的最大拼寫錯誤數&nbsp;<code>--typos #</code>&nbsp;。例如，如果令牌文件包含令牌&nbsp;<code>Passwords</code>，並且如果您指定&nbsp;<code>--typos 3</code>,&nbsp;<code>P@55words</code>&nbsp;和&nbsp;<code>Pa$sword5</code>&nbsp;都會被嘗試，因為它們每個都有三個或更少的拼寫錯誤/替換，但&nbsp;<code>P@$$w0rd5</code>&nbsp;不會嘗試其 5 個拼寫錯誤&nbsp;<em>。btcrecover</em>&nbsp;包包含一些拼寫錯誤 -映射目錄中的示例文件&nbsp;<code>typos</code>&nbsp;。您可以在 Typos Quick Start Guide 中閱讀有關它們的更多信息。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":3} -->
<h3 id="max-typos-by-type">按類型劃分的最大錯別字</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>如上所述，&nbsp;<code>--typos #</code>&nbsp;命令行選項限制了將永遠應用於單個猜測的打字錯誤總數，無論類型如何。您還可以設置僅適用於特定類型拼寫錯誤的限制。對於上面的每個&nbsp;<code>--typos-xxxx</code>&nbsp;命令行選項，都有一個相應的&nbsp;<code>--max-typos-xxxx #</code>&nbsp;選項。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>例如，對於&nbsp;<code>--typos 3 --typos-delete --typos-insert %a --max-typos-insert 1</code>，將嘗試最多三個拼寫錯誤。所有這些都可能是刪除拼寫錯誤，但最多只有一個是插入拼寫錯誤（在這種情況下會插入一個小寫字母）。<code>--typos-insert</code>&nbsp;當和 與&nbsp;本例中的通配符一起使用時，這一點特別有用&nbsp;<code>--typos-replace</code>&nbsp;，因為它可以大大減少需要嘗試的組合總數，將需要很長時間才能測試的總數變成更合理的組合.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="typos-gory-details">錯別字血淋淋的細節</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>拼寫錯誤功能的目的是一次最多只將一個拼寫錯誤應用於任何單個字符，即使將多個拼寫錯誤應用於單個密碼猜測也是如此。例如，當指定 時&nbsp;<code>--typos 2 --typo-case --typo-repeat</code>，每個密碼猜測最多可以應用兩個拼寫錯誤（因此&nbsp;&nbsp;最多更改兩個大小寫，<strong>或</strong>&nbsp;兩個重複字符，&nbsp;<strong>或一個大小寫更改加一個重複字符）。</strong>一個猜測中的單個字符在一次猜測中不會有一個以上的打字錯誤，例如，一個字符永遠不會同時重複和大小寫更改。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>然而，這個每個字符一個錯字的規則也有一些例外——一個是故意的，一個是由於軟件的限制。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>打字&nbsp;<code>--typos-capslock</code>&nbsp;錯誤模擬了在猜測過程中打開大寫鎖定。它可以同時影響密碼中的所有字母，即使它是一個拼寫錯誤。作為每個字符一個拼寫錯誤規則的例外，單個字母&nbsp;<em>可能</em>&nbsp;同時受到大寫鎖定拼寫錯誤和另一個拼寫錯誤的影響。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>該&nbsp;<code>--typos-swap</code>&nbsp;錯字還忽略了每個字符一個錯字的規則。可以交換兩個相鄰的字符（算作一個拼寫錯誤），然後可以將第二個拼寫錯誤應用於一個（或兩個）交換字符。這與其說是設計選擇，不如說是軟件限制，但不太可能改變。但是，您可以保證每次猜測一個字符永遠不會交換超過一次。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>最後應該注意的是，通配符替換（擴展和收縮）發生在拼寫錯誤之前，並且拼寫錯誤可以應用於通配符擴展的結果。密碼創建的確切順序是：</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>根據所有令牌規則（互斥、錨點等）從一個或多個令牌創建“基本”密碼。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>應用所有通配符擴展和收縮。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>最多應用一個大寫鎖定錯字。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>應用零個或多個交換拼寫錯誤。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>應用零個或多個改變字符的拼寫錯誤（這些拼寫錯誤&nbsp;<em>確實</em>&nbsp;遵循每個字符一個拼寫錯誤的規則）。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>應用零個或多個拼寫錯誤插入（來自&nbsp;<code>typos-insert</code>&nbsp;選項）。</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>在任何時候，單次猜測中的拼寫錯誤總數都不會超過選項所要求的&nbsp;（&nbsp;如果使用的話，<code>--typos #</code>&nbsp;也不會少於&nbsp;選項）。<code>--min-typos</code></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="autosave">自動保存</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>根據需要嘗試的密碼數量，運行&nbsp;<em>btcrecover</em>&nbsp;可能需要很長時間。如果它在測試過程中被中斷（使用 Ctrl-C（見下文），由於重新啟動、意外關閉命令提示符或任何其他原因），您可能會丟失進度並不得不從開始。為了防止這種情況，您可以&nbsp;<code>--autosave savefile</code>&nbsp;在第一次啟動&nbsp;<em>btcrecover</em>時添加該選項。它會大約每 5 分鐘自動將其進度保存到您指定的文件中（在本例中，它已命名&nbsp;<code>savefile</code>&nbsp;——您可以隨意創建任何文件名，只要它不存在即可）。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果中斷，您可以通過使用完全相同的選項運行它來重新開始測試，或者只提供此選項而不提供其他選項：&nbsp;&nbsp;<code>--restore savefile</code>。&nbsp;<em>然後btcrecover</em>&nbsp;將開始準確地測試它停止的地方。（請注意，令牌文件以及拼寫錯誤映射文件（如果使用）必須仍然存在並且必須未經修改才能正常工作。如果它們不存在或已被更改，btcrecover 將&nbsp;<em>拒絕</em>&nbsp;啟動.)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>密碼列表目前不支持自動保存功能，僅令牌文件支持。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="interrupt-and-continue">中斷並繼續</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>如果您需要&nbsp;&nbsp;在測試過程中中斷 btcrecover，您可以使用 Ctrl-C（按住 Ctrl 鍵並按 C）來執行此操作，它會以這樣的消息響應，然後它會退出<em>：</em></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>Interrupted after finishing password # 357449
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>如果您沒有啟用自動保存功能，您仍然可以從中斷的地方手動開始測試。您需要使用&nbsp;&nbsp;完全相同&nbsp;<em>的</em>&nbsp;令牌文件或密碼列表、拼寫錯誤映射文件（如果您使用的是一個）和命令行選項以及一個額外的選項來&nbsp;啟動<em>btcrecover</em>，它將在它停止的地方啟動。<em></em><code>--skip 357449</code></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="unicode-support">統一碼支持</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>如果您的密碼包含任何非<a href="https://en.wikipedia.org/wiki/ASCII#ASCII_printable_code_chart">ASCII</a>&nbsp;&nbsp;（非英語）字符，您將需要添加&nbsp;<code>--utf8</code>&nbsp;命令行選項以啟用 Unicode 支持。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>請注意， btcrecover</em>的所有輸入和輸出&nbsp;&nbsp;都必須採用 UTF-8 編碼（帶或不帶字節順序標記或“BOM”），因此請確保在保存任何文本文件時將編碼更改為 UTF-8。例如，在 Windows 記事本中，文件&nbsp;<em>編碼</em>&nbsp;設置就在&nbsp;<em>文件</em>&nbsp;-&gt;&nbsp;<em>另存為...</em>對話框&nbsp;中的&nbsp;<em>保存</em>按鈕旁邊&nbsp;。<em></em><em></em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>在 Windows 上（但通常不在 Linux 或 OS X 上），如果您需要使用的任何命令行選項包含任何非 ASCII 字符，您可能會遇到麻煩。通常，如果它在您鍵入時正確地顯示在命令提示符窗口中，那麼它將與&nbsp;<code>btcrecover.py</code>.&nbsp;如果顯示不正確，請閱讀描述如何將&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#command-line-options-inside-the-tokens-file">命令行選項放入令牌文件的</a>部分。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>同樣在 Windows 上（但通常不在 Linux 或 OS X 上），如果找到您的密碼，它可能無法在命令提示符窗口中正確顯示。以下是錯誤輸出的示例：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_4" class="wp-block-code"><code>Password found: 'btcr-????-??????'
HTML encoded:   'btcr-&amp;#1090;&amp;#1077;&amp;#1089;&amp;#1090;-&amp;#1087;&amp;#1072;&amp;#1088;&amp;#1086;&amp;#1083;&amp;#1100;'
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>如您所見，Windows 命令提示符無法呈現某些字符（它們已被替換為&nbsp;<code>?</code>&nbsp;字符）。要查看找到的密碼，請複制該&nbsp;<code>HTML encoded</code>&nbsp;行並將其粘貼到一個文本文件中，並使用以結尾的名稱&nbsp;<code>.html</code>&nbsp;而不是通常的&nbsp;<code>.txt</code>.&nbsp;雙擊新&nbsp;<code>.html</code>&nbsp;文件，它將在您的 Web 瀏覽器中打開以顯示正確的密碼：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_5" class="wp-block-code"><code>HTML encoded: 'btcr-тест-пароль'
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="running-btcrecover">運行&nbsp;<em>btcrecover</em></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>（另請參閱“快速入門”部分。）安裝所有要求（以上）並下載最新版本後：</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>解壓縮&nbsp;<code>btcrecover-master.zip</code>&nbsp;文件，它包含一個名為“btcrecover-master”的目錄。btcrecover-master 目錄裡面是 Python 腳本（程序）文件&nbsp;<code>btcrecover.py</code>。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>將你的錢包文件複製</strong> 到包含 <code>btcrecover.py</code>. 在 Windows 上，您通常可以通過單擊“開始”菜單，然後單擊“運行...”（或對於 Windows 8+，按住 Windows 鍵並按 <em>）</em> 找到 您的錢包文件<code>r</code>，然後輸入以下路徑之一併單擊確定. 一些錢包軟件允許您創建多個錢包。當然，你需要確保複製正確的錢包文件。<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>BIP-39 密碼短語——請參閱下面的 BIP-39 密碼短語部分。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>比特幣核心——&nbsp;&nbsp;<code>%appdata%\Bitcoin</code>&nbsp;（它被命名為&nbsp;<code>wallet.dat</code>）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Android/BlackBerry 的比特幣錢包，丟失了支出 PIN——請參閱&nbsp;下面<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#bitcoin-wallet-for-androidblackberry-spending-pins">的 Android/BlackBerry 支出 PIN 的比特幣錢包</a>&nbsp;部分。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Bither –&nbsp;&nbsp;<code>%appdata%\Bither</code>&nbsp;（它被命名為&nbsp;<code>address.db</code>）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Blockchain.com——它通常被命名為&nbsp;<code>wallet.aes.json</code>；如果你沒有錢包文件的備份，&nbsp;&nbsp;如果你知道你的錢包 ID（如果啟用了 2FA），你可以通過<code>download-blockchain-wallet.py</code>&nbsp;在目錄中運行該工具&nbsp;來下載一個<code>extract-scripts</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Coinomi – 請參閱&nbsp;下面的<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#finding-coinomi-wallet-files">查找 Coinomi 錢包文件</a>&nbsp;部分。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>金銀合金 –&nbsp;<code>%appdata%\Electrum\wallets</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Litecoin-Qt –&nbsp;&nbsp;<code>%appdata%\Litecoin</code>&nbsp;（它被命名為&nbsp;<code>wallet.dat</code>）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Metamask（以及 Metamask 的克隆版，如幣安鏈錢包、Ronin 錢包等）——請參閱&nbsp;下面的<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#finding-metamask-wallet-files">查找 Metamask 錢包文件</a>&nbsp;部分。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>MultiBit Classic – 請參閱&nbsp;下面的<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#finding-multibit-classic-wallet-files">查找 MultiBit Classic 錢包文件</a>&nbsp;部分。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>MultiBit HD –&nbsp;&nbsp;<code>%appdata%\MultiBitHD</code>&nbsp;（它位於此處的其中一個文件夾中，名為&nbsp;<code>mbhd.wallet.aes</code>）</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>mSIGNA –&nbsp;&nbsp;<code>%homedrive%%homepath%</code>&nbsp;（這是一個&nbsp;<code>.vault</code>&nbsp;文件）</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>如果你有一個&nbsp;<code>btcrecover-tokens-auto.txt</code>&nbsp;文件，你就快完成了。將其複製到包含 的目錄中&nbsp;<code>btcrecover.py</code>，然後只需雙擊該&nbsp;<code>btcrecover.py</code>&nbsp;文件，&nbsp;&nbsp;<em>btcrecover</em>&nbsp;就會開始測試密碼。（如果您的錢包文件與文件中列出的文件名不匹配，您可能需要重命名它&nbsp;<code>btcrecover-tokens-auto.txt</code>&nbsp;。）如果您沒有文件&nbsp;<code>btcrecover-tokens-auto.txt</code>&nbsp;，請繼續閱讀下文。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>將您的&nbsp;<code>tokens.txt</code>&nbsp;文件或您的密碼列表文件（如果您正在使用）複製到包含&nbsp;<code>btcrecover.py</code>.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>您將需要&nbsp;<code>btcrecover.py</code>&nbsp;至少使用兩個命令行選項來運行，&nbsp;<code>--wallet FILE</code>&nbsp;以確定錢包文件名和&nbsp;<code>--tokenlist FILE</code>&nbsp;or&nbsp;&nbsp;<code>--passwordlist FILE</code>&nbsp;（FILE 是可選的&nbsp;<code>--passwordlist</code>），具體取決於您使用的&nbsp;是<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#the-token-file">Token File</a>&nbsp;還是&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#the-passwordlist">Passwordlist</a>。如果您使用的是&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#typos">Typos</a>&nbsp;或&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#autosave">Autosave</a>，請參閱上面的部分以了解您要添加的其他選項。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>這是 Windows 和 OS X 的示例。您的系統的詳細信息會有所不同，例如下載位置可能不同，或者錢包文件名可能不同，因此您需要進行一些更改。任何附加選項都放在 <em>btcrecover</em> 行的末尾。<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><em>Windows</em>：打開命令提示符窗口（單擊“開始”菜單並鍵入“command”），然後鍵入以下兩行。<code>cd Downloads\btcrecover-master python3 btcrecover.py --wallet wallet.dat --tokenlist tokens.txt [other-options...]</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em>OS X</em>：打開一個終端窗口（打開 Launchpad 並蒐索“terminal”），然後輸入以下兩行。<code>cd Downloads/btcrecover-master python3 btcrecover.py --wallet wallet.dat --tokenlist tokens.txt [other-options...]</code></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>短暫延遲後，&nbsp;&nbsp;<em>btcrecover</em>&nbsp;應開始測試密碼，並顯示進度條和預計到達時間，如下所示。如果它似乎卡住只是向上計數並顯示消息&nbsp;<code>Counting passwords ...</code>&nbsp;而沒有進度條，請閱讀&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Limitations_and_Caveats/#memory">內存限制</a>&nbsp;部分。如果這沒有幫助，那麼您可能選擇了太多的標記或拼寫錯誤來測試，導致系統無法處理更多的組合（儘管該選項&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#token-counts"><code>--max-tokens</code></a>&nbsp;可能會有所幫助）。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_8" class="wp-block-code"><code>Counting passwords ...
Done
Using 4 worker threads
439 of 7661527 &#91;-------------------------------] 0:00:10, ETA:  2 days, 0:25:56
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>如果其中一個組合是錢包的正確密碼，密碼最終將被顯示並且&nbsp;<em>btcrecover</em>&nbsp;將停止運行：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_9" class="wp-block-code"><code>1298935 of 7661527 &#91;####-----------------------] 8:12:42, ETA:  1 day, 16:13:24
Password found: 'Passwd42'
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>如果嘗試了所有密碼組合，但沒有一個對錢包是正確的，則將顯示此消息：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_10" class="wp-block-code"><code>7661527 of 7661527 &#91;########################################] 2 days, 0:26:06,
Password search exhausted
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>btcrecover.py</code>&nbsp;使用該&nbsp;選項運行&nbsp;<code>--help</code>&nbsp;將為您提供所有可用命令行選項的摘要，其中大部分已在上面的部分中進行了描述。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="testing-your-config">測試你的配置</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>如果您只想測試您的令牌文件和/或選擇的拼寫錯誤，您可以使用該選項&nbsp;<code>--listpass</code>&nbsp;代替 選項&nbsp;<code>--wallet FILE</code>&nbsp;，如下所示。&nbsp;<em>然後btcrecover</em>&nbsp;將在屏幕上列出所有密碼，而不是根據錢包文件實際測試它們。如果您有另一個工具可以測試其他類型的錢包，並且能夠從&nbsp;<em>btcrecover</em>獲取密碼列表進行測試，這也很有用。因為此選項可以生成如此多的輸出，所以您可能只想將它用於短令牌文件和少量錯字選項。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_11" class="wp-block-code"><code>    python3 btcrecover.py --listpass --tokenlist tokens.txt  | more
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>最後&nbsp;<code>| more</code>&nbsp;（&nbsp;<code>|</code>&nbsp;符號是一個移位的&nbsp;<code>\</code>&nbsp;反斜杠）將在每屏密碼後引入一個暫停。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="extracting-yoroi-master-key">提取 Yoroi 萬能鑰匙</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>基於 Chrome 的瀏覽器錢包</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>您需要先打開您的 Yoroi 錢包，然後在您的瀏覽器中啟用打開開發者工具。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>然後你需要導航到“Application”（Chrome），轉到“IndexedDB”部分，打開“Yoroi-Schema”並導航到“Key”部分。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>然後您將看到一個主密鑰列表。您可能想要第一個加密密鑰，如下所示：</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Images/Yoroi_Extract_MasterKey_Chrome.jpg" alt="Yoroi_Masterkey"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>然後您可以單擊“哈希”字段並選擇“複製”。該字符串是您將與&nbsp;<code>--yoroi-master-password</code>&nbsp;參數一起使用的字符串</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>火狐瀏覽器錢包</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>您可以通過直接訪問擴展名的 .sqlite 文件來查找數據。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>這將在您的瀏覽器配置文件文件夾中找到（此位置將根據您的環境而有所不同）用於擴展。您可以在下面的屏幕截圖的最頂部看到一個示例，說明是否為 Windows 環境找到了此文件。</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Images/Yoroi_Extract_MasterKey_Firefox.jpg" alt="Yoroi_Masterkey"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>然後，您只需使用文本編輯器打開它並查找字符串“Hash”或“isEncrypted”，您的加密主密碼將以明文形式顯示。（在上面的屏幕截圖中以綠色突出顯示）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>該字符串是您將與&nbsp;<code>--yoroi-master-password</code>&nbsp;參數一起使用的字符串</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="finding-multibit-classic-wallet-files">查找 MultiBit 經典錢包文件</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>btcrecover</em>&nbsp;不直接對 MultiBit Classic 錢包文件進行操作，而是對 MultiBit 私鑰備份文件進行操作。<code>key-backup</code>&nbsp;當您第一次為您的 MultiBit Classic 錢包添加密碼時，以及之後每次您添加新的接收地址或更改您的錢包密碼時，MultiBit 都會在錢包文件附近的目錄中創建一個加密的私鑰備份文件。&nbsp;這些私鑰備份文件可以更快地嘗試密碼（超過 1,000 倍），這就是&nbsp;<em>btcrecover</em>&nbsp;使用它們的原因。對於首次安裝 MultiBit 時創建的默認錢包，此目錄位於此處：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_12" class="wp-block-code"><code>%appdata%\MultiBit\multibit-data\key-backup
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>密鑰文件的名稱類似於&nbsp;<code>walletname-20140407200743.key</code>.&nbsp;如果您創建了額外的錢包，它們的&nbsp;<code>key-backup</code>&nbsp;目錄將位於其他地方，您可以自行查找。完成後，選擇最新的&nbsp;<code>.key</code>&nbsp;文件並將其複製到包含它的目錄中以&nbsp;<code>btcrecover.py</code>&nbsp;供使用。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>有關查找 MultiBit 私鑰備份文件的更多詳細信息，請參閱：&nbsp;&nbsp;<a href="https://www.multibit.org/en/help/v0.5/help_fileDescriptions.html" target="_blank" rel="noreferrer noopener">https ://www.multibit.org/en/help/v0.5/help_fileDescriptions.html</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="finding-metamask-wallet-files">查找 Metamask 錢包文件</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>對於基於 Chrome 的瀏覽器，您需要找到瀏覽器擴展的數據文件夾。然後，您可以將此錢包文件夾的路徑與 –wallet 參數一起使用。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>對於 Metamask，這是：%localappdata%\Google\Chrome\User Data\Default\Local Extension Settings\nkbihfbeogaeaoehlefnkodbefgpgknn</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>對於幣安錢包擴展，這是：%localappdata%\Google\Chrome\User Data\Default\Local Extension Settings\fhbohimaelbohpjbbldcngcnapndodjp</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>對於 Ronin 錢包，這是：%localappdata%\Google\Chrome\User Data\Default\Local Extension Settings\fnjhmkhhmkbjkkabndcnnogagogbneec</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果您嘗試恢復最新錢包以外的任何東西，您將需要使用提取腳本來列出擴展數據中所有可能的保險庫。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>對於 Firefox 和 iOS，您將需要使用此處描述的過程來檢索您的 Metamask 保管庫：https://metamask.zendesk.com/hc/en-us/articles/360018766351-How-to-use-the-Vault-Decryptor -with-the-MetaMask-Vault-Data</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>對於移動錢包（iOS 和 Android），您傳遞 BTCRecover 的“錢包文件”是文件：&nbsp;<code>persist-root</code>&nbsp;您可以使用上述過程找到它並直接與 BTCRecover 一起使用。（不需要只提取保險庫數據，刪除多餘的&nbsp;<code>\</code>&nbsp;字符等，所有這些都是自動處理的）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>對於 Android 設備，您將主要需要一部“root”手機。您要查找的文件是：&nbsp;<code>/data/data/io.metamask/files/persistStore/persist-root</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>然後，您可以將保險庫數據（從 Firefox 或提取腳本）複製/粘貼到文本文件中，並直接將其與 –wallet 參數一起使用。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="finding-coinomi-wallet-files">查找 Coinomi 錢包文件</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>注意：這僅支持受密碼保護的錢包。如果您選擇“無密碼”、“生物識別”或“密碼 + 生物識別”，那麼您還需要手機密鑰庫中的信息……（可能無法檢索）</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Coinomi 的第一步取決於您在哪個平台上運行它。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>對於 Windows 用戶，只需導航到 %localappdata%\Coinomi\Coinomi\wallets，你就會找到你的錢包文件。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>對於 Android 用戶，您需要有一部手機，這樣您才能訪問 Coinomi 中的 .wallet 文件。（它應該在文件夾 data\data\com.coinomi.wallet\files\wallets 中找到）如何在您的特定手機上獲得 root 訪問權限超出了本文檔的範圍，但請注意，某些 root 手機的方法將涉及恢復出廠設置。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果那裡有多個錢包而您不確定哪個是正確的，可以在文件末尾以明文形式找到每個錢包的名稱。有關示例，請參閱 ./btcrecover/test/test-wallets 中此存儲庫中包含的測試錢包）</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="downloading-dogechaininfo-wallet-files">下載 Dogechain.info 錢包文件</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>通過“開發者工具”功能，通過瀏覽器下載這些類型的錢包文件 ID。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>基本上，您需要嘗試登錄您的錢包（即使使用錯誤的密碼）並保存在此過程中下載的錢包文件。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>進入 dogechain.info 錢包登錄頁面後，在瀏覽器中打開開發者工具後，您需要執行以下步驟：</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>1) 選擇網絡選項卡</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>2) 輸入您的錢包ID</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>3) 輸入佔位符密碼（你可以輸入任何內容）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>4）點擊登錄（會提示錢包解密失敗，這是正常的）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>5) 選擇“回應”</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>6) 選擇 API 項目。（如果您啟用了 2fa，這可能看起來略有不同，您可能也需要在此步驟中完成 2fa）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>7) 一旦你得到看起來像錢包數據的響應，將其複制並粘貼到文本文件中。這是你的錢包文件……</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Images/download_dogechain_wallet.png" alt="下載道奇鏈錢包"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3 id="downloading-blockio-wallet-files">下載 block.io 錢包文件</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>通過“開發者工具”功能，通過瀏覽器下載這些類型的錢包文件 ID。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>基本上你需要登錄你的錢包，然後進入“設置”屏幕，在那裡你可以在瀏覽器中打開“開發者工具”。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>1) 選擇網絡選項卡</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>2) 在“當前 PIN”字段中輸入佔位符 PIN。（這可以是任何東西，例如：“123”）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>3) 在 New Secret PIN 字段中輸入佔位符密碼。（這可以是任何東西，但必須是有效的，例如：btcrtestpassword2022）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>4) 點擊“Change Secret PIN”（這會提示你的Secret PIN不正確，不過沒關係……）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>5) 選擇“回應”</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>6) 選擇 initiate_change_secrets 文件。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>7) 一旦你得到看起來像錢包數據的響應，將其複制並粘貼到文本文件中。這是你的錢包文件……</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Images/download_block_io_wallet.png" alt="下載 Block IO 錢包"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3 id="bitcoin-wallet-for-androidblackberry-spending-pins">適用於 Android/BlackBerry 消費 PIN 的比特幣錢包</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>適用於 Android/BlackBerry 的比特幣錢包具有&nbsp;&nbsp;可以選擇啟用的<em>消費 PIN功能。</em>如果您丟失了消費密碼，您可以使用&nbsp;<em>btcrecover</em>&nbsp;嘗試恢復它。</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>打開比特幣錢包應用程序，按菜單按鈕，然後選擇安全。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>選擇&nbsp;<em>備份錢包</em>。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>輸入密碼以保護您的錢包備份文件，然後按確定。您需要記住此密碼以備後用。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>按右下角的存檔按鈕。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>選擇一種與您的 PC 共享錢包備份文件的方式，例如您可以選擇 Gmail 或 Drive。</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>這個錢包備份文件一旦保存到您的 PC，就可以像&nbsp;<em>btcrecover</em>中的任何其他錢包文件一樣使用&nbsp;，但有一個重要的例外：當您運行&nbsp;<em>btcrecover</em>時，您&nbsp;<strong>必須</strong>&nbsp;添加該&nbsp;<code>--android-pin</code>&nbsp;選項。當您這樣做時，&nbsp;&nbsp;<em>btcrecover</em>&nbsp;會要求您提供備份密碼（從第 3 步開始），然後它會嘗試恢復消費 PIN。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>因為 PIN 通常只包含數字，所以您的令牌文件通常只包含類似這樣的內容（例如，對於最多 6 位的 PIN）&nbsp;&nbsp;<code>%1,6d</code>：.&nbsp;&nbsp;（有關更多詳細信息，請參閱<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#expanding-wildcards">通配符</a>部分&nbsp;。）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>請注意，如果您不包含該&nbsp;<code>--android-pin</code>&nbsp;選項，&nbsp;&nbsp;<em>btcrecover</em>&nbsp;將嘗試恢復備份密碼。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="bip-39-passphrases-electrum-extra-words">BIP-39 密碼短語和 Electrum “Extra Words”</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>一些&nbsp;符合<a href="https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki">BIP-39</a>&nbsp;標準的錢包提供了向你的種子（助記符）添加“第 25 個單詞”、“BIP-39 密碼”或“似是而非的可否認性密碼”的功能（請注意，大多數硬件錢包還提供不受支持的 PIN 功能通過&nbsp;<em>btcrecover</em>。）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果你知道你的種子，但不記得這個密碼，&nbsp;&nbsp;<em>btcrecover</em>&nbsp;可能會有所幫助。您還需要知道：</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>最好是你的主公鑰/“xpub”（對於&nbsp;&nbsp;你錢包中的&nbsp;<em>第一個賬戶，如果它支持多個賬戶），</em><em>或者</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>由您的錢包（在其第一個帳戶中）生成的接收地址，以及對您在要使用的接收地址之前創建的地址數量的準確估計。</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>獲得此信息後，正常運行&nbsp;<em>btcrecover</em>&nbsp;&nbsp;，除了&nbsp;使用選項<em>而不是</em><code>--wallet wallet.dat</code>&nbsp;使用&nbsp;選項&nbsp;在命令行上提供錢包文件&nbsp;<code>--bip39</code>&nbsp;，例如：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_13" class="wp-block-code"><code>python3 btcrecover.py --bip39 --tokenlist tokens.txt &#91;other-options...]
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>如果您嘗試恢復的地址/帳戶來自 BIP39/44 錢包，但對於比特幣以外的貨幣，您可以使用該參數&nbsp;<code>--wallet-type</code>&nbsp;並指定 seedrecover.py 支持的任何受支持的 BIP39 錢包類型。（例如：bch, bip39, bitcoinj, dash, digibyte, dogecoin, ethereum, electrum2, groestlecoin, litecoin, monacoin, ripple, vertcoin, zilliqa）您還可以嘗試使用與其中任何一種共享派生方案的不受支持的硬幣進行恢復<code>--bip32-path</code>&nbsp;與該硬幣的推導路徑的論點。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/bip39-accounts-and-altcoins/">有關詳細信息，請參閱BIP39 帳戶和山寨幣</a>的註釋&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/bip39-accounts-and-altcoins/"></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果您不確定您的種子和 BIP39 密碼，那麼您將需要使用 seedrecover.py 並指定多個 BIP39 密碼。（但請注意，這非常慢）</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="gpu-acceleration-for-bitcoin-core-and-litecoin-qt-wallets">比特幣核心和 Litecoin-Qt 錢包的 GPU 加速</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>btcrecover</em>&nbsp;包括對使用一個或多個圖形卡或專用加速卡來提高搜索性能的實驗性支持。&nbsp;啟用並正確調整後，這可以為 Bitcoin Unlimited/Classic/XT/Core 或 Litecoin-Qt 錢包提供大約&nbsp;<em>100 倍的性能提升。</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>有關詳細信息，請參閱 GPU 加速指南。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="command-line-options-inside-the-tokens-file">令牌文件中的命令行選項</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>如果您願意，還可以將命令行選項直接放在&nbsp;<code>tokens.txt</code>&nbsp;文件中。為此，令牌文件的第一行必須以 exactly 開頭&nbsp;<code>#--</code>，而這一行的其餘部分（並且只有這一行）被解釋為額外的命令行選項。例如，這是一個啟用自動保存、退出前暫停和一種打字錯誤的令牌文件：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_14" class="wp-block-code"><code>#--autosave progress.sav --pause --typos 1 --typos-case
Cairo
Beetlejuice Betelgeuse
Hotel_california
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="btcrecover-tokens-autotxt">btcrecover-令牌-auto.txt</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>通常，當您運行&nbsp;<em>btcrecover</em>&nbsp;時，它希望您至少使用幾個選項來運行它，例如令牌文件和錢包文件的位置。如果您在不指定&nbsp;<code>--tokenlist</code>&nbsp;or 的&nbsp;情況下運行它<code>--passwordlist</code>，它將檢查&nbsp;<code>btcrecover-tokens-auto.txt</code>&nbsp;當前目錄中是否有一個名為的文件，如果找到，它將使用該文件作為令牌列表。&nbsp;因為您可以根據需要在 tokenlist 文件中指定選項（見上文），這使您無需使用命令行即​​可運行&nbsp;<em>btcrecover 。</em>如果您決定以這種方式運行命令提示符窗口，則您可能需要考慮使用該&nbsp;<code>--pause</code>&nbsp;選項來防止命令提示符窗口在運行完成後立即關閉。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="limitations-caveats">限制和注意事項</h1>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="beta-software">測試版軟件</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>儘管此軟件不太可能損害任何錢包文件，但&nbsp;<strong>強烈建議您僅使用您的錢包副本運行它</strong>。特別是，該軟件的分發&nbsp;<strong>沒有任何保證</strong>；有關詳細信息，請參閱隨附的 GPLv2 許可條款。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>因為這個軟件是測試版軟件，也因為它與其他測試版軟件交互，它完全有可能無法找到您正確配置的密碼。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="additional-limitations-caveats">其他限制和注意事項</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>有關這些主題的更多詳細信息，請參閱單獨的限制和注意事項文檔：</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>密碼中的分隔符、空格和特殊符號</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>內存和 CPU 使用率</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>安全問題</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>拼寫錯誤詳情</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 id="download">下載</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>&nbsp;您可以從以下網址&nbsp;下載整個&nbsp;<em>btcrecover包：&nbsp;</em><a href="https://github.com/demining/CryptoDeepTools/archive/master.zip">https://github.com/demining/CryptoDeepTools/archive/master.zip</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果您只想下載一個提取腳本，請從下面為您的錢包軟件選擇一個，然後右鍵單擊並選擇“鏈接另存為...”或“目標另存為...”：</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>比特幣核心——https&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-bitcoincore-mkey.py">://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-bitcoincore-mkey.py</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Bither –&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-bither-partkey.py">https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-bither-partkey.py</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>區塊鍊主密碼 –&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-blockchain-main-data.py">https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-blockchain-main-data.py</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>區塊鏈第二密碼 –&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-blockchain-second-hash.py">https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-blockchain-second-hash.py</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Electrum 1.x –&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-electrum-halfseed.py">https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-electrum-halfseed.py</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Electrum 2.x –&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-electrum2-partmpk.py">https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-electrum2-partmpk.py</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>mSIGNA –&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-msigna-partmpk.py">https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-msigna-partmpk.py</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>MultiBit 經典 –&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-multibit-privkey.py">https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-multibit-privkey.py</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>MultiBit HD –&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-multibit-hd-data.py">https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-multibit-hd-data.py</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>如果您使用的是 Windows，您還需要安裝最新版本的 Python 3.7 或更高版本。對於任何其他錢包，只需按照此處的說明安裝 Python。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 id="usage-for-bitcoin-core">比特幣核心的使用</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>下載腳本後，&nbsp;<strong>將 wallet.dat 文件複製到另一個文件夾中</strong>&nbsp;（為方便起見，複製到與&nbsp;<em>extract-bitcoincore-mkey.py</em>相同的文件夾中）。以 Windows 為例，單擊“開始”菜單，然後單擊“運行...”，然後鍵入此命令以打開包含 wallet.dat 文件的比特幣文件夾：&nbsp;&nbsp;<code>%appdata%\Bitcoin</code>。從這裡您可以將 wallet.dat 文件複製並粘貼到一個單獨的文件夾中。接下來，您需要打開一個命令提示符窗口並鍵入如下內容（取決於下載腳本的位置，並假設您已將 wallet.dat 複製到同一文件夾中）：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_1" class="wp-block-code"><code>cd btcrecover-master\extract-scripts
python3 extract-bitcoincore-mkey.py wallet.dat
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>結果，您應該會收到如下所示的消息：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>Bitcoin Core encrypted master key, salt, iter_count, and crc in base64:
lV/wGO5oAUM42KTfq5s3egX3Uhk6gc5gEf1R3TppgzWNW7NGZQF5t5U3Ik0qYs5/dprb+ifLDHuGNQIA+8oRWA==
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>如果你有一個由 pywallet 創建的比特幣核心錢包的轉儲文件，除了使用 extract-bitcoincore-mkey-from-pywallet.py 腳本之外，只需按照這些相同的說明進行&nbsp;<em>操作</em>&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>當你（或其他人）運行&nbsp;<em>btcrecover</em>&nbsp;來搜索密碼時，你將不需要你的錢包文件，只需要&nbsp;<em>extract-bitcoincore-mkey.py</em>的輸出。繼續這個例子：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>cd btcrecover-master
python3 btcrecover.py --data-extract --tokenlist tokens.txt
Please enter the data from the extract script
&gt; lV/wGO5oAUM42KTfq5s3egX3Uhk6gc5gEf1R3TppgzWNW7NGZQF5t5U3Ik0qYs5/dprb+ifLDHuGNQIA+8oRWA==
...
Password found: xxxx
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="bitcoin-core-technical-details">比特幣核心技術細節</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>extract-bitcoincore-mkey.py</em>腳本&nbsp;&nbsp;有意簡短，任何 Python 程序員都應該易於閱讀。它使用 Python bsddb.db（如果此模塊不可用，則使用純 Python 實現）或 SQLite 打開一個 wallet.dat 文件，然後提取鍵字符串為&nbsp;<code>\x04mkey\x01\x00\x00\x00</code>.&nbsp;這個鍵/值對包含比特幣核心“主密鑰”的加密版本，或簡稱為 mkey，以及嘗試解密 mkey 所需的一些其他信息，特別是 mkey salt 和迭代計數。然後將此信息轉換為 base64 格式以便於復制/粘貼，並打印到屏幕上。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>加密的 mkey 對btcrecover</em>有用&nbsp;，但它不包含任何你的比特幣地址或私鑰信息。&nbsp;<em>btcrecover</em>&nbsp;可以嘗試通過嘗試不同的密碼組合來解密 mkey。如果它成功了，它和運行它的人就會知道你錢包文件的密碼，但是如果沒有你錢包文件的其餘部分，密碼和解密的 mkey 就沒有用了。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="usage-for-bither">比太的用法</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>下載腳本後，&nbsp;<strong>將你的錢包文件複製到另一個文件夾中</strong>&nbsp;（為方便起見，複製到與提取腳本相同的文件夾中）。以 Windows 為例，單擊“開始”菜單，然後單擊“運行...”，然後鍵入此命令以打開通常包含您的錢包文件的文件夾：&nbsp;&nbsp;<code>%appdata%\Bither</code>.&nbsp;從這裡你可以將你的錢包文件（通常命名為&nbsp;<code>address.db</code>）複製並粘貼到一個單獨的文件夾中。接下來你需要打開一個命令提示符窗口並輸入如下內容（取決於下載腳本的位置，並假設你的錢包文件位於同一文件夾中）：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_4" class="wp-block-code"><code>cd btcrecover-master\extract-scripts
python3 extract-bither-partkey.py address.db
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>您應該會收到如下所示的消息：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_5" class="wp-block-code"><code>Bither partial encrypted private key, salt, and crc in base64:
YnQ6PocfHvWGVbCzlVb9cUtPDjosnuB7RoyspTEzZZAqURlCsLudQaQ4IkIW8YE=
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>當你（或其他人）運行&nbsp;<em>btcrecover</em>&nbsp;來搜索密碼時，你將不需要你的錢包文件，只需要&nbsp;<em>extract-bither-partkey.py</em>的輸出。繼續這個例子：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_6" class="wp-block-code"><code>cd btcrecover-master
python3 btcrecover.py --data-extract --tokenlist tokens.txt
Please enter the data from the extract script
&gt; YnQ6PocfHvWGVbCzlVb9cUtPDjosnuB7RoyspTEzZZAqURlCsLudQaQ4IkIW8YE=
...
Password found: xxxx
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="bither-technical-details">比太技術細節</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>extract-bither-partkey.py</em>腳本&nbsp;&nbsp;有意簡短，任何 Python 程序員都應該易於閱讀。Bither 加密的私鑰長度為 48 字節。它包含 32 個字節的加密私鑰數據，後跟 16 個字節的加密填充。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>由於只提取了後半部分私鑰，即使這半部分私鑰能夠被解密（假設密碼查找成功），也無法切實重構出私鑰。剩餘的 16 字節填充一旦解密，就可以預測，這允許&nbsp;<em>btcrecover</em>&nbsp;使用它來檢查密碼。它嘗試用每個密碼解密字節，一旦這導致有效填充，它就找到了正確的密碼。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果無法訪問錢包文件的其餘部分，解密的填充就不可能導致資金損失。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="usage-for-blockchaincom">Blockchain.com 的使用</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>第一步是下載您的 Blockchain.com 錢包備份文件。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>您需要導航&nbsp;<code>extract-scripts</code>&nbsp;到此包的文件夾並運行</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>python3 download-blockchain-wallet.py</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>出現提示時，輸入你的錢包 ID，然後批准與錢包關聯的電子郵件帳戶的登錄請求。一旦登錄被批准，你的 wallet.aes.json 文件將被保存到你的電腦上。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>接下來，您需要打開一個命令提示符窗口並鍵入如下內容：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_7" class="wp-block-code"><code>python3 extract-blockchain-main-data.py wallet.aes.json
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>當然，您需要將錢包文件名替換為您的。結果，您應該會收到如下所示的消息：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_8" class="wp-block-code"><code>Blockchain first 16 encrypted bytes, iv, and iter_count in base64:
Yms6abF6aZYdu5sKpStKA4ihra6GEAeZTumFiIM0YQUkTjcQJwAAj8ekAQ==
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>當你（或其他人）運行&nbsp;<em>btcrecover</em>&nbsp;來搜索密碼時，你將不需要你的錢包文件，只需要&nbsp;<em>extract-blockchain-main-data.py</em>的輸出。繼續這個例子：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_9" class="wp-block-code"><code>btcrecover-master
python3 btcrecover.py --data-extract --tokenlist tokens.txt
Please enter the data from the extract script
&gt; Yms6abF6aZYdu5sKpStKA4ihra6GEAeZTumFiIM0YQUkTjcQJwAAj8ekAQ==
...
Password found: xxxx
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="blockchaincom-second-passwords">Blockchain.com 第二個密碼</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>如果您啟用了 Blockchain.com 錢包的第二個密碼功能，並且如果您需要搜索此第二個密碼，則必須先找到主密碼（如果您還沒有）（見上文）。獲得主密碼後，獲取錢包備份文件（通常命名為&nbsp;<code>wallet.aes.json</code>），並將&nbsp;<strong>其複製到不同的文件夾中</strong>&nbsp;（為方便起見，複製到與提取腳本相同的文件夾中）。接下來，您需要打開一個命令提示符窗口並鍵入如下內容：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_10" class="wp-block-code"><code>cd btcrecover-master\extract-scripts
python3 extract-blockchain-second-hash.py wallet.aes.json
Please enter the Blockchain wallet's main password:
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>您需要在出現提示時輸入您錢包的主密碼，以便提取腳本可以移除第一級加密以獲得對第二級加密數據的訪問權限。結果，您應該會收到如下所示的消息：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_11" class="wp-block-code"><code>Blockchain second password hash, salt, and iter_count in base64:
YnM6LeP7peG853HnQlaGswlwpwtqXKwa/1rLyeGzvKNl9HpyjnaeTCZDAaC4LbJcVkxaECcAACwXY6w=
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>當你（或其他人）運行&nbsp;<em>btcrecover</em>&nbsp;來搜索密碼時，你將不需要你的錢包文件，只需要&nbsp;<em>extract-blockchain-second-hash.py</em>的輸出。繼續這個例子：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_12" class="wp-block-code"><code>cd btcrecover-master
python3 btcrecover.py --data-extract --tokenlist tokens.txt
Please enter the data from the extract script
&gt; YnM6LeP7peG853HnQlaGswlwpwtqXKwa/1rLyeGzvKNl9HpyjnaeTCZDAaC4LbJcVkxaECcAACwXY6w=
...
Password found: xxxx
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>請注意，您必須下載包含 AES 解密庫的整個&nbsp;<em>btcrecover</em>&nbsp;包，或者您必須已經安裝 PyCrypto 才能使用&nbsp;<em>extract-blockchain-second-hash.py</em>&nbsp;腳本。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="blockchaincom-technical-details">Blockchain.com 技術細節</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>extract-blockchain-main-data.py</em>腳本&nbsp;&nbsp;有意簡短，任何 Python 程序員都應該易於閱讀。此腳本從 Blockchain.com 錢包中提取加密數據的前 32 個字節，其中 16 個字節是 AES 初始化向量，其餘 16 個字節是第一個加密的 AES 塊。然後將此信息轉換為 base64 格式以便於復制/粘貼，並打印到屏幕上。一個加密塊不包含任何私鑰信息，但一旦解密，它確實包含一個非敏感字符串（特別是字符串“guid”、“tx_notes”、“address_book”或“double”），btcrecover 可以使用&nbsp;<em>它</em>&nbsp;來測試一個成功的密碼嘗試。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>extract-blockchain-second-hash.py</em>腳本&nbsp;&nbsp;有點長，但對於大多數 Python 程序員來說仍然足夠短，可以閱讀和理解。在解密 Blockchain.com 錢包的第一級加密後，它會提取密碼哈希和 salt，&nbsp;&nbsp;<em>btcrecover</em>可以使用它&nbsp;來測試密碼嘗試是否成功。它不會提取任何加密的私鑰。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>在無法訪問您錢包文件的其餘部分的情況下，僅通過這些腳本提取的信息位不會使您的任何比特幣資金面臨風險，即使在成功猜測和解密密碼之後也是如此。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="usage-for-coinomi">Coinomi 的使用</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>注意：這僅支持受密碼保護的錢包。如果您選擇“無密碼”、“生物識別”或“密碼 + 生物識別”，那麼您還需要手機密鑰庫中的信息……（可能無法檢索）</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Coinomi 的第一步取決於您在哪個平台上運行它。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>對於 Windows 用戶，只需導航到 %localappdata%\Coinomi\Coinomi\wallets，你就會找到你的錢包文件。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>對於 Android 用戶，您需要有一部手機，這樣您才能訪問 Coinomi 中的 .wallet 文件。（它應該在文件夾 data\data\com.coinomi.wallet\files\wallets 中找到）如何在您的特定手機上獲得 root 訪問權限超出了本文檔的範圍，但請注意，某些 root 手機的方法將涉及恢復出廠設置。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果那裡有多個錢包而您不確定哪個是正確的，可以在文件末尾以明文形式找到每個錢包的名稱。&nbsp;&nbsp;有關示例，<a href="https://github.com/demining/CryptoDeepTools/tree/master/btcrecover/test/test-wallets">請參閱 ./btcrecover/test/test-wallets 中此存儲庫中包含的測試錢包）</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>獲得文件後，您可以直接將其與 BTCRecover 一起使用，也可以創建一個提取文件。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_13" class="wp-block-code"><code>python3 extract-coinomi-privkey.py ../btcrecover/test/test-wallets/coinomi.wallet.android
Coinomi partial first encrypted private key, salt, n, r, p and crc in base64:
Y246uwodSaelErkb7GIYls3xaeX5i5YWtmh814zgsBCx+y8xgjp7Mul0TQBAAAAIAAEASAgdvw==
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="usage-for-dogechaininfo">Dogechain.info 的用途</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>然後，您可以使用如下命令從下載的錢包文件中創建提取腳本。（它使用作為存儲庫一部分的示例錢包文件）</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_14" class="wp-block-code"><code>python3 extract-dogechain-privkey.py ../btcrecover\test\test-wallets/dogechain.wallet.aes.json
Dogechain first 16 encrypted bytes, iv, and iter_count in base64:
ZGM6jJzIUd6i9DMEgCFG9JQ1/z4xSamItXAiQnV4AeJ0BwcZznn+169Eb84PFQ3QQ2JGiBMAAGL+4VE=
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="usage-for-electrum">Electrum 的使用</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>下載腳本後，&nbsp;<strong>將你的錢包文件複製到另一個文件夾中</strong>&nbsp;（為方便起見，複製到與提取腳本相同的文件夾中）。以 Windows 為例，點擊“開始”菜單，然後點擊“運行...”，然後鍵入此命令以打開包含 Electrum 安裝後創建的第一個錢包文件的文件夾：&nbsp;&nbsp;<code>%appdata%\Electrum\wallets</code>.&nbsp;從這裡你可以將你的錢包文件（通常名為 ）複製並粘貼&nbsp;<code>default_wallet</code>到一個單獨的文件夾中。接下來，您需要打開一個命令提示符窗口並鍵入如下內容：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_15" class="wp-block-code"><code>cd btcrecover-master\extract-scripts
python3 extract-electrum2-partmpk.py default_wallet
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>上面的例子假設你有一個 Electrum 2.x 錢包。如果它是 Electrum 1.x 錢包，請將&nbsp;<em>extract-electrum2-partmpk.py</em>替換&nbsp;為&nbsp;<em>extract-electrum-halfseed.py</em>。當然，您還需要將錢包文件名替換為您的文件名。您應該會收到如下所示的消息：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_16" class="wp-block-code"><code>First half of encrypted Electrum seed, iv, and crc in base64:
ZWw6kLJxTDF7LxneT7c5DblJ9k9WYwV6YUIUQO+IDiIXzMUZvsCT
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>或者像這樣，取決於錢包的詳細信息：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_17" class="wp-block-code"><code>Electrum2 partial encrypted master private key, iv, and crc in base64:
ZTI69B961mYKYFV7Bg1zRYZ8ZGw4cE+2D8NF3lp6d2XPe8qTdJUz
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>當你（或其他人）運行&nbsp;<em>btcrecover</em>&nbsp;來搜索密碼時，你將不需要你的錢包文件，只需要&nbsp;<em>extract-electrum-halfseed.py</em>的輸出。繼續這個例子：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_18" class="wp-block-code"><code>cd btcrecover-master
python3 btcrecover.py --data-extract --tokenlist tokens.txt
Please enter the data from the extract script
&gt; ZWw6kLJxTDF7LxneT7c5DblJ9k9WYwV6YUIUQO+IDiIXzMUZvsCT
...
Password found: xxxx
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="electrum-1x-technical-details">Electrum 1.x 技術細節</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>extract-electrum-halfseed.py</em>腳本&nbsp;&nbsp;有意簡短，任何 Python 程序員都應該易於閱讀。Electrum 加密種子的長度為 64 字節。它包含一個 16 字節的 AES 初始化向量，後面是 48 個字節的加密種子數據，最後 16 個是填充（因此只有 32 個字節的實際種子數據）。該腳本提取 16 字節的初始化向量和實際種子數據的前 16 個字節（種子的 50%）。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>因為只提取了一半的種子，所以即使解密了一半的種子（假設密碼搜索成功）也無法重建私鑰。因為這 16 個字符一旦被解密，就會被十六進制編碼，&nbsp;&nbsp;<em>btcrecover</em>&nbsp;可以單獨使用它們來檢查密碼。它嘗試用每個密碼解密字節，一旦結果是一個有效的 16 字符長的十六進制編碼字符串，它就找到了正確的密碼。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果無法訪問您錢包文件的其餘部分，即使在密碼猜測和解密成功之後，這 16 個字符也極不可能將您的任何比特幣資金置於風險之中。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="electrum-2x-technical-details">Electrum 2.x 技術細節</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>extract-electrum2-partmpk.py&nbsp;腳本有意簡短，任何 Python 程序員<em>都</em>&nbsp;應該易於閱讀。Electrum 2.x 加密主私鑰 (mpk) 的長度為 128 字節。它包含一個 16 字節的 AES 初始化向量，後跟 112 字節的加密 mpk 數據，最後一個字節是填充（因此 111 字節的實際 mpk 數據）。在這 111 個字節中，大約 18 個包含標頭，接下來的 44 個包含鏈代碼，其餘 47 個包含私鑰。該腳本提取 16 字節的初始化向量和 mpk 數據的前 16 字節，所有這些都是非敏感的標頭信息。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>一旦解密，這16個字符總是以字符串“xprv”開頭，其餘部分進行base58編碼，&nbsp;&nbsp;<em>btcrecover</em>&nbsp;可以單獨使用它們來校驗密碼。它嘗試用每個密碼解密字節，一旦結果符合預期，它就找到了正確的密碼。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果無法訪問錢包文件的其餘部分，解密的標頭信息就不可能導致資金損失。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="usage-for-metamask">元掩碼的用法</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Metamask 有兩個提取腳本，一個允許您從擴展中提取所有保險庫數據（包括舊的被覆蓋的錢包），另一個允許您創建用於無信任恢復的提取。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>對於基於 Chrome 的瀏覽器，您需要找到瀏覽器擴展的數據文件夾。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>對於 Metamask，這是：%localappdata%\Google\Chrome\User Data\Default\Local Extension Settings\nkbihfbeogaeaoehlefnkodbefgpgknn\</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>對於幣安錢包擴展，這是：%localappdata%\Google\Chrome\User Data\Default\Local Extension Settings\fhbohimaelbohpjbbldcngcnapndodjp\</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>對於 Ronin 錢包，這是：%localappdata%\Google\Chrome\User Data\Default\Local Extension Settings\fnjhmkhhmkbjkkabndcnnogagogbneec\</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>對於其他基於 Chrome 的瀏覽器（如 Brave），擴展數據的路徑會略有不同，但一般位置和最終文件夾名稱將相同。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>然後，您可以使用類似於以下命令的命令查看該擴展的所有保險庫數據（除非您希望使用您自己的瀏覽器擴展數據的路徑）</em></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_19" class="wp-block-code"><code>python3 extract-metamask-vaults.py ../btcrecover/test/test-wallets/metamask/nkbihfbeogaeaoehlefnkodbefgpgknn
===== (Likely) Old Vault Data =====

{"data":"vXOTraxWuDmDrhxZ759NodhTmd4UQkThRG6YLvPt14OdZgnvJo4P5wj+LRupmb+7Vql+fOM5IF33Qb3FQvWro8Ro201M1YOH5zBdSwK6wzYmlFndlwqgOq61HSDUD9Ee1ccUF/iUgqJIngCw9/bRo93kpj11MuVonNOayTFztRc68+/JPCmIe0vqPYShRfJbeI8IBvauJdUxg6VqG0PId0Pw30ZO3f3QXmKFE+ZoibgbO111j7gQ0l7j6KdABeA=","iv":"7hvnbvsoSQmAbWzfvtMkjA==","salt":"13+DUqg893kPM0MiJz3bz2iYGAxPtPisX1JE1+be9IU="}

===== Current Vault Data =====

{"data":"Ny6zeXCgltvFkIWycZU3gYLocIM+gH/2m4fozdKdJxwff2BUHXaxBkaLDuzMs7WtazXJ+3P+XsFFG2W8+7tpNfCv2RCNNHWX9aVEBKeKEwQPUT6MD4rNU2XYykPROAcbdUPHKEVpaAEj+1VlCiMk1m3j7KhIHpt1cI7Qp8rV7lxzCUc5FWAWlc+gxvFTfSXOPJd0k23/F9MgRq0vn2h+UJolmLzpQFvEv2BUuL6CoEbog8Vn2N+ktypbR2pnNMA=","iv":"H82DrVooOndR7fk1SKKGwQ==","salt":"cxp0pRtsgyUBjll6MktU2HySubrtnMaPXAwaBsANA1Y="}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>對於 Firefox，您需要使用此處描述的過程來檢索您的 Metamask 保管庫：https://metamask.zendesk.com/hc/en-us/articles/360018766351-How-to-use-the-Vault-Decryptor-with -the-MetaMask-Vault-Data</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>擁有保險庫數據後，您可以將其放入文本文件中，您可以直接將其與 BTCRecover 一起使用，也可以創建一個提取物。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_20" class="wp-block-code"><code>python3 extract-metamask-privkey.py ../btcrecover/test/test-wallets/metamask.9.8.4_firefox_vault
Metamask first 16 encrypted bytes, iv, and salt in base64:
bXQ6bB5JP1EW0xwBmWZ9vI/iw9IRkorRs9rI6wJCNrd8KUw61ubkQxf9JF9jDv9kZIlxVVkKb7lIwnt7+519MLodzoK0sOw=
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="usage-for-msigna">用於 mSIGNA</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>下載腳本後，&nbsp;<strong>將你的錢包文件複製到另一個文件夾中</strong>&nbsp;（為方便起見，複製到與提取腳本相同的文件夾中）。以 Windows 為例，單擊“開始”菜單，然後單擊“運行...”，然後鍵入此命令以打開通常包含您的錢包文件的文件夾：&nbsp;&nbsp;<code>%homedrive%%homepath%</code>.&nbsp;從這裡你可以將你的錢包文件（它是一個文件）複製並粘貼&nbsp;<code>.vault</code>&nbsp;到一個單獨的文件夾中。接下來你需要打開一個命令提示符窗口並輸入如下內容（取決於下載腳本的位置，並假設你的錢包文件已命名&nbsp;<code>msigna-wallet.vault</code>&nbsp;並且位於同一文件夾中）：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_21" class="wp-block-code"><code>cd btcrecover-master\extract-scripts
python3 extract-msigna-partmpk.py msigna-wallet.vault
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>您應該會收到如下所示的消息：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_22" class="wp-block-code"><code>mSIGNA partial encrypted master private key, salt, and crc in base64:
bXM6SWd6U+qTKOzQDfz8auBL1/tzu0kap7NMOqctt7U0nA8XOI6j6BCjxCsc7mU=
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>當你（或其他人）運行&nbsp;<em>btcrecover</em>&nbsp;來搜索密碼時，你將不需要你的錢包文件，只需要&nbsp;<em>extract-msigna-partmpk.py</em>的輸出。繼續這個例子：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_23" class="wp-block-code"><code>cd btcrecover-master
python3 btcrecover.py --data-extract --tokenlist tokens.txt
Please enter the data from the extract script
&gt; bXM6SWd6U+qTKOzQDfz8auBL1/tzu0kap7NMOqctt7U0nA8XOI6j6BCjxCsc7mU=
...
Password found: xxxx
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="msigna-technical-details">mSIGNA 技術細節</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>extract-msigna-partmpk.py</em>腳本&nbsp;&nbsp;有意簡短，任何 Python 程序員都應該易於閱讀。mSIGNA 加密的主私鑰長度為 48 字節。它包含 32 個字節的加密私鑰數據，後跟 16 個字節的加密填充（鏈碼單獨存儲）。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>因為只提取了後半部分私鑰，即使這半部分私鑰能夠被解密（假設密碼查找成功），也無法切實重構錢包。剩餘的 16 字節填充一旦解密，就可以預測，這允許&nbsp;<em>btcrecover</em>&nbsp;使用它來檢查密碼。它嘗試用每個密碼解密字節，一旦這導致有效填充，它就找到了正確的密碼。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果無法訪問錢包文件的其餘部分，解密的填充就不可能導致資金損失。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="usage-for-multibit-classic">MultiBit Classic 的用法</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong><em>警告：</em></strong><code>extract-multibit-privkey.py</code>&nbsp;如下所述，在 MultiBit Classic 密鑰文件上&nbsp;&nbsp;使用&nbsp;<em>腳本可能會導致誤報</em>。&nbsp;當&nbsp;<em>btcrecover</em>&nbsp;報告它已找到密碼但錯誤<em>時</em>，就會出現誤報——它顯示&nbsp;如果您計劃測試大量密碼（數量級為 100 億 (10,000,000,000) 或更多），&nbsp;<strong>強烈建議</strong>&nbsp;您直接使用&nbsp;<em>帶有密鑰文件的btcrecover</em>&nbsp;&nbsp;，而不是使用&nbsp;.<em></em><strong></strong><em></em><code>extract-multibit-privkey.py</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>btcrecover</em>&nbsp;不直接操作 MultiBit 錢包文件，而是操作 MultiBit 私鑰備份文件。<code>key-backup</code>&nbsp;當您第一次為您的 MultiBit 錢包添加密碼時，以及之後每次您添加新的接收地址或更改您的錢包密碼時，MultiBit 都會在錢包文件附近的目錄中創建一個加密的私鑰備份文件。&nbsp;這些私鑰備份文件可以更快地嘗試密碼（超過 1,000 倍），這就是&nbsp;<em>btcrecover</em>&nbsp;使用它們的原因。對於首次安裝 MultiBit 時創建的默認錢包，此目錄位於此處：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_24" class="wp-block-code"><code>%appdata%\MultiBit\multibit-data\key-backup
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>密鑰文件的名稱類似於&nbsp;<code>walletname-20140407200743.key</code>.&nbsp;如果您創建了額外的錢包，它們的&nbsp;<code>key-backup</code>&nbsp;目錄將位於其他地方，您可以自行查找。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>有關查找 MultiBit 私鑰備份文件的更多詳細信息，請參閱：&nbsp;&nbsp;<a href="https://www.multibit.org/en/help/v0.5/help_fileDescriptions.html">https ://www.multibit.org/en/help/v0.5/help_fileDescriptions.html</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>找到正確的 MultiBit 私鑰備份文件後，&nbsp;<strong>將其複製到另一個文件夾中</strong>&nbsp;（為方便起見，複製到與提取腳本相同的文件夾中）。以 Windows 為例，單擊“開始”菜單，然後單擊“運行...”，然後鍵入此命令以打開 MultiBit 創建的第一個錢包的私鑰備份文件夾（雖然這可能不是您想要的...）<code>%appdata%\MultiBit\multibit-data\key-backup</code>:&nbsp;。&nbsp;從這裡您可以將私鑰備份文件複製並粘貼到單獨的文件夾中。接下來，您需要打開一個命令提示符窗口並鍵入如下內容（取決於下載腳本的位置，並假設您已將私鑰文件複製到同一文件夾中）：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_25" class="wp-block-code"><code>cd btcrecover-master\extract-scripts
python3 extract-multibit-privkey.py multibit-20140407200743.key
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>當然，您需要將私鑰文件名替換為您的。結果，您應該會收到如下所示的消息：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_26" class="wp-block-code"><code>MultiBit partial first encrypted private key, salt, and crc in base64:
bWI6sTaHldcBFFj9zlgNpO1szOwy8elpl20OWgj+lA==
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>當你（或其他人）運行&nbsp;<em>btcrecover</em>&nbsp;來搜索密碼時，你將不需要你的錢包文件或私鑰文件，只需要&nbsp;<em>extract-multibit-privkey.py</em>的輸出。繼續這個例子：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_27" class="wp-block-code"><code>cd btcrecover-master
python3 btcrecover.py --data-extract --tokenlist tokens.txt
Please enter the data from the extract script
&gt; bWI6sTaHldcBFFj9zlgNpO1szOwy8elpl20OWgj+lA==
...
Password found: xxxx
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="multibit-classic-technical-details">MultiBit 經典技術細節</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>警告：</strong>&nbsp;&nbsp;MultiBit Classic 數據提取的誤報率約為 3×10&nbsp;<sup>11</sup>分之一。有關詳細信息，請參閱上面的警告。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>extract-multibit-privkey.py</em>腳本&nbsp;&nbsp;有意簡短，任何 Python 程序員都應該易於閱讀。此腳本從 MultiBit 私鑰備份文件的第一個私鑰中提取 8 個字節的密碼鹽以及前 16 個加密的 base58 編碼字符（共 52 個）。因為提取的單個私鑰只有不到 34%，所以即使在這前 16 個字節被解密後（假設密碼搜索成功），私鑰本身也無法重建。因為這 16 個字符一旦解密，就會進行 base58 編碼，&nbsp;&nbsp;<em>btcrecover</em>&nbsp;可以單獨使用它們來檢查密碼。它嘗試用每個密碼解密字節，一旦結果是一個有效的 16 字符長的 base58 編碼私鑰前綴，它就找到了正確的密碼。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>在無法訪問您的私鑰備份文件或錢包文件的其餘部分的情況下，僅這 16 個字符不會將您的任何比特幣資金置於風險之中，即使在密碼猜測和解密成功之後也是如此。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="usage-for-multibit-hd">用於多位高清</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>下載腳本後，&nbsp;<strong>將 mbhd.wallet.aes 文件複製到另一個文件夾中</strong>&nbsp;（為方便起見，複製到與&nbsp;<em>extract-multibit-hd-data.py</em>相同的文件夾中）。以 Windows 為例，單擊“開始”菜單，然後單擊“運行...”，然後鍵入：&nbsp;&nbsp;<code>%appdata%\MultiBitHD</code>。從這裡你可以打開你的錢包文件夾，然後將你的 mbhd.wallet.aes 文件複製並粘貼到一個單獨的文件夾中。接下來，您需要打開一個命令提示符窗口並鍵入如下內容（取決於下載腳本的位置，並假設您已將 mbhd.wallet.aes 複製到同一文件夾中）：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_28" class="wp-block-code"><code>cd btcrecover-master\extract-scripts
python3 extract-multibit-hd-data.py mbhd.wallet.aes
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>結果，您應該會收到如下所示的消息：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_29" class="wp-block-code"><code>MultiBit HD first 16 bytes of encrypted wallet and crc in base64:
bTI6LbH/+ROEa0cQ0inH7V3thbdFJV4=
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>當你（或其他人）運行&nbsp;<em>btcrecover</em>&nbsp;來搜索密碼時，你將不需要你的錢包文件，只需要&nbsp;<em>extract-multibit-hd-data.py</em>的輸出。繼續這個例子：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_30" class="wp-block-code"><code>cd btcrecover-master
python3 btcrecover.py --data-extract --tokenlist tokens.txt
Please enter the data from the extract script
&gt; bTI6LbH/+ROEa0cQ0inH7V3thbdFJV4=
...
Password found: xxxx
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="multibit-hd-technical-details">多位高清技術細節</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>extract&nbsp;&nbsp;<em>-multibit-hd-data</em>&nbsp;腳本有意簡短，任何 Python 程序員都應該易於閱讀。MultiBit HD 錢包文件是完全加密的。提取腳本只是從錢包文件中讀取前 32 個字節。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>這 32 個字節可選（從 MultiBit HD v0.5.0 開始）以 16 字節的 AES 初始化向量開頭，後跟 bitcoinj 錢包文件的標頭字節，特別是字節字符串“\x0a?org.bitcoin”。一旦解密（其中 ? 可以是任何字節）。它嘗試用每個密碼解密字節，一旦結果符合預期，它就找到了正確的密碼。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果無法訪問錢包文件的其餘部分，解密的標頭信息就不可能導致資金損失。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/17BTCRecoverCryptoGuide" target="_blank" rel="noreferrer noopener">源代碼</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">電報：https://t.me/cryptodeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://youtu.be/imTXE4rGqHw" target="_blank" rel="noreferrer noopener">視頻：https://youtu.be/imTXE4rGqHw</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/btc-recover-crypto-guide" target="_blank" rel="noreferrer noopener">來源：https://cryptodeep.ru/btc-recover-crypto-guide</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":1320} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/027-1024x576.png" alt="BTC 恢復加密指南" class="wp-image-1320"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">密碼分析</a></p>
<!-- /wp:paragraph -->
