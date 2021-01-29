---
title: AEM Document Security Extension for Microsoft Office のトラブルシューティング
description: AEM Document Security Extension for Microsoft Office のインストール、設定、または使用に問題がある場合は、この記事に記載されている手順に従ってください。
uuid: 61001ca8-a25a-4879-98ac-563a6eb126e7
contentOwner: khsingh
content-type: reference
topic-tags: using
discoiquuid: bdc3f174-e417-4d3e-b3af-972cdcc10133
translation-type: tm+mt
source-git-commit: ac26ec61f62d7a3db2429c8a9d3f68b82ba8f77a
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 85%

---


# AEM Document Security Extension for Microsoft Office のトラブルシューティング{#troubleshooting-aem-document-security-extension-for-microsoft-office}

## インストールと設定に関する問題のトラブルシューティング {#troubleshootinginstallationandconfiguration}

AEM Document Security Extension for Microsoft Office をインストールまたは設定する際に問題が発生した場合は、[『インストール』](installing-configuring-aemdsext.md)記事を開き、「インストールの前に」のセクションに記載されている手順に注意深く従ってください。

インストールおよび設定をすべてドキュメントどおりに行っている場合は、以降のセクションを参照して、発生している問題に類似の問題があるか確認してください。

### Document Security Extension for Microsoft Office が起動に失敗する  {#document-security-extension-fails-to-load-for-microsoft-office-applications}

Windows レジストリの LoadBehavior プロパティは、ドキュメントセキュリティプラグイン実行時の動作を指定します。LoadBehavior プロパティを 3 に設定すると、すべてのプラグインが自動的に読み込まれます。ドキュメントセキュリティ拡張機能(Microsoft Office)をインストールする前に、LoadBehaviorプロパティの値が3に設定されていることを確認してください。

1. Windows レジストリを変更する前に、バックアップを作成してください。詳しい手順については、[『Windows レジストリを変更する方法』](https://support.microsoft.com/ja-jp/kb/136393)を参照してください。
1. レジストリエディタで、toHKEY_CURRENT_USER\Software\Microsoft\Office\Word\Addins\Adobe.DRMIntegration.WordAddinまたはHKEY_LOCAL_MACHINE\Software\Microsoft\Office\Word\Addins\Adobe.DRMに移動します。
1. **LoadBehavior** のプロパティ値を 3 に設定します。

1. レジストリエディターを終了します。

LoadBehavior の詳細については、[『VSTO アドインのレジストリエントリ』](https://msdn.microsoft.com/en-us/library/bb386106.aspx#LoadBehavior)を参照してください。

## 管理タスクのトラブルシューティング  {#admintasks}

このセクションでは、インストールされている AEM Document Security Extension で発生し得る問題について説明します。

### Document Security Extension をインストールした後、Microsoft Office アプリケーションがスムーズに起動しなくなった  {#microsoft-office-applications-dont-start-smoothly-on-installing-document-security-extension}

Document Security Extension がインストールされ、McAfee VirusScan の On-Access Scan 機能が有効なコンピュータで Office アプリケーションをスムーズに起動するには、McAfee VirusScan Console の「Buffer Overflow Protection」オプションを無効にしてください。
