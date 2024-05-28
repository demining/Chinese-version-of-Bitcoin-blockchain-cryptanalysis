<!-- wp:embed {"url":"https://www.youtube.com/embed/NrQ3oNxlrlU","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/NrQ3oNxlrlU
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>在上一篇文章：<a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">“區塊鏈攻擊向量和智能合約漏洞”</a>中，我們回顧了所有已知的區塊鏈攻擊，在本文中，我們將再次討論加密威脅，我們將討論識別<a href="https://cryptodeeptech.ru/cold-and-hot-wallets" target="_blank" rel="noreferrer noopener">冷錢包和熱錢包的漏洞錢包</a>。區塊鍊是由去中心化賬本和非常安全的數據結構組成的底層技術層，因為有很多分佈式節點參與共識算法。為了破解區塊鏈，黑客應該利用許多去中心化節點中的漏洞。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>區塊鏈的基本安全假設是不可能破解這麼多節點來改變區塊鏈的狀態。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2><strong>如果區塊鏈技術如此安全，它怎麼可能被黑客入侵？</strong></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>該技術的致命弱點是機構用戶的中心化性質，這些用戶為他們的客戶管理著大量的加密資產（金錢），而唯一留在金錢和黑客之間的就是&nbsp;<em>私鑰</em>。私鑰應用於在區塊鏈交易上簽名，就像使用手動簽名簽署傳統支票一樣。如果有人竊取了機構的私鑰，他們可以代表他們創建交易並竊取資金。與銀行系統不同——一旦創建了被黑客入侵的交易，就無法逆轉——錢實際上是被盜了。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>為什麼存儲和保護您的私鑰很重要？</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>持有私鑰的人可以完全控制與該私鑰相關的資產。由於區塊鏈交易是即時且不可撤銷的，因此用戶希望將其私鑰保密。私鑰只生成一次，因此將私鑰放錯地方實際上會使與該地址關聯的所有加密資產變得無用。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>儘管尚未定義最佳託管方案，但毫無疑問，私鑰的控制是最重要的問題。事實上，私鑰本質上就是真正的資產。它的內在屬性和力量意味著沒有辦法真正無一例外地保護它。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>冷錢包</strong>&nbsp;“機構保管人的金庫”是最初存儲比特幣或其他加密貨幣的硬件設備，與互聯網隔離的設備。理論上，據報導冷錢包解決方案是存儲加密貨幣的最安全方式。一些加密貨幣用戶更喜歡將他們的&nbsp;<a href="https://cryptodeeptech.ru/cold-and-hot-wallets/#/news-room/what-is-asset-management/">數字資產</a>保存&nbsp;在物理“錢包”中，通常是一種看起來像 U 盤的設備；它們只能通過直接插入計算機來訪問，並且需要互聯網連接才能讓用戶訪問和移動他們的加密貨幣資金。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1804} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/hot-vs-cold-wallet-1-1024x916.png" alt="冷熱錢包發現漏洞並消除對區塊鏈的各種攻擊" class="wp-image-1804"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>有幾種流行的商業用途冷錢包，例如 Trezor、Ledger Nano S，對於企業和機構投資者，一些其他設備結合使用：&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>USB</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>以太網</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>SD卡</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>外部拇指驅動器</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>帶 HSM 的專用氣隙機器</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>與上述硬件相關的問題是可用性，要訪問加密資產，您需要將冷錢包連接到計算機，因此它會暴露在互聯網上。通過這樣做，您將通過 Internet 連接破壞冷錢包系統，從而使其暴露於<a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">潛在的攻擊媒介</a>並最終導致潛在的網絡盜竊。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>使用冷錢包存儲是一項必要的安全預防措施，尤其是在處理大量比特幣和其他加密資產時。例如，加密貨幣交易所或加密貨幣基金託管人通常會提供即時提款，並且可能負責數十萬比特幣和其他加密資產。為了最大限度地降低黑客在安全漏洞中竊取全部儲備金的能力，金融服務運營商將遵循標準協議，將大部分儲備金保存在冷庫中，同時持有較小比例的日常&nbsp;<em>可用</em>資產貿易活動。&nbsp;&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>從本質上講，他們不會將大部分數字資產的私鑰存儲在他們的服務器或任何其他連接的計算機上。服務器上保存的唯一金額是支付預期客戶提款所需的最低金額。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>用於保護數字資產私鑰的方法：</strong></p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>使用強密碼保護錢包的數據加密</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>在計算機崩潰或欺詐的情況下備份數字錢包</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>冷錢包並不真正安全，因為在某些時候，它們需要發送資金，而這樣做依賴於雙向通信並連接到互聯網。此時它們可能會受到威脅並感染惡意數據並且<a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">極易受到攻擊</a>。因此，所有的冷錢包都變成了熱錢包，打破了機構託管人的整體安全理論。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>如今，熱錢包</strong>&nbsp;發揮著重要作用，因為它們能夠輕鬆訪問資金並處理自動交易，但熱錢包的私鑰存儲方式要求它們始終連接到互聯網。有不同類型的熱錢包採用不同的方法來存儲私鑰。從數學的角度來看，一些在不同參與者之間複製私鑰，另一些在參與者之間劃分一個私鑰。換句話說，今天的熱錢包通過分發私鑰來解決安全風險。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>熱錢包參與者保持對其私鑰的控制，因此熱錢包中的加密貨幣資產仍處於持有者的控制之下。但是，這些資產仍然容易受到黑客攻擊，因為惡意個人或團體可以訪問您的計算機或智能手機，理論上也可以通過訪問私鑰來耗盡您的錢包。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>熱錢包的主要優勢在於它可以用於自動和快速訪問交易。希望實際使用他們的加密貨幣資產進行購買的個人可能會選擇使用熱錢包，例如，因為該錢包中的資產可以通過互聯網轉移，而且一般來說，加密資產的數量具有足夠高的價值，因此黑客投入竊取的時間和金錢是不值得的。另一方面，熱錢包肯定容易受到安全漏洞的影響，因為它們可以持續訪問互聯網。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>不同類型的熱錢包都將私鑰存儲在連接互聯網的應用程序中：</strong></p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>Basic Hot wallet – 私鑰直連互聯網&nbsp;</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Multisig Native Wallet – 複製私鑰 – 您只需要讓兩個參與者妥協即可獲得訪問權限</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>多方計算 (MPC) – 在 2-5 名參與者之間分發私鑰</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>如果我們看一下 Multisig 方法，即使有 2-3 個人或實體必須確認特定交易，黑客組織也會在機構目標上花費數百萬美元，他們只需要三分之二的<a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">攻擊向量來破壞安全性。</a>黑客組織願意這樣做，因為他們將獲得數億美元的被盜加密資產。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>即使是 MPC 方法也容易受到各種攻擊媒介的攻擊。使用 MPC 方法，多個不信任的計算機可以各自對更大數據集的自己獨特的片段進行計算，以共同產生所需的共同結果，而無需任何一個節點知道其他片段的詳細信息。執行交易的私鑰是集體產生的價值；MPC 的支持者堅持認為，在任何時候都不會由一台計算機負責實際的密鑰。&nbsp;<a href="https://cryptodeeptech.ru/cold-and-hot-wallets/#/product/">據說基於 MPC 的錢包</a>&nbsp;是&nbsp;市場上任何硬件或<a href="https://en.bitcoin.it/wiki/Multisignature">&nbsp;多重簽名錢包的更好解決方案。</a>它們在數學上被證明更安全，完全脫鏈，提供更高的靈活性並且通常與賬本無關。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>不幸的是，即使在多個設備上都有碎片，它仍然不是一個完全安全的解決方案，因為老練的黑客可能會在機器集群中逗留足夠長的時間來跟踪和重建密鑰。如果他們設法破壞一台員工機器或服務器，他們將能夠在網絡中橫向移動並破壞作為簽名方法一部分的其他設備。所以這也可以被證明是錯誤的，因為黑客組織足夠老練，可以找到這種方法中的漏洞，並且願意花費數百萬來竊取數十億。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>使用上述解決方案可以從根本上防止流氓員工在現場、冷藏設施或完全由公司管理的任何硬件設備中竊取密鑰。有 mpc 錢包提供商試圖限制攻擊者或流氓員工進入單個網絡並收集他們授權和簽署非法交易所需的所有加密信息，但是，這種解決方案也不是 100% 安全的，只是當數十億美元受到威脅時，<a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">減輕攻擊媒介就不是一種選擇。</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2><strong>行業為什麼要關心？&nbsp;</strong></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>截至撰寫本文時，加密貨幣的總市值已超過 2180 億美元，現已進入第 10 個年頭。在過去的 10 年中，出現了許多著名的黑客攻擊事件。所有託管大量加密資產的機構都有責任對其投資者負責，以確保在整個企業中部署最強大的安全選項。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>此外，黑客攻擊還會導致其他各種網絡損害</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>資產盜竊——不可逆轉</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>名譽受損</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>竊取私人客戶數據</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>失業</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>關閉業務</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>但那是另一篇文章……</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>儘管市場上存在很大的波動，部分是由 FOMO 和媒體炒作驅動的，但重要的是要承認一個主要因素是數字資產的安全性，這可能會影響加密貨幣的價值或交易所資產估值從根本上改變整個生態系統。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>要點：</h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>熱錢包始終連接到互聯網；因此它很容易受到在線攻擊——但它更適合日常使用。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>冷錢包大多沒有連接到互聯網；因此，它不太容易受到在線攻擊——但對於日常使用來說不太方便。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>選擇錢包時，您應該考慮安全性、便利性、費用、支持的幣種和保險因素。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>如果您打算購買數字資產，決定如何以及在何處存儲它們不是一種選擇，而是一種必要。與法定貨幣不同，&nbsp;<a href="https://www.coingecko.com/" target="_blank" rel="noreferrer noopener">加密貨幣</a>&nbsp;存在於&nbsp;<a href="https://www.coingecko.com/learn/what-is-a-blockchain" target="_blank" rel="noreferrer noopener">區塊鏈</a>上&nbsp;，需要一個稱為錢包的適當存儲平台。<a href="https://www.coingecko.com/learn/what-are-public-and-private-keys" target="_blank" rel="noreferrer noopener">這些錢包讓您可以通過公鑰和私鑰</a>訪問您的加密資產&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>您使用公鑰發送和接收加密貨幣，使用私鑰確認交易並證明對加密錢包的所有權。您可以將您的公鑰視為您的銀行帳號，將您的私鑰視為您的密碼。熱錢包和冷錢包的主要區別是前者在線存儲私鑰，而後者離線存儲。&nbsp;&nbsp;&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>本文深入探討了熱錢包和冷錢包的爭論、選擇錢包時的注意事項，以及使用冷熱錢包來管理您的加密資產組合。&nbsp;&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="1">什麼是熱錢包？</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>熱錢包是一種在線存儲公鑰和私鑰的軟件錢包。當連接到互聯網時，您可以通過計算機或智能手機訪問它。熱錢包在日常使用中更方便，因為您無需插拔它們即可使用它們——您只需要一個互聯網連接。它們通常還可以免費下載和使用，並配有易於使用的界面，任何人都可以輕鬆上手。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>熱錢包很<a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">容易受到攻擊，</a>因為它們在線存儲公鑰和私鑰，這會使您面臨網絡釣魚和其他&nbsp;<a href="https://www.coingecko.com/learn/complete-guide-to-bitcoin-scams" target="_blank" rel="noreferrer noopener">詐騙</a>等風險。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>熱錢包的類型</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>有兩種類型的熱錢包——基於交易所的熱錢包，用戶在中心化交易所開立賬戶，該交易所充當用戶資金的託管人，以及非託管軟件熱錢包。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="2">基於交易所的錢包</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>基於交易所的錢包是中心化交易所的一部分。中心化交易所是保管用戶地址私鑰的監管機構。這意味著此類託管金融平台的客戶並未完全託管其資產，因為這些資產存放在該機構持有的冷熱錢包中。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>不幸的是，這使用戶面臨交易所從事某些導致客戶資金損失的活動的風險，正如 2022 年 11 月 FTX 的案例所示。展望未來，整個行業都在推動提高透明度並通過引入&nbsp;<a href="https://www.coingecko.com/learn/what-is-proof-of-reserves-por" target="_blank" rel="noreferrer noopener">儲備證明</a>，讓託管機構對其客戶的代幣負責。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>雖然中心化交易活動總體下降，但基於交易的錢包仍然很受歡迎，尤其是在散戶投資者中，因為它們使用戶可以輕鬆地用法定貨幣買賣加密貨幣。此外，如果您丟失了登錄詳細信息，可以通過聯繫交易所的客戶服務來恢復對您錢包的訪問權限。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1786} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/Main-Table-4-1024x673.png" alt="冷熱錢包發現漏洞並消除對區塊鏈的各種攻擊" class="wp-image-1786"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3 id="3">非託管軟件熱錢包</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>非託管軟件熱錢包可以通過手機、瀏覽器或桌面應用程序訪問。大多數時候，它們在這三者中都可用。對於這些熱錢包，用戶對自己的私鑰負責並完全控制自己的資金。雖然這意味著您的資金在發生銀行擠兌時是安全的，因為它們沒有存儲在託管機構中，但如果您丟失了助記詞，您將無法再訪問您的錢包和存儲在其中的加密貨幣。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4 id="4">什麼是種子短語？</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>種子短語也稱為恢復短語。這是一個包含 12、18 或 24 個單詞的隨機列表，可用作恢復鏈上加密資產的主密鑰。種子短語生成私鑰，私鑰又用於生成公鑰。錢包軟件通常會生成一個種子短語，指示用戶在安全存儲之前將其寫下來。種子短語充當解鎖用戶對其錢包的訪問權限的主密鑰，因此它必須安全存儲並且永遠不要在線。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>在存儲您的種子短語時，不要只是將其寫在一張紙上，它會隨著時間的推移而褪色或可能被水和火破壞。相反，使用加密鋼來記錄您的助記詞，並製作多份副本作為備份。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>切勿將您的助記詞存儲在密碼管理器或在線任何地方或您的設備上。這包括不給它拍照，或者把它放在谷歌文檔或筆記中。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1788} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/content_Main_Table_12.png" alt="冷熱錢包發現漏洞並消除對區塊鏈的各種攻擊" class="wp-image-1788"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2 id="5">熱錢包的例子</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3>MetaMask – 探索以太坊生態系統的最佳選擇&nbsp;</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><a href="https://www.coingecko.com/learn/complete-beginners-guide-to-metamask" target="_blank" rel="noreferrer noopener">MetaMask</a>&nbsp;是加密領域最受歡迎的熱錢包之一，支持所有與&nbsp;<a href="https://www.coingecko.com/learn/ethereum-virtual-machine-evm" target="_blank" rel="noreferrer noopener">EVM 兼容的</a>&nbsp;代幣。它易於使用，可在桌面和移動設備上使用。此外，它還具有額外的內置功能，用於&nbsp;&nbsp;跨網絡交換、發送和接收加密貨幣以及收集<a href="https://www.coingecko.com/en/nft" target="_blank" rel="noreferrer noopener">不可替代的代幣 (NFT) 。</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>基於交易所的錢包 – Easy Fiat On-Ramp</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>基於交易所的熱錢包類似於 MetaMask，主要支持桌面和移動設備。基於交易所的錢包連接到大多數銀行以確保輕鬆入職，允許新的加密貨幣用戶直接使用他們的銀行賬戶而不是經紀人購買加密貨幣。您可能（也可能不需要）在交易所開立賬戶才能使用他們的錢包服務。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>然而，如上所述，這些基於交易所的錢包是託管的，這意味著交易所本質上持有你的私鑰和你的硬幣，向你保證你可以在需要時提取你的硬幣。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>出埃及記 - 最適合桌面</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><a href="https://www.exodus.com/" rel="noreferrer noopener" target="_blank">Exodus</a>&nbsp;是最好的桌面熱錢包，因為它具有高交易速度、易用性和提供的多種客戶端功能。它是加密領域最具視覺吸引力和直觀的錢包之一。它最初是一個僅限桌面的錢包，但已經擴展到支持移動設備。然而，適用於 Windows、Linux 和 Mac 操作系統的 Exodus 桌面應用程序仍然是錢包的主要產品。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="6">什麼是冷錢包？&nbsp;</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>冷錢包或硬件錢包是一種離線存儲私鑰的物理設備，價格在 50 美元到 250 美元之間。冷錢包是最安全的加密錢包類型，因為它們沒有連接到互聯網，因此不太可能被黑客入侵（除非他們可以訪問您的私鑰和硬件錢包）。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>硬件錢包是類似於 U 盤或硬盤驅動器的物理設備，它們通過在設備本身上存儲您的密碼、PIN 和私鑰來工作。事實上，即使計算機感染了惡意軟件，冷錢包仍然是安全的，因為它的私鑰保存在永遠不會連接到互聯網的芯片中。因此，即使您的計算機遭到黑客攻擊或您的在線錢包遭到破壞，您的硬幣仍然是安全的……除非您的密碼和設備被盜。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>然而，由於冷錢包是實物，這也使它們面臨因粗心處理而丟失的風險。如果您的加密硬件錢包不幸丟失或被盜，您可以使用助記詞重新生成您的私鑰。因此，請記住確保您的助記詞安全、離線並保存在硬拷貝上。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>由於冷錢包是長期加密存儲的理想選擇，因此它們比交易資金更適合存放加密貨幣。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1790} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/Main-Table-9-1024x673.png" alt="冷熱錢包發現漏洞並消除對區塊鏈的各種攻擊" class="wp-image-1790"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3 id="7">&nbsp;</h3>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3>賬本</h3>
<!-- /wp:heading -->

<!-- wp:image {"id":1792} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/content_image_265.png" alt="冷熱錢包發現漏洞並消除對區塊鏈的各種攻擊" class="wp-image-1792"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>資料來源：Ledger Nano X</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://gcko.io/ledger">Ledger</a>&nbsp;是最受歡迎的加密硬件錢包提供商之一，提供 Ledger Nano X、Ledger Nano S 和 Ledger Nano S plus 錢包。這些設備的大小與拇指驅動器差不多，運行在稱為區塊鏈開放分類帳操作系統的分類帳操作系統上。它還具有內置清晰的 OLED 顯示屏界面，以及兩個用於確認交易的導航按鈕。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Ledger 配有 Ledger Live 移動應用程序和高級別的安全性，其安全元件芯片用於存儲加密數據。他們的旗艦型號 Ledger Nano X 提供超過 5,500 種代幣的加密貨幣兼容性。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>安全的</h3>
<!-- /wp:heading -->

<!-- wp:image {"id":1793} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/10712964857906.jpg" alt="冷熱錢包發現漏洞並消除對區塊鏈的各種攻擊" class="wp-image-1793"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://shop.trezor.io/product/trezor-model-t?offer_id=15&amp;aff_id=1143">Trezor</a>&nbsp;是另一個著名的硬件錢包，提供 Trezor One 和 Trezor Model T。Trezor Model T 兼容 1,456 種硬幣和代幣，並配備桌面、瀏覽器和 Android Trezor Suite。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Trezor Suite 是一個用戶界面，可讓您搜索和購買加密貨幣、管理您的資產並安全地發送加密貨幣。雖然這可以改善用戶體驗，但在您使用支持 Internet 的設備時可能會引入安全漏洞。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="8">選擇錢包時的注意事項</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>根據您的需要，您可以選擇熱錢包、冷錢包或兩者兼而有之。我們在這張表中總結了上述三種類型的錢包如何相互比較：</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1794} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/Main-Table-11-1024x436.png" alt="冷熱錢包發現漏洞並消除對區塊鏈的各種攻擊" class="wp-image-1794"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3>安全</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>選擇加密錢包時，安全性是一項核心功能。區塊鏈技術以其安全和不變的特性而聞名；確保您的錢包具有最好的安全功能是必要的。冷錢包比熱錢包更安全，因為它們並不總是連接到互聯網，並且會面臨潛在的網絡安全風險，例如網絡釣魚或其他黑客攻擊和詐騙。此外，請確保您的錢包具有雙因素身份驗證 (2FA) 功能，以防止未經授權訪問您的資產。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>方便&nbsp;</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>由於冷錢包離線存儲私鑰，因此它們涉及插入物理設備並鏈接到基於網絡的賬戶以轉移資金。另一方面，熱錢包在線；因此，它們更易於用於日常交易，例如日內交易。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>額外交易費用</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>無論您使用哪個錢包，您仍然需要支付汽油費。但是，基於交易所的錢包可能會收取額外費用，該費用源自汽油價格，但如果您持有或質押交易所的原生代幣，則可以免除此費用。在下載或購買任何錢包之前，請先檢查他們的服務費用。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>支持的硬幣</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>您打算使用的錢包可能不支持您要投資的幣種。有些錢包只支持一種幣種！以&nbsp;<a href="https://wallet.mycelium.com/" rel="noreferrer noopener" target="_blank">Mycelium</a>為例。儘管具有出色的功能，但它僅支持比特幣。因此，請務必在使用前檢查錢包支持的硬幣和代幣列表，以免失望。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>保險</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>一些託管人為因技術問題或盜竊而遭受損失的用戶提供資產保險。保管人的保險政策各不相同，但建議選擇與金融機構合作為您的資產提供保險的保險政策。例如，幣安為美國客戶提供高達 250,000 美元的美元存款保險。它已與&nbsp;<a href="https://www.fdic.gov/" rel="noreferrer noopener" target="_blank">聯邦存款保險公司 (FDIC)</a>合作&nbsp;實施該政策。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="9">使用冷熱錢包管理您的加密資產組合</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>熱錢包比冷錢包更方便日常使用。另一方面，冷錢包比熱錢包保證最大的安全性。這兩個錢包都支持廣泛的加密貨幣。因此，適合您的理想錢包取決於您是否將資金安全置於定期使用錢包的便利性之上。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>您可以通過結合這兩種方法來享受這兩種好處。例如，您可以將一小部分資金存放在熱錢包中用於交易目的，並將其餘資金存放在冷錢包中作為長期投資。&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>作為區塊鍊網絡的參與者，o 方可以依靠所謂的“錢包”來管理其賬戶和與區塊鏈的交互。一方有多個密鑰。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>問題</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>一方錢包容易受到<a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">惡意攻擊</a>導緻密鑰被盜。如果遭到破壞，攻擊者可以使用密鑰以該方的身份發出交易。如何防止密鑰洩露？</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>力量：</strong></p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>安全 – 密鑰存儲在設備中時可能會被黑客攻擊，尤其是當連接到 Internet 時。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>可用性——一些密鑰可能被區塊鏈參與者頻繁使用，而其他密鑰可能不經常使用或可能充當備份。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><strong>解決方案</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>用戶可以選擇將密鑰存儲在 2 種類型的錢包中，即&nbsp;<em>熱錢包</em>&nbsp;和&nbsp;<em>冷錢包</em>。熱錢包通常是指連接到互聯網的區塊鍊網關。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://i0.wp.com/research.csiro.au/blockchainpatterns/wp-content/uploads/sites/249/2020/06/hot-cold.png?ssl=1"></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p id="caption-attachment-311">冷熱錢包存儲模式</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>通過熱錢包，用戶可以直接向區塊鏈發起交易。因此，熱錢包通常持有經常使用的密鑰。冷錢包是指保持離線狀態以最大程度減少潛在攻擊的密鑰存儲。因此，土塊錢包通常包含很少使用的密鑰。冷錢包可以是任何與互聯網斷開連接的設備，甚至可以是記錄實體密鑰的紙張。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>當需要存儲在冷錢包中的密鑰來簽署交易時，用戶需要將冷錢包設備連接到計算機並將密鑰複製粘貼到相關字段中。還可以根據使用頻率（例如，最近最少使用和最常使用）在 2 個錢包之間自動遷移密鑰。此外，可以將某個密鑰標記為關鍵，以便它主要保留在冷錢包中。當需要簽署交易時，可以將其複製到熱錢包。然而，一旦交易被簽署，它就應該從熱錢包中刪除。在某些應用程序設置、區塊鏈平台和錢包實現中，也可以完全在冷錢包上簽署交易，並使用熱錢包將簽署的交易發布/中繼到區塊鏈。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>好處</strong></p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>安全存儲——冷錢包與互聯網隔離；因此，為密鑰提供安全存儲。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>可用性——這種安全存儲還保留了密鑰的可用性，因為一旦冷錢包連接到互聯網（直接或通過中間件），一方就可以使用這些密鑰。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><strong>缺點</strong></p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>安全——熱錢包在線存儲一個人的秘密密鑰，因此更容易被盜。一旦連接到熱錢包以復制/遷移密鑰，冷錢包就會變得更容易受到攻擊。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>可用性——冷錢包比熱錢包更安全，但使用起來不太方便，因為用戶必須連接到冷錢包。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><strong>相關模式</strong></p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>在&nbsp;<a href="https://research.csiro.au/blockchainpatterns/master-sub-key/">主子密鑰生成</a>&nbsp;模式中，主密鑰可以保存在冷錢包中，子密鑰可以保存在熱錢包中。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://research.csiro.au/blockchainpatterns/general-patterns/self-sovereign-identity-patterns/key-management-patterns/key-sharding/">密鑰分片</a>&nbsp;模式可用於錢包應用程序以拆分和合併密鑰以最大限度地減少其危害。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://research.csiro.au/blockchainpatterns/general-patterns/self-sovereign-identity-patterns/update-by-delegates/">當集成到錢包應用程序中時，委託列表</a>模式中的預定義委託&nbsp;&nbsp;可以替換已洩露密鑰的密鑰所有權。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><strong>已知用途</strong></p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://www.myetherwallet.com/">MyEtherWallet</a>&nbsp;是一款帶有圖形界面的熱錢包，用於以太坊的即時支付和提款。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://trezor.io/">Trezor</a>&nbsp;是一種加密貨幣硬件錢包，旨在存儲和加密用戶的硬幣、密碼和其他數字密鑰。它是一台具有獨立內存以保存所有私人數據的單一用途計算機。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.ledger.com/">Ledger</a>&nbsp;提供硬件錢包產品，將用戶的私鑰存儲在安全的硬件設備中，保護加密貨幣。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 id="0391">探索不同的加密存儲選項</h2>
<!-- /wp:heading -->

