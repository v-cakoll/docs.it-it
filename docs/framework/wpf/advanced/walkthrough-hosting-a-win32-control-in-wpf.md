---
title: 'Procedura dettagliata: Hosting di un controllo Win32 in WPF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Win32 control in WPF [WPF]
- Win32 code [WPF], WPF interoperation
ms.assetid: a676b1eb-fc55-4355-93ab-df840c41cea0
ms.openlocfilehash: 13845eb662064e0ac1db913bedc0b21214292db5
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2019
ms.locfileid: "58412318"
---
# <a name="walkthrough-hosting-a-win32-control-in-wpf"></a>Procedura dettagliata: Hosting di un controllo Win32 in WPF
Windows Presentation Foundation (WPF) fornisce un ambiente completo per la creazione di applicazioni. Tuttavia, quando si dispone di un investimento sostanziale nel codice Win32, potrebbe essere più efficace riutilizzare almeno parte di tale codice nell'applicazione WPF anziché riscriverlo completamente. WPF fornisce un meccanismo semplice per l'hosting di una finestra Win32, in una pagina WPF.  
  
 Questo argomento illustra in dettaglio un'applicazione [che ospita un controllo Win32 ListBox in WPF Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control), che contiene una casella di riepilogo Win32 controllo. Questa procedura generale può essere estesa all'hosting di qualsiasi finestra Win32.  
  
  
<a name="requirements"></a>   
## <a name="requirements"></a>Requisiti  
 In questo argomento presuppone una conoscenza di base con la programmazione WPF sia all'API di Windows. Per un'introduzione alla programmazione WPF, vedere [introduttiva](../getting-started/index.md). Per un'introduzione alla programmazione dell'API di Windows, vedere uno qualsiasi dei numerosi manuali sull'argomento, in particolare *programmazione Windows* di Charles Petzold.  
  
 Poiché l'esempio che accompagna questo argomento è implementato in C#, rende l'uso di servizi di Platform Invoke (PInvoke) per accedere all'API di Windows. Una certa conoscenza di PInvoke è utile, ma non essenziale.  
  
> [!NOTE]
>  Questo argomento include vari esempi di codice tratti dall'esempio associato. Tuttavia, per una questione di leggibilità, il codice di esempio completo non è compreso. È possibile ottenere o visualizzare il codice completo [che ospita un controllo Win32 ListBox in WPF Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control).  
  
<a name="basic_procedure"></a>   
## <a name="the-basic-procedure"></a>Procedura di base  
 In questa sezione illustra la procedura di base per l'hosting di una finestra Win32 in una pagina WPF. Le sezioni rimanenti illustrano in dettaglio i vari passaggi.  
  
 La procedura di hosting base è la seguente:  
  
1.  Implementare una pagina WPF per contenere la finestra. Una tecnica consiste nel creare un <xref:System.Windows.Controls.Border> elemento riservare una sezione della pagina per la finestra ospitata.  
  
2.  Implementare una classe per ospitare il controllo che eredita da <xref:System.Windows.Interop.HwndHost>.  
  
3.  In questa classe, eseguire l'override di <xref:System.Windows.Interop.HwndHost> membro della classe <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>.  
  
4.  Creare la finestra ospitata come elemento figlio della finestra che contiene la pagina WPF. Sebbene la programmazione WPF convenzionale non è necessario eseguire in modo esplicito di usarla, la pagina di hosting è una finestra con un handle (HWND). Si riceve l'oggetto HWND della pagina tramite il `hwndParent` parametro il <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> (metodo). La finestra ospitata deve essere creata come elemento figlio dell'oggetto HWND.  
  
5.  Dopo aver creato la finestra host, restituire l'oggetto HWND della finestra ospitata. Se si desidera ospitare uno o più controlli Win32, in genere crea una finestra host come elemento figlio dell'oggetto HWND e verificare gli elementi figlio di controlli della finestra host. Il wrapping dei controlli in una finestra host offre un modo semplice per la pagina WPF ricevere le notifiche dai controlli, che illustra alcuni problemi di Win32 particolari con le notifiche oltre il limite HWND.  
  
6.  Gestire i messaggi selezionati inviati alla finestra host, ad esempio notifiche dai controlli figlio. È possibile ottenere questo risultato in due modi.  
  
    -   Se si preferisce gestire i messaggi nella classe di hosting, eseguire l'override di <xref:System.Windows.Interop.HwndHost.WndProc%2A> metodo di <xref:System.Windows.Interop.HwndHost> classe.  
  
    -   Se si preferisce che l'applicazione WPF che gestiscono i messaggi, gestire le <xref:System.Windows.Interop.HwndHost> classe <xref:System.Windows.Interop.HwndHost.MessageHook> eventi nel code-behind. Questo evento si verifica per ogni messaggio ricevuto dalla finestra ospitata. Se si sceglie questa opzione, è necessario comunque eseguire l'override <xref:System.Windows.Interop.HwndHost.WndProc%2A>, ma è necessario solo un'implementazione minima.  
  
