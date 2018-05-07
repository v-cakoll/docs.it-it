---
title: 'Ottimizzazione delle prestazioni: layout e progettazione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- layout [WPF], optimizing performance
- design considerations [WPF]
- layout pass [WPF]
ms.assetid: 005f4cda-a849-448b-916b-38d14d9a96fe
ms.openlocfilehash: 9c9921e664d69038480e73ee6779ca9e48b81c7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="optimizing-performance-layout-and-design"></a>Ottimizzazione delle prestazioni: layout e progettazione
La progettazione dell'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] può influire sulle relative prestazioni, poiché crea un sovraccarico non necessario durante il calcolo del layout e la convalida dei riferimenti agli oggetti. La costruzione di oggetti, soprattutto in fase di runtime, può influire sulle caratteristiche di prestazioni dell'applicazione.  
  
 Questo argomento offre utili suggerimenti per il miglioramento delle prestazioni in queste aree.  
  
## <a name="layout"></a>Layout  
 Il termine "passaggio di layout" descrive il processo di misurazione e disposizione dei membri di un <xref:System.Windows.Controls.Panel>-insieme di elementi figlio e di disegno sullo schermo dell'oggetto derivato. Il passaggio di layout è un processo molto complesso dal punto di vista matematico: più alto è il numero di elementi figlio presenti nella raccolta, maggiore è il numero di calcoli necessari. Ad esempio, ogni volta che un elemento figlio <xref:System.Windows.UIElement> le modifiche alla posizione dell'oggetto nella raccolta, ha la possibilità di eseguire un nuovo passaggio dal sistema di layout. Data la stretta correlazione tra le caratteristiche dell'oggetto e il comportamento del layout, è importante capire i tipi di eventi che possono richiamare il sistema di layout. Le prestazioni dell'applicazione risulteranno migliori se si riuscirà a ridurre al massimo le chiamate non necessarie al passaggio di layout.  
  
 Per ogni membro figlio di una raccolta vengono completati due passaggi: un passaggio di misurazione e uno di disposizione. Ogni oggetto figlio fornisce la propria implementazione sottoposta a override del <xref:System.Windows.UIElement.Measure%2A> e <xref:System.Windows.UIElement.Arrange%2A> metodi per fornire il proprio comportamento in layout specifici. Nella forma più semplice, il layout è un sistema ricorsivo che fa sì che un elemento venga ridimensionato, posizionato e disegnato sullo schermo.  
  
-   Un elemento figlio <xref:System.Windows.UIElement> oggetto inizia il processo di layout con la misurazione delle relative proprietà core.  
  
-   L'oggetto <xref:System.Windows.FrameworkElement> le proprietà correlate alle dimensioni, ad esempio <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Height%2A>, e <xref:System.Windows.FrameworkElement.Margin%2A>, vengono valutati.  
  
-   <xref:System.Windows.Controls.Panel>-viene applicata la logica specifica, ad esempio il <xref:System.Windows.Controls.DockPanel.Dock%2A> proprietà del <xref:System.Windows.Controls.DockPanel>, o il <xref:System.Windows.Controls.StackPanel.Orientation%2A> proprietà del <xref:System.Windows.Controls.StackPanel>.  
  
-   Il contenuto viene disposto, o posizionato, dopo la misurazione di tutti gli oggetti figlio.  
  
-   La raccolta di oggetti figlio viene disegnata sullo schermo.  
  
 Il passaggio di layout viene nuovamente richiamato qualora si verifichi una delle azioni seguenti:  
  
-   Un oggetto figlio viene aggiunto alla raccolta.  
  
-   Oggetto <xref:System.Windows.FrameworkElement.LayoutTransform%2A> viene applicato all'oggetto figlio.  
  
-   Il <xref:System.Windows.UIElement.UpdateLayout%2A> metodo viene chiamato per l'oggetto figlio.  
  
-   Se viene apportata una modifica al valore di una proprietà di dipendenza contrassegnata con metadati che incidono sul passaggio di misurazione o disposizione.  
  
### <a name="use-the-most-efficient-panel-where-possible"></a>Usare il pannello più efficiente, se possibile  
 La complessità del processo di layout è basata direttamente sul comportamento di layout di <xref:System.Windows.Controls.Panel>-utilizzare elementi derivati. Ad esempio, un <xref:System.Windows.Controls.Grid> o <xref:System.Windows.Controls.StackPanel> controllo fornisce molte più funzionalità rispetto a un <xref:System.Windows.Controls.Canvas> controllo. All'aumento delle funzionalità corrisponde, tuttavia, un maggiore dispendio in termini di prestazioni. Tuttavia, se la funzionalità non è necessario che un <xref:System.Windows.Controls.Grid> fornisce controllo, utilizzare le alternative meno costose, ad esempio un <xref:System.Windows.Controls.Canvas> o un riquadro personalizzato.  
  
 Per altre informazioni, vedere [Cenni preliminari sugli elementi Panel](../../../../docs/framework/wpf/controls/panels-overview.md).  
  
### <a name="update-rather-than-replace-a-rendertransform"></a>Aggiornare anziché sostituire una proprietà RenderTransform  
 Potrebbe essere in grado di aggiornare un <xref:System.Windows.Media.Transform> anziché sostituirlo come valore di un <xref:System.Windows.UIElement.RenderTransform%2A> proprietà. Questa possibilità può essere attuata soprattutto negli scenari con animazioni. Aggiornando esistente <xref:System.Windows.Media.Transform>, evitare di avviare un calcolo di layout non necessari.  
  
### <a name="build-your-tree-top-down"></a>Compilare la struttura ad albero dall'alto in basso  
 Quando si aggiunge o si rimuove un nodo dall'albero logico, le convalide di proprietà vengono annullate sull'elemento padre e su tutti gli elementi figlio del nodo. Di conseguenza, è sempre consigliabile seguire un pattern di costruzione dall'alto in basso per evitare il costo di annullamenti di convalide non necessari su nodi già convalidati. Nella tabella seguente viene illustrata la differenza tra la creazione di una struttura di alto in basso o dal basso in alto, in cui la struttura ad albero è 150 livelli con una singola, la velocità di esecuzione <xref:System.Windows.Controls.TextBlock> e <xref:System.Windows.Controls.DockPanel> a ogni livello.  
  
|**Azione**|**Compilazione della struttura ad albero (in ms)**|**Rendering: include la compilazione della struttura ad albero (in ms)**|  
|----------------|---------------------------------|-------------------------------------------------|  
|Dal basso in alto|366|454|  
|Dall'alto in basso|11|96|  
  
 L'esempio di codice seguente illustra come creare una struttura ad albero dall'alto in basso.  
  
 [!code-csharp[Performance#PerformanceSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet1)]
 [!code-vb[Performance#PerformanceSnippet1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet1)]  
  
 Per altre informazioni sull'albero logico, vedere [Strutture ad albero in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Ottimizzazione delle prestazioni di applicazioni WPF](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [Pianificazione delle prestazioni dell'applicazione](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [Sfruttare appieno l'hardware](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [Grafica bidimensionale e creazione di immagini](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [Comportamento dell'oggetto](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [Risorse di applicazioni](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [per](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [Data binding](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [Altri suggerimenti relativi alle prestazioni](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)  
 [Layout](../../../../docs/framework/wpf/advanced/layout.md)
