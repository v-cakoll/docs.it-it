---
title: Layout
description: Informazioni su come e quando vengono eseguiti i calcoli del layout nel sistema di layout Windows Presentation Foundation.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WPF layout system [WPF]
- controls [WPF], layout system
- layout system [WPF]
ms.assetid: 3eecdced-3623-403a-a077-7595453a9221
ms.openlocfilehash: 0db3f2a6cbabc610362435d64de3fc970f01a73c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164766"
---
# <a name="layout"></a>Layout

In questo argomento viene descritto il sistema di layout Windows Presentation Foundation (WPF). Comprendere come e quando si verificano i calcoli di layout è essenziale per la creazione di interfacce utente in WPF.

In questo argomento sono incluse le sezioni seguenti:

- [Rettangoli di selezione degli elementi](#LayoutSystem_BoundingBox)

- [Sistema di layout](#LayoutSystem_Overview)

- [Misurazione e disposizione degli elementi figlio](#LayoutSystem_Measure_Arrange)

- [Elementi Panel e comportamenti di layout personalizzati](#LayoutSystem_PanelsCustom)

- [Considerazioni sulle prestazioni del layout](#LayoutSystem_Performance)

- [Rendering dei sub-pixel e arrotondamento del layout](#LayoutSystem_LayoutRounding)

- [Passaggi successivi](#LayoutSystem_whatsnext)

<a name="LayoutSystem_BoundingBox"></a>

## <a name="element-bounding-boxes"></a>Rettangoli di selezione degli elementi

Quando si pensa al layout in WPF, è importante comprendere il rettangolo di delimitazione che racchiude tutti gli elementi. Ogni oggetto <xref:System.Windows.FrameworkElement> utilizzato dal sistema di layout può essere considerato come un rettangolo con slot nel layout. La <xref:System.Windows.Controls.Primitives.LayoutInformation> classe restituisce i limiti dell'allocazione del layout di un elemento o dello slot. Le dimensioni del rettangolo vengono determinate calcolando lo spazio disponibile sullo schermo, la dimensione di tutti i vincoli, le proprietà specifiche del layout (ad esempio Margin e Padding) e il singolo comportamento dell' <xref:System.Windows.Controls.Panel> elemento padre. Elaborando questi dati, il sistema di layout è in grado di calcolare la posizione di tutti gli elementi figlio di un particolare <xref:System.Windows.Controls.Panel> . È importante ricordare che le caratteristiche di ridimensionamento definite nell'elemento padre, ad esempio <xref:System.Windows.Controls.Border> , influiscono sui relativi elementi figlio.

La figura seguente mostra un layout semplice.

![Screenshot che mostra una griglia tipica, senza un riquadro sovrapposto.](./media/layout/grid-no-bounding-box-superimpose.png)

È possibile ottenere questo layout usando il codice [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] seguente.

[!code-xaml[LayoutInformation#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LayoutInformation/CSharp/Window1.xaml#1)]

Un singolo <xref:System.Windows.Controls.TextBlock> elemento è ospitato all'interno di un oggetto <xref:System.Windows.Controls.Grid> . Mentre il testo riempie solo l'angolo superiore sinistro della prima colonna, lo spazio allocato per l'oggetto <xref:System.Windows.Controls.TextBlock> è effettivamente molto più grande. Il rettangolo di delimitazione di Any <xref:System.Windows.FrameworkElement> può essere recuperato tramite il <xref:System.Windows.Controls.Primitives.LayoutInformation.GetLayoutSlot%2A> metodo. Nell'illustrazione seguente viene mostrato il rettangolo di delimitazione per l' <xref:System.Windows.Controls.TextBlock> elemento.

![Screenshot che mostra che il rettangolo di delimitazione di TextBlock è ora visibile.](./media/layout/visible-textblock-bounding-box.png)

Come illustrato dal rettangolo giallo, lo spazio allocato per l' <xref:System.Windows.Controls.TextBlock> elemento è in realtà molto più grande di quanto appaia. Con l'aggiunta di elementi aggiuntivi all'oggetto <xref:System.Windows.Controls.Grid> , l'allocazione può ridursi o espandersi, a seconda del tipo e delle dimensioni degli elementi aggiunti.

Lo slot di layout dell'oggetto <xref:System.Windows.Controls.TextBlock> viene convertito in un oggetto <xref:System.Windows.Shapes.Path> utilizzando il <xref:System.Windows.Controls.Primitives.LayoutInformation.GetLayoutSlot%2A> metodo. Questa tecnica può essere utile per la visualizzazione del rettangolo di selezione di un elemento.

[!code-csharp[LayoutInformation#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LayoutInformation/CSharp/Window1.xaml.cs#2)]
[!code-vb[LayoutInformation#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LayoutInformation/VisualBasic/Window1.xaml.vb#2)]

<a name="LayoutSystem_Overview"></a>

## <a name="the-layout-system"></a>Sistema di layout

Nella forma più semplice, il layout è un sistema ricorsivo che fa sì che un elemento venga ridimensionato, posizionato e disegnato. In particolare, il layout descrive il processo di misurazione e disposizione dei membri della raccolta di un <xref:System.Windows.Controls.Panel> elemento <xref:System.Windows.Controls.Panel.Children%2A> . Il layout è un processo intensivo. Più grande <xref:System.Windows.Controls.Panel.Children%2A> è la raccolta, maggiore è il numero di calcoli che devono essere effettuati. La complessità può anche essere introdotta in base al comportamento di layout definito dall' <xref:System.Windows.Controls.Panel> elemento proprietario della raccolta. Un oggetto relativamente semplice <xref:System.Windows.Controls.Panel> , ad esempio <xref:System.Windows.Controls.Canvas> , può avere prestazioni significativamente migliori rispetto a un più complesso <xref:System.Windows.Controls.Panel> , ad esempio <xref:System.Windows.Controls.Grid> .

Ogni volta che un elemento figlio <xref:System.Windows.UIElement> modifica la posizione, è possibile attivare un nuovo passaggio dal sistema di layout. Di conseguenza, è importante identificare gli eventi che possono richiamare il sistema di layout, perché una chiamata non necessaria può causare scarse prestazioni dell'applicazione. Di seguito viene descritto il processo avviato quando viene richiamato il sistema di layout.

1. Un figlio <xref:System.Windows.UIElement> inizia il processo di layout con le relative proprietà principali misurate.

2. Le proprietà di ridimensionamento definite in <xref:System.Windows.FrameworkElement> vengono valutate, ad esempio <xref:System.Windows.FrameworkElement.Width%2A> , <xref:System.Windows.FrameworkElement.Height%2A> e <xref:System.Windows.FrameworkElement.Margin%2A> .

3. <xref:System.Windows.Controls.Panel>viene applicata la logica specifica, ad esempio <xref:System.Windows.Controls.Dock> direzione o Stack <xref:System.Windows.Controls.StackPanel.Orientation%2A> .

4. Il contenuto viene disposto dopo la misurazione di tutti gli elementi figlio.

5. La <xref:System.Windows.Controls.Panel.Children%2A> raccolta viene disegnata sullo schermo.

6. Il processo viene richiamato di nuovo se <xref:System.Windows.Controls.Panel.Children%2A> vengono aggiunti ulteriori alla raccolta, <xref:System.Windows.FrameworkElement.LayoutTransform%2A> viene applicato un oggetto o <xref:System.Windows.UIElement.UpdateLayout%2A> viene chiamato il metodo.

Questo processo e il modo in cui viene richiamato vengono descritti con maggiori dettagli nelle sezioni seguenti.

<a name="LayoutSystem_Measure_Arrange"></a>

## <a name="measuring-and-arranging-children"></a>Misurazione e disposizione degli elementi figlio

Il sistema di layout completa due passaggi per ogni membro della <xref:System.Windows.Controls.Panel.Children%2A> raccolta, un passaggio di misurazione e un passaggio di disposizione. Ogni elemento figlio <xref:System.Windows.Controls.Panel> fornisce i <xref:System.Windows.FrameworkElement.MeasureOverride%2A> propri <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> metodi e per ottenere il proprio comportamento di layout specifico.

Durante il passaggio di misurazione, viene valutato ogni membro della <xref:System.Windows.Controls.Panel.Children%2A> raccolta. Il processo inizia con una chiamata al <xref:System.Windows.UIElement.Measure%2A> metodo. Questo metodo viene chiamato all'interno dell'implementazione dell' <xref:System.Windows.Controls.Panel> elemento padre e non deve essere chiamato in modo esplicito affinché il layout venga eseguito.

In primo luogo, vengono valutate le proprietà delle dimensioni native di <xref:System.Windows.UIElement> , ad esempio <xref:System.Windows.UIElement.Clip%2A> e <xref:System.Windows.UIElement.Visibility%2A> . Viene generato un valore denominato `constraintSize` che viene passato a <xref:System.Windows.FrameworkElement.MeasureCore%2A> .

In secondo luogo, le proprietà del framework definite in <xref:System.Windows.FrameworkElement> vengono elaborate, che influiscono sul valore di `constraintSize` . Queste proprietà in genere descrivono le caratteristiche di ridimensionamento dell'oggetto sottostante <xref:System.Windows.UIElement> , ad esempio <xref:System.Windows.FrameworkElement.Height%2A> ,, <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Margin%2A> e <xref:System.Windows.FrameworkElement.Style%2A> . Ognuna di queste proprietà può modificare lo spazio necessario per visualizzare l'elemento. <xref:System.Windows.FrameworkElement.MeasureOverride%2A>viene quindi chiamato con `constraintSize` come parametro.

> [!NOTE]
> Esiste una differenza tra le proprietà di <xref:System.Windows.FrameworkElement.Height%2A> e e <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.ActualHeight%2A> <xref:System.Windows.FrameworkElement.ActualWidth%2A> . Ad esempio, la <xref:System.Windows.FrameworkElement.ActualHeight%2A> proprietà è un valore calcolato in base ad altri input di altezza e al sistema di layout. Il valore viene impostato dal sistema di layout stesso, in base a un passaggio di rendering effettivo, e può quindi essere leggermente indietro rispetto al valore impostato delle proprietà, ad esempio <xref:System.Windows.FrameworkElement.Height%2A> , che costituiscono la base della modifica di input.
>
> Poiché <xref:System.Windows.FrameworkElement.ActualHeight%2A> è un valore calcolato, è necessario tenere presente che potrebbero essere presenti più modifiche segnalate in modo incrementale o incrementale come risultato di varie operazioni da parte del sistema di layout. Il sistema di layout può calcolare lo spazio di misurazione necessario per gli elementi figlio, i vincoli dell'elemento padre e così via.

L'obiettivo finale del passaggio di misurazione è che l'elemento figlio determini il relativo oggetto <xref:System.Windows.UIElement.DesiredSize%2A> , che si verifica durante la <xref:System.Windows.FrameworkElement.MeasureCore%2A> chiamata. Il <xref:System.Windows.UIElement.DesiredSize%2A> valore viene archiviato da <xref:System.Windows.UIElement.Measure%2A> per l'utilizzo durante il passaggio di disposizione del contenuto.

Il passaggio di disposizione inizia con una chiamata al <xref:System.Windows.UIElement.Arrange%2A> metodo. Durante il passaggio di disposizione, l' <xref:System.Windows.Controls.Panel> elemento padre genera un rettangolo che rappresenta i limiti del figlio. Questo valore viene passato al <xref:System.Windows.FrameworkElement.ArrangeCore%2A> metodo per l'elaborazione.

Il <xref:System.Windows.FrameworkElement.ArrangeCore%2A> metodo valuta l'oggetto <xref:System.Windows.UIElement.DesiredSize%2A> del figlio e valuta eventuali margini aggiuntivi che potrebbero influire sulle dimensioni di rendering dell'elemento. <xref:System.Windows.FrameworkElement.ArrangeCore%2A>genera un oggetto `arrangeSize` , che viene passato al <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> metodo di <xref:System.Windows.Controls.Panel> come parametro. <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>genera l'oggetto `finalSize` dell'oggetto figlio. Infine, il <xref:System.Windows.FrameworkElement.ArrangeCore%2A> metodo esegue una valutazione finale delle proprietà di offset, ad esempio il margine e l'allineamento, e inserisce l'elemento figlio all'interno dello slot di layout. L'elemento figlio non deve necessariamente (e in genere non lo fa) occupare l'intero spazio allocato. Il controllo viene quindi restituito al padre <xref:System.Windows.Controls.Panel> e il processo di layout è completo.

<a name="LayoutSystem_PanelsCustom"></a>

## <a name="panel-elements-and-custom-layout-behaviors"></a>Elementi Panel e comportamenti di layout personalizzati

WPF include un gruppo di elementi che derivano da <xref:System.Windows.Controls.Panel> . Questi <xref:System.Windows.Controls.Panel> elementi abilitano molti layout complessi. Ad esempio, è possibile ottenere facilmente gli elementi di stack usando l' <xref:System.Windows.Controls.StackPanel> elemento, mentre i layout più complessi e di flusso libero sono possibili usando un <xref:System.Windows.Controls.Canvas> .

Nella tabella seguente sono riepilogati gli elementi di layout disponibili <xref:System.Windows.Controls.Panel> .

|Nome elemento Panel|Descrizione|
|----------------|-----------------|
|<xref:System.Windows.Controls.Canvas>|Definisce un'area all'interno della quale è possibile posizionare in modo esplicito gli elementi figlio in base alle coordinate relative all' <xref:System.Windows.Controls.Canvas> area.|
|<xref:System.Windows.Controls.DockPanel>|Definisce un'area all'interno della quale è possibile disporre elementi figlio in orizzontale o in verticale, l'uno rispetto all'altro.|
|<xref:System.Windows.Controls.Grid>|Definisce un'area griglia flessibile costituita da righe e colonne.|
|<xref:System.Windows.Controls.StackPanel>|Dispone gli elementi figlio su una sola riga che può essere orientata orizzontalmente o verticalmente.|
|<xref:System.Windows.Controls.VirtualizingPanel>|Fornisce un framework per gli elementi <xref:System.Windows.Controls.Panel> che virtualizzano la raccolta dei dati figlio. Questa è una classe abstract.|
|<xref:System.Windows.Controls.WrapPanel>|Posiziona gli elementi figlio in sequenza da sinistra a destra, interrompendo il contenuto al raggiungimento del bordo della casella contenitore e facendolo ripartire dalla riga successiva. L'ordinamento successivo viene eseguito in sequenza dall'alto verso il basso o da destra a sinistra, a seconda del valore della <xref:System.Windows.Controls.WrapPanel.Orientation%2A> Proprietà.|

Per le applicazioni che richiedono un layout non possibile utilizzando uno degli <xref:System.Windows.Controls.Panel> elementi predefiniti, è possibile ottenere comportamenti di layout personalizzati ereditando da <xref:System.Windows.Controls.Panel> ed eseguendo l'override dei <xref:System.Windows.FrameworkElement.MeasureOverride%2A> <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> metodi e.

<a name="LayoutSystem_Performance"></a>

## <a name="layout-performance-considerations"></a>Considerazioni sulle prestazioni del layout

Il layout è un processo ricorsivo. Ogni elemento figlio in una <xref:System.Windows.Controls.Panel.Children%2A> raccolta viene elaborato durante ogni chiamata del sistema di layout. Di conseguenza, è consigliabile evitare l'attivazione del sistema di layout quando non è necessaria. Le considerazioni seguenti possono essere utili per ottenere prestazioni migliori.

- Identificare le modifiche dei valori di proprietà che forzeranno un aggiornamento ricorsivo da parte del sistema di layout.

  Le proprietà di dipendenza i cui valori possono provocare l'inizializzazione del sistema di layout sono contrassegnate con flag pubblici. <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>e <xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A> forniscono indicazioni utili per le modifiche dei valori di proprietà che forzano un aggiornamento ricorsivo da parte del sistema di layout. In generale, qualsiasi proprietà che può influire sulle dimensioni del rettangolo di delimitazione di un elemento deve avere un <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A> flag impostato su true. Per altre informazioni, vedere [Panoramica  sulle proprietà di dipendenza](dependency-properties-overview.md).

- Quando possibile, utilizzare un <xref:System.Windows.UIElement.RenderTransform%2A> anziché un <xref:System.Windows.FrameworkElement.LayoutTransform%2A> .

  Un oggetto <xref:System.Windows.FrameworkElement.LayoutTransform%2A> può essere un metodo molto utile per influenzare il contenuto di un oggetto [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] . Tuttavia, se l'effetto della trasformazione non ha alcun impatto sulla posizione di altri elementi, è preferibile usare <xref:System.Windows.UIElement.RenderTransform%2A> invece, perché non <xref:System.Windows.UIElement.RenderTransform%2A> richiama il sistema di layout. <xref:System.Windows.FrameworkElement.LayoutTransform%2A>applica la trasformazione e impone un aggiornamento ricorsivo del layout per tenere conto della nuova posizione dell'elemento interessato.

- Evitare chiamate non necessarie a <xref:System.Windows.UIElement.UpdateLayout%2A> .

  Il <xref:System.Windows.UIElement.UpdateLayout%2A> metodo impone un aggiornamento ricorsivo del layout e spesso non è necessario. Se non si ha la certezza della necessità di un aggiornamento completo, lasciare che sia il sistema di layout a chiamare automaticamente questo metodo.

- Quando si lavora con una raccolta di grandi dimensioni <xref:System.Windows.Controls.Panel.Children%2A> , è consigliabile usare un <xref:System.Windows.Controls.VirtualizingStackPanel> anziché un normale <xref:System.Windows.Controls.StackPanel> .

  Virtualizzando la raccolta figlio, il <xref:System.Windows.Controls.VirtualizingStackPanel> mantiene solo gli oggetti in memoria che sono attualmente all'interno del viewport del padre. Come conseguenza, le prestazioni risultano notevolmente migliorate nella maggior parte degli scenari.

<a name="LayoutSystem_LayoutRounding"></a>

## <a name="sub-pixel-rendering-and-layout-rounding"></a>Rendering dei sub-pixel e arrotondamento del layout

Il sistema grafico WPF USA unità indipendenti dal dispositivo per abilitare la risoluzione e l'indipendenza del dispositivo. Ogni Device Independent Pixel scala automaticamente con l'impostazione dpi (punti per pollice) del sistema. In questo modo, le applicazioni WPF vengono ridimensionate correttamente per diverse impostazioni dpi e l'applicazione è in grado di riconoscere automaticamente i dpi.

Questa indipendenza dpi può tuttavia creare un rendering perimetrale irregolare a causa dell'anti-aliasing. Questi elementi, osservabili in genere come bordi sfocati o semitrasparenti, possono essere presenti quando la posizione dei bordi si trova al centro di un pixel del dispositivo invece che tra pixel del dispositivo. Il sistema di layout permette di ovviare a questo problema con l'arrotondamento del layout. L'arrotondamento del layout avviene quando il sistema di layout arrotonda valori di pixel non integrali durante il passaggio di layout.

L'arrotondamento del layout è disabilitato per impostazione predefinita. Per abilitare l'arrotondamento del layout, impostare la <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> proprietà `true` su on Any <xref:System.Windows.FrameworkElement> . Poiché si tratta di una proprietà di dipendenza, il valore viene propagato a tutti gli elementi figlio nell'albero visuale. Per abilitare l'arrotondamento del layout per l'intera interfaccia utente, impostare <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> `true` su sul contenitore radice. Per un esempio, vedere <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A>.

<a name="LayoutSystem_whatsnext"></a>

## <a name="whats-next"></a>Passaggi successivi

La capacità di identificare il modo in cui gli elementi vengono misurati e disposti è il primo passaggio per la comprensione del layout. Per ulteriori informazioni sugli elementi disponibili <xref:System.Windows.Controls.Panel> , vedere [Cenni preliminari sui pannelli](../controls/panels-overview.md). Per meglio determinare le diverse proprietà di posizionamento che possono influire sul layout, vedere [Panoramica su allineamento, margini e spaziatura interna](alignment-margins-and-padding-overview.md). Quando si è pronti per riunire tutti i documenti in un'applicazione leggera, vedere [procedura dettagliata: applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.UIElement>
- [Cenni preliminari sugli elementi Panel](../controls/panels-overview.md)
- [Panoramica su allineamento, margini e spaziatura interna](alignment-margins-and-padding-overview.md)
- [Layout e progettazione](optimizing-performance-layout-and-design.md)
