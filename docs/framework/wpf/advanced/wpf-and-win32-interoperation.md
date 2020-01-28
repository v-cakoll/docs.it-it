---
title: Interoperabilità Win32 e WPF
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- hosting WPF content in Win32 window [WPF]
- HWND interop [WPF]
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 0ffbde0d-701d-45a3-a6fa-dd71f4d9772e
ms.openlocfilehash: 7b7c3ed8f9833094ce1e836c11f84132ae84def2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735223"
---
# <a name="wpf-and-win32-interoperation"></a>Interoperatività di WPF e Win32

In questo argomento viene fornita una panoramica dell'interoperabilità di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e del codice Win32. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce un ambiente completo per la creazione di applicazioni. Tuttavia, quando si ha un investimento sostanziale nel codice Win32, potrebbe essere più efficace riutilizzare parte del codice.

<a name="basics"></a>

## <a name="wpf-and-win32-interoperation-basics"></a>Nozioni di base sull'interoperatività di WPF e Win32

Esistono due tecniche di base per l'interoperatività tra [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e il codice Win32.

- Ospitare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenuto in una finestra Win32. Con questa tecnica, è possibile usare le funzionalità grafiche avanzate di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] all'interno del Framework di una finestra e di un'applicazione Win32 standard.

- Ospita una finestra Win32 nel contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Con questa tecnica, è possibile usare un controllo Win32 personalizzato esistente nel contesto di altri [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenuto e passare i dati attraverso i limiti.

Questo argomento illustra concettualmente queste due tecniche. Per un'illustrazione più orientata al codice dell'hosting [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in Win32, vedere [procedura dettagliata: hosting di contenuto WPF in Win32](walkthrough-hosting-wpf-content-in-win32.md). Per un'illustrazione più orientata al codice dell'hosting di Win32 in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vedere [procedura dettagliata: hosting di un controllo Win32 in WPF](walkthrough-hosting-a-win32-control-in-wpf.md).

<a name="projects"></a>

## <a name="wpf-interoperation-projects"></a>Progetti di interoperatività WPF

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] API sono codice gestito, ma la maggior parte dei programmi Win32 esistenti sono scritti in C++non gestiti.  Non è possibile chiamare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] API da un vero programma non gestito. Tuttavia, usando l'opzione `/clr` con il compilatore visuale C++ Microsoft, è possibile creare un programma misto gestito e non gestito in cui è possibile combinare facilmente le chiamate API gestite e non gestite.

Una complicazione a livello di progetto è che non è possibile compilare [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file C++ in un progetto.  Per ovviare a tale problema, ci sono diverse tecniche di divisione dei progetti.

- Creare una C# dll contenente tutte le pagine di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] come assembly compilato e quindi fare in modo che C++ il file eseguibile includa tale DLL come riferimento.

- Creare un C# eseguibile per il contenuto del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e fare in riferimento C++ a una dll che contiene il contenuto Win32.

- Usare <xref:System.Windows.Markup.XamlReader.Load%2A> per caricare qualsiasi [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in fase di esecuzione, anziché compilare il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].

- Non usare [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] e scrivere tutti i [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nel codice, costruendo l'albero degli elementi da <xref:System.Windows.Application>.

Usare l'approccio che meglio soddisfa le esigenze.

> [!NOTE]
> Se non è stato usato C++/CLI in precedenza, è possibile notare alcune parole chiave "nuove", ad esempio `gcnew` e `nullptr` negli esempi di codice di interoperabilità. Queste parole chiave sostituiscono la sintassi di doppio sottolineatura precedente (`__gc`) e forniscono una sintassi più naturale per il C++codice gestito in.  Per ulteriori informazioni sulle funzionalità C++gestite di/CLI, vedere [estensioni dei componenti per le piattaforme di runtime](/cpp/windows/component-extensions-for-runtime-platforms).

<a name="hwnds"></a>

## <a name="how-wpf-uses-hwnds"></a>Modo d'uso degli handle di finestra (HWND) in WPF

Per sfruttare al meglio le caratteristiche di "interoperatività HWND" di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], è necessario capire in che modo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa gli handle di finestra (HWND). Per qualsiasi HWND, non è possibile combinare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] rendering con il rendering DirectX o il rendering GDI/GDI+. Questo comporta diverse implicazioni. In primo luogo, per combinare questi modelli di rendering, è necessario creare una soluzione di interoperatività e usare segmenti designati di interoperatività per ogni modello di rendering che si sceglie di usare. Il comportamento di rendering crea inoltre una restrizione di "spazio aereo" per le operazioni che la soluzione di interoperatività può completare. Il concetto di "spazio aereo" è illustrato più dettagliatamente nell'argomento [Cenni preliminari sulle aree di tecnologia](technology-regions-overview.md).

