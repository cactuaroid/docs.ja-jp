---
title: LINQ メッセージ クエリの関連付け
ms.date: 03/30/2017
ms.assetid: b746872e-57b1-4514-b337-53398a0e0deb
ms.openlocfilehash: 5b215764f7e02f07873f63872f4ac8c3fcaffbcc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515849"
---
# <a name="linq-message-query-correlation"></a>LINQ メッセージ クエリの関連付け
このサンプルでは、システム標準の <xref:System.ServiceModel.Dispatcher.MessageQuery> ではなく、カスタムの <xref:System.ServiceModel.XPathMessageQuery> 実装を使用して、コンテンツ ベースの関連付けを実行する方法を示します。  
  
## <a name="demonstrates"></a>使用例  
 カスタムの <xref:System.ServiceModel.Dispatcher.MessageQuery>、コンテンツ ベースの相関関係。  
  
## <a name="discussion"></a>説明  
 このサンプルでは、関連付けのために <xref:System.ServiceModel.Dispatcher.MessageQuery> 基本クラスから拡張する方法を示します。 カスタム実装の `LinqMessageQuery` を使用すると、XLinq を使用してメッセージ内で検索する XName を指定できます。 クエリによって取得されたデータを使用して、メッセージを適切なワークフロー インスタンスにディスパッチするための相関関係キーを作成します。  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>サンプルをセットアップ、ビルド、および実行するには  
  
1.  このサンプルでは、HTTP エンドポイントを使用してワークフロー サービスを公開します。 このサンプルを適切な URL Acl を実行するを追加する必要があります (を参照してください[を構成する HTTP および HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353)詳細については)、管理者として Visual Studio を実行しているか、適切な Acl を追加する管理者特権のプロンプトで次のコマンドを実行することによってです。 ドメインとユーザー名は置き換えてください。  
  
    ```  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2.  URL ACL を追加したら、次の手順を実行します。  
  
    1.  ソリューションをビルドします。  
  
    2.  複数のスタートアップ プロジェクトを設定するには、ソリューションを右クリックしを選択すると**スタートアップ プロジェクトの**します。 追加**サービス**と**クライアント**(その順序で) 複数のスタートアップ プロジェクトとして。  
  
    3.  アプリケーションを実行します。 クライアント コンソールには、注文を送信し、発注書 ID を受信した後に、注文を確認するワークフローが示されます。 Service のウィンドウには、処理されている要求が示されます。  
  
> [!IMPORTANT]
>  サンプルは、既にコンピューターにインストールされている場合があります。 続行する前に、次の (既定の) ディレクトリを確認してください。  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  このディレクトリが存在しない場合に、 [Windows Communication Foundation (WCF) および .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](http://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプルです。 このサンプルは、次のディレクトリに格納されます。  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\LinqMessageQueryCorrelation`
