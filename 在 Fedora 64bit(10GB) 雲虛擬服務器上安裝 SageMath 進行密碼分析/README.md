# 在 Fedora 64bit(10GB) 雲虛擬服務器上安裝 SageMath 進行密碼分析

<!-- wp:embed {"url":"https://www.youtube.com/embed/xHnTDRgZwvE","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/xHnTDRgZwvE
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>在本文中，我們將通過幻燈片詳細展示如何在<strong>Fedora 30 64 位 (10GB)</strong>雲虛擬服務器上安裝<strong><a href="https://www.sagemath.org/" target="_blank" rel="noreferrer noopener">“SageMath”</a></strong>&nbsp;。例如，我們將使用<a href="https://digitalruble.tech/cloud" target="_blank" rel="noreferrer noopener"><strong>“DIGITAL RUBLE TECH”</strong></a>服務器。<strong>之前，我們使用Google Colab</strong>雲服務來安裝<strong><a href="https://www.sagemath.org/" target="_blank" rel="noreferrer noopener">“SageMath”</a></strong>，但不幸的是，由於最近的更新，並非所有用於比特幣區塊鏈密碼分析的組件都能正常工作。<strong></strong><a href="https://digitalruble.tech/cloud" target="_blank" rel="noreferrer noopener"><strong></strong></a><strong><a href="https://www.sagemath.org/" target="_blank" rel="noreferrer noopener"></a></strong><strong></strong></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><a href="https://digitalruble.tech/cloud" target="_blank" rel="noreferrer noopener">登記：</a></h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>首先我們需要創建一個個人賬戶，我們將在網站上註冊： https:&nbsp;<a href="https://digitalruble.tech/cloud" target="_blank" rel="noreferrer noopener"><strong>//digitalruble.tech/cloud</strong></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2492,"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://digitalruble.tech/cloud" target="_blank" rel="noreferrer noopener"><img src="https://cryptodeep.ru/wp-content/uploads/2023/03/01.png" alt="在 Fedora 64bit(10GB) 雲虛擬服務器上安裝 SageMath 進行密碼分析" class="wp-image-2492"/></a></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>選擇選項：<strong>個人</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":2514} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/03/02-1.png" alt="在 Fedora 64bit(10GB) 雲虛擬服務器上安裝 SageMath 進行密碼分析" class="wp-image-2514"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>讓我們啟動控制台</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":2495} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/03/03-1.png" alt="在 Fedora 64bit(10GB) 雲虛擬服務器上安裝 SageMath 進行密碼分析" class="wp-image-2495"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>轉到選項：<em><strong>彈性雲服務器</strong></em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":2497} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/03/04.png" alt="在 Fedora 64bit(10GB) 雲虛擬服務器上安裝 SageMath 進行密碼分析" class="wp-image-2497"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>創建<strong>彈性雲服務器</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":2498} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/03/05.png" alt="在 Fedora 64bit(10GB) 雲虛擬服務器上安裝 SageMath 進行密碼分析" class="wp-image-2498"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>我們選擇我們需要的參數：</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":2499} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/03/06.png" alt="在 Fedora 64bit(10GB) 雲虛擬服務器上安裝 SageMath 進行密碼分析" class="wp-image-2499"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>指定 &nbsp;<strong>Fedora 30 64bit(10GB)</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":2500} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/03/07.png" alt="在 Fedora 64bit(10GB) 雲虛擬服務器上安裝 SageMath 進行密碼分析" class="wp-image-2500"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2502} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/03/08.png" alt="在 Fedora 64bit(10GB) 雲虛擬服務器上安裝 SageMath 進行密碼分析" class="wp-image-2502"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>選擇網絡所需的<strong>VPC</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":2503} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/03/09.png" alt="在 Fedora 64bit(10GB) 雲虛擬服務器上安裝 SageMath 進行密碼分析" class="wp-image-2503"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>設置並記住您自己的密碼</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":2504} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/03/10.png" alt="在 Fedora 64bit(10GB) 雲虛擬服務器上安裝 SageMath 進行密碼分析" class="wp-image-2504"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>保存配置</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":2505} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/03/11.png" alt="在 Fedora 64bit(10GB) 雲虛擬服務器上安裝 SageMath 進行密碼分析" class="wp-image-2505"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>雲虛擬服務器&nbsp;<strong>Fedora 30 64bit(10GB)&nbsp;</strong>創建成功！進入終端，點擊：<strong>遠程登錄</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":2506} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/03/12.png" alt="在 Fedora 64bit(10GB) 雲虛擬服務器上安裝 SageMath 進行密碼分析" class="wp-image-2506"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>為我們打開的終端安裝了<em>雲虛擬服務器</em>和<strong>Fedora 30 64 位 (10GB)</strong><em>&nbsp;</em><strong></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":2516} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-1024x573.png" alt="在 Fedora 64bit(10GB) 雲虛擬服務器上安裝 SageMath 進行密碼分析" class="wp-image-2516"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2518} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-1-1024x590.png" alt="在 Fedora 64bit(10GB) 雲虛擬服務器上安裝 SageMath 進行密碼分析" class="wp-image-2518"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2519} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-2-1024x705.png" alt="在 Fedora 64bit(10GB) 雲虛擬服務器上安裝 SageMath 進行密碼分析" class="wp-image-2519"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>檢查安裝，運行命令：</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat /etc/redhat-release</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2520} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-3-1024x351.png" alt="在 Fedora 64bit(10GB) 雲虛擬服務器上安裝 SageMath 進行密碼分析" class="wp-image-2520"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>讓我們更新我們的服務器，運行命令：</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>dnf check-update</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2521} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-4-1024x712.png" alt="在 Fedora 64bit(10GB) 雲虛擬服務器上安裝 SageMath 進行密碼分析" class="wp-image-2521"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>安裝<strong>Python 3</strong>，運行命令：</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>dnf install python3</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2524} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-7-1024x230.png" alt="在 Fedora 64bit(10GB) 雲虛擬服務器上安裝 SageMath 進行密碼分析" class="wp-image-2524"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>安裝</em><strong>SageMath&nbsp;</strong><em>，運行命令：</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>dnf install sagemath</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2525} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-8-1024x717.png" alt="在 Fedora 64bit(10GB) 雲虛擬服務器上安裝 SageMath 進行密碼分析" class="wp-image-2525"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":2526} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-9-1024x707.png" alt="在 Fedora 64bit(10GB) 雲虛擬服務器上安裝 SageMath 進行密碼分析" class="wp-image-2526"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":2527} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-10-1024x698.png" alt="在 Fedora 64bit(10GB) 雲虛擬服務器上安裝 SageMath 進行密碼分析" class="wp-image-2527"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":2528} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-11-1024x704.png" alt="在 Fedora 64bit(10GB) 雲虛擬服務器上安裝 SageMath 進行密碼分析" class="wp-image-2528"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":2529} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-12-1024x711.png" alt="在 Fedora 64bit(10GB) 雲虛擬服務器上安裝 SageMath 進行密碼分析" class="wp-image-2529"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":2530} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-13-1024x710.png" alt="在 Fedora 64bit(10GB) 雲虛擬服務器上安裝 SageMath 進行密碼分析" class="wp-image-2530"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":2532} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-15-1024x700.png" alt="在 Fedora 64bit(10GB) 雲虛擬服務器上安裝 SageMath 進行密碼分析" class="wp-image-2532"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":2569} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-17-1-1024x697.png" alt="在 Fedora 64bit(10GB) 雲虛擬服務器上安裝 SageMath 進行密碼分析" class="wp-image-2569"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>驗證<strong>SageMath安裝</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sage -v</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2570} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-18-1-1024x166.png" alt="在 Fedora 64bit(10GB) 雲虛擬服務器上安裝 SageMath 進行密碼分析" class="wp-image-2570"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>&nbsp;使用我們的&nbsp;<a href="https://github.com/demining/CryptoDeepTools/tree/main/18TwistAttack" target="_blank" rel="noreferrer noopener"><strong>18TwistAttack</strong></a>存儲庫實施&nbsp;<a href="https://attacksafe.ru/twist-attack-on-bitcoin/" target="_blank" rel="noreferrer noopener"><strong>Twist Attack算法</strong></a><a href="https://github.com/demining/CryptoDeepTools/tree/main/18TwistAttack" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/18TwistAttack/

ls</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2572} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-19-1-1024x292.png" alt="在 Fedora 64bit(10GB) 雲虛擬服務器上安裝 SageMath 進行密碼分析" class="wp-image-2572"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>要求解離散對數，&nbsp;<em><code>(Pollard's rho algorithm for logarithms)</code></em>&nbsp;請運行&nbsp;<code>Python-script:</code>&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/bbd83042e7405508cd2e646ad1b0819da0f9c58d/18TwistAttack/discrete.py" target="_blank" rel="noreferrer noopener">discrete.py</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 class="wp-block-heading">運行命令：</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sage -python3 discrete.py</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2573} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-20-1-1024x601.png" alt="在 Fedora 64bit(10GB) 雲虛擬服務器上安裝 SageMath 進行密碼分析" class="wp-image-2573"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong>Sage Math</strong>完成離散對數問題&nbsp;<em><code>(Pollard's rho algorithm for logarithms)</code></em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>現在一切正常！</strong></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>我們收到了十進制格式的比特幣錢包私鑰，然後我們需要按照專門針對<strong><a href="https://cryptodeeptech.ru/twist-attack/" target="_blank" rel="noreferrer noopener">Twist 攻擊的文章的說明進行密碼分析</a></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/Install-SageMath-on-Fedora" target="_blank" rel="noreferrer noopener">來源</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://digitalruble.tech/cloud" target="_blank" rel="noreferrer noopener">數字盧布技術</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">電報：https://t.me/cryptodeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://youtu.be/xHnTDRgZwvE" target="_blank" rel="noreferrer noopener">視頻素材：https://youtu.be/xHnTDRgZwvE</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/install-sagemath-on-fedora" target="_blank" rel="noreferrer noopener">來源：https://cryptodeep.ru/install-sagemath-on-fedora</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2577} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/036-1024x576.png" alt="在 Fedora 64bit(10GB) 雲虛擬服務器上安裝 SageMath 進行密碼分析" class="wp-image-2577"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">密碼分析</a></p>
<!-- /wp:paragraph -->
