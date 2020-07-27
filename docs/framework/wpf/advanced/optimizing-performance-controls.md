---
title: Ottimizzare le prestazioni del controllo
description: Windows Presentation Foundation include molti componenti comuni utilizzati nella maggior parte delle applicazioni Windows. Informazioni su come migliorare le prestazioni dell'interfaccia utente.
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], improving performance
- container recycling [WPF]
- user interface virtualization [WPF]
ms.assetid: 45a31c43-ea8a-4546-96c8-0631b9934179
ms.openlocfilehash: de348dd93e5710b5b81af035ec7aa56e01dc4981
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168300"
---
# <a name="optimizing-performance-controls"></a>Ottimizzazione delle prestazioni: controlli

Windows Presentation Foundation (WPF) include molti componenti dell'interfaccia utente comuni utilizzati nella maggior parte delle applicazioni Windows. Questo argomento illustra le tecniche da adottare per migliorare le prestazioni dell'interfaccia utente.

## <a name="displaying-large-data-sets"></a>Visualizzazione di set di dati di grandi dimensioni

I controlli WPF, ad esempio <xref:System.Windows.Controls.ListView> e, <xref:System.Windows.Controls.ComboBox> vengono utilizzati per visualizzare elenchi di elementi in un'applicazione. Se l'elenco da visualizzare è molto lungo, le prestazioni dell'applicazione possono risentirne. Questo perché il sistema di layout standard crea un contenitore di layout per ogni elemento associato al controllo elenco e ne calcola le dimensioni di layout e la posizione. In genere, non è necessario visualizzare tutti gli elementi contemporaneamente, ma ne viene visualizzato un sottoinsieme e l'utente scorre l'elenco. In questo caso è utile usare la *virtualizzazione* dell'interfaccia utente, ovvero la generazione del contenitore dell'elemento e il calcolo del layout associato sono rinviati al momento in cui l'elemento risulta visibile.

La virtualizzazione dell'interfaccia utente è un aspetto importante dei controlli elenco e non deve essere confusa con la virtualizzazione dei dati. Con la virtualizzazione dell'interfaccia utente vengono archiviati in memoria solo gli elementi visibili, mentre in uno scenario di associazione dati viene archiviata in memoria l'intera struttura dei dati. Con la virtualizzazione dei dati, al contrario, vengono archiviati in memoria solo gli elementi dati visibili sullo schermo.

Per impostazione predefinita, la virtualizzazione dell'interfaccia utente è abilitata per i <xref:System.Windows.Controls.ListView> <xref:System.Windows.Controls.ListBox> controlli e quando i relativi elementi elenco sono associati ai dati. <xref:System.Windows.Controls.TreeView>la virtualizzazione può essere abilitata impostando la <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A?displayProperty=nameWithType> proprietà associata su `true` . Se si vuole abilitare la virtualizzazione dell'interfaccia utente per i controlli personalizzati che derivano da <xref:System.Windows.Controls.ItemsControl> o controlli elemento esistenti che usano la <xref:System.Windows.Controls.StackPanel> classe, ad esempio <xref:System.Windows.Controls.ComboBox> , è possibile impostare <xref:System.Windows.Controls.ItemsControl.ItemsPanel%2A> su <xref:System.Windows.Controls.VirtualizingStackPanel> e impostare <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizing%2A> su `true` . Purtroppo è possibile che la virtualizzazione dell'interfaccia utente venga inavvertitamente disabilitata per questi controlli. Di seguito sono elencate le condizioni che disabilitano la virtualizzazione dell'interfaccia utente.

- I contenitori di elementi vengono aggiunti direttamente a <xref:System.Windows.Controls.ItemsControl> . Se, ad esempio, un'applicazione aggiunge in modo esplicito <xref:System.Windows.Controls.ListBoxItem> oggetti a un oggetto <xref:System.Windows.Controls.ListBox> , <xref:System.Windows.Controls.ListBox> non virtualizza gli <xref:System.Windows.Controls.ListBoxItem> oggetti.

