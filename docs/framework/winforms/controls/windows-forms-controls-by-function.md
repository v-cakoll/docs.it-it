---
title: Controlli per funzione
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], by function
- Windows Forms, controls by function
- Windows Forms controls, list of
ms.assetid: 5e65a6c3-5d6f-480d-beb8-b28f865f07e3
ms.openlocfilehash: f2341d49513b418c244ee7ab93c0858899502487
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741586"
---
# <a name="windows-forms-controls-by-function"></a>Controlli Windows Form per funzione
Windows Forms offre controlli e componenti che eseguono una serie di funzioni. Nella tabella seguente sono elencati i componenti e i controlli Windows Forms in base alla funzione generale. Inoltre, quando esistono più controlli che svolgono la stessa funzione, il controllo consigliato viene elencato con una nota relativa al controllo sostituito. In una tabella successiva separata, i controlli sostituiti vengono elencati con le sostituzioni consigliate.  
  
> [!NOTE]
> Nelle tabelle seguenti non sono elencati tutti i controlli o i componenti che è possibile utilizzare in Windows Forms; per un elenco più completo, vedere [controlli da usare in Windows Forms](controls-to-use-on-windows-forms.md)  
  
## <a name="recommended-controls-and-components-by-function"></a>Controlli e componenti consigliati per funzione  
  
