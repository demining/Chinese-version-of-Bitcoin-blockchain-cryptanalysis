# 從對智能合約的攻擊中提高生態系統的整體安全性

<!-- wp:embed {"url":"https://www.youtube.com/embed/HVh_cbsgSMg","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"align":"center","className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed aligncenter is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/HVh_cbsgSMg
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>前端運行 AKA 事務排序依賴</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>康考迪亞大學認為搶先交易是“一個實體受益於事先獲得有關即將進行的交易和交易的特權市場信息的行動過程。”&nbsp;這種對市場未來事件的了解可能導致剝削。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>例如，知道將要購買特定代幣的大量購買，不良行為者可以提前購買該代幣，並在超大買單價格上漲時出售該代幣以獲利。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">搶先交易長期以來一直是金融市場的一個問題，由於區塊鏈的透明性，這個問題在加密貨幣市場再次出現。</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>由於此問題的解決方案因合同而異，因此很難防範。可能的解決方案包括批處理交易和使用預提交方案，即允許用戶稍後提交詳細信息。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/doc/SoK_Transparent_Dishonesty_Front-Running_Attacks_on_Blockchain.pdf" target="_blank" rel="noreferrer noopener"><strong>PDF：SoK：透明的不誠實行為：對區塊鏈的搶先攻擊</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1>跑在前面</h1>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>由於所有交易在執行前都在內存池中可見一小段時間，因此網絡的觀察者可以在動作被包含在塊中之前看到並對其做出反應。如何利用這一點的一個例子是去中心化交易所，其中可以看到買單交易，並且可以在包含第一筆交易之前廣播和執行第二筆訂單。防止這種情況很困難，因為它會歸結為特定合同本身。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Front-running 最初是為傳統金融市場創造的，是一場為了贏家的利益而秩序混亂的競賽。在金融市場中，信息流催生了中介機構，它們可以通過最先了解某些信息並做出反應來簡單地獲利。這些攻擊主要發生在股票市場交易和早期的域名註冊處，例如 whois 網關。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>領先（/ˌfrəntˈrəniNG/）</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>名詞</em>：領先；</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li><em>股票市場</em>做市商在其客戶獲得信息之前根據其經紀人和投資分析師提供的預先信息進行交易的做法。</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 id="taxonomy">分類</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>通過定義&nbsp;<a href="https://arxiv.org/abs/1902.05164">分類法</a>&nbsp;並將每個組與另一個區分開來，我們可以更輕鬆地討論問題並為每個組找到解決方案。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">我們定義了以下類別的搶先交易攻擊</a>：</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>移位</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>插入</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>抑制</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:heading {"level":4} -->
<h4 id="displacement">移位</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>在第一種攻擊中，&nbsp;<em>位移攻擊</em>，&nbsp;&nbsp;&nbsp;Alice（用戶）的函數調用在 Mallory（對手）運行她的函數之後運行<strong>並不重要。</strong>愛麗絲可以成為孤兒，也可以毫無意義地運行。位移的例子包括：</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>愛麗絲嘗試註冊域名，馬洛里先註冊了；</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Alice 試圖提交一個 bug 以獲得賞金，而 Mallory 竊取了它並首先提交了它；</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>愛麗絲試圖在拍賣中出價，馬洛里抄襲。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>這種攻擊通常是通過增加&nbsp;<code>gasPrice</code>&nbsp;高於網絡平均值的值來執行的，通常是 10 倍或更多。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4 id="insertion">插入</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>對於這種類型的攻擊，&nbsp;&nbsp;對對手來說<strong>重要的是原始函數調用在她的事務之後運行。</strong>在插入攻擊中，在 Mallory 運行她的函數之後，合約的狀態發生了變化，她需要 Alice 的原始函數在這個修改後的狀態上運行。例如，如果 Alice 以高於最佳報價的價格購買區塊鏈資產，Mallory 將插入兩筆交易：她將以最佳報價購買，然後以 Alice 略高的購買價格出售相同資產.&nbsp;如果 Alice 的交易隨後運行，Mallory 將在無需持有資產的情況下從差價中獲利。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>與置換攻擊一樣，這通常是通過在天然氣價格拍賣中出價高於愛麗絲的交易來完成的。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>事務順序依賴</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>交易順序依賴相當於智能合約中的競爭條件。例如，如果一個函數設置了獎勵百分比，而 withdraw 函數使用該百分比；然後撤回交易可以通過更改獎勵函數調用提前運行，這會影響最終撤回的金額。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>參見&nbsp;<a href="https://swcregistry.io/docs/SWC-114">SWC-114</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4 id="suppression">抑制</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>在抑制攻擊中，也稱為&nbsp;<em>塊填充</em>&nbsp;攻擊，在 Mallory 運行她的函數後，她試圖延遲 Alice 運行她的函數。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>“Fomo3d”遊戲和其他一些鏈上黑客的第一個獲勝者就是這種情況。攻擊者向自定義智能合約發送多筆交易&nbsp;<code>gasPrice</code>&nbsp;，&nbsp;<code>gasLimit</code>&nbsp;這些交易斷言（或使用其他方式）消耗所有氣體並填滿區塊的&nbsp;<code>gasLimit</code>.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>變體</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">這些攻擊中的每一種都有兩個變體，&nbsp;<em>非對稱</em>&nbsp;和&nbsp;<em>批量</em>。</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>在某些情況下，Alice 和 Mallory 正在執行不同的操作。例如，Alice 正試圖取消一個提議，而 Mallory 正試圖先完成它。我們稱此&nbsp;<em>為不對稱位移</em>。在其他情況下，馬洛里試圖運行大量功能：例如，愛麗絲和其他人試圖購買一家公司在區塊鏈上提供的一組有限的股票。我們稱此為&nbsp;<em>體積位移</em>。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="mitigations">緩解措施</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>搶先交易是以太坊等公共區塊鏈上普遍存在的問題。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>最好的補救措施是&nbsp;<strong>在您的應用程序中消除搶先交易的好處</strong>，主要是消除交易順序或時間的重要性。例如，在市場中，最好實施批量拍賣（這也可以防止高頻交易問題）。另一種方法是使用預提交方案（“我稍後會提交詳細信息”）。第三種選擇是通過指定交易的最大或最小可接受價格範圍來降低搶先交易的成本，從而限制價格下滑。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>交易排序：</strong>&nbsp;&nbsp;Go-Ethereum (Geth) 節點根據它們的&nbsp;<code>gasPrice</code>&nbsp;地址隨機數對交易進行排序。然而，這會導致網絡參與者之間的天然氣拍賣，以包含在當前正在開采的區塊中。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>保密性：</strong>&nbsp;另一種方法是限制交易的可見性，這可以使用“提交和披露”方案來完成。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>一個簡單的實現是在第一筆交易中存儲數據的 keccak256 哈希值，然後在第二筆交易中顯示數據並根據哈希值對其進行驗證。但是請注意，交易本身會洩露抵押的意圖和可能的價值。有增強的提交和顯示方案更安全，但需要更多事務才能運行，例如</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>具有區塊氣體限制的 DoS</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>在以太坊區塊鏈中，區塊都有 gas limit。區塊 gas 限制的好處之一是它可以防止攻擊者創建無限交易循環，但如果交易的 gas 使用量超過此限制，則交易將失敗。這可能會以幾種不同的方式導致 DoS 攻擊。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3><a href="https://github.com/allpaca/smart-contract-attack-vectors/blob/master/attacks/dos-gas-limit.md#unbounded-operations"></a>無界操作</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>區塊 gas 限制可能成為問題的一種情況是將資金發送到一組地址。即使沒有任何惡意，這也很容易出錯。僅僅因為有太多的用戶需要支付，就會使 gas 限制達到最大值，並阻止交易成功。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>這種情況也可能導致攻擊。假設一個不良行為者決定創建大量地址，每個地址都從智能合約中獲得少量資金。如果有效地完成，交易可以無限期地被阻止，甚至可能阻止進一步的交易通過。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>解決這個問題的一個有效方法是在當前的推送支付系統上使用拉取支付系統。為此，將每筆付款分成自己的交易，並讓收款人調用該函數。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果出於某種原因，你真的需要遍歷一個未指定長度的數組，至少期望它可能會佔用多個塊，並允許它在多個事務中執行——如本例所示：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>struct Payee {
    address addr;
    uint256 value;
}

