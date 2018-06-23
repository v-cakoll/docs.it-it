---
title: 'Procedura dettagliata: hosting di un controllo Win32 in WPF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Win32 control in WPF [WPF]
- Win32 code [WPF], WPF interoperation
ms.assetid: a676b1eb-fc55-4355-93ab-df840c41cea0
ms.openlocfilehash: af8491a2887f4a35e2cd9926304948c12a67623a
ms.sourcegitcommit: c217b067985905cb21eafc5dd9a83568d7ff4e45
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2018
ms.locfileid: "36314978"
---
# <a name="walkthrough-hosting-a-win32-control-in-wpf"></a>Procedura dettagliata: hosting di un controllo Win32 in WPF
Windows Presentation Foundation (WPF) fornisce un ambiente completo per la creazione di applicazioni. Tuttavia, quando si dispone di una grande quantità di codice Win32, può risultare più efficiente riutilizzare almeno parte di tale codice nell'applicazione WPF anziché riscriverla completamente. WPF offre un meccanismo semplice per l'hosting di una finestra Win32, in una pagina WPF.  
  
 Questo argomento viene illustrata un'applicazione [che ospita un controllo ListBox Win32 in WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control), che contiene una casella di riepilogo Win32 controllo. Questa procedura generale può essere estesa per l'hosting di tutte le finestre Win32.  
  
  
<a name="requirements"></a>   
## <a name="requirements"></a>Requisiti  
 Questo argomento si presuppone una conoscenza di base con la programmazione WPF sia Win32. Per un'introduzione alla programmazione di WPF, vedere [Getting Started](../../../../docs/framework/wpf/getting-started/index.md). Per un'introduzione alla programmazione Win32, è necessario fare riferimento a uno dei numerosi manuali sull'argomento, in particolare *programmazione Windows* di Charles Petzold.  
  
 Poiché l'esempio che accompagna questo argomento viene implementato in c#, viene usato servizi di Platform Invoke (PInvoke) per accedere all'API Win32. Una certa familiarità con PInvoke è utile ma non essenziali.  
  
> [!NOTE]
>  Questo argomento include vari esempi di codice tratti dall'esempio associato. Tuttavia, per una questione di leggibilità, il codice di esempio completo non è compreso. È possibile ottenere o visualizzare il codice completo [che ospita un controllo ListBox Win32 in WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control).  
  
<a name="basic_procedure"></a>   
## <a name="the-basic-procedure"></a>Procedura di base  
 Questa sezione descrive la procedura di base per l'hosting di una finestra Win32 in una pagina WPF. Le sezioni rimanenti illustrano in dettaglio i vari passaggi.  
  
 La procedura di hosting base è la seguente:  
  
1.  Implementare una pagina WPF per ospitare la finestra. Una tecnica consiste nel creare un <xref:System.Windows.Controls.Border> elemento riservare una sezione della pagina per la finestra di hosting.  
  
2.  Implementare una classe per ospitare il controllo che eredita da <xref:System.Windows.Interop.HwndHost>.  
  
3.  In questa classe, eseguire l'override di <xref:System.Windows.Interop.HwndHost> membro della classe <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>.  
  
4.  Creare la finestra di hosting come elemento figlio della finestra che contiene la pagina WPF. Anche se non è necessario che la programmazione WPF convenzionale rende in modo esplicito di usarla, la pagina di hosting è una finestra con un handle (HWND). Verrà visualizzata la pagina HWND tramite il `hwndParent` parametro del <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> metodo. La finestra ospitata deve essere creata come elemento figlio dell'oggetto HWND.  
  
5.  Dopo aver creato la finestra host, restituire l'oggetto HWND della finestra ospitata. Se si desidera ospitare uno o più controlli Win32, in genere creano una finestra host come elemento figlio di HWND e verificare gli elementi figlio di controlli di tale finestra host. Il wrapping dei controlli in una finestra host fornisce un modo semplice per la pagina WPF ricevere notifiche da controlli, che gestisce i problemi di Win32 particolare con le notifiche attraverso il limite HWND.  
  
