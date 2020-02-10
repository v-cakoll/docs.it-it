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
ms.openlocfilehash: 87dcfa22bcce730c5a9b61721c3a846a08146475
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094501"
---
# <a name="threading-model"></a>Modello di threading
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] è stato progettato per semplificare il threading. Di conseguenza, la maggior parte dei [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sviluppatori non dovranno scrivere un'interfaccia che usa più di un thread. Poiché i programmi con multithreading sono complessi ed è difficile eseguirne il debug, è preferibile evitarli quando sono disponibili soluzioni a thread singolo.

 Indipendentemente da quanto ben progettato, tuttavia, nessun framework di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] sarà in grado di fornire una soluzione a thread singolo per ogni tipo di problema. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] si avvicina, ma esistono ancora situazioni in cui più thread migliorano [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] la velocità di risposta o le prestazioni dell'applicazione. Dopo aver illustrato alcune nozioni di base, questo documento analizza alcune di queste situazioni per concludere con la descrizione di alcuni aspetti più in dettaglio.

> [!NOTE]
> In questo argomento viene illustrato il threading utilizzando il metodo <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> per le chiamate asincrone. È anche possibile effettuare chiamate asincrone chiamando il metodo <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>, che accetta un <xref:System.Action> o <xref:System.Func%601> come parametro.  Il metodo <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A> restituisce un <xref:System.Windows.Threading.DispatcherOperation> o <xref:System.Windows.Threading.DispatcherOperation%601>, che dispone di una proprietà <xref:System.Windows.Threading.DispatcherOperation.Task%2A>. È possibile usare la parola chiave `await` con il <xref:System.Windows.Threading.DispatcherOperation> o il <xref:System.Threading.Tasks.Task>associato. Se è necessario attendere in modo sincrono il <xref:System.Threading.Tasks.Task> restituito da un <xref:System.Windows.Threading.DispatcherOperation> o <xref:System.Windows.Threading.DispatcherOperation%601>, chiamare il metodo di estensione <xref:System.Windows.Threading.TaskExtensions.DispatcherOperationWait%2A>.  La chiamata di <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> comporterà un deadlock. Per ulteriori informazioni sull'utilizzo di un <xref:System.Threading.Tasks.Task> per eseguire operazioni asincrone, vedere Parallelismo delle attività.  Il metodo <xref:System.Windows.Threading.Dispatcher.Invoke%2A> dispone inoltre di overload che accettano un <xref:System.Action> o <xref:System.Func%601> come parametro.  È possibile usare il metodo <xref:System.Windows.Threading.Dispatcher.Invoke%2A> per eseguire chiamate sincrone passando un delegato, <xref:System.Action> o <xref:System.Func%601>.

