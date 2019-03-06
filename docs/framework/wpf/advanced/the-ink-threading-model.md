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
ms.openlocfilehash: 8089c857d2406f8cfb357ba2efe188ad84605541
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377027"
---
# <a name="the-ink-threading-model"></a>Modello di threading dell'input penna
Uno dei vantaggi dell'input penna su un Tablet PC è che presenta notevoli analogie con la scrittura con una carta e penna regolare.  A tale scopo, la penna del tablet PC raccoglie i dati di input con una frequenza molto più elevato rispetto a un mouse ed esegue il rendering dell'input penna mentre l'utente scrive.  Thread dell'interfaccia utente dell'applicazione non è sufficiente per la raccolta dei dati della penna e rendering di input penna, perché può essere bloccato.  Per risolvere il problema, un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazione utilizza due thread aggiuntivi quando l'utente scrive tramite input penna.  
  
 L'elenco seguente descrive il thread che partecipano nella raccolta e il rendering dell'input penna digitale:  
  
-   Thread di penna - il thread che accetta l'input dallo stilo.  (In realtà, si tratta di un pool di thread, ma in questo argomento fa riferimento a esso come un thread di penna).  
  
-   Thread interfaccia utente dell'applicazione - il thread che controlla l'interfaccia utente dell'applicazione.  
  
-   Thread di rendering dinamico - il thread che esegue il rendering dell'input penna mentre l'utente consente di disegnare un tratto. Il thread di rendering dinamico è diverso rispetto al thread che esegue il rendering di altri elementi dell'interfaccia utente per l'applicazione, come indicato in Windows Presentation Foundation [modello di Threading](threading-model.md).  
  
 Il modello di input penna non cambiano se l'applicazione usa la <xref:System.Windows.Controls.InkCanvas> o un controllo personalizzato simile a quello riportato nella [creazione di un controllo Input penna](creating-an-ink-input-control.md).  Anche se il threading in termini di questo argomento viene descritto il <xref:System.Windows.Controls.InkCanvas>, gli stessi concetti si applicano quando si crea un controllo personalizzato.  
  
## <a name="threading-overview"></a>Cenni preliminari sul threading  
 Quando un utente consente di disegnare un tratto, il diagramma seguente illustra il modello di threading:  
  
 ![Modello di threading nel disegno di un tratto. ](./media/inkthreading-drawingink.png "InkThreading_DrawingInk")  
  
1.  Azioni che si verificano mentre l'utente lo disegna  
  
    1.  Quando l'utente consente di disegnare un tratto, i punti dello stilo sono disponibili in sul thread di penna.  Plug-in dello stilo, tra cui il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, accettare i punti dello stilo sul thread di penna e ha la possibilità di modificarli prima di <xref:System.Windows.Controls.InkCanvas> li riceve.  
  
    2.  Il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> esegue il rendering dei punti dello stilo nel thread di rendering dinamico. Ciò si verifica nello stesso momento del passaggio precedente.  
  
    3.  Il <xref:System.Windows.Controls.InkCanvas> riceve i punti dello stilo sul thread UI.  
  
2.  Azioni che si verificano dopo che l'utente termina il tratto  
  
    1.  Quando l'utente completa il disegno del tratto, la <xref:System.Windows.Controls.InkCanvas> crea un' <xref:System.Windows.Ink.Stroke> dell'oggetto e lo aggiunge al <xref:System.Windows.Controls.InkPresenter>, che in modo statico ne esegue il rendering.  
  
    2.  Gli avvisi di thread dell'interfaccia utente di <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> che in modo statico di rendering del tratto, pertanto la <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> rimuove la rappresentazione visiva del tratto.  
  