Tutti gli elementi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nella schermata sono supportati da un oggetto HWND. Quando si crea un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window>, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] crea un HWND di primo livello e utilizza un <xref:System.Windows.Interop.HwndSource> per inserire il <xref:System.Windows.Window> e il relativo contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] all'interno di HWND.  Il resto del contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nell'applicazione condivide tale oggetto HWND singolo. Un'eccezione è costituita da menu, caselle combinate a discesa e altri popup. Poiché questi elementi creano una propria finestra di primo livello, è possibile che un menu [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] superi potenzialmente il bordo dell'oggetto HWND della finestra che lo contiene. Quando si utilizza <xref:System.Windows.Interop.HwndHost> per inserire un HWND all'interno di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] informa Win32 come posizionare il nuovo HWND figlio rispetto alla [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window> HWND.

Un concetto correlato a HWND è la trasparenza all'interno di ogni oggetto HWND e tra tali oggetti. Questo concetto è illustrato anche nell'argomento [Cenni preliminari sulle aree di tecnologia](technology-regions-overview.md).

<a name="hosting_a_wpf_page"></a>

## <a name="hosting-wpf-content-in-a-microsoft-win32-window"></a>Hosting di contenuto WPF in una finestra Microsoft Win32

La chiave per ospitare un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in una finestra Win32 è la classe <xref:System.Windows.Interop.HwndSource>. Questa classe esegue il wrapping del contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in una finestra Win32, in modo che il contenuto del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] possa essere incorporato nel [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] come finestra figlio. L'approccio seguente combina Win32 e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in un'unica applicazione.

1. Implementare il contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (elemento radice del contenuto) come classe gestita. In genere, la classe eredita da una delle classi che possono contenere più elementi figlio e/o usata come elemento radice, ad esempio <xref:System.Windows.Controls.DockPanel> o <xref:System.Windows.Controls.Page>. Nei passaggi successivi questa classe è detta classe contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e le istanze della classe sono dette oggetti contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