|Funzione|Control|Descrizione|  
|--------------|-------------|-----------------|  
|Visualizzazione dati|Controllo <xref:System.Windows.Forms.DataGridView>|Il controllo <xref:System.Windows.Forms.DataGridView> fornisce una tabella personalizzabile per la visualizzazione dei dati. La classe <xref:System.Windows.Forms.DataGridView> consente la personalizzazione di celle, righe, colonne e bordi. **Nota:**  Il controllo <xref:System.Windows.Forms.DataGridView> offre numerose funzionalità di base e avanzate mancanti nel controllo <xref:System.Windows.Forms.DataGrid>. Per altre informazioni, vedere [differenze tra i controlli DataGridView e DataGrid di Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)|  
|Data Binding e navigazione|<xref:System.Windows.Forms.BindingSource>|Semplifica l'associazione dei controlli di un modulo ai dati fornendo la gestione della valuta, la notifica delle modifiche e altri servizi.|  
||Controllo <xref:System.Windows.Forms.BindingNavigator>|Fornisce un'interfaccia di tipo barra degli strumenti per esplorare e modificare i dati in un form.|  
|Modifica del testo|Controllo <xref:System.Windows.Forms.TextBox>|Visualizza il testo immesso in fase di progettazione che può essere modificato dagli utenti in fase di esecuzione o modificati a livello di codice.|  
||Controllo <xref:System.Windows.Forms.RichTextBox>|Consente la visualizzazione del testo con formattazione in testo normale o RTF (Rich-Text Format).|  
||Controllo <xref:System.Windows.Forms.MaskedTextBox>|Vincola il formato dell'input utente|  
|Visualizzazione delle informazioni (sola lettura)|Controllo <xref:System.Windows.Forms.Label>|Viene visualizzato del testo che gli utenti non possono modificare direttamente.|  
||Controllo <xref:System.Windows.Forms.LinkLabel>|Visualizza il testo come collegamento di tipo Web e attiva un evento quando l'utente fa clic sul testo speciale. In genere il testo è un collegamento a un'altra finestra o a un sito Web.|  
||Controllo <xref:System.Windows.Forms.StatusStrip>|Visualizza informazioni sullo stato corrente dell'applicazione usando un'area incorniciata, in genere nella parte inferiore di un form padre.|  
||Controllo <xref:System.Windows.Forms.ProgressBar>|Visualizza lo stato di avanzamento corrente di un'operazione all'utente.|  
|Visualizzazione della pagina Web|Controllo <xref:System.Windows.Forms.WebBrowser>|Consente all'utente di spostarsi tra le pagine Web all'interno del form.|  
|Selezione da un elenco|Controllo <xref:System.Windows.Forms.CheckedListBox>|Consente di visualizzare un elenco scorrevole di elementi, ognuno dei quali è accompagnato da una casella di controllo.|  
||Controllo <xref:System.Windows.Forms.ComboBox>|Visualizza un elenco a discesa di elementi.|  
||Controllo <xref:System.Windows.Forms.DomainUpDown>|Visualizza un elenco di elementi di testo che gli utenti possono scorrere con i pulsanti su e giù.|  
||Controllo <xref:System.Windows.Forms.ListBox>|Visualizza un elenco di elementi di testo e grafici (icone).|  
||Controllo <xref:System.Windows.Forms.ListView>|Visualizza gli elementi in una delle quattro visualizzazioni diverse. Le visualizzazioni includono solo testo, testo con icone piccole, testo con icone grandi e una visualizzazione dettagli.|  
||Controllo <xref:System.Windows.Forms.NumericUpDown>|Visualizza un elenco di numeri che gli utenti possono scorrere con i pulsanti su e giù.|  
||Controllo <xref:System.Windows.Forms.TreeView>|Visualizza una raccolta gerarchica di oggetti Node che possono essere costituiti da testo con caselle di controllo o icone facoltative.|  
|Visualizzazione grafica|Controllo <xref:System.Windows.Forms.PictureBox>|Visualizza i file grafici, ad esempio bitmap e icone, in un frame.|  
|Archiviazione grafica|Controllo <xref:System.Windows.Forms.ImageList>|Funge da repository per le immagini. i controlli <xref:System.Windows.Forms.ImageList> e le immagini che contengono possono essere riutilizzati da un'applicazione a quella successiva.|  
|Impostazione valore|Controllo <xref:System.Windows.Forms.CheckBox>|Visualizza una casella di controllo e un'etichetta per il testo. Usato in genere per impostare le opzioni.|  
||Controllo <xref:System.Windows.Forms.CheckedListBox>|Consente di visualizzare un elenco scorrevole di elementi, ognuno dei quali è accompagnato da una casella di controllo.|  
||Controllo <xref:System.Windows.Forms.RadioButton>|Visualizza un pulsante che può essere attivato o disattivato.|  
||Controllo <xref:System.Windows.Forms.TrackBar>|Consente agli utenti di impostare i valori su una scala spostando un "pollice" lungo una scala.|  
|Impostazione data|Controllo <xref:System.Windows.Forms.DateTimePicker>|Visualizza un calendario grafico per consentire agli utenti di selezionare una data o un'ora.|  
||Controllo <xref:System.Windows.Forms.MonthCalendar>|Visualizza un calendario grafico per consentire agli utenti di selezionare un intervallo di date.|  
|Finestre di dialogo|Controllo <xref:System.Windows.Forms.ColorDialog>|Consente di visualizzare la finestra di dialogo Selezione colori che consente agli utenti di impostare il colore di un elemento di interfaccia.|  
||Controllo <xref:System.Windows.Forms.FontDialog>|Visualizza una finestra di dialogo che consente agli utenti di impostare un tipo di carattere e i relativi attributi.|  
||Controllo <xref:System.Windows.Forms.OpenFileDialog>|Visualizza una finestra di dialogo che consente agli utenti di passare a un file e selezionarlo.|  
||Controllo <xref:System.Windows.Forms.PrintDialog>|Visualizza una finestra di dialogo che consente agli utenti di selezionare una stampante e di impostarne gli attributi.|  
||Controllo <xref:System.Windows.Forms.PrintPreviewDialog>|Visualizza una finestra di dialogo in cui viene visualizzato il modo in cui un controllo <xref:System.Drawing.Printing.PrintDocument> componente verrà visualizzato quando viene stampato.|  
||Controllo <xref:System.Windows.Forms.FolderBrowserDialog>|Visualizza una finestra di dialogo che consente agli utenti di esplorare, creare e infine selezionare una cartella|  
||Controllo <xref:System.Windows.Forms.SaveFileDialog>|Visualizza una finestra di dialogo che consente agli utenti di salvare un file.|  
|Controlli menu|Controllo <xref:System.Windows.Forms.MenuStrip>|Crea menu personalizzati. **Nota:**  Il <xref:System.Windows.Forms.MenuStrip> è progettato per sostituire il controllo <xref:System.Windows.Forms.MainMenu>.|  
||Controllo <xref:System.Windows.Forms.ContextMenuStrip>|Crea menu di scelta rapida personalizzati. **Nota:**  Il <xref:System.Windows.Forms.ContextMenuStrip> è progettato per sostituire il controllo <xref:System.Windows.Forms.ContextMenu>.|  
|Commands|Controllo <xref:System.Windows.Forms.Button>|Avvia, arresta o interrompe un processo.|  
||Controllo <xref:System.Windows.Forms.LinkLabel>|Visualizza il testo come collegamento di tipo Web e attiva un evento quando l'utente fa clic sul testo speciale. In genere il testo è un collegamento a un'altra finestra o a un sito Web.|  
||Controllo <xref:System.Windows.Forms.NotifyIcon>|Visualizza un'icona nell'area di notifica dello stato della barra delle applicazioni che rappresenta un'applicazione in esecuzione in background.|  
||Controllo <xref:System.Windows.Forms.ToolStrip>|Consente di creare barre degli strumenti che possono avere un Microsoft Windows XP, Microsoft Office, Microsoft Internet Explorer o un aspetto personalizzato, con o senza temi e con supporto per il riordinamento degli elementi in fase di overflow e di Runtime. **Nota:**  Il controllo <xref:System.Windows.Forms.ToolStrip> è progettato per sostituire il controllo <xref:System.Windows.Forms.ToolBar>.|  
|Guida dell'utente|<xref:System.Windows.Forms.HelpProvider>|Fornisce una Guida online o una Guida popup per i controlli.|  
||<xref:System.Windows.Forms.ToolTip>|Fornisce una finestra popup che visualizza una breve descrizione dello scopo di un controllo quando l'utente posiziona il puntatore del mouse sul controllo.|  
|Raggruppamento di altri controlli|Controllo <xref:System.Windows.Forms.Panel>|Raggruppa un set di controlli su un frame scorrevole senza etichetta.|  
||Controllo <xref:System.Windows.Forms.GroupBox>|Raggruppa un set di controlli (ad esempio pulsanti di opzione) su un frame con etichetta e non scorrevole.|  
||Controllo <xref:System.Windows.Forms.TabControl>|Fornisce una pagina a schede per organizzare e accedere in modo efficiente agli oggetti raggruppati.|  
||Controllo <xref:System.Windows.Forms.SplitContainer>|Fornisce due pannelli separati da una barra mobile. **Nota:**  Il controllo <xref:System.Windows.Forms.SplitContainer> è progettato per sostituire il controllo <xref:System.Windows.Forms.Splitter>.|  
||Controllo <xref:System.Windows.Forms.TableLayoutPanel>|Viene illustrato un pannello il cui contenuto è dinamicamente disposto in una griglia composta di righe e colonne.|  
||Controllo <xref:System.Windows.Forms.FlowLayoutPanel>|Rappresenta un pannello che imposta il layout del contenuto orizzontalmente o verticalmente in modo dinamico.|  
|Audio|Controllo <xref:System.Media.SoundPlayer>|Riproduce i file audio nel formato WAV. I suoni possono essere caricati o riprodotti in modo asincrono.|  
  
