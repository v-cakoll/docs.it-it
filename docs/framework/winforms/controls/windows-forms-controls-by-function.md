---
title: Controlli Windows Form per funzione
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], by function
- Windows Forms, controls by function
- Windows Forms controls, list of
ms.assetid: 5e65a6c3-5d6f-480d-beb8-b28f865f07e3
ms.openlocfilehash: 3a82642c985b7ec1cee885cdda7b054adbe3dfee
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61969468"
---
# <a name="windows-forms-controls-by-function"></a>Controlli Windows Form per funzione
Windows Form offre i controlli e componenti che svolgono diverse funzioni. La tabella seguente elenca i controlli Windows Form e i componenti in base alla funzione generali. Inoltre, in cui sono presenti più controlli che hanno la stessa funzione, il controllo consigliato è indicato con una nota relativa al controllo sostituiva. In una tabella separata successive, sono elencati i controlli sostituiti con relative sostituzioni consigliate.  
  
> [!NOTE]
>  Nelle tabelle seguenti non elencano ciascun controllo o componente, che è possibile usare in Windows Form. per un elenco più completo, vedere [controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)  
  
## <a name="recommended-controls-and-components-by-function"></a>Controlli e componenti dalla funzione consigliati  
  
|Funzione|Control|Descrizione|  
|--------------|-------------|-----------------|  
|Visualizzazione dei dati|Controllo <xref:System.Windows.Forms.DataGridView>|Il <xref:System.Windows.Forms.DataGridView> controllo fornisce una tabella personalizzabile per la visualizzazione dei dati. Il <xref:System.Windows.Forms.DataGridView> classe consente la personalizzazione di celle, righe, colonne e i bordi. **Nota:**  Il <xref:System.Windows.Forms.DataGridView> controllo fornisce numerose funzionalità di base e avanzate che non sono presenti nel <xref:System.Windows.Forms.DataGrid> controllo. Per altre informazioni, vedere [differenze tra il Windows Form controlli DataGridView e DataGrid](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)|  
|Navigazione e il data binding|<xref:System.Windows.Forms.BindingSource> |Semplifica l'associazione dei controlli in un form ai dati, fornendo la gestione delle valute, la notifica delle modifiche e altri servizi.|  
||Controllo <xref:System.Windows.Forms.BindingNavigator>|Fornisce un'interfaccia di tipo barra degli strumenti per esplorare e modificare i dati in un form.|  
|Modifica del testo|Controllo <xref:System.Windows.Forms.TextBox>|Visualizza il testo immesso in fase di progettazione che può essere modificato dagli utenti in fase di esecuzione, o a livello di codice.|  
||Controllo <xref:System.Windows.Forms.RichTextBox>|Abilita il testo da visualizzare con la formattazione in formato testo normale o RTF (RTF).|  
||Controllo <xref:System.Windows.Forms.MaskedTextBox>|Vincola il formato dell'input dell'utente|  
|Visualizzazione di informazioni (sola lettura)|Controllo <xref:System.Windows.Forms.Label>|Viene visualizzato del testo che gli utenti non possono modificare direttamente.|  
||Controllo <xref:System.Windows.Forms.LinkLabel>|Visualizza il testo come collegamenti ipertestuali e attiva un evento quando l'utente seleziona il testo speciale. In genere il testo è un collegamento a un'altra finestra o un sito Web.|  
||Controllo <xref:System.Windows.Forms.StatusStrip>|Visualizza informazioni sullo stato corrente dell'applicazione usando un'area di frame, in genere nella parte inferiore della forma padre.|  
||Controllo <xref:System.Windows.Forms.ProgressBar>|Visualizza lo stato corrente di un'operazione per l'utente.|  
|Visualizzazione delle pagine Web|Controllo <xref:System.Windows.Forms.WebBrowser>|Consente all'utente di spostarsi tra le pagine Web all'interno del form.|  
|Selezione da un elenco|Controllo <xref:System.Windows.Forms.CheckedListBox>|Visualizza un elenco scorrevole di elementi, ognuno accompagnati da una casella di controllo.|  
||Controllo <xref:System.Windows.Forms.ComboBox>|Consente di visualizzare un elenco di riepilogo a discesa di elementi.|  
||Controllo <xref:System.Windows.Forms.DomainUpDown>|Visualizza un elenco di elementi di testo che gli utenti possono scorrere mediante i pulsanti su e giù.|  
||Controllo <xref:System.Windows.Forms.ListBox>|Visualizza un elenco di elementi grafici (icone) e testo.|  
||Controllo <xref:System.Windows.Forms.ListView>|Visualizza gli elementi in una delle quattro visualizzazioni distinte. Viste predefinite includono solo testo, testo con icone piccole, il testo con icone grandi e una visualizzazione dettagli.|  
||Controllo <xref:System.Windows.Forms.NumericUpDown>|Consente di visualizzare un elenco di numeri che gli utenti possono scorrere mediante i pulsanti su e giù.|  
||Controllo <xref:System.Windows.Forms.TreeView>|Visualizza una raccolta gerarchica di oggetti del nodo che può essere costituito da testo con icone o le caselle di controllo facoltative.|  
|Visualizzazione degli elementi grafici|Controllo <xref:System.Windows.Forms.PictureBox>|File di grafica consente di visualizzare, ad esempio bitmap e icone, in un frame.|  
|Archiviazione di grafica|Controllo <xref:System.Windows.Forms.ImageList>|Funge da un archivio immagini. <xref:System.Windows.Forms.ImageList> i controlli e le immagini che contengono possono essere riutilizzate da un'applicazione a quella successiva.|  
|Impostazione del valore|Controllo <xref:System.Windows.Forms.CheckBox>|Visualizza una casella di controllo e un'etichetta per il testo. In genere usato per impostare le opzioni.|  
||Controllo <xref:System.Windows.Forms.CheckedListBox>|Visualizza un elenco scorrevole di elementi, ognuno accompagnati da una casella di controllo.|  
||Controllo <xref:System.Windows.Forms.RadioButton>|Consente di visualizzare un pulsante che può essere attivato o disattivata.|  
||Controllo <xref:System.Windows.Forms.TrackBar>|Consente agli utenti di impostare i valori su una scala spostando un "thumb" lungo una scala.|  
|L'impostazione della data|Controllo <xref:System.Windows.Forms.DateTimePicker>|Verrà visualizzato un calendario con interfaccia grafico per consentire agli utenti di selezionare una data o ora.|  
||Controllo <xref:System.Windows.Forms.MonthCalendar>|Verrà visualizzato un calendario con interfaccia grafico per consentire agli utenti di selezionare un intervallo di date.|  
|Finestre di dialogo|Controllo <xref:System.Windows.Forms.ColorDialog>|Consente di visualizzare la finestra di dialogo per la selezione colori che consente agli utenti di impostare il colore di un elemento di interfaccia.|  
||Controllo <xref:System.Windows.Forms.FontDialog>|Visualizza una finestra di dialogo che consente agli utenti di impostare un tipo di carattere e i relativi attributi.|  
||Controllo <xref:System.Windows.Forms.OpenFileDialog>|Visualizza una finestra di dialogo che consente agli utenti di individuare e selezionare un file.|  
||Controllo <xref:System.Windows.Forms.PrintDialog>|Visualizza una finestra di dialogo che consente agli utenti di selezionare una stampante e impostare i relativi attributi.|  
||Controllo <xref:System.Windows.Forms.PrintPreviewDialog>|Visualizza una finestra di dialogo che consente di visualizzare modalità un controllo <xref:System.Drawing.Printing.PrintDocument> componente verrà visualizzato quando si stampa.|  
||Controllo <xref:System.Windows.Forms.FolderBrowserDialog>|Visualizza una finestra di dialogo che consente agli utenti di esplorare, creare e infine selezionare una cartella|  
||Controllo <xref:System.Windows.Forms.SaveFileDialog>|Visualizza una finestra di dialogo che consente agli utenti di salvare un file.|  
|Controlli menu|Controllo <xref:System.Windows.Forms.MenuStrip>|Consente di creare menu personalizzati. **Nota:**  Il <xref:System.Windows.Forms.MenuStrip> è progettato per sostituire il <xref:System.Windows.Forms.MainMenu> controllo.|  
||Controllo <xref:System.Windows.Forms.ContextMenuStrip>|Consente di creare menu di scelta rapida personalizzato. **Nota:**  Il <xref:System.Windows.Forms.ContextMenuStrip> è progettato per sostituire il <xref:System.Windows.Forms.ContextMenu> controllo.|  
|Comandi:|Controllo <xref:System.Windows.Forms.Button>|Viene avviata, arrestata o interrompe un processo.|  
||Controllo <xref:System.Windows.Forms.LinkLabel>|Visualizza il testo come collegamenti ipertestuali e attiva un evento quando l'utente seleziona il testo speciale. In genere il testo è un collegamento a un'altra finestra o un sito Web.|  
||Controllo <xref:System.Windows.Forms.NotifyIcon>|Visualizza un'icona nell'area di notifica dello stato della barra delle applicazioni che rappresenta un'applicazione in esecuzione in background.|  
||Controllo <xref:System.Windows.Forms.ToolStrip>|Consente di creare barre degli strumenti che può contenere un Microsoft Windows XP, Microsoft Office, Microsoft Internet Explorer o un aspetto personalizzato, con o senza i temi e con il supporto per l'overflow e il riordinamento degli elementi in fase di esecuzione. **Nota:**  Il <xref:System.Windows.Forms.ToolStrip> controllo è progettato per sostituire il <xref:System.Windows.Forms.ToolBar> controllo.|  
|Guida dell'utente|<xref:System.Windows.Forms.HelpProvider> |Fornisce la Guida online o popup per i controlli.|  
||<xref:System.Windows.Forms.ToolTip> |Fornisce una finestra popup che consente di visualizzare una breve descrizione dello scopo del controllo quando l'utente posiziona il puntatore del mouse sul controllo.|  
|Raggruppamento di altri controlli|Controllo <xref:System.Windows.Forms.Panel>|Raggruppa un set di controlli in un frame senza etichetta, che è possibile scorrere.|  
||Controllo <xref:System.Windows.Forms.GroupBox>|Raggruppa un set di controlli (ad esempio i pulsanti di opzione) su un frame non scorrevole con etichette.|  
||Controllo <xref:System.Windows.Forms.TabControl>|Fornisce una pagina a schede per l'organizzazione e l'accesso in modo efficiente gli oggetti raggruppati.|  
||Controllo <xref:System.Windows.Forms.SplitContainer>|Fornisce due pannelli separati da una barra mobile. **Nota:**  Il <xref:System.Windows.Forms.SplitContainer> controllo è progettato per sostituire il <xref:System.Windows.Forms.Splitter> controllo.|  
||Controllo <xref:System.Windows.Forms.TableLayoutPanel>|Viene illustrato un pannello il cui contenuto è dinamicamente disposto in una griglia composta di righe e colonne.|  
||Controllo <xref:System.Windows.Forms.FlowLayoutPanel>|Rappresenta un pannello che imposta il layout del contenuto orizzontalmente o verticalmente in modo dinamico.|  
|Audio|Controllo <xref:System.Media.SoundPlayer>|File audio viene riprodotta in formato WAV. Suoni possono essere caricati o riprodurre in modo asincrono.|  
  
