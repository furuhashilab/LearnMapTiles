# 地図タイル技術年表 v0.96
ChatGTP o3-mini と対話しながら修正しているため、すべての内容のエビデンスチェックまで終わっていません。ハルシネーションが起きている可能性がありますのでご注意ください。裏トリ完了後は v1.0 とする予定です。追記提案はプルリクお願いいたします。

| 年           | 主な技術の進化・出来事とオープンソース・コミュニティとの関連・影響 |
| ------------ | --------------------------------------------------------------------- |
| **2003** | - **国土地理院の電子国土Webシステム:** <br>&nbsp;&nbsp;&nbsp;&nbsp;[国土地理院は、2003年に電子国土Webシステムを実装](https://www.gsi.go.jp/common/000104529.pdf)し、タイルベースの地図配信技術を導入。<br>&nbsp;&nbsp;&nbsp;&nbsp;このシステムは、国土情報のデジタル化と公共データの提供を推進する一環として、静的なラスタタイルやプリレンダリング技術を活用し、効率的なウェブ地図表示を実現。電子国土Webシステムプラグインではベクトルタイル化の実装も行っていた。<br>&nbsp;&nbsp;&nbsp;&nbsp;後の Google Maps などの商用サービスに先駆けたタイル配信の技術的基盤となる。 |
| **2004**     | - **Google の買収活動:** <br>&nbsp;&nbsp;&nbsp;&nbsp;*Keyhole 社の買収* により、後の Google Earth/Maps の基盤となる衛星画像データ、タイル配信技術、KML技術を取り込む。 <br>&nbsp;&nbsp;&nbsp;&nbsp;*Where 2 Technologies の買収* により、インタラクティブなウェブマップUI/UXと地図タイルの配信技術を取得。 <br>- **OpenStreetMap (OSM) の開始:** <br>&nbsp;&nbsp;&nbsp;&nbsp;コミュニティ主導で地理データを収集・編集するプロジェクトとして誕生。<br>&nbsp;&nbsp;&nbsp;&nbsp;OSM は、Google Maps で採用される Web メルカトル投影など、同社の技術と高い親和性を持ち、後のオープンソースツールの標準タイルソースとなる。 |
| **2005**     | - **[Google Maps の一般公開](https://blog.google/intl/ja-jp/products/explore-get-answers/2020_02_google-15_6/):** <br>&nbsp;&nbsp;&nbsp;&nbsp;事前にレンダリングされた静的ラスタタイルを利用し、スムーズなパン・ズーム操作が可能なインタラクティブ地図サービスを開始。<br>- **[Google Maps API の提供開始](https://blog.google/intl/ja-jp/products/explore-get-answers/2020_02_google-15_6/):** <br>&nbsp;&nbsp;&nbsp;&nbsp;ウェブサイトやアプリケーションへの地図埋め込みが容易に。<br>&nbsp;&nbsp;&nbsp;&nbsp;この API は RESTful な設計に基づき、シンプルな HTTP GET 要求でタイルを取得できるため、開発者にとって扱いやすく、地図タイル技術の普及を後押しした。<br>→ この手法が、後の地図配信技術のデファクトスタンダードである **XYZタイル** となる。 |
| **2006**     | - **OpenLayers の登場:** <br>&nbsp;&nbsp;&nbsp;&nbsp;Google Maps の成功に刺激され、オープンソースでインタラクティブなウェブ地図ライブラリとして OpenLayers（初期バージョン）が普及。<br>→ Google のタイル配信方式やユーザー体験が、FOSS4G ツールの基本設計に影響。<br>- **Mapnik の登場:** <br>&nbsp;&nbsp;&nbsp;&nbsp;[OpenStreetMap の地図タイルレンダリングサーバーとして、Mapnik が普及。](https://wiki.openstreetmap.org/wiki/History_of_OpenStreetMap)<br>&nbsp;&nbsp;&nbsp;&nbsp;オープンソースの C++/Python ベースのレンダリングエンジンで、OSM のデータから高品質なタイルを生成し、カスタマイズ性やスケーラビリティを提供する。 |
| **2007–2008** | - **gdal2tiles 開発:** <br>&nbsp;&nbsp;&nbsp;&nbsp;Google Summer of Code 2007, 2008 にて Masaryk University in Brno の学生だった Klokan Petr Přidal(現 MapTiler Founder & CEO) が、GDAL に含まれるツールとして、ラスターデータを地図タイルに変換する gdal2tiles をOSSとして開発・注目され、Google のXYZタイル方式がオープンソースコミュニティに広がる。  |
| **2010** | - **Google Mapsベクトルタイル化:** <br>&nbsp;&nbsp;&nbsp;&nbsp;AndroidクライアントアプリでGoogle Mapsのベクトルタイル配信開始。但し、デスクトップ版は2013年から。<br>→ この動向が「動的でリアルタイムな地図表現」の必要性をオープンソースコミュニティに認識させる契機となる。 |
| **2011**     | - **LeafletJS の登場:** <br>&nbsp;&nbsp;&nbsp;&nbsp;軽量でモバイルフレンドリーなインタラクティブ地図ライブラリとして LeafletJS がリリース。<br>→ Google Maps の使いやすさやタイル配信方式を受け継ぎ、シンプルかつ効率的な設計が評価される。LeafletJS開発者の Volodymyr Agafonkin 氏はその後 Mapbox に移籍して Mapbox Vector Tile の実装に関わる。 |
| **2012**     | - **tilemill の登場:** <br>&nbsp;&nbsp;&nbsp;&nbsp;Mapbox によるオープンソース地図デザインツール tilemill が発表。<br>→ Google の動的レンダリングの概念（スタイル変更、拡大縮小時の滑らかさ）に触発され、ユーザーが自由に地図スタイルを設計できるツールとして注目される。 |
| **2013** | - **ベクトルタイルと動的スタイリングの採用:** <br>&nbsp;&nbsp;&nbsp;&nbsp;Google Mapsで本格的にベクトルタイルレンダリングを導入。<br>- **API の進化:** <br>&nbsp;&nbsp;&nbsp;&nbsp;Google Maps API にも動的スタイリングが取り入れられる。 <br>- **地理院地図公開:** <br>&nbsp;&nbsp;&nbsp;&nbsp;2013年から、国土地理院は Google Maps の XYZ 地図タイル仕様を採用したウェブメルカトル方式で地理院地図の公開を開始。<br>&nbsp;&nbsp;&nbsp;&nbsp;これにより、国内の公共地図サービスが商用サービスや FOSS4G ツールと互換性のある形式で提供されるようになった。<br>- **Mapbox GL JS公開:** <br>&nbsp;&nbsp;&nbsp;&nbsp;Mapbox はオープンソースAPIとして Mapbox Vector Tile に最適化した Mapbox GL JS を発表。<br>→ ベクトルタイル技術のOSS化が加速する。 <br>→ この革新が、オープンソースツールにおける柔軟な描画技術の発展に影響。 |
| **2014** | - **Mapbox Vector Tile仕様公開:** <br>&nbsp;&nbsp;&nbsp;&nbsp;[Mapbox Vector Tile Specification v1.0.0 公開](https://github.com/mapbox/vector-tile-spec)。<br>&nbsp;&nbsp;&nbsp;&nbsp;これにより、ベクトルタイル技術の標準仕様が一般化した。<br> |
| **2015**     | - **tippecanoe の登場:** <br>&nbsp;&nbsp;&nbsp;&nbsp;Mapbox が大規模地理空間データから効率的にベクトルタイルセットを生成するツール tippecanoe をリリース。<br>→ ベクトルタイル技術のOSS化が加速する。 |
| **2016**     | <br>- **Mapbox GL JS のリリース:** <br>&nbsp;&nbsp;&nbsp;&nbsp;WebGL を用いた高速・インタラクティブなベクトル地図ライブラリとして登場。<br>→ 各社のベクトルタイル戦略と WebGL 利用の成功例が、オープンソースコミュニティ内での技術発展を後押し。<br>- **[Mapbox Terrain-RGB 公開](https://medium.com/mapbox/global-elevation-data-6689f1d0ba65)(2016年10月27日):** <br>&nbsp;&nbsp;&nbsp;&nbsp;標高値を PNG の RGB に埋め込む全球の標高ラスタタイルセット。標高 = -10000 + (R×256² + G×256 + B)×0.1(0.1 m 刻み)。Mapbox GL JS の 3D 地形・陰影起伏の基盤となる(2021年12月以降、標高データの更新は後継の Terrain-DEM に集約)。<br>- **Mapzen Terrain Tiles / Terrarium 形式の公開(2016年頃・要確認):** <br>&nbsp;&nbsp;&nbsp;&nbsp;Mapzen が Joerd で生成する標高タイル「Terrain Tiles」を 1.0 として提供。PNG に標高を埋め込む **Terrarium** 形式(標高 = R×256 + G + B/256 - 32768)を採用。Mapzen 終了後も AWS Open Data として継続し、Tangram や MapLibre GL JS(`encoding: "terrarium"`)で利用される。 |
| **2019**     | - **地理院地図ベクター試験公開:** <br>&nbsp;&nbsp;&nbsp;&nbsp;国土地理院が Mapbox Vector Tile をベースにベクトルタイルの試験配信を地理院地図ベクターとして開始。 |
| **2020**     | - **[国連OpenGIS Initiative がベクトルタイル技術試験運用開始](https://github.com/unvt):** <br>&nbsp;&nbsp;&nbsp;&nbsp;国連 OpenGIS Initiative が業務で利用可能なベクトルタイル技術の試験運用(UNVT - United Nations Vector Tile Toolkit)を開始。<br>- **MapLibre GL JS のフォーク(2020年12月頃):** <br>&nbsp;&nbsp;&nbsp;&nbsp;Mapbox GL JS v2 が非オープンライセンスとなったことを受け、v1.13 系列からコミュニティが MapLibre GL JS をフォーク。以後、オープンなベクトルタイル描画の中心的存在となる。<br>- **国土地理院 標高タイル(PNG)の整備・公開(2020年頃・要確認):** <br>&nbsp;&nbsp;&nbsp;&nbsp;標高値を 24bit PNG の RGB に格納する「PNG 標高タイル」(分解能 0.01 m、無効値は (R,G,B)=(128,0,0)、標高 = (R×2¹⁶ + G×2⁸ + B)×0.01)。全国 10m メッシュ(DEM10B)などが配信され、産総研のリリース(2020年10月)でも地理院の PNG 標高タイル公開に言及。Terrain-RGB / Terrarium とは式が異なる。 |
| **2021**     | - **Google Earth Web タイルオーバーレイ対応:** <br>&nbsp;&nbsp;&nbsp;&nbsp;Google Earth Web プロジェクト機能にタイルURLを記述することで、XYZタイル画像のインポートが可能となる。<br>- **[Protomapsが地図タイルコンテナPMTiles公開](https://github.com/protomaps/PMTiles/commits/main/?since=2021-10-01&until=2021-10-31):** <br>&nbsp;&nbsp;&nbsp;&nbsp;Protomapsがベクトルタイルなどをクラウドオプティマイズした形でコンテナ化するPMTilesを公開。|
| **2023** | - **Google Photorealistic 3D Tiles 公開:** <br>&nbsp;&nbsp;&nbsp;&nbsp;GoogleはCesium社と共同で、Google Earth用の3Dジオメトリデータを3DTiles形式で外部プラットフォームにも公開する Google Photorealistic 3D Tilesサービスを公開。Google製品以外のプラットフォームとの連携を強化。<br>→ Google の成功事例は、FOSS4G 全体の設計思想や技術選択（タイル方式、WebGL、ベクトルタイル、キャッシュ戦略等）の基準となり、今後もエコシステムに大きな影響を与え続ける。 |
| **2024** | - **経済産業省 空間ID 仕様公開:** <br>&nbsp;&nbsp;&nbsp;&nbsp;経済産業省とデジタル庁は Ouranos Ecosystem(ウラノス・エコシステム）4次元時空間情報基盤の基礎技術として３次元空間ID(空間ボクセル)の仕様を公開。XYZタイルとの互換性を持ち、三次元空間へと拡張した地図タイルの応用事例。<br>
- **MapLibre Tile (MLT) の構想・仕様開発が公に:** <br>&nbsp;&nbsp;&nbsp;&nbsp;Markus Tremmel 氏が State of the Map 2024 で「MapLibre Tiles: A Next Generation Vector Tiles Format specially designed for OSM data」を発表。Mapbox Vector Tile (MVT) の後継を目指し、ジオメトリと属性を列指向(columnar)に格納して圧縮率とデコード速度を高める設計。[仕様リポジトリ](https://github.com/maplibre/maplibre-tile-spec)で開発が進む。<br>&nbsp;&nbsp;&nbsp;&nbsp;※2024年は「発表・仕様策定段階」で、正式リリースは2026年1月。<br>- **国土地理院 テキスト形式標高タイルの更新停止(令和6年=2024年10月):** <br>&nbsp;&nbsp;&nbsp;&nbsp;標高タイルは PNG 形式への一本化が進む。|
| **2025** | - **MLT の実装開始:** <br>&nbsp;&nbsp;&nbsp;&nbsp;2025年1月時点で MapLibre GL JS と MapLibre Native への実装が開始(MapLibre ロードマップ)。<br>- **MLT 論文公開:** <br>&nbsp;&nbsp;&nbsp;&nbsp;Tremmel & Zink [“MapLibre Tile: A Next Generation Vector Tile Format”](https://arxiv.org/abs/2508.10791) が 2025年8月に arXiv 公開(後に ACM SIGSPATIAL で発表)。<br>- **[Mapterhorn](https://mapterhorn.com/) 公開:** <br>&nbsp;&nbsp;&nbsp;&nbsp;元 MapLibre コーディネーターの Oliver Wipfli 氏を中心とするオープンな地形(標高)タイルプロジェクト。Copernicus GLO-30 を全球ベースに、スイス swissALTI3D など各国の高解像度 DEM/LiDAR を統合し、**Terrarium エンコーディング**の標高タイルを **PMTiles** で配布(Source Cooperative 上の公開は 2025年11月)。Mapzen の Joerd の後継的な位置づけ。|
| **2026** | - **MapLibre Tile (MLT) 1.0 正式発表(2026年1月23日):** <br>&nbsp;&nbsp;&nbsp;&nbsp;MapLibre が MLT を MVT の後継として発表。MapLibre GL JS / MapLibre Native が対応済みで、スタイル JSON のソースに `encoding: "mlt"` を指定して利用。MVT と機能同等で、大きなタイルで最大 6 倍の圧縮率(プロジェクト側の主張)。<br>- **Mapterhorn の拡大:** <br>&nbsp;&nbsp;&nbsp;&nbsp;対象国を拡充(v0.0.5 でスウェーデン、ポーランド、オランダ等を追加)。State of the Map 2026 でも "Mapterhorn Terrain and Imagery" のセッションが採択され、衛星画像(imagery)にも展開。日本向けデータ(source.coop 上の mapterhorn-japan-bridge)も確認される。<br>- **国土地理院 高精度標高(DEM1A 1mメッシュ)の提供範囲拡大:** <br>&nbsp;&nbsp;&nbsp;&nbsp;国土地理院ページの更新履歴に 2026年7月31日の拡大の記載あり(詳細は要確認)。|

## 補足説明

- **国土地理院の電子国土Webシステム:** <br>
  2000年代前半に国土地理院が実装したこのシステムは、従来の大規模地図データを効率的にウェブ上で表示するために、地図をあらかじめタイル化して配信する技術を採用している。後の民間サービス（例：Google Maps）のタイル配信方式に先駆けた、重要な技術的試みである。

- **OpenStreetMap (OSM) の役割 & Mapnik:** <br>
  2004年に開始された OSM は、コミュニティ主導のクラウドソーシングで地理情報を収集・編集し、自由なライセンスの下でデータを提供している。<br>
  また、OSM のデータから高品質な地図タイルを生成するレンダリングエンジンとして、Mapnik が普及しており、後に OpenLayers、Leaflet、Mapbox 系ライブラリなどの標準タイルソースとして利用され、地図データのオープン化・民主化に大きく貢献している。

- **RESTful API の一般化:** <br>
  シンプルな HTTP GET 要求で地図タイルを取得できる RESTful な API 設計が一般化したことで、開発者は容易にタイルを利用・統合できるようになった。<br>
  この設計思想は、Google Maps API をはじめとする各種 API の普及に寄与し、地図タイル技術の普及と拡張に大きく貢献している。

- **Google の技術と FOSS4G の相乗効果:** <br>
  Google Maps により確立されたタイル配信方式、動的レンダリング、ベクトルタイル技術は、オープンソースコミュニティでも共通の設計思想となった。<br>
  その結果、OpenLayers、Leaflet、tilemill、tippecanoe、Mapbox GL JS、MapLibre GL JS などのツールが、高品質で柔軟な地図サービス構築の基盤として発展している。

- **標高ラスタ3タイプの比較(年表の2016年・2020年の項目を参照):** <br>
  Web 地図で 3D 地形・陰影起伏・等高線を描くための「標高ラスタ(raster-dem)」には、主に次の3種のエンコーディングがある。MapLibre GL JS では `raster-dem` ソースの `encoding` で指定する(`mapbox` / `terrarium` / 一部バージョンでカスタム)。

  | タイプ | 提供元・例 | 標高の計算式 | 特徴 |
  | --- | --- | --- | --- |
  | **Mapbox Terrain-RGB** | Mapbox Terrain-RGB v1 / Terrain-DEM v1 | `h = -10000 + (R×256×256 + G×256 + B) × 0.1` | 0.1 m 刻み。Mapbox 系・MapLibre の `encoding: "mapbox"` |
  | **Terrarium** | Mapzen Terrain Tiles(Joerd)、AWS Terrain Tiles、**Mapterhorn** | `h = (R×256 + G + B/256) - 32768` | 約 1/256 m 刻み。MapLibre の `encoding: "terrarium"` |
  | **国土地理院 標高タイル(PNG)** | 地理院タイル `dem_png`(DEM10B 等) | `h = (R×2^16 + G×2^8 + B) × 0.01`(`R=128,G=0,B=0` は無効値) | 0.01 m 刻み。そのままでは Terrain-RGB と互換でなく、変換または専用デコーダが必要。DEM10B(10m)・DEM5A/5B(5m)などを zoom に応じて使い分ける例がある |

  ※「3タイプ」は Mapbox Terrain-RGB / Terrarium / 国土地理院 PNG と解釈した整理です。GSI の式・無効値は二次情報(Qiita/Zenn)に基づくため、地理院の[標高タイル仕様](https://maps.gsi.go.jp/development/demtile.html)での確認をお願いします。
