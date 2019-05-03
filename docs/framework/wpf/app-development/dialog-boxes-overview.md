---
title: Cenni preliminari sulle finestre di dialogo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- modeless dialog boxes [WPF]
- dialog boxes [WPF]
- message boxes [WPF]
- modal dialog boxes [WPF]
ms.assetid: 0d23d544-a393-4a02-a3aa-d8cd5d3d6511
ms.openlocfilehash: 162414dbd4b0f5e15eceaf73c87c122701fefc4e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052261"
---
# <a name="dialog-boxes-overview"></a>Cenni preliminari sulle finestre di dialogo
Le applicazioni autonome hanno in genere una finestra principale in cui vengono visualizzati i dati principali su cui opera l'applicazione ed espone la funzionalità di elaborazione dei dati tramite [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] meccanismi come le barre dei menu, barre degli strumenti e le barre di stato. In un'applicazione più complessa sono inoltre disponibili finestre aggiuntive per l'esecuzione delle operazioni riportate di seguito:  
  
- Visualizzazione di informazioni specifiche agli utenti.  
  
- Raccolta delle informazioni immesse dagli utenti.  
  
- Visualizzazione e raccolta di informazioni.  
  
 Questi tipi di windows sono dette *finestre di dialogo*, e sono disponibili due tipi: modali e non modali.  
  
 Oggetto *modale* verrà visualizzata la finestra di dialogo da una funzione quando la funzione necessita di ulteriori dati da un utente di continuare. Poiché la raccolta dei dati da parte della funzione dipende dalla finestra di dialogo modale, finché quest'ultima rimane aperta l'utente non potrà attivare altre finestre nell'applicazione. Nella maggior parte dei casi, una finestra di dialogo modale consente a un utente segnalare quando vengono completati con la finestra di dialogo modale premendo un **OK** oppure **Annulla** pulsante. Premere il **OK** pulsante indica che un utente ha immesso dei dati e desidera continuare l'elaborazione con i dati dalla funzione. Premere il **annullare** pulsante indica che un utente desidera arrestare l'esecuzione della funzione. Gli esempi più comuni di finestre di dialogo modali sono dati dalle finestre di apertura, salvataggio e stampa dei dati.  
  
 Oggetto *modale* finestra di dialogo, d'altra parte, non impedire a un utente di attivare altre finestre mentre è aperto. Ad esempio, se un utente desidera cercare occorrenze di una determinata parola in un documento, dalla finestra principale verrà spesso aperta una finestra di dialogo in cui l'utente dovrà immettere la parola che desidera cercare. Poiché la ricerca di una parola non impedisce all'utente di modificare il documento, la finestra di dialogo non deve essere modale. Una finestra di dialogo non modale è senz'altro disponibile un **chiudere** per chiudere la finestra di dialogo ed eventualmente ulteriori pulsanti per eseguire funzioni specifiche, ad esempio un **Trova successivo** pulsante Trova l'occorrenza successiva di word che corrisponde ai criteri di ricerca di una parola.  
  
 Windows Presentation Foundation (WPF) consente di creare diversi tipi di finestre di dialogo, incluse le finestre di messaggio, finestre di dialogo comuni e finestre di dialogo personalizzate. Questo argomento vengono illustrate e il [esempio di finestra di dialogo](https://go.microsoft.com/fwlink/?LinkID=159984) disponibili alcuni esempi.  

<a name="Message_Boxes"></a>   
## <a name="message-boxes"></a>Finestre di messaggio  
 Oggetto *MessageBox* è una finestra di dialogo che può essere utilizzata per visualizzare le informazioni testuali e consentire agli utenti di prendere decisioni più intelligenti con i pulsanti. Di seguito è illustrata una finestra di messaggio in cui vengono visualizzate informazioni di testo, viene posta una domanda e sono disponibili tre pulsanti per fornire una risposta.  
  
 ![Chiude una finestra di dialogo elaboratore di testo che chiede se si desidera salvare le modifiche apportate al documento prima che l'applicazione.](./media/dialog-boxes-overview/word-processor-dialog.png)  
  
 Per creare una finestra di messaggio, si utilizza il <xref:System.Windows.MessageBox> classe. <xref:System.Windows.MessageBox> Consente di configurare il testo della finestra di messaggio, titolo, icona e i pulsanti, usando codice simile al seguente.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxconfigurecodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxconfigurecodebehind)]  
  
 Per visualizzare una finestra di messaggio, si chiama il `static` <xref:System.Windows.MessageBox.Show%2A> metodo, come illustrato nel codice seguente.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowcodebehind)]  
  
 Quando il codice per la visualizzazione di una finestra di messaggio deve rilevare ed elaborare la decisione dell'utente (quale pulsante è stato premuto), può analizzare il risultato della finestra di messaggio, come illustrato nel codice riportato di seguito.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowandresultcodebehind1)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowandresultcodebehind1)]  
  
 Per altre informazioni sull'uso di finestre di messaggio, vedere <xref:System.Windows.MessageBox>, [MessageBox Sample](https://go.microsoft.com/fwlink/?LinkID=160023), e [esempio di finestra di dialogo](https://go.microsoft.com/fwlink/?LinkID=159984).  
  
 Sebbene <xref:System.Windows.MessageBox> può offrire una semplice finestra di dialogo dell'utente, il vantaggio dell'uso <xref:System.Windows.MessageBox> è che è l'unico tipo di finestra visualizzabile dalle applicazioni eseguite all'interno di una sandbox di sicurezza di attendibilità parziale (vedere [Security](../security-wpf.md)), ad esempio [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)].  
  
 Nella maggior parte delle finestre di dialogo vengono visualizzati e raggruppati dati più complessi del risultato di una finestra di messaggio, ad esempio testo, selezione (caselle di controllo), selezione a esclusione reciproca (pulsanti di opzione) e selezione in elenchi (caselle di riepilogo, caselle combinate, elenchi a discesa). Per questo motivo, Windows Presentation Foundation (WPF) offre diverse finestre di dialogo comuni e consente di creare finestre di dialogo, sebbene l'utilizzo di entrambe sia limitato alle applicazioni in esecuzione con attendibilità totale.  
  
