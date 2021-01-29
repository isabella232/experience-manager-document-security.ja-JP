---
title: AEM Document Security Extension for Microsoft Office のインストールと設定
description: このドキュメントでは、Adobe Experience Manager Document Security Extension 6.2 for Microsoft Office のインストールおよび設定手順を詳しく説明します。
uuid: 9d7eb6bb-4780-4d82-8657-7c6c6d523af0
content-type: reference
topic-tags: installing
discoiquuid: f1cdf344-efe4-4cb5-9fc3-47ee4ba5faf4
translation-type: tm+mt
source-git-commit: ac385c538cdd7d3bb4772b92ee7a94b003595f56
workflow-type: tm+mt
source-wordcount: '2796'
ht-degree: 69%

---


# AEM Document Security Extension for Microsoft Office のインストールと設定{#installing-and-configuring-aem-document-security-extension-for-microsoft-office}

このドキュメントでは、Adobe Experience Manager Document Security Extension for Microsoft Office のインストールおよび設定手順を詳しく説明します。

このドキュメントには、次のタスクに関する情報が含まれます。

* Document Security Extension for Microsoft Office のインストール
* AEM 6.0Forms以降向けのLiveCycle Rights Management ES2以降またはドキュメントセキュリティアドオンを参照するようにインストーラを事前設定する。
* デフォルトポリシーの自動適用を設定する

## インストールの前に {#before-you-install}

Document Security Extension for Microsoft Office をインストールする前に、以下の事柄を確認または実行してください。

* [『リリースノート』](document-security-extension-release-notes.md)を読んでいる
* Microsoft Office のライセンス認証を完了しているライセンス認証画面は、Microsoft Office アプリケーションを開いても表示されません。
* Microsoft Windows および Microsoft Office 用の最新のサービスパックがインストールされている
* サポートされていない言語に対して Document Security for Microsoft Office をインストールする場合は、その前に Office アプリケーションを少なくとも 1 回は開いてください。

>[!NOTE]
>
>名前に全角文字を含むフォルダーには本ソフトウェアをインストールしないでください。このようなフォルダーにインストールすると、AEM Document Security のメニューが Microsoft Office に表示されません。

>[!NOTE]
>
>64 ビット版のオペレーティングシステムに 32 ビット版の Document Security 拡張機能をインストールすることはできますが、この逆はサポートされていません。つまり、64 ビット版の Document Security Extension for Microsoft Office を 32 ビット版のオペレーティングシステムにインストールすることはできません。

### McAfee VirusScan&amp; {#disable-mcafee-virusscan}を無効にする

Document Security Extension がインストールされ、McAfee VirusScan の On-Access Scan 機能が有効なコンピュータで Office アプリケーションをスムーズに起動するには、McAfee VirusScan Console の「Buffer Overflow Protection」オプションを無効にしてください。

### サードパーティ製プラグインをアンインストールする {#uninstall-third-party-plug-ins}

AEM Document Security Extension for Microsoft Office は Microsoft Office アプリケーション向けのサードパーティ製プラグインをサポートしていません。この拡張機能はサードパーティ製プラグンと競合するため、Document Security for Microsoft Office をインストールする前に、アドビ製以外の Microsoft Office 向けプラグインをすべてアンインストールする必要があります。サードパーティ製プラグインがインストールされている場合、アドビでは、Document Security for Microsoft Office アプリケーションのサポートを提供できません。

## システム要件 {#system-requirements}

### ドキュメントセキュリティ拡張クライアント{#document-security-extension-client}

ドキュメントセキュリティ拡張機能をインストールする最小構成を、次のとおりにします。

* 32 ビット版または 64 ビット版の Microsoft Windows 7 または Windows 10 英語版、フランス語版、ドイツ語版、日本語版、イタリア語版、スペイン語版、ポルトガル語（ブラジル）版、韓国語版、中国語（簡体字）版または中国語（繁体字）版。
   **注：***Document Security Extension for Microsoft Office は Microsoft Surface シリーズのデバイスでも動作すると想定されます。*