## <a name="superseded-controls-and-components-by-function"></a>Controlli e componenti sostituiti per funzione  
  
|Funzione|Controllo sostituito|Sostituzione consigliata|  
|--------------|------------------------|-----------------------------|  
|Visualizzazione dati|<xref:System.Windows.Forms.DataGrid>|<xref:System.Windows.Forms.DataGridView>|  
|Visualizzazione delle informazioni (controlli di sola lettura)|<xref:System.Windows.Forms.StatusBar>|<xref:System.Windows.Forms.StatusStrip>|  
|Controlli menu|<xref:System.Windows.Forms.ContextMenu>|<xref:System.Windows.Forms.ContextMenuStrip>|  
||<xref:System.Windows.Forms.MainMenu>|<xref:System.Windows.Forms.MenuStrip>|  
|Commands|<xref:System.Windows.Forms.ToolBar>|<xref:System.Windows.Forms.ToolStrip>|  
||<xref:System.Windows.Forms.StatusBar>|<xref:System.Windows.Forms.StatusStrip>|  
|Layout del form|<xref:System.Windows.Forms.Splitter>|<xref:System.Windows.Forms.SplitContainer>|  
  
## <a name="see-also"></a>Vedere anche

- [Controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)
- [Sviluppo di controlli Windows Form personalizzati con .NET Framework](developing-custom-windows-forms-controls.md)
