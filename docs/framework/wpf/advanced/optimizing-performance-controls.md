---
title: 'Ottimizzazione delle prestazioni: Controlli'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], improving performance
- container recycling [WPF]
- user interface virtualization [WPF]
ms.assetid: 45a31c43-ea8a-4546-96c8-0631b9934179
ms.openlocfilehash: 0917b1555f98fca9cf48cb7d208992848bd8e4b3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694633"
---
# <a name="optimizing-performance-controls"></a>Ottimizzazione delle prestazioni: Controlli
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] include molti dei componenti dell'interfaccia utente comuni alla maggior parte delle applicazioni Windows. Questo argomento illustra le tecniche da adottare per migliorare le prestazioni dell'interfaccia utente.  
  
 
  
<a name="Displaying"></a>   
## <a name="displaying-large-data-sets"></a>Visualizzazione di set di dati di grandi dimensioni  
 I controlli WPF, ad esempio la <xref:System.Windows.Controls.ListView> e <xref:System.Windows.Controls.ComboBox> vengono utilizzati per visualizzare elenchi di elementi in un'applicazione. Se l'elenco da visualizzare è molto lungo, le prestazioni dell'applicazione possono risentirne. Questo perché il sistema di layout standard crea un contenitore di layout per ogni elemento associato al controllo elenco e ne calcola le dimensioni di layout e la posizione. In genere, non è necessario visualizzare tutti gli elementi contemporaneamente, ma ne viene visualizzato un sottoinsieme e l'utente scorre l'elenco. In questo caso è utile usare la *virtualizzazione* dell'interfaccia utente, ovvero la generazione del contenitore dell'elemento e il calcolo del layout associato sono rinviati al momento in cui l'elemento risulta visibile.  
  
 La virtualizzazione dell'interfaccia utente è un aspetto importante dei controlli elenco e non deve essere confusa con la virtualizzazione dei dati. Con la virtualizzazione dell'interfaccia utente vengono archiviati in memoria solo gli elementi visibili, mentre in uno scenario di associazione dati viene archiviata in memoria l'intera struttura dei dati. Con la virtualizzazione dei dati, al contrario, vengono archiviati in memoria solo gli elementi dati visibili sullo schermo.  
  
 Virtualizzazione dell'interfaccia utente è abilitata per impostazione predefinita, il <xref:System.Windows.Controls.ListView> e <xref:System.Windows.Controls.ListBox> controlla quando gli elementi elenco associati a dati. <xref:System.Windows.Controls.TreeView> la virtualizzazione può essere abilitata impostando il <!--zz <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A?displayProperty=nameWithType> --> `IsVirtualizing` proprietà associata `true`. Se si desidera abilitare la virtualizzazione dell'interfaccia utente per i controlli personalizzati che derivano da <xref:System.Windows.Controls.ItemsControl> o controlli di elementi esistenti che usano i <xref:System.Windows.Controls.StackPanel> classe, ad esempio <xref:System.Windows.Controls.ComboBox>, è possibile impostare il <xref:System.Windows.Controls.ItemsControl.ItemsPanel%2A> al <xref:System.Windows.Controls.VirtualizingStackPanel> e impostare <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizing%2A> a `true`. Purtroppo è possibile che la virtualizzazione dell'interfaccia utente venga inavvertitamente disabilitata per questi controlli. Di seguito sono elencate le condizioni che disabilitano la virtualizzazione dell'interfaccia utente.  
  
-   I contenitori vengono aggiunti direttamente al <xref:System.Windows.Controls.ItemsControl>. Ad esempio, se un'applicazione aggiunge in modo esplicito <xref:System.Windows.Controls.ListBoxItem> oggetti in un <xref:System.Windows.Controls.ListBox>, il <xref:System.Windows.Controls.ListBox> non virtualizza il <xref:System.Windows.Controls.ListBoxItem> oggetti.  
  
