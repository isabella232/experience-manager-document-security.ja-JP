---
title: AEM Document Security for Microsoft Office - リリースノート
description: AEM Document Security 6.2 Extension for Microsoft Office をインストールする前に、リリースノートをお読みください。
uuid: f6ab73d4-ac4e-4fff-9bb8-917b75401653
content-type: reference
topic-tags: installing
discoiquuid: c9342c28-8289-4831-a613-4bc03431f557
exl-id: 582f10bb-60d2-46ed-b81d-5818a040edc6
source-git-commit: 28137f26afc024d411857d44887bf69fe1ee2b81
workflow-type: tm+mt
source-wordcount: '1030'
ht-degree: 58%

---

# AEM Document Security for Microsoft Office - リリースノート{#aem-document-security-for-microsoft-office-release-notes}

## AEM Document Security for Microsoft Office の新機能 {#whats-new-in-aem-document-security-for-microsoft-office}

* **Office 2019 のサポート**:Microsoft Office 用 Document Security Extension に、Microsoft Office 2019 のサポートが追加されました。 また、Office 365 の一部としてインストールされたMicrosoft Office 2019 デスクトップアプリケーションでも動作すると想定されます。

>[!NOTE]
>
>この記事では、「Adobe Experience Manager Document Security for Microsoft Office」、「Adobe Experience Manager Document Security Extension for Microsoft Office」、「Document Security Extension for Microsoft Office」の各用語を同じ意味で使用します。

## AEM Document Security Extension for Microsoft Office のインストールと設定 {#installing-and-configuring-aem-document-security-extension-for-microsoft-office}

本バージョンの Document Security Extension for Microsoft Office は、Adobe LiveCycle Rights Management ES2 以降、および AEM Forms 向け Document Security アドオンと互換性があります。

AEM Document Security Extension for Microsoft Office をインストールする前に、このドキュメントの情報を確認してください。 詳細なインストール手順については、[AEM Document Security Extension for Microsoft Office のインストールと設定方法](installing-configuring-aemdsext.md)の記事を参照してください。

## 修正された問題 {#fixed-issues}

* 文字列が垂直方向に表示され、間違った改行がコンテンツに追加されます。 （参照番号 CQ-4201054）

## 既知の問題 {#known-issues}

### サードパーティ製プラグインがサポートされていない {#third-party-plug-ins-not-supported}

AEM Document Security Extension for Microsoft Office は、サードパーティのプラグインでは動作しません。 Document Security Extension for Microsoft Office をインストールする前に、Microsoft Office 用のサードパーティ製プラグインをアンインストールします。

### Microsoft Word、Excel、および PowerPoint でメニューオプションが無効になる {#disabled-menu-options-in-microsoft-word-excel-and-powerpoint}

AEM Document Security Extension for Microsoft Office は組み込みの保護機能を使用して、ドキュメント、ワークシート、およびプレゼンテーションを保護します。Excel、Word、PowerPoint のメニューオプションの一部が無効になります。

### Microsoft Office 2013、2016、2019 の制限 {#restrictions-for-microsoft-office}

Microsoft Office では、保護されたセッション中は次のオプションを使用できません。

* Microsoft Office 2016 またはMicrosoft Office 2019

   * ファイル/名前を付けて保存
   * ファイル/履歴
   * ファイル/共有
   * ファイル/エクスポート
   * ファイル/公開
   * ファイル/アカウント
   * ファイル/情報/ Protectドキュメント/ワークブック/プレゼンテーション/パスワードによる暗号化
   * ファイル/情報/Protectドキュメント/デジタル署名の追加
   * ファイル/情報/Protectドキュメント/最終版にする
   * 右上の共有オプション

* Microsoft Office 2013

   * ファイル/名前を付けて保存
   * ファイル/共有
   * ファイル/エクスポート
   * ファイル/アカウント
   * ファイル/情報/ Protectドキュメント/ワークブック/プレゼンテーション/パスワードによる暗号化
   * ファイル/情報/Protectドキュメント/デジタル署名の追加
   * ファイル/情報/Protectドキュメント/最終版にする

### 保護されたドキュメントを SharePoint Server から開けない {#opening-a-protected-document-from-sharepoint-server}

保護されたドキュメントを開く：ファイルタイプに関連付けられている Microsoft Office プログラム（Microsoft Word、Microsoft Excel、Microsoft PowerPoint など）を先に開かずに、Document Security Extension for Microsoft Office で保護されたドキュメントを SharePoint Server から開こうとすると、ドキュメントが開かれない場合があります。該当するプラグインをインストールする必要があることを示すエラーメッセージが表示されます。したがって、Document Security Extension for Microsoft Office で保護されたドキュメントを SharePoint Server から開く前に、関連付けられている Microsoft Office プログラムを開くことをお勧めします。

（オプション）Document Security Extension for Microsoft Office で保護されたドキュメントを SharePoint Server から開く前に、キャッシュフォルダーを空にすることをお勧めします。

