![banner](https://raw.githubusercontent.com/SPGoding/vscode-datapack-helper-plus/master/img/banner.png)

[![Discord](https://img.shields.io/discord/666020457568403505?logo=discord&style=flat-square)](https://discord.gg/EbdseuS)
[![GitHub Actions](https://img.shields.io/github/workflow/status/SPGoding/vscode-datapack-helper-plus/Release?logo=github&style=flat-square)](https://github.com/SPGoding/vscode-datapack-helper-plus/actions)
[![VSCode Marketplace](https://img.shields.io/visual-studio-marketplace/v/SPGoding.datapack-language-server.svg?logo=visual-studio-code&style=flat-square)](https://marketplace.visualstudio.com/items?itemName=SPGoding.datapack-language-server)
[![VSCode Marketplace Downloads](https://img.shields.io/visual-studio-marketplace/d/SPGoding.datapack-language-server.svg?logo=visual-studio-code&style=flat-square)](https://marketplace.visualstudio.com/items?itemName=SPGoding.datapack-language-server)
[![VSCode Marketplace Installs](https://img.shields.io/visual-studio-marketplace/i/SPGoding.datapack-language-server.svg?logo=visual-studio-code&style=flat-square)](https://marketplace.visualstudio.com/items?itemName=SPGoding.datapack-language-server)
[![VSCode Marketplace Rating](https://img.shields.io/visual-studio-marketplace/stars/SPGoding.datapack-language-server.svg?logo=visual-studio-code&style=flat-square)](https://marketplace.visualstudio.com/items?itemName=SPGoding.datapack-language-server)
[![License](https://img.shields.io/github/license/SPGoding/vscode-datapack-helper-plus.svg?style=flat-square)](https://github.com/SPGoding/vscode-datapack-helper-plus/blob/master/LICENSE)
[![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg?style=flat-square)](https://github.com/semantic-release/semantic-release)
[![Gitmoji](https://img.shields.io/badge/gitmoji-%20%F0%9F%98%9C%20%F0%9F%98%8D-FFDD67.svg?style=flat-square)](https://gitmoji.carloscuesta.me/)

#### [English\(original\)](https://github.com/SPGoding/vscode-datapack-helper-plus/blob/master/README.md) / 日本語 / [简体中文](https://github.com/SPGoding/vscode-datapack-helper-plus/blob/master/README-zh_Hans.md)

Data-pack Helper Plusは、advancements, dimensions, dimension types, functions, loot tables, predicates, recipes, あらゆる種類のtags, worldgen設定を含むデータパック内のドキュメントのための強力な言語機能を提供します。

この拡張機能を気に入ったら、私を[支援](https://github.com/sponsors/SPGoding)することも検討してください。他にもバグの報告, 機能の提案, 翻訳のサポートも可能です！ 詳細については[CONTRIBUTING.md](https://github.com/SPGoding/datapack-language-server/blob/master/CONTRIBUTING.md)を参照してください。

- [免責事項](#免責事項)
- [インストール方法](#インストール方法)
- [機能](#機能)
   - [ワークスペースサポート](#ワークスペースサポート)
   - [複数言語のサポート](#複数言語のサポート)
   - [セマンティックハイライト](#セマンティックハイライト)
   - [記入情報](#記入情報)
   - [補完](#補完)
   - [コードスニペット](#コードスニペット)
   - [宣言コメント](#宣言コメント)
   - [エイリアスコメント](#エイリアスコメント)
   - [診断とコードアクション](#診断とコードアクション)
   - [フォーマットと校閲](#フォーマットと校閲)
   - [折りたたみ範囲](#折りたたみ範囲)
   - [Call Hierarchy](#call-hierarchy)
   - [カラーインフォメーション](#カラーインフォメーション)
   - [ホバーインフォメーション](#ホバーインフォメーション)
   - [名前空間パスの移動](#名前空間パスの移動)
   - [定義への移動](#定義への移動)
   - [参照の検索](#参照の検索)
   - [名前の変更](#名前の変更)
   - [構成設定](#構成設定)
   - [キャッシュの再生成](#キャッシュの再生成)

# 免責事項

> [MIT License](https://github.com/SPGoding/vscode-datapack-helper-plus/blob/master/LICENSE)

私たちはあなたのデータパックを安全に保つために最善を尽くしています。しかし、ドキュメントはDHPによって特定の極端な状況下で破損する可能性があり、発生した場合はサポートを提供できません。大切な作業データはクラウドストレージにアップロードするなど、随時**バックアップ**してください。これは、DHPを使用しない場合でも非常に重要です。

# インストール方法

DHPはVSCode Marketplaceからインストール出来ます: [![VSCode Marketplace](https://img.shields.io/visual-studio-marketplace/v/SPGoding.datapack-language-server.svg?logo=visual-studio-code&style=flat-square)](https://marketplace.visualstudio.com/items?itemName=SPGoding.datapack-language-server)

もしくは、VSCodeで`Ctrl + P`を入力し`ext install spgoding.datapack-language-server`を実行します。

**注**: DHPが動作するにはVSCodeのバージョンが最低でも1.44.0以上である必要があります。VSCodeがこのバージョンより新しいことを確認してください。

# 機能

## ワークスペースサポート

データパックのルートフォルダ（`data`フォルダと`pack.mcmeta`ファイルがある階層）をワークスペースのルートフォルダとして使用することで、DHPが最高の機能を提供できるようになります。

さらに、DHPはVSCodeのマルチルートワークスペース機能を完全にサポートしています。`data`フォルダと`pack.mcmeta`ファイルを含むすべてのルートはデータパックと見なされ、補完が提供されます。その他のルートフォルダはDHPの影響を受けません。

同じワークスペース内にある限り、どのルートのコンテンツにもアクセスできます。ワークスペース内のルートの順序は、DHPにおけるこれらのデータパックの優先度に影響します。最初のルートが最初にロードされ、最後のルートが最後にロードされます。これは、Minecraft がデータパックをロードして、同じ名前空間 ID を持ち、同じカテゴリにあるファイルの場合、どちらが別のファイルを上書きするかを決定する方法と全く同じです。例えば、マルチルートのワークスペースが下記のようになっているとしましょう。

```
─── (Root) Datapack A
   ├── data
   |   └── spgoding
   |       └── functions
   |           └── foo.mcfunction
   └── pack.mcmeta
─── (Root) Datapack B
   ├── data
   |   └── spgoding
   |       └── functions
   |           └── foo.mcfunction
   └── pack.mcmeta
```

そして、mcfunctionファイルで`F2`を押してmcfunctionの`spgoding:foo`を`wtf:foo`に名前を変更すると、Datapack A(`Datapack A/data/spgoding/functions/foo.mcfunction`)に同じ名前空間IDを持つmcfunctionがあったとしても、Datapack B(`Datapack B/data/spgoding/functions/foo.mcfunction`)のファイルだけが、Datapack B(`Datapack B/data/wtf/functions/foo.mcfunction`)に移動してしまいます。

これらのコマンドをMinecraftで実行しようとすると、Datapack Bの関数が実行されていることにも気付くことができます。
```mcfunction
datapack enable "file/Datapack A" first
datapack enable "file/Datapack B" last
function spgoding:foo
```

このように動作することにより、DHPはデータパックを処理する順序がMinecraftと一致することを保証します。

**注**: VSCodeにルートフォルダーをドラッグして配置すると、順序を並べ替えることができます。DHPは、ルートフォルダーの優先度をそれに応じて更新します。これは非常に便利です。

## 複数言語のサポート

DHPは複数の言語をサポートしています。現在これらの言語が利用可能です:

| 言語            | VSCode 言語 ID |
| --------------- | -------------- |
| ドイツ語        | `de`           |
| 英語            | `en`           |
| フランス語      | `fr`           |
| イタリア語      | `it`           |
| 日本語          | `ja`           |
| 中国語 (簡体字) | `zh-cn`        |

このプロジェクトを他の言語に翻訳していただけると助かります。詳細については[CONTRIBUTING.md](https://github.com/SPGoding/datapack-language-server/blob/master/CONTRIBUTING.md)を参照してください。

## セマンティックハイライト

> Wiki: https://github.com/ChenCMD/datapack-helper-plus-JP-Wiki/wiki/Semantic-Coloring

すべてのコマンド引数に意味を持った色を付けることができます。[Arcensoth](https://github.com/Arcensotj)の[language-mcfunction拡張機能](https://github.com/Arcensoth/language-mcfunction)をインストールして、カラーリングのフィードバックを高速に取得することもお勧めします。

![semantic-coloring](https://raw.githubusercontent.com/SPGoding/vscode-datapack-helper-plus/master/img/semantic-coloring.png)

## 記入情報

入力中にコマンドの引数に関するヒントを得ることができます。スペースを入力すると記入情報が自動的に表示されます。

または、`Ctrl + Shift + Space`(またはその他の構成済みのホットキー)を使用して、記入情報を手動で表示することもできます。

![signature-help](https://raw.githubusercontent.com/SPGoding/vscode-datapack-helper-plus/master/img/signature-help.gif)

## 補完

拡張機能は、コマンドを入力するときに補完を提供します。次のいずれかの文字を入力すると、補完が自動的に表示されます

`[' ', ',', '{', '[', '=', ':', '/', '!', "'", '"', '.', '@']`.

または、`Ctrl + Space`(またはその他の構成済みのホットキー)を使用して、補完を手動で表示することもできます。

DHPは、単純なコマンドの補完を提供できます。
![simple-completions](https://raw.githubusercontent.com/SPGoding/vscode-datapack-helper-plus/master/img/simple-completions.gif)

より複雑なNBTタグの補完は[Yurihaia](https://github.com/Yurihaia)の[mc-nbtdoc](https://github.com/Yurihaia/mc-nbtdoc)の助けを借りて
![nbt-tag-completions](https://raw.githubusercontent.com/SPGoding/vscode-datapack-helper-plus/master/img/nbt-tag-completions.gif)

また、NBTPathや
![nbt-path-completions](https://raw.githubusercontent.com/SPGoding/vscode-datapack-helper-plus/master/img/nbt-path-completions.gif)

また、テキストコンポーネントや
![text-component-completions](https://raw.githubusercontent.com/SPGoding/vscode-datapack-helper-plus/master/img/text-component-completions.gif)

そして、それらのネストされたコマンドにも
![ohhhhh-completions](https://raw.githubusercontent.com/SPGoding/vscode-datapack-helper-plus/master/img/ohhhhh-completions.gif)

## コードスニペット

DHPはいくつかの有用なコードスニペットを提供します。コードスニペットの詳細については、[VSCodeの公式ドキュメント](https://code.visualstudio.com/docs/editor/userdefinedsnippets)をご覧ください。DHPとVSCodeはどちらもコードスニペットをカスタマイズでき、DHPはVSCodeに基づいているため同じ構文を使用します。

mcfunctionファイルの場合、DHPによって追加されたコードスニペットは、カーソルがコマンドの先頭にあるときにのみ補完リストに表示されますが、VSCodeのファイル`Code/User/snippets/mcfunction.json`によって追加されたスニペットはファイル内のどこにでも表示されます。

VSCodeのコードスニペットをカスタマイズする場合は[公式ドキュメント](https://code.visualstudio.com/docs/editor/userdefinedsnippets)を、DHPのスニペットをカスタマイズする場合は、[構成設定](#構成設定)セクションを参照してください。

![code-snippets](https://raw.githubusercontent.com/SPGoding/vscode-datapack-helper-plus/master/img/code-snippets.gif)

## 宣言コメント

> Wiki: https://github.com/ChenCMD/datapack-helper-plus-JP-Wiki/wiki/Declare-Comment

`#declare|#define <type: string> <id: string> [<description: string>]`を記入すると補完, シンボルの名前変更, およびDHPによる参照/定義の検索に使用される文字列を宣言できます。

ゲーム内では宣言コメントを通常のコメントとして扱います。

![declaration-comments](https://raw.githubusercontent.com/SPGoding/vscode-datapack-helper-plus/master/img/declaration-comments.png)

## エイリアスコメント

> Wiki: https://github.com/ChenCMD/datapack-helper-plus-JP-Wiki/wiki/Alias-Comment

`#alias <type: string> <alias: string> <value: string>`を記入すると特定の引数の補完に表示される文字列を定義できます。これにより、選択したときに別の値が挿入されます。

![alias-comments](https://raw.githubusercontent.com/SPGoding/vscode-datapack-helper-plus/master/img/alias-comments.gif)

## 診断とコードアクション

> Wiki for code actions: https://github.com/ChenCMD/datapack-helper-plus-JP-Wiki/wiki/Code-Actions

DHPは、コマンドに関するリアルタイムの診断を提供します。Minecraftと同様に構文エラーを表示し、さらに詳細な警告を表示することも可能です。

一部の診断には対応するクイックフィックスアクションもあり、簡単に修正できます。

![diagnostics](https://raw.githubusercontent.com/SPGoding/vscode-datapack-helper-plus/master/img/diagnostics.gif)

## フォーマットと校閲

> Wiki: https://github.com/ChenCMD/datapack-helper-plus-JP-Wiki/wiki/Lint-Rules

`Shift + Alt + F`(またはその他の構成済みのホットキー)を押すことにより、現在の機能をフォーマットできます。

また、構成設定で設定できる校正ルールがいくつかあります。DHPは、ユーザーの設定に従わないコマンドのエラーを報告します。

![formatting](https://raw.githubusercontent.com/SPGoding/vscode-datapack-helper-plus/master/img/formatting.gif)

## 折りたたみ範囲

コメント（#regionおよび#endregion）を使用して折りたたみ範囲を作成できます。これにより、mcfunctionファイルの構造がより明確になります。

```mcfunction
#region This is a block of commands
execute if score @s test matches 1 run say 1
execute if score @s test matches 2 run say 2
execute if score @s test matches 3 run say 3
execute if score @s test matches 4 run say 4
execute if score @s test matches 5 run say 5
#endregion
```

または、異なる値のハッシュ記号に続いて少なくとも1つの空白を使用して、異なるレベルの折りたたみ範囲を作成できます。

```mcfunction
#region This is a block of commands
# One
## One - 1
execute if score @s foo matches 1 run say 1
execute if score @s foo matches 2 run say 2
## One - 2
execute if score @s bar matches 1 run say 1
execute if score @s bar matches 2 run say 2
# Two
execute if score @p test matches 1 run say 1
#endregion
```

![folding-ranges](https://raw.githubusercontent.com/SPGoding/vscode-datapack-helper-plus/master/img/folding-ranges.gif)

## Call Hierarchy

この機能は、インサイダーバージョンでのみ使用可能な、提案されたAPIを使用しています。

Call Hierarchyは、関数をナビゲートするための優れた方法です。この機能を使用してfunction, functionTag, AdvancememntRewardsのすべての呼び出し元/呼び出し先を取得できます。この機能のデフォルトのホットキーは`Shift + Alt + H`です。

![call-hierarchy](https://raw.githubusercontent.com/SPGoding/vscode-datapack-helper-plus/master/img/call-hierarchy.gif)

## カラーインフォメーション

DHPはNBTの`dust`パーティクルと`color`タグの色を表示します。カーソルを合わせる事で色を変更出来ます。

![color-information](https://raw.githubusercontent.com/SPGoding/vscode-datapack-helper-plus/master/img/color-information.gif)

## ホバーインフォメーション

この機能は製作段階のものです。

DHPはfunctionの名前空間ID,tag,teamなどの特定の引数にカーソルを合わせると、ユーザー定義のドキュメントを表示します。

<!-- ![hover-on-function]() -->

## 名前空間パスの移動

名前空間IDをCtrlキーを押しながらクリックすると advancements, loot tables, functions, predicates, あらゆる種類のtagsに移動できます。

![document-link](https://raw.githubusercontent.com/SPGoding/vscode-datapack-helper-plus/master/img/document-link.gif)

## 定義への移動

`Ctrl`キーを押しながらobjectives, entities, tags, teams, bossbars, and data storagesをクリックすると定義に移動できます。

![goto-definition](https://raw.githubusercontent.com/SPGoding/vscode-datapack-helper-plus/master/img/goto-definition.gif)

## 参照の検索

`Shift + F12`(またはその他の構成済みのホットキー)を押すと、ワークスペースでobjectives, entities, tags, teams, bossbars, data storages, advancements, functions, loot tables, predicates, recipes, あらゆる種類のtagsの参照を見つけることができます。

![peek-references](https://raw.githubusercontent.com/SPGoding/vscode-datapack-helper-plus/master/img/peek-references.gif)

## 名前の変更

entity, tags, teams, bossbars, data storages, advancements, functions, loot tables, predicates, recipes, あらゆる種類のtagsの名前を変更するには、それらの名前にカーソルを合わせ`F2`またはその他の構成済みキーを押します。

ワークスペース全体で同じシンボルのすべての参照の名前が変更されます。

![rename-objective](https://raw.githubusercontent.com/SPGoding/vscode-datapack-helper-plus/master/img/rename-objective.gif)

さらに、ファイル定義を使用して名前空間付きID(例: advancements, functions, loot tables, predicates, recipes, Tagsの)の名前を変更すると、ワークスペース内の対応するファイルも名前変更/移動されます。

![rename-function](https://raw.githubusercontent.com/SPGoding/vscode-datapack-helper-plus/master/img/rename-function.gif)

**ただし**、ワークスペース内のファイルの名前を手動で変更しても、ファイルの名前空間IDは更新されず、キャッシュに問題が発生する可能性があります。
その場合は[キャッシュの再生成](#キャッシュの再生成)を実行してください。

## 構成設定

`Ctrl + ,`(またはその他の構成済みのホットキー)を押してVSCodeの[設定]ページを開き、`datapack`と入力しDHPが提供するすべての構成設定を検索します。独自のコードスニペットを追加し、必要に応じて校閲の設定と環境情報を設定できます。これらの構成は、現在のユーザーまたはワークスペースに対して変更できます。設定の構成について詳しくは、[VSCodeの公式ドキュメント](https://code.visualstudio.com/docs/getstarted/settings)をご覧ください。

## キャッシュの再生成

DHPはキャッシュを使用して、名前の変更、参照/定義の検索、ドキュメントリンクなどのプロセスを高速化します。しかし、さまざまな理由によりキャッシュが古くなり奇妙な動作を引き起こす可能性があります。その場合`Datapack: Regenerate Cache`コマンド(日本語名: `Datapack: キャッシュを再生成する`, ID: `datapack.regenerateCache`)を使用して、キャッシュを手動で再生成できます。

- - -
翻訳: [ちぇん](https://twitter.com/CMD__Cat)

翻訳に気になる点がありましたら気軽に連絡ください。
