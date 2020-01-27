---
title: Memorizzare nella cache i dati dell'app
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthroughs [WPF], caching
- caching [.NET Framework]
- caching [WPF]
ms.assetid: dac2c9ce-042b-4d23-91eb-28f584415cef
ms.openlocfilehash: b7d999f94e2f2ae410a16e537d51c0f890def4e1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728063"
---
# <a name="walkthrough-caching-application-data-in-a-wpf-application"></a>Procedura dettagliata: memorizzazione dei dati di un'applicazione nella cache di un'applicazione WPF
La memorizzazione nella cache consente di inserire i dati in memoria per l'accesso rapido. Quando accedono nuovamente ai dati, le applicazioni possono recuperarli dalla cache anziché dall'origine. In questo modo si possono ottenere migliori prestazioni e scalabilità. Inoltre, se si memorizzano i dati nella cache, questi sono accessibili anche quando l'origine dati è temporaneamente non disponibile.

 Il .NET Framework fornisce classi che consentono di usare la memorizzazione nella cache nelle applicazioni .NET Framework. Queste classi si trovano nello spazio dei nomi <xref:System.Runtime.Caching>.

> [!NOTE]
> Lo spazio dei nomi <xref:System.Runtime.Caching> è nuovo in .NET Framework 4. Questo spazio dei nomi rende disponibile la memorizzazione nella cache per tutte le applicazioni .NET Framework. Nelle versioni precedenti del .NET Framework, la memorizzazione nella cache era disponibile solo nello spazio dei nomi <xref:System.Web> e pertanto richiedeva una dipendenza dalle classi ASP.NET.

 In questa procedura dettagliata viene illustrato come utilizzare la funzionalità di memorizzazione nella cache disponibile nel .NET Framework come parte di un'applicazione [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Nella procedura dettagliata viene memorizzato nella cache il contenuto di un file di testo.

 Di seguito vengono illustrate le attività incluse nella procedura dettagliata:

- Creazione di un progetto di applicazione WPF.

- Aggiunta di un riferimento al .NET Framework 4.

- Inizializzazione di una cache.

- Aggiunta di una voce della cache che contiene il contenuto di un file di testo.

- Fornire un criterio di rimozione per la voce della cache.

- Monitoraggio del percorso del file memorizzato nella cache e notifica all'istanza della cache le modifiche apportate all'elemento monitorato.

## <a name="prerequisites"></a>Prerequisiti
 Per completare questa procedura dettagliata, è necessario:

- Visual Studio 2010.

- Un file di testo che contiene una piccola quantità di testo. Il contenuto del file di testo viene visualizzato in una finestra di messaggio. Il codice illustrato nella procedura dettagliata presuppone che si stia utilizzando il file seguente:

     `c:\cache\cacheText.txt`

     Tuttavia, è possibile usare qualsiasi file di testo e apportare piccole modifiche al codice in questa procedura dettagliata.

## <a name="creating-a-wpf-application-project"></a>Creazione di un progetto di applicazione WPF
 Si inizierà creando un progetto di applicazione WPF.

#### <a name="to-create-a-wpf-application"></a>Per creare un'applicazione WPF

1. Avviare Visual Studio.

2. Scegliere **nuovo**dal menu **file** , quindi fare clic su **nuovo progetto**.

     Verrà visualizzata la finestra di dialogo **Nuovo progetto**.

