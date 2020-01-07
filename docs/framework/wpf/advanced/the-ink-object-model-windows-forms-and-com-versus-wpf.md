---
title: 'Modello a oggetti Ink: confronto di Windows Form e COM con WPF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enabling ink [WPF]
- InkCanvas control [WPF]
- ink object model [WPF]
- tablet pen [WPF], events [WPF]
- ink [WPF], enabling
- events [WPF], tablet pen
ms.assetid: 577835be-b145-4226-8570-1d309e9b3901
ms.openlocfilehash: 2c0d155d320bab2f0114280e962c8f2f0b559681
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636419"
---
# <a name="the-ink-object-model-windows-forms-and-com-versus-wpf"></a>Modello a oggetti Ink: confronto di Windows Form e COM con WPF

Sono essenzialmente disponibili tre piattaforme che supportano l'input penna digitale: la piattaforma Windows Forms Tablet PC, la piattaforma COM per Tablet PC e la piattaforma Windows Presentation Foundation (WPF).  Le piattaforme Windows Forms e COM condividono un modello a oggetti simile, ma il modello a oggetti per la piattaforma WPF è sostanzialmente diverso.  In questo argomento vengono illustrate le differenze a livello generale, in modo che gli sviluppatori che hanno lavorato con un modello a oggetti possano comprendere meglio l'altro.  
  
## <a name="enabling-ink-in-an-application"></a>Abilitazione di input penna in un'applicazione  
 Tutte e tre le piattaforme inviano oggetti e controlli che consentono a un'applicazione di ricevere input da una penna del tablet.  Le piattaforme Windows Forms e COM vengono fornite con le classi [Microsoft. Ink. InkPicture](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583740(v=vs.90)), [Microsoft. Ink. InkEdit](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552265(v=vs.90)), [Microsoft. Ink. InkOverlay](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90)) e [Microsoft. Ink. InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)) .  [Microsoft. Ink. InkPicture](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583740(v=vs.90)) e [Microsoft. Ink. InkEdit](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552265(v=vs.90)) sono controlli che è possibile aggiungere a un'applicazione per raccogliere input penna.  È possibile collegare [Microsoft. Ink. InkOverlay](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90)) e [Microsoft. Ink. InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)) a una finestra esistente per abilitare l'input penna per finestre e controlli personalizzati.  
  
 La piattaforma WPF include il controllo <xref:System.Windows.Controls.InkCanvas>.  È possibile aggiungere un <xref:System.Windows.Controls.InkCanvas> all'applicazione e iniziare a raccogliere immediatamente l'input penna. Con il <xref:System.Windows.Controls.InkCanvas>, l'utente può copiare, selezionare e ridimensionare l'input penna.  È possibile aggiungere altri controlli all'<xref:System.Windows.Controls.InkCanvas>e l'utente può scrivere anche su tali controlli.  È possibile creare un controllo personalizzato abilitato per l'input penna aggiungendo un <xref:System.Windows.Controls.InkPresenter> e raccogliendo i punti dello stilo.  
  
 Nella tabella seguente sono elencate le informazioni su come abilitare l'input penna in un'applicazione:  
  
|Per effettuare questa operazione|Sulla piattaforma WPF...|Sulle piattaforme Windows Forms/COM...|  
|-----------------|--------------------------|------------------------------------------|  
|Aggiungere un controllo abilitato per l'input penna a un'applicazione|Vedere [Introduzione con input penna](getting-started-with-ink.md).|Vedere l' [esempio di modulo Claims automatico](/windows/desktop/tablet/auto-claims-form-sample)|  
|Abilitare l'input penna in un controllo personalizzato|Vedere [creazione di un controllo input penna](creating-an-ink-input-control.md).|Vedere l' [esempio di appunti input penna](/windows/desktop/tablet/ink-clipboard-sample).|  
  