<a name="threading_overview"></a>
## <a name="overview-and-the-dispatcher"></a>Panoramica e dispatcher
 In genere, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazioni iniziano con due thread: uno per la gestione del rendering e l'altro per la gestione della [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Il thread di rendering viene eseguito in modo efficace nascosto in background mentre il thread [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] riceve input, gestisce gli eventi, disegna lo schermo ed esegue il codice dell'applicazione. La maggior parte delle applicazioni usa un singolo thread di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], anche se in alcune situazioni è preferibile usare diversi. Questo aspetto verrà spiegato più avanti con un esempio.

 Il thread di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Accoda gli elementi di lavoro all'interno di un oggetto denominato <xref:System.Windows.Threading.Dispatcher>. L'oggetto <xref:System.Windows.Threading.Dispatcher> seleziona gli elementi di lavoro in base alla priorità ed esegue ciascuno fino al completamento.  Ogni thread di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] deve avere almeno una <xref:System.Windows.Threading.Dispatcher>e ogni <xref:System.Windows.Threading.Dispatcher> può eseguire elementi di lavoro in un solo thread.

 Il trucco per la creazione di applicazioni reattive e intuitive è ottimizzare la velocità effettiva <xref:System.Windows.Threading.Dispatcher> mantenendo gli elementi di lavoro ridotti. In questo modo gli elementi non vengono mai aggiornati nella coda <xref:System.Windows.Threading.Dispatcher> in attesa di elaborazione. Qualsiasi ritardo percepibile tra input e risposta può causare frustrazione in un utente.

 In che modo le applicazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dovrebbero gestire operazioni di grandi dimensioni? Cosa è necessario fare se il codice prevede calcoli complessi o l'esecuzione di query su un database in un server remoto? In genere, la risposta consiste nel gestire la grande operazione in un thread separato, lasciando il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] thread libero per tendere agli elementi nella coda di <xref:System.Windows.Threading.Dispatcher>. Al termine della grande operazione, può segnalare il risultato al thread [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] per la visualizzazione.

 In passato, Windows consente di accedere agli elementi di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] solo dal thread che li ha creati. Ciò significava che un thread in background responsabile di un'attività a esecuzione prolungata non poteva aggiornare una casella di testo dopo il suo completamento. Questa operazione viene eseguita da Windows per garantire l'integrità dei componenti di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Una casella di riepilogo può apparire strana se il relativo contenuto viene aggiornato da un thread in background mentre viene disegnata.

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] include un meccanismo predefinito di esclusione reciproca che impone questo coordinamento. La maggior parte delle classi in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] deriva da <xref:System.Windows.Threading.DispatcherObject>. In fase di costruzione, un <xref:System.Windows.Threading.DispatcherObject> archivia un riferimento alla <xref:System.Windows.Threading.Dispatcher> collegata al thread attualmente in esecuzione. In effetti, il <xref:System.Windows.Threading.DispatcherObject> associa al thread che la crea. Durante l'esecuzione del programma, un <xref:System.Windows.Threading.DispatcherObject> può chiamare il relativo metodo <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> pubblico. <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> esamina la <xref:System.Windows.Threading.Dispatcher> associata al thread corrente e la confronta con il riferimento <xref:System.Windows.Threading.Dispatcher> archiviato durante la costruzione. Se non corrispondono, <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> genera un'eccezione. <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> deve essere chiamato all'inizio di ogni metodo appartenente a una <xref:System.Windows.Threading.DispatcherObject>.

 Se solo un thread può modificare la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], in che modo i thread in background interagiscono con l'utente? Un thread in background può richiedere al thread [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] di eseguire un'operazione per suo conto. Questa operazione viene eseguita registrando un elemento di lavoro con il <xref:System.Windows.Threading.Dispatcher> del thread di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. La classe <xref:System.Windows.Threading.Dispatcher> fornisce due metodi per la registrazione degli elementi di lavoro: <xref:System.Windows.Threading.Dispatcher.Invoke%2A> e <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>. Entrambi i metodi pianificano un delegato per l'esecuzione. <xref:System.Windows.Threading.Dispatcher.Invoke%2A> è una chiamata sincrona, ovvero non restituisce un risultato fino a quando il thread di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] non completa effettivamente l'esecuzione del delegato. <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> è asincrono e restituisce immediatamente un risultato.

 Il <xref:System.Windows.Threading.Dispatcher> Ordina gli elementi nella coda per priorità. È possibile specificare dieci livelli quando si aggiunge un elemento alla coda <xref:System.Windows.Threading.Dispatcher>. Queste priorità vengono gestite nell'enumerazione <xref:System.Windows.Threading.DispatcherPriority>. Informazioni dettagliate sui livelli di <xref:System.Windows.Threading.DispatcherPriority> sono disponibili nella documentazione di Windows SDK.

<a name="samples"></a>
## <a name="threads-in-action-the-samples"></a>Thread in azione: esempi

