
# Vim 

Vimの操作一覧

---

### mode

|disp|mode|
|:-:|:-:|
|(i)|insert|  
|(n)|normal|  
|(v)|visual| 
|(c)|command| 
|(w)|whenever|

### operate

|意味|command|full name|
|:-:|:-:|:-:|
|変更|c|change|  
|削除|d|delete| 
|ヤンク|y|yank| 
|移動|g|go|
  
---

#	mode change 
* 挿入ノーマルモードに切り替え  
	(1回だけNormal Modeのコマンドを入力してInsert modeに戻る)  
	`<C-o>`
* カーソル位置の文字を削除して挿入  
	`s`
* カーソル位置の 1 行を削除して挿入モードに移る  
	`S`  
	`cc`  
* カーソル位置から行末まで削除して挿入モードに移る  
	`C`  
	`c$`
* 単語を削除してinsert mode  
	`c{commnad}`
* 行の先頭から挿入  
	`I`
* 行の最後に挿入  
	`A`
* 前の行に挿入  
	`O`
* 直前の選択範囲を再選択  
	`gv`
* 次の行と連結  
	`J`

---
#	move 移動系

* 指定行へ  
	`[line number]G`  
	`:[line number]`
* 定義されているキーワードへ  
	`<C-]>`
*	前の行の最初へ  
	`-`
*	次の行の最初へ  
	`+`
*	対応する括弧へ  
	`%`
* 前の文の先頭  
	`(`
* 次の文の先頭  
	`)`
* 前の段落の先頭  
	`{`
* 次の段落の先頭  
	`}`
* 変更した場所に戻る (n)  
	`g;`
* 変更した場所に進む (n)  
	`g,`
	
*	スクリーンの上端の行へ移動（2Hで2行目）  
	`H`
*	スクリーンの中央行へ移動  
	`M`
*	スクリーンの下端の行へ移動（2Lで下から2行目）  
	`L`
*	スクリーン幅の中央へ移動（行中の横移動）  
	`gm`
*	前回のジャンプ位置に戻る  
	`<C-o>`
*	次回のジャンプ位置に進む  
	`<C-i>`
* カレント行が画面のトップになる  
	`z<Enter>	`
*	カレント行が画面の中央になる  
	`zz`

* カーソル位置の宣言位置にジャンプ(Program)  
	`gd (local変数)`  
	`gd (global変数)`
* カーソル位置のファイル名にジャンプ  
	`gf`

* 表示行で移動  
	`g{j,k,0,^,$}`

---
#	move 移動系(横)

* 行頭へ移動  
	`|`  
* 行頭がタブの場合、タブの右側へ移動  
	`_`
* 行末へ移動  
	`$`
*	次の単語の先頭に移動
 - 英字と記号を区別する  
 `w`  
 - 英字と記号を区別しない  
 `W`
*	前の単語の先頭に移動
 - 英字と記号を区別する  
 `b`
 - 英字と記号を区別しない  
 `B`
*	現在の単語もしくは次の単語の末尾に前進  
 - 英字と記号を区別する  
 `e`
 - 英字と記号を区別しない  
 `E`

* 前の単語の末尾に後退  
	`ge`
* 現在の単語の末尾に追加(組み合わせ)  
	`ea`
* 前の単語の末尾に追加(組み合わせ)  
	`gea`

---
# move 移動系(scroll)

*	1画面ずつ上へ  
	`<C-b>`
*	半画面ずつ上へ  
	`<C-u>`
*	1行ずつ上へ  
	`<C-y>`

*	1画面ずつ下へ  
	`<C-f>`
*	半画面ずつ下へ  
	`<C-d>`
*	1行ずつ下へ  
	`<C-e>`

*	n文字ずつ右へ  
	`zl`
*	半画面ずつ右へ  
	`zL`

*	n文字ずつ左へ  
	`zh`
*	半画面ずつ左へ  
	`zH`

---
# move 移動系(mark)

* 現在のカーソルをマーク  
	`m{letter}`
* 現在のカーソルをマーク(大文字:ファイル)  
	`m{letter}`
* マーク場所へジャンプ  
	<div>`{letter}</div>

* 現在のファイルで直前に行われたジャンプ以前にいた場所  
	<div>``</div>
* 直前に変更された場所  
	<div>`.</div>