<!-- wp:image {"id":1796} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/image-72-1024x576.png" alt="冷熱錢包發現漏洞並消除對區塊鏈的各種攻擊" class="wp-image-1796"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p id="df6c"><strong>每種錢包的優缺點是什麼</strong>？</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p id="3fd8">熱錢包是指連接到互聯網的任何加密貨幣錢包。一般來說，熱錢包更容易設置、訪問和接受更多的代幣。但他們也更<a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">容易受到黑客攻擊</a>、可能的法規和其他技術漏洞。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p id="fa90">冷存儲是指任何未連接到互聯網的加密貨幣錢包。總的來說，冷錢包更安全，但它不像熱錢包那樣接受那麼多的加密貨幣。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="2ad2">我應該買一個冷錢包嗎？</h1>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p id="5080">如果你打算擁有價值超過 100 美元的比特幣、以太坊或其他加密貨幣，你可以立即購買一個冷錢包——這就是它的成本。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p id="c451">也許你聽過人們說，“比特幣讓你有機會成為自己的銀行”？這種責任有利也有弊。通常，加密貨幣的中間人費用較少，銀行法規也不那麼混亂等。不過，確保資產安全是您的責任。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p id="45fe">總的來說，作為一項規則，您應該在熱錢包中保留與放在口袋中的傳統皮革錢包一樣多的錢。這樣想，如果一個小偷要偷你的普通錢包，你只會失去你口袋裡的錢，而不是你銀行賬戶裡的錢。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p id="45b5">簡而言之，這裡有一個可以幫助你的類比：熱錢包可以被認為是你在城裡走來走去的口袋錢包；冷錢包是銀行存款。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="7996">熱錢包的優缺點</h1>
<!-- /wp:heading -->