2. Implementare un'applicazione Windows con C++/cli. Se si inizia con un' C++ applicazione non gestita esistente, in genere è possibile abilitarla per chiamare il codice gestito modificando le impostazioni del progetto in modo da includere il flag del compilatore `/clr` (l'ambito completo di ciò che potrebbe essere necessario per supportare la compilazione `/clr` non è descritto in questo argomento).

3. Impostare il modello di threading su apartment a thread singolo (STA, Single Threaded Apartment). [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa questo modello di threading.

4. Gestire la notifica WM_CREATE nella procedura di finestra.

5. All'interno del gestore (o di una funzione chiamata dal gestore) eseguire queste operazioni:

    1. Creare un nuovo oggetto <xref:System.Windows.Interop.HwndSource> con HWND della finestra padre come parametro di `parent`.

    2. Creare un'istanza della classe contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

    3. Assegnare un riferimento all'oggetto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenuto alla proprietà <xref:System.Windows.Interop.HwndSource> oggetto <xref:System.Windows.Interop.HwndSource.RootVisual%2A>.

    4. La proprietà <xref:System.Windows.Interop.HwndSource> oggetto <xref:System.Windows.Interop.HwndSource.Handle%2A> contiene l'handle di finestra (HWND). Per ottenere un HWND utilizzabile nella parte non gestita dell'applicazione, eseguire il cast di `Handle.ToPointer()` a un HWND.

6. Implementare una classe gestita che include un campo statico contenente un riferimento all'oggetto contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Questa classe consente di ottenere un riferimento all'oggetto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenuto dal codice Win32, ma ancora più importante impedisce che la <xref:System.Windows.Interop.HwndSource> venga inavvertitamente sottoposta a Garbage Collection.

7. Ricevere notifiche dall'oggetto contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] associando un gestore a uno o più eventi dell'oggetto contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

8. Comunicare con l'oggetto contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usando il riferimento archiviato nel campo statico per impostare proprietà, chiamare metodi e così via.

> [!NOTE]
> Tutte le attività di definizione della classe contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], o alcune di esse, per il primo passaggio in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] possono essere eseguite usando la classe parziale predefinita della classe contenuto, se si genera un assembly separato e quindi vi si fa riferimento. Sebbene in genere si includa un oggetto <xref:System.Windows.Application> come parte della compilazione del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in un assembly, non si finisce di utilizzare tale <xref:System.Windows.Application> come parte dell'interoperabilità, è sufficiente utilizzare una o più classi radice per i file [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] a cui fa riferimento l'applicazione e fare riferimento alle relative classi parziali. La parte restante della procedura è essenzialmente simile a quella appena descritta.
>
> Ognuno di questi passaggi viene illustrato tramite il codice nell'argomento [Procedura dettagliata: hosting di contenuto WPF in Win32](walkthrough-hosting-wpf-content-in-win32.md).

<a name="hosting_an_hwnd"></a>

## <a name="hosting-a-microsoft-win32-window-in-wpf"></a>Hosting di una finestra Microsoft Win32 in WPF

La chiave per ospitare una finestra Win32 all'interno di altri [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenuto è la classe <xref:System.Windows.Interop.HwndHost>. Questa classe esegue il wrapping della finestra in un elemento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] che può essere aggiunto a un albero degli elementi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. <xref:System.Windows.Interop.HwndHost> supporta anche le API che consentono di eseguire attività quali l'elaborazione dei messaggi per la finestra ospitata. La procedura di base è la seguente:

1. Creare un albero degli elementi per un'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (tramite codice o markup). Trovare un punto appropriato e ammissibile nell'albero degli elementi in cui è possibile aggiungere l'implementazione del <xref:System.Windows.Interop.HwndHost> come elemento figlio. Nei restanti passaggi questo elemento viene chiamato elemento di riserva.

2. Derivare da <xref:System.Windows.Interop.HwndHost> per creare un oggetto che include il contenuto Win32.

3. In tale classe host, eseguire l'override del metodo <xref:System.Windows.Interop.HwndHost> <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>. Restituire l'oggetto HWND della finestra ospitata. Può essere necessario eseguire il wrapping dei controlli effettivi come finestra figlio della finestra restituita. Il wrapping dei controlli in una finestra host offre un modo semplice per consentire al contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di ricevere notifiche dai controlli. Questa tecnica consente di correggere alcuni problemi Win32 relativi alla gestione dei messaggi in corrispondenza del limite del controllo ospitato.

4. Eseguire l'override dei metodi di <xref:System.Windows.Interop.HwndHost> <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> e <xref:System.Windows.Interop.HwndHost.WndProc%2A>. Lo scopo è quello di eseguire la pulizia e rimuovere i riferimenti al contenuto ospitato, in particolare se sono stati creati riferimenti a oggetti non gestiti.

5. Nel file code-behind creare un'istanza della classe di hosting del controllo e impostarla come figlio dell'elemento di riserva. In genere si usa un gestore eventi, ad esempio <xref:System.Windows.FrameworkElement.Loaded>, oppure si usa il costruttore della classe parziale. È però anche possibile aggiungere il contenuto di interoperatività tramite un comportamento di runtime.