-   Elemento dei contenitori nel <xref:System.Windows.Controls.ItemsControl> sono di tipo diverso. Ad esempio, un <xref:System.Windows.Controls.Menu> che usa <xref:System.Windows.Controls.Separator> gli oggetti non possono implementare il riciclo degli elementi in quanto il <xref:System.Windows.Controls.Menu> contiene oggetti di tipo <xref:System.Windows.Controls.Separator> e <xref:System.Windows.Controls.MenuItem>.  
  
-   L'impostazione <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> a `false`.  
  
-   L'impostazione <!--zz <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A>--> `IsVirtualizing` a `false`.    
  
 Un aspetto importante di cui tener conto quando si virtualizzano contenitori di elementi è la disponibilità di informazioni aggiuntive sullo stato associate a un contenitore di elementi appartenente all'elemento. Nel caso in cui queste informazioni siano disponibili, è necessario salvare lo stato aggiuntivo. Ad esempio, potrebbe essere un elemento contenuto un <xref:System.Windows.Controls.Expander> controllo e il <xref:System.Windows.Controls.Expander.IsExpanded%2A> lo stato è associato al contenitore dell'elemento e non all'elemento stesso. Quando il contenitore viene riusato per un nuovo elemento, il valore corrente di <xref:System.Windows.Controls.Expander.IsExpanded%2A> viene usato per il nuovo elemento. Inoltre, l'elemento precedente perde il corretto <xref:System.Windows.Controls.Expander.IsExpanded%2A> valore.  
  
 Attualmente nessun controllo WPF offre il supporto incorporato per la virtualizzazione dei dati.  
  
<a name="Container"></a>   
## <a name="container-recycling"></a>Riciclo del contenitore  
 Un'ottimizzazione della virtualizzazione dell'interfaccia utente aggiunta in .NET Framework 3.5 SP1 per i controlli che ereditano da <xref:System.Windows.Controls.ItemsControl> viene *riciclo del contenitore,* che può anche migliorare le prestazioni di scorrimento.  Quando un <xref:System.Windows.Controls.ItemsControl> che virtualizzazione dell'interfaccia utente Usa viene popolata, viene creato un contenitore di elementi per ogni elemento che scorre all'interno della visualizzazione viene distrutto il contenitore dell'elemento per ogni elemento che scompare dalla visualizzazione. *Riciclo del contenitore* consente di riusare i contenitori esistenti per gli elementi di dati diversi, in modo che i contenitori di elementi non continuamente creati e distrutti man mano che l'utente scorre il controllo di <xref:System.Windows.Controls.ItemsControl>. È possibile scegliere di abilitare elemento riciclo impostando il <xref:System.Windows.Controls.VirtualizingPanel.VirtualizationMode%2A> proprietà associata <xref:System.Windows.Controls.VirtualizationMode.Recycling>.  
  
 Qualsiasi <xref:System.Windows.Controls.ItemsControl> che supporta la virtualizzazione può utilizzare il riciclo del contenitore.  Per un esempio di come abilitare il riciclo del contenitore in un <xref:System.Windows.Controls.ListBox>, vedere [migliorare le prestazioni di scorrimento di un controllo ListBox](../../../../docs/framework/wpf/controls/how-to-improve-the-scrolling-performance-of-a-listbox.md).  
  
<a name="Supporting"></a>   
## <a name="supporting-bidirectional-virtualization"></a>Supporto della virtualizzazione bidirezionale  
 <xref:System.Windows.Controls.VirtualizingStackPanel> offre supporto predefinito per la virtualizzazione dell'interfaccia utente in una direzione, orizzontalmente o verticalmente. Se si desidera usare la virtualizzazione bidirezionale per i controlli, è necessario implementare un pannello personalizzato che estende il <xref:System.Windows.Controls.VirtualizingStackPanel> classe. Il <xref:System.Windows.Controls.VirtualizingStackPanel> classe espone i metodi virtuali, ad esempio <xref:System.Windows.Controls.VirtualizingStackPanel.OnViewportSizeChanged%2A>, <xref:System.Windows.Controls.VirtualizingStackPanel.LineUp%2A>, <xref:System.Windows.Controls.VirtualizingStackPanel.PageUp%2A>, e <xref:System.Windows.Controls.VirtualizingStackPanel.MouseWheelUp%2A>. Questi metodi virtuali consentono di rilevare una modifica nella parte visibile di un elenco e gestirle di conseguenza.  
  