7.  Eseguire l'override di <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> e <xref:System.Windows.Interop.HwndHost.WndProc%2A> metodi <xref:System.Windows.Interop.HwndHost>. È necessario eseguire l'override di questi metodi per soddisfare il <xref:System.Windows.Interop.HwndHost> contratto, ma si potrebbe essere necessario solo fornire un'implementazione minima.  
  
8.  Nel file code-behind, creare un'istanza della classe di hosting del controllo e impostarla come figlio di <xref:System.Windows.Controls.Border> elemento che deve ospitare la finestra.  
  
9. Comunicare con la finestra ospitata inviando a tale [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] messaggi e gestendo i messaggi dalle relative finestre figlio, ad esempio le notifiche inviate mediante controlli.  
  
<a name="page_layout"></a>   
## <a name="implement-the-page-layout"></a>Implementare il layout di pagina  
 Il layout della pagina WPF che ospita il controllo ListBox è costituito da due aree. Il lato sinistro della pagina ospita vari controlli WPF che forniscono un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] che consente di modificare il controllo di Win32. L'angolo superiore destro della pagina include un'area quadrata per il controllo ListBox ospitato.  
  
 Il codice per implementare questo layout è abbastanza semplice. L'elemento radice è un <xref:System.Windows.Controls.DockPanel> che dispone di due elementi figlio. Il primo è un <xref:System.Windows.Controls.Border> elemento che ospita il controllo ListBox. Occupa un quadrato 200x200 nell'angolo superiore destro della pagina. Il secondo è un <xref:System.Windows.Controls.StackPanel> elemento che contiene un set di controlli WPF che visualizzano informazioni e consentono di modificare il controllo ListBox impostando proprietà di interoperatività esposte. Per ognuno degli elementi figlio del <xref:System.Windows.Controls.StackPanel>, vedere il materiale di riferimento per i vari elementi usati per informazioni dettagliate su questi elementi sono o le operazioni eseguite, questi sono elencati nell'esempio di codice riportato di seguito, ma non saranno illustrati in questo argomento (di base modello di interoperatività non richiede alcuna di esse, vengono forniti per aggiungere interattività all'esempio).  
  
 [!code-xaml[WPFHostingWin32Control#WPFUI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml#wpfui)]  
  
<a name="host_class"></a>   
## <a name="implement-a-class-to-host-the-microsoft-win32-control"></a>Implementare una classe per l'hosting del controllo Microsoft Win32  
 La parte centrale di questo esempio è la classe che ospita effettivamente il controllo, ControlHost.cs. Eredita da <xref:System.Windows.Interop.HwndHost>. Il costruttore accetta due parametri, altezza e larghezza, che corrispondono all'altezza e larghezza del <xref:System.Windows.Controls.Border> elemento che ospita il controllo ListBox. Questi valori vengono utilizzati in un secondo momento per assicurarsi che le dimensioni del controllo corrisponda il <xref:System.Windows.Controls.Border> elemento.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostClass](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostclass)]
 [!code-vb[WPFHostingWin32Control#ControlHostClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostclass)]  
  
 È anche presente un insieme di costanti. Queste costanti sono ampiamente tratte da Winuser. h e consentono di usare nomi convenzionali quando si chiamano funzioni Win32.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostConstants](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostconstants)]
 [!code-vb[WPFHostingWin32Control#ControlHostConstants](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostconstants)]  
  
<a name="buildwindowcore"></a>   
### <a name="override-buildwindowcore-to-create-the-microsoft-win32-window"></a>Eseguire l'override di BuildWindowCore per creare la finestra Microsoft Win32  
 Si esegue l'override di questo metodo per creare la finestra di Win32 che verrà ospitata dalla pagina e stabilire la connessione tra la finestra e la pagina. Poiché questo esempio include l'hosting di un controllo ListBox vengono create due finestre. Il primo è la finestra effettivamente ospitata dalla pagina WPF. Il controllo ListBox viene creato come elemento figlio di questa finestra.  
  
 Lo scopo di questo approccio è semplificare il processo di ricezione di notifiche dal controllo. Il <xref:System.Windows.Interop.HwndHost> classe consente di elaborare i messaggi inviati alla finestra ospitata. Se si ospita un Win32 controllare direttamente, si ricevono i messaggi inviati al ciclo di messaggi interno del controllo. È possibile visualizzare il controllo e inviare a esso messaggi ma non ricevere le notifiche che il controllo invia alla propria finestra padre. Ciò significa, tra l'altro, che non è possibile in alcun modo rilevare quando l'utente interagisce con il controllo. Creare invece una finestra host e impostare il controllo come elemento figlio di tale finestra. Ciò consente di elaborare i messaggi per la finestra host, incluse le notifiche inviate a essa dal controllo. Per comodità, dal momento che la finestra host è poco più di un semplice wrapper per il controllo, il pacchetto verrà restituito come un controllo ListBox.  
  
<a name="create_the_window_and_listbox"></a>   
#### <a name="create-the-host-window-and-listbox-control"></a>Creare la finestra host e il controllo ListBox  
 È possibile usare PInvoke per creare una finestra host per il controllo creando e registrando una classe della finestra e così via. Tuttavia, un approccio molto più semplice consiste nel creare una finestra con la classe della finestra "statica" predefinita. Questo approccio rende disponibile la procedura della finestra necessaria per ricevere le notifiche dal controllo e richiede codice minimo.  
  
 L'oggetto HWND del controllo è esposto tramite una proprietà di sola lettura di modo che la pagina host possa usarlo per inviare messaggi al controllo.  
  
 [!code-csharp[WPFHostingWin32Control#IntPtrProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#intptrproperty)]
 [!code-vb[WPFHostingWin32Control#IntPtrProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#intptrproperty)]  
  
 Il controllo ListBox viene creato come elemento figlio della finestra host. L'altezza e la larghezza di entrambe le finestre sono impostate sui valori passati dal costruttore, come illustrato in precedenza. Ciò garantisce che le dimensioni della finestra host e del controllo siano identiche all'area riservata nella pagina.  Dopo aver creato il windows, nell'esempio viene restituito un <xref:System.Runtime.InteropServices.HandleRef> oggetto che contiene l'oggetto HWND della finestra host.  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCore](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcore)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCore](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcore)]  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCoreHelper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcorehelper)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCoreHelper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcorehelper)]  
  
<a name="destroywindow_wndproc"></a>   
### <a name="implement-destroywindow-and-wndproc"></a>Implementare DestroyWindow e WndProc  
 Oltre a <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>, è anche necessario eseguire l'override di <xref:System.Windows.Interop.HwndHost.WndProc%2A> e <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> metodi del <xref:System.Windows.Interop.HwndHost>. In questo esempio, vengono gestiti i messaggi per il controllo per il <xref:System.Windows.Interop.HwndHost.MessageHook> gestore, pertanto l'implementazione di <xref:System.Windows.Interop.HwndHost.WndProc%2A> e <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> è minimo. Nel caso del <xref:System.Windows.Interop.HwndHost.WndProc%2A>, impostare `handled` a `false` per indicare che il messaggio non è stato gestito e restituiscono 0. Per <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A>, eliminare semplicemente la finestra.  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroy](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroy)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroy](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroy)]  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroyHelper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroyhelper)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroyHelper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroyhelper)]  
  
