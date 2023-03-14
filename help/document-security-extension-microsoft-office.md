---
title: Microsoft&reg；用AEM Document Security Extension の概要オフィス
description: Microsoft&reg；での Document Security Extension の使用Office では、事前定義された機密設定をMicrosoft&reg に適用できます。Office ファイル。
uuid: a5428c50-fae3-4823-9e6f-0f5306e7248f
content-type: reference
topic-tags: using
discoiquuid: cf93f9f5-1fb6-4909-815e-0ffb8c6ea6d1
exl-id: 3e07c031-3f88-4bde-bdb3-b136ef5f9527
source-git-commit: f3456fa7243405a4986ac50540f8b578a6412a6c
workflow-type: tm+mt
source-wordcount: '1313'
ht-degree: 67%

---

# Microsoft® Office 用AEM Document Security Extension の概要{#introduction-to-aem-document-security-extension-for-microsoft-office}

Adobe® Experience Manager Document Security Extension for Microsoft® Office を使用すると、知的財産を含む Word、Excel、および PowerPoint ファイルを、許可したユーザーのみが使用できるようにすることができます。Microsoft® Office 用 Document Security Extension を使用すると、事前に定義された機密設定をファイルに適用できます。

Microsoft® Office 用 Document Security Extension は、Adobe Experience Manager FormsのLiveCycleRights Managementと Document Security アドオンを拡張して Word、Excel、PowerPoint ファイルを保護し、このソフトウェアをインストールした承認済みユーザーがポリシーで定義された機密設定に従ってポリシーで保護されたファイルを使用できるようにします。

## Document Security による知的財産の保護の仕組み {#how-document-security-protects-intellectual-property}

Document Security は、認証したユーザーのみが知的財産を含むファイルを使用できるようにします。 Document Security を利用すると、機密ポリシーを使用してファイルを保護できます。*ポリシー*&#x200B;は、機密設定および許可されたユーザーの一覧を含む情報の集合です。ポリシーを適用したファイルを受信者がどのように使用できるかは、ポリシーで指定した設定で決まります。例えば、受信者がテキストの印刷やコピー、変更内容の保存を行えるかどうかを指定できます。

ポリシーを作成するのは Document Security 管理者およびユーザーです。管理者は、許可されたすべてのユーザーが使用できる組織ポリシーを作成します。管理者またはポリシー設定コーディネータは、ユーザーのサブセットで使用できる&#x200B;*ポリシーセット*&#x200B;と呼ばれるポリシーグループを作成することもできます。ユーザーは自分だけが使える独自のポリシーを作成できます。管理者、ポリシー設定コーディネータ、ユーザーは、Document Security Web ページを使用してポリシーを作成します。

ポリシーは Document Security に保存されますが、Word、Excel、PowerPoint のいずれかを使用してファイルに適用します。ファイルにポリシーを適用すると、そのファイルに含まれている情報が、ポリシーで指定された機密設定により保護されます。ポリシーで保護されたファイルを配布すると、そのポリシーで許可された受信者のみがファイルのコンテンツにアクセスできます。

ポリシーを使用してファイルを保護すると、配布後もファイルを継続的に管理できます。イベントを監査して、受信者がいつどのようにファイルを使用しているかを追跡したり、ポリシーに変更を加えたり、ユーザーがファイルにそれ以上アクセスできないようにしたり、ファイルに関連付けられているポリシーを変更したりできます。

## ポリシーの使用 {#how-policies-work}

ポリシーは、許可されたユーザーおよび知的財産に適用される機密設定に関する情報で構成されます。リンクされた LDAP または Active Directory リストに含まれることで Document Security に認識される人であれば誰でもユーザーになれます。また、Document Security への登録を招待された人や、管理者がアカウントを作成した人もユーザーになれます。

ポリシーで保護されたファイルを受信者がどのように使用できるかは、ポリシーの機密設定で決まります。ポリシーでは、例えば、受信者がファイルを印刷したり、内容を他のファイルにコピーしたり、保護されたファイルに変更内容を保存したりできるかどうかを指定します。また、様々なユーザーに応じて異なる機密設定を指定することもできます。

ファイルにポリシーを適用すると、そのファイルに含まれている情報が、ポリシーで指定された機密設定により保護されます。ファイルを配布すると、それを開こうとする受信者の認証が Document Security によっておこなわれ、ポリシーで指定されている権限に従って受信者にアクセスが許可されます。

ファイルにポリシーを適用した後は、ポリシーの機密設定をいつでも変更できます。 これにより、認証済みユーザーを追加または削除したり、ファイルを受け取った後にそのユーザーの権限を変更したりできます。 ファイルに適用されたポリシーを変更でき、ファイルへのアクセスを取り消して、ファイルのコピーを持っているすべてのユーザーがファイルを開けなくすることができます。

