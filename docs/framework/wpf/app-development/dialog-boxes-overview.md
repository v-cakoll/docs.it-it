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
ms.openlocfilehash: c98d6a45d151d4b683a21e48eaeb5f4a19eaadb1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187446"
---
# <a name="dialog-boxes-overview"></a>Panoramica delle finestre di dialogo
Le applicazioni autonome hanno in genere una finestra principale che visualizza i dati principali su [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] cui opera l'applicazione ed espone la funzionalità per elaborare tali dati attraverso meccanismi come barre dei menu, barre degli strumenti e barre di stato. In un'applicazione più complessa sono inoltre disponibili finestre aggiuntive per l'esecuzione delle operazioni riportate di seguito:  
  
- Visualizzazione di informazioni specifiche agli utenti.  
  
- Raccolta delle informazioni immesse dagli utenti.  
  
- Visualizzazione e raccolta di informazioni.  
  
 Questi tipi di finestre sono noti come finestre di *dialogo*e sono disponibili due tipi: modale e non modale.  
  
 Una finestra di dialogo *modale* viene visualizzata da una funzione quando la funzione richiede dati aggiuntivi da un utente per continuare. Poiché la raccolta dei dati da parte della funzione dipende dalla finestra di dialogo modale, finché quest'ultima rimane aperta l'utente non potrà attivare altre finestre nell'applicazione. Nella maggior parte dei casi, una finestra di dialogo modale consente all'utente di segnalare quando ha terminato con la finestra di dialogo modale premendo un **pulsante OK** o **Annulla.** Premendo il pulsante **OK** si indica che un utente ha immesso dati e desidera che la funzione continui l'elaborazione con tali dati. Premendo il pulsante **Annulla** si indica che un utente desidera interrompere completamente l'esecuzione della funzione. Gli esempi più comuni di finestre di dialogo modali sono dati dalle finestre di apertura, salvataggio e stampa dei dati.  
  
 Una finestra di dialogo *non modale,* d'altra parte, non impedisce a un utente di attivare altre finestre mentre è aperta. Ad esempio, se un utente desidera cercare occorrenze di una determinata parola in un documento, dalla finestra principale verrà spesso aperta una finestra di dialogo in cui l'utente dovrà immettere la parola che desidera cercare. Poiché la ricerca di una parola non impedisce all'utente di modificare il documento, la finestra di dialogo non deve essere modale. Una finestra di dialogo non **modale** fornisce almeno un chiudi pulsante per chiudere la finestra di dialogo e può fornire pulsanti aggiuntivi per eseguire funzioni specifiche, ad esempio un pulsante **Trova successivo** per trovare la parola successiva che corrisponde ai criteri di ricerca di una parola ricerca.  
  
 Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF) consente di creare diversi tipi di finestre di dialogo, tra cui finestre di messaggio, finestre di dialogo comuni e finestre di dialogo personalizzate. In questo argomento vengono illustrati tutti e [l'esempio di finestra di dialogo](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox) fornisce esempi corrispondenti.  

<a name="Message_Boxes"></a>
## <a name="message-boxes"></a>Finestre di messaggio  
 Una *finestra di messaggio* è una finestra di dialogo che può essere utilizzata per visualizzare informazioni testuali e per consentire agli utenti di prendere decisioni con i pulsanti. Di seguito è illustrata una finestra di messaggio in cui vengono visualizzate informazioni di testo, viene posta una domanda e sono disponibili tre pulsanti per fornire una risposta.  
  
 ![Una finestra di dialogo Elaboratore di testi che chiede se si desidera salvare le modifiche apportate al documento prima della chiusura dell'applicazione.](./media/dialog-boxes-overview/word-processor-dialog.png)  
  
 Per creare una finestra di <xref:System.Windows.MessageBox> messaggio, utilizzare la classe . <xref:System.Windows.MessageBox>consente di configurare il testo della finestra di messaggio, il titolo, l'icona e i pulsanti, utilizzando codice simile al seguente.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxconfigurecodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxconfigurecodebehind)]  
  
 Per visualizzare una finestra di `static` <xref:System.Windows.MessageBox.Show%2A> messaggio, chiamare il metodo , come illustrato nel codice seguente.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowcodebehind)]  
  
 Quando il codice per la visualizzazione di una finestra di messaggio deve rilevare ed elaborare la decisione dell'utente (quale pulsante è stato premuto), può analizzare il risultato della finestra di messaggio, come illustrato nel codice riportato di seguito.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowandresultcodebehind1)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowandresultcodebehind1)]  
  
 Per ulteriori informazioni sull'utilizzo <xref:System.Windows.MessageBox>delle finestre di messaggio, vedere Esempio [di finestra di](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/MessageBox)messaggio e Esempio di finestra di [dialogo](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox).  
  
 Sebbene <xref:System.Windows.MessageBox> possa offrire una semplice esperienza utente <xref:System.Windows.MessageBox> della finestra di dialogo, il vantaggio di utilizzare è che è l'unico tipo di finestra che può essere visualizzato dalle applicazioni eseguite all'interno di una sandbox di sicurezza con attendibilità parziale (vedere [Sicurezza](../security-wpf.md)), ad esempio le applicazioni browser XAML (XBAP).  
  
 Nella maggior parte delle finestre di dialogo vengono visualizzati e raggruppati dati più complessi del risultato di una finestra di messaggio, ad esempio testo, selezione (caselle di controllo), selezione a esclusione reciproca (pulsanti di opzione) e selezione in elenchi (caselle di riepilogo, caselle combinate, elenchi a discesa). Per questi, Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF  
  
