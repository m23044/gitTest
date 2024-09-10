![](output/media/media/image3.png){width="1.55in"
height="0.8211920384951881in"}

プログラミングの仕方

PlatformIOでATmega328P-PUのプログラミングをする

![](output/media/media/image4.png){width="0.83in"
height="0.5237664041994751in"}

-   目次

＜[イントロダクション](#イントロダクショ)＞

-   [はじめに](#はじめに)

-   [用意するもの](#用意するもの)

＜[PlatformIOの導入](\l)＞

-   [Visual Studio CodeとPythonの導入](#VSCodeとPythonの導入)

-   [Visual Studio Codeの設定](#VSCodeの設定)

-   [PlatformIOの導入](#PlatformIOの導入)

＜[プロジェクトの作成](\l)＞

-   [プロジェクトの作成（選択肢１）](#プロジェクトの作成（選択肢１）)

-   [プロジェクトの取得（選択肢２）](#プロジェクトの取得（選択肢２）)　※ロボコン2024年の部員向け※

＜[マイコンで動かす](\l)＞

-   [プログラムのビルド](#プログラムのビルド)

-   [プログラムのアップロード](#プログラムのアップロード)

＜[プログラミング](#プログラミング（章）)＞

-   [プログラムの説明](#プログラムの説明)

-   [フォルダとファイルの構成](#フォルダとファイルの構成)

＜[共同開発](\l)＞

-   [共同開発の環境構築](#共同開発の環境構築)

-   

-   [リポジトリの作成（選択肢１）]()[リポジトリの共有（選択肢１）](#リポジトリの共有（選択肢１）)

-   [自分によるプログラムの変更を他人に適用させる](#自分によるプログラムの変更を他人に適用させる)

-   [他人によるプログラムの変更を自分に適用させる](#_Hlk175826784)

-   [1つのファイルを複数人が同時に編集する](#一つのファイルを複数人が同時に編集する)

＜[コンクルージョン](#コンクルージョン（章）)＞

-   [最後に](#最後に)

-   [クレジット](#クレジット)

![挿絵 が含まれている画像
自動的に生成された説明](output/media/media/image3.png){width="1.55in"
height="0.8211920384951881in"}

[]{#イントロダクショ .anchor} イントロダクション

![アイコン
中程度の精度で自動的に生成された説明](output/media/media/image4.png){width="0.83in"
height="0.5237664041994751in"}

-   []{#はじめに .anchor}はじめに

> Arduino
> IDEだと、タイプミスをしてもエラー表示が出なかったり、タイピング中に候補が出てこなかったりする。PlatformIOと比べて取っつきやすい反面、使いにくい点が多い。そこで、PlatformIOを使おうと考えた。
>
> 僕がやろうと言い出した分、他のメンバーに使い方を説明する責任が僕自身に生じた。加えて、来年僕はいないので後輩に知識の引継ぎをしたいと考えた。それらの経緯から本資料を作成した。
>
> この資料はとても長い。なので、目次を見て、興味のあるとこらから読むのをお勧めする。また、この資料を見てわからないところがあったり、読むのが面倒だと感じたりする場合は、遠慮なく僕に相談してほしい。

-   []{#用意するもの .anchor}用意するもの

    -   パソコン

    -   ATmega328P-PU

    -   ブレッドボード

    -   ジャンパーワイヤー

    -   ISP USBケーブル

    -   やる気

    -   気合

    -   根性

    -   パワー

![挿絵 が含まれている画像
自動的に生成された説明](output/media/media/image3.png){width="1.55in"
height="0.8211920384951881in"}

PlatFOrmIOの導入

![アイコン
中程度の精度で自動的に生成された説明](output/media/media/image4.png){width="0.83in"
height="0.5237664041994751in"}

-   []{#VSCodeとPythonの導入 .anchor}Visual Studio CodeとPythonの導入

> PlatformIOの導入方法は[このサイト](https://logikara.blog/install_platform/)が参考になる。Visual
> Studio CodeとPythonをインストールし、Visual Studio
> Codeの拡張機能としてPlatformIOをインストールする必要があるとのこと。このセクションでは、Visual
> Studio
> CodeとPythonの導入方法を説明する。ただ、この２つの導入方法については、調べたら簡単にでてくるので軽く説明するだけにする。
>
> まず、インストーラーをダウンロードする必要がある。インストーラーは、[ここ](https://code.visualstudio.com/)と[ここ](https://www.python.org/downloads/)にアクセスして、ダウンロードできそうなボタンを適当に押せば、ダウンロードすることができる。これ![](output/media/media/image5.jpeg){width="0.6336636045494313in"
> height="0.16488188976377952in"}とか、これ![](output/media/media/image6.jpeg){width="0.5923611111111111in"
> height="0.15328412073490813in"}のことである。
>
> 次に、Windows上のこんな感じのアイコン![](output/media/media/image7.png){width="0.15722331583552057in"
> height="0.15028871391076115in"}をクリックして、エクスプローラーと呼ばれる画面を表示させ、![](output/media/media/image8.png){width="0.7086953193350831in"
> height="0.1267771216097988in"}をクリックし、ダウンロードフォルダを開く。
>
> ![](output/media/media/image9.tmp){width="5.905555555555556in"
> height="0.7965277777777777in"}
>
> そうすると、先ほどダウンロードしたインストーラー２つが表示されるはずなので、それぞれクリックしてインストールを開始する。インストーラーから何か訊かれると思う。基本的に適当に肯定的な返答をしたら問題ないはずだが、Pythonの場合に関しては![](output/media/media/image10.tmp){width="1.1576574803149606in"
> height="0.13375328083989502in"}というところに☑を入れるようにしてほしい。
>
> インストールが終わると、パソコンのどこか（例えばインストールされたアプリを検索する画面など![](output/media/media/image11.png){width="0.32085629921259845in"
> height="0.15609251968503937in"}）にVisual Studio
> Codeのアイコン![](output/media/media/image12.png){width="0.18479768153980752in"
> height="0.16577537182852142in"}があるはずなので、それをクリックして起動させてほしい。Visual
> Studio
> Codeインストール直後の初めての起動になるので、何かしらの設定を要求されるかもしれないが、それは適当にやってほしい。

-   []{#VSCodeの設定 .anchor}Visual Studio Codeの設定

> 　Visual Studio
> Codeを起動させる。左角の![](output/media/media/image13.tmp){width="0.17331036745406825in"
> height="0.16577537182852142in"}から![](output/media/media/image14.png){width="0.33155074365704285in"
> height="0.1630566491688539in"}を開く。
>
> ![コンピューターのスクリーンショット
> 自動的に生成された説明](output/media/media/image15.png){width="5.905555555555556in"
> height="3.321527777777778in"}
>
> ここで、『auto save』と『format on
> save』を検索し、それぞれ有効化する。
>
> ![設定 - Tutorial - Visual Studio
> Code](output/media/media/image16.png){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> ![設定 - Tutorial - Visual Studio
> Code](output/media/media/image17.png){width="5.905555555555556in"
> height="3.3222222222222224in"}

-   []{#PlatformIOの導入 .anchor}PlatformIOの導入

> Visual Studio Code を起動させる。Visual Studio
> Codeの左端にある![](output/media/media/image18.png){width="0.1604265091863517in"
> height="0.1711220472440945in"}をクリックすると、拡張機能を検索する画面が出てくる。ここで、『platformio』と検索すると、蟻と宇宙人を合成したような見た目をした生命体のロゴ![](output/media/media/image19.png){width="0.17800524934383202in"
> height="0.17153324584426946in"}が出現する。それをクリックすると、インストールという選択肢が見えるはずである。その選択肢を押してほしい。ちなみに、これと同じように『japan』と検索しインストールすれば、Visual
> Studio Codeを日本語にすることができる。
>
> ![](output/media/media/image20.tmp){width="1.74996719160105in"
> height="1.3294794400699912in"}　![](output/media/media/image21.tmp){width="1.761253280839895in"
> height="1.3294805336832896in"}　![グラフィカル ユーザー
> インターフェイス, テキスト
> 自動的に生成された説明](output/media/media/image22.tmp){width="1.809248687664042in"
> height="1.3545505249343832in"}
>
> 後はいい感じに待てば、PlatformIOの導入は完了である。これでプログラムをする環境は整った。

![挿絵 が含まれている画像
自動的に生成された説明](output/media/media/image3.png){width="1.55in"
height="0.8211920384951881in"}

プロジェクトの作成

![アイコン
中程度の精度で自動的に生成された説明](output/media/media/image4.png){width="0.83in"
height="0.5237664041994751in"}

-   []{#プロジェクトの作成（選択肢１）
    .anchor}プロジェクトの作成（選択肢１）

> 　Visual Studioを起動させる。左側にある![挿絵, ボール
> が含まれている画像
> 自動的に生成された説明](output/media/media/image23.tmp){width="0.14872156605424322in"
> height="0.15444225721784777in"}を押し、![](output/media/media/image24.tmp){width="1.2299464129483815in"
> height="0.1210586176727909in"}の表示か消えるのを待つ。パソコンによるかもしれないが、１分もしないはずである。
>
> ![ようこそ - Visual Studio
> Code](output/media/media/image25.png){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> 数秒待つと、このような画面に切り替わる。ここで、![](output/media/media/image26.tmp){width="1.38502624671916in"
> height="0.1472769028871391in"}をクリックする。
>
> ![ようこそ - Visual Studio
> Code](output/media/media/image27.tmp){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> ![テキスト
> 自動的に生成された説明](output/media/media/image28.tmp){width="1.2498228346456692in"
> height="0.19786089238845145in"}をクリックする。
>
> ![PIO Home - Visual Studio
> Code](output/media/media/image29.png){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> プロジェクト名、Board（説明できないから言い換えない...）、Framework（説明できないから言い換えない...）を入力する。プロジェクト名以外は写真と同じようにする。入力したら、![PIO
> Home - Visual Studio
> Code](output/media/media/image30.png){width="0.3065693350831146in"
> height="0.13868657042869642in"}をクリックする。
>
> ![PIO Home - Visual Studio
> Code](output/media/media/image31.png){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> 　しばらく待つと![](output/media/media/image32.tmp){width="0.7688232720909887in"
> height="0.14963582677165355in"}ファイルが開かれた状態になる。ここで、以下と同じになるように書き換える。
>
> ![platformio.ini - Tutorial - Visual Studio
> Code](output/media/media/image33.tmp){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> ![](output/media/media/image34.tmp){width="0.3352252843394576in"
> height="0.138996062992126in"}をクリックし、展開する。画像のように右クリックでcontorllerフォルダとrobotフォルダを作成する。
>
> ![main.cpp - Tutorial - Visual Studio
> Code](output/media/media/image35.tmp){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> 作成した２つのフォルダそれぞれの中に、右クリックで![](output/media/media/image36.tmp){width="0.5212357830271216in"
> height="0.14760608048993876in"}ファイルをコピー＆ペーストする。コピー元の![](output/media/media/image36.tmp){width="0.5212357830271216in"
> height="0.14760608048993876in"}は削除する。プログラムは、この２つのファイルに書き加えていく形になる。プログラムの書き方の詳しい説明は、別のセクションで行う。
>
> ![main.cpp - Tutorial - Visual Studio
> Code](output/media/media/image37.tmp){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> 　最後に、![](output/media/media/image38.tmp){width="0.620252624671916in"
> height="0.15075568678915136in"}ファイルをプロジェクト直下に作成し、『BasedOnStyle:
> LLVM』と入力する。
>
> ![.clang-format - Tutorial - Visual Studio
> Code](output/media/media/image39.png){width="5.905555555555556in"
> height="3.3222222222222224in"}

-   []{#プロジェクトの取得（選択肢２）
    .anchor}プロジェクトの取得（選択肢２）

> 　『選択肢１』では、自分でプロジェクトを作成したが、このセクションでは『他人が作成した既存のプロジェクトを取得する方法』について説明する。一応、2024年のロボコンのプログラミングをする人を対象としているが、そうでない人でも参考になる内容となっている。
>
> 　Visual
> Studioを起動させる。もし、既に何らかのファイルを開いてしまっている場合は『![](output/media/media/image40.tmp){width="0.40594050743657045in"
> height="0.1324650043744532in"} -\>
> ![](output/media/media/image41.png){width="1.7509919072615923in"
> height="0.13366360454943133in"}』をクリックし、Visual Studio
> Codeを新たに立ち上げる。次に、左上にある![](output/media/media/image42.png){width="0.13282370953630795in"
> height="0.13469378827646544in"}が選択されていることを確認し、![](output/media/media/image43.png){width="1.149790026246719in"
> height="0.158416447944007in"}をクリックして、テキスト入力ができる画面を表示させる。
>
> ![](output/media/media/image44.png){width="5.905555555555556in"
> height="3.321527777777778in"}
>
> ここに、プログラミングをしたいロボットの『プログラムのURL』を貼り付けてほしい。そのURLは[このサイト](https://github.com/SoshiroFujimori?tab=repositories)から手に入れることができる。例えば、もしAチームの親鳥のプログラミングをしたい場合は、![](output/media/media/image45.tmp){width="1.5085389326334209in"
> height="0.1633672353455818in"}にカーソルを合わせ、右クリックをし、![](output/media/media/image46.png){width="0.9356441382327209in"
> height="0.168416447944007in"}を選択することでプログラムのURLを取得することができる。
>
> ![](output/media/media/image47.png){width="5.905555555555556in"
> height="3.321527777777778in"}
>
> 　URLを貼り付けるとこのような画面になるので![](output/media/media/image48.png){width="2.270203412073491in"
> height="0.15510170603674542in"}を選択する。
>
> ![](output/media/media/image49.png){width="5.905555555555556in"
> height="3.321527777777778in"}
>
> 選択すると、プログラムの保存場所を訊かれる。自分が分かる適当な場所を選んでほしい。ここでは![](output/media/media/image50.tmp){width="0.64081583552056in"
> height="0.15004483814523184in"}を選択した。![](output/media/media/image51.tmp){width="0.987341426071741in"
> height="0.16969925634295713in"}で画面を閉じる。
>
> ![](output/media/media/image52.png){width="5.905555555555556in"
> height="3.3208333333333333in"}
>
> ![](output/media/media/image53.tmp){width="1.257425634295713in"
> height="0.13182742782152232in"}と訊かれるので、![](output/media/media/image54.tmp){width="0.4207917760279965in"
> height="0.1323458005249344in"}を選ぶ。
>
> ![](output/media/media/image55.tmp){width="5.905555555555556in"
> height="3.3208333333333333in"}
>
> さらにこのような画面になるので、![](output/media/media/image56.tmp){width="1.361107830271216in"
> height="0.18863188976377954in"}を選択する。
>
> ![ようこそ - robocon2024-a-team-big-bird - Visual Studio
> Code](output/media/media/image57.tmp){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> 　これで、プログラムの取得は完了である。

![挿絵 が含まれている画像
自動的に生成された説明](output/media/media/image3.png){width="1.55in"
height="0.8211920384951881in"}

マイコンで動かす

![アイコン
中程度の精度で自動的に生成された説明](output/media/media/image4.png){width="0.83in"
height="0.5237664041994751in"}

-   []{#プログラムのビルド .anchor}プログラムのビルド

1.  マイコンをパソコンにつなげる。

2.  （ロボット本体のプログラムをビルドする場合）

右上の![](output/media/media/image58.tmp){width="0.21873468941382326in"
height="0.17088582677165354in"}を押す。

![PIO Home - robocon2024-a-team-big-bird - Visual Studio
Code](output/media/media/image59.png){width="5.905555555555556in"
height="3.3222222222222224in"}

3.  （コントローラーのプログラムをビルドする場合）

『左中央にある![](output/media/media/image60.png){width="0.12448600174978128in"
height="0.15471784776902886in"} -\>
![](output/media/media/image61.tmp){width="0.564815179352581in"
height="0.1300787401574803in"} -\>
![](output/media/media/image62.tmp){width="0.5416666666666666in"
height="0.12985126859142607in"} -\>
![](output/media/media/image63.tmp){width="0.3796292650918635in"
height="0.12534886264216974in"}』の順でクリックする。

![PIO Home - robocon2024-a-team-big-bird - Visual Studio
Code](output/media/media/image64.png){width="5.905555555555556in"
height="3.3222222222222224in"}

-   []{#プログラムのアップロード .anchor}プログラムのアップロード

> 通常のマイコンにアップロードする（書き込む）場合、先ほどのセクションの画面にある![](output/media/media/image65.png){width="0.935184820647419in"
> height="0.12066929133858267in"}や![](output/media/media/image66.png){width="0.37173009623797026in"
> height="0.12036964129483814in"}を押すだけで良い。しかし、今回使用するマイコン（ATmega328P-PU）はその機能性から、アップロードするにはひと手間かかる。
>
> ![コンピューターのスクリーンショット
> 自動的に生成された説明](output/media/media/image67.png){width="5.905555555555556in"
> height="3.321527777777778in"}
>
> ![コンピューターのスクリーンショット
> 自動的に生成された説明](output/media/media/image68.png){width="5.905555555555556in"
> height="3.321527777777778in"}
>
> 　まず、書き込み用の回路を作成する必要がある。こんな感じのやつだ。写真では余分な配線があるのでややこしいが（写真は更新予定）、ATmega328P-PUの特定のピンから6本線を出し、その6本を受けとるISP-USBとかいうケーブルにつなげる。よくわからなければ（よくわからないので）、"あの先生"
> に訊いてほしい。本人の許諾を得れていないので名前は伏せておく。
>
> ![ケーブル, テーブル, 回路, コンピュータ が含まれている画像
> 自動的に生成された説明](output/media/media/image69.jpeg){width="2.0305555555555554in"
> height="2.436765091863517in"}　![](output/media/media/image70.jpeg){width="2.0146839457567802in"
> height="2.6866404199475067in"}
>
> 次に、書き込み用のソフトをダウンロードする必要がある。[ここ](https://github.com/ioelectro/avr-progisp-programmer/raw/main/Software/Prog%20ISP%20Ver%201.72.zip)にアクセスしzipファイルをダウンロードする。ダウンロードしたファイルは展開し、それによって生成されたフォルダに含まれる![](output/media/media/image71.tmp){width="0.46803258967629047in"
> height="0.14327537182852143in"}という実行ファイルをクリックする。
>
> ![Prog ISP Ver 1.72 -
> エクスプローラー](output/media/media/image72.tmp){width="5.905555555555556in"
> height="3.3256944444444443in"}
>
> クリックするとこのような画面で起動する。インストーラー版ではなく、ポータブル版であるのでインストールという工程は無いのだ。画像と同じ設定にする。
>
> ![PROGISP (Ver
> 1.72)](output/media/media/image73.tmp){width="3.9108912948381453in"
> height="2.7128707349081367in"}
>
> 続いて、16進数部分![](output/media/media/image74.tmp){width="0.35066054243219597in"
> height="0.1485148731408574in"}をクリックし、![](output/media/media/image75.tmp){width="0.5416940069991251in"
> height="0.15278543307086614in"}を『E2』にする。
>
> ![PROGISP (Ver
> 1.72)](output/media/media/image73.tmp){width="2.6833858267716537in"
> height="1.861385608048994in"}　![グラフィカル ユーザー
> インターフェイス, アプリケーション, テーブル
> 自動的に生成された説明](output/media/media/image76.png){width="2.8052405949256345in"
> height="1.65456583552056in"}
>
> 先ほど作成した書き込み用の回路をパソコンにUSB接続し、画像の工程を踏む。
>
> ![グラフィカル ユーザー インターフェイス, アプリケーション
> 自動的に生成された説明](output/media/media/image77.tmp){width="3.9305555555555554in"
> height="2.7006386701662293in"}
>
> 　プログラムをビルドすることによって生じたhexファイルを選択する。そのファイルは『プログラムのフォルダ\\.pio\\build\\』の何処かにある。僕の場合、『D:\\デスクトップ\\robocon2024-a-team-big-bird\\.pio\\build\\controller\\firmware.hex』にあった。
>
> ![開く](output/media/media/image78.tmp){width="3.9090912073490816in"
> height="2.9732622484689415in"}
>
> 　最後に、![](output/media/media/image79.tmp){width="0.5845767716535433in"
> height="0.16577537182852142in"}でマイコンにアップロードすることができる。
>
> ![グラフィカル ユーザー インターフェイス, アプリケーション
> 自動的に生成された説明](output/media/media/image77.tmp){width="3.9305555555555554in"
> height="2.7006386701662293in"}

![挿絵 が含まれている画像
自動的に生成された説明](output/media/media/image3.png){width="1.55in"
height="0.8211920384951881in"}

[]{#プログラミング（章） .anchor}プログラミング

![アイコン
中程度の精度で自動的に生成された説明](output/media/media/image4.png){width="0.83in"
height="0.5237664041994751in"}

-   []{#プログラムの説明 .anchor}プログラムの説明

> このセクションでは『車のラジコンのプログラムの説明』を理解することで、『プログラムの書き方』を理解することを目指す。ファイルの構成はこのようになる。これから、ファイルごとにプログラムの解説をする。
>
> 同じプログラムは[ここ](https://github.com/SoshiroFujimori/Tutorial)でも読むことができる。プログラミングにある程度自信のある人は、このサイトで全体のプログラムをざっと読んで、わからないところの説明だけを読むのが良いかもしれない。
>
> ![main.cpp - Tutorial - Visual Studio
> Code](output/media/media/image80.tmp){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> 　controller/main.cppを見る。これはコントローラーのプログラムだ。コントローラーとは車を無線で操作するリモコンのことである。上の行から順番に説明していく。
>
> １～３行目では、他のファイルに書かれたコードを今のプログラムに読み込んでいる。
>
> ![](output/media/media/image81.tmp){width="0.824073709536308in"
> height="0.11986548556430446in"}はこのmain.cppと同じフォルダに位置するファイルであり、コントローラーの構造に関する情報を持つ。![](output/media/media/image81.tmp){width="0.824073709536308in"
> height="0.11986548556430446in"}に書かれている内容については後ほど説明する。
>
> ![](output/media/media/image82.tmp){width="1.4759361329833771in"
> height="0.10811023622047244in"}は[liboshima](https://github.com/SoshiroFujimori/liboshima/tree/master)の一部で、これをインクルードすることでIM920SLの送信機のプログラムを利用できる。
>
> ![](output/media/media/image83.tmp){width="0.5347594050743657in"
> height="0.12873797025371828in"}はArduino
> プログラムの基本的な機能を提供するヘッダーファイルである。このファイルには、Arduino
> ボードで使用される多くのコア機能やマクロが含まれており、例えばデジタルピンやアナログピンの制御、タイマー、シリアル通信、割り込み、基本的な定数（HIGH、LOW、INPUT、OUTPUTなど）を定義している（と思われる）。
>
> 　6～11行目で使われている![](output/media/media/image84.tmp){width="0.5231485126859142in"
> height="0.10341316710411198in"}は、プログラム内で特定の名前に数値を割り当てるための仕組みである。例えば、![](output/media/media/image85.tmp){width="0.9810181539807524in"
> height="0.12037073490813649in"}は『![](output/media/media/image86.tmp){width="0.19445428696412947in"
> height="0.12500656167979002in"}という名前が![](output/media/media/image87.tmp){width="0.24257436570428698in"
> height="0.14967300962379704in"}というピン番号を意味する』ように定義している。これによって、13行目の様に後のコードで![](output/media/media/image86.tmp){width="0.19445428696412947in"
> height="0.12500656167979002in"}と書くと、実際には![](output/media/media/image87.tmp){width="0.24257436570428698in"
> height="0.14967300962379704in"}というピン番号を指していることになる。
>
> 　13行目では、変数の作成が行われている。int型変数を作成する場合、『int
> a =
> 0;』というように、aという名前の変数を宣言し、中に0という数字を入れる。一方で![](output/media/media/image88.tmp){width="0.5668449256342957in"
> height="0.11451443569553806in"}型変数は、もっと複雑な情報を扱うため、作成するときは![](output/media/media/image89.tmp){width="1.4438495188101488in"
> height="0.12471784776902888in"}とする。
>
> この![](output/media/media/image90.tmp){width="0.5198020559930009in"
> height="0.1299507874015748in"}という部分では、型（どのような変数を作るか）を決めている。たとえば、int型では数字を扱う変数を作るのに対し、![](output/media/media/image90.tmp){width="0.5198020559930009in"
> height="0.1299507874015748in"}型では通信を扱うための変数を作る。![](output/media/media/image90.tmp){width="0.5198020559930009in"
> height="0.1299507874015748in"}型は、2行目で![](output/media/media/image91.tmp){width="2.1709372265966755in"
> height="0.1443853893263342in"}をしているため使用できる。
>
> ![](output/media/media/image92.tmp){width="0.5594061679790027in"
> height="0.14436351706036746in"}という部分は、作る変数の名前である。aが数字を入れる変数の名前だったのと同じように、![](output/media/media/image92.tmp){width="0.5594061679790027in"
> height="0.14436351706036746in"}は通信の情報を扱う変数の名前である。
>
> ![](output/media/media/image1.png)は、その変数を設定するときに必要な情報である。例えば、int
> 型変数には数字を入れるが、![](output/media/media/image90.tmp){width="0.5198020559930009in"
> height="0.1299507874015748in"}型変数には![](output/media/media/image93.tmp){width="0.15973097112860893in"
> height="0.1458409886264217in"}と![](output/media/media/image94.tmp){width="0.18056430446194227in"
> height="0.1458409886264217in"}というピン番号を設定する。
>
> 16～20行目では、最初に一度だけ実行される設定が書かれている。ここでは、ボタンからの入力を受け取れるようにピンの設定をする。
>
> 24～32行目では、ボタンが押されているかどうかを常に確認して、結果を送信する処理が繰り返し実行される。
>
> ![](output/media/media/image95.tmp){width="1.470297462817148in"
> height="0.15151902887139107in"}でController型変数を[c]{.underline}ontrollerという名前で作成している。Controller型は、１行目で![](output/media/media/image96.tmp){width="1.4010695538057742in"
> height="0.12877515310586177in"}をしているため使用できる。作成した変数の中には![](output/media/media/image97.tmp){width="1.1069510061242345in"
> height="0.12650918635170605in"}や![](output/media/media/image98.tmp){width="1.22459864391951in"
> height="0.12920056867891513in"}、![](output/media/media/image99.tmp){width="1.12834208223972in"
> height="0.10597769028871391in"}などボタンの数だけ変数があり、それぞれの変数に対し![](output/media/media/image100.tmp){width="3.1925131233595803in"
> height="0.14537839020122484in"}のようにして、１（押されている）か０（押されていない）を割り当てる。![](output/media/media/image101.tmp){width="1.6485148731408574in"
> height="0.16260826771653544in"}の部分は()内に示すボタンが押されている時１になり、逆に押されていないときは０になるのだ。
>
> 確認したコントローラーの情報（前進、後進、左、右のボタンの押し具合）を![](output/media/media/image102.tmp){width="1.5198020559930008in"
> height="0.1529669728783902in"}で車に送信し、![](output/media/media/image103.tmp){width="0.7574256342957131in"
> height="0.1356583552055993in"}で0.1秒ほど待ってから、また同じ確認と送信の繰り返しを行う。
>
> ![テキスト
> 自動的に生成された説明](output/media/media/image104.tmp){width="5.905555555555556in"
> height="3.1798611111111112in"}
>
> 　robot/main.cppを見る。
>
> 　１～９行目はcontorller/main.cppの説明を読むと分かると思うので省略する。ここでは、![](output/media/media/image92.tmp){width="0.5594061679790027in"
> height="0.14436351706036746in"}ではなく![](output/media/media/image105.tmp){width="0.5935826771653543in"
> height="0.1381616360454943in"}（IM920SLの受信機）になっていることに注意しよう。
>
> 　15～17行目では、コントローラーからの信号が届くまで待っている。この部分では、コントローラーが使える状態（![](output/media/media/image106.tmp){width="0.6531791338582678in"
> height="0.12465223097112861in"}）かどうかをチェックする。コントローラーが使えるまで、このコードは何度も100ミリ秒（0.1秒）待つ。
>
> 　19～20行目では、![](output/media/media/image107.tmp){width="0.6531791338582678in"
> height="0.12744969378827647in"}型の![](output/media/media/image108.tmp){width="0.826431539807524in"
> height="0.12500656167979002in"}という名前の変数を作成し、その変数に対しコントローラーからの信号を格納している。これで、コントローラーのボタンが押されているかどうかの情報が取得できる。
>
> 　22～34行目では、前進、後進、旋回の処理をしている。
>
> 　![](output/media/media/image109.tmp){width="1.2620319335083114in"
> height="0.13717738407699037in"}で前進ボタンが押されているかどうかをチェックする。押されていたら、![](output/media/media/image110.tmp){width="0.8556146106736658in"
> height="0.12595253718285215in"}を使いタイヤを前に進める。
>
> ![](output/media/media/image111.tmp){width="1.7540102799650044in"
> height="0.12603674540682414in"}では後進ボタンが押されているかどうかをチェックする。押されていたら、![](output/media/media/image112.tmp){width="0.9884383202099738in"
> height="0.12355533683289589in"}を使いタイヤを後ろに進める。
>
> どちらのボタンも押されていない場合は、![](output/media/media/image113.tmp){width="0.7398840769903762in"
> height="0.15694553805774278in"}を使いタイヤを止める。
>
> 30～34行目の旋回処理も、このようにして行われる。
>
> ![テキスト
> 自動的に生成された説明](output/media/media/image114.tmp){width="5.905555555555556in"
> height="3.4541666666666666in"}
>
> 　controller/Controller.hを見る。
>
> 　このコードは、コントローラーの状態を管理するための![](output/media/media/image115.tmp){width="0.6242782152230971in"
> height="0.1330424321959755in"}という型を定義している。この型は、コントローラーのボタンが押されているかどうかを保存するために使われる。この型は正確には『構造体』と呼ばれていて、複数の変数をまとめて1つの変数にするための仕組みを持つ。この場合、コントローラーの『前進』、『後進』、『左』、『右』の4つのボタン状態を1つにまとめている。
>
> 　6行目の![](output/media/media/image116.tmp){width="1.7225437445319336in"
> height="0.14647528433945756in"}では、『前進ボタン』が押されているかどうかを格納する変数が作成されている。ここで![](output/media/media/image117.tmp){width="0.8034678477690289in"
> height="0.1257130358705162in"}（符号なし整数）を使い、その後に![](output/media/media/image118.tmp){width="0.21965332458442693in"
> height="0.12259733158355206in"}という指定がある。これは『この変数には1ビットだけ使う』という意味である。つまり、『押されているか（1）』『押されていないか（0）』という2つの状態しか取らない。他のボタンの状態も同様だ。
>
> ![テキスト が含まれている画像
> 自動的に生成された説明](output/media/media/image119.tmp){width="5.905555555555556in"
> height="1.5993055555555555in"}
>
> 　robot/Tires.hを見る。
>
> 　このコードは、Tires（タイヤ）を制御する型の『宣言』部分である。タイヤを前進させたり後進させたり、旋回したり止めたりする動作を定義している。
>
> この型は正確には『クラス』と呼ばれていて、先ほど登場した構造体という機能の進化版である。構造体は変数の集まりである（厳密には違うのかもしれないけどまあいいじゃん）のに対し、クラスは変数と関数の集まりである。
>
> 　7行目の![](output/media/media/image120.tmp){width="0.4566469816272966in"
> height="0.13837817147856518in"}というキーワードの後に記述されている部分は、このクラスの内部でしか使えない。他の場所からはアクセスできない『隠された部分』である。![](output/media/media/image121.tmp){width="0.6589599737532809in"
> height="0.12672353455818022in"}、![](output/media/media/image122.tmp){width="0.5549136045494313in"
> height="0.1244663167104112in"}、![](output/media/media/image123.tmp){width="0.6647397200349956in"
> height="0.12956802274715662in"}という3つのモーターを表す変数が作成されている。これらは全てBD62193という別のクラス型で、各モーターを個別に制御するためのものである。
>
> 　12行目の![](output/media/media/image124.tmp){width="0.576418416447944in"
> height="0.12500656167979002in"}というキーワードの後に記述されている部分は、このクラスの外からも呼び出すことができる。そして、タイヤを動かすための関数が定義されている。
>
> 　このコードでは、クラスTiresが持つ変数として![](output/media/media/image121.tmp){width="0.5989304461942258in"
> height="0.11517935258092739in"}などを、関数として![](output/media/media/image125.tmp){width="1.5112718722659668in"
> height="0.13368985126859143in"}などを定義しているが、それらの具体的な初期化や動作については記述していない。これらの変数がどのように実装されるかは後述のrobot/Tires.cppで示される。
>
> ![テキスト
> 自動的に生成された説明](output/media/media/image126.tmp){width="5.905555555555556in"
> height="2.4784722222222224in"}
>
> 　robot/Tires.cppを見る。
>
> このコードは、Tiresクラスを『実装』している。先ほどのrobot/Tires.hが『宣言』であったのに対し、ここでは『実装』をしている。（よくわからなければ無視してください。）
>
> 3～5行目では、先ほどのrobot/Tires.hの8～10行目で宣言した変数の初期化を行っている。![](output/media/media/image127.tmp){width="0.7222594050743657in"
> height="0.12500656167979002in"}がもし仮にint型であれば、『int
> Tires::turnMotor =
> 0;』というように書けば良いが、turnMotorは![](output/media/media/image128.tmp){width="0.49009951881014874in"
> height="0.13923228346456692in"}というクラス型なので初期化は特殊になる。controller/main.cppの![](output/media/media/image89.tmp){width="1.4438495188101488in"
> height="0.12471784776902888in"}の説明で述べた考え方と同じである。
>
> 7～28行目では、先ほどのrobot/Tires.hの13～17行目で宣言した関数の動作が示されている。
>
> ![](output/media/media/image129.tmp){width="0.7673261154855643in"
> height="0.14593285214348206in"}関数は、左右のモーターを前進させる。
>
> ![](output/media/media/image130.tmp){width="0.7524748468941382in"
> height="0.16377515310586177in"}関数は、左右のモーターを後進させる。
>
> ![](output/media/media/image131.tmp){width="0.7582666229221348in"
> height="0.10832458442694663in"}関数は、旋回用モーターを前進させて車を左に旋回させる。
>
> ![](output/media/media/image132.tmp){width="0.7520833333333333in"
> height="9.401027996500437e-2in"}関数は、旋回用モーターを後進させて車を右に旋回させる。
>
> ![](output/media/media/image133.tmp){width="0.7376235783027122in"
> height="0.16454724409448818in"}関数は、左右のモーターを停止させる。
>
> ![テキスト
> 自動的に生成された説明](output/media/media/image134.tmp){width="5.905555555555556in"
> height="3.515277777777778in"}
>
> 　このようにして車のラジコンのプログラミングを行う。ここでの知識をロボット制作に是非活かしてほしい。

-   []{#フォルダとファイルの構成 .anchor}フォルダとファイルの構成

> 　左上にある![](output/media/media/image135.png){width="0.1284722222222222in"
> height="0.15453740157480314in"}を押すと、このような画面になる。左側にプログラムを構成するすべてのファイルやフォルダが載っている。これらのなかから、特に重要なものからいくつか説明する。
>
> ![PIO Home - robocon2024-a-team-big-bird - Visual Studio
> Code](output/media/media/image136.png){width="5.905555555555556in"
> height="3.3222222222222224in"}

-   [platformio.ini]{.underline}

> プロジェクトの設定ファイル。使用するプラットフォーム、ボード、フレームワーク、ビルドオプション、ライブラリの依存関係などを定義する。
>
> ![テキスト
> 自動的に生成された説明](output/media/media/image137.tmp){width="2.3607589676290464in"
> height="2.3607589676290464in"}
>
> ちなみに、このファイルはPlatformIOのUIを使って編集することもできる。
>
> ![PIO Home - robocon2024-a-team-big-bird - Visual Studio
> Code](output/media/media/image138.tmp){width="5.905555555555556in"
> height="3.3222222222222224in"}

-   [src/]{.underline}

> プロジェクトのソースコードを格納するフォルダ。ここにあるファイルがビルド対象になる。より正確に述べると、controllerのマイコンとしてビルドした場合はcontrollerフォルダ内がビルドされ、robotのマイコンとしてビルドした場合はrobotフォルダ内がビルドさる。
>
> ![](output/media/media/image139.tmp){width="0.8854166666666666in"
> height="1.7361111111111112in"}

-   [lib/]{.underline}

> 手動で管理するライブラリを格納するフォルダ。コピー＆ペーストで扱うライブラリがここに入る（？）。今回のロボット制作では恐らく使わない。ちなみに、READMEファイルにこのフォルダの使い方が記載されている。
>
> ![](output/media/media/image140.tmp){width="0.5987084426946632in"
> height="0.2361111111111111in"}

-   [include/]{.underline}

> ヘッダーファイルを格納するフォルダ。本来であればsrc/にあるヘッダーファイルはこのフォルダに置かないといけない（？）。今回のロボット制作では恐らく使わない。こちらも同様にREADMEファイルにこのフォルダの使い方が記載されている。
>
> ![](output/media/media/image141.tmp){width="0.6180555555555556in"
> height="0.27767716535433073in"}

-   .pio/

> ビルドによって生じた実行ファイル（.hexや.elfなど）や、platformio.iniのlib\_depsによってダウンロードされたライブラリなどを格納するフォルダ。自動的に作成や削除がされるフォルダで、人の手で操作するものではない。（このディレクトリは通常、Gitなどのバージョン管理システムでは無視される。）
>
> ![](output/media/media/image142.tmp){width="0.5833333333333334in"
> height="0.4711537620297463in"}

-   [.gitignore]{.underline}

> Gitを使用する場合に、バージョン管理から除外するファイルやフォルダを指定するファイル。
>
> ![テキスト
> 自動的に生成された説明](output/media/media/image143.tmp){width="1.4111800087489064in"
> height="0.5208333333333334in"}

-   .clang-format

> コードのフォーマットを統一するために使用される設定ファイル。ここでは、LLVMスタイルに従うように設定している。
>
> ![グラフィカル ユーザー インターフェイス
> 中程度の精度で自動的に生成された説明](output/media/media/image144.tmp){width="1.7109820647419072in"
> height="0.47759186351706034in"}

![挿絵 が含まれている画像
自動的に生成された説明](output/media/media/image3.png){width="1.55in"
height="0.8211920384951881in"}

共同開発

![アイコン
中程度の精度で自動的に生成された説明](output/media/media/image4.png){width="0.83in"
height="0.5237664041994751in"}

-   []{#共同開発の環境構築 .anchor}共同開発の環境構築

> [このサイト](https://zenn.dev/ojk/books/github-vscode/viewer/install)が参考になる。まず、Gitというソフトをインストールする必要がある。
>
> [このサイト](https://git-scm.com/download/win)の![](output/media/media/image145.tmp){width="1.0099004811898513in"
> height="0.13983267716535433in"}をクリックしインストーラーをダウンロードする。ダウンロードしたインストーラーをエクスプローラーのダウンロードフォルダから見つけ、実行する。インストーラーから何か訊かれたら、適当に答えるか僕に訊いてほしい。
>
> ![Git - Downloading Package - Google
> Chrome](output/media/media/image146.png){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> 　次に、Githubアカウントを作成する必要がある。[ここ](https://github.com/signup)にアクセスし、メールアドレス、パスワードなどを適当に設定する。（選択肢２の人へ：作成したアカウント名は僕に教えてほしい。リポジトリの管理権限を与えるために使用する。）
>
> 　そして、Visual Studio CodeとGithubアカウントを紐づける。Visual
> Studio Codeを起動させ、左下にある![挿絵 が含まれている画像
> 自動的に生成された説明](output/media/media/image147.png){width="0.1485148731408574in"
> height="0.16643919510061242in"}をクリックし、![](output/media/media/image148.png){width="0.9011493875765529in"
> height="0.13565726159230096in"}を選択する。
>
> ![コンピューターの画面のスクリーンショット
> 自動的に生成された説明](output/media/media/image149.png){width="5.905555555555556in"
> height="3.321527777777778in"}
>
> ここで、画面上側に![](output/media/media/image150.tmp){width="0.2772276902887139in"
> height="0.1452143482064742in"}というボタンが出てくるのでそこをクリックする。
>
> ![platformio.ini - Libraries - Visual Studio
> Code](output/media/media/image151.tmp){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> ![](output/media/media/image152.tmp){width="0.8861384514435695in"
> height="0.13366360454943133in"}を選択する。すると、Google
> Chromeが立ち上がり、ログインするためのサイトが表示される。適当に進める。
>
> ![platformio.ini - Libraries - Visual Studio
> Code](output/media/media/image153.tmp){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> Visual Studio Codeの画面左下にある![アイコン
> 自動的に生成された説明](output/media/media/image154.tmp){width="0.21925087489063866in"
> height="0.23727143482064741in"}をクリックし、ログインしたGithubアカウントが表示されれば、ログイン成功である。
>
> ![テキスト
> 自動的に生成された説明](output/media/media/image155.png){width="5.905555555555556in"
> height="3.321527777777778in"}
>
> 最後に、Autofetchを有効にする必要がある。Autofetchの意味が知りたい人は、[このサイト](https://zenn.dev/ojk/books/github-vscode/viewer/pull-push)を参考にしてほしい。『![挿絵,
> 食品 が含まれている画像
> 自動的に生成された説明](output/media/media/image156.png){width="0.14171478565179352in"
> height="0.1265310586176728in"} -\>
> ![](output/media/media/image157.png){width="1.5in"
> height="0.11936351706036745in"}』から設定画面を開く。そこで『git』と検索し、『Autofetch』の項目を『true』にする。
>
> ![モニター画面に映る文字のスクリーンショット
> 自動的に生成された説明](output/media/media/image158.png){width="5.905555555555556in"
> height="3.321527777777778in"}

-   リポジトリの作成（選択肢１）

> 　まず、![](output/media/media/image159.tmp){width="0.12735892388451445in"
> height="0.1717858705161855in"}と![](output/media/media/image160.tmp){width="1.5347594050743658in"
> height="0.16742891513560804in"}を順にクリックする。
>
> ![main.cpp - Tutorial - Visual Studio
> Code](output/media/media/image161.tmp){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> ![](output/media/media/image162.tmp){width="2.17129593175853in"
> height="0.12254265091863517in"}を選択する。
>
> ![main.cpp - Tutorial - Visual Studio
> Code](output/media/media/image163.tmp){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> 　これでリポジトリの作成は完了。右角にこのような表示が出れば成功である。
>
> ![main.cpp - Tutorial - Visual Studio
> Code](output/media/media/image164.tmp){width="5.905555555555556in"
> height="3.3222222222222224in"}

-   []{#リポジトリの共有（選択肢１）
    .anchor}リポジトリの共有（選択肢１）

> 　[ここ](https://github.com/)にアクセスし、自分のアイコンをクリックする。
>
> ![GitHub - Google
> Chrome](output/media/media/image165.png){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> ![](output/media/media/image166.tmp){width="0.8589741907261592in"
> height="0.16666666666666666in"}を選択する。
>
> ![GitHub - Google
> Chrome](output/media/media/image167.png){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> 共有したいリポジトリ（プロジェクト）を選択する。ここでは、![](output/media/media/image168.tmp){width="0.4120374015748032in"
> height="0.1406955380577428in"}を選択する。
>
> ![Your Repositories - Google
> Chrome](output/media/media/image169.png){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> ![](output/media/media/image170.tmp){width="0.5185181539807524in"
> height="0.15762904636920386in"}をクリックする。
>
> ![SoshiroFujimori/Tutorial - Google
> Chrome](output/media/media/image171.png){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> ![](output/media/media/image172.tmp){width="0.7105632108486439in"
> height="0.15197069116360454in"}をクリックする。するとパスワードの入力を要求されるので入力する。
>
> ![Manage access - Google
> Chrome](output/media/media/image173.png){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> 下に少しスクロールし、![グラフィカル ユーザー インターフェイス
> が含まれている画像
> 自動的に生成された説明](output/media/media/image174.tmp){width="0.5527941819772528in"
> height="0.18981517935258094in"}をクリックする。
>
> ![Manage access - Google
> Chrome](output/media/media/image175.png){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> 　共有したい人のユーザー名を検索し、![Manage access - Google
> Chrome](output/media/media/image176.png){width="2.79629593175853in"
> height="0.14814851268591425in"}からユーザーを追加する。ここでは『i22110』というユーザーを追加する。
>
> ![Manage access - Google
> Chrome](output/media/media/image177.png){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> ![Manage access - Google
> Chrome](output/media/media/image178.png){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> 　共有された人には通知が来る。![アイコン
> 低い精度で自動的に生成された説明](output/media/media/image179.tmp){width="0.18271544181977253in"
> height="0.1712959317585302in"}から通知を確認してもらおう。
>
> ![GitHub - Google
> Chrome](output/media/media/image180.tmp){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> 　招待されたことを報告する通知が来ている。クリックで通知の内容を表示してもらおう。
>
> ![Notifications - Google
> Chrome](output/media/media/image181.png){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> 　![テキスト
> 自動的に生成された説明](output/media/media/image182.tmp){width="0.6579571303587052in"
> height="0.18055555555555555in"}で承諾してもらう。
>
> ![Invitation to join SoshiroFujimori/Tutorial - Google
> Chrome](output/media/media/image183.png){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> 　これで、リポジトリの共有は完了だ。この作業によって招待された人にリポジトリの管理権限が与えられる。

-   []{#自分によるプログラムの変更を他人に適用させる
    .anchor}自分によるプログラムの変更を他人に適用させる

> [このサイト](https://zenn.dev/ojk/books/github-vscode/viewer/pull-push)が参考になる。ここでも念のため説明する。
>
> まず、Visual Studio Codeの画面左上にある![アイコン
> 自動的に生成された説明](output/media/media/image184.png){width="0.16831692913385826in"
> height="0.16831692913385826in"}をクリックする。そこで、他人に適用させたい変更を![](output/media/media/image185.png){width="0.1363484251968504in"
> height="0.12173993875765529in"}ボタンで選択する。
>
> ![テキスト
> 自動的に生成された説明](output/media/media/image186.png){width="5.905555555555556in"
> height="3.321527777777778in"}
>
> プログラムに対しどのような変更を加えたのかを、![](output/media/media/image187.tmp){width="1.719025590551181in"
> height="0.17340988626421697in"}に必ず打ち込む。その状態で、![](output/media/media/image188.png){width="1.6138615485564305in"
> height="0.16315944881889763in"}をクリックする。
>
> ![README - robocon2024-a-team-big-bird - Visual Studio
> Code](output/media/media/image189.tmp){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> 　もし、メッセージを入力せずに間違って![](output/media/media/image188.png){width="1.6138615485564305in"
> height="0.16315944881889763in"}を押してしまった場合、表示された![テキスト
> が含まれている画像
> 自動的に生成された説明](output/media/media/image190.tmp){width="0.7913035870516185in"
> height="0.16562117235345583in"}の![](output/media/media/image191.png){width="0.10518919510061242in"
> height="0.1304352580927384in"}ボタンを押して、先述の作業をやり直す必要がある。
>
> ![COMMIT\_EDITMSG - gitTest - Visual Studio
> Code](output/media/media/image192.png){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> 最後に、![](output/media/media/image193.tmp){width="1.8612718722659667in"
> height="0.19226377952755905in"}を押して完了である。
>
> ![README - robocon2024-a-team-big-bird - Visual Studio
> Code](output/media/media/image194.tmp){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> 　これで、『自分によるプログラムの変更を他人に適用させる』ことができる。より正確に言うと、『GitHubにプログラムの変更を適用させる』ことができる。[ここ](https://github.com/SoshiroFujimori?tab=repositories)から自分のプログラムを開き、![](output/media/media/image195.tmp){width="0.6086953193350831in"
> height="0.16439195100612422in"}から変更履歴を確認することができる。
>
> ![SoshiroFujimori/robocon2024-a-team-big-bird - Google
> Chrome](output/media/media/image196.png){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> 　先ほど入力したメッセージが表示されるはずだ。
>
> ![Commits · SoshiroFujimori/robocon2024-a-team-big-bird - Google
> Chrome](output/media/media/image197.tmp){width="5.905555555555556in"
> height="3.3222222222222224in"}

-   []{#_Hlk175826784
    .anchor}他人によるプログラムの変更を自分に適用させる

> 自分が編集したすべてのファイルに対し、先述のセクションの作業をした状態であれば、![](output/media/media/image198.png){width="1.3981485126859143in"
> height="0.15123468941382326in"}をクリックすることで他人によるプログラムの変更を適用することができる。
>
> ![platformio.ini - robocon2024-a-team-big-bird - Visual Studio
> Code](output/media/media/image199.tmp){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> 　ここで、他人によるプログラムの変更があるはずなのに、![](output/media/media/image198.png){width="1.3981485126859143in"
> height="0.15123468941382326in"}という表示が無い場合は、『![](output/media/media/image200.tmp){width="0.1291415135608049in"
> height="0.11881124234470691in"} -\>
> ![](output/media/media/image201.png){width="0.2673261154855643in"
> height="0.13139763779527558in"}』を押す必要がある。
>
> ![グラフィカル ユーザー インターフェイス
> 自動的に生成された説明](output/media/media/image202.png){width="5.905555555555556in"
> height="3.321527777777778in"}
>
> 『他人によるプログラムの変更を自分に適用させる』この作業は、『GitHubから最新のプログラムを取得し自分のプログラムに合成する』ことで実現している。

-   []{#一つのファイルを複数人が同時に編集する
    .anchor}1つのファイルを複数人が同時に編集する

> 　複数人がそれぞれ別々のファイルを同時に編集するのは問題ない。しかし、複数人が1つのファイルを同時に編集すると、エラーが発生する。このセクションでは、そのエラーの解消法について説明する。
>
> 　![](output/media/media/image203.tmp){width="0.8150284339457567in"
> height="0.13405074365704286in"}というテキストファイルを同時に編集する場合を考える。こちらでは、このファイルに『A』という文字を書いたとする。一方、他の人が全く同じファイルに『B』と書いたとする。この状態で、こちらの画面で![](output/media/media/image204.tmp){width="1.8056955380577429in"
> height="0.16488517060367455in"}し、![テキスト
> 自動的に生成された説明](output/media/media/image205.tmp){width="1.5648151793525809in"
> height="0.17348206474190725in"}を押すとどうなるのだろうか？
>
> ![README.md - gitTest - Visual Studio
> Code](output/media/media/image206.png){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> ![README.md - gitTest - Visual Studio
> Code](output/media/media/image207.png){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> 　押すと、このような物々しい画面になる。![](output/media/media/image208.tmp){width="0.935184820647419in"
> height="0.13520778652668416in"}のか、![](output/media/media/image209.tmp){width="1.0972222222222223in"
> height="0.13410542432195977in"}のか、![](output/media/media/image210.tmp){width="0.9166666666666666in"
> height="0.10305774278215223in"}のか訊かれる。適切なものを選ぼう。ここでは、適当に![](output/media/media/image208.tmp){width="0.935184820647419in"
> height="0.13520778652668416in"}を選択することにする。
>
> ![README.md - gitTest - Visual Studio
> Code](output/media/media/image211.png){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> 　すると、他の人が入力した『B』という文字は消え、こちらの方で入力した『A』という文字が適用された。
>
> ![README.md - gitTest - Visual Studio
> Code](output/media/media/image212.png){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> 　あとは、通常通り![](output/media/media/image213.tmp){width="1.79629593175853in"
> height="0.16402668416447944in"}をすれば良い。
>
> ![README.md - gitTest - Visual Studio
> Code](output/media/media/image214.png){width="5.905555555555556in"
> height="3.3222222222222224in"}
>
> ![README.md - gitTest - Visual Studio
> Code](output/media/media/image215.png){width="5.905555555555556in"
> height="3.3222222222222224in"}

![挿絵 が含まれている画像
自動的に生成された説明](output/media/media/image3.png){width="1.55in"
height="0.8211920384951881in"}

[]{#コンクルージョン（章） .anchor}コンクルージョン

![アイコン
中程度の精度で自動的に生成された説明](output/media/media/image4.png){width="0.83in"
height="0.5237664041994751in"}

-   []{#最後に .anchor}最後に

> 思いのほか説明が長くなってしまった。再び述べることになってしまうが、もし読むのが面倒だと感じた場合はご遠慮なく質問してほしい。
>
> それと、僕は専門家ではないので、間違った説明をしてしまっている可能性は大いにある。とくにプログラミングの説明や、Gitの説明が怪しい。日本語にも自信がない。なので、もし間違った所や誤植、あるいはわかりにくいところなどあれば教えてほしい。連絡先を載せておく。
>
> メール：<i22110@oshima.kosen-ac.jp>
>
> Teams：i22110（藤本宗太郎）

-   []{#クレジット .anchor}クレジット

> ・藤本宗太郎（オリジナル）
>
> ・
