---
title: Modello di threading dell'input penna
ms.date: 03/30/2017
helpviewer_keywords:
- application user interface thread [WPF]
- stylus plug-in
- ink threading model [WPF]
- ink [WPF], rendering
- pen thread [WPF]
- threading model [WPF]
- rendering ink [WPF]
- dynamic rendering thread [WPF]
- ink collection plug-in
- plug-ins [WPF], for ink
ms.assetid: c85fcad1-cb50-4431-847c-ac4145a35c89
ms.openlocfilehash: cc0ff8a2345bd945dd2fffdfda80f00e1ab99c67
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="the-ink-threading-model"></a>Modello di threading dell'input penna
Uno dei vantaggi dell'input penna di Tablet PC è che sensazione di scrittura con carta e penna regolare.  A tale scopo, la penna di Tablet PC raccoglie dati di input a una velocità maggiore rispetto a un mouse ed esegue il rendering dell'input penna mentre l'utente scrive.  Thread di interfaccia utente dell'applicazione non è sufficiente per la raccolta dei dati della penna e input penna di rendering, in quanto può essere bloccato.  Per risolvere il problema, un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione utilizza due thread aggiuntivi quando un utente scrive input penna.  
  
 Nell'elenco seguente vengono descritti i thread che prendono parte nella raccolta e il rendering di input penna:  
  
-   Thread di penna: il thread che accetta l'input dallo stilo.  (In realtà, si tratta di un pool di thread, ma in questo argomento fa riferimento come thread di penna)  
  
-   Thread dell'interfaccia utente dell'applicazione, il thread che controlla l'interfaccia utente dell'applicazione.  
  
-   Thread di rendering dinamico, il thread che esegue il rendering dell'input penna mentre l'utente disegna un tratto. Il thread di rendering dinamico è diverso dal thread che esegue il rendering di altri elementi dell'interfaccia utente per l'applicazione, come indicato nella finestra WPF [il modello di Threading](../../../../docs/framework/wpf/advanced/threading-model.md).  
  
 Il modello di input penna è lo stesso sia l'applicazione utilizza il <xref:System.Windows.Controls.InkCanvas> o un controllo personalizzato simile a quello di [creazione di un controllo di Input penna](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).  Anche se in questo argomento viene descritto in termini di threading di <xref:System.Windows.Controls.InkCanvas>, gli stessi concetti si applicano quando si crea un controllo personalizzato.  
  
## <a name="threading-overview"></a>Cenni preliminari sul threading  
 Il diagramma seguente illustra il modello di threading quando un utente consente di disegnare un tratto:  
  
 ![Modello di threading nel disegno di un tratto. ] (../../../../docs/framework/wpf/advanced/media/inkthreading-drawingink.png "InkThreading_DrawingInk")  
  
1.  Azioni eseguite mentre l'utente disegna il tratto  
  
    1.  Quando l'utente disegna un tratto, i punti dello stilo entrano nel thread di penna.  Plug-in dello stilo, incluso il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, accettare i punti dello stilo nel thread di penna e hanno la possibilità di modificarli prima che il <xref:System.Windows.Controls.InkCanvas> li riceve.  
  
    2.  Il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> esegue il rendering di punti dello stilo nel thread di rendering dinamico. Ciò avviene nello stesso momento del passaggio precedente.  
  
    3.  Il <xref:System.Windows.Controls.InkCanvas> riceve i punti dello stilo nel thread dell'interfaccia utente.  
  
2.  Azioni eseguite dopo che l'utente termina il tratto  
  
    1.  Quando l'utente termina di tracciare il tratto, il <xref:System.Windows.Controls.InkCanvas> crea un <xref:System.Windows.Ink.Stroke> e lo aggiunge al <xref:System.Windows.Controls.InkPresenter>, che in modo statico ne esegue il rendering.  
  
    2.  Gli avvisi di thread dell'interfaccia utente di <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> tratto sottoposto al rendering in modo statico, pertanto la <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> rimuove la rappresentazione visiva del tratto.  
  