## <a name="ink-data"></a>Dati Ink  
 Nelle piattaforme Windows Forms e COM [Microsoft. Ink. InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)), [Microsoft. Ink. InkOverlay](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90)), [Microsoft. Ink. InkEdit](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552265(v=vs.90))e [Microsoft. Ink. InkPicture](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583740(v=vs.90)) espongono ogni oggetto [Microsoft. Ink. Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) . L'oggetto [Microsoft. Ink. Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) contiene i dati per uno o più oggetti [Microsoft. Ink. Stroke](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552692(v=vs.90)) ed espone metodi e proprietà comuni per gestire e modificare tali tratti.  L'oggetto [Microsoft. Ink. Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) gestisce la durata dei tratti che contiene; l'oggetto [Microsoft. Ink. Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) crea ed Elimina i tratti di sua proprietà.  Ogni [Microsoft. Ink. Stroke](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552692(v=vs.90)) dispone di un identificatore univoco all'interno dell'oggetto padre [Microsoft. Ink. Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) .  
  
 Nella piattaforma WPF la classe <xref:System.Windows.Ink.Stroke?displayProperty=nameWithType> possiede e gestisce la propria durata. Un gruppo di oggetti <xref:System.Windows.Ink.Stroke> può essere raccolto insieme in una <xref:System.Windows.Ink.StrokeCollection>, che fornisce metodi per operazioni di gestione dei dati di input penna comuni, ad esempio hit testing, cancellazione, trasformazione e serializzazione dell'input penna. Un <xref:System.Windows.Ink.Stroke> può appartenere a zero, uno o più oggetti <xref:System.Windows.Ink.StrokeCollection> in qualsiasi momento.  Anziché disporre di un oggetto [Microsoft. Ink. Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) , il <xref:System.Windows.Controls.InkCanvas> e <xref:System.Windows.Controls.InkPresenter> contengono un <xref:System.Windows.Ink.StrokeCollection?displayProperty=nameWithType>.  
  
 Nella coppia di illustrazioni seguente vengono confrontati i modelli a oggetti dati dell'input penna.  Sulle piattaforme Windows Forms e COM, l'oggetto [Microsoft. Ink. Ink](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) vincola la durata degli oggetti [Microsoft. Ink. Stroke](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552692(v=vs.90)) e i pacchetti dello stilo appartengono ai singoli tratti.  Due o più tratti possono fare riferimento allo stesso oggetto [Microsoft. Ink. DrawingAttributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583636(v=vs.90)) , come illustrato nella figura seguente.  
  
 ![Diagramma del modello a oggetti Ink per WinForms&#47;com.](./media/ink-inkownsstrokes.png "Ink_InkOwnsStrokes")  
  
 Nel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], ogni <xref:System.Windows.Ink.Stroke?displayProperty=nameWithType> è un oggetto Common Language Runtime esistente a condizione che vi sia un riferimento.  Ogni <xref:System.Windows.Ink.Stroke> fa riferimento a un oggetto <xref:System.Windows.Input.StylusPointCollection> e <xref:System.Windows.Ink.DrawingAttributes?displayProperty=nameWithType>, che sono anche Common Language Runtime oggetti.  
  
 ![Diagramma del modello a oggetti Ink per WPF.](./media/ink-wpfinkobjectmodel.png "Ink_WPFInkObjectModel")  
  
 Nella tabella seguente viene illustrato come eseguire alcune attività comuni sulla piattaforma WPF e sulle piattaforme Windows Forms e COM.  
  
|Attività|Windows Presentation Foundation|Windows Forms e COM|  
|----------|-------------------------------------|---------------------------|  
|Salva input penna|<xref:System.Windows.Ink.StrokeCollection.Save%2A>|[Microsoft.Ink.Ink.Save](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms571335(v=vs.90))|  
|Carica input penna|Creare una <xref:System.Windows.Ink.StrokeCollection> con il costruttore di <xref:System.Windows.Ink.StrokeCollection.%23ctor%2A>.|[Microsoft.Ink.Ink.Load](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms569609(v=vs.90))|  
|Hit test|<xref:System.Windows.Ink.StrokeCollection.HitTest%2A>|[Microsoft.Ink.Ink.HitTest](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms571330(v=vs.90))|  
|Copia input penna|<xref:System.Windows.Controls.InkCanvas.CopySelection%2A>|[Microsoft.Ink.Ink.ClipboardCopy](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms571316(v=vs.90))|  
|Incolla input penna|<xref:System.Windows.Controls.InkCanvas.Paste%2A>|[Microsoft.Ink.Ink.ClipboardPaste](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms571318(v=vs.90))|  
|Accedere a proprietà personalizzate in una raccolta di tratti|<xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A> (le proprietà vengono archiviate internamente ed è possibile accedervi tramite <xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A>, <xref:System.Windows.Ink.StrokeCollection.RemovePropertyData%2A>e <xref:System.Windows.Ink.StrokeCollection.ContainsPropertyData%2A>)|Utilizzare [Microsoft. Ink. Ink. ExtendedProperties](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms582214(v=vs.90))|  
  
### <a name="sharing-ink-between-platforms"></a>Condivisione di input penna tra piattaforme  
 Anche se le piattaforme hanno modelli a oggetti diversi per i dati di input penna, la condivisione dei dati tra le piattaforme è molto semplice. Gli esempi seguenti salvano l'input penna da un Windows Forms Application e caricano l'input penna in un'applicazione Windows Presentation Foundation.  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#SaveWinforms](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewinforms)]
