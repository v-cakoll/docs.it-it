---
title: Elaborare le attività asincrone quando vengono completate
ms.date: 09/12/2018
ms.assetid: 25331850-35a7-43b3-ab76-3908e4346b9d
ms.openlocfilehash: 9380be1dc24d7c147c22dbb1a362777f56a32358
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2018
ms.locfileid: "50202042"
---
# <a name="start-multiple-async-tasks-and-process-them-as-they-complete-c"></a>Avviare più attività asincrone ed elaborarle quando vengono completate (C#)

Usando <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>, è possibile avviare più attività contemporaneamente ed elaborarle una ad una quando vengono completate, invece che nell'ordine in cui vengono avviate.

Nell'esempio seguente viene usata una query per creare una Collection di attività. Ogni attività scarica il contenuto di un sito Web specificato. In ogni iterazione di un ciclo while, una chiamata attesa a `WhenAny` restituisce l'attività nella Collection di attività che completa per prima il download. Questa attività viene rimossa dalla Collection ed elaborata. Il ciclo si ripete finché la Collection non contiene più attività.

> [!NOTE]
> Per eseguire gli esempi, è necessario avere installato nel computer Visual Studio 2012 o versioni successive e .NET Framework 4.5 o versioni successive.

## <a name="download-an-example-solution"></a>Scaricare una soluzione di esempio

