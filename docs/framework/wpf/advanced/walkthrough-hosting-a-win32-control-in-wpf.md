---
title: Ospitare un controllo Win32 in WPFHost a Win32 control in WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Win32 control in WPF [WPF]
- Win32 code [WPF], WPF interoperation
ms.assetid: a676b1eb-fc55-4355-93ab-df840c41cea0
ms.openlocfilehash: 5185e60640c652b79bd105db54830ac3acc57129
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186744"
---
# <a name="walkthrough-host-a-win32-control-in-wpf"></a>Procedura dettagliata: ospitare un controllo Win32 in WPFWalkthrough: Host a Win32 Control in WPF
Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF) fornisce un ambiente completo per la creazione di applicazioni. Tuttavia, quando si dispone di un investimento sostanziale nel codice Win32, potrebbe essere più efficace riutilizzare almeno parte di tale codice nell'applicazione WPFWPF anziché riscriverlo completamente. WPFWPF fornisce un meccanismo semplice per l'hosting di una finestra Win32, in una pagina WPFWPF.  
  
 In questo argomento viene illustrata un'applicazione, Hosting di [un controllo ListBox Win32 in Esempio WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control), che ospita un controllo casella di riepilogo Win32. Questa procedura generale può essere estesa all'hosting di qualsiasi finestra Win32.This general procedure can be extended to hosting any Win32 window.  

<a name="requirements"></a>
## <a name="requirements"></a>Requisiti  
 In questo argomento si presuppone una familiarità di base con la programmazione di API WPF e Windows.This topic assumes a basic familiarity with BOTH WPF and Windows API programming. Per un'introduzione di base alla programmazione WPFWPF, vedere [Introduzione](../getting-started/index.md). Per un'introduzione alla programmazione API di Windows, vedere uno dei numerosi libri sull'argomento, in particolare *Programming Windows* di Charles Petzold.  
  
 Poiché l'esempio che accompagna questo argomento è implementato in C, utilizza Platform Invocation Services (PInvoke) per accedere all'API di Windows. Una certa familiarità con PInvoke è utile ma non essenziale.  
  
> [!NOTE]
> Questo argomento include vari esempi di codice tratti dall'esempio associato. Tuttavia, per una questione di leggibilità, il codice di esempio completo non è compreso. È possibile ottenere o visualizzare il codice completo da Hosting di [un controllo ListBox Win32 in Esempio WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control).  
  
<a name="basic_procedure"></a>
## <a name="the-basic-procedure"></a>Procedura di base  
 In questa sezione viene descritta la procedura di base per l'hosting di una finestra Win32 in una pagina WPF. Le sezioni rimanenti illustrano in dettaglio i vari passaggi.  
  
 La procedura di hosting base è la seguente:  
  
1. Implementare una pagina WPFWPF per ospitare la finestra. Una tecnica consiste <xref:System.Windows.Controls.Border> nel creare un elemento per riservare una sezione della pagina per la finestra ospitata.  
  
2. Implementare una classe per ospitare <xref:System.Windows.Interop.HwndHost>il controllo che eredita da .  
  
3. In tale classe <xref:System.Windows.Interop.HwndHost> eseguire <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>l'override del membro della classe .  
  
4. Creare la finestra ospitata come elemento figlio della finestra che contiene la pagina WPF. Anche se la programmazione WPF convenzionale non è necessario utilizzare in modo esplicito, la pagina di hosting è una finestra con un handle (HWND). Si riceve la pagina HWND tramite il `hwndParent` parametro del <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> metodo. La finestra ospitata deve essere creata come elemento figlio dell'oggetto HWND.  
  
5. Dopo aver creato la finestra host, restituire l'oggetto HWND della finestra ospitata. Se si desidera ospitare uno o più controlli Win32, in genere si crea una finestra host come elemento figlio di HWND e si creano gli elementi figlio di tale finestra host. Il wrapping dei controlli in una finestra host fornisce un modo semplice per la pagina WPFWPF ricevere notifiche dai controlli, che gestisce alcuni problemi Win32 specifici con le notifiche attraverso il limite HWND.  
  
6. Gestire i messaggi selezionati inviati alla finestra host, ad esempio notifiche dai controlli figlio. Per eseguire questa operazione è possibile procedere in due modi:  
  
    - Se si preferisce gestire i messaggi <xref:System.Windows.Interop.HwndHost.WndProc%2A> nella classe <xref:System.Windows.Interop.HwndHost> di hosting, eseguire l'override del metodo della classe.  
  
    - Se si preferisce che WPFWPF gestisca i messaggi, gestire l'evento della <xref:System.Windows.Interop.HwndHost> classe <xref:System.Windows.Interop.HwndHost.MessageHook> nel code-behind. Questo evento si verifica per ogni messaggio ricevuto dalla finestra ospitata. Se si sceglie questa opzione, <xref:System.Windows.Interop.HwndHost.WndProc%2A>è comunque necessario eseguire l'override di , ma è necessaria solo un'implementazione minima.  
  
