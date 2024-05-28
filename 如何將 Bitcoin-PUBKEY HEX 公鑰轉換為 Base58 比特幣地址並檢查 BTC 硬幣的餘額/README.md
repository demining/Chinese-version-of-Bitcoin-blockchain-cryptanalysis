<!-- wp:embed {"url":"https://www.youtube.com/embed/Hsk6QIzb7oY","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/Hsk6QIzb7oY
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/main/03CheckBitcoinAddressBalance/bitcoin-checker.py">在本文中，我們將學習如何使用bitcoin-checker.py&nbsp;</a><em>Python 腳本</em>&nbsp;來檢查大量數據中的比特幣硬幣餘額&nbsp;。<a href="https://github.com/demining/CryptoDeepTools/blob/main/03CheckBitcoinAddressBalance/bitcoin-checker.py"></a></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/115/c50/ab8/115c50ab8b21651ae63d3cd8d3ecb98d.png" alt="檢查Python腳本bitcoin-checker.py的結果" title="檢查Python腳本bitcoin-checker.py的結果"/><figcaption class="wp-element-caption">檢查Python腳本bitcoin-checker.py的結果</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><br>我們還將學習如何將比特幣的公鑰轉換&nbsp;<code>PUBKEY (HEX)</code>&nbsp;為比特幣地址&nbsp;<code>(Base58)</code>&nbsp;所有這些大工作都是由&nbsp;<em>Python 腳本</em>&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/03CheckBitcoinAddressBalance/pubtoaddr.py" target="_blank" rel="noreferrer noopener">pubtoaddr.py完成的</a></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>因此，我們將通過在 Google Colab 終端&nbsp;<a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener">[TerminalGoogleColab]中掃描區塊鏈來輕鬆檢查比特幣餘額</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>早些時候我錄製了一個視頻教程：&nbsp;&nbsp;<a href="https://www.youtube.com/watch?v=S2D7PI6dK08" target="_blank" rel="noreferrer noopener">“Google Colab 中的 TERMINAL 為在 GITHUB 中工作創造了所有便利”</a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>讓我們轉到&nbsp;<a href="https://github.com/demining/CryptoDeepTools/tree/main/03CheckBitcoinAddressBalance" target="_blank" rel="noreferrer noopener">“CryptoDeepTools”</a>存儲庫&nbsp;，仔細看看&nbsp;<em>Bash 腳本的工作原理：</em><a href="https://github.com/demining/CryptoDeepTools/blob/main/03CheckBitcoinAddressBalance/getbalance.sh" target="_blank" rel="noreferrer noopener">getbalance.sh</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>命令：</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/03CheckBitcoinAddressBalance/

sudo apt install python2-minimal

wget https://bootstrap.pypa.io/pip/2.7/get-pip.py

sudo python2 get-pip.py

pip3 install -r requirements.txt

chmod +x getbalance.sh

./getbalance.sh
</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/d45/57e/1ae/d4557e1ae1a44f4c54e688da3a4882c7.png" alt="文件" title="文件"/><figcaption class="wp-element-caption">文件</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/4ff/051/a09/4ff051a0999975eca9beb0b3f349896f.png" alt="我們的 Bash 腳本代碼：getbalance.sh" title="我們的 Bash 腳本代碼：getbalance.sh"/><figcaption class="wp-element-caption">我們的 Bash 腳本代碼：getbalance.sh</figcaption></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>grep 'PUBKEY = ' signatures.json &gt; pubkeyall.json</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>該實用程序&nbsp;<code>grep</code>&nbsp;將所有公鑰收集到一個公共文件中：&nbsp;<code>pubkeyall.json</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sort -u pubkeyall.json &gt; pubkey.json</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>該實用程序&nbsp;<code>sort</code>&nbsp;排序並刪除重複項，選擇唯一的公鑰並將結果保存到文件中：&nbsp;<code>pubkey.json</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>rm pubkeyall.json</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>該實用程序&nbsp;<code>rm</code>&nbsp;刪除&nbsp;<code>pubkeyall.json</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sed -i 's/PUBKEY = //g' pubkey.json</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>該實用程序&nbsp;<code>sed</code>&nbsp;擦除前綴&nbsp;<code>PUBKEY =</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 pubtoaddr.py</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>我們運行&nbsp;<em>Python 腳本</em>&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/03CheckBitcoinAddressBalance/pubtoaddr.py" target="_blank" rel="noreferrer noopener">pubtoaddr.py</a><code>pubkey.json</code>並將&nbsp;存儲比特幣公鑰的&nbsp;&nbsp;文件轉換為文件，&nbsp;<code>PUBKEY (HEX)</code>&nbsp;結果&nbsp;<code>addresses.json</code>&nbsp;將保存為比特幣地址&nbsp;<code>(Base58)</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>import</strong> hashlib
<strong>import</strong> base58
 
<strong>def</strong> <strong>hash160</strong>(hex_str):
    sha = hashlib.sha256()
    rip = hashlib.new('ripemd160')
    sha.update(hex_str)
    rip.update(sha.digest())
    <strong>return</strong> rip.hexdigest()  # .hexdigest() is hex ASCII
 
 
pub_keys = open('pubkey.json', 'r', encoding='utf-8')
new_file = open('addresses.json', 'a', encoding='utf-8')
compress_pubkey = False
 
<strong>for</strong> pub_key <strong>in</strong> pub_keys:
    pub_key = pub_key.replace('\n', '')
    <strong>if</strong> compress_pubkey:
        <strong>if</strong> (ord(bytearray.fromhex(pub_key&#91;-2:])) % 2 == 0):
            pubkey_compressed = '02'
        <strong>else</strong>:
            pubkey_compressed = '03'
        pubkey_compressed += pub_key&#91;2:66]
        hex_str = bytearray.fromhex(pubkey_compressed)
    <strong>else</strong>:
        hex_str = bytearray.fromhex(pub_key)
 
 
    key_hash = '00' + hash160(hex_str)
 
 
    sha = hashlib.sha256()
    sha.update(bytearray.fromhex(key_hash))
    checksum = sha.digest()
    sha = hashlib.sha256()
    sha.update(checksum)
    checksum = sha.hexdigest()&#91;0:8]
 
#   new_file.write("" + (base58.b58encode(bytes(bytearray.fromhex(key_hash + checksum)))).decode('utf-8'))
    new_file.write((base58.b58encode(bytes(bytearray.fromhex(key_hash + checksum)))).decode('utf-8') + "\n")
pub_keys.close()
new_file.close()</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>我們已經收到文件，&nbsp;現在我們將使用<a href="https://github.com/demining/CryptoDeepTools/blob/main/03CheckBitcoinAddressBalance/bitcoin-checker.py" target="_blank" rel="noreferrer noopener">bitcoin-checker.py&nbsp;</a><em>Python 腳本</em><code>addresses.json</code>&nbsp;檢查&nbsp;比特幣餘額<em></em>&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/03CheckBitcoinAddressBalance/bitcoin-checker.py" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>運行&nbsp;<em>Python 腳本</em>：&nbsp;<code>python2 bitcoin-checker.py</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>import</strong> sys
<strong>import</strong> re
<strong>from</strong> time <strong>import</strong> sleep

<strong>try</strong>:    # if is python3
    <strong>from</strong> urllib.request <strong>import</strong> urlopen
<strong>except</strong>: # if is python2
    <strong>from</strong> urllib2 <strong>import</strong> urlopen


<strong>def</strong> <strong>check_balance</strong>(address):

    #Modify the value of the variable below to False if you do not want Bell Sound when the Software finds balance.
    SONG_BELL = True

    #Add time different of 0 if you need more security on the checks
    WARN_WAIT_TIME = 0

    blockchain_tags_json = &#91; 
        'total_received',
        'final_balance',
        ]

    SATOSHIS_PER_BTC = 1e+8

    check_address = address

    parse_address_structure = re.match(r' *(&#91;a-zA-Z1-9]{1,34})', check_address)
    <strong>if</strong> ( parse_address_structure <strong>is</strong> <strong>not</strong> None ):
        check_address = parse_address_structure.group(1)
    <strong>else</strong>:
        print( "\nThis Bitcoin Address is invalid" + check_address )
        exit(1)

    #Read info from Blockchain about the Address
    reading_state=1
    <strong>while</strong> (reading_state):
        <strong>try</strong>:
            htmlfile = urlopen("https://blockchain.info/address/%s?format=json" % check_address, timeout = 10)
            htmltext = htmlfile.read().decode('utf-8')
            reading_state  = 0
        <strong>except</strong>:
            reading_state+=1
            print( "Checking... " + str(reading_state) )
            sleep(60*reading_state)

    print( "\nBitcoin Address = " + check_address )

    blockchain_info_array = &#91;]
    tag = ''
    <strong>try</strong>:
        <strong>for</strong> tag <strong>in</strong> blockchain_tags_json:
            blockchain_info_array.append (
                float( re.search( r'%s":(\d+),' % tag, htmltext ).group(1) ) )
    <strong>except</strong>:
        print( "Error '%s'." % tag );
        exit(1)

    <strong>for</strong> i, btc_tokens <strong>in</strong> enumerate(blockchain_info_array):

        sys.stdout.write ("%s \t= " % blockchain_tags_json&#91;i])
        <strong>if</strong> btc_tokens &gt; 0.0:
            print( "%.8f Bitcoin" % (btc_tokens/SATOSHIS_PER_BTC) );
        <strong>else</strong>:
            print( "0 Bitcoin" );

        <strong>if</strong> (SONG_BELL <strong>and</strong> blockchain_tags_json&#91;i] == 'final_balance' <strong>and</strong> btc_tokens &gt; 0.0): 
            
            #If you have a balance greater than 0 you will hear the bell
            sys.stdout.write ('\a\a\a')
            sys.stdout.flush()

            arq1.write("Bitcoin Address: %s" % check_address)
            arq1.write("\t Balance: %.8f Bitcoin" % (btc_tokens/SATOSHIS_PER_BTC))
            arq1.write("\n")
            arq1.close()
            <strong>if</strong> (WARN_WAIT_TIME &gt; 0):
                sleep(WARN_WAIT_TIME)

#Add the filename of your list of Bitcoin Addresses for check all.
<strong>with</strong> open("addresses.json") <strong>as</strong> file:
    <strong>for</strong> line <strong>in</strong> file:

    	arq1 = open('balance.json', 'a')
        address = str.strip(line)
        <strong>print</strong> ("__________________________________________________\n")
        
        check_balance(address)
<strong>print</strong> "__________________________________________________\n"
arq1.close()</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>結果，結果將保存在一個文件中：&nbsp;<code>balance.json</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/93a/f82/c34/93af82c3468566ef9f495d0732c9731c.png" alt="文件：balance.json" title="文件：balance.json"/><figcaption class="wp-element-caption">文件：balance.json</figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>現在我們了解到：</h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>將比特幣公鑰轉換&nbsp;<code>PUBKEY (HEX)</code>&nbsp;為比特幣地址&nbsp;<code>(Base58)</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>檢查比特幣硬幣的所有比特幣地址 (Base58)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>將此應用於密碼分析</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><strong>源代碼：&nbsp;&nbsp;</strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/03CheckBitcoinAddressBalance" target="_blank" rel="noreferrer noopener"><strong>https://github.com/demining/CryptoDeepTools/tree/main/03CheckBitcoinAddressBalance</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>電報：&nbsp; https:&nbsp;</strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener"><strong>//t.me/cryptodeeptech</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>視頻素材：&nbsp; https:&nbsp;</strong><a href="https://youtu.be/Hsk6QIzb7oY" target="_blank" rel="noreferrer noopener"><strong>//youtu.be/Hsk6QIzb7oY</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/Hsk6QIzb7oY","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/Hsk6QIzb7oY
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">密碼分析</a></p>
<!-- /wp:paragraph -->