<a name="Common_Dialogs"></a>   
## <a name="common-dialog-boxes"></a>Finestre di dialogo comuni  
 In [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] è implementata una varietà di finestre di dialogo riutilizzabili comuni a tutte le applicazioni, incluse le finestre di dialogo per l'apertura, il salvataggio e la stampa di file. Poiché queste finestre di dialogo sono implementate dal sistema operativo, possono essere condivise da tutte le applicazioni eseguite nel sistema operativo, con notevoli vantaggi in termini della coerenza di utilizzo: se un utente utilizza con frequenza una finestra di dialogo basata sul sistema operativo in un'applicazione, non dovrà imparare a utilizzare la stessa finestra in altre applicazioni. Poiché queste finestre di dialogo sono disponibili per tutte le applicazioni e poiché consentono un'esperienza utente coerente, sono note come *finestre di dialogo comuni*.  
  
 Windows Presentation Foundation (WPF) incapsula il file aperto, salvare file e finestre di dialogo comuni di stampa e li espone come classi gestite per l'utilizzo in applicazioni autonome. Questo argomento fornisce alcuni cenni preliminari su ognuna.  
  
<a name="Open_File_Dialog"></a>   
### <a name="open-file-dialog"></a>Finestra di dialogo Apri  
 La finestra di dialogo Apri illustrata di seguito viene utilizzata dalla funzionalità di apertura file per recuperare il nome di un file da aprire.  
  
 ![Una finestra di dialogo Apri che mostra il percorso in cui recuperare il file.](./media/dialog-boxes-overview/open-file-dialog-box.png)  
  
 La finestra di dialogo Apri file comuni viene implementato come le <xref:Microsoft.Win32.OpenFileDialog> classe e si trova nel <xref:Microsoft.Win32> dello spazio dei nomi. Il codice seguente illustra come creare, configurare e visualizzare questa finestra di dialogo, nonché come elaborare il relativo risultato.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#openfiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#openfiledialogboxcodebehind)]  
  
 Per altre informazioni nella finestra di dialogo Apri file, vedere <xref:Microsoft.Win32.OpenFileDialog?displayProperty=nameWithType>.  
  