<a name="prime_number"></a>
### <a name="a-single-threaded-application-with-a-long-running-calculation"></a>Applicazione a thread singolo con calcolo a esecuzione prolungata
 La maggior parte dell'interfaccia utente grafica (GUI) dedica una grande parte del tempo di inattività durante l'attesa degli eventi generati in risposta alle interazioni dell'utente. Con un'attenta programmazione questo tempo di inattività può essere usato in modo costruttivo, senza influire sulla velocità di risposta del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Il modello di threading [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] non consente all'input di interrompere un'operazione che si verifica nel thread di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Ciò significa che è necessario assicurarsi di tornare al <xref:System.Windows.Threading.Dispatcher> periodicamente per elaborare gli eventi di input in sospeso prima di diventare obsoleti.

 Prendere in considerazione gli esempi seguenti:

 ![Screenshot che mostra il threading dei numeri primi.](./media/threading-model/threading-prime-numbers.png)

 Questa semplice applicazione conta verso l'alto a partire da tre, cercando i numeri primi. Quando l'utente fa clic sul pulsante **Start** , inizia la ricerca. Quando il programma trova un numero primo, aggiorna l'interfaccia utente con il risultato trovato. In qualsiasi momento, l'utente può interrompere la ricerca.

 Anche se è abbastanza semplice, la ricerca di numeri primi potrebbe continuare all'infinito e questo comporta alcune difficoltà.  Se l'intera ricerca è stata gestita all'interno del gestore dell'evento click del pulsante, non si darebbe mai al thread di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] la possibilità di gestire altri eventi. Il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] non sarà in grado di rispondere ai messaggi di input o di elaborazione. L'interfaccia utente non verrebbe mai ridisegnata e i clic sui pulsanti non riceverebbero alcuna risposta.

 È possibile eseguire la ricerca dei numeri primi in un thread separato, ma in questo caso sarebbe necessario affrontare problemi di sincronizzazione. Con un approccio a thread singolo, è possibile aggiornare direttamente l'etichetta che indica il numero primo più grande trovato.

 Se si suddivide l'attività di calcolo in blocchi gestibili, è possibile tornare periodicamente al <xref:System.Windows.Threading.Dispatcher> ed elaborare gli eventi. Possiamo dare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] la possibilità di ridisegnare ed elaborare l'input.

 Il modo migliore per suddividere i tempi di elaborazione tra calcolo e gestione degli eventi consiste nel gestire il calcolo dal <xref:System.Windows.Threading.Dispatcher>. Utilizzando il metodo <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>, è possibile pianificare i controlli dei numeri primi nella stessa coda da cui vengono tracciati [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] eventi. Nell'esempio viene pianificato il controllo di un singolo numero primo per volta. Al termine del controllo del numero primo, viene pianificato immediatamente il controllo successivo. Questo controllo continua solo dopo che sono stati gestiti gli eventi [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] in sospeso.

 ![Screenshot che mostra la coda del dispatcher.](./media/threading-model/threading-dispatcher-queue.png)

 Microsoft Word realizza il controllo ortografico usando questo meccanismo. Il controllo ortografico viene eseguito in background utilizzando il tempo di inattività del thread [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Di seguito è riportato il codice.

 L'esempio seguente mostra il codice XAML che crea l'interfaccia utente.

 [!code-xaml[ThreadingPrimeNumbers#ThreadingPrimeNumberXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml#threadingprimenumberxaml)]

 L'esempio seguente mostra il code-behind.

 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumbercodebehind)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumbercodebehind)]

 Nell'esempio seguente viene illustrato il gestore eventi per la <xref:System.Windows.Controls.Button>.

 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberStartOrStop](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumberstartorstop)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberStartOrStop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumberstartorstop)]

 Oltre ad aggiornare il testo nella <xref:System.Windows.Controls.Button>, questo gestore è responsabile della pianificazione del primo controllo dei numeri primi mediante l'aggiunta di un delegato alla coda di <xref:System.Windows.Threading.Dispatcher>. A questo punto, dopo che il gestore dell'evento ha completato il proprio lavoro, il <xref:System.Windows.Threading.Dispatcher> selezionerà questo delegato per l'esecuzione.

 Come indicato in precedenza, <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> è il membro <xref:System.Windows.Threading.Dispatcher> usato per pianificare un delegato per l'esecuzione. In questo caso, si sceglie la priorità <xref:System.Windows.Threading.DispatcherPriority.SystemIdle>. Il <xref:System.Windows.Threading.Dispatcher> eseguirà questo delegato solo quando non ci sono eventi importanti da elaborare. La velocità di risposta dell'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] è più importante del controllo dei numeri. Viene anche passato un nuovo delegato che rappresenta la routine di controllo dei numeri.

 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberCheckNextNumber](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumberchecknextnumber)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberCheckNextNumber](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumberchecknextnumber)]

 Questo metodo controlla se il numero dispari successivo è un numero primo. Se è primo, il metodo aggiorna direttamente il `bigPrime`<xref:System.Windows.Controls.TextBlock> per rifletterne l'individuazione. Ciò è possibile perché il calcolo viene eseguito nello stesso thread usato per creare il componente. Se avessimo scelto di usare un thread separato per il calcolo, avremmo dovuto usare un meccanismo di sincronizzazione più complicato ed eseguire l'aggiornamento nel thread [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Questa situazione verrà illustrata più avanti.

 Per il codice sorgente completo per questo esempio, vedere l' [esempio di applicazione a thread singolo con calcolo a esecuzione prolungata](https://github.com/Microsoft/WPF-Samples/tree/master/Threading/SingleThreadedApplication)

<a name="weather_sim"></a>
### <a name="handling-a-blocking-operation-with-a-background-thread"></a>Gestione di un'operazione di blocco con un thread in background
 La gestione delle operazioni di blocco in un'applicazione grafica può essere complessa. Non è consigliabile chiamare metodi di blocco dai gestori eventi perché l'applicazione risulterebbe bloccata. È possibile usare un thread separato per gestire queste operazioni, ma al termine è necessario eseguire la sincronizzazione con il thread di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] perché non è possibile modificare direttamente l'interfaccia utente grafica dal thread di lavoro. È possibile utilizzare <xref:System.Windows.Threading.Dispatcher.Invoke%2A> o <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> per inserire delegati nel <xref:System.Windows.Threading.Dispatcher> del thread [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Alla fine, questi delegati verranno eseguiti con l'autorizzazione per modificare [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementi.

 In questo esempio viene simulata una chiamata RPC (Remote Procedure Call) che recupera i dati delle previsioni meteo. Viene usato un thread di lavoro separato per eseguire questa chiamata e si pianifica un metodo di aggiornamento nel <xref:System.Windows.Threading.Dispatcher> del thread [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] al termine dell'operazione.

 ![Screenshot che mostra l'interfaccia utente Meteo.](./media/threading-model/threading-weather-ui.png)

 [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweathercodebehind)]
 [!code-vb[ThreadingWeatherForecast#ThreadingWeatherCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweathercodebehind)]

 Di seguito sono elencati alcuni dettagli da considerare.

- Creazione del gestore dei pulsanti

     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherButtonHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherbuttonhandler)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherButtonHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherbuttonhandler)]

 Quando si fa clic sul pulsante, viene visualizzato il disegno dell'orologio e viene avviata l'animazione. Il pulsante viene disabilitato. Il metodo `FetchWeatherFromServer` viene richiamato in un nuovo thread, quindi viene restituito, consentendo al <xref:System.Windows.Threading.Dispatcher> di elaborare gli eventi mentre si è in attesa di raccogliere le previsioni meteorologiche.

