---
title: Modello di threading
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "33"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f598cecef2d0994692f197df09e9befc39a58723
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="threading-model"></a>Modello di threading
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] è stato progettato per semplificare il threading. Di conseguenza, la maggior parte dei [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gli sviluppatori non sono necessario scrivere un'interfaccia che utilizza più di un thread. Poiché i programmi con multithreading sono complessi ed è difficile eseguirne il debug, è preferibile evitarli quando sono disponibili soluzioni a thread singolo.  
  
 Nessun indipendentemente dall'architettura, tuttavia, non [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] framework sarà mai in grado di fornire una soluzione a thread singolo per ogni tipo di problema. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]si avvicina, ma sono ancora presenti situazioni in cui più thread migliorano [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] delle prestazioni di velocità di risposta o l'applicazione. Dopo aver illustrato alcune nozioni di base, questo documento analizza alcune di queste situazioni per concludere con la descrizione di alcuni aspetti più in dettaglio.  
  

  
> [!NOTE]
>  Questo argomento viene illustrato il threading con il <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> metodo per le chiamate asincrone. È anche possibile effettuare chiamate asincrone chiamando il <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A> (metodo), che prendono un <xref:System.Action> o <xref:System.Func%601> come parametro.  Il <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A> metodo restituisce un <xref:System.Windows.Threading.DispatcherOperation> o <xref:System.Windows.Threading.DispatcherOperation%601>, che presenta un <xref:System.Windows.Threading.DispatcherOperation.Task%2A> proprietà. È possibile utilizzare il `await` (parola chiave) con il <xref:System.Windows.Threading.DispatcherOperation> o associato <xref:System.Threading.Tasks.Task>. Se è necessario attendere in modo sincrono il <xref:System.Threading.Tasks.Task> restituito da un <xref:System.Windows.Threading.DispatcherOperation> o <xref:System.Windows.Threading.DispatcherOperation%601>, chiamare il <xref:System.Windows.Threading.TaskExtensions.DispatcherOperationWait%2A> metodo di estensione.  La chiamata <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> comporterà un deadlock. Per ulteriori informazioni sull'utilizzo di un <xref:System.Threading.Tasks.Task> per eseguire operazioni asincrone, vedere parallelismo delle attività.  Il <xref:System.Windows.Threading.Dispatcher.Invoke%2A> dispone inoltre di overload che accettano un <xref:System.Action> o <xref:System.Func%601> come parametro.  È possibile utilizzare il <xref:System.Windows.Threading.Dispatcher.Invoke%2A> metodo per rendere sincroni chiama passando un delegato, <xref:System.Action> o <xref:System.Func%601>.  
  
<a name="threading_overview"></a>   
## <a name="overview-and-the-dispatcher"></a>Panoramica e dispatcher  
 In genere, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazioni avviate con due thread: uno per la gestione per il rendering e l'altro per la gestione di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Il thread di rendering in modo efficace viene eseguito in background durante il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread riceve l'input, gestisce gli eventi, aggiorna la visualizzazione sullo schermo e viene eseguito il codice dell'applicazione. La maggior parte delle applicazioni di utilizzare un singolo [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread, sebbene in alcune situazioni è consigliabile utilizzare più. Questo aspetto verrà spiegato più avanti con un esempio.  
  
 Il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread accoda elementi di lavoro in un oggetto denominato un <xref:System.Windows.Threading.Dispatcher>. L'oggetto <xref:System.Windows.Threading.Dispatcher> seleziona gli elementi di lavoro in base alla priorità ed esegue ciascuno fino al completamento.  Ogni [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread deve essere presente almeno un <xref:System.Windows.Threading.Dispatcher>e ogni <xref:System.Windows.Threading.Dispatcher> possono eseguire gli elementi di lavoro in un solo thread.  
  
 È la soluzione per compilare applicazioni reattive e intuitiva per ottimizzare il <xref:System.Windows.Threading.Dispatcher> velocità effettiva mantenendo gli elementi di lavoro piccola. In questo modo, gli elementi non rimarranno mai <xref:System.Windows.Threading.Dispatcher> coda in attesa di elaborazione. Qualsiasi ritardo percepibile tra input e risposta può causare frustrazione in un utente.  
  
 Come si sono [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] deve per gestire operazioni più complesse applicazioni? Cosa è necessario fare se il codice prevede calcoli complessi o l'esecuzione di query su un database in un server remoto? In genere, la risposta è per la gestione dell'operazione in un thread separato, lasciando il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread libero di tendono a elementi di <xref:System.Windows.Threading.Dispatcher> coda. Al termine dell'operazione, è possibile segnalare il risultato al [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread per la visualizzazione.  
  
 In passato, [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] consente [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementi può accedere solo dal thread che li ha creati. Ciò significava che un thread in background responsabile di un'attività a esecuzione prolungata non poteva aggiornare una casella di testo dopo il suo completamento. [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]ha lo scopo di garantire l'integrità di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] componenti. Una casella di riepilogo può apparire strana se il relativo contenuto viene aggiornato da un thread in background mentre viene disegnata.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] include un meccanismo predefinito di esclusione reciproca che impone questo coordinamento. La maggior parte delle classi in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] derivano da <xref:System.Windows.Threading.DispatcherObject>. In fase di costruzione, un <xref:System.Windows.Threading.DispatcherObject> archivia un riferimento di <xref:System.Windows.Threading.Dispatcher> collegato al thread attualmente in esecuzione. In effetti, il <xref:System.Windows.Threading.DispatcherObject> associato al thread che l'ha creato. Durante l'esecuzione del programma, un <xref:System.Windows.Threading.DispatcherObject> può chiamare pubblici <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> metodo. <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A>esamina la <xref:System.Windows.Threading.Dispatcher> associata al thread corrente e confrontato con il <xref:System.Windows.Threading.Dispatcher> riferimento archiviato durante la costruzione. Se non corrispondono, <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> genera un'eccezione. <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A>può essere chiamato all'inizio di ogni metodo appartenente a un <xref:System.Windows.Threading.DispatcherObject>.  
  
 Se solo un thread può modificare il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], come interagiscono con l'utente i thread in background? Un thread in background può chiedere il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread per eseguire un'operazione per suo conto. A tale scopo, la registrazione di un elemento di lavoro con la <xref:System.Windows.Threading.Dispatcher> del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread. Il <xref:System.Windows.Threading.Dispatcher> classe fornisce due metodi per la registrazione degli elementi di lavoro: <xref:System.Windows.Threading.Dispatcher.Invoke%2A> e <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>. Entrambi i metodi pianificano un delegato per l'esecuzione. <xref:System.Windows.Threading.Dispatcher.Invoke%2A>una chiamata sincrona, ovvero non restituisce fino a quando il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread non termina l'esecuzione del delegato. <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>è asincrona e restituisce immediatamente.  
  
 Il <xref:System.Windows.Threading.Dispatcher> Ordina gli elementi nella coda in base alla priorità. Sono disponibili dieci livelli che possono essere specificati quando si aggiunge un elemento di <xref:System.Windows.Threading.Dispatcher> coda. Tali priorità vengono mantenute nel <xref:System.Windows.Threading.DispatcherPriority> enumerazione. Informazioni dettagliate sui <xref:System.Windows.Threading.DispatcherPriority> livelli sono reperibili il [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)] documentazione.  
  
