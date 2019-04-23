---
title: Cenni preliminari sull'elemento ScrollViewer
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], ScrollViewer
- ScrollViewer control [WPF], about ScrollViewer control
ms.assetid: 94a13b94-cfdf-4b12-a1aa-90cb50c6e9b9
ms.openlocfilehash: a3302d9c360b0918a1fce956af3e3aa14f29361b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212427"
---
# <a name="scrollviewer-overview"></a>Cenni preliminari sull'elemento ScrollViewer
Il contenuto all'interno di un'interfaccia utente è spesso di dimensioni maggiori dell'area di visualizzazione dello schermo di un computer. Il <xref:System.Windows.Controls.ScrollViewer> controllo offre un modo pratico per abilitare lo scorrimento del contenuto in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] applicazioni. Questo argomento vengono presentate le <xref:System.Windows.Controls.ScrollViewer> elemento e fornisce diversi esempi di utilizzo.  
  
<a name="what_is_a_scrollviewer_element"></a>   
## <a name="the-scrollviewer-control"></a>Controllo ScrollViewer  
 Sono presenti due elementi predefiniti che consentono lo scorrimento nelle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le applicazioni: <xref:System.Windows.Controls.Primitives.ScrollBar> e <xref:System.Windows.Controls.ScrollViewer>. Il <xref:System.Windows.Controls.ScrollViewer> controllo incapsula orizzontale e verticale <xref:System.Windows.Controls.Primitives.ScrollBar> gli elementi e un contenitore di contenuto (ad esempio un <xref:System.Windows.Controls.Panel> elemento) per visualizzare altri elementi visibili nell'area di scorrevole. È necessario compilare un oggetto personalizzato per poter utilizzare il <xref:System.Windows.Controls.Primitives.ScrollBar> (elemento) per lo scorrimento di contenuto. Tuttavia, è possibile usare la <xref:System.Windows.Controls.ScrollViewer> elemento da solo perché è un controllo composito che incapsula <xref:System.Windows.Controls.Primitives.ScrollBar> funzionalità.  
  
 Il <xref:System.Windows.Controls.ScrollViewer> controllo risponde ai comandi del mouse e tastiera e definire numerosi metodi con cui scorrere il contenuto in base a incrementi predeterminati. È possibile usare la <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> eventi per rilevare una modifica in un <xref:System.Windows.Controls.ScrollViewer> dello stato.  
  
 Oggetto <xref:System.Windows.Controls.ScrollViewer> può avere in genere solo un elemento figlio, un' <xref:System.Windows.Controls.Panel> elemento che può contenere un <xref:System.Windows.Controls.Panel.Children%2A> raccolta di elementi. Il <xref:System.Windows.Controls.ContentPresenter.Content%2A> proprietà definisce l'unico elemento figlio di <xref:System.Windows.Controls.ScrollViewer>.  
  
<a name="scrollviewer_physical_vs_logical"></a>   
## <a name="physical-vs-logical-scrolling"></a>Differenza tra scorrimento fisico e scorrimento logico  
 Si usa lo scorrimento fisico per scorrere il contenuto di un incremento fisico predeterminato, in genere un valore che viene dichiarato in pixel. Si usa lo scorrimento logico per passare all'elemento successivo nell'albero logico. Lo scorrimento fisico rappresenta il comportamento predefinito per la maggior parte <xref:System.Windows.Controls.Panel> elementi. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] supporta entrambi i tipi di scorrimento.  
  