<!-- wp:heading {"level":1} -->
<h1 id="ef48">使用熱錢包會給你帶來以下好處：</h1>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>通過在錢包中輸入您的密碼和訪問號碼，您可以快速訪問您的代幣。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>投資成本較低。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>它具有廣泛的應用程序或軟件組合，可用作熱錢包。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>您需要設置 PIN 碼或安全碼才能使用。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>它們允許您連接到任何平台，以便您可以操作和交易。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":1} -->
<h1 id="d294">使用這些錢包之一可能有以下缺點：</h1>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>由於資金存儲在雲中，因此盜竊風險更高，更容易受到網絡騙子的攻擊。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>它需要一直連接到互聯網。否則無法支持，因此如果互聯網連接失敗可能會是個大問題。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":1} -->
<h1 id="d041">冷錢包的優缺點</h1>
<!-- /wp:heading -->

<!-- wp:heading {"level":1} -->
<h1 id="2510">使用此錢包將為您帶來以下好處：</h1>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>這種類型的錢包可以在沒有互聯網的情況下使用，為您提供高級別的安全性，因為許多盜竊都發生在互聯網上。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>冷錢包支持ERC20或其他代幣標準，可以支持無限數量的代幣。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>您需要設置 PIN 碼或安全碼才能使用。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>您可以將設備帶到任何地方。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":1} -->
<h1 id="c4a5">使用這些錢包之一可能會產生以下缺點：</h1>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>存在丟失設備的風險。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>您不能使用這些類型的設備進行交易。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>您需要投資大約 100 美元才能獲得它。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>與任何物理設備一樣，它容易出現故障、損壞或讀取問題。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p id="a37a">請記住，如果您想進行交易，熱錢包是更好的選擇。儘管如此，我們還是建議您盡可能對其進行加密，並選擇最佳軟件以獲得最重要的安全性。另一方面，如果您是非交易投資者並且想要最高級別的保護，那麼冷錢包將是更好的選擇。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>熱錢包和冷錢包都是安全存儲加密資產的必需品。當前者用於發送和接收加密令牌時，後者會安全地持有您積累的加密貨幣而沒有漏洞。由於熱錢包需要互聯網連接才能發送和接收令牌，因此它們在很大程度上面臨著被證明代價高昂的加密攻擊的風險。因此，它不能容納大量代幣。這就是冷錢包發揮作用的地方。同時使用熱錢包和冷錢包是加密漏洞管理的安全做法，不會給攻擊者留下漏洞。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>讓我們了解冷熱錢包架構以及應該如何設置它來降低漏洞風險。</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://www.leewayhertz.com/hot-and-cold-wallet-architecture/#What-are-hot-wallets?">什麼是熱錢包？</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.leewayhertz.com/hot-and-cold-wallet-architecture/#What-are-cold-wallets?">什麼是冷錢包？</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.leewayhertz.com/hot-and-cold-wallet-architecture/#Hot-wallet-vs-Cold-Wallet-Differences">熱錢包與冷錢包：差異</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.leewayhertz.com/hot-and-cold-wallet-architecture/#Hot-and-cold-wallet-setupns?">冷熱錢包設置</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.leewayhertz.com/hot-and-cold-wallet-architecture/#How-does-hot-and-cold-wallet-interact?">冷熱錢包如何交互？</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.leewayhertz.com/hot-and-cold-wallet-architecture/#How-do-hot-and-cold-wallet-setups-in-big-systems-work?">大型系統中的冷熱錢包設置如何運作？</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 id="What-are-hot-wallets?">什麼是熱錢包？</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>熱錢包是始終連接到互聯網並且比冷錢包更容易被用戶訪問的加密錢包。它們可以是移動、桌面或基於網絡的錢包，並且用戶友好，便於加密貨幣用戶之間輕鬆轉移貨幣。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>私鑰在應用程序本身的熱錢包中保存和加密，並在線存儲。它有隱藏的漏洞，黑客可以瞄準它闖入系統。由於其易用性，它是購買和交易加密貨幣或一段時間後兌現資產的首選錢包。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3><strong>熱錢包存儲如何工作？</strong></h3>
<!-- /wp:heading -->