<a name="Optimizing"></a>   
## <a name="optimizing-templates"></a>Ottimizzazione dei modelli  
 La struttura ad albero visuale contiene tutti gli elementi visivi di un'applicazione.  Oltre agli oggetti creati direttamente, contiene anche oggetti generati dall'espansione del modello.  Ad esempio, quando si crea una <xref:System.Windows.Controls.Button>, è anche possibile ottenere <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> e <xref:System.Windows.Controls.ContentPresenter> oggetti nell'albero visuale.  Se non si è provveduto a ottimizzare i modelli di controllo, quindi, è possibile che si creino molti oggetti in più non necessari nella struttura ad albero visuale.   Per altre informazioni sulla struttura ad albero visuale, vedere [Cenni preliminari sul rendering della grafica WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).  
  
<a name="Deferred"></a>   
## <a name="deferred-scrolling"></a>Scorrimento posticipato  
 Per impostazione predefinita, quando l'utente trascina il cursore su una barra di scorrimento, la visualizzazione del contenuto viene continuamente aggiornata.  Se lo scorrimento è lento nel controllo, valutare la possibilità di usare lo scorrimento posticipato,  in cui il contenuto viene aggiornato solo quando l'utente rilascia il cursore.  
  
 Per implementare lo scorrimento posticipato, impostare il <xref:System.Windows.Controls.ScrollViewer.IsDeferredScrollingEnabled%2A> proprietà `true`.  <xref:System.Windows.Controls.ScrollViewer.IsDeferredScrollingEnabled%2A> è una proprietà associata e può essere impostata su <xref:System.Windows.Controls.ScrollViewer> e qualsiasi controllo che ha un <xref:System.Windows.Controls.ScrollViewer> nel relativo modello di controllo.  
  
<a name="Controls"></a>   
## <a name="controls-that-implement-performance-features"></a>Controlli che implementano le funzioni relative alle prestazioni  
 La tabella seguente elenca i controlli comuni per la visualizzazione dei dati e ne indica il tipo di supporto per le funzionalità relative alle prestazioni.  Vedere le sezioni precedenti per informazioni su come abilitare queste funzionalità.  
  
|Control|Virtualizzazione|Riciclo del contenitore|Scorrimento posticipato|  
|-------------|--------------------|-------------------------|------------------------|  
|<xref:System.Windows.Controls.ComboBox>|Può essere abilitato|Può essere abilitato|Può essere abilitato|  
|<xref:System.Windows.Controls.ContextMenu>|Può essere abilitato|Può essere abilitato|Può essere abilitato|  
|<xref:System.Windows.Controls.DocumentViewer>|Non disponibile|Non disponibile|Può essere abilitato|  
|<xref:System.Windows.Controls.ListBox>|Impostazione predefinita|Può essere abilitato|Può essere abilitato|  
|<xref:System.Windows.Controls.ListView>|Impostazione predefinita|Può essere abilitato|Può essere abilitato|  
|<xref:System.Windows.Controls.TreeView>|Può essere abilitato|Può essere abilitato|Può essere abilitato|  
|<xref:System.Windows.Controls.ToolBar>|Non disponibile|Non disponibile|Può essere abilitato|  
  
> [!NOTE]
>  Per un esempio di come permettono una virtualizzazione e riciclo del contenitore in un <xref:System.Windows.Controls.TreeView>, vedere [migliorare le prestazioni di un controllo TreeView](../../../../docs/framework/wpf/controls/how-to-improve-the-performance-of-a-treeview.md).  
  
## <a name="see-also"></a>Vedere anche
- [Layout](../../../../docs/framework/wpf/advanced/layout.md)
- [Ottimizzazione delle prestazioni: layout e progettazione](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)
- [Data binding](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)
- [Controlli](../../../../docs/framework/wpf/controls/index.md)
- [Applicazione di stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [Procedura dettagliata: La memorizzazione nella cache i dati dell'applicazione in un'applicazione WPF](../../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)
