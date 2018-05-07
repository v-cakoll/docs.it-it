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
ms.openlocfilehash: 1797f956ec41ba085dee7e1cb11a3129004552b1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="scrollviewer-overview"></a>Cenni preliminari sull'elemento ScrollViewer
Il contenuto all'interno di un'interfaccia utente è spesso di dimensioni maggiori dell'area di visualizzazione dello schermo di un computer. Il <xref:System.Windows.Controls.ScrollViewer> controllo fornisce un modo pratico per consentire lo scorrimento del contenuto in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] applicazioni. Questo argomento vengono presentate le <xref:System.Windows.Controls.ScrollViewer> elemento e fornisce alcuni esempi di utilizzo.  
  
<a name="what_is_a_scrollviewer_element"></a>   
## <a name="the-scrollviewer-control"></a>Controllo ScrollViewer  
 Sono presenti due elementi predefiniti che consentono lo scorrimento in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazioni: <xref:System.Windows.Controls.Primitives.ScrollBar> e <xref:System.Windows.Controls.ScrollViewer>. Il <xref:System.Windows.Controls.ScrollViewer> controllo incapsula impostazioni orizzontale e verticale <xref:System.Windows.Controls.Primitives.ScrollBar> elementi e un contenitore di contenuto (ad esempio un <xref:System.Windows.Controls.Panel> elemento) per visualizzare gli altri elementi visibili in un'area scorrevole. È necessario compilare un oggetto personalizzato per utilizzare il <xref:System.Windows.Controls.Primitives.ScrollBar> elemento per lo scorrimento del contenuto. Tuttavia, è possibile utilizzare il <xref:System.Windows.Controls.ScrollViewer> elemento autonomamente perché è un controllo composito che incapsula <xref:System.Windows.Controls.Primitives.ScrollBar> funzionalità.  
  
 Il <xref:System.Windows.Controls.ScrollViewer> risponde ai comandi di tastiera e mouse, controllo e definire numerosi metodi con cui scorrere il contenuto in base a incrementi predeterminati. È possibile utilizzare il <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> evento per rilevare una modifica in un <xref:System.Windows.Controls.ScrollViewer> stato.  
  
 Oggetto <xref:System.Windows.Controls.ScrollViewer> avere solo un elemento figlio, in genere un <xref:System.Windows.Controls.Panel> elemento che può contenere un <xref:System.Windows.Controls.Panel.Children%2A> raccolta di elementi. Il <xref:System.Windows.Controls.ContentPresenter.Content%2A> proprietà definisce l'unico elemento figlio del <xref:System.Windows.Controls.ScrollViewer>.  
  
<a name="scrollviewer_physical_vs_logical"></a>   
## <a name="physical-vs-logical-scrolling"></a>Differenza tra scorrimento fisico e scorrimento logico  
 Si usa lo scorrimento fisico per scorrere il contenuto di un incremento fisico predeterminato, in genere un valore che viene dichiarato in pixel. Si usa lo scorrimento logico per passare all'elemento successivo nell'albero logico. Lo scorrimento fisico è il comportamento predefinito per la maggior parte <xref:System.Windows.Controls.Panel> elementi. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] supporta entrambi i tipi di scorrimento.  
  