6. Elaborare i messaggi della finestra selezionati, ad esempio le notifiche dei controlli. Ci sono due approcci. Entrambi offrono un accesso identico al flusso di messaggi, quindi la scelta dipende per lo più dalle esigenze di programmazione.

    - Implementare l'elaborazione del messaggio per tutti i messaggi (non solo per i messaggi di arresto) nell'override del metodo <xref:System.Windows.Interop.HwndHost> <xref:System.Windows.Interop.HwndHost.WndProc%2A>.

    - Fare in modo che l'elemento host [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elabori i messaggi gestendo l'evento <xref:System.Windows.Interop.HwndHost.MessageHook>. Questo evento viene generato per ogni messaggio inviato alla procedura di finestra principale della finestra ospitata.

    - Non è possibile elaborare messaggi da finestre che non sono in corso di elaborazione utilizzando <xref:System.Windows.Interop.HwndHost.WndProc%2A>.

7. Comunicare con la finestra ospitata usando platform invoke per chiamare la funzione `SendMessage` non gestita.

Questi passaggi consentono di creare un'applicazione che funziona con l'input del mouse. È possibile aggiungere il supporto di tabulazione per la finestra ospitata implementando l'interfaccia <xref:System.Windows.Interop.IKeyboardInputSink>.

Ognuno di questi passaggi viene illustrato tramite il codice nell'argomento [Procedura dettagliata: hosting di un controllo Win32 in WPF](walkthrough-hosting-a-win32-control-in-wpf.md).

### <a name="hwnds-inside-wpf"></a>Handle di finestra (HWND) in WPF

È possibile considerare <xref:System.Windows.Interop.HwndHost> come un controllo speciale. Tecnicamente, <xref:System.Windows.Interop.HwndHost> è una classe derivata <xref:System.Windows.FrameworkElement>, non una classe derivata <xref:System.Windows.Controls.Control>, ma può essere considerata un controllo per l'interoperabilità. <xref:System.Windows.Interop.HwndHost> astrae la natura Win32 sottostante del contenuto ospitato in modo che il resto del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consideri il contenuto ospitato come un altro oggetto simile a un controllo, che deve eseguire il rendering e l'elaborazione dell'input. <xref:System.Windows.Interop.HwndHost> in genere si comporta in modo analogo a qualsiasi altra [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement>, anche se esistono alcune importanti differenze nell'output (disegno e grafica) e input (mouse e tastiera) in base alle limitazioni di ciò che gli HWND sottostanti sono in grado di supportare.

#### <a name="notable-differences-in-output-behavior"></a>Differenze rilevanti nel comportamento di output

- <xref:System.Windows.FrameworkElement>, ovvero la classe di base <xref:System.Windows.Interop.HwndHost>, presenta alcune proprietà che implicano modifiche all'interfaccia utente. Sono incluse proprietà come <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType>, che modifica il layout degli elementi all'interno di tale elemento come padre. Tuttavia, la maggior parte di queste proprietà non è mappata ai possibili equivalenti Win32, anche se potrebbero esistere tali equivalenti. Poiché un numero elevato di queste proprietà e dei relativi significati è troppo specifico della tecnologia di rendering, il mapping non è una soluzione pratica. Di conseguenza, l'impostazione di proprietà quali <xref:System.Windows.FrameworkElement.FlowDirection%2A> su <xref:System.Windows.Interop.HwndHost> non ha alcun effetto.

- <xref:System.Windows.Interop.HwndHost> non possono essere ruotate, ridimensionate, inclinate o modificate in altro modo da una trasformazione.