Payee&#91;] payees;
uint256 nextPayeeIndex;

function payOut() {
    uint256 i = nextPayeeIndex;
    while (i &lt; payees.length &amp;&amp; msg.gas &gt; 200000) {
      payees&#91;i].addr.send(payees&#91;i].value);
      i++;
    }
    nextPayeeIndex = i;
}
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3><a href="https://github.com/allpaca/smart-contract-attack-vectors/blob/master/attacks/dos-gas-limit.md#block-stuffing"></a>塊餡</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>在某些情況下，即使您不遍歷未指定長度的數組，您的合約也可能會受到區塊 gas 限制的攻擊。攻擊者可以在使用足夠高的汽油價格處理交易之前填充幾個區塊。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>這種攻擊是通過以非常高的 gas 價格發出幾筆交易來完成的。如果 gas 價格足夠高，並且交易消耗足夠的 gas，它們可以填滿整個區塊並阻止其他交易被處理。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>以太坊交易要求發送者支付 gas 以阻止垃圾郵件攻擊，但在某些情況下，可能有足夠的激勵來完成此類攻擊。例如，在賭博 Dapp Fomo3D 上使用了塊填充攻擊。該應用程序有一個倒計時計時器，用戶可以通過最後一個購買鑰匙來贏得大獎，但每次用戶購買鑰匙時，計時器都會延長。攻擊者買了一把鑰匙，然後填充接下來的 13 個塊和一行，這樣他們就可以贏得大獎。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>為<a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">防止發生此類攻擊，請務必仔細考慮在您的應用程序中加入基於時間的操作是否安全。</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1>拒絕服務</h1>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2 id="dos-with-unexpected-revert">具有（意外）還原的 DoS</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>考慮一個簡單的拍賣合約：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_1" class="wp-block-code"><code>// INSECURE
contract Auction {
    address currentLeader;
    uint highestBid;

    function bid() payable {
        require(msg.value &gt; highestBid);

        require(currentLeader.send(highestBid)); // Refund the old leader, if it fails then revert

        currentLeader = msg.sender;
        highestBid = msg.value;
    }
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>如果攻擊者使用具有回退功能的智能合約出價，則攻擊者可以贏得任何拍賣。當它嘗試向舊領導者退款時，如果退款失敗，它會恢復。這意味著惡意投標人可以成為領導者，同時確保向其地址的任何退款都將&nbsp;<em>始終</em>&nbsp;失敗。通過這種方式，他們可以防止其他任何人調用該&nbsp;<code>bid()</code>&nbsp;函數，並永遠保持領先地位。&nbsp;如前所述，建議改用&nbsp;<a href="https://consensys.github.io/smart-contract-best-practices/development-recommendations/general/external-calls/">拉式支付系統。</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>另一個例子是當一個合同可以通過一個數組迭代來支付用戶（例如，眾籌合同中的支持者）。想要確保每次付款都成功是很常見的。如果沒有，應該恢復。問題是，如果一個調用失敗，您將恢復整個支付系統，這意味著循環永遠不會完成。沒有人得到報酬，因為一個地址強制出錯。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>address&#91;] private refundAddresses;
mapping (address =&gt; uint) public refunds;

// bad
function refundAll() public {
    for(uint x; x &lt; refundAddresses.length; x++) { // arbitrary length iteration based on how many addresses participated
        require(refundAddresses&#91;x].send(refunds&#91;refundAddresses&#91;x]])) // doubly bad, now a single failure on send will hold up all funds
    }
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>同樣，推薦的解決方案是支持&nbsp;<a href="https://consensys.github.io/smart-contract-best-practices/development-recommendations/general/external-calls/">pull over push payments</a>。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>參見&nbsp;<a href="https://swcregistry.io/docs/SWC-113">SWC-113</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="dos-with-block-gas-limit">具有區塊氣體限制的 DoS</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>每個區塊都有可以消耗的氣體量上限，因此可以進行計算量上限。這是區塊氣體限制。如果消耗的 gas 超過此限制，交易將失敗。這導致了幾個可能的拒絕服務向量：</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="gas-limit-dos-on-a-contract-via-unbounded-operations">通過無界操作對合約進行 Gas Limit DoS</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>您可能已經註意到前面示例的另一個問題：通過一次向所有人付款，您可能會遇到區塊 gas 限制。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>即使沒有蓄意攻擊，這也可能導致問題。但是，如果攻擊者可以操縱所需的氣體量，那就尤其糟糕了。在前面的示例中，攻擊者可以添加一堆地址，每個地址都需要獲得非常小的退款。因此，退還每個攻擊者地址的 gas 成本最終可能會超過 gas 限制，從而阻止退款交易的發生。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>這是&nbsp;<a href="https://consensys.github.io/smart-contract-best-practices/development-recommendations/general/external-calls/">支持拉式付款而非推式付款</a>的另一個原因。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果您絕對必須遍歷一個未知大小的數組，那麼您應該計劃它可能會佔用多個塊，因此需要多個事務。您將需要跟踪您走了多遠，並能夠從該點繼續，如以下示例所示：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>struct Payee {
    address addr;
    uint256 value;
}

Payee&#91;] payees;
uint256 nextPayeeIndex;

function payOut() {
    uint256 i = nextPayeeIndex;
    while (i &lt; payees.length &amp;&amp; gasleft() &gt; 200000) {
      payees&#91;i].addr.send(payees&#91;i].value);
      i++;
    }
    nextPayeeIndex = i;
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>如果在等待函數的下一次迭代時處理其他事務，您將需要確保不會發生任何不良情況&nbsp;<code>payOut()</code>&nbsp;。因此，僅在絕對必要時才使用此模式。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="gas-limit-dos-on-the-network-via-block-stuffing">通過塊填充在網絡上進行 Gas 限制 DoS</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>即使您的合約不包含無限循環，攻擊者也可以通過以足夠高的 gas 價格放置計算密集型交易來防止其他交易被包含在區塊鏈中幾個區塊。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>為此，攻擊者可以發出多個交易，這些交易將消耗整個 gas 限制，並在下一個區塊被開採時立即包含足夠高的 gas 價格。沒有 gas 價格可以保證包含在區塊中，但價格越高，機會就越大。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果攻擊成功，則該塊中不會包含其他交易。有時，攻擊者的目標是在特定時間之前阻止對特定合約的交易。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>此次攻擊&nbsp;<a href="https://solmaz.io/2018/10/18/anatomy-block-stuffing/">是</a>&nbsp;在一款賭博應用 Fomo3D 上進行的。該應用程序旨在獎勵最後一個購買“鑰匙”的地址。每次購買鑰匙都會延長計時器，一旦計時器變為 0，遊戲就會結束。攻擊者購買一把鑰匙，然後連續填充 13 個區塊，直到計時器被觸發並釋放支出。攻擊者發送的交易在每個區塊上消耗了 790 萬氣體，因此氣體限制允許一些小的“發送”交易（每個消耗 21,000 氣體），但不允許調用函數（消耗 300,000+ 氣體）&nbsp;&nbsp;<code>buyKey()</code>&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Block Stuffing 攻擊可用於任何需要在特定時間段內採取行動的合約。然而，與任何攻擊一樣，它只有在預期回報超過其成本時才有利可圖。這種攻擊的成本與需要填充的塊數成正比。如果通過阻止其他參與者的行動可以獲得大筆支出，那麼您的合約很可能會成為此類攻擊的目標。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>具有（意外）還原的 DoS</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>當您嘗試向用戶發送資金並且該功能依賴於資金轉移成功時，功能中可能會發生 DoS（拒絕服務）攻擊。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果資金被發送到由不良行為者創建的智能合約，這可能會出現問題，因為他們可以簡單地創建一個回退功能來恢復所有支付。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>例如：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>// INSECURE
contract Auction {
    address currentLeader;
    uint highestBid;

    function bid() payable {
        require(msg.value &gt; highestBid);

        require(currentLeader.send(highestBid)); // Refund the old leader, if it fails then revert

        currentLeader = msg.sender;
        highestBid = msg.value;
    }
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>正如你在這個例子中看到的，如果攻擊者從一個具有回退功能的智能合約中出價，那麼他們將永遠無法退還，因此沒有人可以出更高的價。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果沒有攻擊者在場，這也可能會出現問題。例如，您可能希望通過遍歷數組來向一組用戶付款，當然您會希望確保每個用戶都得到適當的付款。這裡的問題是，如果一次支付失敗，功能將被恢復，並且沒有人支付。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>address&#91;] private refundAddresses;
mapping (address =&gt; uint) public refunds;

// bad
function refundAll() public {
    for(uint x; x &lt; refundAddresses.length; x++) { // arbitrary length iteration based on how many addresses participated
        require(refundAddresses&#91;x].send(refunds&#91;refundAddresses&#91;x]])) // doubly bad, now a single failure on send will hold up all funds
    }
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>解決這個問題的一個有效方法是在當前的推送支付系統上使用拉取支付系統。為此，將每筆付款分成自己的交易，並讓收款人調用該函數。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>contract auction {
    address highestBidder;
    uint highestBid;
    mapping(address =&gt; uint) refunds;

    function bid() payable external {
        require(msg.value &gt;= highestBid);

        if (highestBidder != address(0)) {
            refunds&#91;highestBidder] += highestBid; // record the refund that this user can claim
        }

        highestBidder = msg.sender;
        highestBid = msg.value;
    }

    function withdrawRefund() external {
        uint refund = refunds&#91;msg.sender];
        refunds&#91;msg.sender] = 0;
        (bool success, ) = msg.sender.call.value(refund)("");
        require(success);
    }
}
</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":1} -->
<h1>拒絕服務</h1>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2 id="dos-with-unexpected-revert">具有（意外）還原的 DoS</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>考慮一個簡單的拍賣合約：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_1" class="wp-block-code"><code>// INSECURE
contract Auction {
    address currentLeader;
    uint highestBid;

    function bid() payable {
        require(msg.value &gt; highestBid);

        require(currentLeader.send(highestBid)); // Refund the old leader, if it fails then revert

        currentLeader = msg.sender;
        highestBid = msg.value;
    }
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>如果攻擊者使用具有回退功能的智能合約出價，則攻擊者可以贏得任何拍賣。當它嘗試向舊領導者退款時，如果退款失敗，它會恢復。這意味著惡意投標人可以成為領導者，同時確保向其地址的任何退款都將&nbsp;<em>始終</em>&nbsp;失敗。通過這種方式，他們可以防止其他任何人調用該&nbsp;<code>bid()</code>&nbsp;函數，並永遠保持領先地位。&nbsp;如前所述，建議改用&nbsp;<a href="https://consensys.github.io/smart-contract-best-practices/development-recommendations/general/external-calls/">拉式支付系統。</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>另一個例子是當一個合同可以通過一個數組迭代來支付用戶（例如，眾籌合同中的支持者）。想要確保每次付款都成功是很常見的。如果沒有，應該恢復。問題是，如果一個調用失敗，您將恢復整個支付系統，這意味著循環永遠不會完成。沒有人得到報酬，因為一個地址強制出錯。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>address&#91;] private refundAddresses;
mapping (address =&gt; uint) public refunds;

// bad
function refundAll() public {
    for(uint x; x &lt; refundAddresses.length; x++) { // arbitrary length iteration based on how many addresses participated
        require(refundAddresses&#91;x].send(refunds&#91;refundAddresses&#91;x]])) // doubly bad, now a single failure on send will hold up all funds
    }
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>同樣，推薦的解決方案是支持&nbsp;<a href="https://consensys.github.io/smart-contract-best-practices/development-recommendations/general/external-calls/">pull over push payments</a>。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>參見&nbsp;<a href="https://swcregistry.io/docs/SWC-113">SWC-113</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="dos-with-block-gas-limit">具有區塊氣體限制的 DoS</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>每個區塊都有可以消耗的氣體量上限，因此可以進行計算量上限。這是區塊氣體限制。如果消耗的 gas 超過此限制，交易將失敗。這導致了幾個可能的拒絕服務向量：</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="gas-limit-dos-on-a-contract-via-unbounded-operations">通過無界操作對合約進行 Gas Limit DoS</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>您可能已經註意到前面示例的另一個問題：通過一次向所有人付款，您可能會遇到區塊 gas 限制。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>即使沒有蓄意攻擊，這也可能導致問題。但是，如果攻擊者可以操縱所需的氣體量，那就尤其糟糕了。在前面的示例中，攻擊者可以添加一堆地址，每個地址都需要獲得非常小的退款。因此，退還每個攻擊者地址的 gas 成本最終可能會超過 gas 限制，從而阻止退款交易的發生。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>這是&nbsp;<a href="https://consensys.github.io/smart-contract-best-practices/development-recommendations/general/external-calls/">支持拉式付款而非推式付款</a>的另一個原因。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果您絕對必須遍歷一個未知大小的數組，那麼您應該計劃它可能會佔用多個塊，因此需要多個事務。您將需要跟踪您走了多遠，並能夠從該點繼續，如以下示例所示：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>struct Payee {
    address addr;
    uint256 value;
}

Payee&#91;] payees;
uint256 nextPayeeIndex;

function payOut() {
    uint256 i = nextPayeeIndex;
    while (i &lt; payees.length &amp;&amp; gasleft() &gt; 200000) {
      payees&#91;i].addr.send(payees&#91;i].value);
      i++;
    }
    nextPayeeIndex = i;
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>如果在等待函數的下一次迭代時處理其他事務，您將需要確保不會發生任何不良情況&nbsp;<code>payOut()</code>&nbsp;。因此，僅在絕對必要時才使用此模式。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="gas-limit-dos-on-the-network-via-block-stuffing">通過塊填充在網絡上進行 Gas 限制 DoS</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>即使您的合約不包含無限循環，攻擊者也可以通過以足夠高的 gas 價格放置計算密集型交易來防止其他交易被包含在區塊鏈中幾個區塊。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>為此，攻擊者可以發出多個交易，這些交易將消耗整個 gas 限制，並在下一個區塊被開採時立即包含足夠高的 gas 價格。沒有 gas 價格可以保證包含在區塊中，但價格越高，機會就越大。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果攻擊成功，則該塊中不會包含其他交易。有時，攻擊者的目標是在特定時間之前阻止對特定合約的交易。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>此次攻擊&nbsp;<a href="https://solmaz.io/2018/10/18/anatomy-block-stuffing/">是</a>&nbsp;在一款賭博應用 Fomo3D 上進行的。該應用程序旨在獎勵最後一個購買“鑰匙”的地址。每次購買鑰匙都會延長計時器，一旦計時器變為 0，遊戲就會結束。攻擊者購買一把鑰匙，然後連續填充 13 個區塊，直到計時器被觸發並釋放支出。攻擊者發送的交易在每個區塊上消耗了 790 萬氣體，因此氣體限制允許一些小的“發送”交易（每個消耗 21,000 氣體），但不允許調用函數（消耗 300,000+ 氣體）&nbsp;&nbsp;<code>buyKey()</code>&nbsp;。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Block Stuffing 攻擊可用於任何需要在特定時間段內採取行動的合約。然而，與任何攻擊一樣，它只有在預期回報超過其成本時才有利可圖。這種攻擊的成本與需要填充的塊數成正比。如果通過阻止其他參與者的行動可以獲得大筆支出，那麼您的合約很可能會成為此類攻擊的目標。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":1} -->
<h1>外部調用</h1>
<!-- /wp:heading -->

<!-- wp:heading {"level":4} -->
<h4 id="use-caution-when-making-external-calls">撥打外部電話時要小心</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>調用不受信任的合約可能會帶來一些意想不到的風險或錯誤。<em>外部調用可能會在該合約或</em>&nbsp;它所依賴的任何其他合約中執行惡意代碼&nbsp;。因此，每個外部調用都應被視為潛在的安全風險。當不可能或不希望刪除外部調用時，請使用本節其餘部分中的建議將危險降至最低。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":4} -->
<h4 id="mark-untrusted-contracts">標記不受信任的合約</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>與外部合約交互時，以明確表明與它們交互可能不安全的方式命名變量、方法和合約接口。這適用於您自己調用外部合約的函數。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_1" class="wp-block-code"><code>// bad
Bank.withdraw(100); // Unclear whether trusted or untrusted

function makeWithdrawal(uint amount) { // Isn't clear that this function is potentially unsafe
    Bank.withdraw(amount);
}

// good
UntrustedBank.withdraw(100); // untrusted external call
TrustedBank.withdraw(100); // external but trusted bank contract maintained by XYZ Corp

function makeUntrustedWithdrawal(uint amount) {
    UntrustedBank.withdraw(amount);
}
</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":4} -->
<h4 id="avoid-state-changes-after-external-calls">避免外部調用後狀態改變</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>無論是使用&nbsp;<em>原始調用</em>&nbsp;（形式&nbsp;<code>someAddress.call()</code>）還是&nbsp;<em>合約調用</em>&nbsp;（形式&nbsp;<code>ExternalContract.someMethod()</code>），假設惡意代碼可能會執行。即使&nbsp;不是惡意的，惡意代碼也可以由<em>它</em><code>ExternalContract</code>調用的&nbsp;任何合約執行&nbsp;&nbsp;。<em></em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>一個特別的危險是惡意代碼可能會劫持控制流，從而導致由於重入而導致的漏洞。（有關&nbsp;&nbsp;此問題的更全面討論，請參閱<a href="https://consensys.github.io/smart-contract-best-practices/attacks/reentrancy/">重入）。</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果您正在調用不受信任的外部合約，&nbsp;<em>請避免在調用後更改狀態</em>。這種模式有時也稱為&nbsp;<a href="http://solidity.readthedocs.io/en/develop/security-considerations.html?highlight=check%20effects#use-the-checks-effects-interactions-pattern">檢查-效果-交互模式</a>。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>參見&nbsp;<a href="https://swcregistry.io/docs/SWC-107">SWC-107</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":4} -->
<h4 id="dont-use-transfer-or-send">不要使用&nbsp;<code>transfer()</code>&nbsp;或&nbsp;<code>send()</code>。</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><code>.transfer()</code>&nbsp;並將&nbsp;<code>.send()</code>&nbsp;恰好 2,300 gas 轉發給接收者。這種硬編碼的 gas 津貼的目標是防止&nbsp;<a href="https://consensys.github.io/smart-contract-best-practices/attacks/reentrancy/">重入漏洞</a>，但這只有在 gas 成本不變的假設下才有意義。最近&nbsp;<a href="https://eips.ethereum.org/EIPS/eip-1884">EIP 1884</a>&nbsp;被包含在伊斯坦布爾硬分叉中。EIP 1884 中包含的變化之一是增加了操作的 gas 成本&nbsp;<code>SLOAD</code>&nbsp;，導致合約的回退功能花費超過 2300 gas。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>建議停止使用&nbsp;<code>.transfer()</code>&nbsp;，&nbsp;<code>.send()</code>&nbsp;改用&nbsp;<code>.call()</code>.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>// bad
contract Vulnerable {
    function withdraw(uint256 amount) external {
        // This forwards 2300 gas, which may not be enough if the recipient
        // is a contract and gas costs change.
        msg.sender.transfer(amount);
    }
}

// good
contract Fixed {
    function withdraw(uint256 amount) external {
        // This forwards all available gas. Be sure to check the return value!
        (bool success, ) = msg.sender.call.value(amount)("");
        require(success, "Transfer failed.");
    }
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>請注意，這&nbsp;<code>.call()</code>&nbsp;對減輕重入攻擊沒有任何作用，因此必須採取其他預防措施。為防止重入攻擊，建議您使用&nbsp;<a href="https://solidity.readthedocs.io/en/develop/security-considerations.html?highlight=check%20effects#use-the-checks-effects-interactions-pattern">checks-effects-interactions 模式</a>。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":4} -->
<h4 id="handle-errors-in-external-calls">處理外部調用中的錯誤</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Solidity 提供了適用於原始地址的低級調用方法：&nbsp;&nbsp;<code>address.call()</code>、&nbsp;&nbsp;<code>address.callcode()</code>、&nbsp;<code>address.delegatecall()</code>和&nbsp;<code>address.send()</code>。這些低級方法從不拋出異常，但會&nbsp;<code>false</code>&nbsp;在調用遇到異常時返回。另一方面，&nbsp;<em>合約調用</em>&nbsp;（例如，&nbsp;&nbsp;<code>ExternalContract.doSomething()</code>）將自動傳播拋出（例如，&nbsp;&nbsp;如果&nbsp;拋出，<code>ExternalContract.doSomething()</code>&nbsp;也會傳播&nbsp;&nbsp;）。<code>throw</code><code>doSomething()</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>如果您選擇使用低級調用方法，請確保通過檢查返回值來處理調用失敗的可能性。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>// bad
someAddress.send(55);
someAddress.call.value(55)(""); // this is doubly dangerous, as it will forward all remaining gas and doesn't check for result
someAddress.call.value(100)(bytes4(sha3("deposit()"))); // if deposit throws an exception, the raw call() will only return false and transaction will NOT be reverted

// good
(bool success, ) = someAddress.call.value(55)("");
if(!success) {
    // handle failure code
}

ExternalContract(someAddress).deposit.value(100)();
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>參見&nbsp;<a href="https://swcregistry.io/docs/SWC-104">SWC-104</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":4} -->
<h4 id="favor-pull-over-push-for-external-calls">贊成&nbsp;<em>拉</em>&nbsp;過&nbsp;<em>推送</em>&nbsp;外部呼叫</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>外部調用可能會意外或故意失敗。為了最大限度地減少此類故障造成的損害，通常最好將每個外部調用隔離到它自己的事務中，該事務可以由調用的接收者啟動。這與支付尤其相關，在這種情況下，最好讓用戶提取資金而不是自動將資金推送給他們。<a href="https://consensys.github.io/smart-contract-best-practices/attacks/denial-of-service/">（這也減少了gas limit 出現問題</a>的可能性&nbsp;。）避免在單個交易中合併多個以太幣轉移。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_4" class="wp-block-code"><code>// bad
contract auction {
    address highestBidder;
    uint highestBid;

    function bid() payable {
        require(msg.value &gt;= highestBid);

        if (highestBidder != address(0)) {
            (bool success, ) = highestBidder.call.value(highestBid)("");
            require(success); // if this call consistently fails, no one else can bid
        }

       highestBidder = msg.sender;
       highestBid = msg.value;
    }
}

// good
contract auction {
    address highestBidder;
    uint highestBid;
    mapping(address =&gt; uint) refunds;

    function bid() payable external {
        require(msg.value &gt;= highestBid);

        if (highestBidder != address(0)) {
            refunds&#91;highestBidder] += highestBid; // record the refund that this user can claim
        }

        highestBidder = msg.sender;
        highestBid = msg.value;
    }

    function withdrawRefund() external {
        uint refund = refunds&#91;msg.sender];
        refunds&#91;msg.sender] = 0;
        (bool success, ) = msg.sender.call.value(refund)("");
        require(success);
    }
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>參見&nbsp;<a href="https://swcregistry.io/docs/SWC-128">SWC-128</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":4} -->
<h4 id="dont-delegatecall-to-untrusted-code">不要將調用委託給不受信任的代碼</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>該&nbsp;<code>delegatecall</code>&nbsp;函數用於從其他合約調用函數，就好像它們屬於調用方合約一樣。因此，被調用者可以改變調用地址的狀態。這可能是不安全的。下面的示例顯示了使用如何&nbsp;<code>delegatecall</code>&nbsp;導致合約的破壞和余額的損失。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_5" class="wp-block-code"><code>contract Destructor
{
    function doWork() external
    {
        selfdestruct(0);
    }
}

contract Worker
{
    function doWork(address _internalWorker) public
    {
        // unsafe
        _internalWorker.delegatecall(bytes4(keccak256("doWork()")));
    }
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>如果以&nbsp;已部署&nbsp;合約的地址作為參數&nbsp;<code>Worker.doWork()</code>&nbsp;調用&nbsp;，&nbsp;合約將自毀。僅將執行委託給受信任的合約，而絕不會委託給用戶提供的地址。<code>Destructor</code><code>Worker</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>搶先交易是以太坊 DApp 中普遍存在的問題。DApp 開發人員不一定有設計 DApps 的心態。這是提出主題並提高對此類攻擊的認識的嘗試。雖然可以構建一些 DApp 級別的應用程序邏輯來緩解這些攻擊，但它在不同 DApp 類別中的普遍存在表明區塊鏈級別的緩解措施可能會更有效。我們強調這是一個重要的研究領域。我們認為搶先交易是一個行動過程，在這種過程中，一個實體可以從事先獲得有關即將進行的交易和交易的特權市場信息中獲益。自 1970 年代以來，搶先交易一直是金融工具市場的一個問題。隨著區塊鏈技術的出現，搶先交易以我們在這裡探索的新形式重新出現，受區塊鏈去中心化和透明性的啟發。在本文中，我們從分散的知識體系和以太坊區塊鏈上部署的前 25 個最活躍的去中心化應用程序 (DApps) 的前端運行實例中汲取靈感。此外，我們對 Status.im 初始代幣發行 (ICO) 進行了詳細分析，並展示了異常礦工行為的證據，這些行為表明了搶先購買代幣。最後，我們將提出的解決方案映射到有用的類別中&nbsp;im 初始代幣發行 (ICO) 並顯示異常礦工行為的證據表明搶先購買代幣。最後，我們將提出的解決方案映射到有用的類別中&nbsp;im 初始代幣發行 (ICO) 並顯示異常礦工行為的證據表明搶先購買代幣。最後，我們將提出的解決方案映射到有用的類別中</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/Improving-Overall-Security" target="_blank" rel="noreferrer noopener">GitHub</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">電報：https://t.me/cryptodeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://youtu.be/HVh_cbsgSMg" target="_blank" rel="noreferrer noopener"><strong>視頻：https://youtu.be/HVh_cbsgSMg</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeeptech.ru/improving-overall-security" target="_blank" rel="noreferrer noopener">來源：https://cryptodeeptech.ru/improving-overall-security</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":1999} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2023/03/035-1-1024x576.png" alt="從對智能合約的攻擊中提高生態系統的整體安全性" class="wp-image-1999"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeeptech.ru/category/cryptanalysis/">密碼分析</a></p>
<!-- /wp:paragraph -->
