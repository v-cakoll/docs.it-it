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
ms.openlocfilehash: c351f3d6bf6dbaf94d865fd56e140c44edc20394
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44062690"
---
# <a name="the-ink-object-model-windows-forms-and-com-versus-wpf"></a>Modello a oggetti Ink: confronto di Windows Form e COM con WPF

Esistono essenzialmente e tre le piattaforme che supportano l'input penna digitale: la piattaforma Tablet PC Windows Form, la piattaforma Tablet PC COM e la piattaforma Windows Presentation Foundation (WPF).  La condivisione di piattaforme di Windows Form e COM un modello a oggetti simili, ma l'oggetto del modello per il [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] piattaforma è sostanzialmente diversa.  In questo argomento vengono illustrate le differenze a livello generale in modo che gli sviluppatori che hanno lavorato con un modello a oggetti possono comprendere meglio l'altro.  
  
## <a name="enabling-ink-in-an-application"></a>Attivazione input penna in un'applicazione  
 Tutti e tre le piattaforme invia gli oggetti e i controlli che consentono a un'applicazione ricevere l'input da una penna del tablet PC.  I controlli Windows Form e piattaforme COM dotato [Microsoft.Ink.InkPicture](https://msdn.microsoft.com/library/aa514604.aspx), [Microsoft.Ink.InkEdit](https://msdn.microsoft.com/library/ms835842.aspx), [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx) e [ InkCollector](https://msdn.microsoft.com/library/ms836493.aspx) classi.  [Microsoft.Ink.InkPicture](https://msdn.microsoft.com/library/aa514604.aspx) e [Microsoft.Ink.InkEdit](https://msdn.microsoft.com/library/ms835842.aspx) sono controlli che è possibile aggiungere a un'applicazione per raccogliere l'input penna.  Il [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx) e [InkCollector](https://msdn.microsoft.com/library/ms836493.aspx) può essere collegato a una finestra esistente all'input penna-enable windows e i controlli personalizzati.  
  
 La piattaforma WPF include il <xref:System.Windows.Controls.InkCanvas> controllo.  È possibile aggiungere un <xref:System.Windows.Controls.InkCanvas> all'applicazione e iniziare a raccogliere subito i dati dell'input penna. Con la <xref:System.Windows.Controls.InkCanvas>, l'utente può copiare, selezionare e ridimensionare l'input penna.  È possibile aggiungere altri controlli a cui il <xref:System.Windows.Controls.InkCanvas>, l'utente può scrivere a mano su di essi troppo.  È possibile creare un controllo personalizzato compatibile aggiungendo un <xref:System.Windows.Controls.InkPresenter> al suo interno e raccogliendo i relativi punti dello stilo.  
  
 La tabella seguente elenca i riferimenti per altre informazioni sull'abilitazione dell'input penna in un'applicazione:  
  
|Per eseguire questa operazione...|Nella piattaforma WPF...|Nelle piattaforme Windows Form/COM...|  
|-----------------|--------------------------|------------------------------------------|  
|Aggiungere un controllo input penna abilitato a un'applicazione|Visualizzare [Introduzione all'input penna](../../../../docs/framework/wpf/advanced/getting-started-with-ink.md).|Vedere [automatico attestazioni formano esempio](/windows/desktop/tablet/auto-claims-form-sample)|  
|Abilitare l'input penna su un controllo personalizzato|Visualizzare [creazione di un'annotazione a penna di controllo di Input](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).|Visualizzare [dell'input penna Appunti esempio](/windows/desktop/tablet/ink-clipboard-sample).|  
  
## <a name="ink-data"></a>Dati di input penna  
 Nelle piattaforme di COM e Windows Forms [InkCollector](https://msdn.microsoft.com/library/ms836493.aspx), [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx), [Microsoft.Ink.InkEdit](https://msdn.microsoft.com/library/ms835842.aspx), e [ Microsoft.Ink.InkPicture](https://msdn.microsoft.com/library/aa514604.aspx) ogni espongono una [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx?displayProperty=nameWithType) oggetto. Il [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx) oggetto contiene i dati per uno o più [Microsoft.Ink.Stroke](https://msdn.microsoft.com/library/ms827842.aspx?displayProperty=nameWithType) oggetti ed espone metodi e proprietà per gestire e modificare questi tratti comuni.  Il [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx) oggetto gestisce la durata dei tratti contiene; il [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx) oggetto crea ed elimina i tratti di sua proprietà.  Ciascuna [Microsoft.Ink.Stroke](https://msdn.microsoft.com/library/ms827842.aspx) dispone di un identificatore univoco all'interno di relativo elemento padre [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx) oggetto.  
  
 Nella piattaforma WPF, il <xref:System.Windows.Ink.Stroke?displayProperty=nameWithType> classe possiede e gestisce la propria durata. Un gruppo di <xref:System.Windows.Ink.Stroke> oggetti possono essere raccolto in un <xref:System.Windows.Ink.StrokeCollection>, che fornisce metodi per input penna comune operazioni di gestione dati, ad esempio di hit test, la cancellazione, la trasformazione e la serializzazione dell'input penna. Oggetto <xref:System.Windows.Ink.Stroke> può appartenere a zero, uno o più <xref:System.Windows.Ink.StrokeCollection> gli oggetti di qualsiasi concedere tempo.  Invece di avere una [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx?displayProperty=nameWithType) oggetti, il <xref:System.Windows.Controls.InkCanvas> e <xref:System.Windows.Controls.InkPresenter> contengono un <xref:System.Windows.Ink.StrokeCollection?displayProperty=nameWithType>.  
  
 La seguente coppia di illustrazioni confronta i modelli a oggetti dati dell'input penna.  Nei moduli di Windows e le piattaforme di COM, il [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx?displayProperty=nameWithType) oggetto limita la durata delle [Microsoft.Ink.Stroke](https://msdn.microsoft.com/library/ms827842.aspx?displayProperty=nameWithType) oggetti e i pacchetti dello stilo appartengono a singoli tratti.  Due o più tratti possano fanno riferimento allo stesso [Microsoft.Ink.DrawingAttributes](https://msdn.microsoft.com/library/ms837931.aspx?displayProperty=nameWithType) dell'oggetto, come illustrato nella figura seguente.  
  
 ![Diagramma del modello a oggetti Ink per COM&#47;Windows Form. ](../../../../docs/framework/wpf/advanced/media/ink-inkownsstrokes.png "Ink_InkOwnsStrokes")  
  
 Nel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], ognuna <xref:System.Windows.Ink.Stroke?displayProperty=nameWithType> è un oggetto common language runtime esistente, purché si abbia un riferimento a esso.  Ciascuna <xref:System.Windows.Ink.Stroke> riferimenti a un <xref:System.Windows.Input.StylusPointCollection> e <xref:System.Windows.Ink.DrawingAttributes?displayProperty=nameWithType> oggetto, che sono anche oggetti common language runtime.  
  
 ![Diagramma del modello a oggetti Ink per WPF. ](../../../../docs/framework/wpf/advanced/media/ink-wpfinkobjectmodel.png "Ink_WPFInkObjectModel")  
  
 Nella tabella seguente viene illustrato come eseguire alcune attività comuni nel [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] piattaforma e le piattaforme Windows Form e COM.  
  
|Attività|Windows Presentation Foundation|COM e Windows Form|  
|----------|-------------------------------------|---------------------------|  
|Salvataggio dell'input penna|<xref:System.Windows.Ink.StrokeCollection.Save%2A>|[Microsoft.Ink.Ink.Save](https://technet.microsoft.com/library/security/microsoft.ink.ink.save(v=vs.90))|  
|Caricamento dell'input penna|Creare un <xref:System.Windows.Ink.StrokeCollection> con il <xref:System.Windows.Ink.StrokeCollection.%23ctor%2A> costruttore.|[Microsoft.Ink.Ink.Load](https://msdn.microsoft.com/library/microsoft.ink.ink.load(v=vs.90).aspx)|  
|Eseguire un hit test|<xref:System.Windows.Ink.StrokeCollection.HitTest%2A>|[Microsoft.Ink.Ink.HitTest](https://msdn.microsoft.com/library/aa515934.aspx)|  
|Copiare l'input penna|<xref:System.Windows.Controls.InkCanvas.CopySelection%2A>|[Microsoft.Ink.Ink.ClipboardCopy](https://msdn.microsoft.com/library/microsoft.ink.ink.clipboardcopy(v=vs.100).aspx)|  
|Incollare l'input penna|<xref:System.Windows.Controls.InkCanvas.Paste%2A>|[Microsoft.Ink.Ink.ClipboardPaste](https://msdn.microsoft.com/library/microsoft.ink.ink.clipboardpaste(v=vs.100).aspx)|  
|Accedere alle proprietà personalizzate in un insieme di tratti|<xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A> (le proprietà vengono archiviate internamente e accessibili tramite <xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A>, <xref:System.Windows.Ink.StrokeCollection.RemovePropertyData%2A>, e <xref:System.Windows.Ink.StrokeCollection.ContainsPropertyData%2A>)|Usare [Microsoft.Ink.Ink.ExtendedProperties](https://msdn.microsoft.com/library/microsoft.ink.ink.extendedproperties(v=vs.100).aspx)|  
  
### <a name="sharing-ink-between-platforms"></a>Condivisione dell'input penna tra le piattaforme  
 Sebbene le piattaforme dispongono di modelli a oggetti diversi per i dati di input penna, è molto semplice condivisione dei dati tra le piattaforme. Nell'esempio seguente Salva dell'input penna da un'applicazione Windows Forms e caricare l'input penna in un'applicazione Windows Presentation Foundation.  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#SaveWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewinforms)]
[!code-vb[WinFormWPFInk#SaveWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewinforms)]  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#LoadWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwpf)]
[!code-vb[WinFormWPFInk#LoadWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwpf)]  
  
 Negli esempi seguenti input penna salvato da un'applicazione Windows Presentation Foundation e caricare l'input penna in un'applicazione Windows Form.  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#SaveWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewpf)]
[!code-vb[WinFormWPFInk#SaveWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewpf)]  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#LoadWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwinforms)]
[!code-vb[WinFormWPFInk#LoadWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwinforms)]
## <a name="events-from-the-tablet-pen"></a>Eventi dalla penna del Tablet PC  
 Il [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx), [InkCollector](https://msdn.microsoft.com/library/ms836493.aspx), e [Microsoft.Ink.InkPicture](https://msdn.microsoft.com/library/aa514604.aspx) nei moduli di Windows e COM piattaforme ricevano eventi quando l'utente dati con la penna.  Il [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx) oppure [InkCollector](https://msdn.microsoft.com/library/ms836493.aspx) è collegato a una finestra o un controllo e può sottoscrivere gli eventi generati dai dati di input penna di tablet.  Il thread in cui questi eventi si verifica dipende dal fatto che gli eventi vengono generati con una penna, mouse, o a livello di codice.  Per altre informazioni sul threading in relazione a tali eventi, vedere [considerazioni generali Threading](/windows/desktop/tablet/general-threading-considerations) e [thread su cui può essere generato un evento](/windows/desktop/tablet/threads-on-which-an-event-can-fire).  
  
 Nella piattaforma Windows Presentation Foundation, il <xref:System.Windows.UIElement> classe dispone di eventi per l'input penna. Ciò significa che ogni controllo espone il set completo di eventi dello stilo.  Gli eventi dello stilo sono eventi di tunneling/bubbling coppie e devono essere sempre eseguiti nel thread dell'applicazione.  Per altre informazioni, vedere [Cenni preliminari sugli eventi indirizzati](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 Il diagramma seguente illustra confronta i modelli a oggetti per le classi che generano gli eventi dello stilo. Il modello a oggetti Windows Presentation Foundation Mostra solo gli eventi di bubbling, non le relative controparti evento tunneling.  
  
 ![Diagramma degli eventi Stylus in WPF e Windows Form. ](../../../../docs/framework/wpf/advanced/media/ink-stylusevents.png "Ink_StylusEvents")  
  
## <a name="pen-data"></a>Dati penna  
 Tutti e tre le piattaforme consentono di intercettare e modificare i dati provengono da una penna del tablet PC.  Nelle piattaforme di COM e Windows Form, questo risultato viene ottenuto creando una [Microsoft.StylusInput.RealTimeStylus](https://msdn.microsoft.com/library/microsoft.stylusinput.realtimestylus(v=vs.100).aspx), la connessione di una finestra o il controllo all'applicazione e la creazione di una classe che implementa il [ Microsoft.StylusInput.IStylusSyncPlugin](https://msdn.microsoft.com/library/microsoft.stylusinput.istylussyncplugin(v=vs.100).aspx) oppure [Microsoft.StylusInput.IStylusAsyncPlugin](https://msdn.microsoft.com/library/microsoft.stylusinput.istylusasyncplugin(v=vs.100).aspx) interfaccia. Il plug-in personalizzato viene quindi aggiunto alla raccolta di plug-in di [Microsoft.StylusInput.RealTimeStylus](https://msdn.microsoft.com/library/microsoft.stylusinput.realtimestylus(v=vs.100).aspx). Per altre informazioni su questo modello a oggetti, vedere [architettura di StylusInput APIs](/windows/desktop/tablet/architecture-of-the-stylusinput-apis).  
  
 Nel [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] piattaforma, il <xref:System.Windows.UIElement> classe espone una raccolta di plug-in, simile nella progettazione per il [Microsoft.StylusInput.RealTimeStylus](https://msdn.microsoft.com/library/microsoft.stylusinput.realtimestylus(v=vs.100).aspx).  Per intercettare dati penna, creare una classe che eredita da <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> e aggiungere l'oggetto per il <xref:System.Windows.UIElement.StylusPlugIns%2A> insieme del <xref:System.Windows.UIElement>. Per altre informazioni su questa interazione, vedere [intercettazione Input dello stilo](../../../../docs/framework/wpf/advanced/intercepting-input-from-the-stylus.md).  
  
 In tutte le piattaforme, un pool di thread riceva i dati di input penna tramite gli eventi dello stilo e lo invia al thread dell'applicazione.  Per altre informazioni sul threading di COM e le piattaforme Windows, vedere [considerazioni sul Threading per StylusInput APIs](/windows/desktop/tablet/threading-considerations-for-the-stylusinput-apis).  Per altre informazioni sul threading il software di presentazione di Windows, vedere [il modello di Threading dell'input penna](../../../../docs/framework/wpf/advanced/the-ink-threading-model.md).  
  
 Nella figura seguente vengono confrontati i modelli a oggetti per le classi che ricevono dati penna nel pool di thread di penna.  
  
 ![Diagramma del modello StylusPlugIn in WPF e Windows Form. ](../../../../docs/framework/wpf/advanced/media/ink-stylusplugins.png "Ink_StylusPlugins")