<a name="Common_Dialogs"></a>
## <a name="common-dialog-boxes"></a>Finestre di dialogo comuni  
 Windows implementa un'ampia gamma di finestre di dialogo riutilizzabili comuni a tutte le applicazioni, incluse le finestre di dialogo per l'apertura di file, il salvataggio di file e la stampa. Poiché queste finestre di dialogo sono implementate dal sistema operativo, possono essere condivise da tutte le applicazioni eseguite nel sistema operativo, con notevoli vantaggi in termini della coerenza di utilizzo: se un utente utilizza con frequenza una finestra di dialogo basata sul sistema operativo in un'applicazione, non dovrà imparare a utilizzare la stessa finestra in altre applicazioni. Poiché queste finestre di dialogo sono disponibili per tutte le applicazioni e contribuiscono a fornire un'esperienza utente coerente, sono note come finestre di *dialogo comuni.*  
  
 Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Questo argomento fornisce alcuni cenni preliminari su ognuna.  
  
<a name="Open_File_Dialog"></a>
### <a name="open-file-dialog"></a>Finestra di dialogo Apri file  
 La finestra di dialogo Apri illustrata di seguito viene utilizzata dalla funzionalità di apertura file per recuperare il nome di un file da aprire.  
  
 ![Una finestra di dialogo Apri che mostra la posizione in cui recuperare il file.](./media/dialog-boxes-overview/open-file-dialog-box.png)  
  
 La finestra di dialogo file <xref:Microsoft.Win32.OpenFileDialog> aperto comune viene <xref:Microsoft.Win32> implementata come classe e si trova nello spazio dei nomi . Il codice seguente illustra come creare, configurare e visualizzare questa finestra di dialogo, nonché come elaborare il relativo risultato.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#openfiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#openfiledialogboxcodebehind)]  
  
 Per ulteriori informazioni sulla finestra di <xref:Microsoft.Win32.OpenFileDialog?displayProperty=nameWithType>dialogo Apri file, vedere .  
  
> [!NOTE]
> <xref:Microsoft.Win32.OpenFileDialog>può essere utilizzato per recuperare in modo sicuro i nomi dei file dalle applicazioni in esecuzione con attendibilità parziale (vedere [Sicurezza](../security-wpf.md)).  
  