6.  Gestire i messaggi selezionati inviati alla finestra host, ad esempio notifiche dai controlli figlio. È possibile ottenere questo risultato in due modi.  
  
    -   Se si preferisce per gestire i messaggi nella classe di hosting, eseguire l'override di <xref:System.Windows.Interop.HwndHost.WndProc%2A> metodo la <xref:System.Windows.Interop.HwndHost> classe.  
  
    -   Se si preferisce che l'applicazione WPF gestiscono i messaggi, gestire il <xref:System.Windows.Interop.HwndHost> classe <xref:System.Windows.Interop.HwndHost.MessageHook> evento nel code-behind. Questo evento si verifica per ogni messaggio ricevuto dalla finestra ospitata. Se si sceglie questa opzione, è comunque necessario sostituire <xref:System.Windows.Interop.HwndHost.WndProc%2A>, ma è necessario solo un'implementazione minima.  
  
7.  Eseguire l'override di <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> e <xref:System.Windows.Interop.HwndHost.WndProc%2A> metodi di <xref:System.Windows.Interop.HwndHost>. È necessario eseguire l'override di questi metodi per soddisfare il <xref:System.Windows.Interop.HwndHost> contratto, ma potrebbe essere necessario solo fornire un'implementazione minima.  
  
8.  Nel file code-behind, creare un'istanza della classe di hosting del controllo e renderlo un elemento figlio del <xref:System.Windows.Controls.Border> elemento che deve ospitare la finestra.  
  
9. Comunicare con la finestra di hosting inviandolo [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] messaggi e gestione delle finestre figlio, ad esempio le notifiche inviate mediante controlli.  
  
