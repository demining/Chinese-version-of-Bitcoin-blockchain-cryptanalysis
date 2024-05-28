# 在 Google Colab 中安裝 SageMath

<!-- wp:embed {"url":"https://www.youtube.com/embed/DBu0UnVe0ig","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/DBu0UnVe0ig
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>在本文中，我們將<code>SageMath</code>在<code>Google Colab</code>.&nbsp;我們之前發表過一篇文章：“<strong><a href="https://cryptodeeptech.ru/install-sagemath-on-fedora/" target="_blank" rel="noreferrer noopener">在 Fedora 64 位（10GB）雲虛擬服務器上安裝 SageMath 進行密碼分析</a></strong>”，但為了繼續對比特幣區塊鏈進行密碼分析，我們的許多讀者更喜歡<code>Debian</code>使用.&nbsp;據我們所知，它已更新為.<code>Ubuntu</code><code>Fedora</code><code>Google Colab</code><code>"Ubuntu 20.04.5 LTS"</code></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>我們可以通過運行命令來檢查這一點：</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!cat /etc/lsb-release
</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2598} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-21-1024x192.png" alt="在 Google Colab 中安裝 SageMath" class="wp-image-2598"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>因此<code>"Ubuntu 20.04.5 LTS"</code>，該版本只允許我們安裝<code>SageMath version 9.0, Release Date: 2020-01-01</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>使用標準安裝命令：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!sudo apt-get install -y sagemath-common</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2599} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-22-1024x120.png" alt="在 Google Colab 中安裝 SageMath" class="wp-image-2599"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>不幸的是這個版本不能正常工作。</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>為了進行完整的密碼分析，我們將安裝<code>Google Colab</code>一個全新的版本<code>SageMath version 9.3</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>文件：<a href="https://github.com/demining/CryptoDeepTools/blob/main/19SageMathGoogleColab/Install_SageMath_in_Google_Colab.ipynb" target="_blank" rel="noreferrer noopener"><strong>Install_SageMath_in_Google_Colab.ipynb</strong></a>&nbsp;我們發佈在<code>GitHub</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>我們去官網看看： https:&nbsp;<strong><a href="https://colab.research.google.com/" target="_blank" rel="noreferrer noopener">//colab.research.google.com</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>選擇選項<strong>“下載記事本”</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2605} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-24.png" alt="在 Google Colab 中安裝 SageMath" class="wp-image-2605"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>下載文件：<a href="https://github.com/demining/CryptoDeepTools/blob/main/19SageMathGoogleColab/Install_SageMath_in_Google_Colab.ipynb" target="_blank" rel="noreferrer noopener"><strong>Install_SageMath_in_Google_Colab.ipynb</strong></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2606} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-25.png" alt="在 Google Colab 中安裝 SageMath" class="wp-image-2606"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>現在，通過該實用程序，<code>wget</code>&nbsp;下載<code>tar-file</code>：<a href="https://cryptodeeptech.ru/sage-9.3-Ubuntu_20.04-x86_64.tar.bz2" target="_blank" rel="noreferrer noopener"><strong>sage-9.3-Ubuntu_20.04-x86_64.tar.bz2</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!wget https://cryptodeeptech.ru/sage-9.3-Ubuntu_20.04-x86_64.tar.bz2
!tar -xf sage-9.3-Ubuntu_20.04-x86_64.tar.bz2</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2612} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-29-1024x321.png" alt="在 Google Colab 中安裝 SageMath" class="wp-image-2612"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>讓我們瀏覽一下目錄：</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cd SageMath/</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2617} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-32-1024x110.png" alt="在 Google Colab 中安裝 SageMath" class="wp-image-2617"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>打開面板並轉到文件夾：<code>SageMath</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2619} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-34.png" alt="在 Google Colab 中安裝 SageMath" class="wp-image-2619"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>檢查<code>Python-script:</code><strong>relocate-once.py是否存在</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2618} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-33-1024x180.png" alt="在 Google Colab 中安裝 SageMath" class="wp-image-2618"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>使用以下命令運行<code>Python-script:</code><strong>relocate-once.py ：</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!python3 relocate-once.py</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2620} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-35-1024x451.png" alt="在 Google Colab 中安裝 SageMath" class="wp-image-2620"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong>一切準備就緒！</strong></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>現在讓我們運行<code>SageMath</code>命令：</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!./sage -sh</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2623} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-36-1024x304.png" alt="在 Google Colab 中安裝 SageMath" class="wp-image-2623"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>讓我們運行版本檢查命令：</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sage -v</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2624} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-37-1024x344.png" alt="在 Google Colab 中安裝 SageMath" class="wp-image-2624"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong>好的！</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>我們有一個新版本：&nbsp;<code>SageMath version 9.3, Release Date: 2021-05-09</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>實現<a href="https://cryptodeeptech.ru/twist-attack/" target="_blank" rel="noreferrer noopener">Twist Attack</a>算法，下載 &nbsp;<code>Python-script:</code><a href="https://github.com/demining/CryptoDeepTools/blob/bbd83042e7405508cd2e646ad1b0819da0f9c58d/18TwistAttack/discrete.py" target="_blank" rel="noreferrer noopener">discrete.py</a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>wget https://raw.githubusercontent.com/demining/CryptoDeepTools/bbd83042e7405508cd2e646ad1b0819da0f9c58d/18TwistAttack/discrete.py</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2628} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-41-1024x517.png" alt="在 Google Colab 中安裝 SageMath" class="wp-image-2628"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>要求解離散對數，&nbsp;<em><code>(Pollard's rho algorithm for logarithms)</code></em>&nbsp;請運行&nbsp;<code>Python-script:</code><a href="https://github.com/demining/CryptoDeepTools/blob/bbd83042e7405508cd2e646ad1b0819da0f9c58d/18TwistAttack/discrete.py" target="_blank" rel="noreferrer noopener">discrete.py</a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>現在，要獲取私鑰，我們只需要運行命令：</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 discrete.py</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2654} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-43-1024x548.png" alt="在 Google Colab 中安裝 SageMath" class="wp-image-2654"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong>Sage Math&nbsp;</strong><strong>9.3</strong>&nbsp;求解離散對數問題&nbsp;<em><code>(Pollard's rho algorithm for logarithms)</code></em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><br>現在一切正常！</strong></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>我們收到了十進制格式的比特幣錢包私鑰，然後我們需要按照專門針對&nbsp;<strong><a href="https://cryptodeeptech.ru/twist-attack/" target="_blank" rel="noreferrer noopener">Twist 攻擊的文章的說明進行密碼分析</a></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/Install-SageMath-in-Google-Colab" target="_blank" rel="noreferrer noopener">來源</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">電報：https://t.me/cryptodeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://youtu.be/DBu0UnVe0ig" target="_blank" rel="noreferrer noopener">視頻素材：https://youtu.be/DBu0UnVe0ig</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/install-sagemath-in-google-colab" target="_blank" rel="noreferrer noopener">來源：https://cryptodeep.ru/install-sagemath-in-google-colab</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2669} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/037-1-1024x576.png" alt="在 Google Colab 中安裝 SageMath" class="wp-image-2669"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">密碼分析</a></p>
<!-- /wp:paragraph -->