- Recupero dei dati meteo

     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherFetchWeather](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherfetchweather)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherFetchWeather](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherfetchweather)]

 Per maggiore semplicità, l'esempio non contiene codice di rete. Viene invece simulato il ritardo dell'accesso di rete sospendendo il thread per quattro secondi. In questo periodo, il thread di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] originale è ancora in esecuzione e risponde agli eventi. Per illustrare questa situazione, viene lasciata in esecuzione un'animazione e i pulsanti di riduzione a icona e ingrandimento continuano a funzionare.

 Al termine del ritardo e abbiamo selezionato in modo casuale le previsioni meteorologiche, è il momento di riportare al thread [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Questa operazione viene eseguita pianificando una chiamata a `UpdateUserInterface` nel thread [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] utilizzando <xref:System.Windows.Threading.Dispatcher>di tale thread. Viene passata una stringa che descrive le condizioni meteo alla chiamata al metodo pianificata.

- Aggiornamento del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]

     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherUpdateUI](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherupdateui)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherUpdateUI](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherupdateui)]

 Quando il <xref:System.Windows.Threading.Dispatcher> nel thread [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] dispone di tempo, viene eseguita la chiamata pianificata a `UpdateUserInterface`. Questo metodo interrompe l'animazione dell'orologio e sceglie un'immagine per descrivere le condizioni meteo. L'immagine viene visualizzata e il pulsante "Fetch Forecast" viene ripristinato.