3. In **modelli installati**selezionare il linguaggio di programmazione che si desidera utilizzare (**Visual Basic** o **oggetto C#visivo** ).

4. Nella finestra di dialogo **nuovo progetto** selezionare **applicazione WPF**.

    > [!NOTE]
    > Se il modello **applicazione WPF** non è visibile, assicurarsi che la destinazione sia una versione del .NET Framework che supporta WPF. Nella finestra di dialogo **nuovo progetto** selezionare .NET Framework 4 nell'elenco.

5. Nella casella di testo **nome** immettere un nome per il progetto. Ad esempio, è possibile immettere **WPFCaching**.

6. Selezionare la casella di controllo **Crea directory per soluzione**.

7. Fare clic su **OK**.

     WPF Designer viene aperto in visualizzazione **progettazione** e visualizza il file MainWindow. XAML. Visual Studio crea la cartella del **progetto** , il file Application. XAML e il file MainWindow. XAML.

## <a name="targeting-the-net-framework-and-adding-a-reference-to-the-caching-assemblies"></a>Destinazione della .NET Framework e aggiunta di un riferimento agli assembly di memorizzazione nella cache
 Per impostazione predefinita, le applicazioni WPF sono destinate al profilo client di .NET Framework 4. Per utilizzare lo spazio dei nomi <xref:System.Runtime.Caching> in un'applicazione WPF, è necessario che l'applicazione sia destinata al .NET Framework 4 (non al profilo client .NET Framework 4) e che includa un riferimento allo spazio dei nomi.

 Il passaggio successivo consiste quindi nel modificare la destinazione .NET Framework e aggiungere un riferimento allo spazio dei nomi <xref:System.Runtime.Caching>.

> [!NOTE]
> La procedura per la modifica della destinazione .NET Framework è diversa in un progetto Visual Basic e in un C# progetto visuale.

#### <a name="to-change-the-target-net-framework-in-visual-basic"></a>Per modificare la .NET Framework di destinazione in Visual Basic

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nome del progetto, quindi scegliere **Proprietà**.

     Verrà visualizzata la finestra proprietà per l'applicazione.

2. Fare clic sulla scheda **Compila**.

3. Nella parte inferiore della finestra fare clic su **Opzioni di compilazione avanzate**.

     Viene visualizzata la finestra di dialogo **impostazioni del compilatore avanzate** .

4. Nell'elenco **Framework di destinazione (tutte le configurazioni)** selezionare .NET Framework 4. (Non selezionare .NET Framework 4 profilo client).

5. Fare clic su **OK**.

     Viene visualizzata la finestra di dialogo **Modifica del framework di destinazione**.

6. Nella finestra di dialogo **modifica Framework di destinazione** fare clic su **Sì**.

     Il progetto viene chiuso e quindi riaperto.

7. Aggiungere un riferimento all'assembly di Caching attenendosi alla procedura seguente:

    1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nome del progetto, quindi scegliere **Aggiungi riferimento**.

    2. Selezionare la scheda **.NET** , selezionare `System.Runtime.Caching`e quindi fare clic su **OK**.

#### <a name="to-change-the-target-net-framework-in-a-visual-c-project"></a>Per modificare la .NET Framework di destinazione in un C# progetto Visual

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nome del progetto, quindi scegliere **Proprietà**.

     Verrà visualizzata la finestra proprietà per l'applicazione.

2. Fare clic sulla scheda **Applicazione** .

3. Nell'elenco **Framework di destinazione** selezionare .NET Framework 4. (Non selezionare **.NET Framework 4 profilo client**).

4. Aggiungere un riferimento all'assembly di Caching attenendosi alla procedura seguente:

    1. Fare clic con il pulsante destro del mouse sulla cartella **riferimenti** , quindi scegliere **Aggiungi riferimento**.

    2. Selezionare la scheda **.NET** , selezionare `System.Runtime.Caching`e quindi fare clic su **OK**.

## <a name="adding-a-button-to-the-wpf-window"></a>Aggiunta di un pulsante alla finestra WPF
 Successivamente, si aggiungerà un controllo Button e si creerà un gestore eventi per l'evento `Click` del pulsante. Successivamente, quando si fa clic sul pulsante viene aggiunto il codice, il contenuto del file di testo viene memorizzato nella cache e visualizzato.

#### <a name="to-add-a-button-control"></a>Per aggiungere un controllo Button

1. In **Esplora soluzioni**fare doppio clic sul file MainWindow. XAML per aprirlo.

2. Dalla **casella degli strumenti**, sotto **controlli WPF comuni**trascinare un controllo `Button` nella finestra di `MainWindow`.

3. Nella finestra **Proprietà** impostare la proprietà `Content` del controllo `Button` per **ottenere la cache**.

## <a name="initializing-the-cache-and-caching-an-entry"></a>Inizializzazione della cache e memorizzazione nella cache di una voce
 Successivamente, verrà aggiunto il codice per eseguire le attività seguenti:

- Creare un'istanza della classe cache, ovvero si creerà un'istanza di un nuovo oggetto <xref:System.Runtime.Caching.MemoryCache>.

- Consente di specificare che la cache utilizza un oggetto <xref:System.Runtime.Caching.HostFileChangeMonitor> per monitorare le modifiche nel file di testo.

- Leggere il file di testo e memorizzare nella cache il relativo contenuto come voce della cache.

- Visualizza il contenuto del file di testo memorizzato nella cache.

#### <a name="to-create-the-cache-object"></a>Per creare l'oggetto cache

1. Fare doppio clic sul pulsante appena aggiunto per creare un gestore eventi nel file MainWindow.xaml.cs o MainWindow. XAML. vb.

2. Nella parte superiore del file (prima della dichiarazione di classe) aggiungere le seguenti istruzioni `Imports` (Visual Basic) o `using` (C#):

    ```csharp
    using System.Runtime.Caching;
    using System.IO;
    ```

    ```vb
    Imports System.Runtime.Caching
    Imports System.IO
    ```

3. Nel gestore eventi aggiungere il codice seguente per creare un'istanza dell'oggetto cache:

    ```csharp
    ObjectCache cache = MemoryCache.Default;
    ```

    ```vb
    Dim cache As ObjectCache = MemoryCache.Default
    ```

     La classe <xref:System.Runtime.Caching.ObjectCache> è una classe incorporata che fornisce una cache di oggetti in memoria.

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

     Se la voce della cache specificata non esiste, è necessario leggere il file di testo e aggiungerlo come voce della cache alla cache.

6. Nel blocco `if/then` aggiungere il codice seguente per creare un nuovo oggetto <xref:System.Runtime.Caching.CacheItemPolicy> che specifichi che la voce della cache scade dopo 10 secondi.

    ```vb
    Dim policy As New CacheItemPolicy()
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)
    ```

    ```csharp
    CacheItemPolicy policy = new CacheItemPolicy();
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);
    ```

     Se non viene fornita alcuna informazione di rimozione o scadenza, il valore predefinito è <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, il che significa che le voci della cache non scadono mai in base a un tempo assoluto. Al contrario, le voci della cache scadono solo quando si verifica un numero eccessivo di richieste di memoria. Come procedura consigliata, è consigliabile specificare sempre in modo esplicito una scadenza assoluta o variabile.

7. All'interno del blocco `if/then` e dopo il codice aggiunto nel passaggio precedente, aggiungere il codice seguente per creare una raccolta per i percorsi di file che si desidera monitorare e per aggiungere il percorso del file di testo alla raccolta:

    ```vb
    Dim filePaths As New List(Of String)()
    filePaths.Add("c:\cache\cacheText.txt")
    ```

    ```csharp
    List<string> filePaths = new List<string>();
    filePaths.Add("c:\\cache\\cacheText.txt");
    ```

    > [!NOTE]
    > Se il file di testo che si desidera utilizzare non è `c:\cache\cacheText.txt`, specificare il percorso in cui si desidera utilizzare il file di testo.

8. Dopo il codice aggiunto nel passaggio precedente, aggiungere il codice seguente per aggiungere un nuovo oggetto <xref:System.Runtime.Caching.HostFileChangeMonitor> alla raccolta di monitoraggi delle modifiche per la voce della cache:

    ```vb
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))
    ```

    ```csharp
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));
    ```

     L'oggetto <xref:System.Runtime.Caching.HostFileChangeMonitor> monitora il percorso del file di testo e invia una notifica alla cache se si verificano modifiche. In questo esempio, la voce della cache scadrà se il contenuto del file viene modificato.

9. Dopo il codice aggiunto nel passaggio precedente, aggiungere il codice seguente per leggere il contenuto del file di testo:

    ```vb
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()
    ```

    ```csharp
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + "\n" + DateTime.Now;
    ```

     Viene aggiunto il timestamp di data e ora in modo che sia possibile visualizzare la scadenza della voce della cache.

10. Dopo il codice aggiunto nel passaggio precedente, aggiungere il codice seguente per inserire il contenuto del file nell'oggetto cache come istanza di <xref:System.Runtime.Caching.CacheItem>:

    ```vb
    cache.Set("filecontents", fileContents, policy)
    ```

    ```csharp
    cache.Set("filecontents", fileContents, policy);
    ```

     Specificare le informazioni sulla modalità di eliminazione della voce della cache passando l'oggetto <xref:System.Runtime.Caching.CacheItemPolicy> creato in precedenza come parametro.

11. Dopo il blocco `if/then` aggiungere il codice seguente per visualizzare il contenuto del file memorizzato nella cache in una finestra di messaggio:

    ```vb
    MessageBox.Show(fileContents)
    ```

    ```csharp
    MessageBox.Show(fileContents);
    ```

12. Scegliere **Compila WPFCaching** dal menu **Compila** per compilare il progetto.

## <a name="testing-caching-in-the-wpf-application"></a>Test della memorizzazione nella cache nell'applicazione WPF
 È ora possibile eseguire il test dell’applicazione.

#### <a name="to-test-caching-in-the-wpf-application"></a>Per testare la memorizzazione nella cache nell'applicazione WPF

1. Premere CTRL+F5 per eseguire l'applicazione.

     Viene visualizzata la finestra `MainWindow`.

2. Fare clic su **Ottieni cache**.

     Il contenuto memorizzato nella cache del file di testo viene visualizzato in una finestra di messaggio. Si noti il timestamp del file.

3. Chiudere la finestra di messaggio e quindi fare di nuovo clic su **Get cache** .

     Il timestamp è invariato. Indica che viene visualizzato il contenuto memorizzato nella cache.

4. Attendere 10 secondi o più, quindi fare di nuovo clic su **Ottieni cache** .

     Questa volta viene visualizzato un nuovo timestamp. Ciò indica che i criteri consentono la scadenza della voce della cache e che viene visualizzato il nuovo contenuto memorizzato nella cache.

5. In un editor di testo aprire il file di testo creato. Non apportare alcuna modifica.

6. Chiudere la finestra di messaggio e quindi fare di nuovo clic su **Get cache** .

     Si noti di nuovo il timestamp.

7. Apportare una modifica al file di testo e quindi salvare il file.

8. Chiudere la finestra di messaggio e quindi fare di nuovo clic su **Get cache** .

     Questa finestra di messaggio contiene il contenuto aggiornato del file di testo e un nuovo timestamp. Ciò indica che il monitoraggio delle modifiche del file host ha rimosso la voce della cache immediatamente quando è stato modificato il file, anche se il periodo di timeout assoluto non è scaduto.

    > [!NOTE]
    > È possibile aumentare il tempo di rimozione a 20 secondi o più per consentire più tempo per apportare modifiche al file.

## <a name="code-example"></a>Esempio di codice
 Al termine di questa procedura dettagliata, il codice per il progetto creato sarà simile all'esempio seguente.

 [!code-csharp[CachingWPFApplications#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.Caching.MemoryCache>
- <xref:System.Runtime.Caching.ObjectCache>
- <xref:System.Runtime.Caching>
- [Memorizzazione nella cache in applicazioni .NET Framework](../../performance/caching-in-net-framework-applications.md)