<a name="Save_File_Dialog"></a>
### <a name="save-file-dialog-box"></a>Salva file (finestra di dialogo)  
 La finestra di dialogo Salva con nome illustrata di seguito viene utilizzata dalla funzionalità di salvataggio file per recuperare il nome di un file da salvare.  
  
 ![Finestra di dialogo Salva con nome che mostra la posizione in cui salvare il file.](./media/dialog-boxes-overview/save-file-dialog-box.png)  
  
 La finestra di dialogo file <xref:Microsoft.Win32.SaveFileDialog> di salvataggio comune <xref:Microsoft.Win32> viene implementata come classe e si trova nello spazio dei nomi . Il codice seguente illustra come creare, configurare e visualizzare questa finestra di dialogo, nonché come elaborare il relativo risultato.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#savefiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#savefiledialogboxcodebehind)]  
  
 Per ulteriori informazioni sulla finestra di <xref:Microsoft.Win32.SaveFileDialog?displayProperty=nameWithType>dialogo Salva file, vedere .  
  
<a name="Print_Dialog"></a>
### <a name="print-dialog-box"></a>Finestra di dialogo Stampa

La finestra di dialogo Stampa illustrata di seguito viene utilizzata dalla funzionalità di stampa per la scelta e la configurazione della stampante su cui stampare dati.  
  
![Screenshot che mostra una finestra di dialogo Stampa.](./media/dialog-boxes-overview/print-data-dialog-box.png)  
  
La finestra di dialogo <xref:System.Windows.Controls.PrintDialog> di stampa comune viene <xref:System.Windows.Controls> implementata come classe e si trova nello spazio dei nomi . Il codice seguente illustra come creare, configurare e visualizzare una finestra di dialogo di questo tipo.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#printdialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#printdialogboxcodebehind)]  
  
 Per ulteriori informazioni sulla finestra <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType>di dialogo Stampa, vedere . Per informazioni dettagliate sulla stampa in WPFWPF, vedere [Cenni preliminari sulla stampa](../advanced/printing-overview.md).  
  
<a name="Custom_Dialog_Boxes"></a>
## <a name="custom-dialog-boxes"></a>Finestre di dialogo personalizzate

Sebbene le finestre di dialogo comuni siano utili e debbano essere utilizzate quando possibile, non supportano i requisiti delle finestre di dialogo specifiche di vari domini. In questi casi, è necessario creare finestre di dialogo personalizzate. Come verrà illustrato in seguito, una finestra di dialogo è una finestra con particolari comportamenti. <xref:System.Windows.Window>implementa tali comportamenti e, di <xref:System.Windows.Window> conseguenza, si usa per creare finestre di dialogo modali e non modali personalizzate.  
  
<a name="Creating_a_Modal_Custom_Dialog_Box"></a>
### <a name="creating-a-modal-custom-dialog-box"></a>Creazione di una finestra di dialogo personalizzata modale

In questo argomento <xref:System.Windows.Window> viene illustrato come utilizzare per creare `Margins` un'implementazione tipica della finestra di dialogo modale, utilizzando la finestra di dialogo come esempio (vedere Esempio di finestra di [dialogo](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)). La `Margins` finestra di dialogo è illustrata nella figura seguente.  
  
 ![Finestra di dialogo Margini con campi per definire il margine sinistro, il margine superiore, il margine destro e il margine inferiore.](./media/dialog-boxes-overview/margin-size-dialog-box.png)  
  
#### <a name="configuring-a-modal-dialog-box"></a>Configurazione di una finestra di dialogo modale

L'interfaccia utente di una finestra di dialogo tipica include gli elementi riportati di seguito:  
  
- I diversi controlli necessari per raccogliere i dati desiderati.  
  
- Pulsante **OK** su cui gli utenti fanno clic per chiudere la finestra di dialogo, tornare alla funzione e continuare l'elaborazione.  
  
- Un pulsante **Annulla** su cui gli utenti fanno clic per chiudere la finestra di dialogo e interrompere l'ulteriore elaborazione della funzione.  
  