#### <a name="the-iscrollinfo-interface"></a>Interfaccia IScrollInfo  
 Il <xref:System.Windows.Controls.Primitives.IScrollInfo> interfaccia rappresenta l'area di scorrimento principale all'interno di un <xref:System.Windows.Controls.ScrollViewer> o controllo derivato. L'interfaccia definisce le proprietà e metodi che possono essere implementati dalle scorrimento <xref:System.Windows.Controls.Panel> gli elementi che richiedono lo scorrimento di unità logica, anziché a un incremento fisico. Esegue il cast di un'istanza di <xref:System.Windows.Controls.Primitives.IScrollInfo> in un controllo derivato <xref:System.Windows.Controls.Panel> e usando quindi i relativi metodi di scorrimento fornisce un modo utile per scorrere fino all'unità logica successiva in una raccolta figlio, anziché dall'incremento in pixel. Per impostazione predefinita, il <xref:System.Windows.Controls.ScrollViewer> controllo supporta lo scorrimento in base a unità fisiche.  
  
 <xref:System.Windows.Controls.StackPanel> e <xref:System.Windows.Controls.VirtualizingStackPanel> implementano entrambi <xref:System.Windows.Controls.Primitives.IScrollInfo> e in modo nativo supportano lo scorrimento logico. Per layout di controlli che supportano a livello nativo lo scorrimento logico, è comunque possibile ottenere lo scorrimento fisico eseguendo il wrapping dell'host <xref:System.Windows.Controls.Panel> elemento in un <xref:System.Windows.Controls.ScrollViewer> e impostando le <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> proprietà `false`.  
  
 Esempio di codice seguente viene illustrato come eseguire il cast di un'istanza di <xref:System.Windows.Controls.Primitives.IScrollInfo> a un <xref:System.Windows.Controls.StackPanel> e usare i metodi di scorrimento del contenuto (<xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> e <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>) definiti dall'interfaccia.  
  
 [!code-csharp[IScrollInfoMethods#3](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
<a name="scrollviewer_markup_syntax_and_sample"></a>   
## <a name="defining-and-using-a-scrollviewer-element"></a>Definizione e uso di un elemento ScrollViewer  
 L'esempio seguente crea un <xref:System.Windows.Controls.ScrollViewer> in una finestra che contiene testo e un rettangolo. <xref:System.Windows.Controls.Primitives.ScrollBar> gli elementi vengono visualizzati solo quando sono necessari. Quando si ridimensiona la finestra, il <xref:System.Windows.Controls.Primitives.ScrollBar> elementi visualizzati e nascosti a causa dei valori aggiornati delle <xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A> e <xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A> proprietà.  
  
 [!code-cpp[ScrollViewer#1](~/samples/snippets/cpp/VS_Snippets_Wpf/ScrollViewer/CPP/ScrollViewer_wcp.cpp#1)]
 [!code-csharp[ScrollViewer#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewer/CSharp/ScrollViewer_wcp.cs#1)]
 [!code-vb[ScrollViewer#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewer/VisualBasic/ScrollViewer.vb#1)]
 [!code-xaml[ScrollViewer#1](~/samples/snippets/xaml/VS_Snippets_Wpf/ScrollViewer/XAML/Pane1.xaml#1)]  
  
<a name="scrollviewer_styling_scrollviewer"></a>   
## <a name="styling-a-scrollviewer"></a>Applicazione di uno stile a un elemento ScrollViewer  
 Come tutti i controlli in Windows Presentation Foundation, il <xref:System.Windows.Controls.ScrollViewer> può essere applicato uno stile per modificare il comportamento di rendering predefinito del controllo. Per altre informazioni sull'applicazione di stili di controllo, vedere [Applicazione di stili e modelli](styling-and-templating.md).  
  
<a name="scrollviewer_scroll_vs_paginate"></a>   
## <a name="paginating-documents"></a>Paginazione di documenti  
 Per il contenuto del documento, un'alternativa alla visualizzazione a scorrimento consiste nello scegliere un contenitore di documenti che supporta l'impaginazione. <xref:System.Windows.Documents.FlowDocument> è per i documenti che sono progettati per essere ospitati all'interno di un controllo di visualizzazione, ad esempio <xref:System.Windows.Controls.FlowDocumentPageViewer>, che supporta l'impaginazione del contenuto tra più pagine, evitando la necessità di scorrimento. <xref:System.Windows.Controls.DocumentViewer> offre una soluzione per la visualizzazione <xref:System.Windows.Documents.FixedDocument> content, che usa lo scorrimento tradizionale per visualizzare contenuto all'esterno dell'area di visualizzazione.  
  
 Per altre informazioni sui formati di documento e sulle opzioni di presentazione, vedere [Documenti in WPF](../advanced/documents-in-wpf.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.Primitives.ScrollBar>
- <xref:System.Windows.Controls.Primitives.IScrollInfo>
- [Procedura: Creare un visualizzatore a scorrimento](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752352(v=vs.90))
- [Documenti in WPF](../advanced/documents-in-wpf.md)
- [Stili e modelli di ScrollBar](scrollbar-styles-and-templates.md)
- [Controlli](../advanced/optimizing-performance-controls.md)