<!-- wp:image {"id":1798} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/hot-wallet-storage-work.png" alt="冷熱錢包發現漏洞並消除對區塊鏈的各種攻擊" class="wp-image-1798"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>當您將熱錢包存儲安裝到您的計算機或設備時，它允許您購買、發送和接收加密資產而無需真正持有任何加密貨幣。相反，它持有用戶可以用來發起交易的私鑰。這是可能的，因為它與存儲您資產的區塊鏈交互。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Metamask 是當今最受歡迎的熱錢包之一。因此，我們將解釋熱錢包如何使用 Metamask 工作。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Metamask 可用作網絡瀏覽器擴展，充當區塊鏈（尤其是以太坊）與瀏覽器之間的橋樑。當您下載並安裝 Metamask 並將其添加為您的瀏覽器擴展時，系統會要求您“導入錢包”或“創建錢包”。導入錢包允許您通過輸入秘密恢復短語來添加現有錢包，而後者允許創建新的加密錢包。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果您創建一個新錢包，您需要設置一個新的 Metamask 密碼以保護您設備上的應用程序或平台。這個密碼可以是一串字符、人臉識別，甚至是您可以經常用來訪問應用程序的指紋，而不是秘密助記詞。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>創建密碼後，您必須複製秘密備份短語並將其粘貼或寫在安全的地方。對於您在 Metamask 錢包中的每個帳戶，您將獲得一個私鑰。您可以使用此私鑰解鎖您的加密貨幣。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="What-are-cold-wallets?">什麼是冷錢包？</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>冷錢包是基於硬件的，離線存在。冷錢包雖然不如熱錢包方便使用，但安全性要高得多。使用此離線錢包可讓您的密鑰完全免受在線黑客攻擊。冷錢包可以是紙錢包或硬件設備。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>紙錢包是一種將私鑰和公鑰寫下來或打印在紙上的傳統方式。這是一種存儲密鑰的安全方式，因為它不易受到網絡釣魚攻擊。硬件錢包是 USB 或藍牙設備形式的外部設備，用於存儲您的密鑰。由於它們提供的流動性較低，因此冷錢包最適合計劃購買並長期持有其加密資產的人。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>要在離線冷錢包和在線熱錢包之間進行交易，您需要使用插頭將硬件設備連接到另一台可以訪問互聯網的設備（主要是計算機），然後將所需金額從冷錢包轉移到熱錢包。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3><strong>冷錢包存儲如何工作？</strong></h3>
<!-- /wp:heading -->

