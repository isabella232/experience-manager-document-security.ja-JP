---
cloud: experience-cloud
solution-title: ラーニングとサポート
solution-hub-url: https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=ja
getting-started-title: 概要
getting-started-url: https://helpx.adobe.com/jp/experience-manager/get-started.html
tutorials-title: チュートリアル
tutorials-url: https://experienceleague.adobe.com/?tag=Tutorial&lang=ja#recommended/solutions/experience-manage
mini-toc-levels: 2
git-repo: https://git.corp.adobe.com/AdobeDocs/experience-manager-document-security.ja-JP
index: true
translation-type: ht
source-git-commit: 29c078e0820b42b53eb65061893e45c8cb63e549
workflow-type: ht
source-wordcount: '150'
ht-degree: 100%

---


# 内部使用メタデータ

metadata.md ファイルには、リポジトリー内にあるユーザーガイドの TOC.md ファイルにパススルーされるリポジトリーレベルのメタデータが含まれています。任意のユーザーガイドの metadata.md コンテンツを変更するには、任意の TOC.md ファイル内でそのように処理してください。

| メタデータ | 動作 |
|--- |--- |
| solution-title | 記事ヘッダーでリンクとして使用されます。 |
| solution-hub-url | helpx ハブページを開きます。 |
| solution-icon | ソリューションタイトルの横にソリューションアイコンを表示します。まだ実装されていません。 |
| getting-started-url | helpx の「はじめに」のページへのリンク |
| tutorials-url | ビデオチュートリアル（helpx チュートリアルまたは KT チュートリアル）へのリンク |
| mini-toc-levels | 右側のレールに表示される見出しレベルの数を決定します。デフォルトは 2 です。 |
| git-repo | 内部使用のマスターリポジトリーの場所を指定します。 |

TOC.md ファイル内

| メタデータ | 動作 |
|--- |--- |
| user-guide-title | 記事ヘッダーでリンクとして使用されます。 |
| user-guide-url | helpx ハブページを開きます。 |
