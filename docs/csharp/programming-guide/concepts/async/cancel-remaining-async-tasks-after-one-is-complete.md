---
title: "完了後の残りの非同期タスクのキャンセル | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: d3cebc74-c392-497b-b1e6-62a262eabe05
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3434dc4b13295101970fd4aadb69d56ddbca7142
ms.lasthandoff: 03/13/2017

---
# <a name="cancel-remaining-async-tasks-after-one-is-complete-c"></a>完了後の残りの非同期タスクのキャンセル (C#)
<xref:System.Threading.CancellationToken> とともに <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=fullName> メソッドを使用すると、1 つのタスクが完了したあと、残りのすべてのタスクをキャンセルすることができます。 `WhenAny` メソッドは、タスクのコレクションである引数を受け取ります。 このメソッドは、すべてのタスクを開始し、単一のタスクを返します。 単一のタスクは、コレクションのいずれかのタスクが完了すると完了します。  
  
 この例では、キャンセル トークンを `WhenAny` と共に使用して、タスクのコレクションから最初のタスクを終了まで保持し、残りのタスクを取り消す方法を示しています。 各タスクは、Web サイトのコンテンツをダウンロードします。 この例は最初のダウンロードが完了したコンテンツの長さを表示し、他のダウンロードを取り消します。  
  
> [!NOTE]
>  この例を実行するには、コンピューターに Visual Studio 2012 以降および .NET Framework 4.5 以降がインストールされている必要があります。  
  