<!-- wp:image {"id":1800} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/hot-wallet-storage-work-1.png" alt="冷熱錢包發現漏洞並消除對區塊鏈的各種攻擊" class="wp-image-1800"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>冷錢包本身無法連接到區塊鏈並完成交易。當用戶想要使用冷錢包進行交易時，需要將其連接到具有互聯網連接的設備。但是，這不會將您的私鑰置於安全威脅之下。讓我們看看它是如何工作的。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>一個冷錢包存儲大致可以分為兩個部分，冷錢包核心和冷網關。雖然冷錢包核心無法訪問互聯網並且完全氣隙，但冷網關連接到互聯網。交易在冷錢包的冷網關中創建，然後在離線冷錢包核心中籤名。因此，如果用戶想要將 x 個代幣發送到另一個錢包，交易將在具有互聯網連接的冷網關中創建，但交易簽名將離線完成。交易簽署後，在冷錢包核心中公開或在線廣播。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>讓我們以冷錢包 ELLIPAL 為例來更好地理解這一點。ELLIPAL 是一個氣隙硬件錢包，本質上是一個安全的冷錢包。它與互聯網完全隔離，旨在防止未經授權的訪問、黑客、惡意軟件和其他在線攻擊。因此，要發起交易，用戶需要安裝 ELLIPAL 移動應用程序，作為其連接到區塊鏈的代理。通過 ELLIPAL 錢包進行交易的整個過程可以概括為以下步驟：</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>用戶在應用程序上發起交易。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>該應用程序要求冷錢包確認。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>硬件錢包通過私鑰簽署交易。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>審核通過後，APP完成交易</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 id="Hot-wallet-vs-Cold-Wallet-Differences">熱錢包與冷錢包：差異</h2>
<!-- /wp:heading -->