- I contenitori di elementi in <xref:System.Windows.Controls.ItemsControl> sono di tipi diversi. Ad esempio, un oggetto <xref:System.Windows.Controls.Menu> che usa <xref:System.Windows.Controls.Separator> gli oggetti non può implementare il riciclo degli elementi perché <xref:System.Windows.Controls.Menu> contiene oggetti di tipo <xref:System.Windows.Controls.Separator> e <xref:System.Windows.Controls.MenuItem> .

- Impostazione <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> su `false` .

- Impostazione <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A> su `false` .

Un aspetto importante di cui tener conto quando si virtualizzano contenitori di elementi è la disponibilità di informazioni aggiuntive sullo stato associate a un contenitore di elementi appartenente all'elemento. Nel caso in cui queste informazioni siano disponibili, è necessario salvare lo stato aggiuntivo. Ad esempio, è possibile che sia presente un elemento contenuto in un <xref:System.Windows.Controls.Expander> controllo e che lo <xref:System.Windows.Controls.Expander.IsExpanded%2A> stato sia associato al contenitore dell'elemento e non all'elemento stesso. Quando il contenitore viene riutilizzato per un nuovo elemento, viene utilizzato il valore corrente di <xref:System.Windows.Controls.Expander.IsExpanded%2A> per il nuovo elemento. Inoltre, l'elemento precedente perde il valore corretto <xref:System.Windows.Controls.Expander.IsExpanded%2A> .

Attualmente nessun controllo WPF offre il supporto incorporato per la virtualizzazione dei dati.

## <a name="container-recycling"></a>Riciclo del contenitore

Un'ottimizzazione per la virtualizzazione dell'interfaccia utente aggiunta in .NET Framework 3,5 SP1 per i controlli che ereditano da <xref:System.Windows.Controls.ItemsControl> è il *riciclo del contenitore,* che può anche migliorare le prestazioni di scorrimento. Quando un oggetto <xref:System.Windows.Controls.ItemsControl> che usa la virtualizzazione dell'interfaccia utente viene popolato, crea un contenitore di elementi per ogni elemento che scorre nella visualizzazione ed Elimina il contenitore di elementi per ogni elemento che scorre fuori dalla visualizzazione. Il *riciclo del contenitore* consente al controllo di riutilizzare i contenitori di elementi esistenti per elementi di dati diversi, in modo che i contenitori di elementi non vengano creati ed eliminati continuamente quando l'utente scorre <xref:System.Windows.Controls.ItemsControl> . È possibile scegliere di abilitare il riciclo degli elementi impostando la <xref:System.Windows.Controls.VirtualizingPanel.VirtualizationMode%2A> proprietà associata su <xref:System.Windows.Controls.VirtualizationMode.Recycling> .

Qualsiasi <xref:System.Windows.Controls.ItemsControl> che supporta la virtualizzazione può usare il riciclo dei contenitori. Per un esempio di come abilitare il riciclo del contenitore in un <xref:System.Windows.Controls.ListBox> , vedere [migliorare le prestazioni di scorrimento di un controllo ListBox](../controls/how-to-improve-the-scrolling-performance-of-a-listbox.md).

## <a name="supporting-bidirectional-virtualization"></a>Supporto della virtualizzazione bidirezionale

<xref:System.Windows.Controls.VirtualizingStackPanel>offre supporto incorporato per la virtualizzazione dell'interfaccia utente in una direzione, orizzontalmente o verticalmente. Se si vuole usare la virtualizzazione bidirezionale per i controlli, è necessario implementare un pannello personalizzato che estende la <xref:System.Windows.Controls.VirtualizingStackPanel> classe. La <xref:System.Windows.Controls.VirtualizingStackPanel> classe espone metodi virtuali come <xref:System.Windows.Controls.VirtualizingStackPanel.OnViewportSizeChanged%2A> ,, <xref:System.Windows.Controls.VirtualizingStackPanel.LineUp%2A> <xref:System.Windows.Controls.VirtualizingStackPanel.PageUp%2A> e <xref:System.Windows.Controls.VirtualizingStackPanel.MouseWheelUp%2A> . Questi metodi virtuali consentono di rilevare una modifica nella parte visibile di un elenco e di gestirla di conseguenza.

