---
title: Modello di threading
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text on buttons [WPF], updating
- message processing [WPF], nested
- blocking operations [WPF]
- Common Language Runtime (CLR), locking mechanism
- locking mechanism of Common Language Runtime (CLR)
- threading model [WPF]
- Word [WPF], spelling checking
- button text [WPF], updating
- spelling checking in Word [WPF]
- asynchronous behavior [WPF], exposing
- nested message processing [WPF]
- reentrancy [WPF]
ms.assetid: 02d8fd00-8d7c-4604-874c-58e40786770b
ms.openlocfilehash: c86ab6c7d5113f95b0fd93d194465c4af701f78a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54513651"
---
# <a name="threading-model"></a>Modello di threading
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] è stato progettato per semplificare il threading. Di conseguenza, la maggior parte delle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gli sviluppatori non sarà necessario scrivere un'interfaccia che usa più thread. Poiché i programmi con multithreading sono complessi ed è difficile eseguirne il debug, è preferibile evitarli quando sono disponibili soluzioni a thread singolo.  
  
 Nessun indipendentemente dall'architettura, tuttavia, no [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] framework mai saranno in grado di fornire una soluzione a thread singolo per ogni tipo di problema. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] si avvicina, ma ci sono comunque situazioni in cui più thread migliorano [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] delle prestazioni di velocità di risposta o l'applicazione. Dopo aver illustrato alcune nozioni di base, questo documento analizza alcune di queste situazioni per concludere con la descrizione di alcuni aspetti più in dettaglio.  
  

  
> [!NOTE]
>  In questo argomento illustra il threading usando il <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> metodo per le chiamate asincrone. È anche possibile eseguire chiamate asincrone chiamando il <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A> metodo, che accettano un' <xref:System.Action> o <xref:System.Func%601> come parametro.  Il <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A> metodo restituisce un <xref:System.Windows.Threading.DispatcherOperation> oppure <xref:System.Windows.Threading.DispatcherOperation%601>, che ha un <xref:System.Windows.Threading.DispatcherOperation.Task%2A> proprietà. È possibile usare la `await` parola chiave con il <xref:System.Windows.Threading.DispatcherOperation> o associato <xref:System.Threading.Tasks.Task>. Se è necessario attendere in modo sincrono il <xref:System.Threading.Tasks.Task> restituito da un <xref:System.Windows.Threading.DispatcherOperation> oppure <xref:System.Windows.Threading.DispatcherOperation%601>, chiamare il <xref:System.Windows.Threading.TaskExtensions.DispatcherOperationWait%2A> metodo di estensione.  La chiamata a <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> provoca un deadlock. Per altre informazioni sull'uso di un <xref:System.Threading.Tasks.Task> per eseguire operazioni asincrone, vedere parallelismo delle attività.  Il <xref:System.Windows.Threading.Dispatcher.Invoke%2A> metodo ha anche overload che accettano un' <xref:System.Action> o <xref:System.Func%601> come parametro.  È possibile usare la <xref:System.Windows.Threading.Dispatcher.Invoke%2A> per rendere sincrono un metodo viene chiamato passando un delegato <xref:System.Action> o <xref:System.Func%601>.  
  