- <xref:System.Windows.Interop.HwndHost> non supporta la proprietà <xref:System.Windows.UIElement.Opacity%2A> (fusione alfa). Se il contenuto all'interno del <xref:System.Windows.Interop.HwndHost> esegue <xref:System.Drawing> operazioni che includono informazioni Alpha, non si tratta di una violazione, ma l'<xref:System.Windows.Interop.HwndHost> nel suo complesso supporta solo l'opacità = 1,0 (100%).

- <xref:System.Windows.Interop.HwndHost> verranno visualizzati sopra gli altri elementi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nella stessa finestra di primo livello. Tuttavia, un menu <xref:System.Windows.Controls.ToolTip> o <xref:System.Windows.Controls.ContextMenu> generato è una finestra di primo livello distinta e quindi si comporterà correttamente con <xref:System.Windows.Interop.HwndHost>.

- <xref:System.Windows.Interop.HwndHost> non rispetta l'area di visualizzazione del <xref:System.Windows.UIElement>padre. Si tratta potenzialmente di un problema se si tenta di inserire una classe <xref:System.Windows.Interop.HwndHost> all'interno di un'area di scorrimento o di un <xref:System.Windows.Controls.Canvas>.

#### <a name="notable-differences-in-input-behavior"></a>Differenze rilevanti nel comportamento di input

- In generale, mentre i dispositivi di input sono limitati all'ambito della <xref:System.Windows.Interop.HwndHost> area Win32 ospitata, gli eventi di input passano direttamente a Win32.

- Quando il mouse è posizionato sul <xref:System.Windows.Interop.HwndHost>, l'applicazione non riceve [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eventi del mouse e il valore della proprietà [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.IsMouseOver%2A> verrà `false`.

- Mentre il <xref:System.Windows.Interop.HwndHost> ha lo stato attivo della tastiera, l'applicazione non riceverà [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eventi della tastiera e il valore della proprietà [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> verrà `false`.

- Quando lo stato attivo è all'interno del <xref:System.Windows.Interop.HwndHost> e le modifiche apportate a un altro controllo all'interno del <xref:System.Windows.Interop.HwndHost>, l'applicazione non riceverà gli eventi di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.GotFocus> o <xref:System.Windows.UIElement.LostFocus>.

- Le proprietà e gli eventi dello stilo correlati sono analoghi e non segnalano informazioni quando lo stilo è sopra <xref:System.Windows.Interop.HwndHost>.

<a name="tabbing_mnemonics_accelerators"></a>

## <a name="tabbing-mnemonics-and-accelerators"></a>Tabulazioni, tasti di scelta e tasti di scelta rapida

Le interfacce <xref:System.Windows.Interop.IKeyboardInputSink> e <xref:System.Windows.Interop.IKeyboardInputSite> consentono di creare un'esperienza di tastiera senza problemi per le applicazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e Win32 miste:

- Tabulazione tra componenti Win32 e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]

- Tasti di scelta e tasti di scelta rapida che funzionano sia quando lo stato attivo è all'interno di un componente Win32 che quando è all'interno di un componente WPF.

Le classi <xref:System.Windows.Interop.HwndHost> e <xref:System.Windows.Interop.HwndSource> forniscono entrambe le implementazioni di <xref:System.Windows.Interop.IKeyboardInputSink>, ma non possono gestire tutti i messaggi di input desiderati per scenari più avanzati. Eseguire l'override dei metodi appropriati per ottenere il comportamento di tastiera desiderato.

Le interfacce forniscono solo il supporto per le operazioni eseguite nella transizione tra le aree [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e Win32. All'interno dell'area Win32, il comportamento di tabulazione è interamente controllato dalla logica implementata da Win32 per l'eventuale tabulazione.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Interop.HwndHost>
- <xref:System.Windows.Interop.HwndSource>
- <xref:System.Windows.Interop>
- [Procedura dettagliata: Hosting di un controllo Win32 in WPF](walkthrough-hosting-a-win32-control-in-wpf.md)
- [Procedura dettagliata: hosting di contenuto WPF in Win32](walkthrough-hosting-wpf-content-in-win32.md)