<a name="host_the_control"></a>   
## <a name="host-the-control-on-the-page"></a>Ospitare il controllo nella pagina  
 Per ospitare il controllo nella pagina, si creerà una nuova istanza di `ControlHost` classe. Passare l'altezza e la larghezza dell'elemento bordo che contiene il controllo (`ControlHostElement`) per il `ControlHost` costruttore. Questo garantisce che le dimensioni di ListBox siano corrette. Quindi ospitare il controllo nella pagina assegnando il `ControlHost` dell'oggetto per il <xref:System.Windows.Controls.Decorator.Child%2A> proprietà dell'host <xref:System.Windows.Controls.Border>.  
  
 L'esempio associa un gestore per il <xref:System.Windows.Interop.HwndHost.MessageHook> eventi del `ControlHost` per ricevere messaggi dal controllo. Questo evento viene generato per ogni messaggio inviato alla finestra ospitata. In questo caso, si tratta dei messaggi inviati alla finestra che esegue il wrapping del controllo ListBox effettivo, incluse le notifiche dal controllo. L'esempio chiama SendMessage per ottenere informazioni dal controllo e ne modifica il contenuto. I dettagli di come la pagina comunica con il controllo sono illustrati nella sezione successiva.  
  
> [!NOTE]
>  Si noti che esistono due dichiarazioni PInvoke per SendMessage. Ciò è necessario poiché una Usa il `wParam` parametro da passare una stringa e l'altra lo usa per passare un numero intero. È necessaria una dichiarazione separata per ogni firma per assicurare che venga eseguito correttamente il marshalling dei dati.  
  
 [!code-csharp[WPFHostingWin32Control#HostWindowClass](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#hostwindowclass)]
 [!code-vb[WPFHostingWin32Control#HostWindowClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#hostwindowclass)]  
  
 [!code-csharp[WPFHostingWin32Control#ControlMsgFilterSendMessage](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#controlmsgfiltersendmessage)]
 [!code-vb[WPFHostingWin32Control#ControlMsgFilterSendMessage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#controlmsgfiltersendmessage)]  
  
<a name="communication"></a>   
## <a name="implement-communication-between-the-control-and-the-page"></a>Implementare la comunicazione tra il controllo e la pagina  
 Modificare il controllo tramite l'invio di messaggi di Windows. Il controllo comunica quando l'utente interagisce con esso inviando notifiche alla propria finestra host. Il [che ospita un controllo Win32 ListBox in WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control) esempio include un'interfaccia utente che fornisce alcuni esempi del relativo funzionamento:  
  
-   Accodare un elemento all'elenco.  
  
-   Eliminare l'elemento selezionato dall'elenco.  
  
-   Visualizzare il testo dell'elemento attualmente selezionato.  
  
-   Visualizzare il numero di elementi nell'elenco.  
  
 L'utente può anche selezionare un elemento nella casella di riepilogo facendo clic su di esso, esattamente come accade per un'applicazione Win32 convenzionale. I dati visualizzati vengono aggiornati ogni vota che l'utente modifica lo stato della casella di riepilogo, selezionando, aggiungendo o accodando un elemento.  
  
 Per accodare elementi, inviare la casella di riepilogo un' [ `LB_ADDSTRING` messaggio](/windows/desktop/Controls/lb-addstring). Per eliminare gli elementi, inviare [ `LB_GETCURSEL` ](/windows/desktop/Controls/lb-getcursel) per ottenere l'indice della selezione corrente e quindi [ `LB_DELETESTRING` ](/windows/desktop/Controls/lb-deletestring) per eliminare l'elemento. Nell'esempio vengono inoltre inviati [ `LB_GETCOUNT` ](/windows/desktop/Controls/lb-getcount), il valore restituito viene utilizzato per aggiornare la visualizzazione che mostra il numero di elementi. Entrambe queste istanze di [ `SendMessage` ](/windows/desktop/api/winuser/nf-winuser-sendmessage) usare una delle dichiarazioni PInvoke illustrate nella sezione precedente.  
  
 [!code-csharp[WPFHostingWin32Control#AppendDeleteText](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#appenddeletetext)]
 [!code-vb[WPFHostingWin32Control#AppendDeleteText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#appenddeletetext)]  
  
 Quando l'utente seleziona un elemento o la selezione viene modificato, il controllo notifica alla finestra inviando un [ `WM_COMMAND` messaggio](/windows/desktop/menurc/wm-command), che genera il <xref:System.Windows.Interop.HwndHost.MessageHook> eventi per la pagina. Il gestore riceve le stesse informazioni della routine della finestra principale della finestra host. Inoltre, viene passato un riferimento a un valore booleano, `handled`. Si imposta `handled` a `true` per indicare che il messaggio è stato gestito e necessita di alcuna ulteriore elaborazione.  
  
 [`WM_COMMAND`](/windows/desktop/menurc/wm-command) viene inviato per diversi motivi, pertanto è necessario esaminare l'ID della notifica per determinare se si tratta di un evento che si desidera gestire. L'ID è contenuto nel word alto del `wParam` parametro. L'esempio Usa operatori bit per bit per estrarre l'ID. Se l'utente ha effettuato o modificato la selezione, l'ID sarà [ `LBN_SELCHANGE` ](/windows/desktop/Controls/lbn-selchange).  
  
 Quando [ `LBN_SELCHANGE` ](/windows/desktop/Controls/lbn-selchange) viene ricevuto, il codice di esempio Ottiene l'indice dell'elemento selezionato inviando al controllo un [ `LB_GETCURSEL` messaggio](/windows/desktop/Controls/lb-getcursel). Per ottenere il testo, creare innanzitutto un <xref:System.Text.StringBuilder>. Quindi inviare al controllo un [ `LB_GETTEXT` messaggio](/windows/desktop/Controls/lb-gettext). Passare il vuoto <xref:System.Text.StringBuilder> dell'oggetto come il `wParam` parametro. Quando [ `SendMessage` ](/windows/desktop/api/winuser/nf-winuser-sendmessage) termina, il <xref:System.Text.StringBuilder> conterrà il testo dell'elemento selezionato. Questo uso di [ `SendMessage` ](/windows/desktop/api/winuser/nf-winuser-sendmessage) richiede un'altra dichiarazione di PInvoke.  
  
 Infine, impostare `handled` a `true` per indicare che il messaggio è stato gestito.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Interop.HwndHost>
- [Interoperatività di WPF e Win32](wpf-and-win32-interoperation.md)
- [Procedura dettagliata: Prima applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