<a name="threading_overview"></a>   
## <a name="overview-and-the-dispatcher"></a>Panoramica e dispatcher  
 In genere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione inizia con due thread: uno per la gestione di rendering e l'altro per la gestione di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Il thread di rendering viene eseguito nascosto in background mentre il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread riceve l'input, gestisce gli eventi, disegna lo schermo ed esegue il codice dell'applicazione. La maggior parte delle applicazioni utilizzano un singolo [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread, anche se in alcune situazioni è preferibile usarne diversi. Questo aspetto verrà spiegato più avanti con un esempio.  
  
 Il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] code del thread di lavoro elementi all'interno di un oggetto denominato un <xref:System.Windows.Threading.Dispatcher>. L'oggetto <xref:System.Windows.Threading.Dispatcher> seleziona gli elementi di lavoro in base alla priorità ed esegue ciascuno fino al completamento.  Ogni [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] deve avere almeno un thread <xref:System.Windows.Threading.Dispatcher>e ogni <xref:System.Windows.Threading.Dispatcher> possono eseguire gli elementi di lavoro in un unico thread.  
  
 Il trucco per la creazione di applicazioni reattive e intuitive, consiste nell'ottimizzare il <xref:System.Windows.Threading.Dispatcher> velocità effettiva mantenendo gli elementi di lavoro sia piccoli. In questo modo, gli elementi non rimarranno mai <xref:System.Windows.Threading.Dispatcher> coda in attesa di elaborazione. Qualsiasi ritardo percepibile tra input e risposta può causare frustrazione in un utente.  
  
 Come si sono [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le applicazioni devono per gestire le operazioni di grandi dimensioni? Cosa è necessario fare se il codice prevede calcoli complessi o l'esecuzione di query su un database in un server remoto? In genere, la risposta è per gestire l'operazione di big data in un thread separato, lasciando il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread libero per gli elementi nella <xref:System.Windows.Threading.Dispatcher> coda. Una volta completata l'operazione di big data, è possibile segnalare il risultato al [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread per la visualizzazione.  
  
 In passato i [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] consente a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementi accessibile solo tramite il thread che li ha creati. Ciò significava che un thread in background responsabile di un'attività a esecuzione prolungata non poteva aggiornare una casella di testo dopo il suo completamento. [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] esegue questa operazione per garantire l'integrità del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] componenti. Una casella di riepilogo può apparire strana se il relativo contenuto viene aggiornato da un thread in background mentre viene disegnata.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] include un meccanismo predefinito di esclusione reciproca che impone questo coordinamento. La maggior parte delle classi nello [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] derivano da <xref:System.Windows.Threading.DispatcherObject>. In fase di costruzione, un <xref:System.Windows.Threading.DispatcherObject> archivia un riferimento di <xref:System.Windows.Threading.Dispatcher> collegato al thread attualmente in esecuzione. In effetti, il <xref:System.Windows.Threading.DispatcherObject> associa il thread che lo crea. Durante l'esecuzione del programma, un <xref:System.Windows.Threading.DispatcherObject> può chiamare pubblici <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> (metodo). <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> esamina i <xref:System.Windows.Threading.Dispatcher> associato al thread corrente e confrontato con il <xref:System.Windows.Threading.Dispatcher> riferimento archiviato durante la costruzione. Se non corrispondono, <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> genera un'eccezione. <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> è destinato a essere chiamato all'inizio di ogni metodo appartenente a un <xref:System.Windows.Threading.DispatcherObject>.  
  
 Se solo un thread può modificare il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], come interagiscono con l'utente i thread in background? Un thread in background può chiedere il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread per eseguire un'operazione per suo conto. A tale scopo, la registrazione di un elemento di lavoro con il <xref:System.Windows.Threading.Dispatcher> del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread. Il <xref:System.Windows.Threading.Dispatcher> classe fornisce due metodi per la registrazione degli elementi di lavoro: <xref:System.Windows.Threading.Dispatcher.Invoke%2A> e <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>. Entrambi i metodi pianificano un delegato per l'esecuzione. <xref:System.Windows.Threading.Dispatcher.Invoke%2A> una chiamata sincrona, ovvero non restituisce finché il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread termina l'esecuzione del delegato. <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> è asincrona e restituisce immediatamente.  
  
 Il <xref:System.Windows.Threading.Dispatcher> Ordina gli elementi nella coda in base alla priorità. Ci sono dieci livelli che possono essere specificati quando si aggiunge un elemento verso il <xref:System.Windows.Threading.Dispatcher> coda. Queste priorità vengono mantenute nel <xref:System.Windows.Threading.DispatcherPriority> enumerazione. Informazioni dettagliate sui <xref:System.Windows.Threading.DispatcherPriority> livelli sono reperibili nel [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)] documentazione.  
  
<a name="samples"></a>   
## <a name="threads-in-action-the-samples"></a>Thread in azione: Gli esempi  
  
