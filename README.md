# 自己紹介
> **LEE YOHAN （イ ヨハン）**<br>
Kumoh National Institute of Technology 情報科学科 在学 （27年卒見込み）

# スキル
**Language**<br>
- Python
- C
- C++
- Java
- Dart

**FrameWork**
- Flutter
- Spring（少し）

# 📝プロジェクト
> チームプロジェクトや個人プロジェクトたちです。
リーダーとしてはチームの仲間とのコミュニケーションやみんなでどう協力するといいのかを経験できたし、リーダーじゃなかったプロジェクトでは他のリーダーのやり取りを見習えるきっかけとなりました。
> ## 1. 📰 NewsClip<br>
> ニュース要約、ニュースコミュニティ アプリケーション
> - 開発期間：2025.09 ~ 2025.12
> - 役割：Flutterを利用したFrontendまたその中のロジック開発
> - 仕様 <br>
>   > **Back-end**
>   > - Language : Go
>   > - Skill : Postgre, Redis, DuckDns, nginx
> 
>   > **Front-end**<br>
>   > - Language : Flutter
>   > - Skill : FLutter
> - [NewsClipのReadme](https://github.com/yohan020/portfolio/blob/main/NewsClip.md)
> - [FrontendのReadme](https://github.com/yohan020/portfolio/blob/main/NewsClip_Frontend.md)
> - [BackendのReadme](https://github.com/yohan020/portfolio/blob/main/NewsClip_Backend.md)
>
> ## 2. 🤖 スマートロボット掃除機<br>
> Raspberry5を利用した見守りカメラ＋ロボット掃除機
> - 開発期間：2025.11 ~ 2025.12
> - 役割： リーダーとしてチームをリード、C言語のマルチスレッドで掃除機のセンサー部分、Bluetooth通信部分と経路制御アルゴリズム部分開発、掃除機の制御アプリケーション開発
> - 仕様 <br>
>   - 掃除機：超音波センサー、DCモーター、吸引モーター、カメラ、ラズベリーパイ5、Bluetoothモジュール など
>   - 制御アプリケーション : 掃除機のマニュアルモードとオートモードの切り替え、掃除機の方向制御、パワーオン・オフ制御、カメラ確認
> - [スマートロボット掃除機のReadme](https://github.com/yohan020/portfolio/blob/main/Smart_Robot_Vacuuum.md)
> - [アプリケーション](https://github.com/yohan020/robot_vacuum_app.git)
> 
> ## 3. 🧠 AlphaZero実装: 五目並べ強化学習AI<br>
> Python, PyTorchを活用した強化学習(Reinforcement Learning)プロジェクト
> - 開発期間：2025.12
> - 役割： 個人開発。AlphaZeroアルゴリズム（MCTS + ResNet）の設計・実装、自己対局（Self-Play）パイプラインの構築、学習効率化のための報酬システム設計、対局用GUI開発
> - 仕様 <br>
>   - 技術スタック：Python 3.10, PyTorch, NumPy, Tkinter
>   - アルゴリズム：Monte Carlo Tree Search (MCTS), ResNet (Policy & Value Network)
>   - 主要な技術的工夫 : 
>     - 初期学習の効率化：盤面中央での戦闘を学習させるため、「Virtual Fence（仮想フェンス）」アルゴリズムを導入
>     - 攻撃性の向上：防御偏重（引き分け狙い）を防ぐため、攻撃パターン（3連・4連）に即時報酬を与える「Intermediate Reward（中間報酬）」システムを設計
>     - 局所解からの脱出：学習停滞を防ぐため、周期的に学習率をリセットするSGDR手法を適用
>   - 成果 : 約1,000サイクルの学習を経て、定石においては開発者（人間）と互角（理論上の引き分け/Nash Equilibrium）の防御力を達成。また、データ分布外（Out-of-Distribution）の攻撃に対するAIの「死角（Blind Spot）」を発見・分析
> - [AlphaZero五目並べ](https://github.com/yohan020/omok_AI_new)
