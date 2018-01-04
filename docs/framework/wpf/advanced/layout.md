---
title: Layout
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WPF layout system [WPF]
- controls [WPF], layout system
- layout system [WPF]
ms.assetid: 3eecdced-3623-403a-a077-7595453a9221
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c9a5f33ab22779002e85d7a73b29ae74dac81c26
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="layout"></a>Layout
Questo argomento descrive il sistema di layout di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. La capacità di identificare correttamente i casi in cui vengono eseguiti calcoli del layout è essenziale per la creazione di interfacce utente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Di seguito sono elencate le diverse sezioni di questo argomento:  
  
-   [Rettangoli di selezione degli elementi](#LayoutSystem_BoundingBox)  
  
-   [Sistema di layout](#LayoutSystem_Overview)  
  
-   [Misurazione e disposizione degli elementi figlio](#LayoutSystem_Measure_Arrange)  
  
-   [Elementi Panel e comportamenti di layout personalizzati](#LayoutSystem_PanelsCustom)  
  
-   [Considerazioni sulle prestazioni del layout](#LayoutSystem_Performance)  
  
-   [Rendering dei sub-pixel e arrotondamento del layout](#LayoutSystem_LayoutRounding)  
  
-   [Argomenti successivi](#LayoutSystem_whatsnext)  
  
<a name="LayoutSystem_BoundingBox"></a>   
## <a name="element-bounding-boxes"></a>Rettangoli di selezione degli elementi  
 Nel considerare il layout in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], è importante comprendere il rettangolo di selezione che circonda tutti gli elementi. Ogni <xref:System.Windows.FrameworkElement> utilizzato per il layout del sistema possa essere considerato come un rettangolo inciso nel layout. La <xref:System.Windows.Controls.Primitives.LayoutInformation> classe restituisce i limiti di allocazione di layout di un elemento, o uno slot. Le dimensioni del rettangolo sono determinata da calcolare lo spazio disponibile sullo schermo, la dimensione di tutti i vincoli, proprietà specifiche del layout (ad esempio margine e spaziatura interna) e al comportamento dell'elemento padre <xref:System.Windows.Controls.Panel> elemento. Elaborazione di tali dati, il sistema di layout è in grado di calcolare la posizione di tutti gli elementi figlio di un particolare <xref:System.Windows.Controls.Panel>. È importante ricordare che le caratteristiche delle dimensioni definite per l'elemento padre, ad esempio un <xref:System.Windows.Controls.Border>, influiscono sui relativi elementi figlio.  
  
 La figura seguente mostra un layout semplice.  
  
 ![Tipico elemento Grid senza rettangolo di selezione sovrapposto](../../../../docs/framework/wpf/advanced/media/boundingbox1.png "boundingbox1")  
  
 È possibile ottenere questo layout usando il codice [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] seguente.  
  
 [!code-xaml[LayoutInformation#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LayoutInformation/CSharp/Window1.xaml#1)]  
  
 Un singolo <xref:System.Windows.Controls.TextBlock> elemento è ospitato in un <xref:System.Windows.Controls.Grid>. Mentre il testo riempie solo nell'angolo superiore sinistro della prima colonna, lo spazio allocato per il <xref:System.Windows.Controls.TextBlock> è effettivamente molto grande. Il rettangolo di selezione di qualsiasi <xref:System.Windows.FrameworkElement> può essere recuperato tramite il <xref:System.Windows.Controls.Primitives.LayoutInformation.GetLayoutSlot%2A> metodo. La figura seguente mostra il rettangolo di selezione per il <xref:System.Windows.Controls.TextBlock> elemento.  
  
 ![Il rettangolo di selezione di TextBlock è ora visibile.](../../../../docs/framework/wpf/advanced/media/boundingbox2.png "boundingbox2")  
  
 Come illustrato dal rettangolo giallo, lo spazio allocato per il <xref:System.Windows.Controls.TextBlock> elemento è effettivamente molto maggiore di quanto viene visualizzato. Con l'aggiungono di elementi aggiuntivi per il <xref:System.Windows.Controls.Grid>, questa allocazione può espandersi o ridursi, a seconda del tipo e dimensioni degli elementi che vengono aggiunti.  
  
 Lo slot di layout del <xref:System.Windows.Controls.TextBlock> viene convertita in un <xref:System.Windows.Shapes.Path> utilizzando il <xref:System.Windows.Controls.Primitives.LayoutInformation.GetLayoutSlot%2A> metodo. Questa tecnica può essere utile per la visualizzazione del rettangolo di selezione di un elemento.  
  
 [!code-csharp[LayoutInformation#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LayoutInformation/CSharp/Window1.xaml.cs#2)]
 [!code-vb[LayoutInformation#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/LayoutInformation/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="LayoutSystem_Overview"></a>   
## <a name="the-layout-system"></a>Sistema di layout  
 Nella forma più semplice, il layout è un sistema ricorsivo che fa sì che un elemento venga ridimensionato, posizionato e disegnato. In particolare, layout descrive il processo di misurazione e disposizione dei membri di un <xref:System.Windows.Controls.Panel> dell'elemento <xref:System.Windows.Controls.Panel.Children%2A> insieme. Il layout è un processo intensivo. Il più elevato di <xref:System.Windows.Controls.Panel.Children%2A> raccolta, maggiore è il numero di calcoli che devono essere eseguite. Complessità può essere introdotta anche in base al comportamento di layout definito per il <xref:System.Windows.Controls.Panel> elemento che possiede la raccolta. Relativamente semplice <xref:System.Windows.Controls.Panel>, ad esempio <xref:System.Windows.Controls.Canvas>, può avere un miglioramento significativo delle prestazioni rispetto a più complesso <xref:System.Windows.Controls.Panel>, ad esempio <xref:System.Windows.Controls.Grid>.  
  
 Ogni volta che un elemento figlio <xref:System.Windows.UIElement> cambia posizione, è in grado di eseguire un nuovo passaggio dal sistema di layout. Di conseguenza, è importante identificare gli eventi che possono richiamare il sistema di layout, perché una chiamata non necessaria può causare scarse prestazioni dell'applicazione. Di seguito viene descritto il processo avviato quando viene richiamato il sistema di layout.  
  
1.  Un elemento figlio <xref:System.Windows.UIElement> inizia il processo di layout con la misurazione delle relative proprietà core.  
  
2.  Ridimensionamento le proprietà definite su <xref:System.Windows.FrameworkElement> vengono valutate, ad esempio <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Height%2A>, e <xref:System.Windows.FrameworkElement.Margin%2A>.  
  
3.  <xref:System.Windows.Controls.Panel>-viene applicata la logica specifica, ad esempio <xref:System.Windows.Controls.Dock> direzione o sovrapposizione <xref:System.Windows.Controls.StackPanel.Orientation%2A>.  
  
4.  Il contenuto viene disposto dopo la misurazione di tutti gli elementi figlio.  
  
5.  Il <xref:System.Windows.Controls.Panel.Children%2A> insieme viene disegnato sullo schermo.  
  
6.  Il processo viene nuovamente richiamato se altri <xref:System.Windows.Controls.Panel.Children%2A> vengono aggiunti alla raccolta, un <xref:System.Windows.FrameworkElement.LayoutTransform%2A> viene applicato, o <xref:System.Windows.UIElement.UpdateLayout%2A> metodo viene chiamato.  
  
 Questo processo e il modo in cui viene richiamato vengono descritti con maggiori dettagli nelle sezioni seguenti.  
  
<a name="LayoutSystem_Measure_Arrange"></a>   
## <a name="measuring-and-arranging-children"></a>Misurazione e disposizione degli elementi figlio  
 Il sistema di layout completa due passaggi per ogni membro del <xref:System.Windows.Controls.Panel.Children%2A> insieme, un passaggio di misurazione e un passaggio di disposizione. Ogni elemento figlio <xref:System.Windows.Controls.Panel> fornisce la propria <xref:System.Windows.FrameworkElement.MeasureOverride%2A> e <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> metodi per ottenere un comportamento di layout specifiche.  
  
 Durante il passaggio di misurazione, ogni membro del <xref:System.Windows.Controls.Panel.Children%2A> raccolta viene valutata. Il processo inizia con una chiamata al <xref:System.Windows.UIElement.Measure%2A> metodo. Questo metodo viene chiamato all'interno dell'implementazione dell'elemento padre <xref:System.Windows.Controls.Panel> elemento e non deve essere chiamato in modo esplicito per eseguire il layout.  
  
 Le proprietà di dimensione nativo prima del <xref:System.Windows.UIElement> vengono valutate, ad esempio <xref:System.Windows.UIElement.Clip%2A> e <xref:System.Windows.UIElement.Visibility%2A>. Viene generato un valore denominato `constraintSize` che viene passata a <xref:System.Windows.FrameworkElement.MeasureCore%2A>.  
  
 In secondo luogo, le proprietà di framework definite in <xref:System.Windows.FrameworkElement> vengono elaborati, che influisce sul valore di `constraintSize`. In genere, queste proprietà descrivono le caratteristiche di ridimensionamento dell'oggetto sottostante <xref:System.Windows.UIElement>, ad esempio il <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, e <xref:System.Windows.FrameworkElement.Style%2A>. Ognuna di queste proprietà può modificare lo spazio necessario per visualizzare l'elemento. <xref:System.Windows.FrameworkElement.MeasureOverride%2A>viene quindi chiamato con `constraintSize` come parametro.  
  
> [!NOTE]
>  Non c'è una differenza tra le proprietà di <xref:System.Windows.FrameworkElement.Height%2A> e <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.ActualHeight%2A> e <xref:System.Windows.FrameworkElement.ActualWidth%2A>. Ad esempio, il <xref:System.Windows.FrameworkElement.ActualHeight%2A> proprietà è un valore calcolato basato su altri input di altezza e il sistema di layout. Il valore viene impostato dal sistema di layout, in base a un passaggio di rendering effettivo e potrebbe pertanto rimanere indietro rispetto al valore impostato di proprietà, ad esempio <xref:System.Windows.FrameworkElement.Height%2A>, che costituiscono la base della modifica dell'input.  
>   
>  Poiché <xref:System.Windows.FrameworkElement.ActualHeight%2A> è un valore calcolato, è necessario essere consapevoli che potrebbe essere più modifiche o modifiche incrementali a esso in seguito a operazioni diverse dal sistema di layout. Il sistema di layout può calcolare lo spazio di misurazione necessario per gli elementi figlio, i vincoli dell'elemento padre e così via.  
  
 È l'obiettivo finale di passaggio di misurazione per determinare l'elemento figlio relativo <xref:System.Windows.UIElement.DesiredSize%2A>, che si verifica durante la <xref:System.Windows.FrameworkElement.MeasureCore%2A> chiamare. Il <xref:System.Windows.UIElement.DesiredSize%2A> valore viene archiviato dal <xref:System.Windows.UIElement.Measure%2A> da utilizzare durante il passaggio di disposizione del contenuto.  
  
 Il passaggio di disposizione inizia con una chiamata al <xref:System.Windows.UIElement.Arrange%2A> metodo. Durante questo passaggio, l'elemento padre <xref:System.Windows.Controls.Panel> elemento genera un rettangolo che rappresenta i limiti dell'elemento figlio. Questo valore viene passato per il <xref:System.Windows.FrameworkElement.ArrangeCore%2A> metodo per l'elaborazione.  
  
 Il <xref:System.Windows.FrameworkElement.ArrangeCore%2A> metodo valuta il <xref:System.Windows.UIElement.DesiredSize%2A> dell'elemento figlio e qualsiasi margini aggiuntivi che possono influire sulle dimensioni di rendering dell'elemento. <xref:System.Windows.FrameworkElement.ArrangeCore%2A>Genera un `arrangeSize`, che viene passato al <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> metodo il <xref:System.Windows.Controls.Panel> come parametro. <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>Genera il `finalSize` dell'elemento figlio. Infine, il <xref:System.Windows.FrameworkElement.ArrangeCore%2A> metodo esegue una valutazione delle proprietà di offset, ad esempio margine e l'allineamento e posiziona l'elemento figlio all'interno del relativo slot di layout. L'elemento figlio non deve necessariamente (e in genere non lo fa) occupare l'intero spazio allocato. Il controllo viene quindi restituito al padre <xref:System.Windows.Controls.Panel> e il processo di layout è stato completato.  
  
<a name="LayoutSystem_PanelsCustom"></a>   
## <a name="panel-elements-and-custom-layout-behaviors"></a>Elementi Panel e comportamenti di layout personalizzati  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]include un gruppo di elementi che derivano da <xref:System.Windows.Controls.Panel>. Questi <xref:System.Windows.Controls.Panel> elementi abilitano numerosi layout complessi. Ad esempio, sovrapposizione di elementi può facilmente essere ottenuto utilizzando il <xref:System.Windows.Controls.StackPanel> elemento, anche se sono possibili più complessi e layout utilizzando un <xref:System.Windows.Controls.Canvas>.  
  
 Nella tabella seguente sono riepilogati i layout disponibili <xref:System.Windows.Controls.Panel> elementi.  
  
|Nome elemento Panel|Descrizione|  
|----------------|-----------------|  
|<xref:System.Windows.Controls.Canvas>|Definisce un'area all'interno del quale è possibile posizionare in modo esplicito gli elementi figlio utilizzando coordinate relative la <xref:System.Windows.Controls.Canvas> area.|  
|<xref:System.Windows.Controls.DockPanel>|Definisce un'area all'interno della quale è possibile disporre elementi figlio in orizzontale o in verticale, l'uno rispetto all'altro.|  
|<xref:System.Windows.Controls.Grid>|Definisce un'area griglia flessibile costituita da righe e colonne.|  
|<xref:System.Windows.Controls.StackPanel>|Dispone gli elementi figlio su una sola riga che può essere orientata orizzontalmente o verticalmente.|  
|<xref:System.Windows.Controls.VirtualizingPanel>|Fornisce un framework per <xref:System.Windows.Controls.Panel> elementi virtualizzazione della raccolta dati figlio corrispondente. Questa è una classe abstract.|  
|<xref:System.Windows.Controls.WrapPanel>|Posiziona gli elementi figlio in sequenza da sinistra a destra, interrompendo il contenuto al raggiungimento del bordo della casella contenitore e facendolo ripartire dalla riga successiva. Ordinamento successivo si verifica in modo sequenziale dall'alto verso il basso o da destra a sinistra, in base al valore di <xref:System.Windows.Controls.WrapPanel.Orientation%2A> proprietà.|  
  
 Per le applicazioni che richiedono un layout che non è possibile tramite predefiniti <xref:System.Windows.Controls.Panel> elementi, i comportamenti di layout personalizzato possono essere ottenuti ereditando dalla <xref:System.Windows.Controls.Panel> ed eseguendo l'override di <xref:System.Windows.FrameworkElement.MeasureOverride%2A> e <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> metodi. Per un esempio, vedere l'[esempio di pannello radiale personalizzato](http://go.microsoft.com/fwlink/?LinkID=159982).  
  
<a name="LayoutSystem_Performance"></a>   
## <a name="layout-performance-considerations"></a>Considerazioni sulle prestazioni del layout  
 Il layout è un processo ricorsivo. Ogni elemento figlio di un <xref:System.Windows.Controls.Panel.Children%2A> insieme viene elaborato durante ogni chiamata del sistema di layout. Di conseguenza, è consigliabile evitare l'attivazione del sistema di layout quando non è necessaria. Le considerazioni seguenti possono essere utili per ottenere prestazioni migliori.  
  
-   Identificare le modifiche dei valori di proprietà che forzeranno un aggiornamento ricorsivo da parte del sistema di layout.  
  
     Le proprietà di dipendenza i cui valori possono provocare l'inizializzazione del sistema di layout sono contrassegnate con flag pubblici. <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>e <xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A> forniscono indizi utili per la proprietà valore viene modificato forzerà una ricorsiva aggiornare dal sistema di layout. In generale, qualsiasi proprietà che possono influenzare le dimensioni del rettangolo di selezione dell'elemento è necessario un <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A> flag impostato su true. Per altre informazioni, vedere [Panoramica sulle proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
-   Quando possibile, utilizzare un <xref:System.Windows.UIElement.RenderTransform%2A> anziché un <xref:System.Windows.FrameworkElement.LayoutTransform%2A>.  
  
     Oggetto <xref:System.Windows.FrameworkElement.LayoutTransform%2A> può essere molto utile per determinare il contenuto di un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Tuttavia, se l'effetto della trasformazione non ha alcun impatto sulla posizione di altri elementi, è consigliabile utilizzare un <xref:System.Windows.UIElement.RenderTransform%2A> invece perché <xref:System.Windows.UIElement.RenderTransform%2A> non richiama il sistema di layout. <xref:System.Windows.FrameworkElement.LayoutTransform%2A>Applica la trasformazione e forza un aggiornamento ricorsivo del layout per la nuova posizione dell'elemento interessato.  
  
-   Evitare le chiamate a <xref:System.Windows.UIElement.UpdateLayout%2A>.  
  
     Il <xref:System.Windows.UIElement.UpdateLayout%2A> metodo forza un aggiornamento ricorsivo del layout e spesso non è necessario. Se non si ha la certezza della necessità di un aggiornamento completo, lasciare che sia il sistema di layout a chiamare automaticamente questo metodo.  
  
-   Quando si lavora con una grande <xref:System.Windows.Controls.Panel.Children%2A> insieme, è consigliabile utilizzare un <xref:System.Windows.Controls.VirtualizingStackPanel> anziché una normale <xref:System.Windows.Controls.StackPanel>.  
  
     Mediante la virtualizzazione della raccolta figlio, il <xref:System.Windows.Controls.VirtualizingStackPanel> solo degli oggetti in memoria che sono attualmente nel riquadro di visualizzazione dell'elemento padre. Come conseguenza, le prestazioni risultano notevolmente migliorate nella maggior parte degli scenari.  
  
<a name="LayoutSystem_LayoutRounding"></a>   
## <a name="sub-pixel-rendering-and-layout-rounding"></a>Rendering dei sub-pixel e arrotondamento del layout  
 Il sistema grafico di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa unità indipendenti dal dispositivo per assicurare l'indipendenza dalla risoluzione e dal dispositivo. Ogni Device Independent Pixel viene ridimensionato automaticamente con l'impostazione [!INCLUDE[TLA#tla_dpi](../../../../includes/tlasharptla-dpi-md.md)] del sistema. In questo modo, le applicazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ottengono il ridimensionamento appropriato per impostazioni [!INCLUDE[TLA2#tla_dpi](../../../../includes/tla2sharptla-dpi-md.md)] diverse e l'applicazione viene automaticamente resa sensibile ai valori [!INCLUDE[TLA2#tla_dpi](../../../../includes/tla2sharptla-dpi-md.md)].  
  
 Tuttavia, questa indipendenza dai [!INCLUDE[TLA2#tla_dpi](../../../../includes/tla2sharptla-dpi-md.md)] può creare un rendering dei bordi irregolare a causa dell'anti-aliasing. Questi elementi, osservabili in genere come bordi sfocati o semitrasparenti, possono essere presenti quando la posizione dei bordi si trova al centro di un pixel del dispositivo invece che tra pixel del dispositivo. Il sistema di layout permette di ovviare a questo problema con l'arrotondamento del layout. L'arrotondamento del layout avviene quando il sistema di layout arrotonda valori di pixel non integrali durante il passaggio di layout.  
  
 L'arrotondamento del layout è disabilitato per impostazione predefinita. Per abilitare l'arrotondamento del layout, impostare il <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> proprietà `true` su qualsiasi <xref:System.Windows.FrameworkElement>. Poiché si tratta di una proprietà di dipendenza, il valore viene propagato a tutti gli elementi figlio nell'albero visuale. Per abilitare l'arrotondamento del layout per l'intera interfaccia utente, impostare <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> a `true` nel contenitore radice. Per un esempio, vedere <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A>.  
  
<a name="LayoutSystem_whatsnext"></a>   
## <a name="whats-next"></a>Argomenti successivi  
 La capacità di identificare il modo in cui gli elementi vengono misurati e disposti è il primo passaggio per la comprensione del layout. Per ulteriori informazioni sui contatori <xref:System.Windows.Controls.Panel> elementi, vedere [Panoramica pannelli](../../../../docs/framework/wpf/controls/panels-overview.md). Per meglio determinare le diverse proprietà di posizionamento che possono influire sul layout, vedere [Panoramica su allineamento, margini e spaziatura interna](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md). Per un esempio di un oggetto personalizzato <xref:System.Windows.Controls.Panel> elemento, vedere [esempio pannello radiale personalizzato](http://go.microsoft.com/fwlink/?LinkID=159982). Quando si è pronti per mettere in pratica tutti insieme in un'applicazione leggera, vedere [procedura dettagliata: applicazione desktop WPF prima](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.FrameworkElement>  
 <xref:System.Windows.UIElement>  
 [Cenni preliminari sugli elementi Panel](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Panoramica su allineamento, margini e spaziatura interna](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md)  
 [Ottimizzazione delle prestazioni: layout e progettazione](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)