* 32 ビット版または 64 ビット版の Microsoft Office 2013、2016、2019 および Office 365 の一部としてインストールされたデスクトップ用アプリケーションの英語版、フランス語版、ドイツ語版、日本語版、イタリア語版、スペイン語版、ポルトガル語（ブラジル）版、韓国語版、中国語（簡体字）版または中国語（繁体字）版。

   **注**：*AEM Document Security Extension for Microsoft Office は Microsoft Office アプリケーション向けのサードパーティ製プラグインをサポートしていません。この拡張機能はサードパーティプラグインと競合する場合があるため、Document Security Extension for Microsoft Office をインストールする前に、アドビ製以外の Microsoft Office アプリケーション用プラグインをアンインストールする必要があります。 サードパーティ製プラグインがインストールされている場合、アドビでは、Document Security Extensions for Microsoft Office アプリケーションのサポートを提供できません。*

* 1.3 GHz 以上のプロセッサー
* 2 GB の RAM
* 100 MB のハードディスク容量

### Document Security {#document-security}

Document Security Extension を使用するには、Adobe LiveCycle Rights Management ES2 以降または AEM 6.0 Forms 以降向けの Document Security アドオンに接続できる必要があります。

## Document Security Extension for Microsoft Office のインストール  {#installing-document-security-extension-for-microsoft-office}

インストーラーは[ダウンロードページ](download-installer.md)からダウンロードできます。 インストーラーの実行可能ファイルを直接カスタマイズすることはできませんが、ソフトウェアを対話形式でインストールすることも、サイレントインストールを実行することもできます。ソフトウェアをインストールするには、管理者として Windows にログインします。

32 ビット版と 64 ビット版の Microsoft Office Excel には、それぞれ別のインストーラーが用意されています。32 ビット版 Microsoft Office Excel の場合は、DocumentSecurityExtensionforMicrosoftOffice.exe をダウンロードします。64 ビット版 Microsoft Office Excel の場合は、umentSecurityExtensionforMicrosoftOffice64.exe をダウンロードします。

>[!NOTE]
>
>このドキュメントでは、32 ビット版のインストーラファイル（DocumentSecurityExtensionforMicrosoftOffice.exe）を使用しながら、各種のコマンドやオプションについて説明します。64 ビット版の Microsoft Office を使用している場合、このドキュメントに記載されている操作を実行するには、64 ビット版のインストーラーファイル（DocumentSecurityExtensionforMicrosoftOffice64.exe）を使用してください。

### 無人モードでのインストール {#install-in-silent-mode}

WinZipなどのファイル抽出ユーティリティを使用して、インストーラーファイルから`DocumentSecurityExtensionforMicrosoftOffice.exe`を抽出します。 コマンドプロンプトを開き、セットアップファイルが含まれているディレクトリに移動し、次のように入力します。

`DocumentSecurityExtensionforMicrosoftOffice.exe -s -a -s -v" /qn"`

インストーラーは、MSIファイルとしても利用でき、カスタマイズに使用できます。

### MSIファイルをサイレントモードでインストール{#install-an-msi-file-in-silent-mode}

1. WinZipなどのファイル抽出ユーティリティを使用して、ZIPファイルから`DocumentSecurityExtensionforMicrosoftOffice.msi`ファイルを抽出します。

1. コマンドプロンプトを開き、MSI ファイルが含まれているフォルダーに移動し、次のように入力します。

   `msiexec /I DocumentSecurityExtensionforMicrosoftOffice.msi /qn`

## ドキュメントセキュリティに接続するためのインストーラの事前設定{#preconfiguring-the-installer-to-connect-to-document-security}

ドキュメントセキュリティ拡張機能（Microsoft Office版）のインストーラーを事前設定して、LiveCycleまたはAEMサーバーを指すようにし、ドキュメントセキュリティ拡張機能（Microsoft Office版）をインストールしたユーザーは、接続を設定せずに機能を使用できます。 したがって、保護されたドキュメントは、設定を必要とせずに開くことができます。 ただし、新しいドキュメントは、特定のサーバーを使用するようにクライアントを設定するまで保護できません。

