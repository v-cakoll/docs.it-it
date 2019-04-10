---
title: "Procedura dettagliata: Memorizzazione dei dati di un'applicazione nella cache di un'applicazione WPF"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthroughs [WPF], caching
- caching [.NET Framework]
- caching [WPF]
ms.assetid: dac2c9ce-042b-4d23-91eb-28f584415cef
ms.openlocfilehash: 1d00c222dabf446c7c102307c3b904d3f1ff4bca
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59314393"
---
# <a name="walkthrough-caching-application-data-in-a-wpf-application"></a>Procedura dettagliata: Memorizzazione dei dati di un'applicazione nella cache di un'applicazione WPF
La memorizzazione nella cache consente di inserire i dati in memoria per l'accesso rapido. Quando accedono nuovamente ai dati, le applicazioni possono recuperarli dalla cache anziché dall'origine. In questo modo si possono ottenere migliori prestazioni e scalabilità. Inoltre, se si memorizzano i dati nella cache, questi sono accessibili anche quando l'origine dati è temporaneamente non disponibile.

 Il [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] fornisce le classi che consentono di usare la memorizzazione nella cache [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] applicazioni. Queste classi si trovano nel <xref:System.Runtime.Caching> dello spazio dei nomi.

> [!NOTE]
>  Il <xref:System.Runtime.Caching> dello spazio dei nomi è una novità di [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]. Questo spazio dei nomi rende la memorizzazione nella cache è disponibile per tutti [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] applicazioni. Nelle versioni precedenti di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] la memorizzazione nella cache è disponibile solo nello spazio dei nomi <xref:System.Web> e pertanto richiede una dipendenza dalle classi ASP.NET.

 Questa procedura dettagliata illustra come usare le funzionalità di memorizzazione nella cache sono disponibile nel [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] come parte di un [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] dell'applicazione. Nella procedura dettagliata, si memorizzano nella cache il contenuto di un file di testo.

 Di seguito vengono illustrate le attività incluse nella procedura dettagliata:

-   Creazione di un progetto di applicazione WPF.

-   Aggiunge un riferimento al [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].

-   Inizializzazione di una cache.

-   Aggiunta di una voce della cache che contiene il contenuto di un file di testo.

-   Fornire un criterio di rimozione della voce della cache.

-   Il percorso del file memorizzato nella cache di monitoraggio e la notifica l'istanza della cache sulla modifica dell'elemento monitorato.

## <a name="prerequisites"></a>Prerequisiti
 Per completare questa procedura dettagliata, è necessario:

-   Microsoft Visual Studio 2010

-   Un file di testo che contiene una piccola quantità di testo. (Si verrà visualizzato il contenuto del file di testo in una finestra di messaggio). Il codice illustrato nella procedura dettagliata si presuppone che si lavora con il file seguente:

     `c:\cache\cacheText.txt`

     Tuttavia, è possibile usare qualsiasi file di testo e apportare piccole modifiche al codice in questa procedura dettagliata.

## <a name="creating-a-wpf-application-project"></a>Creazione di un progetto di applicazione WPF
 Inizierà creando un progetto di applicazione WPF.

#### <a name="to-create-a-wpf-application"></a>Per creare un'applicazione WPF

1. Avviare Visual Studio.

2. Nel **File** menu, fare clic su **New**, quindi fare clic su **nuovo progetto**.

     Verrà visualizzata la finestra di dialogo **Nuovo progetto**.

