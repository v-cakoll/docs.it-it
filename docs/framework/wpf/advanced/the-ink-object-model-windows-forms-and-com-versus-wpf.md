---
title: 'Modello a oggetti Ink: confronto di Windows Form e COM con WPF'
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology:
- dotnet-wpf
ms.topic: article
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
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 06a2c2049ec7fe7046bd6dae2711fe8e46592fcf
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="the-ink-object-model-windows-forms-and-com-versus-wpf"></a>Modello a oggetti Ink: confronto di Windows Form e COM con WPF

Sono disponibili essenzialmente e tre le piattaforme che supportano la penna: la piattaforma di Windows Form di Tablet PC, la piattaforma COM di Tablet PC e la piattaforma Windows Presentation Foundation (WPF).  La condivisione di piattaforme Windows Form e COM un modello a oggetti simili, ma l'oggetto del modello per il [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] piattaforma è sostanzialmente diversa.  In questo argomento vengono illustrate le differenze ad alto livello in modo che gli sviluppatori che hanno lavorato con un modello a oggetti comprendere meglio l'altro.  
  
## <a name="enabling-ink-in-an-application"></a>Abilitazione dell'input penna in un'applicazione  
 Tutti e tre le piattaforme sono inclusi gli oggetti e i controlli che consentono a un'applicazione ricevere l'input penna.  Le piattaforme Windows Form e COM forniti con [Microsoft.Ink.InkPicture](https://msdn.microsoft.com/library/aa514604.aspx), [Microsoft.Ink.InkEdit](https://msdn.microsoft.com/library/ms835842.aspx), [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx) e [ Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/ms836493.aspx) classi.  [Microsoft.Ink.InkPicture](https://msdn.microsoft.com/library/aa514604.aspx) e [Microsoft.Ink.InkEdit](https://msdn.microsoft.com/library/ms835842.aspx) sono controlli che è possibile aggiungere a un'applicazione per raccogliere l'input penna.  Il [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx) e [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/ms836493.aspx) può essere collegato a una finestra esistente a windows di abilitare input penna e controlli personalizzati.  
  
 La piattaforma WPF include il <xref:System.Windows.Controls.InkCanvas> controllo.  È possibile aggiungere un <xref:System.Windows.Controls.InkCanvas> all'applicazione e iniziare immediatamente la raccolta di input penna. Con il <xref:System.Windows.Controls.InkCanvas>, l'utente può copiare, selezionare e ridimensionare l'input penna.  È possibile aggiungere altri controlli per il <xref:System.Windows.Controls.InkCanvas>, e l'utente può scrivere troppo su di essi.  È possibile creare un controllo personalizzato abilitato input penna aggiungendo un <xref:System.Windows.Controls.InkPresenter> e raccogliendo i relativi punti dello stilo.  
  
 Nella tabella seguente sono elencate altre informazioni sull'abilitazione di input penna in un'applicazione in cui:  
  
|Per eseguire questa operazione...|Nella piattaforma WPF...|Nelle piattaforme Windows Form/COM...|  
|-----------------|--------------------------|------------------------------------------|  
|Aggiungere un controllo input penna abilitato a un'applicazione|Vedere [Getting Started with Ink](../../../../docs/framework/wpf/advanced/getting-started-with-ink.md).|Vedere [Auto attestazioni formano esempio](http://msdn.microsoft.com/bec4333a-62ca-4254-a39b-04bc2c556992)|  
|Abilitare l'input penna su un controllo personalizzato|Vedere [la creazione di un input penna di controllo di Input](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).|Vedere [input penna di esempio Appunti](http://msdn.microsoft.com/a0c42f1c-543d-44f8-83d9-fe810de410ff).|  
  
## <a name="ink-data"></a>Dati di input penna  
 Nelle piattaforme COM e Windows Form [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/ms836493.aspx), [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx), [Microsoft.Ink.InkEdit](https://msdn.microsoft.com/library/ms835842.aspx), e [ Microsoft.Ink.InkPicture](https://msdn.microsoft.com/library/aa514604.aspx) espongono ognuno un [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx?displayProperty=nameWithType) oggetto. Il [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx) oggetto contiene i dati per uno o più [Microsoft.Ink.Stroke](https://msdn.microsoft.com/library/ms827842.aspx?displayProperty=nameWithType) oggetti ed espone metodi e proprietà per gestire e modificare questi tratti comuni.  Il [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx) oggetto gestisce la durata dei tratti contiene; il [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx) oggetto crea ed elimina i tratti di sua proprietà.  Ogni [Microsoft.Ink.Stroke](https://msdn.microsoft.com/library/ms827842.aspx) dispone di un identificatore univoco all'interno del relativo padre [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx) oggetto.  
  
 Nella piattaforma WPF la <xref:System.Windows.Ink.Stroke?displayProperty=nameWithType> classe possiede e gestisce il proprio ciclo di vita. Un gruppo di <xref:System.Windows.Ink.Stroke> oggetti possono essere raccolto un <xref:System.Windows.Ink.StrokeCollection>, che fornisce metodi per input penna di comune operazioni di gestione dati, ad esempio hit test, la cancellazione, trasformazione e serializzazione dell'input penna. Oggetto <xref:System.Windows.Ink.Stroke> può appartenere a zero, uno o più <xref:System.Windows.Ink.StrokeCollection> gli oggetti di qualsiasi concedere tempo.  Anziché un [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx?displayProperty=nameWithType) oggetto, il <xref:System.Windows.Controls.InkCanvas> e <xref:System.Windows.Controls.InkPresenter> contengono un <xref:System.Windows.Ink.StrokeCollection?displayProperty=nameWithType>.  
  
 La seguente coppia di illustrazioni confronta i modelli di oggetto dati di input penna.  Nelle piattaforme COM e Windows Form di [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx?displayProperty=nameWithType) oggetto limita la durata del [Microsoft.Ink.Stroke](https://msdn.microsoft.com/library/ms827842.aspx?displayProperty=nameWithType) oggetti e i pacchetti di stilo appartengono ai singoli tratti.  Due o più tracce possono fanno riferimento allo stesso [Microsoft.Ink.DrawingAttributes](https://msdn.microsoft.com/library/ms837931.aspx?displayProperty=nameWithType) dell'oggetto, come illustrato nella figura seguente.  
  
 ![Diagramma del modello a oggetti Ink per COM&#47;Windows Form. ] (../../../../docs/framework/wpf/advanced/media/ink-inkownsstrokes.png "Ink_InkOwnsStrokes")  
  
 Nel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], ogni <xref:System.Windows.Ink.Stroke?displayProperty=nameWithType> è un oggetto di common language runtime che esiste fino a quando un elemento è un riferimento a esso.  Ogni <xref:System.Windows.Ink.Stroke> riferimenti un <xref:System.Windows.Input.StylusPointCollection> e <xref:System.Windows.Ink.DrawingAttributes?displayProperty=nameWithType> oggetto, che sono anche oggetti common language runtime.  
  
 ![Diagramma del modello a oggetti Ink per WPF. ] (../../../../docs/framework/wpf/advanced/media/ink-wpfinkobjectmodel.png "Ink_WPFInkObjectModel")  
  
 Nella tabella seguente viene illustrato come eseguire alcune attività comuni nel [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] piattaforma e le piattaforme Windows Form e COM.  
  
|Attività|Windows Presentation Foundation|COM e Windows Form|  
|----------|-------------------------------------|---------------------------|  
|Salvare l'input penna|<xref:System.Windows.Ink.StrokeCollection.Save%2A>|[Microsoft.Ink.Ink.Save](https://technet.microsoft.com/library/security/microsoft.ink.ink.save(v=vs.90))|  
|Input penna di carico|Creare un <xref:System.Windows.Ink.StrokeCollection> con il <xref:System.Windows.Ink.StrokeCollection.%23ctor%2A> costruttore.|[Microsoft.Ink.Ink.Load](https://msdn.microsoft.com/library/microsoft.ink.ink.load(v=vs.90).aspx)|  
|Eseguire l'hit test|<xref:System.Windows.Ink.StrokeCollection.HitTest%2A>|[Microsoft.Ink.Ink.HitTest](https://msdn.microsoft.com/library/aa515934.aspx)|  
|Copiare l'input penna|<xref:System.Windows.Controls.InkCanvas.CopySelection%2A>|[Microsoft.Ink.Ink.ClipboardCopy](https://msdn.microsoft.com/library/microsoft.ink.ink.clipboardcopy(v=vs.100).aspx)|  
|Incolla input penna|<xref:System.Windows.Controls.InkCanvas.Paste%2A>|[Microsoft.Ink.Ink.ClipboardPaste](https://msdn.microsoft.com/library/microsoft.ink.ink.clipboardpaste(v=vs.100).aspx)|  
|Proprietà personalizzate di accesso su una raccolta di tracce|<xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A> (le proprietà sono archiviate internamente e accessibili tramite <xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A>, <xref:System.Windows.Ink.StrokeCollection.RemovePropertyData%2A>, e <xref:System.Windows.Ink.StrokeCollection.ContainsPropertyData%2A>)|Utilizzare [Microsoft.Ink.Ink.ExtendedProperties](https://msdn.microsoft.com/library/microsoft.ink.ink.extendedproperties(v=vs.100).aspx)|  
  
### <a name="sharing-ink-between-platforms"></a>Condivisione di input penna tra piattaforme  
 Sebbene le piattaforme dispongono di modelli a oggetti diversi per i dati di input penna, la condivisione dei dati tra le piattaforme è molto semplice. Negli esempi seguenti viene salvato input penna in un'applicazione Windows Form e caricano l'input penna in un'applicazione Windows Presentation Foundation.  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#SaveWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewinforms)]
[!code-vb[WinFormWPFInk#SaveWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewinforms)]  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#LoadWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwpf)]
[!code-vb[WinFormWPFInk#LoadWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwpf)]  
  
 Negli esempi seguenti viene salvato input penna in un'applicazione Windows Presentation Foundation e caricano l'input penna in un'applicazione Windows Form.  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#SaveWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewpf)]
[!code-vb[WinFormWPFInk#SaveWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewpf)]  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#LoadWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwinforms)]
[!code-vb[WinFormWPFInk#LoadWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwinforms)]
## <a name="events-from-the-tablet-pen"></a>Eventi del Tablet PC  
 Il [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx), [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/ms836493.aspx), e [Microsoft.Ink.InkPicture](https://msdn.microsoft.com/library/aa514604.aspx) nei moduli di Windows e COM piattaforme riceveranno eventi quando l'utente input pennino di dati.  Il [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx) o [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/ms836493.aspx) è collegato a una finestra o un controllo e può sottoscrivere gli eventi generati dai dati di input penna di tablet.  Il thread in cui questi eventi si verifica dipende se gli eventi vengono generati con una penna, mouse, o a livello di codice.  Per ulteriori informazioni sul threading in relazione a questi eventi, vedere [considerazioni generali Threading](http://msdn.microsoft.com/cf35724f-5f80-4b3e-992a-a9d5ea99aae9) e [thread su cui può essere generato un evento](http://msdn.microsoft.com/d1a5ab9b-d474-4ed7-9aa8-b5bdb771934f).  
  
 Nella piattaforma Windows Presentation Foundation, il <xref:System.Windows.UIElement> classe dispone di eventi per l'input penna. Ciò significa che ogni controllo espone il set completo di eventi dello stilo.  Gli eventi dello stilo hanno tunneling bubbling evento coppie e si verificano sempre il thread dell'applicazione.  Per ulteriori informazioni, vedere [indirizzato Cenni preliminari sugli eventi](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 Il diagramma seguente illustra confronta i modelli a oggetti per le classi che generano gli eventi dello stilo. Il modello a oggetti Windows Presentation Foundation Mostra solo gli eventi di bubbling, non le relative controparti evento tunneling.  
  
 ![Diagramma degli eventi Stylus in WPF e in Windows Form. ] (../../../../docs/framework/wpf/advanced/media/ink-stylusevents.png "Ink_StylusEvents")  
  
## <a name="pen-data"></a>Dati della penna  
 Tutti e tre le piattaforme consentono di intercettare e modificare i dati da cui deriva una penna di Tablet PC.  Nelle piattaforme COM e Windows Form, questo risultato viene ottenuto creando un [Microsoft.StylusInput.RealTimeStylus](https://msdn.microsoft.com/library/microsoft.stylusinput.realtimestylus(v=vs.100).aspx), la connessione di una finestra o un controllo all'applicazione e la creazione di una classe che implementa il [ Microsoft.StylusInput.IStylusSyncPlugin](https://msdn.microsoft.com/library/microsoft.stylusinput.istylussyncplugin(v=vs.100).aspx) o [Microsoft.StylusInput.IStylusAsyncPlugin](https://msdn.microsoft.com/library/microsoft.stylusinput.istylusasyncplugin(v=vs.100).aspx) interfaccia. Il plug-in personalizzato viene quindi aggiunto alla raccolta di plug-in di [Microsoft.StylusInput.RealTimeStylus](https://msdn.microsoft.com/library/microsoft.stylusinput.realtimestylus(v=vs.100).aspx). Per ulteriori informazioni su questo modello a oggetti, vedere [architettura di StylusInput APIs](http://msdn.microsoft.com/88bab0ab-df9f-4813-9a9f-9a137813f0b4).  
  
 Nel [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] piattaforma, il <xref:System.Windows.UIElement> classe espone una raccolta di plug-in con progettazione simile al [Microsoft.StylusInput.RealTimeStylus](https://msdn.microsoft.com/library/microsoft.stylusinput.realtimestylus(v=vs.100).aspx).  Per intercettare i dati della penna, creare una classe che eredita da <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> e aggiungere l'oggetto per il <xref:System.Windows.UIElement.StylusPlugIns%2A> insieme del <xref:System.Windows.UIElement>. Per ulteriori informazioni su questa interazione, vedere [intercettazione Input dallo stilo](../../../../docs/framework/wpf/advanced/intercepting-input-from-the-stylus.md).  
  
 In tutte le piattaforme, un pool di thread riceve i dati di input penna tramite gli eventi dello stilo e lo invia al thread dell'applicazione.  Per ulteriori informazioni sul threading nelle piattaforme Windows e COM, vedere [Threading Considerations for the StylusInput APIs](http://msdn.microsoft.com/5d98768a-c60b-4bb0-8640-9bf38254d41f).  Per ulteriori informazioni sul threading al software di presentazione di Windows, vedere [al modello di Threading dell'input penna](../../../../docs/framework/wpf/advanced/the-ink-threading-model.md).  
  
 Nella figura seguente vengono confrontati i modelli a oggetti per le classi che ricevono dati penna nel pool di thread di penna.  
  
 ![Diagramma del modello StylusPlugIn in WPF e Windows Form. ] (../../../../docs/framework/wpf/advanced/media/ink-stylusplugins.png "Ink_StylusPlugins")