<a name="prime_number"></a>   
### <a name="a-single-threaded-application-with-a-long-running-calculation"></a>Applicazione a thread singolo con calcolo a esecuzione prolungata  
 La maggior parte delle [!INCLUDE[TLA#tla_gui#plural](../../../../includes/tlasharptla-guisharpplural-md.md)] rimane per gran parte del loro tempo di inattività durante l'attesa di eventi che vengono generati in risposta alle interazioni dell'utente. Con un'attenta programmazione questo tempo di inattività può essere usato in modo costruttivo, senza influire sulla velocità di risposta del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] modello di threading non consente l'input di interrompere un'operazione in corso nel [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread. Ciò significa che è necessario tornare al <xref:System.Windows.Threading.Dispatcher> periodicamente al processo in attesa di eventi di input prima che diventino obsoleti.  
  
 Si consideri l'esempio seguente:  
  
 ![Screenshot relativo ai numeri primi](../../../../docs/framework/wpf/advanced/media/threadingprimenumberscreenshot.PNG "ThreadingPrimeNumberScreenShot")  
  
 Questa semplice applicazione conta verso l'alto a partire da tre, cercando i numeri primi. Quando l'utente sceglie il **avviare** pulsante, la ricerca viene avviata. Quando il programma trova un numero primo, aggiorna l'interfaccia utente con il risultato trovato. In qualsiasi momento, l'utente può interrompere la ricerca.  
  
 Anche se è abbastanza semplice, la ricerca di numeri primi potrebbe continuare all'infinito e questo comporta alcune difficoltà.  Se venisse gestita l'intera ricerca all'interno di gestore dell'evento click del pulsante, non avrebbe mai la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] l'opportunità di gestire altri eventi del thread. Il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] sarebbe in grado di rispondere all'input o elaborare i messaggi. L'interfaccia utente non verrebbe mai ridisegnata e i clic sui pulsanti non riceverebbero alcuna risposta.  
  
 È possibile eseguire la ricerca dei numeri primi in un thread separato, ma in questo caso sarebbe necessario affrontare problemi di sincronizzazione. Con un approccio a thread singolo, è possibile aggiornare direttamente l'etichetta che indica il numero primo più grande trovato.  
  
 Scomponendo l'attività di calcolo in blocchi gestibili, è possibile tornare periodicamente al <xref:System.Windows.Threading.Dispatcher> ed elaborare gli eventi. Assegniamo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un'opportunità per ridisegnare l'interfaccia ed elaborare l'input.  
  
 È il modo migliore per dividere il tempo di elaborazione tra calcolo e gestione degli eventi per gestire il calcolo dalla <xref:System.Windows.Threading.Dispatcher>. Tramite il <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> metodo, è possibile pianificare le verifiche dei numeri primi nella stessa coda che [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] provengono gli eventi. Nell'esempio viene pianificato il controllo di un singolo numero primo per volta. Al termine del controllo del numero primo, viene pianificato immediatamente il controllo successivo. Questo controllo continua solo dopo che in sospeso [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] gli eventi sono stati gestiti.  
  
 ![Illustrazione della coda del dispatcher](../../../../docs/framework/wpf/advanced/media/threadingdispatcherqueue.PNG "ThreadingDispatcherQueue")  
  
 [!INCLUDE[TLA#tla_word](../../../../includes/tlasharptla-word-md.md)] esegue il controllo ortografico usando questo meccanismo. Controllo ortografico viene eseguito in background con il tempo di inattività del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread. Di seguito è riportato il codice.  
  
 L'esempio seguente mostra il codice XAML che crea l'interfaccia utente.  
  
 [!code-xaml[ThreadingPrimeNumbers#ThreadingPrimeNumberXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml#threadingprimenumberxaml)]  
  
 L'esempio seguente mostra il code-behind.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumbercodebehind)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumbercodebehind)]  
  
 Nell'esempio seguente mostra il gestore eventi per il <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberStartOrStop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumberstartorstop)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberStartOrStop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumberstartorstop)]  
  
 Oltre ad aggiornare il testo sul <xref:System.Windows.Controls.Button>, questo gestore è responsabile della pianificazione il primo controllo dei numeri primi tramite l'aggiunta di un delegato per il <xref:System.Windows.Threading.Dispatcher> coda. Dopo che questo gestore eventi ha completato l'elaborazione, a volte il <xref:System.Windows.Threading.Dispatcher> seleziona il delegato per l'esecuzione.  
  
 Come accennato in precedenza <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> è il <xref:System.Windows.Threading.Dispatcher> membro usato per pianificare un delegato per l'esecuzione. In questo caso, scegliamo la <xref:System.Windows.Threading.DispatcherPriority.SystemIdle> priorità. Il <xref:System.Windows.Threading.Dispatcher> esegue questo delegato solo quando non sono presenti eventi importanti per l'elaborazione. La velocità di risposta dell'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] è più importante del controllo dei numeri. Viene anche passato un nuovo delegato che rappresenta la routine di controllo dei numeri.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberCheckNextNumber](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumberchecknextnumber)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberCheckNextNumber](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumberchecknextnumber)]  
  
 Questo metodo controlla se il numero dispari successivo è un numero primo. Se si tratta di un numero primo, il metodo aggiorna direttamente la `bigPrime` <xref:System.Windows.Controls.TextBlock> per visualizzare il risultato. Ciò è possibile perché il calcolo viene eseguito nello stesso thread usato per creare il componente. Se avessimo scelto di utilizzare un thread separato per il calcolo, avremmo usare un meccanismo di sincronizzazione più complesso ed eseguire l'aggiornamento nel [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread. Questa situazione verrà illustrata più avanti.  
  
 Per il codice sorgente completo per questo esempio, vedere il [applicazione Single-Threaded con calcolo a esecuzione prolungata](https://go.microsoft.com/fwlink/?LinkID=160038)  
  
<a name="weather_sim"></a>   
### <a name="handling-a-blocking-operation-with-a-background-thread"></a>Gestione di un'operazione di blocco con un thread in background  
 La gestione delle operazioni di blocco in un'applicazione grafica può essere complessa. Non è consigliabile chiamare metodi di blocco dai gestori eventi perché l'applicazione risulterebbe bloccata. È possibile usare un thread separato per gestire queste operazioni, ma al termine, è necessario eseguire la sincronizzazione con il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread perché è possibile modificare direttamente il [!INCLUDE[TLA2#tla_gui](../../../../includes/tla2sharptla-gui-md.md)] dal thread di lavoro. È possibile usare <xref:System.Windows.Threading.Dispatcher.Invoke%2A> oppure <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> per inserire delegati nel <xref:System.Windows.Threading.Dispatcher> del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread. Infine, questi delegati verranno eseguiti con l'autorizzazione per modificare [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementi.  
  
 In questo esempio viene simulata una chiamata RPC (Remote Procedure Call) che recupera i dati delle previsioni meteo. Per eseguire questa chiamata viene utilizzato un thread di lavoro separato e viene pianificato un metodo di aggiornamento nel <xref:System.Windows.Threading.Dispatcher> del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread al termine.  
  
 ![Screenshot dell'interfaccia utente relativa al meteo](../../../../docs/framework/wpf/advanced/media/threadingweatheruiscreenshot.PNG "ThreadingWeatherUIScreenShot")  
  
 [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweathercodebehind)]
 [!code-vb[ThreadingWeatherForecast#ThreadingWeatherCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweathercodebehind)]  
  
 Di seguito sono elencati alcuni dettagli da considerare.  
  
-   Creazione del gestore dei pulsanti  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherButtonHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherbuttonhandler)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherButtonHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherbuttonhandler)]  
  
 Quando si fa clic sul pulsante, viene visualizzato il disegno dell'orologio e viene avviata l'animazione. Il pulsante viene disabilitato. È richiamare la `FetchWeatherFromServer` metodo in un nuovo thread, quindi viene restituito, che consente la <xref:System.Windows.Threading.Dispatcher> per elaborare gli eventi nell'attesa di raccogliere le previsioni meteo.  
  
-   Recupero dei dati meteo  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherFetchWeather](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherfetchweather)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherFetchWeather](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherfetchweather)]  
  
 Per maggiore semplicità, l'esempio non contiene codice di rete. Viene invece simulato il ritardo dell'accesso di rete sospendendo il thread per quattro secondi. In questo momento, originale [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread è ancora in esecuzione e risposta agli eventi. Per illustrare questa situazione, viene lasciata in esecuzione un'animazione e i pulsanti di riduzione a icona e ingrandimento continuano a funzionare.  
  
 Quando è terminato il ritardo e abbiamo selezionato la nostra previsione meteo casuale, è possibile segnalare al [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread. Tale scopo, la pianificazione di una chiamata a `UpdateUserInterface` nella [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread usando tale thread <xref:System.Windows.Threading.Dispatcher>. Viene passata una stringa che descrive le condizioni meteo alla chiamata al metodo pianificata.  
  
-   L'aggiornamento di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherUpdateUI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherupdateui)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherUpdateUI](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherupdateui)]  
  
 Quando la <xref:System.Windows.Threading.Dispatcher> nella [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread dispone di tempo, esegue la chiamata pianificata a `UpdateUserInterface`. Questo metodo interrompe l'animazione dell'orologio e sceglie un'immagine per descrivere le condizioni meteo. L'immagine viene visualizzata e il pulsante "Fetch Forecast" viene ripristinato.  
  
<a name="multi_browser"></a>   
### <a name="multiple-windows-multiple-threads"></a>Più finestre, più thread  
 Alcuni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazioni richiedono più finestre di primo livello. È perfettamente accettabile per un solo Thread /<xref:System.Windows.Threading.Dispatcher> combinazione per gestire più finestre, ma in alcuni casi diversi thread le prestazioni migliori. Ciò è particolarmente vero nel caso in cui ci sia la possibilità che una delle finestre monopolizzi il thread.  
  
 Esplora risorse di [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] funziona in questo modo. Ogni nuova finestra di Esplora risorse appartiene al processo originale, ma viene creata sotto il controllo di un thread indipendente.  
  
 Usando un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Frame> (controllo), è possibile visualizzare le pagine Web. È possibile creare facilmente un semplice [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] sostituire. Si inizia con una funzionalità importante: la possibilità di aprire una nuova finestra. Quando l'utente fa clic sul pulsante "Nuova finestra", viene aperta una copia della finestra in un thread separato. In questo modo, le operazioni a esecuzione prolungata o di blocco in una delle finestre non bloccheranno tutte le altre finestre.  
  
 In realtà, il modello di browser Web ha un proprio modello di threading complesso. È stato scelto questo esempio perché dovrebbe risultare familiare alla maggior parte dei lettori.  
  
 L'esempio seguente mostra il codice.  
  
 [!code-xaml[ThreadingMultipleBrowsers#ThreadingMultiBrowserXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml#threadingmultibrowserxaml)]  
  
 [!code-csharp[ThreadingMultipleBrowsers#ThreadingMultiBrowserCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml.cs#threadingmultibrowsercodebehind)]
 [!code-vb[ThreadingMultipleBrowsers#ThreadingMultiBrowserCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingMultipleBrowsers/VisualBasic/Window1.xaml.vb#threadingmultibrowsercodebehind)]  
  
 I segmenti di threading seguenti del codice sono i più interessanti in questo contesto:  
  
 [!code-csharp[ThreadingMultipleBrowsers#ThreadingMultiBrowserNewWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml.cs#threadingmultibrowsernewwindow)]
 [!code-vb[ThreadingMultipleBrowsers#ThreadingMultiBrowserNewWindow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingMultipleBrowsers/VisualBasic/Window1.xaml.vb#threadingmultibrowsernewwindow)]  
  
 Questo metodo viene chiamato quando si fa clic sul pulsante "Nuova finestra". Il metodo crea un nuovo thread e lo avvia in modo asincrono.  
  
 [!code-csharp[ThreadingMultipleBrowsers#ThreadingMultiBrowserThreadStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml.cs#threadingmultibrowserthreadstart)]
 [!code-vb[ThreadingMultipleBrowsers#ThreadingMultiBrowserThreadStart](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingMultipleBrowsers/VisualBasic/Window1.xaml.vb#threadingmultibrowserthreadstart)]  
  
 Questo metodo è il punto di partenza per il nuovo thread. Viene creata una nuova finestra sotto il controllo di questo thread. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Crea automaticamente un nuovo <xref:System.Windows.Threading.Dispatcher> per gestire il nuovo thread. Per rendere funzionale la finestra è necessario avviare il <xref:System.Windows.Threading.Dispatcher>.  
  
<a name="stumbling_points"></a>   
## <a name="technical-details-and-stumbling-points"></a>Dettagli tecnici e difficoltà  
  
### <a name="writing-components-using-threading"></a>Scrittura di componenti usando il threading  
 Manuale dello sviluppatore di Microsoft .NET Framework descrive un modello al quale un componente può esporre il comportamento asincrono ai relativi client (vedere [Event-based Asynchronous Pattern Overview](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)). Ad esempio, supponiamo di voler creare un pacchetto di `FetchWeatherFromServer` metodo in un componente riutilizzabile non grafico. In seguito il modello standard di Microsoft .NET Framework, questo avrebbe un aspetto simile al seguente.  
  
 [!code-csharp[CommandingOverviewSnippets#ThreadingArticleWeatherComponent1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#threadingarticleweathercomponent1)]
 [!code-vb[CommandingOverviewSnippets#ThreadingArticleWeatherComponent1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#threadingarticleweathercomponent1)]  
  
 `GetWeatherAsync` userebbe una delle tecniche descritte in precedenza, ad esempio la creazione di un thread in background, per eseguire le attività in modo asincrono, senza bloccare il thread chiamante.  
  
 Una delle parti più importanti di questo modello consiste nel chiamare il *NomeMetodo* `Completed` metodo sullo stesso thread che ha chiamato la *MethodName* `Async` cui iniziare. È possibile eseguire questa operazione usando [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] modo piuttosto semplice, archiviando <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A>, ma quindi questo caso il componente può essere usato solo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] delle applicazioni, non nel [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] o [!INCLUDE[TLA#tla_aspnet](../../../../includes/tlasharptla-aspnet-md.md)] programmi.  
  
 Il <xref:System.Windows.Threading.DispatcherSynchronizationContext> classe soddisfa questa esigenza, considerarlo come una versione semplificata del <xref:System.Windows.Threading.Dispatcher> che interagisce con altri [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] anche i Framework.  
  
 [!code-csharp[CommandingOverviewSnippets#ThreadingArticleWeatherComponent2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#threadingarticleweathercomponent2)]
 [!code-vb[CommandingOverviewSnippets#ThreadingArticleWeatherComponent2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#threadingarticleweathercomponent2)]  
  
### <a name="nested-pumping"></a>Distribuzione annidata  
 In alcuni casi non è possibile bloccare completamente il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread. Si prenda ad esempio la <xref:System.Windows.MessageBox.Show%2A> metodo di <xref:System.Windows.MessageBox> classe. <xref:System.Windows.MessageBox.Show%2A> non viene restituita finché l'utente fa clic sul pulsante OK. Crea però una finestra che deve avere un ciclo di messaggi per essere interattiva. Mentre è in attesa del clic dell'utente su OK, la finestra dell'applicazione originale non risponde all'input utente. Continua però a elaborare i messaggi di disegno dell'interfaccia. La finestra originale ridisegna se stessa quando viene coperta e mostrata.  
  
 ![MessageBox con pulsante "OK"](../../../../docs/framework/wpf/advanced/media/threadingnestedpumping.png "ThreadingNestedPumping")  
  
 Un thread deve essere responsabile della finestra di messaggio. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] potrebbe creare un nuovo thread solo per la finestra di messaggio, ma questo thread non sarebbe in grado di disegnare gli elementi disabilitati nella finestra originale (in base a quanto illustrato in precedenza in relazione all'esclusione reciproca). Al contrario, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Usa un sistema di elaborazione dei messaggi annidati. Il <xref:System.Windows.Threading.Dispatcher> classe include un metodo speciale denominato <xref:System.Windows.Threading.Dispatcher.PushFrame%2A>, che archivia il punto di esecuzione corrente di un'applicazione, quindi avvia un nuovo ciclo di messaggi. Al termine del ciclo di messaggi annidati, l'esecuzione riprende dopo l'originale <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> chiamare.  
  
 In questo caso <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> gestisce il contesto del programma alla chiamata a <xref:System.Windows.MessageBox>.<xref:System.Windows.MessageBox.Show%2A>, e avvia un nuovo ciclo di messaggi per ridisegnare la finestra di sfondo e gestire l'input per la finestra di messaggio. Quando l'utente fa clic su OK e cancella la finestra popup, il ciclo annidato viene interrotto e il controllo riprende dopo la chiamata a <xref:System.Windows.MessageBox.Show%2A>.  
  
### <a name="stale-routed-events"></a>Eventi indirizzati non aggiornati  
 Il sistema degli eventi indirizzati in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] notifica all'intero albero quando vengono generati eventi.  
  
 [!code-xaml[InputOvw#ThreadingArticleStaticRoutedEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#threadingarticlestaticroutedevent)]  
  
 Quando viene premuto il pulsante sinistro del mouse sui puntini di sospensione, `handler2` viene eseguita. Dopo aver `handler2` al termine, l'evento viene passata per il <xref:System.Windows.Controls.Canvas> oggetto, che usa `handler1` elaborarlo. Ciò si verifica solo se `handler2` viene non esplicitamente contrassegna l'oggetto evento come gestito.  
  
 È possibile che `handler2` richiederà una notevole quantità di tempo l'elaborazione dell'evento. `handler2` può usare <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> per avviare un ciclo di messaggi annidati che non restituisce risultati per ore. Se `handler2` non contrassegna l'evento come gestito quando questo ciclo di messaggi viene completato, l'evento viene passato l'alto nell'albero anche se molto vecchio.  
  
### <a name="reentrancy-and-locking"></a>Reentrancy e blocco  
 Il meccanismo di blocco del [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] non si comporta esattamente come si potrebbe pensare, ci si aspetterebbe interrompa completamente quando viene richiesto un blocco di un thread. In realtà, il thread continua a ricevere ed elaborare i messaggi con priorità alta. Questo consente di evitare i deadlock e rendere le interfacce un minimo reattive, ma introduce la possibilità di bug.  La maggior parte dei casi non occorre conoscere questo aspetto, ma in casi rari (in genere con [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] i messaggi della finestra o componenti COM STA) può essere utile esserne a conoscenza.  
  
 La maggior parte delle interfacce non compilate con thread-safe presente perché gli sviluppatori si basano sul presupposto che un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] non possano accedere più thread. In questo caso, che singolo thread può apportare eventuali modifiche ambientali in momenti imprevisti, causando tali mal gli effetti di <xref:System.Windows.Threading.DispatcherObject> meccanismo di esclusione reciproca dovrebbe per risolvere. Si consideri lo pseudocodice seguente:  
  
 ![Diagramma della reentrancy del threading](../../../../docs/framework/wpf/advanced/media/threadingreentrancy.png "ThreadingReentrancy")  
  
 La maggior parte dei casi che è la cosa giusta, ma vi sono casi in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in cui tali reentrancy imprevista può causare problemi. In questo caso, determinati momenti, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] chiamate <xref:System.Windows.Threading.Dispatcher.DisableProcessing%2A>, che viene modificato l'istruzione di blocco per il thread da utilizzare il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] blocco senza reentrancy invece del solito [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] blocco.  
  
 Perché è stata la [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] team scegliere questo comportamento? La scelta ha a che fare con gli oggetti COM STA e il thread di finalizzazione. Quando un oggetto viene sottoposto a garbage collection, relativi `Finalize` metodo viene eseguito sul thread finalizzatore dedicato, non il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread. E al suo interno si trova il problema, perché un oggetto STA COM che è stato creato il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread può essere eliminato solo nel [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread. Il [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] esegue l'equivalente di un <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> (in questo caso utilizza di Win32 `SendMessage`). Se tuttavia il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread è occupato, il thread finalizzatore si blocca e l'oggetto COM STA non può essere eliminato, che consente di creare una perdita di memoria gravi. Pertanto la [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] team eseguito la chiamata necessaria per rendere i blocchi funzionano in modo affermativo.  
  
 L'attività per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consiste nell'evitare la reentrancy imprevista senza reintrodurre la perdita di memoria, motivo per cui è non bloccano reentrancy ovunque.  
  
## <a name="see-also"></a>Vedere anche
- [Esempio di applicazione a thread singolo con calcolo a esecuzione prolungata](https://go.microsoft.com/fwlink/?LinkID=160038)
