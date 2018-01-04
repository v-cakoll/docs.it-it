---
title: Controlli Windows Form per funzione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], by function
- Windows Forms, controls by function
- Windows Forms controls, list of
ms.assetid: 5e65a6c3-5d6f-480d-beb8-b28f865f07e3
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a48e1e728e3ded58b0045554a81588933027074c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="windows-forms-controls-by-function"></a>Controlli Windows Form per funzione
Windows Form offre i controlli e componenti che eseguono una serie di funzioni. Nella tabella seguente sono elencati i controlli Windows Form e i componenti in base alla funzione generale. Inoltre, in cui sono presenti più controlli che svolgono la stessa funzione, il controllo consigliato viene elencato con una nota relativa al controllo sostituiva. In una tabella successiva, sono elencati i controlli sostituiti con sostitutivi consigliati.  
  
> [!NOTE]
>  Le tabelle seguenti elencano non ciascun controllo o un componente, che è possibile usare in Windows Form. per un elenco più completo, vedere [controlli da usare in Windows Form](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
  
## <a name="recommended-controls-and-components-by-function"></a>Controlli e componenti dalla funzione consigliati  
  
|Funzione|Control|Descrizione|  
|--------------|-------------|-----------------|  
|Visualizzazione dei dati|Controllo <xref:System.Windows.Forms.DataGridView>|Il <xref:System.Windows.Forms.DataGridView> controllo fornisce una tabella personalizzabile per la visualizzazione dei dati. La <xref:System.Windows.Forms.DataGridView> classe consente la personalizzazione di celle, righe, colonne e i bordi. **Nota:** il <xref:System.Windows.Forms.DataGridView> controllo fornisce diverse funzionalità di base e avanzate che non sono presenti nel <xref:System.Windows.Forms.DataGrid> controllo. Per ulteriori informazioni, vedere [differenze tra il Windows Form controlli DataGridView e DataGrid](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)|  
|Spostamento e l'associazione dati|<xref:System.Windows.Forms.BindingSource>componente|Semplifica l'associazione dei controlli in un form ai dati, fornendo la gestione delle valute, la notifica delle modifiche e altri servizi.|  
||Controllo <xref:System.Windows.Forms.BindingNavigator>|Fornisce un'interfaccia di tipo barra degli strumenti per esplorare e modificare i dati in un form.|  
|Modifica del testo|Controllo <xref:System.Windows.Forms.TextBox>|Visualizza il testo immesso in fase di progettazione che può essere modificato dagli utenti in fase di esecuzione, o modificata a livello di codice.|  
||Controllo <xref:System.Windows.Forms.RichTextBox>|Consente il testo da visualizzare con formattazione in formato testo normale o RTF (RICH).|  
||Controllo <xref:System.Windows.Forms.MaskedTextBox>|Vincola il formato dell'input utente|  
|Visualizzazione di informazioni (in sola lettura)|Controllo <xref:System.Windows.Forms.Label>|Viene visualizzato del testo che gli utenti non possono modificare direttamente.|  
||Controllo <xref:System.Windows.Forms.LinkLabel>|Visualizza il testo come un collegamento ipertestuale e genera un evento quando l'utente fa clic sul testo speciale. In genere il testo è un collegamento a un'altra finestra o un sito Web.|  
||Controllo <xref:System.Windows.Forms.StatusStrip>|Visualizza le informazioni di stato corrente dell'applicazione utilizzando un'area del frame, in genere nella parte inferiore di un form padre.|  
||Controllo <xref:System.Windows.Forms.ProgressBar>|Visualizza lo stato corrente di un'operazione per l'utente.|  
|Visualizzazione delle pagine Web|Controllo <xref:System.Windows.Forms.WebBrowser>|Consente all'utente di spostarsi tra le pagine Web all'interno del form.|  
|Selezione da un elenco|Controllo <xref:System.Windows.Forms.CheckedListBox>|Visualizza un elenco di elementi, ognuno accompagnati da una casella di controllo di scorrimento.|  
||Controllo <xref:System.Windows.Forms.ComboBox>|Visualizza un elenco a discesa di elementi.|  
||Controllo <xref:System.Windows.Forms.DomainUpDown>|Visualizza un elenco di elementi di testo che gli utenti possono scorrere mediante i pulsanti su e giù.|  
||Controllo <xref:System.Windows.Forms.ListBox>|Visualizza un elenco di elementi grafici (icone) e di testo.|  
||Controllo <xref:System.Windows.Forms.ListView>|Visualizza gli elementi in una delle quattro diverse visualizzazioni. Le visualizzazioni includono solo testo, testo con icone piccole, il testo con icone grandi e una visualizzazione dettagli.|  
||Controllo <xref:System.Windows.Forms.NumericUpDown>|Visualizza un elenco di numeri che agli utenti di scorrere con pulsanti su e giù.|  
||Controllo <xref:System.Windows.Forms.TreeView>|Visualizza una raccolta gerarchica di oggetti del nodo che può essere costituita da testo con icone o caselle di controllo facoltative.|  
|Visualizzazione grafica|Controllo <xref:System.Windows.Forms.PictureBox>|File di grafica consente di visualizzare, ad esempio le bitmap e icone, in un frame.|  
|Archiviazione di grafica|Controllo <xref:System.Windows.Forms.ImageList>|Funge da repository per le immagini. <xref:System.Windows.Forms.ImageList>controlli e le immagini che contengono possono essere riutilizzate da un'applicazione al successivo.|  
|Impostazione del valore|Controllo <xref:System.Windows.Forms.CheckBox>|Visualizza una casella di controllo e l'etichetta di testo. In genere utilizzato per impostare le opzioni.|  
||Controllo <xref:System.Windows.Forms.CheckedListBox>|Visualizza un elenco di elementi, ognuno accompagnati da una casella di controllo di scorrimento.|  
||Controllo <xref:System.Windows.Forms.RadioButton>|Visualizza un pulsante che può essere attivato o disattivata.|  
||Controllo <xref:System.Windows.Forms.TrackBar>|Consente agli utenti di impostare i valori su una scala spostando "thumb" lungo la scala.|  
|Impostazione della data|Controllo <xref:System.Windows.Forms.DateTimePicker>|Visualizza un calendario con interfaccia grafico per consentire agli utenti di selezionare una data o ora.|  
||Controllo <xref:System.Windows.Forms.MonthCalendar>|Visualizza un calendario con interfaccia grafico per consentire agli utenti di selezionare un intervallo di date.|  
|Finestre di dialogo|Controllo <xref:System.Windows.Forms.ColorDialog>|Consente di visualizzare la finestra di dialogo per la selezione colori che consente agli utenti di impostare il colore di un elemento di interfaccia.|  
||Controllo <xref:System.Windows.Forms.FontDialog>|Visualizza una finestra di dialogo che consente agli utenti di impostare un tipo di carattere e i relativi attributi.|  
||Controllo <xref:System.Windows.Forms.OpenFileDialog>|Visualizza una finestra di dialogo che consente agli utenti di individuare e selezionare un file.|  
||Controllo <xref:System.Windows.Forms.PrintDialog>|Visualizza una finestra di dialogo che consente agli utenti di selezionare una stampante e impostare i relativi attributi.|  
||Controllo <xref:System.Windows.Forms.PrintPreviewDialog>|Visualizza una finestra di dialogo che consente di visualizzare modalità un controllo <xref:System.Drawing.Printing.PrintDocument> componente apparirà in stampa.|  
||Controllo <xref:System.Windows.Forms.FolderBrowserDialog>|Visualizza una finestra di dialogo che consente agli utenti di esplorare, creare e infine selezionare una cartella|  
||Controllo <xref:System.Windows.Forms.SaveFileDialog>|Visualizza una finestra di dialogo che consente agli utenti di salvare un file.|  
|Controlli menu|Controllo <xref:System.Windows.Forms.MenuStrip>|Consente di creare menu personalizzati. **Nota:** il <xref:System.Windows.Forms.MenuStrip> è progettato per sostituire il <xref:System.Windows.Forms.MainMenu> controllo.|  
||Controllo <xref:System.Windows.Forms.ContextMenuStrip>|Crea i menu di scelta rapida personalizzato. **Nota:** il <xref:System.Windows.Forms.ContextMenuStrip> è progettato per sostituire il <xref:System.Windows.Forms.ContextMenu> controllo.|  
|Comandi:|Controllo <xref:System.Windows.Forms.Button>|Avvia, arresta o interrompe un processo.|  
||Controllo <xref:System.Windows.Forms.LinkLabel>|Visualizza il testo come un collegamento ipertestuale e genera un evento quando l'utente fa clic sul testo speciale. In genere il testo è un collegamento a un'altra finestra o un sito Web.|  
||Controllo <xref:System.Windows.Forms.NotifyIcon>|Visualizza un'icona nell'area di notifica dello stato della barra delle applicazioni che rappresenta un'applicazione in esecuzione in background.|  
||Controllo <xref:System.Windows.Forms.ToolStrip>|Consente di creare barre degli strumenti che può contenere un Microsoft Windows XP, Microsoft Office, Microsoft Internet Explorer o un aspetto personalizzato, con o senza temi e con supporto per l'overflow e il riordino degli elementi in fase di esecuzione. **Nota:** il <xref:System.Windows.Forms.ToolStrip> controllo è progettato per sostituire il <xref:System.Windows.Forms.ToolBar> controllo.|  
|Guida dell'utente|<xref:System.Windows.Forms.HelpProvider>componente|Fornisce la Guida in linea o popup per i controlli.|  
||<xref:System.Windows.Forms.ToolTip>componente|Fornisce una finestra popup che consente di visualizzare una breve descrizione dello scopo del controllo quando l'utente posiziona il puntatore del mouse sul controllo.|  
|Raggruppamento di altri controlli.|Controllo <xref:System.Windows.Forms.Panel>|Consente di raggruppare un set di controlli in un frame senza etichetta, che è possibile scorrere.|  
||Controllo <xref:System.Windows.Forms.GroupBox>|Su un frame non scorrevole con etichette, di raggruppare un set di controlli (ad esempio i pulsanti di opzione).|  
||Controllo <xref:System.Windows.Forms.TabControl>|Fornisce una pagina a schede per l'organizzazione e l'accesso in modo efficiente gli oggetti raggruppati.|  
||Controllo <xref:System.Windows.Forms.SplitContainer>|Fornisce due pannelli separati da una barra mobile. **Nota:** il <xref:System.Windows.Forms.SplitContainer> controllo è progettato per sostituire il <xref:System.Windows.Forms.Splitter> controllo.|  
||Controllo <xref:System.Windows.Forms.TableLayoutPanel>|Viene illustrato un pannello il cui contenuto è dinamicamente disposto in una griglia composta di righe e colonne.|  
||Controllo <xref:System.Windows.Forms.FlowLayoutPanel>|Rappresenta un pannello che imposta il layout del contenuto orizzontalmente o verticalmente in modo dinamico.|  
|Audio|Controllo <xref:System.Media.SoundPlayer>|Riproduce file audio in formato WAV. Suoni possono essere caricati o riprodotto in modo asincrono.|  
  
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
 [Controlli da usare in Windows Form](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Sviluppo di controlli Windows Form personalizzati con .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)
