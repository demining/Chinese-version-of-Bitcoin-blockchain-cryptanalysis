<!-- wp:paragraph -->
<p>目前，機器學習和深度學習已成為計算機科學行業最熱門的趨勢。許多開發人員使用 Google Colab 創建了令人驚嘆的項目。</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>什麼是 Google Colab？</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>Google Colab 由 Google 開發，旨在提供對 GPU 和 TPU 的免費訪問。Google Colab 可以定義為 Jupyter Notebook 的改進版。</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>Google Colab 的特點</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>Google Colab 提供了許多現代 IDE 提供的很酷的功能。</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>您無需在本地安裝即可編寫和運行 Python 3 代碼。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>您可以從 Kaggle 等外部來源導入數據集。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>您可以將您的工作保存到 Google 雲端硬盤。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>您可以從 Google 雲端硬盤導入您的作品。</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Google Colab 還提供免費的雲服務、GPU 和 TPU，並與 PyTorch、Tensor Flow、Open CV 集成，但最重要的是，您可以直接從 GitHub 導入或發布您的項目。</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>讓我們運行命令</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>!cat /etc/lsb-release</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>DISTRIB_ID=UbuntuDISTRIB_RELEASE=18.04DISTRIB_CODENAME=仿生DISTRIB_DESCRIPTION=”Ubuntu 18.04.5 LTS”</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>所以我們確保我們有<strong>&nbsp;“Ubuntu 18.04.5 LTS”</strong>。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>唯一剩下要做的就是為&nbsp;<strong>JSON-RPC</strong>服務找到一個命令行解釋器。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>在網上沖浪時，我遇到了&nbsp;<strong>jQuery Terminal Emulator</strong>插件。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>接下來，我粘貼了 JS Shell 代碼：</em></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/2d4/0b5/069/2d40b5069b1d3c566a225d7f1d93211d.png" alt="我們在 Google Colab 中創建自己的終端，以便在 GitHub、GDrive、NGrok 等中工作。"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><em>這是一些帶有默認模塊的 Python 代碼</em></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/803/3b6/c4e/8033b6c4e41df6312566d5e4d0cb655c.png" alt="我們在 Google Colab 中創建自己的終端，以便在 GitHub、GDrive、NGrok 等中工作。"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><em>接下來</em>&nbsp;google.colab.kernel.invokeFunction('shell', [command])</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>通過命名問候&nbsp;</em>語：'Terminal CryptoDeepTech'</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>提示：'加密&gt;</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/7b5/e31/b2d/7b5e31b2d08f84b29a1dfeabd47cb9ed.png" alt="我們在 Google Colab 中創建自己的終端，以便在 GitHub、GDrive、NGrok 等中工作。"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>在我們在&nbsp;</em><strong><em>Google Colab中獲得終端后，可以在</em></strong><strong><em>&nbsp;GitHub、GDrive、NGrok</em></strong><em>&nbsp;中工作</em><strong><em></em></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><strong>源代碼：&nbsp; https:&nbsp;<a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener">//github.com/demining/TerminalGoogleColab</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>電報：&nbsp; https:&nbsp;<a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">//t.me/cryptodeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>視頻素材：&nbsp; https:&nbsp;<a href="https://youtu.be/S2D7PI6dK08" target="_blank" rel="noreferrer noopener">//youtu.be/S2D7PI6dK08</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/S2D7PI6dK08","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/S2D7PI6dK08
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">密碼分析</a></p>
<!-- /wp:paragraph -->