<a name="samples"></a>   
## <a name="threads-in-action-the-samples"></a>Thread in azione: esempi  
  
<a name="prime_number"></a>   
### <a name="a-single-threaded-application-with-a-long-running-calculation"></a>Applicazione a thread singolo con calcolo a esecuzione prolungata  
 La maggior parte delle [!INCLUDE[TLA#tla_gui#plural](../../../../includes/tlasharptla-guisharpplural-md.md)] spesa gran parte del proprio tempo di inattività durante l'attesa di eventi che vengono generati in risposta alle interazioni dell'utente. Con un'attenta programmazione questo tempo di inattività può essere usato modo costruttivo, senza influire sulla velocità di risposta del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] modello di threading non consente l'input interrompere un'operazione in corso nel [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread. Ciò significa che sarà necessario ripristinare il <xref:System.Windows.Threading.Dispatcher> periodicamente al processo in attesa di eventi di input prima di ottenere non aggiornati.  
  
 Si consideri l'esempio seguente:  
  
 ![Screenshot relativo ai numeri primi](../../../../docs/framework/wpf/advanced/media/threadingprimenumberscreenshot.PNG "ThreadingPrimeNumberScreenShot")  
  
 Questa semplice applicazione conta verso l'alto a partire da tre, cercando i numeri primi. Quando l'utente sceglie il **avviare** pulsante, la ricerca ha inizio. Quando il programma trova un numero primo, aggiorna l'interfaccia utente con il risultato trovato. In qualsiasi momento, l'utente può interrompere la ricerca.  
  
 Anche se è abbastanza semplice, la ricerca di numeri primi potrebbe continuare all'infinito e questo comporta alcune difficoltà.  Se l'intera ricerca all'interno dell'evento Click del pulsante è gestita, non si sarà mai il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] l'opportunità di gestire gli eventi di altri thread. Il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] sarebbero in grado di rispondere all'input o elaborare i messaggi. L'interfaccia utente non verrebbe mai ridisegnata e i clic sui pulsanti non riceverebbero alcuna risposta.  
  
 È possibile eseguire la ricerca dei numeri primi in un thread separato, ma in questo caso sarebbe necessario affrontare problemi di sincronizzazione. Con un approccio a thread singolo, è possibile aggiornare direttamente l'etichetta che indica il numero primo più grande trovato.  
  
 Scomponendo l'attività di calcolo in blocchi gestibili, è possibile tornare periodicamente per il <xref:System.Windows.Threading.Dispatcher> ed elaborare gli eventi. In questo modo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] opportunità di aggiornare la visualizzazione e di elaborare l'input.  
  
 È il modo migliore per dividere il tempo di elaborazione tra calcolo e la gestione degli eventi per gestire il calcolo dal <xref:System.Windows.Threading.Dispatcher>. Tramite il <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> (metodo), è possibile pianificare le verifiche di numeri primi in quella coda che [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] provengono gli eventi. Nell'esempio viene pianificato il controllo di un singolo numero primo per volta. Al termine del controllo del numero primo, viene pianificato immediatamente il controllo successivo. La ricerca procede solo dopo aver sospeso [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] eventi sono stati gestiti.  
  
 ![Illustrazione della coda del dispatcher](../../../../docs/framework/wpf/advanced/media/threadingdispatcherqueue.PNG "ThreadingDispatcherQueue")  
  
 [!INCLUDE[TLA#tla_word](../../../../includes/tlasharptla-word-md.md)] esegue il controllo ortografico usando questo meccanismo. Il controllo ortografico viene eseguito in background con il tempo di inattività di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread. Di seguito è riportato il codice.  
  
 L'esempio seguente mostra il codice XAML che crea l'interfaccia utente.  
  
 [!code-xaml[ThreadingPrimeNumbers#ThreadingPrimeNumberXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml#threadingprimenumberxaml)]  
  
 L'esempio seguente mostra il code-behind.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumbercodebehind)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumbercodebehind)]  
  
 Nell'esempio seguente viene illustrato il gestore eventi per il <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberStartOrStop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumberstartorstop)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberStartOrStop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumberstartorstop)]  
  
 Oltre ad aggiornare il testo sul <xref:System.Windows.Controls.Button>, questo gestore è responsabile della pianificazione il primo controllo per i numeri primi tramite l'aggiunta di un delegato per il <xref:System.Windows.Threading.Dispatcher> coda. Talvolta al termine delle operazioni, questo gestore eventi di <xref:System.Windows.Threading.Dispatcher> selezionerà il delegato per l'esecuzione.  
  
 Come menzionato in precedenza, <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> è il <xref:System.Windows.Threading.Dispatcher> membro usato per pianificare un delegato per l'esecuzione. In questo caso, viene scelta la <xref:System.Windows.Threading.DispatcherPriority.SystemIdle> priorità. Il <xref:System.Windows.Threading.Dispatcher> il delegato verrà eseguito solo quando non sono presenti eventi importanti per l'elaborazione. La velocità di risposta dell'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] è più importante del controllo dei numeri. Viene anche passato un nuovo delegato che rappresenta la routine di controllo dei numeri.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberCheckNextNumber](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumberchecknextnumber)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberCheckNextNumber](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumberchecknextnumber)]  
  
 Questo metodo controlla se il numero dispari successivo è un numero primo. Se è un numero primo, il metodo aggiorna direttamente il `bigPrime` <xref:System.Windows.Controls.TextBlock> di conseguenza. Ciò è possibile perché il calcolo viene eseguito nello stesso thread usato per creare il componente. Se avessimo utilizzare un thread separato per il calcolo, è sarebbe stato necessario utilizzare un meccanismo di sincronizzazione più complesso ed eseguire l'aggiornamento nel [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread. Questa situazione verrà illustrata più avanti.  
  
 Per il codice sorgente completo per questo esempio, vedere il [applicazione Single-Threaded con esempio di calcolo a esecuzione prolungata](http://go.microsoft.com/fwlink/?LinkID=160038)  
  
<a name="weather_sim"></a>   
### <a name="handling-a-blocking-operation-with-a-background-thread"></a>Gestione di un'operazione di blocco con un thread in background  
 La gestione delle operazioni di blocco in un'applicazione grafica può essere complessa. Non è consigliabile chiamare metodi di blocco dai gestori eventi perché l'applicazione risulterebbe bloccata. È possibile utilizzare un thread separato per gestire queste operazioni, ma al termine, è necessario eseguire la sincronizzazione con il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread poiché è possibile modificare direttamente il [!INCLUDE[TLA2#tla_gui](../../../../includes/tla2sharptla-gui-md.md)] dal thread di lavoro. È possibile utilizzare <xref:System.Windows.Threading.Dispatcher.Invoke%2A> o <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> per inserire delegati nel <xref:System.Windows.Threading.Dispatcher> del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread. Infine, verranno eseguiti con l'autorizzazione per modificare questi delegati [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementi.  
  
 In questo esempio viene simulata una chiamata RPC (Remote Procedure Call) che recupera i dati delle previsioni meteo. Viene utilizzato un thread di lavoro distinti per eseguire questa chiamata e viene pianificato un metodo di aggiornamento nel <xref:System.Windows.Threading.Dispatcher> del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] al termine del thread.  
  
 ![Screenshot dell'interfaccia utente relativa al meteo](../../../../docs/framework/wpf/advanced/media/threadingweatheruiscreenshot.PNG "ThreadingWeatherUIScreenShot")  
  
 [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweathercodebehind)]
 [!code-vb[ThreadingWeatherForecast#ThreadingWeatherCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweathercodebehind)]  
  
 Di seguito sono elencati alcuni dettagli da considerare.  
  
-   Creazione del gestore dei pulsanti  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherButtonHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherbuttonhandler)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherButtonHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherbuttonhandler)]  
  
 Quando si fa clic sul pulsante, viene visualizzato il disegno dell'orologio e viene avviata l'animazione. Il pulsante viene disabilitato. Viene chiamato il `FetchWeatherFromServer` metodo in un nuovo thread e viene quindi restituito, che consente il <xref:System.Windows.Threading.Dispatcher> per elaborare gli eventi durante l'attesa di raccogliere le previsioni meteorologiche.  
  
-   Recupero dei dati meteo  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherFetchWeather](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherfetchweather)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherFetchWeather](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherfetchweather)]  
  
 Per maggiore semplicità, l'esempio non contiene codice di rete. Viene invece simulato il ritardo dell'accesso di rete sospendendo il thread per quattro secondi. In questo periodo, originale [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread è ancora in esecuzione e risponde agli eventi. Per illustrare questa situazione, viene lasciata in esecuzione un'animazione e i pulsanti di riduzione a icona e ingrandimento continuano a funzionare.  
  
 Al termine il ritardo, e sono state selezionate in modo casuale le previsioni meteo, è necessario segnalare per il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread. Questa operazione viene effettuata una chiamata a pianificazione `UpdateUserInterface` nel [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread mediante tale thread <xref:System.Windows.Threading.Dispatcher>. Viene passata una stringa che descrive le condizioni meteo alla chiamata al metodo pianificata.  
  
-   L'aggiornamento di[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherUpdateUI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherupdateui)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherUpdateUI](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherupdateui)]  
  
 Quando il <xref:System.Windows.Threading.Dispatcher> nel [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread dispone di tempo, viene eseguita la chiamata pianificata a `UpdateUserInterface`. Questo metodo interrompe l'animazione dell'orologio e sceglie un'immagine per descrivere le condizioni meteo. L'immagine viene visualizzata e il pulsante "Fetch Forecast" viene ripristinato.  
  
<a name="multi_browser"></a>   
### <a name="multiple-windows-multiple-threads"></a>Più finestre, più thread  
 Alcuni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazioni richiedono più finestre di primo livello. È perfettamente accettabile per un Thread /<xref:System.Windows.Threading.Dispatcher> combinazione per gestire più finestre, ma talvolta più thread rappresentano una soluzione più efficiente. Ciò è particolarmente vero nel caso in cui ci sia la possibilità che una delle finestre monopolizzi il thread.  
  
 Esplora risorse di [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] funziona in questo modo. Ogni nuova finestra di Esplora risorse appartiene al processo originale, ma viene creata sotto il controllo di un thread indipendente.  
  
 Utilizzando un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Frame> (controllo), è possibile visualizzare le pagine Web. È possibile creare facilmente un semplice [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] sostituire. Si inizia con una funzionalità importante: la possibilità di aprire una nuova finestra. Quando l'utente fa clic sul pulsante "Nuova finestra", viene aperta una copia della finestra in un thread separato. In questo modo, le operazioni a esecuzione prolungata o di blocco in una delle finestre non bloccheranno tutte le altre finestre.  
  
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
  
 Questo metodo è il punto di partenza per il nuovo thread. Viene creata una nuova finestra sotto il controllo di questo thread. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Crea automaticamente un nuovo <xref:System.Windows.Threading.Dispatcher> per gestire il nuovo thread. Per rendere funzionale la finestra è necessario avviare il <xref:System.Windows.Threading.Dispatcher>.  
  
<a name="stumbling_points"></a>   
## <a name="technical-details-and-stumbling-points"></a>Dettagli tecnici e difficoltà  
  
### <a name="writing-components-using-threading"></a>Scrittura di componenti usando il threading  
 Il [!INCLUDE[TLA#tla_netframewk](../../../../includes/tlasharptla-netframewk-md.md)] Guida per gli sviluppatori descrive un modello al quale un componente può esporre il comportamento asincrono ai propri client (vedere [Panoramica del modello asincrono basato su eventi](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)). Ad esempio, di voler creare un pacchetto di `FetchWeatherFromServer` metodo in un componente riutilizzabile e non grafico. Segue lo standard [!INCLUDE[TLA#tla_netframewk](../../../../includes/tlasharptla-netframewk-md.md)] modello, questo avrà un aspetto simile al seguente.  
  
 [!code-csharp[CommandingOverviewSnippets#ThreadingArticleWeatherComponent1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#threadingarticleweathercomponent1)]
 [!code-vb[CommandingOverviewSnippets#ThreadingArticleWeatherComponent1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#threadingarticleweathercomponent1)]  
  
 `GetWeatherAsync` userebbe una delle tecniche descritte in precedenza, ad esempio la creazione di un thread in background, per eseguire le attività in modo asincrono, senza bloccare il thread chiamante.  
  
 Una delle parti più importanti di questo modello consiste nel chiamare il *NomeMetodo* `Completed` metodo sullo stesso thread che ha chiamato la *NomeMetodo* `Async` metodo per iniziare. È possibile eseguire questa operazione usando [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] piuttosto semplice, archiviando <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A>, ma quindi questo componente può essere usato solo in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazioni, non in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] o [!INCLUDE[TLA#tla_aspnet](../../../../includes/tlasharptla-aspnet-md.md)] programmi.  
  
 Il <xref:System.Windows.Threading.DispatcherSynchronizationContext> classe risolve questa esigenza, considerarlo come una versione semplificata di <xref:System.Windows.Threading.Dispatcher> che interagisce con altri [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] nonché Framework.  
  
 [!code-csharp[CommandingOverviewSnippets#ThreadingArticleWeatherComponent2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#threadingarticleweathercomponent2)]
 [!code-vb[CommandingOverviewSnippets#ThreadingArticleWeatherComponent2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#threadingarticleweathercomponent2)]  
  
### <a name="nested-pumping"></a>Distribuzione annidata  
 In alcuni casi non è fattibile bloccare completamente il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread. Si consideri il <xref:System.Windows.MessageBox.Show%2A> metodo la <xref:System.Windows.MessageBox> classe. <xref:System.Windows.MessageBox.Show%2A>non restituisce fino a quando l'utente fa clic sul pulsante OK. Crea però una finestra che deve avere un ciclo di messaggi per essere interattiva. Mentre è in attesa del clic dell'utente su OK, la finestra dell'applicazione originale non risponde all'input utente. Continua però a elaborare i messaggi di disegno dell'interfaccia. La finestra originale ridisegna se stessa quando viene coperta e mostrata.  
  
 ![MessageBox con pulsante "OK"](../../../../docs/framework/wpf/advanced/media/threadingnestedpumping.png "ThreadingNestedPumping")  
  
 Un thread deve essere responsabile della finestra di messaggio. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] potrebbe creare un nuovo thread solo per la finestra di messaggio, ma questo thread non sarebbe in grado di disegnare gli elementi disabilitati nella finestra originale (in base a quanto illustrato in precedenza in relazione all'esclusione reciproca). In alternativa, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utilizza un messaggio annidato di sistema di elaborazione. Il <xref:System.Windows.Threading.Dispatcher> classe include un metodo speciale denominato <xref:System.Windows.Threading.Dispatcher.PushFrame%2A>, che archivia il punto di esecuzione corrente di un'applicazione, quindi avvia un nuovo ciclo di messaggi. Al termine del ciclo di messaggi annidati, l'esecuzione riprende dopo originale <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> chiamare.  
  
 In questo caso, <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> mantiene il contesto di programma alla chiamata a <xref:System.Windows.MessageBox>.<xref:System.Windows.MessageBox.Show%2A>, e viene avviato un nuovo ciclo di messaggi per ridisegnare la finestra di sfondo e gestire l'input per la finestra di messaggio. Quando l'utente fa clic su OK e cancella la finestra popup, il ciclo annidato viene interrotto e il controllo riprende dopo la chiamata a <xref:System.Windows.MessageBox.Show%2A>.  
  
### <a name="stale-routed-events"></a>Eventi indirizzati non aggiornati  
 Il sistema di eventi indirizzati [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] notifica intere strutture ad albero quando vengono generati eventi.  
  
 [!code-xaml[InputOvw#ThreadingArticleStaticRoutedEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#threadingarticlestaticroutedevent)]  
  
 Quando viene premuto il pulsante sinistro del mouse sui puntini di sospensione, `handler2` viene eseguita. Dopo aver `handler2` al termine, l'evento viene passato al <xref:System.Windows.Controls.Canvas> oggetto, che utilizza `handler1` per elaborarlo. Ciò si verifica solo se `handler2` non in modo non esplicito contrassegna l'evento oggetto come gestito.  
  
 È possibile che `handler2` richiederà una notevole quantità di tempo di elaborazione di questo evento. `handler2`potrebbe utilizzare <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> per avviare un ciclo di messaggi annidati che non restituisce per ore. Se `handler2` non contrassegna l'evento come gestito quando questo ciclo di messaggi è completata, l'evento viene passato alla struttura ad albero, sebbene sia molto obsoleto.  
  
### <a name="reentrancy-and-locking"></a>Reentrancy e blocco  
 Il meccanismo di blocco di [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] non funzionano esattamente come prevedibile, ci si aspetterebbe annullare l'operazione completamente quando viene richiesto un blocco di un thread. In realtà, il thread continua a ricevere ed elaborare i messaggi con priorità alta. Questo consente di evitare i deadlock e rendere le interfacce un minimo reattive, ma introduce la possibilità di bug.  La maggior parte dei casi non è necessario conoscere il linguaggio su questo argomento, ma in rare circostanze (in genere [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] i messaggi della finestra o componenti COM STA) può essere molto utili.  
  
 La maggior parte delle interfacce non compilate con presente la sicurezza dei thread perché gli sviluppatori si basano sul presupposto che un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] non possano accedere più thread. In questo caso, che un thread singolo può apportare modifiche ambientali in momenti imprevisti, causando tali valido gli effetti di <xref:System.Windows.Threading.DispatcherObject> meccanismo di esclusione reciproca dovrebbe per risolvere. Si consideri lo pseudocodice seguente:  
  
 ![Diagramma della reentrancy del threading](../../../../docs/framework/wpf/advanced/media/threadingreentrancy.png "ThreadingReentrancy")  
  
 La maggior parte dei casi è giusto, ma vi sono casi in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in tali reentrancy imprevista può causare problemi. In questo caso, in determinati momenti chiave, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] chiamate <xref:System.Windows.Threading.Dispatcher.DisableProcessing%2A>, che modifica l'istruzione di blocco per il thread da utilizzare il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] blocco senza reentrancy, anziché le consuete [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] blocco.  
  
 Perché ha il [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] team scegliere questo comportamento? La scelta ha a che fare con gli oggetti COM STA e il thread di finalizzazione. Quando un oggetto viene sottoposto a garbage collection, il relativo `Finalize` metodo viene eseguito sul thread del finalizzatore dedicato, non il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread. Al suo interno si trova il problema, perché un oggetto STA COM che è stato creato il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread può essere eliminato solo sul [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread. Il [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] esegue l'equivalente di un <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> (in questo caso utilizzando Win32 `SendMessage`). Se tuttavia il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread è occupato, il thread del finalizzatore è bloccato e non può essere eliminato l'oggetto COM STA, che consente di creare una perdita di memoria gravi. Pertanto la [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] team eseguito la chiamata necessaria per fare in modo che blocchi il modo affermativo.  
  
 L'attività per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consiste nell'evitare reentrancy imprevista senza causare la perdita di memoria, motivo per cui non venga bloccato reentrancy ovunque.  
  
## <a name="see-also"></a>Vedere anche  
 [Esempio di applicazione a thread singolo con calcolo a esecuzione prolungata](http://go.microsoft.com/fwlink/?LinkID=160038)