7. Eseguire <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> l'override dei metodi e <xref:System.Windows.Interop.HwndHost.WndProc%2A> di <xref:System.Windows.Interop.HwndHost>. È necessario eseguire l'override di questi metodi per soddisfare il <xref:System.Windows.Interop.HwndHost> contratto, ma potrebbe essere necessario fornire solo un'implementazione minima.  
  
8. Nel file code-behind creare un'istanza della classe di hosting <xref:System.Windows.Controls.Border> del controllo e impostarla come elemento figlio dell'elemento destinato ad ospitare la finestra.  
  
9. Comunicare con la finestra ospitata inviandogli messaggi di Microsoft Windows e gestendo i messaggi dalle relative finestre figlio, ad esempio le notifiche inviate dai controlli.  
  
<a name="page_layout"></a>
## <a name="implement-the-page-layout"></a>Implementare il layout di pagina  
 Il layout per la pagina WPFWPF che ospita il controllo ListBox è costituito da due aree. Il lato sinistro della pagina ospita [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] diversi controlli WPFWPF che forniscono un che consente di modificare il controllo Win32. L'angolo superiore destro della pagina include un'area quadrata per il controllo ListBox ospitato.  
  
 Il codice per implementare questo layout è abbastanza semplice. L'elemento radice <xref:System.Windows.Controls.DockPanel> è un che dispone di due elementi figlio. Il primo <xref:System.Windows.Controls.Border> è un elemento che ospita il controllo ListBox.The first is a element that hosts the ListBox Control. Occupa un quadrato 200x200 nell'angolo superiore destro della pagina. Il secondo <xref:System.Windows.Controls.StackPanel> è un elemento che contiene un set di controlli WPFWPF che visualizzano informazioni e consentono di modificare il controllo ListBox impostando le proprietà di interoperabilità esposte. Per ognuno degli elementi che <xref:System.Windows.Controls.StackPanel>sono elementi figlio del , vedere il materiale di riferimento per i vari elementi utilizzati per i dettagli su ciò che questi elementi sono o cosa fanno, questi sono elencati nel codice di esempio qui sotto, ma non verranno spiegati qui (il modello di interoperatività di base non richiede nessuno di essi, vengono forniti per aggiungere un po 'di interattività al campione).  
  
 [!code-xaml[WPFHostingWin32Control#WPFUI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml#wpfui)]  
  
<a name="host_class"></a>
## <a name="implement-a-class-to-host-the-microsoft-win32-control"></a>Implementare una classe per l'hosting del controllo Microsoft Win32  
 La parte centrale di questo esempio è la classe che ospita effettivamente il controllo, ControlHost.cs. Eredita da <xref:System.Windows.Interop.HwndHost>. Il costruttore accetta due parametri, height e width, <xref:System.Windows.Controls.Border> che corrispondono all'altezza e alla larghezza dell'elemento che ospita il controllo ListBox. Questi valori vengono utilizzati in un secondo <xref:System.Windows.Controls.Border> momento per garantire che la dimensione del controllo corrisponda all'elemento.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostClass](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostclass)]
 [!code-vb[WPFHostingWin32Control#ControlHostClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostclass)]  
  
 È anche presente un insieme di costanti. Queste costanti sono in gran parte tratte da Winuser.h e consentono di utilizzare nomi convenzionali quando si chiamano le funzioni Win32.These constants are largely taken from Winuser.h, and allow you to use conventional names when calling Win32 functions.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostConstants](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostconstants)]
 [!code-vb[WPFHostingWin32Control#ControlHostConstants](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostconstants)]  
  
<a name="buildwindowcore"></a>
### <a name="override-buildwindowcore-to-create-the-microsoft-win32-window"></a>Eseguire l'override di BuildWindowCore per creare la finestra Microsoft Win32  
 Eseguire l'override di questo metodo per creare la finestra Win32 che verrà ospitata dalla pagina e rendere la connessione tra la finestra e la pagina. Poiché questo esempio include l'hosting di un controllo ListBox vengono create due finestre. Il primo è la finestra che viene effettivamente ospitata dalla pagina WPFWPF. Il controllo ListBox viene creato come elemento figlio di questa finestra.  
  
 Lo scopo di questo approccio è semplificare il processo di ricezione di notifiche dal controllo. La <xref:System.Windows.Interop.HwndHost> classe consente di elaborare i messaggi inviati alla finestra che ospita. Se si ospita un controllo Win32 direttamente, si ricevono i messaggi inviati al ciclo di messaggi interno del controllo. È possibile visualizzare il controllo e inviare a esso messaggi ma non ricevere le notifiche che il controllo invia alla propria finestra padre. Ciò significa, tra l'altro, che non è possibile in alcun modo rilevare quando l'utente interagisce con il controllo. Creare invece una finestra host e impostare il controllo come elemento figlio di tale finestra. Ciò consente di elaborare i messaggi per la finestra host, incluse le notifiche inviate a essa dal controllo. Per comodità, dal momento che la finestra host è poco più di un semplice wrapper per il controllo, il pacchetto verrà restituito come un controllo ListBox.  
  
<a name="create_the_window_and_listbox"></a>
#### <a name="create-the-host-window-and-listbox-control"></a>Creare la finestra host e il controllo ListBox  
 È possibile utilizzare PInvoke per creare una finestra host per il controllo creando e registrando una classe finestra e così via. Tuttavia, un approccio molto più semplice consiste nel creare una finestra con la classe della finestra "statica" predefinita. Questo approccio rende disponibile la procedura della finestra necessaria per ricevere le notifiche dal controllo e richiede codice minimo.  
  
 L'oggetto HWND del controllo è esposto tramite una proprietà di sola lettura di modo che la pagina host possa usarlo per inviare messaggi al controllo.  
  
 [!code-csharp[WPFHostingWin32Control#IntPtrProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#intptrproperty)]
 [!code-vb[WPFHostingWin32Control#IntPtrProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#intptrproperty)]  
  
 Il controllo ListBox viene creato come elemento figlio della finestra host. L'altezza e la larghezza di entrambe le finestre sono impostate sui valori passati dal costruttore, come illustrato in precedenza. Ciò garantisce che le dimensioni della finestra host e del controllo siano identiche all'area riservata nella pagina.  Dopo la creazione delle finestre, <xref:System.Runtime.InteropServices.HandleRef> nell'esempio viene restituito un oggetto che contiene HWND della finestra host.  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCore](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcore)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCore](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcore)]  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCoreHelper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcorehelper)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCoreHelper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcorehelper)]  
  
<a name="destroywindow_wndproc"></a>
### <a name="implement-destroywindow-and-wndproc"></a>Implementare DestroyWindow e WndProc  
 Oltre a <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>, è necessario <xref:System.Windows.Interop.HwndHost.WndProc%2A> <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> eseguire anche <xref:System.Windows.Interop.HwndHost>l'override dei metodi e di . In questo esempio, i messaggi per il <xref:System.Windows.Interop.HwndHost.MessageHook> controllo vengono gestiti dal gestore, pertanto l'implementazione di <xref:System.Windows.Interop.HwndHost.WndProc%2A> e <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> è minima. Nel caso <xref:System.Windows.Interop.HwndHost.WndProc%2A>di `handled` , `false` impostare su per indicare che il messaggio non è stato gestito e restituire 0. Per <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A>, è sufficiente distruggere la finestra.  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroy](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroy)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroy](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroy)]  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroyHelper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroyhelper)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroyHelper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroyhelper)]  
  
<a name="host_the_control"></a>
## <a name="host-the-control-on-the-page"></a>Ospitare il controllo nella pagina  
 Per ospitare il controllo nella pagina, è innanzitutto necessario creare una nuova istanza della `ControlHost` classe . Passare l'altezza e la larghezza dell'elemento border che contiene il controllo (`ControlHostElement`) al `ControlHost` costruttore. Questo garantisce che le dimensioni di ListBox siano corrette. È quindi possibile ospitare il controllo `ControlHost` nella pagina <xref:System.Windows.Controls.Decorator.Child%2A> assegnando <xref:System.Windows.Controls.Border>l'oggetto alla proprietà dell'host.  
  
 Nell'esempio viene associato un <xref:System.Windows.Interop.HwndHost.MessageHook> gestore `ControlHost` all'evento dell'oggetto per ricevere messaggi dal controllo. Questo evento viene generato per ogni messaggio inviato alla finestra ospitata. In questo caso, si tratta dei messaggi inviati alla finestra che esegue il wrapping del controllo ListBox effettivo, incluse le notifiche dal controllo. L'esempio chiama SendMessage per ottenere informazioni dal controllo e ne modifica il contenuto. I dettagli di come la pagina comunica con il controllo sono illustrati nella sezione successiva.  
  
> [!NOTE]
> Si noti che sono presenti due dichiarazioni PInvoke per SendMessage.Notice that there are two PInvoke declarations for SendMessage. Ciò è necessario `wParam` perché uno utilizza il parametro per passare una stringa e l'altro lo utilizza per passare un numero intero. È necessaria una dichiarazione separata per ogni firma per assicurare che venga eseguito correttamente il marshalling dei dati.  
  
 [!code-csharp[WPFHostingWin32Control#HostWindowClass](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#hostwindowclass)]
 [!code-vb[WPFHostingWin32Control#HostWindowClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#hostwindowclass)]  
  
 [!code-csharp[WPFHostingWin32Control#ControlMsgFilterSendMessage](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#controlmsgfiltersendmessage)]
 [!code-vb[WPFHostingWin32Control#ControlMsgFilterSendMessage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#controlmsgfiltersendmessage)]  
  
<a name="communication"></a>
## <a name="implement-communication-between-the-control-and-the-page"></a>Implementare la comunicazione tra il controllo e la pagina  
 Modificare il controllo inviandogli messaggi di Windows. Il controllo comunica quando l'utente interagisce con esso inviando notifiche alla propria finestra host. L'esempio Hosting a ListBox Control Win32 in WPF include un'interfaccia utente che fornisce diversi esempi di come funziona:The Hosting a [Win32 ListBox Control in WPFWPF](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control) sample includes a UI that provides several examples of how this works:  
  
- Accodare un elemento all'elenco.  
  
- Eliminare l'elemento selezionato dall'elenco.  
  
- Visualizzare il testo dell'elemento attualmente selezionato.  
  
- Visualizzare il numero di elementi nell'elenco.  
  
 L'utente può anche selezionare un elemento nella casella di riepilogo facendo clic su di esso, proprio come farebbero per un'applicazione Win32 convenzionale. I dati visualizzati vengono aggiornati ogni vota che l'utente modifica lo stato della casella di riepilogo, selezionando, aggiungendo o accodando un elemento.  
  
 Per aggiungere elementi, inviare [ `LB_ADDSTRING` ](/windows/desktop/Controls/lb-addstring)alla casella di riepilogo un messaggio . Per eliminare gli [`LB_GETCURSEL`](/windows/desktop/Controls/lb-getcursel) elementi, inviare per ottenere [`LB_DELETESTRING`](/windows/desktop/Controls/lb-deletestring) l'indice della selezione corrente e quindi per eliminare l'elemento. Nell'esempio [`LB_GETCOUNT`](/windows/desktop/Controls/lb-getcount)viene inoltre inviato e viene utilizzato il valore restituito per aggiornare la visualizzazione che mostra il numero di elementi. Entrambe queste [`SendMessage`](/windows/desktop/api/winuser/nf-winuser-sendmessage) istanze di utilizzo di una delle dichiarazioni PInvoke descritte nella sezione precedente.  
  
 [!code-csharp[WPFHostingWin32Control#AppendDeleteText](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#appenddeletetext)]
 [!code-vb[WPFHostingWin32Control#AppendDeleteText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#appenddeletetext)]  
  
 Quando l'utente seleziona un elemento o modifica la selezione, il controllo invia una <xref:System.Windows.Interop.HwndHost.MessageHook> notifica alla finestra host inviandole un [ `WM_COMMAND` messaggio](/windows/desktop/menurc/wm-command)che genera l'evento per la pagina. Il gestore riceve le stesse informazioni della routine della finestra principale della finestra host. Passa inoltre un riferimento a `handled`un valore booleano, . Impostare `handled` `true` su per indicare che il messaggio è stato gestito e non sono necessarie ulteriori elaborazioni.  
  
 [`WM_COMMAND`](/windows/desktop/menurc/wm-command)viene inviato per diversi motivi, pertanto è necessario esaminare l'ID notifica per determinare se si tratta di un evento che si desidera gestire. L'ID è contenuto nella `wParam` parola alta del parametro. Nell'esempio vengono utilizzati operatori bit per bit per estrarre l'ID. Se l'utente ha effettuato o modificato [`LBN_SELCHANGE`](/windows/desktop/Controls/lbn-selchange)la selezione, l'ID sarà .  
  
 Quando [`LBN_SELCHANGE`](/windows/desktop/Controls/lbn-selchange) viene ricevuto, l'esempio ottiene l'indice dell'elemento selezionato inviando al controllo un [ `LB_GETCURSEL` messaggio](/windows/desktop/Controls/lb-getcursel). Per ottenere il testo, <xref:System.Text.StringBuilder>è innanzitutto necessario creare un file . Viene quindi inviato un [ `LB_GETTEXT` messaggio](/windows/desktop/Controls/lb-gettext)al controllo . Passare l'oggetto <xref:System.Text.StringBuilder> `wParam` vuoto come parametro. Quando [`SendMessage`](/windows/desktop/api/winuser/nf-winuser-sendmessage) si <xref:System.Text.StringBuilder> ritorna, il conterrà il testo dell'elemento selezionato. Questo utilizzo [`SendMessage`](/windows/desktop/api/winuser/nf-winuser-sendmessage) di richiede ancora un'altra dichiarazione PInvoke.  
  
 Infine, `handled` impostare su `true` per indicare che il messaggio è stato gestito.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Interop.HwndHost>
- [Interoperatività di WPF e Win32](wpf-and-win32-interoperation.md)
- [Procedura dettagliata: Prima applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