## <a name="superseded-controls-and-components-by-function"></a>Controlli e componenti dalla funzione sostituiti  
  
|Funzione|Controllo sostituito|Sostitutiva consigliata|  
|--------------|------------------------|-----------------------------|  
|Visualizzazione dei dati|<xref:System.Windows.Forms.DataGrid>|<xref:System.Windows.Forms.DataGridView>|  
|Visualizzazione di informazioni (controlli di sola lettura)|<xref:System.Windows.Forms.StatusBar>|<xref:System.Windows.Forms.StatusStrip>|  
|Controlli menu|<xref:System.Windows.Forms.ContextMenu>|<xref:System.Windows.Forms.ContextMenuStrip>|  
||<xref:System.Windows.Forms.MainMenu>|<xref:System.Windows.Forms.MenuStrip>|  
|Comandi:|<xref:System.Windows.Forms.ToolBar>|<xref:System.Windows.Forms.ToolStrip>|  
||<xref:System.Windows.Forms.StatusBar>|<xref:System.Windows.Forms.StatusStrip>|  
|Layout del form|<xref:System.Windows.Forms.Splitter>|<xref:System.Windows.Forms.SplitContainer>|  
  
## <a name="see-also"></a>Vedere anche

- [Controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)
- [Sviluppo di controlli Windows Form personalizzati con .NET Framework](developing-custom-windows-forms-controls.md)