È possibile scaricare il progetto completo di Windows Presentation Foundation (WPF) da [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: ottimizzazione dell'applicazione) e seguire la procedura seguente.

> [!TIP]
> Se non si vuole scaricare il progetto, è invece possibile esaminare il file MainWindow.xaml.cs alla fine di questo argomento.

1.  Estrarre i file che sono stati scaricati dal file ZIP e quindi avviare Visual Studio.

2.  Nella barra dei menu scegliere **File** > **Apri** > **Progetto/soluzione**.

3.  Nella finestra di dialogo **Apri progetto** aprire la cartella che contiene il codice di esempio che è stato scaricato e aprire il file di soluzione (SLN) per AsyncFineTuningCS.

4.  In **Esplora soluzioni** aprire il menu di scelta rapida per il progetto **ProcessTasksAsTheyFinish** e quindi scegliere **Imposta come progetto di avvio**.

5.  Premere **F5** per eseguire il programma (oppure **CTRL**+**F5** per eseguire il programma senza il debug).

6.  Eseguire il progetto più volte per verificare che le lunghezze scaricate non siano sempre nello stesso ordine.

## <a name="create-the-program-yourself"></a>Creare il programma autonomamente

Questo esempio è basato sul codice sviluppato in [Annullare le attività asincrone rimanenti dopo che ne è stata completata una (C#)](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md) e usa la stessa interfaccia utente.

Per compilare l'esempio passo a passo, seguire le istruzioni nella sezione [Download dell'esempio](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md#downloading-the-example), ma scegliere **CancelAfterOneTask** come progetto di avvio. Aggiungere le modifiche in questo argomento al metodo `AccessTheWebAsync` in tale progetto. Le modifiche sono contrassegnate con asterischi.

Il progetto **CancelAfterOneTask** include già una query che, se eseguita, crea una Collection di attività. Ogni chiamata a `ProcessURLAsync` nel codice seguente restituisce un <xref:System.Threading.Tasks.Task%601>, dove `TResult` è un valore intero:

```csharp
IEnumerable<Task<int>> downloadTasksQuery = from url in urlList select ProcessURL(url, client, ct);
```

Nel file MainWindow.xaml.cs di tale progetto apportare le modifiche seguenti al metodo `AccessTheWebAsync`.

-   Eseguire la query applicando <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> anziché <xref:System.Linq.Enumerable.ToArray%2A>.

    ```csharp
    List<Task<int>> downloadTasks = downloadTasksQuery.ToList();
    ```

-   Aggiungere un ciclo `while` che esegue i passaggi seguenti per ogni attività nella raccolta:

    1.  Attende una chiamata a `WhenAny` per identificare la prima attività nella raccolta che deve completare il relativo download.

        ```csharp
        Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);
        ```

    2.  Rimuove l'attività dalla Collection.

        ```csharp
        downloadTasks.Remove(firstFinishedTask);
        ```

    3.  Attende `firstFinishedTask`, che viene restituito da una chiamata a `ProcessURLAsync`. La variabile `firstFinishedTask` è un <xref:System.Threading.Tasks.Task%601> dove `TReturn` è un valore intero. L'attività è già stata completata, ma è possibile metterla in attesa per recuperare la lunghezza del sito Web scaricato, come illustrato di seguito.

        ```csharp
        int length = await firstFinishedTask;
        resultsTextBox.Text += String.Format("\r\nLength of the download:  {0}", length);
        ```

Eseguire il programma più volte per verificare che le lunghezze scaricate non siano sempre nello stesso ordine.

> [!CAUTION]
> È possibile usare `WhenAny` in un ciclo, come descritto nell'esempio, per risolvere i problemi che includono un numero limitato di attività. Tuttavia, se ci sono molte attività da elaborare, altri approcci sono più efficienti. Per altre informazioni ed esempi, vedere [Processing tasks as they complete](https://blogs.msdn.microsoft.com/pfxteam/2012/08/02/processing-tasks-as-they-complete/) (Elaborazione di attività completate).

## <a name="complete-example"></a>Esempio completo

Il codice seguente è il testo completo del file MainWindow.xaml.cs per l'esempio. Gli asterischi contrassegnano gli elementi che sono stati aggiunti per questo esempio. Si noti inoltre che è necessario aggiungere un riferimento per <xref:System.Net.Http>.

È possibile scaricare il progetto da [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: ottimizzazione dell'applicazione).

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

// Add a using directive and a reference for System.Net.Http.
using System.Net.Http;

// Add the following using directive.
using System.Threading;

namespace ProcessTasksAsTheyFinish
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
            resultsTextBox.Clear();

            // Instantiate the CancellationTokenSource.
            cts = new CancellationTokenSource();

            try
            {
                await AccessTheWebAsync(cts.Token);
                resultsTextBox.Text += "\r\nDownloads complete.";
            }
            catch (OperationCanceledException)
            {
                resultsTextBox.Text += "\r\nDownloads canceled.\r\n";
            }
            catch (Exception)
            {
                resultsTextBox.Text += "\r\nDownloads failed.\r\n";
            }

            cts = null;
        }

        private void cancelButton_Click(object sender, RoutedEventArgs e)
        {
            if (cts != null)
            {
                cts.Cancel();
            }
        }

        async Task AccessTheWebAsync(CancellationToken ct)
        {
            HttpClient client = new HttpClient();

            // Make a list of web addresses.
            List<string> urlList = SetUpURLList();

            // ***Create a query that, when executed, returns a collection of tasks.
            IEnumerable<Task<int>> downloadTasksQuery =
                from url in urlList select ProcessURL(url, client, ct);

            // ***Use ToList to execute the query and start the tasks.
            List<Task<int>> downloadTasks = downloadTasksQuery.ToList();

            // ***Add a loop to process the tasks one at a time until none remain.
            while (downloadTasks.Count > 0)
            {
                    // Identify the first task that completes.
                    Task<int> firstFinishedTask = await Task.WhenAny(downloadTasks);

                    // ***Remove the selected task from the list so that you don't
                    // process it more than once.
                    downloadTasks.Remove(firstFinishedTask);

                    // Await the completed task.
                    int length = await firstFinishedTask;
                    resultsTextBox.Text += String.Format("\r\nLength of the download:  {0}", length);
            }
        }

        private List<string> SetUpURLList()
        {
            List<string> urls = new List<string>
            {
                "https://msdn.microsoft.com",
                "https://msdn.microsoft.com/library/windows/apps/br211380.aspx",
                "https://msdn.microsoft.com/library/hh290136.aspx",
                "https://msdn.microsoft.com/library/dd470362.aspx",
                "https://msdn.microsoft.com/library/aa578028.aspx",
                "https://msdn.microsoft.com/library/ms404677.aspx",
                "https://msdn.microsoft.com/library/ff730837.aspx"
            };
            return urls;
        }

        async Task<int> ProcessURL(string url, HttpClient client, CancellationToken ct)
        {
            // GetAsync returns a Task<HttpResponseMessage>.
            HttpResponseMessage response = await client.GetAsync(url, ct);

            // Retrieve the website contents from the HttpResponseMessage.
            byte[] urlContents = await response.Content.ReadAsByteArrayAsync();

            return urlContents.Length;
        }
    }
}

// Sample Output:

// Length of the download:  226093
// Length of the download:  412588
// Length of the download:  175490
// Length of the download:  204890
// Length of the download:  158855
// Length of the download:  145790
// Length of the download:  44908
// Downloads complete.
```

## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.Tasks.Task.WhenAny%2A>
- [Ottimizzazione dell'applicazione Async (C#)](../../../../csharp/programming-guide/concepts/async/fine-tuning-your-async-application.md)
- [Programmazione asincrona con Async e Await (C#)](../../../../csharp/programming-guide/concepts/async/index.md)
- [Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: Ottimizzazione dell'applicazione)