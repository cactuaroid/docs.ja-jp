---
title: "LINQ to SQL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5f39db9e-0e62-42c9-8c98-bb8b54cec98c
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# LINQ to SQL
このサンプルでは、SQL Server データベース内のテーブルの LINQ to SQL クエリ エンティティを使用するアクティビティを作成する方法を示します。  
  
> [!IMPORTANT]
>  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] サンプルは、既にコンピューターにインストールされている場合があります。続行する前に、次の \(既定の\) ディレクトリを確認してください。  
>   
>  `<InstallDrive>:\Samples\WCFWFCardspace`  
>   
>  このディレクトリが存在しない場合は、このページの上部にあるサンプルのダウンロードのリンクをクリックします。このリンクをクリックすると、[!INCLUDE[wf1](../../../../includes/wf1-md.md)]、[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]、および [!INCLUDE[infocard](../../../../includes/infocard-md.md)] のサンプルがすべてダウンロードおよびインストールされます。このサンプルは、次のディレクトリに格納されます。  
>   
>  `<InstallDrive>:\Samples\WCFWFCardSpace\WF\Scenario\ActivityLibrary\Linq\LinqToSql`  
  
## FindInSqlTable のアクティビティの詳細  
 このアクティビティでは、LINQ to SQL を使用してデータベース内のテーブルのエンティティに対してクエリを実行できます。アクティビティのユーザーは、LINQ 述語をラムダ式のフォームで指定して、結果をフィルター処理することもできます。述語を指定しない場合、テーブル全体が返されます。次の表で、アクティビティのプロパティと戻り値について詳しく説明します。  
  
|プロパティ値または戻り値|説明|  
|------------------|--------|  
|`Collection` プロパティ|ソース コレクションを指定する必須のプロパティ|  
|`Predicate` プロパティ|コレクションのフィルターをラムダ式のフォームで指定する必須のプロパティ|  
|戻り値|フィルター処理されたコレクション|  
  
## カスタム アクティビティを使用するコード サンプル  
 `FindInSqlTable` カスタム アクティビティを使用して、`Employee` という名前の SQL Server テーブルで `Role` 列が `SDE` になっている行をすべて検索するコード例を次に示します。  
  
```csharp  
  
new FindInSqlTable<Employee>   
{  
    ConnectionString = @"Data Source=.\SQLExpress;Initial Catalog=LinqToSqlSample;Integrated Security=True",                          
    Predicate = new LambdaValue<Func<Employee, bool>>(c => new Func<Employee, bool>(emp => emp.Role.Equals("SDE"))),  
    Result = new OutArgument<IList<Employee>>(employees)  
},  
  
```  
  
#### このサンプルを使用するには  
  
1.  コマンド プロンプトを開きます。  
  
2.  このサンプルが含まれるフォルダーに移動します。  
  
3.  Setup.cmd コマンド ファイルを実行します。  
  
    > [!NOTE]
    >  Setup.cmd スクリプトは、ローカル コンピューターに SQL Server Express のサンプル データベースをインストールしようとします。他の SQL Server インスタンスにインストールする場合は、Setup.cmd を編集します。  
  
     Setup.cmd スクリプトでは、次の操作を実行します。  
  
    -   LinqToSqlSample という名前のデータベースを作成します。  
  
    -   Roles テーブルを作成します。  
  
    -   Employees テーブルを作成します。  
  
    -   3 個のレコードを Roles テーブルに挿入します。  
  
    -   12 個のレコードを Employees テーブルに挿入します。  
  
4.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] を使用して、LinqToSQL.sln ソリューション ファイルを開きます。  
  
5.  ソリューションをビルドするには、Ctrl キーと Shift キーを押しながら B キーを押します。  
  
6.  ソリューションを実行するには、F5 キーを押します。  
  
#### LinqToSql サンプル データベースをアンインストールするには  
  
1.  コマンド プロンプトを開きます。  
  
2.  このサンプルが含まれるフォルダーに移動します。  
  
3.  Cleanup.cmd コマンド ファイルを実行します。  
  
> [!IMPORTANT]
>  サンプルは、既にコンピューターにインストールされている場合があります。続行する前に、次の \(既定の\) ディレクトリを確認してください。  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  このディレクトリが存在しない場合は、「[.NET Framework 4 向けの Windows Communication Foundation \(WCF\) および Windows Workflow Foundation \(WF\) のサンプル](http://go.microsoft.com/fwlink/?LinkId=150780)」にアクセスして、[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] および [!INCLUDE[wf1](../../../../includes/wf1-md.md)] のサンプルをすべてダウンロードしてください。このサンプルは、次のディレクトリに格納されます。  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Liiinq\LinqToSql`  
  
## 参照  
 [LINQ to SQL](http://go.microsoft.com/fwlink/?LinkId=150376)   
 [概要 \(LINQ to SQL\)](http://go.microsoft.com/fwlink/?LinkId=150377)