オフラインアクセスがポリシーで許可されている場合、受信者は、ポリシーで保護されたファイルを、ポリシーで指定された期間、オフライン（アクティブなインターネット接続やネットワーク接続がない状態）で使用することもできます。

## ポリシーで保護されたファイルの使用 {#how-policy-protected-files-work}

ポリシーで保護された Word、Excel、PowerPoint の各ファイルをユーザーが開いて使用するには、そのユーザーを受信者として含めるか、匿名アクセスを許可する必要があります。また、Document Security Extension for Microsoft® Office がインストールされている必要があります。 Microsoft® Office 用の Document Security Extension を持たないユーザーにポリシーで保護されたファイルを渡すには、ソフトウェアのコピーを渡すか、Web サイトからのダウンロード方法を伝えます。 インストーラーがない場合は、[ダウンロードページ](https://experienceleague.adobe.com/docs/experience-manager-document-security/using/download-installer.html?lang=en)からダウンロードできます。

ユーザーがポリシーで保護されたファイルを開こうとすると、Document Security Extension for Microsoft® Office が Document Security に接続し、ユーザーを認証します。 ファイルの使用状況を監査するように Document Security が設定されている場合は、ファイルの使用状況が監査中であることを示す通知が表示されます。ユーザーに付与されるファイル権限は Document Security によって決定され、ユーザーは、次の条件の下でポリシー設定に従ってファイルを使用できます。

* ポリシーで指定された有効期間内。
* 管理者またはポリシーの適用者がファイルへのアクセスを無効にするか、ポリシーを変更するまで。

   ポリシーを適用したユーザーがポリシーを変更したり、ファイルへのアクセスを無効にした場合、ユーザーが既にファイルを持っているにもかかわらず、ファイルに対するユーザーの権限が変更または削除されます。 ファイル自体が無効になった場合は、最新のコピーを取得するための URL をユーザーに提供できます。

   ポリシーで保護されたファイルは、ポリシーで指定されたオフラインリース期間中に、ポリシーがオフラインアクセスを許可している場合は、オフラインで開くことができます（インターネットやネットワークに接続していない場合）。 オフラインリース期間が終了したら、ユーザーはオンラインにして、Document Security と同期する必要があります。その結果、新しいリース期間が始まります。

   ファイルの保存がポリシーで許可されていて、ポリシーで保護されたファイルのコピーをユーザーが保存した場合は、保存されたファイルにポリシーが自動的に適用されされます。新しいファイルを開こうとするといったイベントも、元のファイルの場合と同じように、監査され記録されます。

## Document Security を使用したファイルの保護 {#using-document-security-to-protect-your-files}

ポリシーを使用すると、様々な状況でファイルを保護できます。

例えば、あるメーカーは、新しい製品の部品を提供するベンダーからの入札を受け付けています。 メーカーは、入札者に提出を最終決定する独自の情報を提供する必要があります。 メーカーは、Document Security を使用して、入札者がファイルを開いて情報を閲覧できるように指定したポリシーでファイルを保護します。ただし、入札者はファイルの変更、印刷、コピーをおこなうことはできず、権限を持たないユーザーはファイルを開くことができません。

いずれかの入札を受諾したら、メーカーはポリシーを更新して、入札に成功したベンダーにはファイルの印刷やコピーおよび変更内容のローカル保存の権限を与えます。一方、入札に失敗したベンダーを削除して、ファイルを開く権限を取り消します。

入札者との作業中に、製造元のエンジニアがファイル内の設計仕様の一部を変更します。 新しい仕様を公開するために、メーカーは一部のファイルへのアクセスを無効にして、新しいバージョンを公開します。入札に成功したベンダーのエンジニアがこのファイルを開こうとすると、ファイルへのアクセスが無効になったというメッセージが表示されます。このメッセージには URL が含まれており、エンジニアはそこからファイルの新しいバージョンをダウンロードできます。

## 追加情報 {#additional-information}

次の表に、AEM Document Security の参考情報を記載します。

<table >
 <tbody>
  <tr>
   <th><p>情報</p> </th>
   <th><p>参照先</p> </th>
  </tr>
  <tr>
   <td><p>AEM Forms 管理者ヘルプ</p> </td>
   <td><p><a href="https://experienceleague.adobe.com/docs/experience-manager-65/forms/administrator-help/get-started/configure-general-aem-forms-settings.html?lang=en">管理ヘルプ</a>または Document Security 管理ページで、ページの右上にある「ヘルプ」リンクをクリックしてください。</p> </td>
  </tr>
  <tr>
   <td><p>現在のバージョンに関するパッチアップデート、テクニカルノート、および追加情報</p> </td>
   <td><p><a href="https://experienceleague.adobe.com/?support-solution=General&amp;support-tab=home#support">Experience Cloudテクニカルサポート</a></p> </td>
  </tr>
 </tbody>
</table>
