---
title: Controlli Windows Form per funzione
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], by function
- Windows Forms, controls by function
- Windows Forms controls, list of
ms.assetid: 5e65a6c3-5d6f-480d-beb8-b28f865f07e3
ms.openlocfilehash: 3a82642c985b7ec1cee885cdda7b054adbe3dfee
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115479"
---
# <a name="windows-forms-controls-by-function"></a>Controlli Windows Form per funzione
Windows Form offre i controlli e componenti che svolgono diverse funzioni. La tabella seguente elenca i controlli Windows Form e i componenti in base alla funzione generali. Inoltre, in cui sono presenti più controlli che hanno la stessa funzione, il controllo consigliato è indicato con una nota relativa al controllo sostituiva. In una tabella separata successive, sono elencati i controlli sostituiti con relative sostituzioni consigliate.  
  
> [!NOTE]
>  Nelle tabelle seguenti non elencano ciascun controllo o componente, che è possibile usare in Windows Form. per un elenco più completo, vedere [controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)  
  
## <a name="recommended-controls-and-components-by-function"></a>Controlli e componenti dalla funzione consigliati  
  
|Funzione|Control|Descrizione|  
|--------------|-------------|-----------------|  
|Visualizzazione dei dati|<xref:System.Windows.Forms.DataGridView> controllo|Il <xref:System.Windows.Forms.DataGridView> controllo fornisce una tabella personalizzabile per la visualizzazione dei dati. Il <xref:System.Windows.Forms.DataGridView> classe consente la personalizzazione di celle, righe, colonne e i bordi. **Nota:**  Il <xref:System.Windows.Forms.DataGridView> controllo fornisce numerose funzionalità di base e avanzate che non sono presenti nel <xref:System.Windows.Forms.DataGrid> controllo. Per altre informazioni, vedere [differenze tra il Windows Form controlli DataGridView e DataGrid](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)|  
|Navigazione e il data binding|<xref:System.Windows.Forms.BindingSource> component|Semplifica l'associazione dei controlli in un form ai dati, fornendo la gestione delle valute, la notifica delle modifiche e altri servizi.|  
||<xref:System.Windows.Forms.BindingNavigator> controllo|Fornisce un'interfaccia di tipo barra degli strumenti per esplorare e modificare i dati in un form.|  
|Modifica del testo|<xref:System.Windows.Forms.TextBox> controllo|Visualizza il testo immesso in fase di progettazione che può essere modificato dagli utenti in fase di esecuzione, o a livello di codice.|  
||<xref:System.Windows.Forms.RichTextBox> controllo|Abilita il testo da visualizzare con la formattazione in formato testo normale o RTF (RTF).|  
||<xref:System.Windows.Forms.MaskedTextBox> controllo|Vincola il formato dell'input dell'utente|  
|Visualizzazione di informazioni (sola lettura)|<xref:System.Windows.Forms.Label> controllo|Viene visualizzato del testo che gli utenti non possono modificare direttamente.|  
||<xref:System.Windows.Forms.LinkLabel> controllo|Visualizza il testo come collegamenti ipertestuali e attiva un evento quando l'utente seleziona il testo speciale. In genere il testo è un collegamento a un'altra finestra o un sito Web.|  
||<xref:System.Windows.Forms.StatusStrip> controllo|Visualizza informazioni sullo stato corrente dell'applicazione usando un'area di frame, in genere nella parte inferiore della forma padre.|  
||<xref:System.Windows.Forms.ProgressBar> controllo|Visualizza lo stato corrente di un'operazione per l'utente.|  
|Visualizzazione delle pagine Web|<xref:System.Windows.Forms.WebBrowser> controllo|Consente all'utente di spostarsi tra le pagine Web all'interno del form.|  
|Selezione da un elenco|<xref:System.Windows.Forms.CheckedListBox> controllo|Visualizza un elenco scorrevole di elementi, ognuno accompagnati da una casella di controllo.|  
||<xref:System.Windows.Forms.ComboBox> controllo|Consente di visualizzare un elenco di riepilogo a discesa di elementi.|  
||<xref:System.Windows.Forms.DomainUpDown> controllo|Visualizza un elenco di elementi di testo che gli utenti possono scorrere mediante i pulsanti su e giù.|  
||<xref:System.Windows.Forms.ListBox> controllo|Visualizza un elenco di elementi grafici (icone) e testo.|  
||<xref:System.Windows.Forms.ListView> controllo|Visualizza gli elementi in una delle quattro visualizzazioni distinte. Viste predefinite includono solo testo, testo con icone piccole, il testo con icone grandi e una visualizzazione dettagli.|  
||<xref:System.Windows.Forms.NumericUpDown> controllo|Consente di visualizzare un elenco di numeri che gli utenti possono scorrere mediante i pulsanti su e giù.|  
||<xref:System.Windows.Forms.TreeView> controllo|Visualizza una raccolta gerarchica di oggetti del nodo che può essere costituito da testo con icone o le caselle di controllo facoltative.|  
|Visualizzazione degli elementi grafici|<xref:System.Windows.Forms.PictureBox> controllo|File di grafica consente di visualizzare, ad esempio bitmap e icone, in un frame.|  
|Archiviazione di grafica|<xref:System.Windows.Forms.ImageList> controllo|Funge da un archivio immagini. <xref:System.Windows.Forms.ImageList> i controlli e le immagini che contengono possono essere riutilizzate da un'applicazione a quella successiva.|  
|Impostazione del valore|<xref:System.Windows.Forms.CheckBox> controllo|Visualizza una casella di controllo e un'etichetta per il testo. In genere usato per impostare le opzioni.|  
||<xref:System.Windows.Forms.CheckedListBox> controllo|Visualizza un elenco scorrevole di elementi, ognuno accompagnati da una casella di controllo.|  
||<xref:System.Windows.Forms.RadioButton> controllo|Consente di visualizzare un pulsante che può essere attivato o disattivata.|  
||<xref:System.Windows.Forms.TrackBar> controllo|Consente agli utenti di impostare i valori su una scala spostando un "thumb" lungo una scala.|  
|L'impostazione della data|<xref:System.Windows.Forms.DateTimePicker> controllo|Verrà visualizzato un calendario con interfaccia grafico per consentire agli utenti di selezionare una data o ora.|  
||<xref:System.Windows.Forms.MonthCalendar> controllo|Verrà visualizzato un calendario con interfaccia grafico per consentire agli utenti di selezionare un intervallo di date.|  
|Finestre di dialogo|<xref:System.Windows.Forms.ColorDialog> controllo|Consente di visualizzare la finestra di dialogo per la selezione colori che consente agli utenti di impostare il colore di un elemento di interfaccia.|  
||<xref:System.Windows.Forms.FontDialog> controllo|Visualizza una finestra di dialogo che consente agli utenti di impostare un tipo di carattere e i relativi attributi.|  
||<xref:System.Windows.Forms.OpenFileDialog> controllo|Visualizza una finestra di dialogo che consente agli utenti di individuare e selezionare un file.|  
||<xref:System.Windows.Forms.PrintDialog> controllo|Visualizza una finestra di dialogo che consente agli utenti di selezionare una stampante e impostare i relativi attributi.|  
||<xref:System.Windows.Forms.PrintPreviewDialog> controllo|Visualizza una finestra di dialogo che consente di visualizzare modalità un controllo <xref:System.Drawing.Printing.PrintDocument> componente verrà visualizzato quando si stampa.|  
||<xref:System.Windows.Forms.FolderBrowserDialog> controllo|Visualizza una finestra di dialogo che consente agli utenti di esplorare, creare e infine selezionare una cartella|  
||<xref:System.Windows.Forms.SaveFileDialog> controllo|Visualizza una finestra di dialogo che consente agli utenti di salvare un file.|  
|Controlli menu|<xref:System.Windows.Forms.MenuStrip> controllo|Consente di creare menu personalizzati. **Nota:**  Il <xref:System.Windows.Forms.MenuStrip> è progettato per sostituire il <xref:System.Windows.Forms.MainMenu> controllo.|  
||<xref:System.Windows.Forms.ContextMenuStrip> controllo|Consente di creare menu di scelta rapida personalizzato. **Nota:**  Il <xref:System.Windows.Forms.ContextMenuStrip> è progettato per sostituire il <xref:System.Windows.Forms.ContextMenu> controllo.|  
|Comandi:|<xref:System.Windows.Forms.Button> controllo|Viene avviata, arrestata o interrompe un processo.|  
||<xref:System.Windows.Forms.LinkLabel> controllo|Visualizza il testo come collegamenti ipertestuali e attiva un evento quando l'utente seleziona il testo speciale. In genere il testo è un collegamento a un'altra finestra o un sito Web.|  
||<xref:System.Windows.Forms.NotifyIcon> controllo|Visualizza un'icona nell'area di notifica dello stato della barra delle applicazioni che rappresenta un'applicazione in esecuzione in background.|  
||<xref:System.Windows.Forms.ToolStrip> controllo|Consente di creare barre degli strumenti che può contenere un Microsoft Windows XP, Microsoft Office, Microsoft Internet Explorer o un aspetto personalizzato, con o senza i temi e con il supporto per l'overflow e il riordinamento degli elementi in fase di esecuzione. **Nota:**  Il <xref:System.Windows.Forms.ToolStrip> controllo è progettato per sostituire il <xref:System.Windows.Forms.ToolBar> controllo.|  
|Guida dell'utente|<xref:System.Windows.Forms.HelpProvider> component|Fornisce la Guida online o popup per i controlli.|  
||<xref:System.Windows.Forms.ToolTip> component|Fornisce una finestra popup che consente di visualizzare una breve descrizione dello scopo del controllo quando l'utente posiziona il puntatore del mouse sul controllo.|  
|Raggruppamento di altri controlli|<xref:System.Windows.Forms.Panel> controllo|Raggruppa un set di controlli in un frame senza etichetta, che è possibile scorrere.|  
||<xref:System.Windows.Forms.GroupBox> controllo|Raggruppa un set di controlli (ad esempio i pulsanti di opzione) su un frame non scorrevole con etichette.|  
||<xref:System.Windows.Forms.TabControl> controllo|Fornisce una pagina a schede per l'organizzazione e l'accesso in modo efficiente gli oggetti raggruppati.|  
||<xref:System.Windows.Forms.SplitContainer> controllo|Fornisce due pannelli separati da una barra mobile. **Nota:**  Il <xref:System.Windows.Forms.SplitContainer> controllo è progettato per sostituire il <xref:System.Windows.Forms.Splitter> controllo.|  
||<xref:System.Windows.Forms.TableLayoutPanel> controllo|Viene illustrato un pannello il cui contenuto è dinamicamente disposto in una griglia composta di righe e colonne.|  
||<xref:System.Windows.Forms.FlowLayoutPanel> controllo|Rappresenta un pannello che imposta il layout del contenuto orizzontalmente o verticalmente in modo dinamico.|  
|Audio|<xref:System.Media.SoundPlayer> controllo|File audio viene riprodotta in formato WAV. Suoni possono essere caricati o riprodurre in modo asincrono.|  
  
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