MSI ファイルを作成し設定する方法を以下の手順で説明します。このMSIファイルには、企業にインストールされているLiveCycleまたはAEMサーバーに対して、Microsoft Office用ドキュメントセキュリティ拡張機能のインストーラーを事前に構成するために必要なレジストリ値が含まれています。

### インストーラー{#prerequisites-for-customizing-the-installer}をカスタマイズするための前提条件

Orcaデータベースエディターを使用してインストーラーをカスタマイズします。 次の手順では、Orcaデータベースエディターを使用してMSIインストールファイルのコピーを変更し、カスタムMSIファイルを作成する方法を説明します。 Orca は、Windows SDK for Windows Server 2008 および .NET Framework 3.5 に含まれています。Orca を使用して Microsoft Windows® Installer ファイルを編集する方法については、[『Microsoft サポート』](http://support.microsoft.com/kb/255905/EN-US/) を参照してください。

>[!NOTE]
>
>カスタムMSIファイルを作成する前に、すべてのインストーラーファイルの完全なバックアップを作成することをお勧めします。

#### Orca {#install-orca}のインストール

1. Windows SDK for Windows Server 2008 および .NET Framework 3.5 を[『Microsoft Download Center』](http://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=11310) からダウンロードします。
1. \Microsoft SDK\binフォルダー内のOrca.msiファイルを重複がクリックします。

   また、インストーラーファイルのMSIバリアントも必要です。 Adobeサポートに問い合わせて、MSIインストーラーの最新バージョンを入手してください。

   >[!NOTE]
   >
   >インストーラーを実行する前に、必ずDocumentSecurityExtensionforMicrosoftOffice.msiファイルを閉じてください。 OrcaがMSIファイルを使用している場合は、インストーラーを実行できません。

### MSIファイル{#create-and-configure-the-msi-file}の作成と設定

1. **[!UICONTROL スタート／プログラム／Orca]** をクリックします。

1. **[!UICONTROL ファイル／開く]**&#x200B;をクリックし、`DocumentSecurityExtensionforMicrosoftOffice.msi` ファイルを参照します。

1. テーブルのリスト（左側）から「プロパティ」を選択します。

1. 企業向けにインストールされた Rights Management または Document Security に合わせて、以下のキー名の値を編集します。

<table>
 <tbody>
  <tr>
   <td><p><strong></strong><strong></strong><strong>キー名</strong></p> </td>
   <td><p><strong>説明</strong></p> </td>
   <td><p><strong></strong><strong></strong><strong>キー値のデフォルト</strong></p> </td>
  </tr>
  <tr>
   <td><p><code>APS_SERVER_NAME</code></p> </td>
   <td><p>表示名。</p> </td>
   <td><p>デフォルトのサーバー</p> </td>
  </tr>
  <tr>
   <td><p><code>APS_SERVER_URL</code></p> </td>
   <td><p>ホストサーバーのURL。</p> </td>
   <td><p>https://default.corp.com:1234</p> </td>
  </tr>
 </tbody>
</table>

1. テーブルのリスト（左側）から「レジストリ」を選択します。

1. 次のキー名の値を編集します。

   | **キー名** | **説明** | **キー値のデフォルト** |
   |---|---|---|
   | `IsDefault` | デフォルトのAPSサーバー。 | デフォルトのサーバー |

1. 変更したファイルを、元のMSIインストーラーが格納されているのと同じディレクトリに保存します。

   >[!NOTE]
   >
   >一般的には、元の MSI ファイルと同じファイル名を使用します（例：`DocumentSecurityExtensionforMicrosoftOffice.msi`）。

## デフォルトポリシー{#configuring-automatic-application-of-a-default-policy}の自動適用の設定

構成の一環として、既定のポリシーの自動適用を構成し、Microsoft Officeのドキュメントセキュリティ拡張機能で保存されたすべてのドキュメントを保護することができます。

次のいずれかのオプションを指定できます。

* すべてのドキュメントをデフォルトのポリシーでProtectします。
* ユーザーがサーバーに接続できない場合に、保護されていない形式でファイルをオプションで保存できるようにします。 この柔軟性により、ドキュメントとの接続を切断した状態（例えば、飛行機の中など）でユーザーがネットワークを作成している場合に対応できます。

ポリシーの自動適用機能を有効にすると、次の場合にドキュメントがデフォルトのポリシーで保護されます。

* ユーザーが新しく作成したドキュメントを編集して保存
* ユーザーは、保護されていないドキュメントを編集して保存します。
* ユーザーがアプリを開き、デフォルトのドキュメントで開き、編集して、ドキュメントを保存します

### MSIファイルで自動適用ポリシー機能を設定  {#configure-the-auto-apply-policy-feature-in-the-msi-file}

操作を開始する前に、本記事で前述したように、LiveCycle サーバーまたは AEM Forms サーバーを参照するようにインストーラーを事前設定します。

1. **[!UICONTROL スタート／プログラム／Orca]** をクリックします。

1. **[!UICONTROL ファイル／開く]**&#x200B;をクリックし、`DocumentSecurityExtensionforMicrosoftOffice.msi` ファイルを参照します。

1. テーブルのリスト（左側）から「プロパティ」を選択します。

1. 企業向けにインストールされた Rights Management または Document Security に合わせて、以下のキー名の値を編集します。

<table>
 <tbody>
  <tr>
   <td><p><strong>キー名</strong></p> </td>
   <td><p><strong>説明</strong></p> </td>
   <td><p><strong></strong><strong></strong><strong>キー値のデフォルト</strong></p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_IS_AUTO_ APPLY</code></p> </td>
   <td><p>自動適用ポリシー機能を有効または無効にします。</p> <p><code>1</code>: Enable（有効）</p> <p>0:無効</p> </td>
   <td><p>0</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_POLICY_I D</code></p> </td>
   <td><p>新しいドキュメントが保存されるときに使用するポリシーGUIDです。 自動適用ポリシー機能に適用されます。</p> </td>
   <td><p>RMサーバーに表示される16進数のポリシーID</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_SERVER_U RL</code></p> </td>
   <td><p>サーバー URL.</p> </td>
   <td><p>default.corp.com</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_SERVER_P ORT_NO</code></p> </td>
   <td><p>サーバーのポート番号。</p> </td>
   <td><p>1234</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_ALLOW_UN PROTECTED_SAVE</code></p> </td>
   <td><p>最初の保存時に、ドキュメントを保護するためにクライアントがサーバーに接続できない場合に、ドキュメントセキュリティ保護なしでドキュメントを作成できるかどうかを指定します。</p> <p>1:保護されていない保存を許可する </p> <p>0:クライアントがドキュメントを保存するためにサーバーに接続できない場合に、新しいドキュメントを作成しないようにします。</p> </td>
   <td><p>0</p> </td>
  </tr>
 </tbody>
</table>

>[!NOTE]
>
>`AUTO_APPLY_POLICY_ALLOW_UN PROTECTED_SAVE` 」オプションは、すべてのドキュメントを保護するように強制することなく、ユーザーに促す場合に便利です。また、このオプションは、ユーザーがネットワークから切断されているときにユーザーがドキュメントを作成したということを知ることができるので便利です。ユーザーがドキュメントを作成し保存することを禁止しません。

1. 変更したファイルを、元の MSI ファイルが格納されているのと同じディレクトリに保存します。

   >[!NOTE]
   >
   >一般的には、元の MSI ファイルと同じファイル名を使用します（例：`DocumentSecurityExtensionforMicrosoftOffice.msi`）。

## 新しいドキュメントの自動保護を有効にする{#enabling-automatic-protection-of-new-documents}

管理者は、ユーザーが保存したドキュメントを自動的に保護する機能を有効にできます。 ドキュメントセキュリティ拡張機能（Microsoft Office用）のインストールプログラムに、自動適用ポリシー機能を構成します。

「ポリシーの自動適用」を有効にすると、ユーザーが保存したすべてのドキュメントがデフォルトのポリシーで保護されます。 この操作は次のような状況で実行します。

* ユーザが新しいドキュメントを作成すると、編集して保存します。
* ユーザーが未保護のドキュメントを開いたとき、編集して保存します。

自動適用ポリシーの設定については、[『デフォルトポリシーの自動適用を設定する』](installing-configuring-aemdsext.md#p-configuring-automatic-application-of-a-default-policy-p)を参照してください。

## リボンを使用しないユーザーインターフェイスを有効にする  {#enable-ribbon-less-user-interface}

リボンを使用しないユーザーインターフェイスは、Windows レジストリの設定を変更することで有効/無効にすることができます。レジストリを更新し、リボンを使用しないユーザーインターフェイスを有効にするには、次の手順を実行します。

1. Windows レジストリを変更する前に、バックアップを作成してください。詳しい手順については、[『Windows レジストリを変更する方法』](https://support.microsoft.com/ja-jp/kb/136393)を参照してください。
1. レジストリエディタで、HKEY_CURRENT_USER\Software\Adobe\LiveCycle Rights Management ES4\11.0.0 or HKEY_LOCAL_MACHINE\Software\Adobe\LiveCycle Rights Management ES4\11.0.0 を開きます。
1. **「HidePluginUI」**&#x200B;という名前で、新しい Dword（32 ビット）値を作成します。

1. リボンを使用しないユーザーインターフェイスを有効にするには、**HidePluginUI **propertyの値を1に設定します。

1. レジストリエディターを終了します。

## Microsoft Excel からの印刷時にウォーターマークを付ける  {#enable-watermark-for-printing-in-microsoft-excel}

Windows のレジストリ設定を変更することで、既存のヘッダーとフッターに動的ウォーターマークを共存させることができます。レジストリ設定では、印刷中にのみウォーターマークが有効になります。レジストリを更新し、ウォーターマークも印刷するには、以下の手順を実行します。

1. Windows レジストリを変更する前に、バックアップを作成してください。詳しい手順については、[『Windows レジストリを変更する方法』](https://support.microsoft.com/en-us/kb/136393)を参照してください。
1. レジストリエディタで、HKEY_CURRENT_USER\Software\Adobe\LiveCycle Rights Management ES4\11.0.0 or HKEY_LOCAL_MACHINE\WOW6432NODE\Software\Adobe\LiveCycle Rights Management ES4\11.0.0 を開きます。
1. 新しいレジストリキー **WatermarkModehors** を作成します。
1. WatermarkModeレジストリキーで、**WatermarkMode** の DWORD を作成し、**WatermarkMode** の DWORD 値を **1** に設定します。

1. レジストリエディターを終了します。

>[!NOTE]
>
>Windows エクスプローラでは、「ファイル」メニューまたはコンテキストメニューから Microsoft Excel 文書を作成できます。静的メソッドで作成された文書の場合、印刷日を検索または変更することはできません。これは Microsoft Excel による制限です。AEM Document Security のウォーターマークは、文書の印刷日付に依存します。したがって、静的メソッドで作成された文書のウォーターマークは前の日付に戻ります。さらに、ヘッダーとフッターも保持されません。

## ドキュメントにカスタム表紙を追加する {#coverpage}

AEM Document Security for Microsoft Office プラグインがインストールされていない PC 上でも、保護されたドキュメントをユーザーが開こうとする可能性があります。このような PC では、文書を開くことができません。そのような PC では、AEM Document Security for Microsoft Office プラグインのダウンロード方法などの情報を含む表紙を表示させることができます。

### 表紙を構成する前に、以下の事柄を実行または確認します。  {#before-you-configure-a-cover-page}

* CommonResources.dll ファイルのバックアップを作成する。デフォルトのパス：

   * **（32 ビット版の Office または 32 ビット版の PC の場合）** C:\Program Files\Adobe\Adobe Experience Manager Forms\Document Security Extension

   * **（32 ビット版の Office または 64 ビット版の PC の場合）** C:\Program Files (x86)\Adobe\Adobe Experience Manager Forms\Document Security Extension

   * **（64 ビット版の Office または 64 ビット版の PC の場合）** C:\Program Files\Adobe\Adobe Experience Manager Forms\Document Security Extension

* Microsoft Visual Studio 2008 以降がインストールされている。他のユーティリティを使用して DLL ファイルを編集することもできます。
* templates.zip アーカイブを解凍します。アーカイブには、表紙の.xlsx、.docx、および .pptx テンプレートが含まれています。.xlsx、.docx、および .pptx のファイル形式には、指定されたテンプレートのみを使用してください。他のファイルタイプ用に独自のテンプレートを作成することもできます。テンプレートをカスタマイズすることで、独自のメッセージや指示を含めることができます。template.zipは次の場所で入手できます。

[ファイルを入手](assets/templates.zip)

### CommonResources.dll ファイルの構成 {#structure-of-the-commonresources-dll-file}

CommonResources.dll ファイルには、リソーステンプレートに関する情報が含まれています。中には、TEMPLATE_FILE と RT_MANIFEST の 2 つの名前識別子が含まれています。カスタム表紙を使用可能にするには、TEMPLATE_FILE の名前識別子を変更します。TEMPLATE_FILE の名前識別子には 6 個のリソースがあります。

<table>
 <tbody>
  <tr>
   <td><p><strong>Resource</strong></p> </td>
   <td><p><strong>対応ファイル </strong></p> </td>
  </tr>
  <tr>
   <td><p>101 </p> </td>
   <td><p>.xls</p> </td>
  </tr>
  <tr>
   <td><p>102</p> </td>
   <td><p>.doc</p> </td>
  </tr>
  <tr>
   <td><p>103 </p> </td>
   <td><p>.ppt</p> </td>
  </tr>
  <tr>
   <td><p>104 </p> </td>
   <td><p>.xlsx</p> </td>
  </tr>
  <tr>
   <td><p>105</p> </td>
   <td><p>.docx</p> </td>
  </tr>
  <tr>
   <td><p>106</p> </td>
   <td><p>.pptx</p> </td>
  </tr>
 </tbody>
</table>

#### テンプレートをカバーページとして構成する  {#configure-the-template-as-a-cover-page}

1. Microsoft Visual Studio を開きます。CommonResources.dll ファイルを参照して開き、編集します。

   >[!NOTE]
   >
   >ファイルが「Solution Explorer」ウィンドウに表示されない場合は、「ファイルを開く」のオプションからファイルを再度開きます。「リソース」エディタをエディタとして選択します。

1. 「Solution Explorer」ウィンドウで、TEMPLATE_FILEディレクトリを展開し、リソース101を削除します。

1. リソースを追加する：

   1. Solution Explorer でプロジェクトを選択し、「プロジェクト」メニューから「プロパティ」をクリックします。
   1. 「リソース」タブを選択します。
   1. 「リソースデザイナー」のツールバーで「リソースの追加」にマウスオーバーし、矢印をクリックします。リソースのタイプに「TEMPLATE_FILE」を選択し、「インポート」をクリックします。
   1. 「既存のファイルをリソースに追加」のダイアログボックスで「Resource.xlsx」ファイルを参照し、「開く」をクリックします。ファイルが「TEMPLATE_FILE」ディレクトリに追加されます。

   >[!NOTE]
   >
   >言語設定が正しいことを確認してください。中立言語のリソースを削除します。

1. すべてのリソースタイプに対して手順 2 と 3 を繰り返します。

   >[!NOTE]
   >
   >リソースタイプを削除・追加する場合は、順番を維持してください。例えば、101 の後には 102 が来る必要があります。

### AEM Document Security extension for Microsoft Office のインストーラに、カスタムCommonResources.dll ファイルをパッケージ化する  {#package-custom-commonresources-dll-file-with-the-installer-of-aem-document-security-extension-for-microsoft-office}

CommonResources.dll ファイルをカスタマイズすることで、カスタムの表紙を追加することができます。ファイルをカスタマイズした後は、すべてのワークステーション上で元のファイルを手動でカスタムファイルに置き換えるか、あるいは自動化された方法でファイルを置き換えることができます。

大規模な環境では、デフォルト `CommonResources.dll file` ファイルをカスタムの`CommonResources.dll` ファイルに手動で置き換えることは困難で大変な作業です。自己解凍パッケージツール（WinZip Self-Extractor など）を使用することで、カスタムの CommonResources.dll ファイルを AEM Document Security Extension for Microsoft Office インストーラにパッケージ化することができます。パッケージ化した後は、カスタムインストーラをすべてのワークステーションに配布することができます。この方法により、デフォルトの `CommonResources.dll` ファイルをカスタムファイルで置き換えるのに必要な時間を短縮できます。また、必要な CommonResources.dll ファイルをすべてのワークステーションに確実に提供する上でも役立ちます。自己解凍型のパッケージングツールは、ファイルを自動的に置き換える多数の方法の1つにすぎません。 お使いの環境に適した任意の方法を選択できます。

AEM Document Security extension for Microsoft Office のインストーラにカスタムの `CommonResources.dll`   ファイルをパッケージ化するには、次の手順を実行します。

1. 自己解凍型のパッケージツールをインストールします。例えば、WinZip Self-Extractor などを使用できます。
1. 新しいフォルダーを作成します。例えば、「YOUR_FOLDER_NAME」の名前を付けます。
1. 新しく作成されたフォルダに、AEM Document Security 拡張機能とカスタムCommonResources.dll ファイルの元のインストーラを配置します。
1. フォルダ内にバッチファイルを作成します。例えば、「YOUR_FOLDER_NAME\Installer.bat」の名前を付けます。
1. 編集用のバッチファイルを開き、次のコードをバッチファイルに追加します。

   ```shell
    @echo off
   
    setlocal EnableDelayedExpansion
   
    msiexec /i YOUR_FOLDER_NAME\MSI_NAME.exe
   
   
    FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\HARDWARE\DESCRIPTION\System\CentralProcessor\0" /v "Identifier"') DO set "IDENTIFIER=%%B"
   
    set IDENTIFIER= %IDENTIFIER: =%
   
    if not %IDENTIFIER:x86=%==%IDENTIFIER% (
   
    REM Fetching install path for 32 bit machine.
   
    FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0" /v "InstallPath"') DO set "INSTALLPATH=%%B"
   
    ) else (
   
        REM Fetching install path for 64 bit machine.
   
            FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\SOFTWARE\Wow6432Node\Adobe\LiveCycle Rights Management ES4\11.0.0" /v "InstallPath"') DO set "INSTALLPATH=%%B"
   
        )
   
    COPY "YOUR_FOLDER_NAME\CommonResources.dll" "%INSTALLPATH%"
   
    endlocal
   ```

   JEE 上で LiveCycle Rights Management ES4 およびバージョン 11.0.0 以外の LiveCycle または AEM Forms を使用している場合は、レジストリキーのパスを次のように置き換えます。

   * (LivecycleRights ManagementES2およびバージョン9.0):*HKLM\SOFTWARE\Adobe/LiveCycle* *Rights ManagementES2\9.0 *
   * （Livecycle Rights Management ES3 およびバージョン 10.0 の場合）
   * （Livecycle Rights Management ES4 およびバージョン 11.0 の場合） HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0
   * （AEM 6.0 Forms on JEE 以降の場合）HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0

1. 上記のコードでは、YOUR_FOLDER_NAME のインスタンスすべてを、手順 2 で作成したフォルダ名に置き換えます。
1. **（「.exe」の拡張子を持つ、AEM Document Security extension for Microsoft Office のインストーラーのみ）** 次のコード行：

   `msiexec /i YOUR_FOLDER_NAME\MSI_NAME.msi`を次のタグに置換します。

   `START /w YOUR_FOLDER_NAME\APPLICATION_NAME.exe`

1. バッチファイルを保存して閉じます。
1. 自己解凍型のパッケージ作成ツールを使用して、カスタムのCommonResources.dllファイル、AEM Security extension for Microsoft Officeの元のインストーラ、およびバッチファイルを含むドキュメントをパッケージ化します。

   >[!NOTE]
   >
   >自己解凍パッケージが管理者として実行され、自動的に実行されるように設定されていることを確認します。
   >抽出の完了時にバッチファイルを実行します。

これで、カスタムの CommonResources.dll ファイルを含む AEM Document Security extension for Microsoft Office パッケージの自己解凍インストーラが完成し、配布準備が整いました。