## <a name="ink-collection-and-stylus-plug-ins"></a>Raccolta di input penna e Plug-in dello stilo  
 Ciascuna <xref:System.Windows.UIElement> ha un <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.  Il <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> oggetti nel <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> ricevono e possono modificare i punti dello stilo sul thread di penna. Il <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> gli oggetti ricevono i punti dello stilo in base al relativo ordine nella <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.  
  
 Il diagramma seguente illustra lo scenario ipotetico in cui il <xref:System.Windows.UIElement.StylusPlugIns%2A> raccolta di un <xref:System.Windows.UIElement> contiene `stylusPlugin1`, una <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, e `stylusPlugin2`, in questo ordine.  
  
 ![Ordine di StylusPlugIns influisce sull'output. ](./media/inkthreading-pluginorder.png "InkThreading_PluginOrder")  
  
 Nel diagramma precedente, il comportamento seguente viene eseguita:  
  
1.  `StylusPlugin1` Modifica i valori per x e y.  
  
2.  <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> riceve i punti dello stilo modificato e ne esegue il rendering nel thread di rendering dinamico.  
  
3.  `StylusPlugin2` riceve i punti dello stilo modificato e ulteriore modifica i valori per x e y.  
  
4.  L'applicazione raccoglie i punti dello stilo e, quando l'utente completa del tratto, in modo statico viene eseguito il rendering del tratto.  
  
 Si supponga che `stylusPlugin1` limita i punti dello stilo a un rettangolo e `stylusPlugin2` converte i punti dello stilo a destra.  Nello scenario precedente, il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> riceve i punti dello stilo limitato, ma non i punti dello stilo tradotti.  Quando l'utente lo disegna, entro i limiti del rettangolo di rendering del tratto, ma il tratto non sembra essere tradotto fino a quando l'utente solleva la penna.  
  
### <a name="performing-operations-with-a-stylus-plug-in-on-the-ui-thread"></a>Esecuzione di operazioni con uno stilo plug-in sul thread UI  
 Poiché hit test accurati non possono essere eseguite sul thread di penna, alcuni elementi potrebbero ricevere occasionalmente input dello stilo destinato ad altri elementi. Se è necessario assicurarsi che l'input è stato instradato correttamente prima di eseguire un'operazione, sottoscrivere ed eseguire l'operazione dei <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusDownProcessed%2A>, <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusMoveProcessed%2A>, o <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusUpProcessed%2A> (metodo). Questi metodi vengono richiamati dal thread dell'applicazione dopo l'esecuzione di hit test accurati. Per eseguire la sottoscrizione a questi metodi, chiamare il <xref:System.Windows.Input.StylusPlugIns.RawStylusInput.NotifyWhenProcessed%2A> metodo nel metodo che si verifica nel thread di penna.  
  
 Il diagramma seguente illustra la relazione tra il thread di penna e il thread dell'interfaccia utente per quanto riguarda gli eventi dello stilo di un <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>.  
  
 ![Modelli di Threading dell'input penna &#40;dell'interfaccia utente e penna&#41;](./media/inkthreading-plugincallbacks.png "InkThreading_PluginCallbacks")  
  
## <a name="rendering-ink"></a>Il rendering dell'input penna  
 Quando l'utente consente di disegnare un tratto, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> esegue il rendering dell'input penna in un thread separato in modo che sembri "fluire" dalla penna anche quando il thread UI è occupato.  Il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> compila un struttura ad albero visuale nel thread di rendering dinamico che raccoglie i punti dello stilo.  Quando l'utente completa il tratto di <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> chiede di ricevere una notifica quando l'applicazione esegue il successivo passaggio di rendering.  Dopo l'applicazione ha completato il passaggio successivo per il rendering, il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> pulisce la struttura ad albero visuale.  Il diagramma seguente illustra questo processo.  
  
 ![Diagramma di threading dell'input penna](./media/inkthreading-visualtree.png "InkThreading_VisualTree")  
  
1.  L'utente inizia il tratto.  
  
    1.  Il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> crea la struttura ad albero visuale.  
  
2.  L'utente lo disegna il tratto.  
  
    1.  Il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> compila la struttura ad albero visuale.  
  
3.  L'utente termina il tratto.  
  
    1.  Il <xref:System.Windows.Controls.InkPresenter> aggiunge il tratto alla relativa struttura ad albero visuale.  
  
    2.  Il livello di integrazione Media (MIL) sottoposto a rendering statico.  
  
    3.  Il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> pulisce gli oggetti visivi.