<!-- wp:table -->
<figure class="wp-block-table"><table><thead><tr><th scope="col"></th><th scope="col"><strong>熱錢包</strong></th><th scope="col">冷錢包</th></tr></thead><tbody><tr><td><strong>互聯網連接</strong></td><td>在線的</td><td>離線</td></tr><tr><td><strong>輔助功能</strong></td><td>交通便利</td><td>可及性低</td></tr><tr><td><strong>有形性</strong></td><td>基於軟件的錢包；所以，無形的</td><td>實體錢包；所以，有形的</td></tr><tr><td><strong>類型</strong></td><td>移動、網絡或桌面錢包</td><td>紙質或硬件錢包</td></tr><tr><td><strong>安全</strong></td><td>容易受到黑客攻擊。所以，不太安全。</td><td>來自黑客和攻擊的威脅更少。所以，更安全</td></tr><tr><td><strong>方便</strong></td><td>簡單方便</td><td>不太方便</td></tr><tr><td><strong>成本</strong></td><td>不會那麼貴</td><td>更貴</td></tr><tr><td><strong>可用性</strong></td><td>最好存儲少量加密貨幣</td><td>最好存儲大量加密貨幣</td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:heading -->
<h2 id="Hot-and-cold-wallet-setupns?">冷熱錢包設置</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>雖然使用熱錢包進行交易簡單方便，但由於存在安全威脅，不能用於保存大量加密貨幣。建議將大量加密貨幣存儲在冷錢包中，因為它們最不容易受到安全威脅，例如惡意軟件攻擊和網絡釣魚。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>設置錢包以避免風險的一種重要方法是將熱錢包和冷錢包結合使用，這可以減少您的資金在網上的曝光率。在此，每個錢包都是為不同的目的而設置的。熱錢包作為接收錢包和發送錢包。接收錢包將管理進入交易所的資金，而發送錢包將用於發送加密貨幣以進行交易和交易。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>由於發送和接收錢包都將託管在在線服務器上，因此應盡量減少兩個錢包中的資金數量，以降低加密漏洞的風險。其餘的加密貨幣應存儲在您的冷錢包中。這樣做可以確保您的大部分資產在發生任何安全威脅時都是安全的。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="How-does-hot-and-cold-wallet-interact?">冷熱錢包如何交互？</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>由於轉移給您的所有資金都進入您的收款錢包，因此您的收款錢包中有可能積累加密貨幣，從而導致加密貨幣漏洞。所以，你需要將大部分發送到冷錢包，一些發送到發送錢包。一旦缺少加密貨幣，您需要在接收錢包中有一個最低金額才能轉移到發送錢包，這可以確保發送錢包在需要時有足夠的加密貨幣。然而，假設資金無法可靠地到達接收錢包，而發送錢包急需貨幣。在這種情況下，您可以將所需金額從冷錢包轉移到發送錢包。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="Content:HotandColdWalletArchitecture-Howtomitigatecryptovulnerability?">如何緩解加密漏洞？</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>假設你總共擁有 200 ETH，並且在任何時候，你都希望避免超過 30% 的資金去冒險。基於此計算，您需要為每個錢包設置最大和最小閾值，以降低任何惡意軟件攻擊的嚴重性。因此，接收錢包應該至少有 10 個 ETH，最多有 20 個 ETH。同樣，發送錢包應至少擁有 20 個 ETH，最多 40 個 ETH。您的其餘資產應保存在冷錢包中。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果您為您的發送和接收錢包設置了閾值，請遵守它並確保設置的金額不超過或低於該限制。過剩的資金容易出現漏洞，低於限額就無法在需要的時候產生所需的數量。所以，時刻保持充足的資金</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="How-do-hot-and-cold-wallet-setups-in-big-systems-work?">大型系統中的冷熱錢包設置如何運作？</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>冷熱錢包設置各不相同，每種設置都是根據開發人員的要求和思考過程設計的。通過以下信息圖，讓我們了解在大系統中如何設計冷熱錢包設置。</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1802} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/hot-and-cold-wallet-setups-in-big-systems-work-696x1024.png" alt="冷熱錢包發現漏洞並消除對區塊鏈的各種攻擊" class="wp-image-1802"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>在上面給出的信息圖中，如果一個人想向另一個用戶發送 x 個令牌，他們在應用程序的前端輸入一個請求，該請求在 API 層或應用程序的後端獲取。後端將輸入請求傳輸到錢包服務器。在典型的錢包架構中，錢包服務器處理多個微服務，如管理節點、數據庫、API 或交易服務。在這種情況下，由於用戶輸入與交易服務相關，因此將請求發送到該微服務。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>然後交易服務將請求發送到錢包微服務，錢包微服務處理與錢包相關的所有服務。錢包微服務因平台而異。在上面的信息圖中，錢包微服務包括以下內容：</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><strong>熱錢包的資金管理——&nbsp;</strong>它確保它始終堅持其閾值而不會出現加密貨幣溢出或赤字，以防止風險暴露。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>列入白名單的 IP –&nbsp;</strong>它將可以訪問您的域或服務器的人數限制為您允許的幾個受信任的 IP 地址。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>代幣——&nbsp;</strong>它管理並跟踪您的代幣，例如 x 個 ETH 或 x 個 SOL。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>服務監控——&nbsp;</strong>該微服務檢查所有服務是否正常運行。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>閾值 –&nbsp;</strong>這些可確保您的錢包中有所需的金額，或者不會將其發送給他人。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>兩步驗證——&nbsp;</strong>這是一個安全過程，您必須在訪問錢包生態系統之前驗證您的身份兩次。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>通知——&nbsp;</strong>它會提醒用戶注意重要事項，例如成功交易完成通知。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>KMS –&nbsp;</strong>密鑰管理系統或 KMS 有助於安全地創建、存儲和管理它。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>旋轉熱錢包&nbsp;</strong></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>當交易輸入從交易服務轉移到錢包微服務時，上述所有的微服務都會被執行。一旦完成所有服務，並確定您的熱錢包有足夠數量的代幣，x 數量的代幣將發送給接收方。那麼，交易就可以說是成功完成了。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>結論</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>合併熱錢包和冷錢包有助於降低用戶和服務提供商遭受加密攻擊的風險。它作為一個舒適的中間地帶，提供了兩個錢包的好處，一個用於加密交易，另一個用於安全地持有加密貨幣。儘管在加密貨幣出現的最初幾天只有熱錢包流行，但如今冷錢包的使用越來越流行。此外，由於其巨大的優勢，混合冷熱錢包正逐漸受到加密專家和服務提供商的重視。因此，只使用一個錢包已經過時了，人們逐漸意識到將冷熱錢包結合起來作為一種額外的安全措施的優勢。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/Cold-and-Hot-Wallets" target="_blank" rel="noreferrer noopener">GitHub</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">電報：https://t.me/cryptodeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://youtu.be/NrQ3oNxlrlU" target="_blank" rel="noreferrer noopener"><strong>視頻：https://youtu.be/NrQ3oNxlrlU</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/cold-and-hot-wallets" target="_blank" rel="noreferrer noopener">來源：https://cryptodeep.ru/cold-and-hot-wallets</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":1817} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/030-1-1024x576.png" alt="冷熱錢包發現漏洞並消除對區塊鏈的各種攻擊" class="wp-image-1817"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">密碼分析</a></p>
<!-- /wp:paragraph -->
