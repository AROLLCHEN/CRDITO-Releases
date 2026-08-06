<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="src/Lcsc2Ad.App/Assets/Crdito-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="src/Lcsc2Ad.App/Assets/Crdito.svg">
    <img src="src/Lcsc2Ad.App/Assets/Crdito.svg" width="104" height="104" alt="CRDITO Logo">
  </picture>
  <h1>CRDITO</h1>
  <p><strong>JLC / LCSC と Altium Designer をつなぐ部品ライブラリーツール</strong></p>
  <p>部品の検索、検証、プレビュー、書き出し、Altium Designer への直接配置を一つのアプリで。</p>
  <p>
    <a href="README.md">简体中文</a> · <a href="README.en.md">English</a> · 日本語
  </p>
  <p>
    <a href="https://github.com/AROLLCHEN/CRDITO-Releases/releases/latest"><img src="https://img.shields.io/github/v/release/AROLLCHEN/CRDITO-Releases?display_name=tag&style=flat-square&color=0969da" alt="最新リリース"></a>
    <a href="https://github.com/AROLLCHEN/CRDITO-Releases/releases"><img src="https://img.shields.io/github/downloads/AROLLCHEN/CRDITO-Releases/total?style=flat-square&color=1f883d" alt="ダウンロード数"></a>
    <img src="https://img.shields.io/badge/Windows-10%20%7C%2011-0078d4?style=flat-square" alt="Windows 10/11">
    <img src="https://img.shields.io/badge/Altium-22%20%7C%2026-a35c00?style=flat-square" alt="Altium Designer 22/26">
    <img src="https://img.shields.io/badge/license-Proprietary-555?style=flat-square" alt="プロプライエタリライセンス">
  </p>
  <p>
    <a href="https://github.com/AROLLCHEN/CRDITO-Releases/releases/download/v1.0.9/CRDITO-Setup-1.0.9-win-x64.exe"><strong>CRDITO 1.0.9 をダウンロード</strong></a>
    ·
    <a href="https://github.com/AROLLCHEN/CRDITO-Releases/releases/latest">リリースノート</a>
  </p>
</div>

---

CRDITO は電子設計ワークフロー向けの Windows デスクトップツールです。JLC / LCSC の部品データを検証済みの Altium Designer 回路図ライブラリーと PCB ライブラリーに変換し、シンボル、フットプリント、STEP 3D モデルをプレビューできます。

## プレビュー

<p align="center">
  <img src="docs/images/online-3d-preview-gpu.png" width="92%" alt="CRDITO 3D モデルプレビュー">
</p>

<table>
  <tr>
    <td width="50%" align="center">
      <img src="docs/images/online-component-details.png" alt="CRDITO 部品情報"><br>
      <sub>部品情報とコピー可能なパラメーター</sub>
    </td>
    <td width="50%" align="center">
      <img src="docs/images/online-footprint-preview.png" alt="CRDITO PCB フットプリントプレビュー"><br>
      <sub>最終パッド形状を使用した PCB プレビュー</sub>
    </td>
  </tr>
</table>

## 操作ガイド

### 1. 部品を検索して検証する

1. 上部でデータソースを選択します。オンライン部品には **JLC EDA オンラインモデル**を使用します。
2. LCSC 部品番号、MPN、メーカー、キーワード、パッケージを入力します。必要に応じて在庫と EDA モデルのフィルターを有効にします。
3. 左側から一つの結果を選択します。CRDITO は読み込み中と検証中の状態を表示し、両方が完了してから書き出しと配置を有効にします。
4. 上部で MPN、パッケージ、説明、データシートを確認します。検証エラーがある場合は書き出さず、更新するか正しい部品を選び直してください。

### 2. 回路図、フットプリント、3D を確認する

- **回路図**、**PCB フットプリント**、**3D モデル**、**パラメーター**の各タブを使用するか、**表示 → 4 ビュー**で同時に比較します。
- 回路図とフットプリントはホイールでズームし、左ドラッグで移動できます。3D はドラッグで回転、ホイールでズームでき、アイソメ、上、下、前、後、左、右の視点を選択できます。
- **表示 → フットプリント寸法を表示**で外形寸法を確認します。**ツール → 長さを測定**を選び、二点をクリックして測定します。辺、頂点、中心、水平、垂直のスナップに対応し、`Esc` で終了します。
- コンパクトモードでは、部品名と検証状態の間に**データシート**への入口が表示されます。有効なリンクがある部品だけに表示され、クリックすると既定のブラウザーで開きます。

### 3. Altium ライブラリーを書き出す