> [!NOTE]
>  <xref:Microsoft.Win32.OpenFileDialog> può essere utilizzato per recuperare in modo sicuro i nomi di file da applicazioni in esecuzione con attendibilità parziale (vedere [sicurezza](../security-wpf.md)).  
  
<a name="Save_File_Dialog"></a>   
### <a name="save-file-dialog-box"></a>Finestra di dialogo Salva con nome  
 La finestra di dialogo Salva con nome illustrata di seguito viene utilizzata dalla funzionalità di salvataggio file per recuperare il nome di un file da salvare.  
  
 ![Salva con nome finestra di dialogo che mostra il percorso in cui salvare il file.](./media/dialog-boxes-overview/save-file-dialog-box.png)  
  
 Salva con nome finestra di dialogo file comune viene implementata come le <xref:Microsoft.Win32.SaveFileDialog> classe e si trova nel <xref:Microsoft.Win32> dello spazio dei nomi. Il codice seguente illustra come creare, configurare e visualizzare questa finestra di dialogo, nonché come elaborare il relativo risultato.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#savefiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#savefiledialogboxcodebehind)]  
  
 Per altre informazioni sul salvataggio di file nella finestra di dialogo, vedere <xref:Microsoft.Win32.SaveFileDialog?displayProperty=nameWithType>.  
  
<a name="Print_Dialog"></a>   
### <a name="print-dialog-box"></a>Finestra di dialogo Stampa  
 La finestra di dialogo Stampa illustrata di seguito viene utilizzata dalla funzionalità di stampa per la scelta e la configurazione della stampante su cui stampare dati.  
  
 ![Screenshot che mostra una finestra di dialogo di stampa.](./media/dialog-boxes-overview/print-data-dialog-box.png)  
  
 La finestra di dialogo Stampa comune viene implementata come le <xref:System.Windows.Controls.PrintDialog> classe e si trova nel <xref:System.Windows.Controls> dello spazio dei nomi. Il codice seguente illustra come creare, configurare e visualizzare una finestra di dialogo di questo tipo.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#printdialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#printdialogboxcodebehind)]  
  
 Per altre informazioni nella finestra di dialogo di stampa, vedere <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType>. Per informazioni dettagliate sulla stampa nel [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], vedere [Cenni preliminari sulla stampa](../advanced/printing-overview.md).  
  
<a name="Custom_Dialog_Boxes"></a>   
## <a name="custom-dialog-boxes"></a>Finestre di dialogo personalizzate  
 Sebbene le finestre di dialogo comuni siano utili e debbano essere utilizzate quando possibile, non supportano i requisiti delle finestre di dialogo specifiche di vari domini. In questi casi, è necessario creare finestre di dialogo personalizzate. Come verrà illustrato in seguito, una finestra di dialogo è una finestra con particolari comportamenti. <xref:System.Windows.Window> implementa tali comportamenti e, pertanto, si utilizza <xref:System.Windows.Window> creare finestre di dialogo modali e non modali personalizzate.  
  
<a name="Creating_a_Modal_Custom_Dialog_Box"></a>   
### <a name="creating-a-modal-custom-dialog-box"></a>Creazione di una finestra di dialogo modale personalizzata  
 In questo argomento viene illustrato come utilizzare <xref:System.Windows.Window> per creare un'implementazione tipica di finestra di dialogo modale, utilizzando il `Margins` finestra di dialogo, ad esempio (vedere [esempio di finestra di dialogo](https://go.microsoft.com/fwlink/?LinkID=159984)). Il `Margins` nella finestra di dialogo è illustrata nella figura seguente.  
  
 ![Finestra di dialogo margini con i campi di definizione margine sinistro, del margine superiore, del margine destro e il margine inferiore.](./media/dialog-boxes-overview/margin-size-dialog-box.png)  
  
#### <a name="configuring-a-modal-dialog-box"></a>Configurazione di una finestra di dialogo modale  
 L'interfaccia utente di una finestra di dialogo tipica include gli elementi riportati di seguito:  
  
- I diversi controlli necessari per raccogliere i dati desiderati.  
  
- Visualizzazione di un **OK** pulsante che gli utenti fare clic per chiudere la finestra di dialogo, torna alla funzione e continuano l'elaborazione.  
  