* 直前に挿入された場所  
	<div>`^</div>
* 直前に変更もしくはヤンクが行われた先頭
	<div>'[</div>
* 直前に変更もしくはヤンクが行われた末尾
	<div>']</div>
* 直前のビジュアルな選択範囲の先頭
	<div>'<</div>
* 直前のビジュアルな選択範囲の末尾  
	<div>'></div>

---
# search 検索系

* 順方向検索  
 `/{letter}`

* 逆方向検索  
 `?{letter}`

* 検索中の移動
 - 順方向  
 `n`
 - 逆方向  
 `N`
 
* Option
 - 大文字, 小文字区別する  
	`\C`
 - 大文字, 小文字区別しない  
	`\c`

* command
 - 以後、大文字小文字を区別しないで検索するようになる  
	`:set ignorecase`   
  `:set ic` (短縮形)
 - 以後、大文字小文字を区別して検索するようになる  
	`:set noignorecase`  
	`:set noic` (短縮形)

* 正規表現
 + 正規表現の特殊文字除外  
	 以降の文字の特殊文字を`\`無しで使用可  
	`\v`
 + 正規表現の特殊文字除外(テキストそのものを検索)
	 以降の\以外の特殊文字を除外  
	`\V`
 + 正規表現[0-9A-Fa-f]の代わり  
  `\x`
 + 空白文字, 改行文字にmatch  
	\_s
 + match境界を指定  
	 - matchの先頭  
	  `\zs`
	 - matchの末尾  
	  `\ze`  
   > e.g.) text: The "hoge" is foo.  
			\v"[^"]"				=> "hoge"  
			\v"\zs[^"]+\ze"		 =>  hoge  

* 検索のmatch数を数える(nフラグは無視を意味)   
	:%s///gn
* 文字数を数える  
	:'<,'>s/./&/gn

* カーソル上の単語を検索 (n, v)  

||完全一致|部分一致|
|:-:|:-:|:-:|
|下方向|*|g*|
|上方向|#|g#|

* カーソル行の1文字検索

||一致文字の直前|一致文字の先頭|
|:-:|:-:|:-:|
|行末方向|t[string]|f[string]|
|行頭方向|T[string]|F[string]|

 > 最後に使用したf,t,F,Tコマンドを繰り返す  
	`;`  
 > 最後に使用したf,t,F,Tコマンドを向きを変えて繰り返す  
	`,`

---
# copy & paste

* Insert Modeでpaste  
	`<C-r>{register}`
	+ 無名レジスタをpaste  
	`<C-r>"`  
	+ ヤンクレジスタをpaste  
	`<C-r>0`
* register確認  
	`:reg`
* 無名registerをペースト(pと同等)  
	`""p`  
* ヤンクregisterをペースト(dコマンド等で上書きされない)  
	`"Op`
* 無名register '0'をペースト  
	`"0p`
* 無名register 'a'に現在の行をヤンク  
	`"ayy`
* 名前付きレジスタにヤンク  
	`"{alphabet}y{motion}`
	>e.g.) "ayiw
* 名前付きレジスタをペースト  
	`"{alphabet}p`
* 削除時にレジスタに保存させない(ブラックホールレジスタ)  
	`"_d{motion}`

* n行目を現在行の下にコピぺ  
	`:{n}t.`
* 現在行を{n}行目の下にコピぺ  
	`:t{n}`
*	現在行をコピぺ  
	`:t.		(≒ypp)`
* 現在行をファイルの先頭にコピぺ  
	`:'<,'>t0`
* 現在行をファイルの末尾にコピぺ  
	`:t$`
  > e.g.) TODOを含む行をファイル末尾にコピペ  
	`:g/TODO/t$`

---
# substitute 置換

* flag

|意味|フラグ|正式名|
|:-:|:-:|:-:|
|全てのmatchに適用|g|globally|
|実行か確認|c|confirm|
|match数を数える|n|number|
|エラー非表示|e|error|
|直前と同じフラグ|&|　|

* 特殊文字													

|意味|特殊文字|
|:-:|:-:|
|キャリッジリターン|\r|	
|タブ|\t|
|バックスラッシュ|\\|
|１つ目の部分マッチ|\1|
|２つ目の部分マッチ|\2|
|マッチしたパターン全体|\0, &|
|直前の置換の{string}を使用|~|
|vim scriptを評価|\={vim script}|

* 直前の置換を繰り返し  
	`g&			(≒ :%s//~/&)`
* カーソル上から入力分の置換(n)  
	`R{letter}`

* 大文字,小文字変換

||カーソル(n)|visual mode(v)|現在行(n)|motion|
|:-:|:-:|:-:|:-:|:-:|
|大文字変換||U|gUU|gU{motion}|
|小文字変換||u|guu|gu{motion}|
|toggle|~|~|g~~|g~{motion}|

* 文字列置換  
	`:%s/{before word}/{after word}`
  > e.g.) オプション(ファイル全体 g)(確認あり c)  
	`:%s/{before word}/{after word}/gc`
* 範囲置換
	> e.g.) 63~81行目を置換  
	`:63,81s/{before}{after}`  
	> e.g.) 選択範囲を置換  
	`:'<,'>s/{before}/{after}`