1. **設定 → 回路図書き出しの既定表示**で、デジグネーター、コメント、ピン名、ピン番号を選択します。
2. 部品を選択し、**AD ライブラリーを書き出す**をクリックして出力先を指定します。
3. バイナリー再読込とピン—パッド対応の検証完了を待ちます。成功すると `.SchLib`、`.PcbLib`、STEP、`.validation.json` が生成されます。

### 4. Altium Designer に直接配置する

1. AD で対象プロジェクトと回路図ドキュメントを開き、回路図キャンバスを編集可能な状態にします。
2. CRDITO で **AD に配置**を選択します。同時に保持される配置待ちタスクは一つだけです。
3. AD に切り替え、回路図キャンバス内をダブルクリックして配置を開始します。部品がポインターに追従し、プロジェクト内の統合 SchLib/PcbLib に関連付けられます。
4. 同じ部品を繰り返し配置する場合は、**設定**で**同じ部品を連続配置**を有効にします。配置を確定するたびに次の部品が作成され、`Esc` で終了します。
5. **設定 → Esc キーを押したとき**で、現在の部品を削除するか、配置だけを終了するかを選択できます。

> ヒント：`Ctrl` を押しながら設定可能な上部メニュー項目をクリックすると、ショートカットを割り当てられます。保存前に競合が検出されます。**常に手前に表示**と**固定時にコンパクトモードへ移行**を使うと、部品選択と連続配置をコンパクトな画面で継続できます。

## 主な機能

| 機能 | 内容 |
| --- | --- |
| 部品検索 | LCSC 部品番号、MPN、キーワード、パッケージで検索し、追加読み込みとローカルキャッシュに対応 |
| 一貫したプレビュー | 書き出しと同じ変換ルールでシンボル、PCB フットプリント、3D モデルを表示 |
| ネイティブライブラリー出力 | AD を起動せずに `.SchLib`、`.PcbLib`、STEP、検証レポートを生成 |
| 直接配置 | CRDITO から配置タスクを作成し、AD の回路図上で統合フットプリントライブラリーと関連付けて配置 |
| 連続配置 | 配置確定後に同じ部品の次の配置を自動作成でき、`Esc` で終了 |
| 厳密な検証 | ピン、パッド、長穴、異形パッド、マルチユニットシンボル、モデル位置、バイナリー再読込を確認 |
| 快適な確認操作 | 4 ビュー、滑らかなズーム、寸法測定、視点切り替え、大容量 STEP のメッシュキャッシュに対応 |

## クイックスタート

1. [Releases](https://github.com/AROLLCHEN/CRDITO-Releases/releases/latest) から最新版をダウンロードしてインストールします。
2. 部品を検索し、回路図、PCB フットプリント、3D ビューを確認します。
3. ライブラリーを単独で書き出すか、**AD に配置**を選択して Altium Designer の配置フローを開始します。

インストーラーは Windows 10/11 x64 向けで、.NET、NPNP、OCC、VC++ ランタイム、AD 配置拡張を同梱しています。インストール先は選択可能で、管理者権限が必要です。Altium Designer 本体と商用ライセンスは含まれません。

> Altium Designer がなくても検索、プレビュー、単独書き出しは利用できます。直接配置と PCB 更新には互換性のある Altium Designer 環境が必要です。

## 出力ファイル

```text
部品データ
├── Altium 回路図ライブラリー (.SchLib)
├── Altium PCB ライブラリー (.PcbLib)
├── STEP 3D モデル (.step)
└── 検証レポート (.validation.json)
```

CRDITO はライブラリーを公開する前に、生成したバイナリーファイルを独立して再読込します。ピン不足、識別子の重複、ピンとパッドの対応不一致、形状検証エラーがある場合は書き出しを停止します。

## 詳細情報

- [バージョンとリリースノート](https://github.com/AROLLCHEN/CRDITO-Releases/releases)
- [問題の報告](https://github.com/AROLLCHEN/CRDITO-Releases/issues)
- [ソフトウェアライセンス](LICENSE)
- [サードパーティー通知](docs/THIRD-PARTY-NOTICES.md)

## データ、商標、ライセンス

オンライン部品データはユーザーが明示的に検索した場合のみ取得します。無人の一括クロールや、ログイン・CAPTCHA の回避は行いません。JLC、LCSC、EasyEDA、Altium Designer、および各コンテンツ権利者の条件を遵守してください。

CRDITO は独立した相互運用ツールであり、これらの企業との提携、スポンサー関係、推奨関係はありません。CRDITO はプロプライエタリソフトウェアです。Copyright © 2026 AROLLCHEN. 詳細は [LICENSE](LICENSE) を参照してください。ソースリポジトリは非公開で、公式インストーラーと更新メタデータは公開 [CRDITO-Releases](https://github.com/AROLLCHEN/CRDITO-Releases) リポジトリからのみ配布します。

<p align="right"><a href="#crdito">トップへ戻る</a></p>