<a name="multi_browser"></a>
### <a name="multiple-windows-multiple-threads"></a>Più finestre, più thread
 Alcune applicazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] richiedono più finestre di primo livello. È perfettamente accettabile per una combinazione di thread/<xref:System.Windows.Threading.Dispatcher> gestire più finestre, ma a volte diversi thread offrono un processo migliore. Ciò è particolarmente vero nel caso in cui ci sia la possibilità che una delle finestre monopolizzi il thread.

 Esplora risorse funziona in questo modo. Ogni nuova finestra di Esplora risorse appartiene al processo originale, ma viene creata sotto il controllo di un thread indipendente.

 Utilizzando un controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Frame>, è possibile visualizzare le pagine Web. È possibile creare facilmente un sostituto semplice di Internet Explorer. Si inizia con una funzionalità importante: la possibilità di aprire una nuova finestra. Quando l'utente fa clic sul pulsante "Nuova finestra", viene aperta una copia della finestra in un thread separato. In questo modo, le operazioni a esecuzione prolungata o di blocco in una delle finestre non bloccheranno tutte le altre finestre.

 In realtà, il modello di browser Web ha un proprio modello di threading complesso. È stato scelto questo esempio perché dovrebbe risultare familiare alla maggior parte dei lettori.

 L'esempio seguente mostra il codice.

 [!code-xaml[ThreadingMultipleBrowsers#ThreadingMultiBrowserXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml#threadingmultibrowserxaml)]

 [!code-csharp[ThreadingMultipleBrowsers#ThreadingMultiBrowserCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml.cs#threadingmultibrowsercodebehind)]
 [!code-vb[ThreadingMultipleBrowsers#ThreadingMultiBrowserCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingMultipleBrowsers/VisualBasic/Window1.xaml.vb#threadingmultibrowsercodebehind)]

 I segmenti di threading seguenti del codice sono i più interessanti in questo contesto:

 [!code-csharp[ThreadingMultipleBrowsers#ThreadingMultiBrowserNewWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml.cs#threadingmultibrowsernewwindow)]
 [!code-vb[ThreadingMultipleBrowsers#ThreadingMultiBrowserNewWindow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingMultipleBrowsers/VisualBasic/Window1.xaml.vb#threadingmultibrowsernewwindow)]

 Questo metodo viene chiamato quando si fa clic sul pulsante "Nuova finestra". Il metodo crea un nuovo thread e lo avvia in modo asincrono.

 [!code-csharp[ThreadingMultipleBrowsers#ThreadingMultiBrowserThreadStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml.cs#threadingmultibrowserthreadstart)]
 [!code-vb[ThreadingMultipleBrowsers#ThreadingMultiBrowserThreadStart](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingMultipleBrowsers/VisualBasic/Window1.xaml.vb#threadingmultibrowserthreadstart)]

 Questo metodo è il punto di partenza per il nuovo thread. Viene creata una nuova finestra sotto il controllo di questo thread. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] crea automaticamente una nuova <xref:System.Windows.Threading.Dispatcher> per gestire il nuovo thread. Per rendere funzionale la finestra, è sufficiente avviare il <xref:System.Windows.Threading.Dispatcher>.

<a name="stumbling_points"></a>
## <a name="technical-details-and-stumbling-points"></a>Dettagli tecnici e difficoltà

### <a name="writing-components-using-threading"></a>Scrittura di componenti usando il threading
 La guida per gli sviluppatori di Microsoft .NET Framework descrive un modello per il modo in cui un componente può esporre il comportamento asincrono ai propri client. vedere [Cenni preliminari sul modello asincrono basato su eventi](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md). Si supponga, ad esempio, di voler creare il pacchetto del `FetchWeatherFromServer` metodo in un componente riutilizzabile e non grafico. Seguendo il modello di Microsoft .NET Framework standard, il risultato sarà simile al seguente.

 [!code-csharp[CommandingOverviewSnippets#ThreadingArticleWeatherComponent1](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#threadingarticleweathercomponent1)]
 [!code-vb[CommandingOverviewSnippets#ThreadingArticleWeatherComponent1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#threadingarticleweathercomponent1)]

 `GetWeatherAsync` userebbe una delle tecniche descritte in precedenza, ad esempio la creazione di un thread in background, per eseguire le attività in modo asincrono, senza bloccare il thread chiamante.

 Una delle parti più importanti di questo modello è la chiamata al metodo *methodname*`Completed` sullo stesso thread che ha chiamato il metodo *MethodName*`Async` per iniziare. Questa operazione può essere eseguita in modo abbastanza semplice, archiviando <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A>, ma in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] questo caso il componente non grafico può essere usato solo in applicazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], non nei programmi Windows Forms o ASP.NET.

 La classe <xref:System.Windows.Threading.DispatcherSynchronizationContext> risponde a questa esigenza, ovvero una versione semplificata di <xref:System.Windows.Threading.Dispatcher> che funziona anche con altri [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Framework.

 [!code-csharp[CommandingOverviewSnippets#ThreadingArticleWeatherComponent2](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#threadingarticleweathercomponent2)]
 [!code-vb[CommandingOverviewSnippets#ThreadingArticleWeatherComponent2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#threadingarticleweathercomponent2)]

### <a name="nested-pumping"></a>Distribuzione annidata
 In alcuni casi non è possibile bloccare completamente il thread di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Si prenda in considerazione il metodo <xref:System.Windows.MessageBox.Show%2A> della classe <xref:System.Windows.MessageBox>. <xref:System.Windows.MessageBox.Show%2A> non viene restituito fino a quando l'utente non fa clic sul pulsante OK. Crea però una finestra che deve avere un ciclo di messaggi per essere interattiva. Mentre è in attesa del clic dell'utente su OK, la finestra dell'applicazione originale non risponde all'input utente. Continua però a elaborare i messaggi di disegno dell'interfaccia. La finestra originale ridisegna se stessa quando viene coperta e mostrata.

 ![Screenshot che mostra un MessageBox con un pulsante OK](./media/threading-model/threading-message-loop.png)

 Un thread deve essere responsabile della finestra di messaggio. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] potrebbe creare un nuovo thread solo per la finestra di messaggio, ma questo thread non sarebbe in grado di disegnare gli elementi disabilitati nella finestra originale (in base a quanto illustrato in precedenza in relazione all'esclusione reciproca). [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utilizza invece un sistema di elaborazione dei messaggi annidato. La classe <xref:System.Windows.Threading.Dispatcher> include un metodo speciale denominato <xref:System.Windows.Threading.Dispatcher.PushFrame%2A>, che archivia il punto di esecuzione corrente di un'applicazione, quindi avvia un nuovo ciclo di messaggi. Al termine del ciclo di messaggi annidati, l'esecuzione riprende dopo la chiamata di <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> originale.

 In questo caso, <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> gestisce il contesto del programma alla chiamata a <xref:System.Windows.MessageBox.Show%2A?displayProperty=nameWithType>e avvia un nuovo ciclo di messaggi per ridisegnare la finestra di sfondo e gestire l'input della finestra di messaggio. Quando l'utente fa clic su OK e cancella la finestra popup, il ciclo annidato viene chiuso e il controllo riprende dopo la chiamata a <xref:System.Windows.MessageBox.Show%2A>.

### <a name="stale-routed-events"></a>Eventi indirizzati non aggiornati
 Il sistema di eventi indirizzati in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] notifica a interi alberi quando vengono generati eventi.

 [!code-xaml[InputOvw#ThreadingArticleStaticRoutedEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#threadingarticlestaticroutedevent)]

 Quando viene premuto il pulsante sinistro del mouse sull'ellisse, viene eseguito `handler2`. Al termine dell'`handler2`, l'evento viene passato all'oggetto <xref:System.Windows.Controls.Canvas>, che usa `handler1` per elaborarlo. Questa situazione si verifica solo se `handler2` non contrassegna in modo esplicito l'oggetto evento come gestito.

 È possibile che `handler2` l'elaborazione di questo evento venga eseguita da molto tempo. `handler2` possibile utilizzare <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> per avviare un ciclo di messaggi annidato che non restituisce per ore. Se `handler2` non contrassegna l'evento come gestito quando il ciclo di messaggi è completo, l'evento viene passato alla struttura ad albero anche se è molto vecchio.

### <a name="reentrancy-and-locking"></a>Reentrancy e blocco
 Il meccanismo di blocco del Common Language Runtime (CLR) non si comporta esattamente come si può immaginare; si potrebbe aspettare che un thread smetta completamente l'operazione quando viene richiesto un blocco. In realtà, il thread continua a ricevere ed elaborare i messaggi con priorità alta. Questo consente di evitare i deadlock e rendere le interfacce un minimo reattive, ma introduce la possibilità di bug.  Nella maggior parte dei casi non è necessario conoscere questo aspetto, ma in rari casi (in genere che coinvolgono i messaggi della finestra Win32 o i componenti COM STA) può essere utile sapere.

 La maggior parte delle interfacce non è compilata tenendo conto di thread safety perché gli sviluppatori utilizzano il presupposto che non venga mai eseguito l'accesso a una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] da più di un thread. In questo caso, il singolo thread può apportare modifiche ambientali in momenti imprevisti, causando gli effetti negativi che la <xref:System.Windows.Threading.DispatcherObject> meccanismo di esclusione reciproca dovrebbe risolvere. Si consideri lo pseudocodice seguente:

 ![Diagramma che mostra la rientranza del threading.](./media/threading-model/threading-reentrancy.png "ThreadingReentrancy")

 Nella maggior parte dei casi questo è il momento giusto, ma in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] casi in cui tali rientranze impreviste possono effettivamente causare problemi. Quindi, in determinati momenti chiave, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] chiama <xref:System.Windows.Threading.Dispatcher.DisableProcessing%2A>, che modifica l'istruzione di blocco per il thread in modo da utilizzare il blocco [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] rientrante, anziché il consueto blocco CLR.

 Perché il team CLR ha scelto questo comportamento? La scelta ha a che fare con gli oggetti COM STA e il thread di finalizzazione. Quando un oggetto viene sottoposto a Garbage Collection, il relativo `Finalize` metodo viene eseguito sul thread del finalizzatore dedicato, non sul thread [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Il problema risiede nel fatto che un oggetto COM STA creato nel thread di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] può essere eliminato solo sul thread di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. CLR esegue l'equivalente di un <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> (in questo caso utilizzando Win32 `SendMessage`). Tuttavia, se il thread di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] è occupato, il thread del finalizzatore viene bloccato e l'oggetto COM STA non può essere eliminato, il che crea una perdita di memoria grave. Quindi, il team CLR ha fatto la chiamata complessa per far funzionare i blocchi nel modo in cui fanno.

 L'attività per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consiste nel evitare una rientranza imprevista senza reintrodurre la perdita di memoria, motivo per cui non è possibile bloccare la rientranza in tutto il mondo.

## <a name="see-also"></a>Vedere anche

- [Esempio di applicazione a thread singolo con calcolo a esecuzione prolungata](https://github.com/Microsoft/WPF-Samples/tree/master/Threading/SingleThreadedApplication)