---
#	選択(motion)

* 記号で含まれた範囲を選択(記号含む)  
 `a`

* 記号で含まれた範囲を選択(記号含まない)  
 `i`

* motion 

|記号|意味||
|:-:|:-:|:-:|
|(, )|()カッコを含む|bに置き換え可能|
|{, }|{}カッコを含む|Bに置き換え可能|
|各種記号|カッコを含む|[, ], <, >, ', " 等|
|t|タグ||
|w|word + 前後どちらかの空白||
|W|WORD + 前後どちらかの空白||
|s|現在の文 + 前後どちらかの空白||
|p|現在の段落 + 前後どちらかの空白|　|

>e.g.)  

> * 単語を消して挿入  
	`ciw`  
* カーソル上の単語を削除 (n)  
	`daw`  
* カーソル上の単語を削除して挿入 (n)  
	`ciw`  
* カーソル上の単語を前方削除 (n)  
	`db`  
* カーソル上の単語を後方削除 (n)  
	`dw`  
* ""で囲まれた文字を削除 (n)  
	`di"`  
* メソッド削除 (n)  
	`dap`  
* タグの中身選択  
	`vit`  

## visual block(矩形選択)  

* Ctrl + v =>

	-  選択範囲の左端から各行に同じテキストを挿入する  
	`I`
	- 選択範囲の右端から各行に同じテキストを挿入する  
	`A`
	- 選択範囲のテキストを削除する  
	`d`
	- 選択範囲のテキストを削除し、選択範囲の左端から各行に同じテキストを挿入する  
		`c`

---
# window操作

* 空の横ウインドウを開く  
	`:new`
* 空の縦ウインドウを開く  
	`:vnew`
* ウインドウを横に分割  
	`:sp [file name]`
* ウインドウを縦に分割  
	`:vs [filename]`
* カーソルのあるウインドウを閉じる  
	`:close`  
	`:clo`(省略形)  
	`<C-w>c`
* カーソルのあるウインドウ以外を全部閉じる  
	`:only`  
	`:on`(省略形)  
	`<C-w>o`
* 次のウインドウに移動  
	`<C-w> w`
* 前のウインドウに移動  
	`<C-w> p`
* ウインドウ移動  
	`<C-w> h,i,j,k`

---
# tab操作

* 新しいタブでオープン  
	`:tabe[edit] {filename}`
* 現在のウインドウを独立したタブに移動する  
	`<C-w>T`
* タブclose  
	`:tabc[lose]`  
	`:tabc`(省略形)
* activeタブ以外close  
	`:tabo[nly]`  
	`:tabo`(省略形)

### tab切り替え 
* {N}番号のタブに切り替え  
	`:tabn[ext] {N}`  
	`:tabn {N}`(省略形)  
	`{N}gt`
* 次のタブに切り替え  
	`:tabn[ext]`  
	`:tabn`(省略形)   
	`gt`
* 前のタブに切り替え  
	`:tabp[revious]`  
	`:tabp`(省略形)  
	`gT`

||Command|
|:-:|:-:|
|左に移動|`<C-w>h`|
|下に移動|`<C-w>j`|
|上に移動|`<C-w>k`|
|右に移動|`<C-w>l`|
|次に移動|`<C-w>w`|

* Window自体の移動

||Command|
|:-:|:-:|
|左に移動|`<C-w>H`|
|下に移動|`<C-w>J`|
|上に移動|`<C-w>K`|
|右に移動|`<C-w>L`|
|回転|`<C-w>`|

### tabサイズ変更

||command|
|:-:|:-:|
|縦に最大化|`<C-w>_`|
|横に最大化|`<C-w> + pipe`|
|大きさを揃える|`<C-w>=`|
|幅を増やす|`<C-w>>`|
|幅を減らす|`<C-w><`|
|高さを増やす|`<C-w>+`|
|高さを減らす|`<C-w>-`|

---
# Macro

* macro記録  
	`q{register}`
* macro記録stop  
	`q`
* macro追記(大文字で同じ文字)  
	`q{REGISTER}`
* Macroレジスタ確認 Escは^で表示  
	`:reg {register}`
* macro実行  
	`@{register}`

### macroの直列実行と並列実行  

* 直列  
	{回数}@{register} -> 失敗したところで止まる  
* 並列  
	選択 + :normal @{register} -> 別々に判断  失敗したところは無視  
* 変数定義(n)  
	`:let {変数}`
* 変数挿入(i)  
	`<C-r>{変数}`
	
---
# Tips

* カーソルから行の先頭までの文字をすべて削除する (i)  
	`<C-u>`
* カーソル直前の単語を削除する (i)  
	`<C-w>`
* カーソル上の数字をインクリメント (n)  
	`<C-a>`