- Un pulsante **Chiudi** nella barra del titolo.  
  
- Un'icona.  
  
- **Pulsanti Riduci a icona**, **Ingrandisci**e **Ripristina.**  
  
- Un menu **di sistema** per ridurre a icona, ingrandire, ripristinare e chiudere la finestra di dialogo.  
  
- Una posizione sopra e al centro della finestra che ha aperto la finestra di dialogo.  
  
- La possibilità di essere ridimensionato dove possibile per evitare che la finestra di dialogo sia troppo piccola e per fornire all'utente una dimensione predefinita utile. A tale scopo, è necessario impostare sia le dimensioni predefinite che una dimensione minima.  
  
- Tasto ESC come scelta rapida da tastiera che determina la pressione del pulsante **Annulla.** A tale scopo, <xref:System.Windows.Controls.Button.IsCancel%2A> impostare la `true`proprietà del pulsante **Annulla** su .  
  
- Il tasto INVIO (o RITORNO) come scelta rapida da tastiera che causa la pressione del pulsante **OK.** A tale scopo, <xref:System.Windows.Controls.Button.IsDefault%2A> impostare la `true`proprietà del pulsante **OK** .  
  
Il codice seguente illustra questa configurazione.  
  
[!code-xaml[MarginsDialogBox XAML file](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml?range=1-16,106-112)]  