- Visualizzazione di un **annullare** pulsante che gli utenti fanno clic per chiudere la finestra di dialogo e interrompere l'elaborazione da parte della funzione.  
  
- Visualizzazione di un **Chiudi** pulsante nella barra del titolo.  
  
- Un'icona.  
  
- Che illustra **Riduci a icona**, **Ingrandisci**, e **Restore** pulsanti.  
  
- Visualizzazione di un **sistema** menu per ridurre al minimo, ingrandire, ripristinare e chiudere la finestra di dialogo.  
  
- L'apertura sopra e al centro della finestra da cui è stata aperta la finestra di dialogo.  
  
- Poiché le finestre di dialogo devono essere, per quanto possibile, ridimensionabili, per impedire che diventino troppo piccole e per fornire utili dimensioni predefinite, è necessario impostare sia dimensioni minime sia dimensioni predefinite.  
  
- Premendo il tasto ESC dovrebbe essere configurato come un tasto di scelta rapida che causa il **annullare** pulsante ai tasti da premere. Questo risultato viene ottenuto impostando il <xref:System.Windows.Controls.Button.IsCancel%2A> proprietà del **annullare** pulsante `true`.  
  
- Premendo il tasto INVIO (o a capo) deve essere configurato come un tasto di scelta rapida che causa il **OK** pulsante ai tasti da premere. Questo risultato viene ottenuto impostando il <xref:System.Windows.Controls.Button.IsDefault%2A> proprietà del **OK** pulsante `true`.  
  
 Il codice seguente illustra questa configurazione.  
  
 [!code-xaml[DialogBoxSample#MarginsDialogBoxMainBitsMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsdialogboxmainbitsmarkup1)]  
[!code-xaml[DialogBoxSample#MarginsDialogBoxMainBitsMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsdialogboxmainbitsmarkup2)]  
  
 [!code-csharp[DialogBoxSample#MarginsDialogBoxMainBitsCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxmainbitscodebehind1)]
 [!code-vb[DialogBoxSample#MarginsDialogBoxMainBitsCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxmainbitscodebehind1)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxMainBitsCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxmainbitscodebehind2)]
[!code-vb[DialogBoxSample#MarginsDialogBoxMainBitsCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxmainbitscodebehind2)]  
  
 L'esperienza utente relativa all'utilizzo di una finestra di dialogo si estende anche alla barra dei menu della finestra da cui viene aperta la finestra di dialogo. Quando una voce di menu attiva una funzione la cui elaborazione richiede interazione da parte dell'utente tramite una finestra di dialogo, nell'intestazione della voce di menu saranno visibili dei puntini di sospensione, come illustrato di seguito.  
  
 [!code-xaml[DialogBoxSample#MainWindowMarginsDialogBoxMenuItemMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#mainwindowmarginsdialogboxmenuitemmarkup1)]  
[!code-xaml[DialogBoxSample#MainWindowMarginsDialogBoxMenuItemMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#mainwindowmarginsdialogboxmenuitemmarkup2)]  
  
 Quando una voce di menu attiva una funzione che comporta la visualizzazione di una finestra di dialogo che non richiede interazione da parte dell'utente, ad esempio una finestra di dialogo Informazioni su, i puntini di sospensione non sono necessari.  
  
#### <a name="opening-a-modal-dialog-box"></a>Apertura di una finestra di dialogo modale  
 Una finestra di dialogo viene in genere visualizzata in seguito alla selezione, da parte dell'utente, di una voce di menu per l'esecuzione di una funzione specifica di un dominio, ad esempio l'impostazione dei margini di un documento in un elaboratore di testo. La visualizzazione di una finestra come una finestra di dialogo è simile alla visualizzazione di una normale finestra, sebbene richieda operazioni di configurazione specifiche. L'intero processo di creazione di un'istanza, configurazione e apertura di una finestra di dialogo viene illustrato nel codice riportato di seguito.  
  
 [!code-csharp[DialogBoxSample#OpenMarginsDialogCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogcodebehind1)]
 [!code-vb[DialogBoxSample#OpenMarginsDialogCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogcodebehind1)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogcodebehind2)]
[!code-vb[DialogBoxSample#OpenMarginsDialogCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogcodebehind2)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogcodebehind3)]
[!code-vb[DialogBoxSample#OpenMarginsDialogCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogcodebehind3)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogCODEBEHIND4](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogcodebehind4)]
[!code-vb[DialogBoxSample#OpenMarginsDialogCODEBEHIND4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogcodebehind4)]  
  
 In questo punto del codice, le informazioni predefinite (i margini correnti) vengono passate alla finestra di dialogo. Viene inoltre impostata la <xref:System.Windows.Window.Owner%2A?displayProperty=nameWithType> proprietà con un riferimento alla finestra che mostra la finestra di dialogo. In generale, è consigliabile impostare sempre il proprietario di una finestra di dialogo per fornire i comportamenti correlati allo stato finestra comuni a tutte le finestre di dialogo (vedere [Panoramica di Windows WPF](wpf-windows-overview.md) per altre informazioni).  
  
> [!NOTE]
>  È necessario specificare un proprietario per supportare [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] automazione per le finestre di dialogo (vedere [Panoramica di automazione interfaccia utente](../../ui-automation/ui-automation-overview.md)).  
  
 Dopo aver configurata la finestra di dialogo, viene visualizzata come modale chiamando il <xref:System.Windows.Window.ShowDialog%2A> (metodo).  
  
#### <a name="validating-user-provided-data"></a>Convalida di dati forniti dall'utente  
 Quando viene aperta una finestra di dialogo e l'utente fornisce i dati necessari, la finestra di dialogo deve garantire che i dati forniti siano validi per i motivi riportati di seguito:  
  
- Da un punto di vista della sicurezza, tutti gli input devono essere convalidati.  
  
- Da un punto di vista specifico del dominio, la convalida dei dati impedisce l'elaborazione di dati errati da parte del codice, che potrebbe potenzialmente generare eccezioni.  
  
- Da un punto di vista dell'esperienza utente, una finestra di dialogo può aiutare l'utente mostrandogli quali dati immessi non sono validi.  
  
- Da un punto di vista delle prestazioni, la convalida dei dati in un'applicazione a più livelli può ridurre il numero di round trip tra il client e i livelli dell'applicazione, in particolare se l'applicazione è composta da servizi Web o database basati su server.  
  
 Per convalidare un controllo associato in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], è necessario definire una regola di convalida e associarlo con l'associazione. Una regola di convalida è una classe personalizzata che deriva da <xref:System.Windows.Controls.ValidationRule>. L'esempio seguente illustra una regola di convalida `MarginValidationRule`, che verifica che un valore associato è un <xref:System.Double> e si trova all'interno di un intervallo specificato.  
  
 [!code-csharp[DialogBoxSample#MarginValidationRuleCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginValidationRule.cs#marginvalidationrulecode)]
 [!code-vb[DialogBoxSample#MarginValidationRuleCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginValidationRule.vb#marginvalidationrulecode)]  
  
 In questo codice, la logica di convalida di una regola di convalida viene implementata eseguendo l'override di <xref:System.Windows.Controls.ValidationRule.Validate%2A> metodo, che convalida i dati e restituisce un oggetto appropriato <xref:System.Windows.Controls.ValidationResult>.  
  
 Per abbinare la regola di convalida al controllo associato, utilizzare il markup riportato di seguito.  
  
 [!code-xaml[DialogBoxSample#MarginsValidationMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsvalidationmarkup1)]  
[!code-xaml[DialogBoxSample#MarginsValidationMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsvalidationmarkup2)]  
[!code-xaml[DialogBoxSample#MarginsValidationMARKUP3](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsvalidationmarkup3)]  
  
 Una volta associata, la regola di convalida [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] verranno automaticamente applicati quando vengono immessi dati nel controllo associato. Quando un elemento control contiene dati non validi, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] verrà visualizzato un bordo rosso intorno al controllo non valido, come illustrato nella figura seguente.  
  
 ![Una finestra di dialogo margini con un bordo rosso intorno al valore di margine sinistro non valido.](./media/dialog-boxes-overview/invalid-left-margin-dialog.png)  
  
 In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] l'utente non rimane bloccato sul controllo non valido finché non vengono immessi dati validi. In questo modo, l'utente sarà libero di spostarsi tra i controlli della finestra di dialogo anche se i dati immessi non sono validi. Tuttavia, ciò significa che un utente può immettere dati non validi e premere il **OK** pulsante. Per questo motivo, il codice deve anche convalidare tutti i controlli in una finestra di dialogo quando il **OK** pulsante viene premuto gestendo il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento.  
  
 [!code-csharp[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxvalidationcodebehind1)]
 [!code-vb[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxvalidationcodebehind1)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxvalidationcodebehind2)]
[!code-vb[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxvalidationcodebehind2)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxvalidationcodebehind3)]
[!code-vb[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxvalidationcodebehind3)]  
  
 Questo codice enumera tutti gli oggetti di dipendenza in una finestra e, se non è validi (come restituito da <xref:System.Windows.Controls.Validation.GetHasError%2A>, il controllo non valido riceve lo stato attivo, il `IsValid` restituzione del metodo `false`, e la finestra viene considerata non valida.  
  
 Dopo essere stata ritenuta valida, la finestra di dialogo può essere chiusa. Questo processo deve inoltre prevedere la restituzione di un risultato alla funzione chiamante.  
  
#### <a name="setting-the-modal-dialog-result"></a>Impostazione del risultato di una finestra di dialogo modale  
 Aprire una finestra di dialogo tramite <xref:System.Windows.Window.ShowDialog%2A> è sostanzialmente equivalente alla chiamata a un metodo: il codice che ha aperto la finestra di dialogo utilizzando <xref:System.Windows.Window.ShowDialog%2A> attende <xref:System.Windows.Window.ShowDialog%2A> restituisce. Quando <xref:System.Windows.Window.ShowDialog%2A> restituisce, il codice che lo ha chiamato deve decidere se continuare o arrestare l'elaborazione, a seconda che l'utente ha premuto il **OK** pulsante o il **Annulla** pulsante. Per facilitare questa decisione, la finestra di dialogo deve restituire la scelta dell'utente come un <xref:System.Boolean> valore restituito dal <xref:System.Windows.Window.ShowDialog%2A> (metodo).  
  
 Quando la **OK** si fa clic sul pulsante, <xref:System.Windows.Window.ShowDialog%2A> dovrebbe restituire `true`. Questo risultato viene ottenuto impostando il <xref:System.Windows.Window.DialogResult%2A> della finestra di dialogo Proprietà finestra quando il **OK** si fa clic sul pulsante.  
  
 [!code-csharp[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxokresultsetcodebehind1)]
 [!code-vb[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxokresultsetcodebehind1)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxokresultsetcodebehind2)]
[!code-vb[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxokresultsetcodebehind2)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxokresultsetcodebehind3)]
[!code-vb[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxokresultsetcodebehind3)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND4](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxokresultsetcodebehind4)]
[!code-vb[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxokresultsetcodebehind4)]  
  
 Si noti che l'impostazione di <xref:System.Windows.Window.DialogResult%2A> proprietà comporta la chiusura della finestra automaticamente, che riduce la necessità di chiamare in modo esplicito <xref:System.Windows.Window.Close%2A>.  
  
 Quando la **annullare** si fa clic sul pulsante, <xref:System.Windows.Window.ShowDialog%2A> deve restituire `false`, che richiede l'impostazione di <xref:System.Windows.Window.DialogResult%2A> proprietà.  
  
 [!code-csharp[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxcancelresultsetcodebehind1)]
 [!code-vb[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxcancelresultsetcodebehind1)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxcancelresultsetcodebehind2)]
[!code-vb[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxcancelresultsetcodebehind2)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxcancelresultsetcodebehind3)]
[!code-vb[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxcancelresultsetcodebehind3)]  
  
 Quando un pulsante <xref:System.Windows.Controls.Button.IsCancel%2A> è impostata su `true` e l'utente preme il **Cancel** pulsante o il tasto ESC, <xref:System.Windows.Window.DialogResult%2A> viene impostata automaticamente su `false`. Il markup seguente ha lo stesso effetto del codice precedente, senza la necessità di gestire il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento.  
  
 [!code-xaml[DialogBoxSample#MarginsDialogDefaultCancelMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsdialogdefaultcancelmarkup)]  
  
 Una finestra di dialogo restituisce automaticamente `false` quando l'utente preme il **Close** pulsante nella barra del titolo o sceglie la **Chiudi** voce di menu dal **sistema** menu.  
  
#### <a name="processing-data-returned-from-a-modal-dialog-box"></a>Elaborazione di dati restituiti da una finestra di dialogo modale  
 Quando <xref:System.Windows.Window.DialogResult%2A> è impostata da una finestra di dialogo, la funzione che l'apertura può ottenere il risultato della finestra dialogo controllando la <xref:System.Windows.Window.DialogResult%2A> proprietà quando <xref:System.Windows.Window.ShowDialog%2A> restituisce.  
  
 [!code-csharp[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogprocessreturncodebehind1)]
 [!code-vb[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogprocessreturncodebehind1)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogprocessreturncodebehind2)]
[!code-vb[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogprocessreturncodebehind2)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogprocessreturncodebehind3)]
[!code-vb[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogprocessreturncodebehind3)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND4](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogprocessreturncodebehind4)]
[!code-vb[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogprocessreturncodebehind4)]  
  
 Se il risultato della finestra di dialogo è `true`, la funzione che usa come un'indicazione per recuperare ed elaborare i dati forniti dall'utente.  
  
> [!NOTE]
>  Dopo aver <xref:System.Windows.Window.ShowDialog%2A> ha restituito, non è possibile riaprire una finestra di dialogo. È invece necessario creare una nuova istanza.  
  
 Se il risultato della finestra di dialogo è `false`, la funzione deve terminare l'elaborazione in modo appropriato.  
  
<a name="Creating_a_Modeless_Custom_Dialog_Box"></a>   
### <a name="creating-a-modeless-custom-dialog-box"></a>Creazione di una finestra di dialogo non modale personalizzata  
 Una finestra di dialogo non modale, ad esempio la finestra di dialogo Trova illustrata di seguito, presenta sostanzialmente lo stesso aspetto di una finestra di dialogo modale.  
  
 ![Screenshot che mostra una finestra di dialogo Trova.](./media/dialog-boxes-overview/find-modeless-dialog-box.png)  
  
 Il comportamento è invece leggermente diverso, come descritto nelle sezioni riportate di seguito.  
  
#### <a name="opening-a-modeless-dialog-box"></a>Apertura di una finestra di dialogo non modale  
 Viene aperta una finestra di dialogo non modale chiamando il <xref:System.Windows.Window.Show%2A> (metodo).  
  
 [!code-xaml[DialogBoxSample#OpenFindDialogMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#openfinddialogmarkup1)]  
  
 [!code-csharp[DialogBoxSample#OpenFindDialogCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openfinddialogcodebehind1)]
 [!code-vb[DialogBoxSample#OpenFindDialogCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openfinddialogcodebehind1)]  
[!code-csharp[DialogBoxSample#OpenFindDialogCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openfinddialogcodebehind2)]
[!code-vb[DialogBoxSample#OpenFindDialogCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openfinddialogcodebehind2)]  
[!code-csharp[DialogBoxSample#OpenFindDialogCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openfinddialogcodebehind3)]
[!code-vb[DialogBoxSample#OpenFindDialogCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openfinddialogcodebehind3)]  
  
 A differenza <xref:System.Windows.Window.ShowDialog%2A>, <xref:System.Windows.Window.Show%2A> restituisce immediatamente. Di conseguenza, la finestra chiamante non può stabilire quando la finestra di dialogo non modale viene chiusa e pertanto non sa quando verificare il risultato della finestra di dialogo o quando ottenere dati dalla finestra di dialogo per continuare l'elaborazione. La finestra di dialogo deve quindi disporre di un modo alternativo per restituire dati alla finestra chiamante.  
  
#### <a name="processing-data-returned-from-a-modeless-dialog-box"></a>Elaborazione di dati restituiti da una finestra di dialogo non modale  
 In questo esempio, il `FindDialogBox` può restituire uno o più risultati di ricerca alla finestra principale, in base al testo cercato senza una frequenza specifica. Come con una finestra di dialogo modale, una finestra di dialogo non modale può restituire risultati utilizzando le proprietà. Tuttavia, la finestra proprietaria della finestra di dialogo deve sapere quando controllare tali proprietà. A tal fine, la finestra di dialogo dovrebbe implementare un evento generato ogni volta che viene trovato il testo. `FindDialogBox` implementa il `TextFoundEvent` a tale scopo, che innanzitutto richiede un delegato.  
  
 [!code-csharp[DialogBoxSample#TextFoundEventHandlerCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/TextFoundEventHandler.cs#textfoundeventhandlercode)]
 [!code-vb[DialogBoxSample#TextFoundEventHandlerCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/TextFoundEventHandler.vb#textfoundeventhandlercode)]  
  
 Usando il `TextFoundEventHandler` delegato `FindDialogBox` implementa il `TextFoundEvent`.  
  
 [!code-csharp[DialogBoxSample#TextFoundEventCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventcodebehind1)]
 [!code-vb[DialogBoxSample#TextFoundEventCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventcodebehind1)]  
[!code-csharp[DialogBoxSample#TextFoundEventCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventcodebehind2)]
[!code-vb[DialogBoxSample#TextFoundEventCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventcodebehind2)]  
  
 Di conseguenza, `Find` può generare l'evento quando viene trovato un risultato della ricerca.  
  
 [!code-csharp[DialogBoxSample#TextFoundEventRaiseCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventraisecodebehind1)]
 [!code-vb[DialogBoxSample#TextFoundEventRaiseCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventraisecodebehind1)]  
[!code-csharp[DialogBoxSample#TextFoundEventRaiseCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventraisecodebehind2)]
[!code-vb[DialogBoxSample#TextFoundEventRaiseCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventraisecodebehind2)]  
[!code-csharp[DialogBoxSample#TextFoundEventRaiseCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventraisecodebehind3)]
[!code-vb[DialogBoxSample#TextFoundEventRaiseCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventraisecodebehind3)]  
[!code-csharp[DialogBoxSample#TextFoundEventRaiseCODEBEHIND4](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventraisecodebehind4)]
[!code-vb[DialogBoxSample#TextFoundEventRaiseCODEBEHIND4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventraisecodebehind4)]  
[!code-csharp[DialogBoxSample#TextFoundEventRaiseCODEBEHIND5](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventraisecodebehind5)]
[!code-vb[DialogBoxSample#TextFoundEventRaiseCODEBEHIND5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventraisecodebehind5)]  
  
 La finestra proprietaria deve quindi eseguire la registrazione e gestire questo evento.  
  
 [!code-csharp[DialogBoxSample#OpenFindDialogResultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openfinddialogresultcodebehind1)]
 [!code-vb[DialogBoxSample#OpenFindDialogResultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openfinddialogresultcodebehind1)]  
[!code-csharp[DialogBoxSample#OpenFindDialogResultCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openfinddialogresultcodebehind2)]
[!code-vb[DialogBoxSample#OpenFindDialogResultCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openfinddialogresultcodebehind2)]  
  
#### <a name="closing-a-modeless-dialog-box"></a>Chiusura di una finestra di dialogo non modale  
 Poiché <xref:System.Windows.Window.DialogResult%2A> non dovrà essere configurata, una finestra di dialogo non modale può essere chiusa utilizzando sistema forniscono meccanismi, inclusi i seguenti:  
  
- Scegliere il **Chiudi** pulsante nella barra del titolo.  
  
- ALT + F4.  
  
- Scelta **Close** dalle **sistema** menu.  
  
 In alternativa, è possibile chiamare <xref:System.Windows.Window.Close%2A> quando il **Chiudi** si fa clic sul pulsante.  
  
 [!code-csharp[DialogBoxSample#FindDialogCloseCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#finddialogclosecodebehind1)]
 [!code-vb[DialogBoxSample#FindDialogCloseCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#finddialogclosecodebehind1)]  
[!code-csharp[DialogBoxSample#FindDialogCloseCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#finddialogclosecodebehind2)]
[!code-vb[DialogBoxSample#FindDialogCloseCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#finddialogclosecodebehind2)]  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sul controllo Popup](../controls/popup-overview.md)
- [Esempio di finestra di dialogo](https://go.microsoft.com/fwlink/?LinkID=159984)
- [Esempio di controllo personalizzato ColorPicker](https://go.microsoft.com/fwlink/?LinkID=159977)