#### <a name="the-iscrollinfo-interface"></a>Interfaccia IScrollInfo  
 Il <xref:System.Windows.Controls.Primitives.IScrollInfo> interfaccia rappresenta la principale area di scorrimento all'interno di un <xref:System.Windows.Controls.ScrollViewer> o controllo derivato. L'interfaccia definisce le proprietà e metodi che possono essere implementati dalle scorrimento <xref:System.Windows.Controls.Panel> gli elementi che richiedono lo scorrimento di unità logica, anziché a un incremento fisico. Cast di un'istanza di <xref:System.Windows.Controls.Primitives.IScrollInfo> in un controllo derivato <xref:System.Windows.Controls.Panel> e quindi utilizzare i metodi di scorrimento fornisce un modo utile per lo scorrimento all'unità logica successiva in una raccolta figlio, anziché di incremento in pixel. Per impostazione predefinita, il <xref:System.Windows.Controls.ScrollViewer> controllo supporta lo scorrimento in base a unità fisiche.  
  
 <xref:System.Windows.Controls.StackPanel> e <xref:System.Windows.Controls.VirtualizingStackPanel> implementano entrambi <xref:System.Windows.Controls.Primitives.IScrollInfo> e in modo nativo supportano lo scorrimento logico. Per layout di controlli che supportano a livello nativo lo scorrimento logico, è comunque possibile ottenere lo scorrimento fisico eseguendo il wrapping dell'host <xref:System.Windows.Controls.Panel> elemento in un <xref:System.Windows.Controls.ScrollViewer> e impostando il <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> proprietà `false`.  
  
 Esempio di codice riportato di seguito viene illustrato come eseguire il cast di un'istanza di <xref:System.Windows.Controls.Primitives.IScrollInfo> per un <xref:System.Windows.Controls.StackPanel> e usare i metodi di scorrimento del contenuto (<xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> e <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>) definiti dall'interfaccia.  
  
 [!code-csharp[IScrollInfoMethods#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
<a name="scrollviewer_markup_syntax_and_sample"></a>   
## <a name="defining-and-using-a-scrollviewer-element"></a>Definizione e uso di un elemento ScrollViewer  
 Nell'esempio seguente viene creato un <xref:System.Windows.Controls.ScrollViewer> in una finestra che contiene testo e un rettangolo. <xref:System.Windows.Controls.Primitives.ScrollBar> gli elementi vengono visualizzati solo quando sono necessari. Quando si ridimensiona la finestra, il <xref:System.Windows.Controls.Primitives.ScrollBar> elementi vengono visualizzati e nascosti, a causa dei valori aggiornati del <xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A> e <xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A> proprietà.  
  
 [!code-cpp[ScrollViewer#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/ScrollViewer/CPP/ScrollViewer_wcp.cpp#1)]
 [!code-csharp[ScrollViewer#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewer/CSharp/ScrollViewer_wcp.cs#1)]
 [!code-vb[ScrollViewer#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewer/VisualBasic/ScrollViewer.vb#1)]
 [!code-xaml[ScrollViewer#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/ScrollViewer/XAML/Pane1.xaml#1)]  
  
<a name="scrollviewer_styling_scrollviewer"></a>   
## <a name="styling-a-scrollviewer"></a>Applicazione di uno stile a un elemento ScrollViewer  
 Come tutti i controlli Windows Presentation Foundation, il <xref:System.Windows.Controls.ScrollViewer> può essere applicato uno stile per modificare le impostazioni predefinite per il rendering del controllo. Per altre informazioni sull'applicazione di stili di controllo, vedere [Applicazione di stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
<a name="scrollviewer_scroll_vs_paginate"></a>   
## <a name="paginating-documents"></a>Paginazione di documenti  
 Per il contenuto del documento, un'alternativa alla visualizzazione a scorrimento consiste nello scegliere un contenitore di documenti che supporta l'impaginazione. <xref:System.Windows.Documents.FlowDocument> è per i documenti che sono progettati per essere ospitato all'interno di un controllo di visualizzazione, ad esempio <xref:System.Windows.Controls.FlowDocumentPageViewer>, che supporta l'impaginazione del contenuto tra più pagine, evitando la necessità di scorrimento. <xref:System.Windows.Controls.DocumentViewer> fornisce una soluzione per la visualizzazione <xref:System.Windows.Documents.FixedDocument> contenuto, che utilizza lo scorrimento tradizionale per visualizzare il contenuto all'esterno dell'area di visualizzazione.  
  
 Per altre informazioni sui formati di documento e sulle opzioni di presentazione, vedere [Documenti in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.ScrollViewer>  
 <xref:System.Windows.Controls.Primitives.ScrollBar>  
 <xref:System.Windows.Controls.Primitives.IScrollInfo>  
 [Creare un visualizzatore a scorrimento](http://msdn.microsoft.com/library/c8e46af7-b417-441b-aa30-791cbdbd43ef)  
 [Documenti in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Stili e modelli di ScrollBar](../../../../docs/framework/wpf/controls/scrollbar-styles-and-templates.md)  
 [Controlli](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