[!code-csharp[MarginsDialogBox C# code-behind](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-12,67-68)]
[!code-vb[MarginsDialogBox VB code-behind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-11,61-62)]  
  
L'esperienza utente relativa all'utilizzo di una finestra di dialogo si estende anche alla barra dei menu della finestra da cui viene aperta la finestra di dialogo. Quando una voce di menu attiva una funzione la cui elaborazione richiede interazione da parte dell'utente tramite una finestra di dialogo, nell'intestazione della voce di menu saranno visibili dei puntini di sospensione, come illustrato di seguito.  
  
[!code-xaml[Menu bar of MainWindow.Xaml file](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#L26-L27)]  
  
Quando una voce di menu attiva una funzione che comporta la visualizzazione di una finestra di dialogo che non richiede interazione da parte dell'utente, ad esempio una finestra di dialogo Informazioni su, i puntini di sospensione non sono necessari.  
  
#### <a name="opening-a-modal-dialog-box"></a>Apertura di una finestra di dialogo modale

Una finestra di dialogo viene in genere visualizzata in seguito alla selezione, da parte dell'utente, di una voce di menu per l'esecuzione di una funzione specifica di un dominio, ad esempio l'impostazione dei margini di un documento in un elaboratore di testo. La visualizzazione di una finestra come una finestra di dialogo è simile alla visualizzazione di una normale finestra, sebbene richieda operazioni di configurazione specifiche. L'intero processo di creazione di un'istanza, configurazione e apertura di una finestra di dialogo viene illustrato nel codice riportato di seguito.  
  
[!code-csharp[Opening a modal dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-11,78-88,193-195)]
[!code-vb[Opening a modal dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,58-67,130-132)]  

In questo caso, il codice passa le informazioni predefinite (i margini correnti) alla finestra di dialogo. Imposta inoltre <xref:System.Windows.Window.Owner%2A?displayProperty=nameWithType> la proprietà con un riferimento alla finestra che visualizza la finestra di dialogo. In generale, è sempre necessario impostare il proprietario di una finestra di dialogo per fornire i comportamenti correlati allo stato della finestra comuni a tutte le finestre di dialogo (vedere [Cenni](wpf-windows-overview.md) preliminari su Windows WPF per ulteriori informazioni).

> [!NOTE]
> È necessario fornire un proprietario per supportare l'automazione dell'interfaccia utente per le finestre di dialogo (vedere Cenni preliminari [sull'automazione interfaccia utente).](../../ui-automation/ui-automation-overview.md)

Dopo aver configurato la finestra di dialogo, <xref:System.Windows.Window.ShowDialog%2A> viene visualizzata in modo modale chiamando il metodo .  
  
#### <a name="validating-user-provided-data"></a>Convalida dei dati forniti dall'utente

Quando viene aperta una finestra di dialogo e l'utente fornisce i dati necessari, la finestra di dialogo deve garantire che i dati forniti siano validi per i motivi riportati di seguito:  
  
- Da un punto di vista della sicurezza, tutti gli input devono essere convalidati.  
  
- Da un punto di vista specifico del dominio, la convalida dei dati impedisce l'elaborazione di dati errati da parte del codice, che potrebbe potenzialmente generare eccezioni.  
  
- Da un punto di vista dell'esperienza utente, una finestra di dialogo può aiutare l'utente mostrandogli quali dati immessi non sono validi.  
  
- Da un punto di vista delle prestazioni, la convalida dei dati in un'applicazione a più livelli può ridurre il numero di round trip tra il client e i livelli dell'applicazione, in particolare se l'applicazione è composta da servizi Web o database basati su server.  

Per convalidare un controllo associato in WPFWPF, è necessario definire una regola di convalida e associarla all'associazione. Una regola di convalida è una <xref:System.Windows.Controls.ValidationRule>classe personalizzata che deriva da . Nell'esempio seguente viene `MarginValidationRule`illustrata una regola di <xref:System.Double> convalida, , che verifica che un valore associato sia compreso e rientri in un intervallo specificato.  

[!code-csharp[Margin validation rules](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginValidationRule.cs)]
[!code-vb[Margin validation rules](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginValidationRule.vb)]  

In questo codice, la logica di convalida di <xref:System.Windows.Controls.ValidationRule.Validate%2A> una regola di convalida viene implementata eseguendo l'override del metodo , che convalida i dati e restituisce un oggetto appropriato. <xref:System.Windows.Controls.ValidationResult>  

Per abbinare la regola di convalida al controllo associato, utilizzare il markup riportato di seguito.  
  
[!code-xaml[Associating a validation rule with a control](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml?range=1-16,57-68,111-112)]

Una volta associata la regola di convalida, WPFWPF la applicherà automaticamente quando i dati vengono immessi nel controllo associato. Quando un controllo contiene dati non validi, WPFWPF visualizzerà un bordo rosso intorno al controllo non valido, come illustrato nella figura seguente.  
  
![Una finestra di dialogo Margini con un bordo rosso intorno al valore del margine sinistro non valido.](./media/dialog-boxes-overview/invalid-left-margin-dialog.png)  

WPFWPF non limita un utente al controllo non valido fino a quando non sono stati immessi dati validi. In questo modo, l'utente sarà libero di spostarsi tra i controlli della finestra di dialogo anche se i dati immessi non sono validi. Tuttavia, ciò significa che un utente può immettere dati non validi e premere il pulsante **OK.** Per questo motivo, il codice deve anche convalidare **OK** tutti i controlli <xref:System.Windows.Controls.Primitives.ButtonBase.Click> in una finestra di dialogo quando il OK pulsante viene premuto gestendo l'evento.  
  
[!code-csharp[Validating all controls in a dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,26-29,33-68)]
[!code-vb[Validating all controls in a dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,27-29,33-62)]  

Questo codice enumera tutti gli oggetti dipendenza in una finestra e, <xref:System.Windows.Controls.Validation.GetHasError%2A>se non sono validi `IsValid` (come `false`restituito da , il controllo non valido ottiene lo stato attivo, il metodo restituisce e la finestra viene considerata non valida.  
  
Dopo essere stata ritenuta valida, la finestra di dialogo può essere chiusa. Questo processo deve inoltre prevedere la restituzione di un risultato alla funzione chiamante.  
  
#### <a name="setting-the-modal-dialog-result"></a>Impostazione del risultato della finestra di dialogo modale

L'apertura di <xref:System.Windows.Window.ShowDialog%2A> una finestra di dialogo utilizzando è fondamentalmente <xref:System.Windows.Window.ShowDialog%2A> come <xref:System.Windows.Window.ShowDialog%2A> chiamare un metodo: il codice che ha aperto la finestra di dialogo utilizzando waits fino a restituisce restituisce. Quando <xref:System.Windows.Window.ShowDialog%2A> viene restituito, il codice che lo ha chiamato deve decidere se continuare l'elaborazione o interrompere l'elaborazione, a seconda che l'utente abbia premuto il pulsante **OK** o **Annulla.** Per facilitare questa decisione, la finestra di dialogo <xref:System.Boolean> deve restituire la <xref:System.Windows.Window.ShowDialog%2A> scelta dell'utente come valore restituito dal metodo.  

Quando si fa clic <xref:System.Windows.Window.ShowDialog%2A> sul `true`pulsante **OK,** dovrebbe tornare a . Ciò si ottiene <xref:System.Windows.Window.DialogResult%2A> impostando la proprietà della finestra di dialogo quando si fa clic sul pulsante **OK.**  

[!code-csharp[Responding to the OK button](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,25-27,32-33,67-68)]
[!code-vb[Responding to the OK button](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,27,31-33,61-62)]  

Si noti <xref:System.Windows.Window.DialogResult%2A> che l'impostazione della proprietà determina anche la chiusura automatica della finestra, che riduce la necessità di chiamare <xref:System.Windows.Window.Close%2A>in modo esplicito .  
  
Quando si fa clic <xref:System.Windows.Window.ShowDialog%2A> sul `false`pulsante **Annulla,** <xref:System.Windows.Window.DialogResult%2A> deve restituire , che richiede anche l'impostazione della proprietà .  
  
[!code-csharp[Responding to the Cancel button](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,19-24,67-68)]
[!code-vb[Responding to the Cancel button](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,22-25,61-62)]  

Quando la proprietà <xref:System.Windows.Controls.Button.IsCancel%2A> di un `true` pulsante è impostata su e l'utente <xref:System.Windows.Window.DialogResult%2A> preme il `false`pulsante **Annulla** o il tasto ESC, viene impostato automaticamente su . Il markup seguente ha lo stesso effetto del codice precedente, senza la necessità di gestire l'evento. <xref:System.Windows.Controls.Primitives.ButtonBase.Click>  
  
[!code-xaml[Markup instead of handling the Click event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#L109-L109)]  

Una finestra di `false` dialogo viene restituita automaticamente quando un utente preme il pulsante **Chiudi** nella barra del titolo o sceglie la voce di menu **Chiudi** dal menu **sistema.**  

#### <a name="processing-data-returned-from-a-modal-dialog-box"></a>Elaborazione dei dati restituiti da una finestra di dialogo modaleProcessing data returned from a modal dialog box  

Quando <xref:System.Windows.Window.DialogResult%2A> viene impostata da una finestra di dialogo, la funzione <xref:System.Windows.Window.DialogResult%2A> che <xref:System.Windows.Window.ShowDialog%2A> l'ha aperta può ottenere il risultato della finestra di dialogo controllando la proprietà quando restituisce .  
  
[!code-csharp[Processing data returned from the modal dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,77-79,89-96,194-195)]
[!code-vb[Processing data returned from the modal dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,58,69-73,131-132)]

Se il risultato della finestra di dialogo è `true`, la funzione lo utilizza come segnale per recuperare ed elaborare i dati forniti dall'utente.  
  
> [!NOTE]
> Dopo <xref:System.Windows.Window.ShowDialog%2A> la restituzione, non è possibile riaprire una finestra di dialogo. È invece necessario creare una nuova istanza.

Se il risultato della finestra di dialogo è `false`, la funzione deve terminare l'elaborazione in modo appropriato.  
  
<a name="Creating_a_Modeless_Custom_Dialog_Box"></a>
### <a name="creating-a-modeless-custom-dialog-box"></a>Creazione di una finestra di dialogo personalizzata non modale

Una finestra di dialogo non modale, ad esempio la finestra di dialogo Trova illustrata di seguito, presenta sostanzialmente lo stesso aspetto di una finestra di dialogo modale.  

![Screenshot che mostra una finestra di dialogo Trova.](./media/dialog-boxes-overview/find-modeless-dialog-box.png)  

Il comportamento è invece leggermente diverso, come descritto nelle sezioni riportate di seguito.  
  
#### <a name="opening-a-modeless-dialog-box"></a>Apertura di una finestra di dialogo non modale

Una finestra di dialogo non <xref:System.Windows.Window.Show%2A> modale viene aperta chiamando il metodo .  

[!code-xaml[XAML to define a modeless dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#L21-L22)]  

[!code-csharp[Opening a modeless dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,65-76,194-195)]
[!code-vb[Openng a modeless dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,18-23,131,132)]  

A <xref:System.Windows.Window.ShowDialog%2A> <xref:System.Windows.Window.Show%2A> differenza di , restituisce immediatamente. Di conseguenza, la finestra chiamante non può stabilire quando la finestra di dialogo non modale viene chiusa e pertanto non sa quando verificare il risultato della finestra di dialogo o quando ottenere dati dalla finestra di dialogo per continuare l'elaborazione. La finestra di dialogo deve quindi disporre di un modo alternativo per restituire dati alla finestra chiamante.  
  
#### <a name="processing-data-returned-from-a-modeless-dialog-box"></a>Elaborazione dei dati restituiti da una finestra di dialogo non modaleProcessing data returned from a modeless dialog box  

In questo esempio, il `FindDialogBox` può restituire uno o più risultati di ricerca alla finestra principale, a seconda del testo cercato senza alcuna frequenza specifica. Come con una finestra di dialogo modale, una finestra di dialogo non modale può restituire risultati utilizzando le proprietà. Tuttavia, la finestra proprietaria della finestra di dialogo deve sapere quando controllare tali proprietà. A tal fine, la finestra di dialogo dovrebbe implementare un evento generato ogni volta che viene trovato il testo. `FindDialogBox`implementa `TextFoundEvent` il per questo scopo, che prima richiede un delegato.  

[!code-csharp[The TextFoundEventHandler delegate](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/TextFoundEventHandler.cs)]
[!code-vb[The TextFoundEventHandler delegate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/TextFoundEventHandler.vb)]  

Utilizzando `TextFoundEventHandler` il `FindDialogBox` delegato, `TextFoundEvent`implementa il metodo .
  
[!code-csharp[The TextFound event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-17,125-126)]
[!code-vb[The TextFound event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-15,102-103)]

Di conseguenza, `Find` può generare l'evento quando viene trovato un risultato di ricerca.  
  
[!code-csharp[Raising the TextFound event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-9,50-52,91-94,124-127)]
[!code-vb[Raising the TextFound event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-9,15,60-64,102-103)]  

La finestra proprietaria deve quindi eseguire la registrazione e gestire questo evento.

[!code-csharp[Registering and handling the event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,184-195)]
[!code-vb[Registering and handling the event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,126-132)]  

#### <a name="closing-a-modeless-dialog-box"></a>Chiusura di una finestra di dialogo non modale

Poiché <xref:System.Windows.Window.DialogResult%2A> non è necessario impostare, una finestra di dialogo non modale può essere chiusa utilizzando meccanismi di sistema, inclusi i seguenti:  
  
- Facendo clic sul pulsante **Chiudi** nella barra del titolo.  
  
- ALT+F4.  
  
- Scegliere **Chiudi** dal menu **Sistema.**  
  
In alternativa, il <xref:System.Windows.Window.Close%2A> codice può chiamare quando si fa clic sul pulsante **Chiudi.**  

[!code-csharp[Calling the Close method](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-9,119-126)]
[!code-vb[Calling the Close method](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-9,99-103)]  

## <a name="see-also"></a>Vedere anche

- [Panoramica sul controllo Popup](../controls/popup-overview.md)
- [Esempio di finestra di dialogo](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)