## <a name="ink-collection-and-stylus-plug-ins"></a>Raccolta di input penna e Plug-in dello stilo  
 Ogni <xref:System.Windows.UIElement> ha un <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.  Il <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> gli oggetti di <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> ricevono e possono modificare i punti dello stilo nel thread di penna. Il <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> oggetti ricevono i punti dello stilo in base all'ordine nel <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.  
  
 Il diagramma seguente illustra la situazione ipotetica in cui il <xref:System.Windows.UIElement.StylusPlugIns%2A> raccolta di un <xref:System.Windows.UIElement> contiene `stylusPlugin1`, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, e `stylusPlugin2`, in questo ordine.  
  
 ![Ordine di StylusPlugIns influisce sull'output. ] (../../../../docs/framework/wpf/advanced/media/inkthreading-pluginorder.png "InkThreading_PluginOrder")  
  
 Nel diagramma precedente, il comportamento seguente viene eseguita:  
  
1.  `StylusPlugin1` Modifica i valori per x e y.  
  
2.  <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> riceve i punti dello stilo modificati e li esegue il rendering nel thread di rendering dinamico.  
  
3.  `StylusPlugin2` riceve i punti dello stilo modificati e un'ulteriore modifica i valori per x e y.  
  
4.  L'applicazione raccoglie i punti dello stilo e, quando l'utente termina il tratto, in modo statico esegue il rendering del tratto.  
  
 Si supponga che `stylusPlugin1` limita i punti dello stilo a un rettangolo e `stylusPlugin2` converte i punti dello stilo a destra.  Nello scenario precedente, il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> riceve i punti dello stilo limitati, ma non dello stilo tradotti.  Quando l'utente disegna il tratto, entro i limiti del rettangolo di rendering del tratto, ma il tratto non sembra essere convertiti solo quando l'utente solleva la penna.  
  
### <a name="performing-operations-with-a-stylus-plug-in-on-the-ui-thread"></a>Esecuzione di operazioni con uno stilo plug-nel thread UI  
 Poiché hit test accurati non possono essere eseguite sul thread di penna, alcuni elementi possono a volte ricevere input con stilo destinato ad altri elementi. Se è necessario assicurarsi che l'input sia stato indirizzato correttamente prima di eseguire un'operazione, sottoscrivere ed eseguire l'operazione di <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusDownProcessed%2A>, <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusMoveProcessed%2A>, o <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusUpProcessed%2A> metodo. Questi metodi vengono richiamati dal thread dell'applicazione dopo l'esecuzione di hit test accurati. Per sottoscrivere questi metodi, chiamare il <xref:System.Windows.Input.StylusPlugIns.RawStylusInput.NotifyWhenProcessed%2A> metodo nel metodo che si verifica nel thread di penna.  
  
 Il diagramma seguente illustra la relazione tra il thread di penna e il thread dell'interfaccia utente rispetto agli eventi dello stilo di un <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>.  
  
 ![Modelli di Threading dell'input penna &#40;dell'interfaccia utente e penna&#41;](../../../../docs/framework/wpf/advanced/media/inkthreading-plugincallbacks.png "InkThreading_PluginCallbacks")  
  
## <a name="rendering-ink"></a>Il rendering di input penna  
 Come l'utente disegna un tratto, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> esegue il rendering dell'input penna in un thread separato in modo sembri "fluire" dalla penna anche quando il thread UI è occupato.  Il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> compila un struttura ad albero visuale del thread di rendering dinamico mentre raccoglie punti dello stilo.  Quando l'utente termina la traccia, il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> chiede di ricevere una notifica quando l'applicazione esegue il passaggio successivo per il rendering.  Dopo l'applicazione ha completato il passaggio di rendering successivo, il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> pulisce la struttura ad albero visuale.  Nel diagramma seguente viene illustrato questo processo.  
  
 ![Diagramma di threading dell'input penna](../../../../docs/framework/wpf/advanced/media/inkthreading-visualtree.png "InkThreading_VisualTree")  
  
1.  L'utente inizia il tratto.  
  
    1.  Il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> crea la struttura ad albero visuale.  
  
2.  L'utente disegna il tratto.  
  
    1.  Il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> compila la struttura ad albero visuale.  
  
3.  L'utente termina la traccia.  
  
    1.  Il <xref:System.Windows.Controls.InkPresenter> aggiunge il tratto alla struttura ad albero visiva.  
  
    2.  Il livello di integrazione Media (MIL) in modo statico sottoposto a rendering.  
  
    3.  Il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> pulisce la visualizzazione.