[!code-vb[WinFormWPFInk#SaveWinforms](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewinforms)]  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#LoadWPF](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwpf)]
[!code-vb[WinFormWPFInk#LoadWPF](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwpf)]  
  
 Gli esempi seguenti salvano l'input penna da un'applicazione Windows Presentation Foundation e caricano l'input penna in una Windows Forms Application.  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#SaveWPF](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewpf)]
[!code-vb[WinFormWPFInk#SaveWPF](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewpf)]  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#LoadWinforms](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwinforms)]
[!code-vb[WinFormWPFInk#LoadWinforms](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwinforms)]
## <a name="events-from-the-tablet-pen"></a>Eventi della penna del Tablet  

 [Microsoft. Ink. InkOverlay](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90)), [Microsoft. Ink. InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90))e [Microsoft. ink. INKPICTURE](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583740(v=vs.90)) sulle piattaforme Windows Forms e com ricevono eventi quando l'utente immette dati penna. [Microsoft. Ink. InkOverlay](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90)) o [Microsoft. Ink. InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)) è associato a una finestra o a un controllo e può sottoscrivere gli eventi generati dai dati di input del tablet. Il thread in cui si verificano questi eventi varia a seconda che gli eventi vengano generati con una penna, un mouse o a livello di codice. Per ulteriori informazioni sul threading in relazione a questi eventi, vedere [considerazioni generali relative al threading](/windows/desktop/tablet/general-threading-considerations) e [thread sui quali un evento può essere attivato](/windows/desktop/tablet/threads-on-which-an-event-can-fire).  
  
 Nella piattaforma Windows Presentation Foundation la classe <xref:System.Windows.UIElement> dispone di eventi per l'input penna. Ciò significa che ogni controllo espone il set completo di eventi dello stilo.  Gli eventi dello stilo hanno coppie di eventi di tunneling/bubbling e si verificano sempre nel thread dell'applicazione.  Per ulteriori informazioni, vedere [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md).  
  
 Il diagramma seguente mostra un confronto tra i modelli a oggetti per le classi che generano eventi dello stilo. Il modello a oggetti Windows Presentation Foundation Mostra solo gli eventi di bubbling, non le controparti degli eventi di tunneling.  
  
 ![Diagramma degli eventi dello stilo in WPF rispetto a WinForms.](./media/ink-stylusevents.png "Ink_StylusEvents")  
  
## <a name="pen-data"></a>Dati penna  
 Tutte e tre le piattaforme forniscono modi per intercettare e modificare i dati provenienti da una penna del tablet.  Sulle piattaforme Windows Forms e COM, questa operazione viene eseguita creando un oggetto [Microsoft. StylusInput. RealTimeStylus](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms585724(v=vs.90)), collegando una finestra o un controllo e creando una classe che implementa l'interfaccia [Microsoft. StylusInput. IStylusSyncPlugin](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms575201(v=vs.90)) o [Microsoft. StylusInput. IStylusAsyncPlugin](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms575194(v=vs.90)) . Il plug-in personalizzato viene quindi aggiunto alla raccolta plug-in di [Microsoft. StylusInput. RealTimeStylus](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms585724(v=vs.90)). Per altre informazioni su questo modello a oggetti, vedere [architettura delle API StylusInput](/windows/desktop/tablet/architecture-of-the-stylusinput-apis).  
  
 Nella piattaforma WPF la classe <xref:System.Windows.UIElement> espone una raccolta di plug-in, simile in progettazione a [Microsoft. StylusInput. RealTimeStylus](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms585724(v=vs.90)).  Per intercettare i dati di penna, creare una classe che erediti da <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> e aggiungere l'oggetto alla raccolta <xref:System.Windows.UIElement.StylusPlugIns%2A> dell'<xref:System.Windows.UIElement>. Per altre informazioni su questa interazione, vedere [intercettazione dell'input dallo stilo](intercepting-input-from-the-stylus.md).  
  
 In tutte le piattaforme, un pool di thread riceve i dati di input penna tramite gli eventi dello stilo e li invia al thread dell'applicazione.  Per altre informazioni sul threading sulle piattaforme COM e Windows, vedere [considerazioni relative al threading per le API StylusInput](/windows/desktop/tablet/threading-considerations-for-the-stylusinput-apis).  Per ulteriori informazioni sul threading sul software Windows Presentation, vedere [il modello di threading dell'input penna](the-ink-threading-model.md).  
  
 Nella figura seguente vengono confrontati i modelli a oggetti per le classi che ricevono dati penna nel pool di thread della penna.  
  
 ![Diagramma del modello StylusPlugin WPF rispetto a WinForms.](./media/ink-stylusplugins.png "Ink_StylusPlugins")