<a name="page_layout"></a>   
## <a name="implement-the-page-layout"></a>Implementare il layout di pagina  
 Il layout per la pagina WPF che contiene il controllo casella di riepilogo è costituito da due aree. Il lato sinistro della pagina ospita diversi controlli WPF che forniscono un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] che consente di modificare il controllo di Win32. L'angolo superiore destro della pagina include un'area quadrata per il controllo ListBox ospitato.  
  
 Il codice per implementare questo layout è piuttosto semplice. L'elemento radice è un <xref:System.Windows.Controls.DockPanel> che dispone di due elementi figlio. Il primo è un <xref:System.Windows.Controls.Border> elemento che contiene il controllo casella di riepilogo. Occupa un quadrato 200x200 nell'angolo superiore destro della pagina. Il secondo è un <xref:System.Windows.Controls.StackPanel> elemento che contiene un set di controlli WPF che visualizzano informazioni e consentono di modificare il controllo ListBox impostando proprietà di interoperatività esposte. Per ognuno degli elementi che sono figli del <xref:System.Windows.Controls.StackPanel>, vedere il materiale di riferimento per i diversi elementi utilizzati per informazioni dettagliate su questi elementi sono o le operazioni eseguite, questi sono elencati nell'esempio di codice riportato di seguito, ma non potranno essere illustrati in questo argomento (di base modello di interoperabilità non richiede alcuna di esse, vengono forniti per aggiungere alcune funzionalità interattive per il codice di esempio).  
  
 [!code-xaml[WPFHostingWin32Control#WPFUI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml#wpfui)]  
  
<a name="host_class"></a>   
## <a name="implement-a-class-to-host-the-microsoft-win32-control"></a>Implementare una classe per l'hosting del controllo Microsoft Win32  
 La parte centrale di questo esempio è la classe che ospita effettivamente il controllo, ControlHost.cs. Eredita da <xref:System.Windows.Interop.HwndHost>. Il costruttore accetta due parametri, altezza e la larghezza, che corrisponde all'altezza e larghezza di <xref:System.Windows.Controls.Border> elemento che contiene il controllo casella di riepilogo. Questi valori vengono utilizzati in un secondo momento per assicurarsi che le dimensioni del controllo corrisponda il <xref:System.Windows.Controls.Border> elemento.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostclass)]
 [!code-vb[WPFHostingWin32Control#ControlHostClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostclass)]  
  
 È anche presente un insieme di costanti. Queste costanti sono in gran parte tratte da Winuser. h che consentono di utilizzare nomi convenzionali per chiamare le funzioni Win32.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostConstants](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostconstants)]
 [!code-vb[WPFHostingWin32Control#ControlHostConstants](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostconstants)]  
  
<a name="buildwindowcore"></a>   
### <a name="override-buildwindowcore-to-create-the-microsoft-win32-window"></a>Eseguire l'override di BuildWindowCore per creare la finestra Microsoft Win32  
 Si esegue l'override di questo metodo per creare la finestra Win32 che verrà ospitata dalla pagina, effettuare la connessione tra la finestra e la pagina. Poiché questo esempio include l'hosting di un controllo ListBox vengono create due finestre. Il primo è la finestra effettivamente ospitata dalla pagina WPF. Il controllo ListBox viene creato come elemento figlio di questa finestra.  
  
 Lo scopo di questo approccio è semplificare il processo di ricezione di notifiche dal controllo. Il <xref:System.Windows.Interop.HwndHost> classe consente di elaborare i messaggi inviati alla finestra di hosting. Se si ospita un Win32 controllare direttamente, si ricevono i messaggi inviati al ciclo di messaggi interni del controllo. È possibile visualizzare il controllo e inviare a esso messaggi ma non ricevere le notifiche che il controllo invia alla propria finestra padre. Ciò significa, tra l'altro, che non è possibile in alcun modo rilevare quando l'utente interagisce con il controllo. Creare invece una finestra host e impostare il controllo come elemento figlio di tale finestra. Ciò consente di elaborare i messaggi per la finestra host, incluse le notifiche inviate a essa dal controllo. Per comodità, dal momento che la finestra host è poco più di un semplice wrapper per il controllo, il pacchetto verrà restituito come un controllo ListBox.  
  
<a name="create_the_window_and_listbox"></a>   
#### <a name="create-the-host-window-and-listbox-control"></a>Creare la finestra host e il controllo ListBox  
 È possibile utilizzare PInvoke per creare una finestra host per il controllo tramite la creazione e la registrazione di una classe della finestra e così via. Tuttavia, un approccio molto più semplice consiste nel creare una finestra con la classe della finestra "statica" predefinita. Questo approccio rende disponibile la procedura della finestra necessaria per ricevere le notifiche dal controllo e richiede codice minimo.  
  
 L'oggetto HWND del controllo è esposto tramite una proprietà di sola lettura di modo che la pagina host possa usarlo per inviare messaggi al controllo.  
  
 [!code-csharp[WPFHostingWin32Control#IntPtrProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#intptrproperty)]
 [!code-vb[WPFHostingWin32Control#IntPtrProperty](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#intptrproperty)]  
  
 Il controllo ListBox viene creato come elemento figlio della finestra host. L'altezza e la larghezza di entrambe le finestre sono impostate sui valori passati dal costruttore, come illustrato in precedenza. Ciò garantisce che le dimensioni della finestra host e del controllo siano identiche all'area riservata nella pagina.  Dopo aver create le finestre, nell'esempio viene restituito un <xref:System.Runtime.InteropServices.HandleRef> oggetto che contiene l'HWND della finestra host.  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCore](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcore)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCore](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcore)]  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCoreHelper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcorehelper)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCoreHelper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcorehelper)]  
  
<a name="destroywindow_wndproc"></a>   
### <a name="implement-destroywindow-and-wndproc"></a>Implementare DestroyWindow e WndProc  
 Oltre ai <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>, è inoltre necessario sostituire il <xref:System.Windows.Interop.HwndHost.WndProc%2A> e <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> metodi del <xref:System.Windows.Interop.HwndHost>. In questo esempio, vengono gestiti i messaggi per il controllo per il <xref:System.Windows.Interop.HwndHost.MessageHook> gestore, pertanto l'implementazione di <xref:System.Windows.Interop.HwndHost.WndProc%2A> e <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> è minimo. Nel caso di <xref:System.Windows.Interop.HwndHost.WndProc%2A>, impostare `handled` a `false` per indicare che il messaggio non è stato gestito e restituiscono 0. Per <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A>, eliminare semplicemente la finestra.  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroy](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroy)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroy](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroy)]  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroyHelper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroyhelper)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroyHelper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroyhelper)]  
  
<a name="host_the_control"></a>   
## <a name="host-the-control-on-the-page"></a>Ospitare il controllo nella pagina  
 Per ospitare il controllo nella pagina, creare innanzitutto una nuova istanza di `ControlHost` classe. Passare l'altezza e larghezza dell'elemento bordo che contiene il controllo (`ControlHostElement`) per il `ControlHost` costruttore. Questo garantisce che le dimensioni di ListBox siano corrette. Quindi ospitare il controllo nella pagina assegnando il `ControlHost` dell'oggetto per il <xref:System.Windows.Controls.Decorator.Child%2A> proprietà dell'host <xref:System.Windows.Controls.Border>.  
  
 L'esempio consente di collegare un gestore per il <xref:System.Windows.Interop.HwndHost.MessageHook> evento del `ControlHost` per ricevere messaggi dal controllo. Questo evento viene generato per ogni messaggio inviato alla finestra ospitata. In questo caso, si tratta dei messaggi inviati alla finestra che esegue il wrapping del controllo ListBox effettivo, incluse le notifiche dal controllo. L'esempio chiama SendMessage per ottenere informazioni dal controllo e ne modifica il contenuto. I dettagli di come la pagina comunica con il controllo sono illustrati nella sezione successiva.  
  
> [!NOTE]
>  Si noti che esistono due dichiarazioni PInvoke per SendMessage. Ciò è necessario perché una viene utilizzato il `wParam` parametro da passare una stringa e l'altro viene utilizzato per passare un numero intero. È necessaria una dichiarazione separata per ogni firma per assicurare che venga eseguito correttamente il marshalling dei dati.  
  
 [!code-csharp[WPFHostingWin32Control#HostWindowClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#hostwindowclass)]
 [!code-vb[WPFHostingWin32Control#HostWindowClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#hostwindowclass)]  
  
 [!code-csharp[WPFHostingWin32Control#ControlMsgFilterSendMessage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#controlmsgfiltersendmessage)]
 [!code-vb[WPFHostingWin32Control#ControlMsgFilterSendMessage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#controlmsgfiltersendmessage)]  
  
<a name="communication"></a>   
## <a name="implement-communication-between-the-control-and-the-page"></a>Implementare la comunicazione tra il controllo e la pagina  
 Modificare il controllo mediante l'invio dei messaggi di Windows. Il controllo comunica quando l'utente interagisce con esso inviando notifiche alla propria finestra host. Il [che ospita un controllo ListBox Win32 in WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control) esempio include un'interfaccia utente che fornisce alcuni esempi del funzionamento:  
  
-   Accodare un elemento all'elenco.  
  
-   Eliminare l'elemento selezionato dall'elenco.  
  
-   Visualizzare il testo dell'elemento attualmente selezionato.  
  
-   Visualizzare il numero di elementi nell'elenco.  
  
 L'utente può anche selezionare un elemento nella casella di riepilogo, fare clic su di esso, esattamente come accade per un'applicazione Win32 convenzionale. I dati visualizzati vengono aggiornati ogni vota che l'utente modifica lo stato della casella di riepilogo, selezionando, aggiungendo o accodando un elemento.  
  
 Per aggiungere elementi, inviare la casella di riepilogo un' [ `LB_ADDSTRING` messaggio](https://msdn.microsoft.com/library/windows/desktop/bb775181(v=vs.85).aspx). Per eliminare gli elementi, inviare [ `LB_GETCURSEL` ](https://msdn.microsoft.com/library/windows/desktop/bb775197(v=vs.85).aspx) per ottenere l'indice della selezione corrente e quindi [ `LB_DELETESTRING` ](https://msdn.microsoft.com/library/windows/desktop/bb775183(v=vs.85).aspx) eliminare l'elemento. Nell'esempio vengono inoltre inviati [ `LB_GETCOUNT` ](https://msdn.microsoft.com/library/windows/desktop/bb775195(v=vs.85).aspx), il valore restituito viene utilizzato per aggiornare la visualizzazione che mostra il numero di elementi. Entrambe queste istanze del [ `SendMessage` ](https://msdn.microsoft.com/library/windows/desktop/ms644950(v=vs.85).aspx) utilizzare una delle dichiarazioni PInvoke illustrate nella sezione precedente.  
  
 [!code-csharp[WPFHostingWin32Control#AppendDeleteText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#appenddeletetext)]
 [!code-vb[WPFHostingWin32Control#AppendDeleteText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#appenddeletetext)]  
  
 Quando l'utente seleziona un elemento o si modifica la selezione, il controllo notifica alla finestra host mediante l'invio un [ `WM_COMMAND` messaggio](https://msdn.microsoft.com/library/windows/desktop/ms647591(v=vs.85).aspx), che genera il <xref:System.Windows.Interop.HwndHost.MessageHook> evento per la pagina. Il gestore riceve le stesse informazioni della routine della finestra principale della finestra host. Inoltre, viene passato un riferimento a un valore booleano, `handled`. È impostato `handled` a `true` per indicare che il messaggio è stato gestito e senza ulteriore elaborazione è necessaria.  
  
 [`WM_COMMAND`](https://msdn.microsoft.com/library/windows/desktop/ms647591(v=vs.85).aspx) viene inviato per svariati motivi, pertanto è necessario esaminare l'ID di notifica per determinare se si tratta di un evento che si desidera gestire. L'ID è contenuto in word alto del `wParam` parametro. Nell'esempio vengono utilizzati gli operatori bit per bit per estrarre l'ID. Se l'utente ha effettuato o modificato la selezione, l'ID sarà [ `LBN_SELCHANGE` ](https://msdn.microsoft.com/library/windows/desktop/bb775161(v=vs.85).aspx).  
  
 Quando si [ `LBN_SELCHANGE` ](https://msdn.microsoft.com/library/windows/desktop/bb775161(v=vs.85).aspx) viene ricevuto, l'esempio Ottiene l'indice dell'elemento selezionato inviando il controllo un [ `LB_GETCURSEL` messaggio](https://msdn.microsoft.com/library/windows/desktop/bb775197(v=vs.85).aspx). Per ottenere il testo, creare innanzitutto un <xref:System.Text.StringBuilder>. È quindi inviare il controllo un' [ `LB_GETTEXT` messaggio](https://msdn.microsoft.com/library/windows/desktop/bb761313(v=vs.85).aspx). Passare il vuoto <xref:System.Text.StringBuilder> dell'oggetto come il `wParam` parametro. Quando si [ `SendMessage` ](https://msdn.microsoft.com/library/windows/desktop/ms644950(v=vs.85).aspx) viene restituito, il <xref:System.Text.StringBuilder> conterrà il testo dell'elemento selezionato. Questo utilizzo di [ `SendMessage` ](https://msdn.microsoft.com/library/windows/desktop/ms644950(v=vs.85).aspx) richiede un'altra dichiarazione di PInvoke.  
  
 Infine, impostare `handled` a `true` per indicare che il messaggio è stato gestito.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Interop.HwndHost>  
 [Interoperatività di WPF e Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 [Procedura dettagliata: Prima applicazione desktop WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)