* カーソル上の数字をデリメント (n)  
	`<C-x>`
* Enter (w)  
	`<C-m>`
* Back (w)  
	`<C-h>`
* 前に開いたファイルを開く  
	`<C-^>`
* 簡単な計算を実行して挿入 (i)  
	`<C-r>=`
* 選択範囲に対してNormal Modeのコマンドを実行する  
	`:'<,'>normal {command}`
	>e.g.) 全部の末尾に;を追加して選択範囲を繰り返し
		A;<Esc>					一行に;追加
		VG							最後の行まで選択
		:'<,'>normal .	操作の繰り返し
* shellのコマンド実行  
	`:!{cmd}`
* shell mode (c)  
	`:shell`		exitでvimにreturn
* 選択範囲をsort  
	`選択 => :sort`
* grepの起源  
	`:g/re/p`			<= :globalコマンド + 正規表現 + :print
* マッチするラインを削除  
	`:g/{regular expression}/d`
* マッチするラインだけを残す  
	`:v/{regular expression}/d`


|自動補完 起動||
|:-:|:-:|
|汎用のキーワード|`<C-n>`|
|現在のバッファのキーワード|`<C-x><C-n>`|
|includeされてるファイルのキーワード|`<C-x><C-i>`|
|tagsファイルのキーワード|`<C-x><C-]>`|
|辞書のルックアップ|`<C-x><C-k>`|
|行全体を補完|`<C-x><C-l>`|
|ファイル名を補完|`<C-x><C-f>`|
|オムニ補完|`<C-x><C-o>`|

* スペルチェック言語選択  
	`:set spelllang=en_us`
	- 言語調べる  
	`:set spell-remarks`

* スペルチェック 起動  
	`:set spell`  <=> `:set nospell`

|spell check|command|
|:-:|:-:|
|次のスペルミスにジャンプ|]s|
|前のスペルミスにジャンプ|[s|
|現在の単語修正候補を表示|z=|
|現在の単語をスペルファイルに追加|zg|
|現在の単語をスペルファイルから削除|zw|
|現在の単語に関してzgコマンドもしくはzwコマンドをundo|zug|

* 直前に挿入した文字を挿入 (i)  
	`<C-a>`
* 直前に挿入した文字を挿入してinsert終了 (i)  
	`<C-@>`
* サスペンド  
	`<C-z>`
* 全体をインデント整形  
	`gg=G`
* 再描画  
	`<C-l>`
* 開く時に指定行で開く  
	`$ vim +[line number] ~/[file name]`  
	`$ vim -c [line number] ~/[file name]`  
	>e.g.)  
		$ vim +123 ~/.hoge.txt  
		$ vim -c 123 ~/.hoge.txt

* ファイルごとに情報(ヤンク等のレジスタや履歴を保存する)
 - 元ファイル
	 - `:wv`
 - 利用ファイル
	 - `:rv!`

# vimrc keymap

## mode

|mode|再割当無し|再割当有り|
|:-:|:-:|:-:|
|normal + visual|noremap|map|
|command line + insert|noremap!|map!|
|normal|nnoremap|nmap|
|visual|vnoremap|vmap|
|command line|cnoremap|cmap|
|insert|inoremap|imap|

## mark

|表記|意味|
|:-:|:-:|
|`<Up>`             |上|
|`<Down>`           |下|
|`<Left>`           |左|
|`<Right>`          |右|
|`<F1> - <F12>`     |Function 1~12|
|`<Help>`           |Help|
|`<Undo>`           |Undo|
|`<Insert>`         |Insert|
|`<Home>`           |Home|
|`<End>`            |End|
|`<PageUp>`         |Page up|
|`<PageDown>`       |Page down|
|`<kHome>`          |テンキーのホーム(左上)|
|`<kEnd>`           |テンキーのエンド(左下)|
|`<kPageUp>`        |テンキーのページアップ(右上)|
|`<kPageDown>`      |テンキーのページダウン(右下)|
|`<kPlus>`          |テンキーの+|
|`<kMinus>`         |テンキーの-|
|`<kMultiply>`      |テンキーの \*|
|`<kDivide>`        |テンキーの /|
|`<kEnter>`         |テンキーのEnter|
|`<kPoint>`         |テンキーのピリオド|
|`<k0> - <k9>`      |テンキーの0から9|
|`<S-?>`            |Shift + 任意のキー|
|`<C-?>`            |Ctrl + 任意のキー|
|`<M-?>`            |Alt or Meta + 任意のキー|
|`<A-?>`            |<M-...>と同じ + 任意のキー|
|`<D-?>`            |Command(mac) + 任意のキー|
|`<t_xx>`           |termcapで"xx"エントリを持つキー|
