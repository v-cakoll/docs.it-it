---
title: Interoperatività di WPF e Win32
ms.date: 03/30/2017
helpviewer_keywords:
- hosting WPF content in Win32 window [WPF]
- HWND interop [WPF]
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 0ffbde0d-701d-45a3-a6fa-dd71f4d9772e
ms.openlocfilehash: 8a0e27d46248bdfd782c2cf650faaf8f3bc29960
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="wpf-and-win32-interoperation"></a>Interoperatività di WPF e Win32
Questo argomento fornisce una panoramica dell'interoperatività tra codice [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce un ambiente completo per la creazione di applicazioni. Tuttavia, se si ha una grande quantità di codice [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], può essere più efficace riutilizzare tale codice.  
  

  
<a name="basics"></a>   
## <a name="wpf-and-win32-interoperation-basics"></a>Nozioni di base sull'interoperatività di WPF e Win32  
 Ci sono due tecniche di base per l'interoperatività tra codice [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
-   Ospitare il contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in una finestra [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Con questa tecnica, è possibile usare le funzionalità grafiche avanzate di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nel framework di una finestra e di un'applicazione [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] standard.  
  
-   Ospitare una finestra [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] nel contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Con questa tecnica, è possibile usare un controllo [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] personalizzato esistente nel contesto di altro contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e passare i dati attraversando i limiti.  
  
 Questo argomento illustra concettualmente queste due tecniche. Per informazioni maggiormente orientate al codice relative all'hosting di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], vedere [Procedura dettagliata: hosting di contenuto WPF in Win32](../../../../docs/framework/wpf/advanced/walkthrough-hosting-wpf-content-in-win32.md). Per informazioni maggiormente orientate al codice relative all'hosting di [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vedere [Procedura dettagliata: hosting di un controllo Win32 in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-win32-control-in-wpf.md).  
  
<a name="projects"></a>   
## <a name="wpf-interoperation-projects"></a>Progetti di interoperatività WPF  
 Le [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono costituite da codice gestito, ma la maggior parte dei programmi [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] esistenti è scritta in codice [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)] non gestito.  Non è possibile chiamare [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] da un programma non gestito vero e proprio. Usando tuttavia l'opzione `/clr` con il compilatore [!INCLUDE[TLA#tla_visualcpp](../../../../includes/tlasharptla-visualcpp-md.md)], è possibile creare un programma misto gestito e non gestito in cui si possono combinare facilmente chiamate ad [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] gestite e non gestite.  
  
 Una complicazione a livello di progetto è costituita dal fatto che non è possibile compilare file [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] in un progetto [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)].  Per ovviare a tale problema, ci sono diverse tecniche di divisione dei progetti.  
  
-   Creare una DLL c# contenente tutti i [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pagine come un assembly compilato e quindi chiedere il [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)] eseguibile includono che [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] come riferimento.  
  
-   Creare c# eseguibile per il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] il contenuto e fare in modo che fanno riferimento a un [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)] [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] che contiene il [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] contenuto.  
  
-   Utilizzare <xref:System.Windows.Markup.XamlReader.Load%2A> caricare qualsiasi [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in fase di esecuzione, anziché compilando il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
-   Non utilizzare [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] e scrivere tutti i [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nel codice, costruendo l'albero degli elementi da <xref:System.Windows.Application>.  
  
 Usare l'approccio che meglio soddisfa le esigenze.  
  
> [!NOTE]
>  Se non si è mai usato [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)] in precedenza, si potrebbero notare alcune "nuove" parole chiave, come `gcnew` e `nullptr`, negli esempi di codice relativi all'interoperatività. Queste parole chiave sostituiscono la sintassi precedente con doppio carattere di sottolineatura (`__gc`) e forniscono una sintassi più naturale per il codice gestito in [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)].  Per altre informazioni sulle funzionalità gestite di [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)], vedere [Estensioni di componenti per le piattaforme di runtime](/cpp/windows/component-extensions-for-runtime-platforms) e [Hello, C++/CLI](http://go.microsoft.com/fwlink/?LinkId=98739).  
  
<a name="hwnds"></a>   
## <a name="how-wpf-uses-hwnds"></a>Modo d'uso degli handle di finestra (HWND) in WPF  
 Per sfruttare al meglio le caratteristiche di "interoperatività HWND" di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], è necessario capire in che modo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa gli handle di finestra (HWND). Per qualsiasi oggetto HWND, non è possibile combinare il rendering [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] con il rendering [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] o il rendering [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] / [!INCLUDE[TLA2#tla_gdiplus](../../../../includes/tla2sharptla-gdiplus-md.md)]. Questo comporta diverse implicazioni. In primo luogo, per combinare questi modelli di rendering, è necessario creare una soluzione di interoperatività e usare segmenti designati di interoperatività per ogni modello di rendering che si sceglie di usare. Il comportamento di rendering crea inoltre una restrizione di "spazio aereo" per le operazioni che la soluzione di interoperatività può completare. Il concetto di "spazio aereo" è illustrato più dettagliatamente nell'argomento [Cenni preliminari sulle aree di tecnologia](../../../../docs/framework/wpf/advanced/technology-regions-overview.md).  
  
 Tutti gli elementi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nella schermata sono supportati da un oggetto HWND. Quando si crea un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window>, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] crea un elemento di primo livello HWND e utilizza un <xref:System.Windows.Interop.HwndSource> per inserire il <xref:System.Windows.Window> e il relativo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenuto all'interno di HWND.  Il resto del contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nell'applicazione condivide tale oggetto HWND singolo. Un'eccezione è costituita da menu, caselle combinate a discesa e altri popup. Poiché questi elementi creano una propria finestra di primo livello, è possibile che un menu [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] superi potenzialmente il bordo dell'oggetto HWND della finestra che lo contiene. Quando si utilizza <xref:System.Windows.Interop.HwndHost> per inserire un elemento HWND in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] informa [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] come nuovo figlio HWND relativo a posizionare il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window> HWND.  
  
 Un concetto correlato a HWND è la trasparenza all'interno di ogni oggetto HWND e tra tali oggetti. Questo concetto è illustrato anche nell'argomento [Cenni preliminari sulle aree di tecnologia](../../../../docs/framework/wpf/advanced/technology-regions-overview.md).  
  
<a name="hosting_a_wpf_page"></a>   
## <a name="hosting-wpf-content-in-a-microsoft-win32-window"></a>Hosting di contenuto WPF in una finestra Microsoft Win32  
 La chiave per ospitare un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] su un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra è la <xref:System.Windows.Interop.HwndSource> classe. Questa classe esegue il wrapping del contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in una finestra [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], consentendo di incorporare il contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nell'[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] come finestra figlio. Nell'approccio che segue, [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono combinati in un'unica applicazione.  
  
1.  Implementare il contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (elemento radice del contenuto) come classe gestita. In genere, la classe eredita da una delle classi che possono contenere più elementi figlio e/o utilizzata come un elemento radice, ad esempio <xref:System.Windows.Controls.DockPanel> o <xref:System.Windows.Controls.Page>. Nei passaggi successivi questa classe è detta classe contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e le istanze della classe sono dette oggetti contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
2.  Implementare un'applicazione [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] con [!INCLUDE[TLA2#tla_cppcli](../../../../includes/tla2sharptla-cppcli-md.md)]. Se si parte da un'applicazione [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)] non gestita esistente, in genere è possibile consentire la chiamata al codice gestito modificando le impostazioni del progetto in modo da includere il flag del compilatore `/clr` (l'ambito completo degli elementi necessari per supportare la compilazione `/clr` non viene illustrato in questo argomento).  
  
3.  Impostare il modello di threading su apartment a thread singolo (STA, Single Threaded Apartment). [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa questo modello di threading.  
  
4.  Gestire la notifica WM_CREATE nella procedura di finestra.  
  
5.  All'interno del gestore (o di una funzione chiamata dal gestore) eseguire queste operazioni:  
  
    1.  Creare un nuovo <xref:System.Windows.Interop.HwndSource> oggetto con la finestra padre HWND come relativo `parent` parametro.  
  
    2.  Creare un'istanza della classe contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
    3.  Assegnare un riferimento di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] oggetto contenuto il <xref:System.Windows.Interop.HwndSource> oggetto <xref:System.Windows.Interop.HwndSource.RootVisual%2A> proprietà.  
  
    4.  Il <xref:System.Windows.Interop.HwndSource> oggetto <xref:System.Windows.Interop.HwndSource.Handle%2A> proprietà contiene l'handle di finestra (HWND). Per ottenere un HWND utilizzabile nella parte non gestita dell'applicazione, eseguire il cast di `Handle.ToPointer()` a un HWND.  
  
6.  Implementare una classe gestita che include un campo statico contenente un riferimento all'oggetto contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Questa classe consente di ottenere un riferimento al [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] oggetto contenuto dal [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] codice, ma più importante, impedisce il <xref:System.Windows.Interop.HwndSource> vengano inavvertitamente sottoposto a garbage collection.  
  
7.  Ricevere notifiche dall'oggetto contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] associando un gestore a uno o più eventi dell'oggetto contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
8.  Comunicare con l'oggetto contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usando il riferimento archiviato nel campo statico per impostare proprietà, chiamare metodi e così via.  
  
> [!NOTE]
>  Tutte le attività di definizione della classe contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], o alcune di esse, per il primo passaggio in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] possono essere eseguite usando la classe parziale predefinita della classe contenuto, se si genera un assembly separato e quindi vi si fa riferimento. Anche se si include in genere un <xref:System.Windows.Application> oggetto come parte della compilazione di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in un assembly, non comporta l'utilizzo che <xref:System.Windows.Application> come parte dell'interoperatività, è sufficiente utilizzare uno o più classi radice per [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file cui fa riferimento per l'applicazione e fare riferimento alle relative classi parziali. La parte restante della procedura è essenzialmente simile a quella appena descritta.  
>   
>  Ognuno di questi passaggi viene illustrato tramite il codice nell'argomento [Procedura dettagliata: hosting di contenuto WPF in Win32](../../../../docs/framework/wpf/advanced/walkthrough-hosting-wpf-content-in-win32.md).  
  
<a name="hosting_an_hwnd"></a>   
## <a name="hosting-a-microsoft-win32-window-in-wpf"></a>Hosting di una finestra Microsoft Win32 in WPF  
 La chiave per ospitare un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra all'interno di altri [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è contenuto il <xref:System.Windows.Interop.HwndHost> classe. Questa classe esegue il wrapping della finestra in un elemento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] che può essere aggiunto a un albero degli elementi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. <xref:System.Windows.Interop.HwndHost> supporta inoltre [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] che consentono di eseguire tali attività come elaborare i messaggi per la finestra di hosting. La procedura di base è la seguente:  
  
1.  Creare un albero degli elementi per un'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (tramite codice o markup). Trovare un punto appropriato e consentito nell'albero degli elementi in cui il <xref:System.Windows.Interop.HwndHost> implementazione può essere aggiunto come elemento figlio. Nei restanti passaggi questo elemento viene chiamato elemento di riserva.  
  
2.  Derivare da <xref:System.Windows.Interop.HwndHost> per creare un oggetto che contiene il [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] contenuto.  
  
3.  Nella classe host, eseguire l'override di <xref:System.Windows.Interop.HwndHost> metodo <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>. Restituire l'oggetto HWND della finestra ospitata. Può essere necessario eseguire il wrapping dei controlli effettivi come finestra figlio della finestra restituita. Il wrapping dei controlli in una finestra host offre un modo semplice per consentire al contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di ricevere notifiche dai controlli. Questa tecnica aiuta a correggere alcuni problemi di [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] relativi alla gestione dei messaggi in corrispondenza del limite del controllo ospitato.  
  
4.  Eseguire l'override di <xref:System.Windows.Interop.HwndHost> metodi <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> e <xref:System.Windows.Interop.HwndHost.WndProc%2A>. Lo scopo è quello di eseguire la pulizia e rimuovere i riferimenti al contenuto ospitato, in particolare se sono stati creati riferimenti a oggetti non gestiti.  
  
5.  Nel file code-behind creare un'istanza della classe di hosting del controllo e impostarla come figlio dell'elemento di riserva. In genere si utilizzerebbe un gestore eventi, ad esempio <xref:System.Windows.FrameworkElement.Loaded>, oppure utilizzare il costruttore di classe parziale. È però anche possibile aggiungere il contenuto di interoperatività tramite un comportamento di runtime.  
  
6.  Elaborare i messaggi della finestra selezionati, ad esempio le notifiche dei controlli. Ci sono due approcci. Entrambi offrono un accesso identico al flusso di messaggi, quindi la scelta dipende per lo più dalle esigenze di programmazione.  
  
    -   L'elaborazione di tutti i messaggi (non solo i messaggi di chiusura) nell'override del messaggio di implementare il <xref:System.Windows.Interop.HwndHost> metodo <xref:System.Windows.Interop.HwndHost.WndProc%2A>.  
  
    -   Dispone l'hosting [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elemento elaborare i messaggi mediante la gestione di <xref:System.Windows.Interop.HwndHost.MessageHook> evento. Questo evento viene generato per ogni messaggio inviato alla procedura di finestra principale della finestra ospitata.  
  
    -   Non è possibile elaborare i messaggi da windows che sono esterne al processo utilizzando <xref:System.Windows.Interop.HwndHost.WndProc%2A>.  
  
7.  Comunicare con la finestra ospitata usando platform invoke per chiamare la funzione `SendMessage` non gestita.  
  
 Questi passaggi consentono di creare un'applicazione che funziona con l'input del mouse. È possibile aggiungere il supporto della tabulazione per la finestra ospitata implementando il <xref:System.Windows.Interop.IKeyboardInputSink> interfaccia.  
  
 Ognuno di questi passaggi viene illustrato tramite il codice nell'argomento [Procedura dettagliata: hosting di un controllo Win32 in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-win32-control-in-wpf.md).  
  
### <a name="hwnds-inside-wpf"></a>Handle di finestra (HWND) in WPF  
 È possibile considerare <xref:System.Windows.Interop.HwndHost> come controllo speciale. (Tecnicamente, <xref:System.Windows.Interop.HwndHost> è un <xref:System.Windows.FrameworkElement> derivata, non un <xref:System.Windows.Controls.Control> classe derivata, ma può essere considerato un controllo ai fini dell'interoperatività.) <xref:System.Windows.Interop.HwndHost> astrae sottostante [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] natura del contenuto ospitato in modo che il resto della [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] considera il contenuto ospitato da un altro oggetto simile al controllo, che deve eseguire il rendering e l'elaborazione dell'input. <xref:System.Windows.Interop.HwndHost> in genere si comporta come qualsiasi altro [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement>, anche se esistono alcune differenze importanti relative all'output (disegno e la grafica) e di input (mouse e tastiera) in base alle limitazioni di HWND sottostante può supportare.  
  
#### <a name="notable-differences-in-output-behavior"></a>Differenze rilevanti nel comportamento di output  
  
-   <xref:System.Windows.FrameworkElement>, ovvero il <xref:System.Windows.Interop.HwndHost> classe base, che dispone di diverse proprietà che implicano modifiche all'interfaccia utente. Queste sono incluse proprietà, ad esempio <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType>, che modifica il layout degli elementi all'interno di tale elemento come padre. La maggior parte di queste proprietà non è tuttavia mappata a possibili equivalenti [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], anche se tali equivalenti possono essere presenti. Poiché un numero elevato di queste proprietà e dei relativi significati è troppo specifico della tecnologia di rendering, il mapping non è una soluzione pratica. Pertanto, l'impostazione di proprietà, ad esempio <xref:System.Windows.FrameworkElement.FlowDirection%2A> in <xref:System.Windows.Interop.HwndHost> non ha alcun effetto.  
  
-   <xref:System.Windows.Interop.HwndHost> non può essere asimmetrici, in caso contrario, ridimensionato o ruotata interessate da una trasformazione.  
  
-   <xref:System.Windows.Interop.HwndHost> non supporta il <xref:System.Windows.UIElement.Opacity%2A> proprietà (riempimenti con fusione alfa). Se il contenuto all'interno di <xref:System.Windows.Interop.HwndHost> esegue <xref:System.Drawing> operazioni che includono informazioni alfa, che non costituisce una violazione, ma la <xref:System.Windows.Interop.HwndHost> nel suo complesso supporta solo l'opacità = 1.0 (100%).  
  
-   <xref:System.Windows.Interop.HwndHost> verrà visualizzata sopra altro [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elementi nella stessa finestra di primo livello. Tuttavia, un <xref:System.Windows.Controls.ToolTip> o <xref:System.Windows.Controls.ContextMenu> menu generata è una finestra separata di primo livello e pertanto si comporterà in modo corretto con <xref:System.Windows.Interop.HwndHost>.  
  
-   <xref:System.Windows.Interop.HwndHost> non rispetta l'area di visualizzazione del relativo padre <xref:System.Windows.UIElement>. Si tratta di potenzialmente un problema se si tenta di inserire un <xref:System.Windows.Interop.HwndHost> classe all'interno di un'area di scorrimento o <xref:System.Windows.Controls.Canvas>.  
  
#### <a name="notable-differences-in-input-behavior"></a>Differenze rilevanti nel comportamento di input  
  
-   In generale, mentre l'ambito dei dispositivi di input all'interno di <xref:System.Windows.Interop.HwndHost> ospitato [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] area, gli eventi di input passare direttamente alla [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  
  
-   Quando il mouse è posizionato il <xref:System.Windows.Interop.HwndHost>, l'applicazione riceve [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gli eventi del mouse e il valore della [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proprietà <xref:System.Windows.UIElement.IsMouseOver%2A> sarà `false`.  
  
-   Mentre il <xref:System.Windows.Interop.HwndHost> con lo stato attivo, l'applicazione non riceverà [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eventi della tastiera e il valore della [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proprietà <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> sarà `false`.  
  
-   Quando lo stato attivo è all'interno di <xref:System.Windows.Interop.HwndHost> e le modifiche apportate a un altro controllo all'interno il <xref:System.Windows.Interop.HwndHost>, l'applicazione non riceverà il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eventi <xref:System.Windows.UIElement.GotFocus> o <xref:System.Windows.UIElement.LostFocus>.  
  
-   Stilo proprietà ed eventi sono analoghi e non comunicano informazioni mentre lo stilo è posizionato correlati <xref:System.Windows.Interop.HwndHost>.  
  
<a name="tabbing_mnemonics_accelerators"></a>   
## <a name="tabbing-mnemonics-and-accelerators"></a>Tabulazioni, tasti di scelta e tasti di scelta rapida  
 Il <xref:System.Windows.Interop.IKeyboardInputSink> e <xref:System.Windows.Interop.IKeyboardInputSite> le interfacce consentono di creare un'esperienza trasparente tastiera per mista [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] applicazioni:  
  
-   Spostamento tra componenti [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tramite il tasto TAB  
  
-   Tasti di scelta e tasti di scelta rapida che funzionano sia quando lo stato attivo è all'interno di un componente Win32 che quando è all'interno di un componente WPF.  
  
 Il <xref:System.Windows.Interop.HwndHost> e <xref:System.Windows.Interop.HwndSource> classi forniscono entrambe le implementazioni di <xref:System.Windows.Interop.IKeyboardInputSink>, ma non gestiscono tutti i messaggi di input che si desidera per scenari più avanzati. Eseguire l'override dei metodi appropriati per ottenere il comportamento di tastiera desiderato.  
  
 Le interfacce forniscono supporto solo per le operazioni eseguite nella transizione tra le aree [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. All'interno dell'area [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], il comportamento di tabulazione è completamente controllato dalla logica implementata da [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] per la tabulazione, se presente.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Interop.HwndHost>  
 <xref:System.Windows.Interop.HwndSource>  
 <xref:System.Windows.Interop>  
 [Procedura dettagliata: Hosting di un controllo Win32 in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-win32-control-in-wpf.md)  
 [Procedura dettagliata: hosting di contenuto WPF in Win32](../../../../docs/framework/wpf/advanced/walkthrough-hosting-wpf-content-in-win32.md)