## <a name="optimizing-templates"></a>Ottimizzazione di modelli

La struttura ad albero visuale contiene tutti gli elementi visivi di un'applicazione. Oltre agli oggetti creati direttamente, contiene anche oggetti generati dall'espansione del modello. Ad esempio, quando si crea un oggetto <xref:System.Windows.Controls.Button> , si ottengono <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> anche <xref:System.Windows.Controls.ContentPresenter> gli oggetti e nella struttura ad albero visuale. Se non si è provveduto a ottimizzare i modelli di controllo, quindi, è possibile che si creino molti oggetti in più non necessari nella struttura ad albero visuale. Per altre informazioni sulla struttura ad albero visuale, vedere [Cenni preliminari sul rendering della grafica WPF](../graphics-multimedia/wpf-graphics-rendering-overview.md).

## <a name="deferred-scrolling"></a>Scorrimento posticipato

Per impostazione predefinita, quando l'utente trascina il cursore su una barra di scorrimento, la visualizzazione del contenuto viene continuamente aggiornata. Se lo scorrimento è lento nel controllo, valutare la possibilità di usare lo scorrimento posticipato, in cui il contenuto viene aggiornato solo quando l'utente rilascia il cursore.

Per implementare lo scorrimento posticipato, impostare la <xref:System.Windows.Controls.ScrollViewer.IsDeferredScrollingEnabled%2A> proprietà su `true` . <xref:System.Windows.Controls.ScrollViewer.IsDeferredScrollingEnabled%2A>è una proprietà associata e può essere impostata su <xref:System.Windows.Controls.ScrollViewer> e su qualsiasi controllo che dispone <xref:System.Windows.Controls.ScrollViewer> di un oggetto nel relativo modello di controllo.

## <a name="controls-that-implement-performance-features"></a>Controlli che implementano le funzionalità delle prestazioni

La tabella seguente elenca i controlli comuni per la visualizzazione dei dati e ne indica il tipo di supporto per le funzionalità relative alle prestazioni. Vedere le sezioni precedenti per informazioni su come abilitare queste funzionalità.

|Controllo|Virtualizzazione|Riciclo del contenitore|Scorrimento posticipato|
|-------------|--------------------|-------------------------|------------------------|
|<xref:System.Windows.Controls.ComboBox>|Può essere abilitato|Può essere abilitato|Può essere abilitato|
|<xref:System.Windows.Controls.ContextMenu>|Può essere abilitato|Può essere abilitato|Può essere abilitato|
|<xref:System.Windows.Controls.DocumentViewer>|Non disponibile|Non disponibile|Può essere abilitato|
|<xref:System.Windows.Controls.ListBox>|Predefinito|Può essere abilitato|Può essere abilitato|
|<xref:System.Windows.Controls.ListView>|Predefinito|Può essere abilitato|Può essere abilitato|
|<xref:System.Windows.Controls.TreeView>|Può essere abilitato|Può essere abilitato|Può essere abilitato|
|<xref:System.Windows.Controls.ToolBar>|Non disponibile|Non disponibile|Può essere abilitato|

> [!NOTE]
> Per un esempio di come abilitare la virtualizzazione e il riciclo del contenitore in un <xref:System.Windows.Controls.TreeView> , vedere [migliorare le prestazioni di un controllo TreeView](../controls/how-to-improve-the-performance-of-a-treeview.md).

## <a name="see-also"></a>Vedere anche

- [Layout](layout.md)
- [Layout e progettazione](optimizing-performance-layout-and-design.md)
- [Data Binding](optimizing-performance-data-binding.md)
- [Controlli](../controls/index.md)
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Procedura dettagliata: Memorizzazione dei dati di un'applicazione nella cache di un'applicazione WPF](walkthrough-caching-application-data-in-a-wpf-application.md)