3. Sotto **modelli installati**, selezionare il linguaggio di programmazione da usare (**Visual Basic** oppure **Visual c#**).

4. Nel **nuovo progetto** finestra di dialogo **applicazione WPF**.

    > [!NOTE]
    >  Se non viene visualizzato il **applicazione WPF** modello, assicurarsi che si intende utilizzare una versione del [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] che supporta WPF. Nel **nuovo progetto** finestra di dialogo [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] dall'elenco.

5. Nel **nome** testo casella, immettere un nome per il progetto. Ad esempio, è possibile immettere **WPFCaching**.

6. Selezionare la casella di controllo **Crea directory per soluzione**.

7. Fare clic su **OK**.

     Viene aperta WPF **progettazione** consente di visualizzare e visualizza il file MainWindow. Xaml. Visual Studio crea il **My Project** cartella, il file Application. XAML e il file MainWindow. Xaml.

## <a name="targeting-the-net-framework-and-adding-a-reference-to-the-caching-assemblies"></a>Sviluppare per .NET Framework e aggiungere un riferimento all'assembly di memorizzazione nella cache
 Per impostazione predefinita, sono destinate le applicazioni WPF di [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]. Usare la <xref:System.Runtime.Caching> dello spazio dei nomi in un'applicazione WPF, l'applicazione deve avere come destinazione il [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] (non il [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]) e deve includere un riferimento allo spazio dei nomi.

 Pertanto, il passaggio successivo è modificare la destinazione di .NET Framework e aggiungere un riferimento al <xref:System.Runtime.Caching> dello spazio dei nomi.

> [!NOTE]
>  La procedura per la modifica della destinazione di .NET Framework è diversa in un progetto Visual Basic e in un progetto Visual c#.

#### <a name="to-change-the-target-net-framework-in-visual-basic"></a>Per modificare la destinazione di .NET Framework in Visual Basic

1. Nelle **Esplora soluzioni**, fare clic sul nome del progetto e quindi fare clic su **proprietà**.

     Viene visualizzata la finestra delle proprietà per l'applicazione.

2. Fare clic sulla scheda **Compila**.

3. Nella parte inferiore della finestra, fare clic su **opzioni di compilazione avanzate...** .

     Il **impostazioni del compilatore avanzate** verrà visualizzata la finestra di dialogo.

4. Nel **framework di destinazione (tutte le configurazioni)** elenco, selezionare [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]. (Non selezionare [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].)

5. Fare clic su **OK**.

     Viene visualizzata la finestra di dialogo **Modifica del framework di destinazione**.

6. Nel **modifica Framework di destinazione** finestra di dialogo, fare clic su **Yes**.

     Il progetto viene chiuso e riaperto.

7. Aggiungere un riferimento all'assembly di memorizzazione nella cache, seguire questi passaggi:

    1.  Nelle **Esplora soluzioni**, fare doppio clic il nome del progetto e quindi fare clic su **Aggiungi riferimento**.

    2.  Selezionare il **.NET** scheda, seleziona `System.Runtime.Caching`, quindi fare clic su **OK**.

#### <a name="to-change-the-target-net-framework-in-a-visual-c-project"></a>Per modificare la destinazione di .NET Framework in un progetto Visual c#

1. Nelle **Esplora soluzioni**, fare clic sul nome del progetto e quindi fare clic su **proprietà**.

     Viene visualizzata la finestra delle proprietà per l'applicazione.

2. Fare clic sulla scheda **Applicazione** .

3. Nel **framework di destinazione** elenco, selezionare [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]. (Non si seleziona **.NET Framework 4 Client Profile**.)

4. Aggiungere un riferimento all'assembly di memorizzazione nella cache, seguire questi passaggi:

    1.  Fare doppio clic il **riferimenti** cartella e quindi fare clic su **Aggiungi riferimento**.

    2.  Selezionare il **.NET** scheda, seleziona `System.Runtime.Caching`, quindi fare clic su **OK**.

## <a name="adding-a-button-to-the-wpf-window"></a>Aggiunta di un pulsante nella finestra di WPF
 Quindi si verrà aggiunto un pulsante e creare un gestore eventi per il pulsante `Click` evento. In seguito si aggiungerà codice a in modo che quando si fa clic sul pulsante, il contenuto del file di testo è memorizzati nella cache e visualizzato.

#### <a name="to-add-a-button-control"></a>Per aggiungere un controllo pulsante

1. Nelle **Esplora soluzioni**, fare doppio clic sul file MainWindow. XAML per aprirlo.

2. Dal **casella degli strumenti**, in **controlli WPF comuni**, trascinare un' `Button` il controllo al `MainWindow` finestra.

3. Nel **proprietà** impostare nella finestra di `Content` proprietà del `Button` il controllo a **Ottieni Cache**.

## <a name="initializing-the-cache-and-caching-an-entry"></a>Inizializzazione della Cache e la memorizzazione nella cache una voce
 Successivamente, si aggiungerà il codice per eseguire le attività seguenti:

-   Creare un'istanza della classe della cache, vale a dire, si creerà un nuovo <xref:System.Runtime.Caching.MemoryCache> oggetto.

-   Specificare che la cache utilizza un <xref:System.Runtime.Caching.HostFileChangeMonitor> oggetto per monitorare le modifiche nel file di testo.

-   Leggere il file di testo e il contenuto memorizzato nella cache come una voce della cache.

-   Visualizzare il contenuto del file di testo memorizzato nella cache.

#### <a name="to-create-the-cache-object"></a>Per creare l'oggetto della cache

1. Fare doppio clic sul pulsante che appena aggiunta per poter creare un gestore eventi nel file XAML. vb o MainWindow.xaml.cs.

2. Nella parte superiore del file (prima della dichiarazione di classe), aggiungere quanto segue `Imports` (Visual Basic) o `using` istruzioni (c#):

    ```csharp
    using System.Runtime.Caching;
    using System.IO;
    ```

    ```vb
    Imports System.Runtime.Caching
    Imports System.IO
    ```

3. Nel gestore dell'evento, aggiungere il codice seguente per creare un'istanza di oggetto della cache:

    ```csharp
    ObjectCache cache = MemoryCache.Default;
    ```

    ```vb
    Dim cache As ObjectCache = MemoryCache.Default
    ```

     Il <xref:System.Runtime.Caching.ObjectCache> classe è una classe incorporata che fornisce una cache oggetti in memoria.

4. Aggiungere il codice seguente per leggere il contenuto di una voce della cache denominata `filecontents`:

    ```vb
    Dim fileContents As String = TryCast(cache("filecontents"), String)
    ```

    ```csharp
    string fileContents = cache["filecontents"] as string;
    ```

5. Aggiungere il codice seguente per verificare se la voce della cache denominata `filecontents` esiste:

    ```vb
    If fileContents Is Nothing Then

    End If
    ```

    ```csharp
    if (fileContents == null)
    {

    }
    ```

     Se la voce della cache specificata non esiste, è necessario leggere il file di testo e aggiungerlo come una voce della cache nella cache.

6. Nel `if/then` blocco, aggiungere il codice seguente per creare un nuovo <xref:System.Runtime.Caching.CacheItemPolicy> oggetto che specifica che la voce della cache scade dopo 10 secondi.

    ```vb
    Dim policy As New CacheItemPolicy()
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)
    ```

    ```csharp
    CacheItemPolicy policy = new CacheItemPolicy();
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);
    ```

     Se viene fornita alcuna informazione di eliminazione o scadenza, il valore predefinito è <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, ovvero le voci della cache senza scadenza in base solo in un tempo assoluto. Al contrario, le voci della cache scadono solo quando sono presenti richieste di memoria. Come procedura consigliata, è necessario fornire sempre in modo esplicito assoluto o su una scadenza.

7. All'interno di `if/then` in blocchi e dopo il codice aggiunto nel passaggio precedente, aggiungere il codice seguente per creare una raccolta per i percorsi dei file che si desidera monitorare e aggiungere il percorso del file di testo nella raccolta:

    ```vb
    Dim filePaths As New List(Of String)()
    filePaths.Add("c:\cache\cacheText.txt")
    ```

    ```csharp
    List<string> filePaths = new List<string>();
    filePaths.Add("c:\\cache\\cacheText.txt");
    ```

    > [!NOTE]
    >  Se si desidera utilizzare il file di testo non `c:\cache\cacheText.txt`, specificare il percorso in cui il file di testo è che si desidera utilizzare.

8. Dopo il codice aggiunto nel passaggio precedente, aggiungere il codice seguente per aggiungere un nuovo <xref:System.Runtime.Caching.HostFileChangeMonitor> oggetto alla raccolta di modifiche consente di monitorare la voce della cache:

    ```vb
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))
    ```

    ```csharp
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));
    ```

     Il <xref:System.Runtime.Caching.HostFileChangeMonitor> oggetto consente di monitorare il percorso del file di testo e invia una notifica della cache se si verificano cambiamenti. In questo esempio, la voce della cache scadrà se il contenuto del file viene modificato.

9. Dopo il codice aggiunto nel passaggio precedente, aggiungere il codice seguente per leggere il contenuto del file di testo:

    ```vb
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()
    ```

    ```csharp
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + "\n" + DateTime.Now;
    ```

     Il timestamp di data e ora viene aggiunto in modo che sarà in grado di vedere quando scade la voce della cache.

10. Dopo il codice aggiunto nel passaggio precedente, aggiungere il codice seguente per inserire il contenuto del file in oggetto cache come un <xref:System.Runtime.Caching.CacheItem> istanza:

    ```vb
    cache.Set("filecontents", fileContents, policy)
    ```

    ```csharp
    cache.Set("filecontents", fileContents, policy);
    ```

     Specificare le informazioni sulle modalità di eliminazione della voce della cache passando il <xref:System.Runtime.Caching.CacheItemPolicy> oggetto creato in precedenza come parametro.

11. Dopo il `if/then` blocco, aggiungere il codice seguente per visualizzare il contenuto del file memorizzato nella cache in una finestra di messaggio:

    ```vb
    MessageBox.Show(fileContents)
    ```

    ```csharp
    MessageBox.Show(fileContents);
    ```

12. Nel **compilare** menu, fare clic su **compilare WPFCaching** per compilare il progetto.

## <a name="testing-caching-in-the-wpf-application"></a>Test di memorizzazione nella cache nell'applicazione WPF
 È ora possibile testare l'applicazione.

#### <a name="to-test-caching-in-the-wpf-application"></a>Per testare la memorizzazione nella cache nell'applicazione WPF

1. Premere CTRL+F5 per eseguire l'applicazione.

     Il `MainWindow` viene visualizzata la finestra.

2. Fare clic su **ottenere Cache**.

     Il contenuto memorizzato nella cache dal file di testo viene visualizzato in una finestra di messaggio. Si noti che il timestamp sul file.

3. Chiudere la finestra di messaggio e quindi fare clic su **Ottieni Cache** nuovamente.

     Il timestamp è invariato. Ciò indica che viene visualizzato il contenuto memorizzato nella cache.

4. Attendere almeno 10 secondi e quindi fare clic su **Ottieni Cache** nuovamente.

     Questo tempo viene visualizzato un nuovo timestamp. Ciò indica che i criteri consentono la voce della cache scadono e che venga visualizzato nuovo contenuto memorizzato nella cache.

5. In un editor di testo aprire il file di testo che è stato creato. Non apportare eventuali modifiche ancora.

6. Chiudere la finestra di messaggio e quindi fare clic su **Ottieni Cache** nuovamente.

     Si noti che il timestamp nuovamente.

7. Apportare una modifica al file di testo e quindi salvare il file.

8. Chiudere la finestra di messaggio e quindi fare clic su **Ottieni Cache** nuovamente.

     Questa finestra di messaggio contiene il contenuto aggiornato dai file di testo e un nuovo timestamp. Ciò indica che il monitoraggio delle modifiche file host rimosso la voce della cache immediatamente quando si modifica il file, anche se il periodo di timeout assoluto non era scaduto.

    > [!NOTE]
    >  È possibile aumentare il tempo di eliminazione per almeno 20 secondi per dare più tempo per poter apportare una modifica nel file.

## <a name="code-example"></a>Esempio di codice
 Dopo aver completato questa procedura dettagliata, il codice per il progetto creato sarà simile all'esempio seguente.

 [!code-csharp[CachingWPFApplications#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.Caching.MemoryCache>
- <xref:System.Runtime.Caching.ObjectCache>
- <xref:System.Runtime.Caching>
- [Memorizzazione nella cache in applicazioni .NET Framework](../../performance/caching-in-net-framework-applications.md)