保護されたドキュメントをSharePoint Server から開くと、適用されたポリシーに関係なく、ドキュメントに対するすべての権限が無効になります。

### プリンターがインストールされていないMicrosoft Excel 2013、Microsoft Excel 2016、Microsoft Excel 2019 の各ファイルに動的透かしを含むポリシーを適用する {#apply-a-policy-with-a-dynamic-watermark-to-microsoft-excel-microsoft-excel-and-microsoft-excel-file-with-no-printer-installed}

プリンターがインストールされていないコンピューターでMicrosoft Excel 2013、Microsoft Excel 2016、Microsoft Excel 2019 の各ファイルに動的透かし付きのポリシーを適用し、ファイルを保存すると、次のエラーが表示されます。&quot;動的な透かしを適用中に内部エラーが発生しました。&quot; このエラーは、保護ファイルを再度開くときにも表示されます。透かしは適用されず、表示／ページレイアウトにも表示されません。

### サポートされている Office アプリケーションの Windows データ実行防止機能を無効にする {#disable-windows-data-execution-prevention-for-supported-office-applications}

Document Security Extension for Microsoft Office を使用するときは、Windows データ実行防止（DEP）機能を無効にすることをお勧めします。

### 共有中の Microsoft Office ファイルは Document Security Extension を使用して保護できない {#shared-microsoft-office-files-cannot-be-protected-using-document-security-extension}

共有中の Microsoft Office ファイルを Document Security Extension を使用して保護すると、エラーが発生し、共有ファイルが保護されません。

### Document Security Extension for Microsoft Office および McAfee VirusScan がインストールされている PC 上で Office アプリケーションを起動する {#starting-office-applications-on-a-machine-containing-document-security-extension-for-microsoft-office-and-mcafee-virusscan}

Document Security がインストールされ、McAfee VirusScan の On-Access Scan 機能が有効なコンピューターで Office アプリケーションをスムーズに起動するには、McAfee VirusScan Console の「Buffer Overflow Protection」オプションを無効にしてください。

### サポートされていないMicrosoft Office 言語を使用しているコンピューターにMicrosoft Office 用 Document Security Extension をインストールする {#installing-document-security-extension-for-microsoft-office-on-a-machine-with-an-unsupported-microsoft-office-language}

サポートされていない言語のMicrosoft Office アプリケーションを使用しているコンピュータにMicrosoft Office 用 Document Security Extension をインストールする前に、少なくとも 1 回 Office アプリケーションを開いてください。

### 「オフライン同期」ボタンは、ユーザーにオフライン権限がない場合でも有効になります {#synchronize-offline-button-is-enabled-even-when-a-user-does-not-have-offline-permissions}

ユーザーにドキュメントに対するオフライン権限がない場合でも、「オフライン同期」ボタンを使用できます。 ただし、「 」ボタンを選択しても何も実行されません。

### Microsoft Officeの体験版はサポート対象外 {#no-support-for-trial-versions-of-microsoft-office}

AEM Document Security Extension for Microsoft Office は体験版の Microsoft Office をサポートしていません。拡張機能をインストールする前に、ライセンス取得済みの Microsoft Office がインストールされ、ライセンス認証が完了していることを確認してください。

### 保護された Microsoft Office ファイルを開けない {#unable-to-open-a-protected-microsoft-office-files}

Microsoft Office の保護ビューが有効の場合、Right Management Extension は保護された Microsoft Excel ファイル（XLS、XLSX）および保護された Microsoft PowerPoint（PPT）ファイルをリモート場所から開くことができません。

### 画像や背景色を含む Microsoft Excel 文書のセルが透かしの上に表示される {#cells-of-microsoft-excel-document-containing-an-image-or-background-color-appear-on-top-of-watermark}

Microsoft Excel 文書のセルに画像が含まれているか、または背景色で塗りつぶされていて、動的透かしポリシーが文書に適用されている場合、セルに埋め込まれた画像や背景色が透かしの上に表示され、透かしが覆われます。

### 複数の証明書に関するユーザビリティの問題 {#usability-issue-with-multiple-certificates}

クライアントマシン上の複数の証明書が存在し、ユーザーが証明書選択ダイアログをキャンセルすると、このダイアログが再び表示され、ユーザーはダイアログを 2 回キャンセルすることになります。

### 保護されたドキュメントを Microsoft PowerPoint で編集できる {#microsoft-powerpoint-allows-editing-protected-documents}

保護されたドキュメントを編集しようとすると、Microsoft PowerPoint に「このドキュメントを変更できません。 変更を保存することはできません。」 しかし、メッセージを閉じた後も、引き続きテキストの追加や編集をおこなうことができます。ただし、保護されたドキュメントに加えた変更は保存されません。

上記の動作は、PowerPoint 2013、PowerPoint 2016、および PowerPoint 2019 で期待される動作です。