## <a name="downloading-the-example"></a>例をダウンロードする  
 完全な Windows Presentation Foundation (WPF) プロジェクトは「[非同期のサンプル: アプリケーションの微調整](http://go.microsoft.com/fwlink/?LinkId=255046)」からダウンロードできます。ダウンロード後、次の手順に従います。  
  
1.  ダウンロードしたファイルを圧縮解除し、Visual Studio を起動します。  
  
2.  メニュー バーで **[ファイル]**、 **[開く]**、 **[プロジェクト/ソリューション]**の順に選択します。  
  
3.  **[プロジェクトを開く]** ダイアログ ボックスで、圧縮解除したサンプル コードを含むフォルダーを開き、AsyncFineTuningCS のソリューション (.sln) ファイルを開きます。  
  
4.  **ソリューション エクスプローラー**で、**CancelAfterOneTask** プロジェクトのショートカット メニューを開き、**[スタートアップ プロジェクトに設定]** をクリックします。  
  
5.  F5 キーを押してプロジェクトを実行します。  
  
     Ctrl + F5 キーを押して、デバッグを行わずにプロジェクトを実行します。  
  
6.  プログラムを複数回実行し、最初に終了するダウンロードが異なることを確認します。  
  
 プロジェクトをダウンロードしない場合は、このトピックの最後の MainWindow.xaml.cs ファイルをレビューできます。  
  
## <a name="building-the-example"></a>例のビルド  
 このトピックの例では、「[非同期タスクまたはタスクの一覧のキャンセル (C#)](../../../../csharp/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md)」で開発したプロジェクトに追加して、タスクのリストをキャンセルします。 この例では、[**キャンセル**] ボタンは明示的に使用していませんが、同じ UI を使用します。  
  
 この例を自分で 1 つずつビルドするには、"例をダウンロードする" セクションの手順に従います。ただし、**[スタートアップ プロジェクト]** として **CancelAListOfTasks** を選択します。 そのプロジェクトに、このトピックでの変更を追加します。  
  
 **CancelAListOfTasks** プロジェクトの MainWindow.xaml.cs ファイルで、各 Web サイトの処理ステップを `AccessTheWebAsync` のループから次の非同期メソッドに移動して、遷移を開始します。  
  
```cs  
/ ***Bundle the processing steps for a website into one async method.  
async Task<int> ProcessURLAsync(string url, HttpClient client, CancellationToken ct)  
{  
    // GetAsync returns a Task<HttpResponseMessage>.   
    HttpResponseMessage response = await client.GetAsync(url, ct);  
  
    // Retrieve the website contents from the HttpResponseMessage.  
    byte[] urlContents = await response.Content.ReadAsByteArrayAsync();  
  
    return urlContents.Length;  
}  
```  
  
 この例では、`AccessTheWebAsync` で <xref:System.Linq.Enumerable.ToArray%2A> メソッドというクエリと `WhenAny` メソッドを使用して、タスクの配列を作成して開始します。 配列への `WhenAny` のアプリケーションは、待機したときに、タスクの配列で完了に到達する最初のタスクを評価する 1 つのタスクを返します。  
  
 `AccessTheWebAsync` で次の変更を行います。 アスタリスクはコード ファイルの変更点を示しています。  
  
1.  ループをコメント アウトするか、削除します。  
  
2.  実行されると、一般的なタスクのコレクションを生成するクエリを作成します。 `ProcessURLAsync` に対する各呼び出しは、`TResult` が整数である <xref:System.Threading.Tasks.Task%601> を返します。  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
3.  `ToArray` を呼び出してクエリを実行し、タスクを開始します。 次の手順で `WhenAny` メソッドのアプリケーションは、`ToArray` を使用せずにクエリを実行してタスクを開始しますが、他のメソッドはそうでない場合があります。 最も安全な方法は、クエリの実行を明示的に強制することです。  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
4.  タスクのコレクションで `WhenAny` を呼び出します。 `WhenAny` は `Task(Of Task(Of Integer))` または `Task<Task<int>>` を返します。  つまり、`WhenAny` は、待機すると、単一の `Task(Of Integer)` または `Task<int>` に評価するタスクを返します。 その単一のタスクが、コレクションで最初に終了するタスクです。 最初に終了したタスクは `firstFinishedTask` に割り当てられます。 `firstFinishedTask` の型は、`TResult` が整数である <xref:System.Threading.Tasks.Task%601> です。それが `ProcessURLAsync` の戻り値の型であるためです。  
  
    ```cs  
    // ***Call WhenAny and then await the result. The task that finishes   
    // first is assigned to firstFinishedTask.  
    Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);  
    ```  
  
5.  この例では、最初に終了したタスクにのみ焦点を当てています。 そのため、残りのタスクをキャンセルするには、<xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName> を使用します。  
  
    ```cs  
    // ***Cancel the rest of the downloads. You just want the first one.  
    cts.Cancel();  
    ```  
  
6.  最後に、`firstFinishedTask` を待機して、ダウンロードされたコンテンツの長さを取得します。  
  
    ```cs  
    var length = await firstFinishedTask;  
    resultsTextBox.Text += String.Format("\r\nLength of the downloaded website:  {0}\r\n", length);  
    ```  
  
 プログラムを複数回実行し、最初に終了するダウンロードが異なることを確認します。  
  
## <a name="complete-example"></a>コード例全体  
 次のコードは、この例で使用した MainWindow.xaml.cs ファイルの全体です。 アスタリスクはこの例のために追加された要素を示しています。  
  
 <xref:System.Net.Http> の参照を追加する必要があることに注意してください。  
  
 このプロジェクトは「[非同期のサンプル: アプリケーションの微調整](http://go.microsoft.com/fwlink/?LinkId=255046)」からダウンロードできます。  
  
```cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Threading.Tasks;  
using System.Windows;  
using System.Windows.Controls;  
using System.Windows.Data;  
using System.Windows.Documents;  
using System.Windows.Input;  
using System.Windows.Media;  
using System.Windows.Media.Imaging;  
using System.Windows.Navigation;  
using System.Windows.Shapes;  
  
// Add a using directive and a reference for System.Net.Http.  
using System.Net.Http;  
  
// Add the following using directive.  
using System.Threading;  
  
namespace CancelAfterOneTask  
{  
    public partial class MainWindow : Window  
    {  
        // Declare a System.Threading.CancellationTokenSource.  
        CancellationTokenSource cts;  
  
        public MainWindow()  
        {  
            InitializeComponent();  
        }  
  
        private async void startButton_Click(object sender, RoutedEventArgs e)  
        {  
            // Instantiate the CancellationTokenSource.  
            cts = new CancellationTokenSource();  
  
            resultsTextBox.Clear();  
  
            try  
            {  
                await AccessTheWebAsync(cts.Token);  
                resultsTextBox.Text += "\r\nDownload complete.";  
            }  
            catch (OperationCanceledException)  
            {  
                resultsTextBox.Text += "\r\nDownload canceled.";  
            }  
            catch (Exception)  
            {  
                resultsTextBox.Text += "\r\nDownload failed.";  
            }  
  
            // Set the CancellationTokenSource to null when the download is complete.  
            cts = null;  
        }  
  
        // You can still include a Cancel button if you want to.  
        private void cancelButton_Click(object sender, RoutedEventArgs e)  
        {  
            if (cts != null)  
            {  
                cts.Cancel();  
            }  
        }  
  
        // Provide a parameter for the CancellationToken.  
        async Task AccessTheWebAsync(CancellationToken ct)  
        {  
            HttpClient client = new HttpClient();  
  
            // Call SetUpURLList to make a list of web addresses.  
            List<string> urlList = SetUpURLList();  
  
            // ***Comment out or delete the loop.  
            //foreach (var url in urlList)  
            //{  
            //    // GetAsync returns a Task<HttpResponseMessage>.   
            //    // Argument ct carries the message if the Cancel button is chosen.   
            //    // ***Note that the Cancel button can cancel all remaining downloads.  
            //    HttpResponseMessage response = await client.GetAsync(url, ct);  
  
            //    // Retrieve the website contents from the HttpResponseMessage.  
            //    byte[] urlContents = await response.Content.ReadAsByteArrayAsync();  
  
            //    resultsTextBox.Text +=  
            //        String.Format("\r\nLength of the downloaded string: {0}.\r\n", urlContents.Length);  
            //}  
  
            // ***Create a query that, when executed, returns a collection of tasks.  
            IEnumerable<Task<int>> downloadTasksQuery =  
                from url in urlList select ProcessURLAsync(url, client, ct);  
  
            // ***Use ToArray to execute the query and start the download tasks.   
            Task<int>[] downloadTasks = downloadTasksQuery.ToArray();  
  
            // ***Call WhenAny and then await the result. The task that finishes   
            // first is assigned to firstFinishedTask.  
            Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);  
  
            // ***Cancel the rest of the downloads. You just want the first one.  
            cts.Cancel();  
  
            // ***Await the first completed task and display the results.   
            // Run the program several times to demonstrate that different  
            // websites can finish first.  
            var length = await firstFinishedTask;  
            resultsTextBox.Text += String.Format("\r\nLength of the downloaded website:  {0}\r\n", length);  
        }  
  
        // ***Bundle the processing steps for a website into one async method.  
        async Task<int> ProcessURLAsync(string url, HttpClient client, CancellationToken ct)  
        {  
            // GetAsync returns a Task<HttpResponseMessage>.   
            HttpResponseMessage response = await client.GetAsync(url, ct);  
  
            // Retrieve the website contents from the HttpResponseMessage.  
            byte[] urlContents = await response.Content.ReadAsByteArrayAsync();  
  
            return urlContents.Length;  
        }  
  
        // Add a method that creates a list of web addresses.  
        private List<string> SetUpURLList()  
        {  
            List<string> urls = new List<string>   
            {   
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            };  
            return urls;  
        }  
    }  
    // Sample output:  
  
    // Length of the downloaded website:  158856  
  
    // Download complete.  
}  
```  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Threading.Tasks.Task.WhenAny%2A>   
 [非同期アプリケーションの微調整 (C#)](../../../../csharp/programming-guide/concepts/async/fine-tuning-your-async-application.md)   
 [async および await を使用した非同期プログラミング (C#)](../../../../csharp/programming-guide/concepts/async/index.md)   
 [非同期のサンプル: アプリケーションの微調整](http://go.microsoft.com/fwlink/?LinkId=255046)