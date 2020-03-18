---
title: Come effettuare più richieste Web in parallelo utilizzando async e await (C
ms.date: 07/20/2015
ms.assetid: 19745899-f97a-4499-a7c7-e813d1447580
ms.openlocfilehash: 9f7420113d4af83d7d057b772af307bd8d4bcc00
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79169949"
---
# <a name="how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await-c"></a>Come effettuare più richieste Web in parallelo utilizzando async e await (C
In un metodo asincrono le attività vengono avviate al momento della creazione. L'operatore [await](../../../language-reference/operators/await.md) viene applicato all'attività in un punto del metodo in cui è impossibile continuare l'elaborazione finché l'attività non è terminata. Spesso un'attività viene messa in attesa al momento della creazione, come illustrato nell'esempio seguente.  
  
```csharp  
var result = await someWebAccessMethodAsync(url);  
```  
  
 Tuttavia, è possibile separare la creazione dalla messa in attesa dell'attività se il programma ha altro lavoro da eseguire che non dipende dal completamento dell'attività.  
  
```csharp  
// The following line creates and starts the task.  
var myTask = someWebAccessMethodAsync(url);  
  
// While the task is running, you can do other work that doesn't depend  
// on the results of the task.  
// . . . . .  
  
// The application of await suspends the rest of this method until the task is complete.  
var result = await myTask;  
```  
  
 Tra l'avvio di un'attività e la messa in attesa, è possibile avviare altre attività. Le attività aggiuntive vengono eseguite in modo implicito in parallelo, ma non vengono creati thread aggiuntivi.  
  
 Il programma seguente avvia tre download Web asincroni e quindi li mette in attesa nell'ordine in cui vengono chiamati. Si noti che, quando si esegue il programma, non sempre le attività finiscono nell'ordine in cui sono state create e messe in attesa. Vengono avviate al momento della creazione ed è possibile che una o più di una finiscano prima che il metodo raggiunga le espressioni await.  
  
> [!NOTE]
> Per completare il progetto, è necessario che nel computer siano installati Visual Studio 2012 o versioni successive e .NET Framework 4.5 o versioni successive.  
  
 Per un altro esempio in cui vengono avviate più attività contemporaneamente, vedere [Come estendere la procedura dettagliata asincrona utilizzando Task.WhenAll (C )](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md).
  
 È possibile scaricare il codice per l'esempio da [Developer Code Samples](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e) (Esempi di codice per sviluppatori).  
  
### <a name="to-set-up-the-project"></a>Per impostare il progetto  
  
1. Per configurare un'applicazione WPF, completare i passaggi seguenti. È possibile trovare istruzioni dettagliate per i passaggi in [Procedura dettagliata: Accesso al Web tramite async e await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md).  
  
    - Creare un'applicazione WPF che contenga una casella di testo e un pulsante. Denominare il pulsante `startButton` e la casella di testo `resultsTextBox`.  
  
    - Aggiunge un riferimento a <xref:System.Net.Http>.  
  
    - Nel file MainWindow.xaml.cs aggiungere una direttiva `using` per `System.Net.Http`.  
  
### <a name="to-add-the-code"></a>Per aggiungere il codice  
  
1. Nella finestra di progettazione MainWindow.xaml fare doppio clic sul pulsante per creare il gestore eventi `startButton_Click` in MainWindow.xaml.cs.  
  
2. Copiare il codice seguente e incollarlo nel corpo di `startButton_Click` in MainWindow.xaml.cs.  
  
    ```csharp  
    resultsTextBox.Clear();  
    await CreateMultipleTasksAsync();  
    resultsTextBox.Text += "\r\n\r\nControl returned to startButton_Click.\r\n";  
    ```  
  
     Il codice chiama un metodo asincrono, `CreateMultipleTasksAsync`, che avvia l'applicazione.  
  
3. Aggiungere i metodi di supporto seguenti al progetto:  
  
    - `ProcessURLAsync` usa un metodo <xref:System.Net.Http.HttpClient> per scaricare il contenuto di un sito Web come matrice di byte. Il metodo di supporto `ProcessURLAsync` visualizza e restituisce la lunghezza della matrice.  
  
    - `DisplayResults` visualizza il numero di byte della matrice di byte per ogni URL. Questa visualizzazione indica quando ogni attività ha terminato il download.  
  
     Copiare i metodi seguenti e incollarli dopo il gestore eventi `startButton_Click` in MainWindow.xaml.cs.  
  
    ```csharp  
    async Task<int> ProcessURLAsync(string url, HttpClient client)  
    {  
        var byteArray = await client.GetByteArrayAsync(url);  
        DisplayResults(url, byteArray);  
        return byteArray.Length;  
    }  
  
    private void DisplayResults(string url, byte[] content)  
    {  
        // Display the length of each website. The string format
        // is designed to be used with a monospaced font, such as  
        // Lucida Console or Global Monospace.  
        var bytes = content.Length;  
        // Strip off the "https://".  
        var displayURL = url.Replace("https://", "");  
        resultsTextBox.Text += $"\n{displayURL,-58} {bytes,8}";
    }  
    ```  
  
4. Infine, definire il metodo `CreateMultipleTasksAsync`, che esegue i passaggi seguenti.  
  
    - Il metodo dichiara un oggetto `HttpClient`, che è necessario per accedere al metodo <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> in `ProcessURLAsync`.  
  
    - Il metodo crea e avvia tre attività di tipo <xref:System.Threading.Tasks.Task%601>, dove `TResult` è un numero intero. Al termine di ogni attività, `DisplayResults` vengono visualizzati l'URL dell'attività e la lunghezza del contenuto scaricato. Poiché le attività sono in esecuzione in modo asincrono, l'ordine in cui vengono visualizzati i risultati potrebbe essere diverso da quello in cui le attività sono stati dichiarate.  
  
    - Il metodo attende il completamento di ogni attività. Ogni operatore `await` sospende l'esecuzione di `CreateMultipleTasksAsync` finché non viene completata l'attività in attesa. L'operatore recupera anche il valore restituito dalla chiamata a `ProcessURLAsync` da ogni attività completata.  
  
    - Quando sono state completate le attività e sono stati recuperati i valori interi, il metodo somma le lunghezze dei siti Web e visualizza il risultato.  
  
     Copiare il metodo seguente e incollarlo nella soluzione.  
  
    ```csharp  
    private async Task CreateMultipleTasksAsync()  
    {  
        // Declare an HttpClient object, and increase the buffer size. The  
        // default buffer size is 65,536.  
        HttpClient client =  
            new HttpClient() { MaxResponseContentBufferSize = 1000000 };  
  
        // Create and start the tasks. As each task finishes, DisplayResults
        // displays its length.  
        Task<int> download1 =
            ProcessURLAsync("https://msdn.microsoft.com", client);  
        Task<int> download2 =
            ProcessURLAsync("https://msdn.microsoft.com/library/hh156528(VS.110).aspx", client);  
        Task<int> download3 =
            ProcessURLAsync("https://msdn.microsoft.com/library/67w7t67f.aspx", client);  
  
        // Await each task.  
        int length1 = await download1;  
        int length2 = await download2;  
        int length3 = await download3;  
  
        int total = length1 + length2 + length3;  
  
        // Display the total count for the downloaded websites.  
        resultsTextBox.Text += $"\r\n\r\nTotal bytes returned:  {total}\r\n";
    }  
    ```  
  
5. Premere F5 per eseguire il programma e quindi scegliere il pulsante **Avvia**.  
  
     Eseguire il programma più volte per verificare che le tre attività non vengano completate sempre nello stesso ordine e che l'ordine in cui vengono completate non è necessariamente l'ordine in cui sono state create e messe in attesa.  
  
## <a name="example"></a>Esempio  
 Il codice seguente contiene l'esempio completo.  
  
```csharp  
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
  
// Add the following using directive, and add a reference for System.Net.Http.  
using System.Net.Http;  
  
namespace AsyncExample_MultipleTasks  
{  
    public partial class MainWindow : Window  
    {  
        public MainWindow()  
        {  
            InitializeComponent();  
        }  
  
        private async void startButton_Click(object sender, RoutedEventArgs e)  
        {  
            resultsTextBox.Clear();  
            await CreateMultipleTasksAsync();  
            resultsTextBox.Text += "\r\n\r\nControl returned to startButton_Click.\r\n";  
        }  
  
        private async Task CreateMultipleTasksAsync()  
        {  
            // Declare an HttpClient object, and increase the buffer size. The  
            // default buffer size is 65,536.  
            HttpClient client =  
                new HttpClient() { MaxResponseContentBufferSize = 1000000 };  
  
            // Create and start the tasks. As each task finishes, DisplayResults
            // displays its length.  
            Task<int> download1 =
                ProcessURLAsync("https://msdn.microsoft.com", client);  
            Task<int> download2 =
                ProcessURLAsync("https://msdn.microsoft.com/library/hh156528(VS.110).aspx", client);  
            Task<int> download3 =
                ProcessURLAsync("https://msdn.microsoft.com/library/67w7t67f.aspx", client);  
  
            // Await each task.  
            int length1 = await download1;  
            int length2 = await download2;  
            int length3 = await download3;  
  
            int total = length1 + length2 + length3;  
  
            // Display the total count for the downloaded websites.  
            resultsTextBox.Text += $"\r\n\r\nTotal bytes returned:  {total}\r\n";
        }  
  
        async Task<int> ProcessURLAsync(string url, HttpClient client)  
        {  
            var byteArray = await client.GetByteArrayAsync(url);  
            DisplayResults(url, byteArray);  
            return byteArray.Length;  
        }  
  
        private void DisplayResults(string url, byte[] content)  
        {  
            // Display the length of each website. The string format
            // is designed to be used with a monospaced font, such as  
            // Lucida Console or Global Monospace.  
            var bytes = content.Length;  
            // Strip off the "https://".  
            var displayURL = url.Replace("https://", "");  
            resultsTextBox.Text += $"\n{displayURL,-58} {bytes,8}";
        }
    }  
}  
```  
  
## <a name="see-also"></a>Vedere anche

- [Procedura dettagliata: accesso al Web tramite async e await (C#)](./walkthrough-accessing-the-web-by-using-async-and-await.md)
- [Programmazione asincrona con async e await (C#)](./index.md)
- [Come estendere la procedura dettagliata asincrona utilizzando Task.WhenAll (C )How to extend the async walkthrough by using Task.WhenAll (C](./how-to-extend-the-async-walkthrough-by-using-task-whenall.md)
