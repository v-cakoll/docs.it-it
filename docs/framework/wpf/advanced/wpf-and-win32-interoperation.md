---
title: Interoperatività di WPF e Win32
ms.date: 03/30/2017
helpviewer_keywords:
- hosting WPF content in Win32 window [WPF]
- HWND interop [WPF]
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 0ffbde0d-701d-45a3-a6fa-dd71f4d9772e
ms.openlocfilehash: a942d72f27d394d31a52fd02ecaa158add4d2e0f
ms.sourcegitcommit: 4b9c2d893b45d47048c6598b4182ba87759b1b59
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/25/2019
ms.locfileid: "68484638"
---
# <a name="wpf-and-win32-interoperation"></a>Interoperatività di WPF e Win32
Questo argomento fornisce una panoramica dell'interoperatività tra codice [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce un ambiente completo per la creazione di applicazioni. Tuttavia, se si ha una grande quantità di codice [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], può essere più efficace riutilizzare tale codice.  

<a name="basics"></a>   
## <a name="wpf-and-win32-interoperation-basics"></a>Nozioni di base sull'interoperatività di WPF e Win32  
 Ci sono due tecniche di base per l'interoperatività tra codice [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
- Ospitare il contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in una finestra [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Con questa tecnica, è possibile usare le funzionalità grafiche avanzate di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nel framework di una finestra e di un'applicazione [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] standard.  
  
- Ospitare una finestra [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] nel contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Con questa tecnica, è possibile usare un controllo [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] personalizzato esistente nel contesto di altro contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e passare i dati attraversando i limiti.  
  
 Questo argomento illustra concettualmente queste due tecniche. Per un'illustrazione più orientata al codice dell' [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hosting [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]di in [, vedere Procedura dettagliata: Hosting di contenuto WPF in](walkthrough-hosting-wpf-content-in-win32.md)Win32. Per un'illustrazione più orientata al codice dell' [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] hosting [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]di in [, vedere Procedura dettagliata: Hosting di un controllo Win32 in](walkthrough-hosting-a-win32-control-in-wpf.md)WPF.  
  
<a name="projects"></a>   
## <a name="wpf-interoperation-projects"></a>Progetti di interoperatività WPF  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Le API sono codice gestito, ma la [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] maggior parte dei programmi esistenti viene scritta C++in non gestita.  Non è possibile [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] chiamare le API da un vero programma non gestito. Tuttavia, usando l' `/clr` opzione con il [!INCLUDE[TLA#tla_visualcpp](../../../../includes/tlasharptla-visualcpp-md.md)] compilatore, è possibile creare un programma misto gestito e non gestito in cui è possibile combinare facilmente le chiamate API gestite e non gestite.  
  
 Una complicazione a livello di progetto è che non è [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] possibile compilare i C++ file in un progetto.  Per ovviare a tale problema, ci sono diverse tecniche di divisione dei progetti.  
  
- Creare una C# dll contenente tutte le [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pagine come assembly compilato e quindi fare in modo che il C++ file eseguibile [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] includa tale file come riferimento.  
  
- Creare un C# eseguibile per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] il contenuto e fare riferimento a un C++ [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] oggetto che contiene [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] il contenuto.  
  
- Usare <xref:System.Windows.Markup.XamlReader.Load%2A> per caricare qualsiasi [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in fase di esecuzione, anziché compilare il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
- Non usare [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] affatto e scrivere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tutto il codice nel codice, costruendo l'albero degli elementi da <xref:System.Windows.Application>.  
  
 Usare l'approccio che meglio soddisfa le esigenze.  
  
> [!NOTE]
>  Se non è stato usato C++/CLI in precedenza, è possibile notare alcune parole chiave "nuove" `gcnew` , `nullptr` ad esempio e negli esempi di codice di interoperabilità. Queste parole chiave sostituiscono la sintassi di doppio sottolineatura`__gc`precedente () e forniscono una sintassi più naturale per il C++codice gestito in.  Per ulteriori informazioni sulle funzionalità C++gestite di/CLI, vedere [estensioni dei componenti per le piattaforme di runtime](/cpp/windows/component-extensions-for-runtime-platforms) e [Hello, C++/CLI](https://go.microsoft.com/fwlink/?LinkId=98739).  
  
<a name="hwnds"></a>   
## <a name="how-wpf-uses-hwnds"></a>Modo d'uso degli handle di finestra (HWND) in WPF  
 Per sfruttare al meglio le caratteristiche di "interoperatività HWND" di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], è necessario capire in che modo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa gli handle di finestra (HWND). Per qualsiasi oggetto HWND, non è possibile combinare il rendering [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] con il rendering [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] o il rendering [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] / [!INCLUDE[TLA2#tla_gdiplus](../../../../includes/tla2sharptla-gdiplus-md.md)]. Questo comporta diverse implicazioni. In primo luogo, per combinare questi modelli di rendering, è necessario creare una soluzione di interoperatività e usare segmenti designati di interoperatività per ogni modello di rendering che si sceglie di usare. Il comportamento di rendering crea inoltre una restrizione di "spazio aereo" per le operazioni che la soluzione di interoperatività può completare. Il concetto di "spazio aereo" è illustrato più dettagliatamente nell'argomento [Cenni preliminari sulle aree di tecnologia](technology-regions-overview.md).  
  
 Tutti gli elementi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nella schermata sono supportati da un oggetto HWND. Quando si crea un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] oggetto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window>, viene creato un HWND di primo livello e viene <xref:System.Windows.Interop.HwndSource> utilizzato un oggetto <xref:System.Windows.Window> per inserire [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] l'oggetto e il relativo contenuto all'interno di HWND.  Il resto del contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nell'applicazione condivide tale oggetto HWND singolo. Un'eccezione è costituita da menu, caselle combinate a discesa e altri popup. Poiché questi elementi creano una propria finestra di primo livello, è possibile che un menu [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] superi potenzialmente il bordo dell'oggetto HWND della finestra che lo contiene. Quando si usa <xref:System.Windows.Interop.HwndHost> per inserire un HWND all' [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]interno [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di, informa [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] come posizionare il nuovo HWND figlio rispetto a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window> HWND.  
  
 Un concetto correlato a HWND è la trasparenza all'interno di ogni oggetto HWND e tra tali oggetti. Questo concetto è illustrato anche nell'argomento [Cenni preliminari sulle aree di tecnologia](technology-regions-overview.md).  
  
<a name="hosting_a_wpf_page"></a>   
## <a name="hosting-wpf-content-in-a-microsoft-win32-window"></a>Hosting di contenuto WPF in una finestra Microsoft Win32  
 La chiave per ospitare un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] oggetto in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] una finestra è <xref:System.Windows.Interop.HwndSource> la classe. Questa classe esegue il wrapping del contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in una finestra [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], consentendo di incorporare il contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nell'[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] come finestra figlio. Nell'approccio che segue, [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono combinati in un'unica applicazione.  
  
1. Implementare il contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (elemento radice del contenuto) come classe gestita. In genere, la classe eredita da una delle classi che possono contenere più elementi figlio e/o usata come elemento radice, ad esempio <xref:System.Windows.Controls.DockPanel> o. <xref:System.Windows.Controls.Page> Nei passaggi successivi questa classe è detta classe contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e le istanze della classe sono dette oggetti contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
2. Implementare un'applicazione Windows con C++/cli. Se si inizia con un' C++ applicazione non gestita esistente, in genere è possibile abilitarla per chiamare il codice gestito modificando le impostazioni del progetto in modo `/clr` da includere il flag del compilatore (l'ambito completo di ciò che `/clr` potrebbe essere necessario supportare la compilazione non è descritta in questo argomento.  
  
3. Impostare il modello di threading su apartment a thread singolo (STA, Single Threaded Apartment). [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa questo modello di threading.  
  
4. Gestire la notifica WM_CREATE nella procedura di finestra.  
  
5. All'interno del gestore (o di una funzione chiamata dal gestore) eseguire queste operazioni:  
  
    1. Creare un nuovo <xref:System.Windows.Interop.HwndSource> oggetto con il valore HWND della finestra padre `parent` come parametro.  
  
    2. Creare un'istanza della classe contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
    3. Assegnare un riferimento all' [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] oggetto contenuto alla proprietà dell' <xref:System.Windows.Interop.HwndSource> oggetto. <xref:System.Windows.Interop.HwndSource.RootVisual%2A>  
  
    4. La <xref:System.Windows.Interop.HwndSource> proprietà <xref:System.Windows.Interop.HwndSource.Handle%2A> dell'oggetto contiene l'handle di finestra (HWND). Per ottenere un HWND utilizzabile nella parte non gestita dell'applicazione, eseguire il cast di `Handle.ToPointer()` a un HWND.  
  
6. Implementare una classe gestita che include un campo statico contenente un riferimento all'oggetto contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Questa classe consente di ottenere un riferimento all' [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] oggetto contenuto [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dal codice, ma ancora più <xref:System.Windows.Interop.HwndSource> importante impedisce che venga inavvertitamente sottoposta a Garbage Collection.  
  
7. Ricevere notifiche dall'oggetto contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] associando un gestore a uno o più eventi dell'oggetto contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
8. Comunicare con l'oggetto contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usando il riferimento archiviato nel campo statico per impostare proprietà, chiamare metodi e così via.  
  
> [!NOTE]
>  Tutte le attività di definizione della classe contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], o alcune di esse, per il primo passaggio in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] possono essere eseguite usando la classe parziale predefinita della classe contenuto, se si genera un assembly separato e quindi vi si fa riferimento. Sebbene in genere si <xref:System.Windows.Application> includa un oggetto come parte della compilazione [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] di in un assembly, <xref:System.Windows.Application> non si finisce di usarlo come parte dell'interoperabilità, ma si usano solo una o più classi radice per i [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file a cui si fa riferimento a dall'applicazione e fanno riferimento alle relative classi parziali. La parte restante della procedura è essenzialmente simile a quella appena descritta.  
>   
>  Ognuno di questi passaggi viene illustrato tramite il codice nell'argomento [procedura dettagliata: Hosting di contenuto WPF in](walkthrough-hosting-wpf-content-in-win32.md)Win32.  
  
<a name="hosting_an_hwnd"></a>   
## <a name="hosting-a-microsoft-win32-window-in-wpf"></a>Hosting di una finestra Microsoft Win32 in WPF  
 La chiave per ospitare una [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra all'interno [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di altro contenuto <xref:System.Windows.Interop.HwndHost> è la classe. Questa classe esegue il wrapping della finestra in un elemento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] che può essere aggiunto a un albero degli elementi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. <xref:System.Windows.Interop.HwndHost>supporta anche le API che consentono di eseguire attività come l'elaborazione dei messaggi per la finestra ospitata. La procedura di base è la seguente:  
  
1. Creare un albero degli elementi per un'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (tramite codice o markup). Trovare un punto appropriato e ammissibile nell'albero degli elementi in cui <xref:System.Windows.Interop.HwndHost> l'implementazione può essere aggiunta come elemento figlio. Nei restanti passaggi questo elemento viene chiamato elemento di riserva.  
  
2. Derivare <xref:System.Windows.Interop.HwndHost> da per creare un oggetto che include [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] il contenuto.  
  
3. In tale classe host eseguire l'override <xref:System.Windows.Interop.HwndHost> del <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>metodo. Restituire l'oggetto HWND della finestra ospitata. Può essere necessario eseguire il wrapping dei controlli effettivi come finestra figlio della finestra restituita. Il wrapping dei controlli in una finestra host offre un modo semplice per consentire al contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di ricevere notifiche dai controlli. Questa tecnica aiuta a correggere alcuni problemi di [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] relativi alla gestione dei messaggi in corrispondenza del limite del controllo ospitato.  
  
4. Eseguire l' <xref:System.Windows.Interop.HwndHost> override <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> dei <xref:System.Windows.Interop.HwndHost.WndProc%2A>metodi e. Lo scopo è quello di eseguire la pulizia e rimuovere i riferimenti al contenuto ospitato, in particolare se sono stati creati riferimenti a oggetti non gestiti.  
  
5. Nel file code-behind creare un'istanza della classe di hosting del controllo e impostarla come figlio dell'elemento di riserva. In genere si usa un gestore eventi <xref:System.Windows.FrameworkElement.Loaded>, ad esempio, o si usa il costruttore della classe parziale. È però anche possibile aggiungere il contenuto di interoperatività tramite un comportamento di runtime.  
  
6. Elaborare i messaggi della finestra selezionati, ad esempio le notifiche dei controlli. Ci sono due approcci. Entrambi offrono un accesso identico al flusso di messaggi, quindi la scelta dipende per lo più dalle esigenze di programmazione.  
  
    - Implementare l'elaborazione del messaggio per tutti i messaggi (non solo per i messaggi di arresto <xref:System.Windows.Interop.HwndHost> ) <xref:System.Windows.Interop.HwndHost.WndProc%2A>nell'override del metodo.  
  
    - Fare in modo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] che l'elemento host elabori i messaggi <xref:System.Windows.Interop.HwndHost.MessageHook> gestendo l'evento. Questo evento viene generato per ogni messaggio inviato alla procedura di finestra principale della finestra ospitata.  
  
    - Non è possibile elaborare messaggi da finestre che non sono in corso <xref:System.Windows.Interop.HwndHost.WndProc%2A>di elaborazione utilizzando.  
  
7. Comunicare con la finestra ospitata usando platform invoke per chiamare la funzione `SendMessage` non gestita.  
  
 Questi passaggi consentono di creare un'applicazione che funziona con l'input del mouse. È possibile aggiungere il supporto di tabulazione per la finestra ospitata <xref:System.Windows.Interop.IKeyboardInputSink> implementando l'interfaccia.  
  
 Ognuno di questi passaggi viene illustrato tramite il codice nell'argomento [procedura dettagliata: Hosting di un controllo Win32 in](walkthrough-hosting-a-win32-control-in-wpf.md)WPF.  
  
### <a name="hwnds-inside-wpf"></a>Handle di finestra (HWND) in WPF  
 È possibile considerare <xref:System.Windows.Interop.HwndHost> come un controllo speciale. Tecnicamente, <xref:System.Windows.Interop.HwndHost> è una <xref:System.Windows.FrameworkElement> classe derivata, non una <xref:System.Windows.Controls.Control> classe derivata, ma può essere considerata un controllo per finalità di interoperabilità. astrae la natura [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] sottostante del contenuto ospitato in modo che il resto di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consideri il contenuto ospitato come un altro oggetto simile a un controllo, che deve eseguire il rendering e l'elaborazione dell'input. <xref:System.Windows.Interop.HwndHost> <xref:System.Windows.Interop.HwndHost>in genere si comporta in modo analogo a qualsiasi altro [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement>, anche se esistono alcune differenze importanti sull'output (disegno e grafica) e sull'input (mouse e tastiera) in base alle limitazioni di ciò che gli HWND sottostanti sono in grado di supportare.  
  
#### <a name="notable-differences-in-output-behavior"></a>Differenze rilevanti nel comportamento di output  
  
- <xref:System.Windows.FrameworkElement>, che è la <xref:System.Windows.Interop.HwndHost> classe di base, ha alcune proprietà che implicano modifiche all'interfaccia utente. Sono incluse proprietà <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType>come, che modificano il layout degli elementi all'interno di tale elemento come padre. La maggior parte di queste proprietà non è tuttavia mappata a possibili equivalenti [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], anche se tali equivalenti possono essere presenti. Poiché un numero elevato di queste proprietà e dei relativi significati è troppo specifico della tecnologia di rendering, il mapping non è una soluzione pratica. Di conseguenza, l'impostazione <xref:System.Windows.FrameworkElement.FlowDirection%2A> di proprietà quali on <xref:System.Windows.Interop.HwndHost> non ha alcun effetto.  
  
- <xref:System.Windows.Interop.HwndHost>non può essere ruotato, ridimensionato, inclinato o influenzato in altro modo da una trasformazione.  
  
- <xref:System.Windows.Interop.HwndHost>non supporta la <xref:System.Windows.UIElement.Opacity%2A> proprietà (fusione alfa). Se il contenuto all' <xref:System.Windows.Interop.HwndHost> interno <xref:System.Drawing> di esegue operazioni che includono informazioni Alpha, non si tratta di una violazione, <xref:System.Windows.Interop.HwndHost> ma l'oggetto nel suo complesso supporta solo l'opacità = 1,0 (100%).  
  
- <xref:System.Windows.Interop.HwndHost>verrà visualizzato sopra gli altri [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elementi nella stessa finestra di primo livello. Tuttavia, un <xref:System.Windows.Controls.ToolTip> menu <xref:System.Windows.Controls.ContextMenu> generato da o è una finestra di primo livello distinta e pertanto si comporterà correttamente con <xref:System.Windows.Interop.HwndHost>.  
  
- <xref:System.Windows.Interop.HwndHost>non rispetta l'area di visualizzazione del padre <xref:System.Windows.UIElement>. Si tratta potenzialmente di un problema se si tenta di inserire <xref:System.Windows.Interop.HwndHost> una classe all'interno di un'area <xref:System.Windows.Controls.Canvas>di scorrimento o.  
  
#### <a name="notable-differences-in-input-behavior"></a>Differenze rilevanti nel comportamento di input  
  
- In generale, mentre l'ambito dei dispositivi di input è <xref:System.Windows.Interop.HwndHost> all' [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] interno dell'area ospitata, gli [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]eventi di input passano direttamente a.  
  
- Quando il mouse è posizionato sull' <xref:System.Windows.Interop.HwndHost>oggetto, l'applicazione non riceve [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gli eventi del mouse [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e il valore `false`della proprietà <xref:System.Windows.UIElement.IsMouseOver%2A> sarà.  
  
- Con lo <xref:System.Windows.Interop.HwndHost> stato attivo della tastiera, l'applicazione non riceverà [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gli eventi della tastiera [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e il valore <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> `false`della proprietà sarà.  
  
- Quando lo <xref:System.Windows.Interop.HwndHost> stato attivo si trova all'interno di e passa a <xref:System.Windows.Interop.HwndHost>un altro controllo all'interno di, l' <xref:System.Windows.UIElement.GotFocus> applicazione <xref:System.Windows.UIElement.LostFocus>non riceverà gli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eventi o.  
  
- Le proprietà e gli eventi dello stilo correlati sono analoghi e non segnalano informazioni quando <xref:System.Windows.Interop.HwndHost>lo stilo è sopra.  
  
<a name="tabbing_mnemonics_accelerators"></a>   
## <a name="tabbing-mnemonics-and-accelerators"></a>Tabulazioni, tasti di scelta e tasti di scelta rapida  
 Le <xref:System.Windows.Interop.IKeyboardInputSink> interfacce <xref:System.Windows.Interop.IKeyboardInputSite> e consentono di creare un'esperienza di tastiera senza problemi per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] applicazioni miste e:  
  
- Spostamento tra componenti [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tramite il tasto TAB  
  
- Tasti di scelta e tasti di scelta rapida che funzionano sia quando lo stato attivo è all'interno di un componente Win32 che quando è all'interno di un componente WPF.  
  
 Le <xref:System.Windows.Interop.HwndHost> classi <xref:System.Windows.Interop.HwndSource> e forniscono entrambe le implementazioni <xref:System.Windows.Interop.IKeyboardInputSink>di, ma non possono gestire tutti i messaggi di input desiderati per scenari più avanzati. Eseguire l'override dei metodi appropriati per ottenere il comportamento di tastiera desiderato.  
  
 Le interfacce forniscono supporto solo per le operazioni eseguite nella transizione tra le aree [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. All'interno dell'area [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], il comportamento di tabulazione è completamente controllato dalla logica implementata da [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] per la tabulazione, se presente.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Interop.HwndHost>
- <xref:System.Windows.Interop.HwndSource>
- <xref:System.Windows.Interop>
- [Procedura dettagliata: Hosting di un controllo Win32 in WPF](walkthrough-hosting-a-win32-control-in-wpf.md)
- [Procedura dettagliata: Hosting di contenuto WPF in Win32](walkthrough-hosting-wpf-content-in-win32.md)
