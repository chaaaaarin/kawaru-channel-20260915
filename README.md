# 【Astra不要】Obsidianで絞って、GPT-5.6 Lunaに任せるトークン節約術

🎁 [プレゼントはこちら](https://chaaaaarin.github.io/gift-library/aa/ep/130/)

GPT-6 Astra（ジーピーティーシックス・アストラ）にボルト（メモの保管庫）を丸ごと読ませるのをやめて、「探す・並べる」は Obsidian（オブシディアン）の標準機能で、「まとめる・書く」だけを GPT-5.6 Luna（ルナ）に任せる方法を、章ごとの要点でまとめました。

## 目次

1. GPT-6 Astraの枠は、なぜすぐ減るのか
2. 「トークン消費ゼロ」でできること（Obsidianの標準機能）
3. GPT-5.6 Lunaとは・どの作業に向くか
4. 実演：同じ質問を「Astraに丸投げ」と「Obsidianで絞ってLuna」で比べる
5. 結果の読み方（同じになる所・差が出る所）
6. Codexでモデルを切り替えるには
7. 今日からやること
8. プレゼントの中身と受け取り方

確度の見方: ✅ 公式で確認済み ／ 🔶 公式情報はあるが解釈を含む

## 各章の要点

### 1. GPT-6 Astraの枠は、なぜすぐ減るのか

Codex（コーデックス）を ChatGPT のアカウントで使うと、モデルごとに使うクレジットの単価が違います ✅ [Codex 料金](https://learn.chatgpt.com/codex/pricing)

| モデル | 入力（100万トークンあたり） | 出力（100万トークンあたり） | Plus・5時間あたりのメッセージの目安 |
|---|---|---|---|
| GPT-6 Astra | 250 | 1,250 | 5〜45 |
| GPT-5.6 Terra（テラ） | 50 | 300 | 25〜200 |
| GPT-5.6 Luna（ルナ） | 5 | 30 | 250〜2,000 |

- Luna の単価は Astra の**入力50分の1・出力約42分の1**（上の単価表から計算）。API の料金でも同じ比です（Astra 入力$10・出力$50／Luna 入力$0.2・出力$1.2）✅ [GPT-5.6 Luna モデルページ](https://developers.openai.com/api/docs/models/gpt-5.6-luna)
- 5時間の目安は「固定の上限ではなく、作業の中身や設定で変わる」ものです ✅ [OpenAI ヘルプ](https://help.openai.com/en/articles/20001516-managing-usage-with-gpt-6-astra-in-work-and-codex)
- 注意: 枠を使い切ってからモデルを切り替えても、使った分は戻りません。作業を始める前にモデルを決めます ✅ [OpenAI ヘルプ](https://help.openai.com/en/articles/20001516-managing-usage-with-gpt-6-astra-in-work-and-codex)

### 2. 「トークン消費ゼロ」でできること（Obsidianの標準機能）

AI に頼まずに Obsidian の中で済ませる作業は、AI にデータを送らないのでトークンを使いません。

- **検索**: 標準の検索機能で、`file:`（ファイル名）・`path:`（フォルダ）・`tag:`（タグ）・`task-todo:`（未完了のタスク）・`[プロパティ名:値]` などを使って絞り込めます。検索結果をノートに埋め込むこともできます（`query` のコードブロック） ✅ [Obsidian ヘルプ「Search」](https://obsidian.md/help/plugins/search)
- **Bases（ベース）**: ノートのプロパティ（期限・状態などの欄）を、表やカードの一覧にする標準機能。データはパソコンの中の Markdown ファイルとプロパティのまま使われます。`today()`（今日）と比べて「期限が近いもの」だけを並べる、といった絞り込みもできます ✅ [Obsidian ヘルプ「Bases」](https://obsidian.md/help/bases) ✅ [Bases の関数](https://obsidian.md/help/bases/functions)
- **Obsidian CLI（シーエルアイ）**: AI に `search`（検索して、当たったファイルの場所を返す）を使わせれば、当たったノートだけを読ませられます。Obsidian のアプリが起動している間だけ使えます ✅ [Obsidian ヘルプ「CLI」](https://obsidian.md/help/cli)
- 向かない場面: 「まとめる・書く・判断する」は AI が要るので、ここはゼロになりません。Bases で並べるには、ノートに「期限」などのプロパティを先に付けておく必要があります

### 3. GPT-5.6 Lunaとは・どの作業に向くか

- Luna は「速くて手ごろな GPT-5.6 のモデル」。公式が挙げる得意分野は、抜き出し・分類・書式の変換・決まった形の要約のような「はっきりした、繰り返しの作業」 ✅ [Codex「Models」](https://learn.chatgpt.com/codex/models)
- Terra は「ふだんの仕事向けの、バランス型の GPT-5.6 のモデル」 ✅ [Codex「Models」](https://learn.chatgpt.com/codex/models)
- 公式の節約のヒントにも「決まった作業は Terra や Luna のような小さいモデルに切り替える」とあります ✅ [Codex 料金](https://learn.chatgpt.com/codex/pricing)

| 作業 | 向くモデル |
|---|---|
| 会議メモから宿題と期限を抜き出す／メモの分類／決まった形の要約 | Luna |
| 複数のノートをまとめた資料づくり・ふだんの相談 | Terra |
| ノート同士の食い違い探し・判断が要る相談・ボルト全体の棚卸し | Astra |

- 向かない場面: 読ませたノートに書いていない食い違いや変更は、Luna には分かりません（5章）🔶 使い分けの表は、公式の説明をもとにした今回の整理です

### 4. 実演：同じ質問を「Astraに丸投げ」と「Obsidianで絞ってLuna」で比べる

架空の会社員（あおば包装・営業企画の佐藤さん）のボルトで、同じ質問を2通りで試します。

- 質問: 「今週やるべきことを、期限と根拠のノート付きで一覧にして」
- A（丸投げ）: Codex で GPT-6 Astra を選び、ボルト全体を読ませて答えさせる
- B（絞ってLuna）: Obsidian の Bases で「期限が近い案件」を表にして候補を確かめる（ここはトークン0）→ Codex で GPT-5.6 Luna を選び、候補のノートだけを読ませて同じ質問をする
- 比べるところ: 答えの中身（期限・根拠のノート）と、使った量（CLI の `/status`、アプリは「設定 → 使用状況」） ✅ [Codex CLI「Slash commands」](https://learn.chatgpt.com/docs/cli/slash-commands)

### 5. 結果の読み方（同じになる所・差が出る所）

- **同じになりやすい所**: 読ませたノートに書いてある期限・次にやること。ここは Luna でも根拠のノート付きで返ります
- **差が出やすい所**: 期限の変更が会議メモにだけ書いてあって、案件ノートが古いまま、というような「ノート同士の食い違い」。読ませる範囲に会議メモが入っていないと、Luna は古い期限のまま答えます
- 差が出たら: 足すノートを1枚増やすか、その質問だけ Terra か Astra に上げます
- 使う量の目安（計算例）: 入力3万トークン・出力2千トークンの作業なら、Astra は約10クレジット、Luna は約0.21クレジット（1章の単価で計算。実際の量は作業ごとに変わります）

### 6. Codexでモデルを切り替えるには

- デスクトップアプリ・IDE の拡張機能: 入力欄の下にあるモデルと強さの切り替えで選びます ✅ [Codex「Models」](https://learn.chatgpt.com/codex/models)
- CLI: 設定を別ファイル（例: `~/.codex/luna.config.toml`）に書き、`codex --profile luna` で呼び出します。Codex 0.134.0 以降は、`config.toml` の中に `[profiles.名前]` と書く方法は読まれません ✅ [Codex「Advanced configuration」](https://learn.chatgpt.com/docs/config-file/config-advanced)
- 公式は「必要な結果が出る、いちばん低い強さを使う」「ほとんどの作業に Max も Ultra も要らない」としています ✅ [Codex「Models」](https://learn.chatgpt.com/codex/models)

### 7. 今日からやること

1. 案件のノートに「期限」のプロパティを付け、Bases で「期限が7日以内の案件」の表を1つ作る（トークン0で毎日見られる）
2. ボルトの AGENTS.md（エージェンツ・エムディー。Codex が作業の前に読むルールファイル）に「指定したノートだけ読む」「作業ごとに Luna・Terra・Astra を振り分ける」を書く ✅ [Codex「AGENTS.md」](https://learn.chatgpt.com/codex/agent-configuration/agents-md)
3. 同じ作業を Luna と Astra で1回ずつ試し、`/status` の数字と結果を記録表に書く。結果が変わらない作業から Luna に移す

<a id="kit"></a>
## プレゼントの中身と受け取り方

1. 🎁 【第二の脳】自動構築キット — AIの質問（最大9問）に答えるだけで、自己紹介・判断基準・進行中の3枚のメモと目次（INDEX.md）の案ができる。毎回説明していた前提をメモに残して、AIに渡せる
2. 🎁 Obsidian × AI トークン節約5点セット — 目次ノート・読む順番・ノートの名札・引き継ぎメモ・節約ルールの5つを、Codex に貼る指示文つきで。必要なメモだけを読ませて、探すための読み込みや説明のし直しを減らす
3. 🎁 AI学習アプリ「HIROGERU」1ヶ月無料クーポン — AIの使い方を基礎から学べるアプリを、1ヶ月無料で使える

受け取りは [プレゼント図書館](https://chaaaaarin.github.io/gift-library/aa/ep/130/) から。動画の概要欄の公式LINEからも案内しています。

## 動画内で補足する用語

| 用語 | 読み | 意味 |
|---|---|---|
| GPT-6 Astra | ジーピーティーシックス・アストラ | OpenAI のいちばん高性能なモデル（2026年9月発表） |
| GPT-5.6 Luna | ジーピーティーファイブポイントシックス・ルナ | OpenAI の速くて手ごろなモデル。決まった形の作業向け |
| GPT-5.6 Terra | テラ | ふだんの仕事向けのバランス型モデル |
| Codex | コーデックス | OpenAI のAIエージェント。アプリや CLI でフォルダを開いて作業する |
| Obsidian | オブシディアン | 無料のメモアプリ。メモをパソコン内のファイルとして持つ |
| ボルト | — | Obsidian でメモを入れるフォルダ（保管庫） |
| プロパティ | — | ノートの先頭に付ける期限・状態などの欄 |
| Bases | ベース | ノートを表やカードの一覧にする Obsidian の標準機能 |
| AGENTS.md | エージェンツ・エムディー | Codex が作業の前に読むルールファイル |
| クレジット | — | Codex の使用量を払う単位 |
| /status | スラッシュ・ステータス | Codex の CLI で、今の会話のトークン使用量を見るコマンド |
| プロファイル | — | モデルや強さの設定をまとめた別ファイル。CLI で `--profile` を付けて呼ぶ |
| CLI | シーエルアイ | 文字で命令して動かす操作方法（コマンドライン） |
| トークン | — | AI が文章を扱う単位。読む量・書く量が増えるほど多く使う |

<!-- research-variant: readme-only -->
