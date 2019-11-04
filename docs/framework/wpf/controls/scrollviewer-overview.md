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
ms.openlocfilehash: 993f3c861cbead88df3503eb01f18e5d1f69e2d8
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458431"
---
# <a name="scrollviewer-overview"></a>Cenni preliminari sull'elemento ScrollViewer
Il contenuto all'interno di un'interfaccia utente è spesso di dimensioni maggiori dell'area di visualizzazione dello schermo di un computer. Il controllo <xref:System.Windows.Controls.ScrollViewer> offre un modo pratico per consentire lo scorrimento del contenuto nelle applicazioni [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Questo argomento introduce l'elemento <xref:System.Windows.Controls.ScrollViewer> e fornisce diversi esempi di utilizzo.  
  
<a name="what_is_a_scrollviewer_element"></a>   
## <a name="the-scrollviewer-control"></a>Controllo ScrollViewer  
 Sono disponibili due elementi predefiniti che consentono lo scorrimento nelle applicazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: <xref:System.Windows.Controls.Primitives.ScrollBar> e <xref:System.Windows.Controls.ScrollViewer>. Il controllo <xref:System.Windows.Controls.ScrollViewer> incapsula gli elementi <xref:System.Windows.Controls.Primitives.ScrollBar> orizzontali e verticali e un contenitore di contenuto (ad esempio un elemento <xref:System.Windows.Controls.Panel>) per visualizzare altri elementi visibili in un'area scorrevole. Per poter usare l'elemento <xref:System.Windows.Controls.Primitives.ScrollBar> per lo scorrimento del contenuto, è necessario compilare un oggetto personalizzato. Tuttavia, è possibile utilizzare l'elemento <xref:System.Windows.Controls.ScrollViewer> da solo perché si tratta di un controllo composito che incapsula <xref:System.Windows.Controls.Primitives.ScrollBar> funzionalità.  
  
 Il controllo <xref:System.Windows.Controls.ScrollViewer> risponde ai comandi del mouse e della tastiera e definisce diversi metodi con cui scorrere il contenuto in base a incrementi predeterminati. È possibile utilizzare l'evento <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> per rilevare una modifica in uno stato di <xref:System.Windows.Controls.ScrollViewer>.  
  
 Un <xref:System.Windows.Controls.ScrollViewer> può avere un solo elemento figlio, in genere un elemento <xref:System.Windows.Controls.Panel> che può ospitare una raccolta di <xref:System.Windows.Controls.Panel.Children%2A> di elementi. La proprietà <xref:System.Windows.Controls.ContentPresenter.Content%2A> definisce l'unico elemento figlio del <xref:System.Windows.Controls.ScrollViewer>.  
  
<a name="scrollviewer_physical_vs_logical"></a>   
## <a name="physical-vs-logical-scrolling"></a>Scorrimento fisico rispetto a scorrimento logico  
 Si usa lo scorrimento fisico per scorrere il contenuto di un incremento fisico predeterminato, in genere un valore che viene dichiarato in pixel. Si usa lo scorrimento logico per passare all'elemento successivo nell'albero logico. Lo scorrimento fisico è il comportamento di scorrimento predefinito per la maggior parte degli elementi <xref:System.Windows.Controls.Panel>. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] supporta entrambi i tipi di scorrimento.  
  
#### <a name="the-iscrollinfo-interface"></a>Interfaccia IScrollInfo  
 L'interfaccia <xref:System.Windows.Controls.Primitives.IScrollInfo> rappresenta l'area di scorrimento principale all'interno di un <xref:System.Windows.Controls.ScrollViewer> o di un controllo derivato. L'interfaccia definisce le proprietà e i metodi di scorrimento che possono essere implementati da <xref:System.Windows.Controls.Panel> elementi che richiedono lo scorrimento in base a un'unità logica, anziché a un incremento fisico. Il cast di un'istanza di <xref:System.Windows.Controls.Primitives.IScrollInfo> a una <xref:System.Windows.Controls.Panel> derivata e quindi l'uso dei metodi di scorrimento fornisce un modo utile per scorrere fino all'unità logica successiva in una raccolta figlio, anziché in base all'incremento del pixel. Per impostazione predefinita, il controllo <xref:System.Windows.Controls.ScrollViewer> supporta lo scorrimento in base alle unità fisiche.  
  
 <xref:System.Windows.Controls.StackPanel> e <xref:System.Windows.Controls.VirtualizingStackPanel> implementano sia <xref:System.Windows.Controls.Primitives.IScrollInfo> che supportano in modo nativo lo scorrimento logico. Per i controlli di layout che supportano a livello nativo lo scorrimento logico, è comunque possibile ottenere lo scorrimento fisico eseguendo il wrapping dell'elemento <xref:System.Windows.Controls.Panel> host in un <xref:System.Windows.Controls.ScrollViewer> e impostando la proprietà <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> su `false`.  
  
 Nell'esempio di codice riportato di seguito viene illustrato come eseguire il cast di un'istanza di <xref:System.Windows.Controls.Primitives.IScrollInfo> a un <xref:System.Windows.Controls.StackPanel> e utilizzare i metodi di scorrimento del contenuto (<xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> e <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>) definiti dall'interfaccia.  
  
 [!code-csharp[IScrollInfoMethods#3](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
<a name="scrollviewer_markup_syntax_and_sample"></a>   
## <a name="defining-and-using-a-scrollviewer-element"></a>Definizione e uso di un elemento ScrollViewer  
 Nell'esempio seguente viene creato un <xref:System.Windows.Controls.ScrollViewer> in una finestra contenente testo e un rettangolo. gli elementi <xref:System.Windows.Controls.Primitives.ScrollBar> vengono visualizzati solo quando sono necessari. Quando si ridimensiona la finestra, gli elementi <xref:System.Windows.Controls.Primitives.ScrollBar> appaiono e scompaiono, a causa dei valori aggiornati delle proprietà <xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A> e <xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A>.  
  
 [!code-cpp[ScrollViewer#1](~/samples/snippets/cpp/VS_Snippets_Wpf/ScrollViewer/CPP/ScrollViewer_wcp.cpp#1)]
 [!code-csharp[ScrollViewer#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewer/CSharp/ScrollViewer_wcp.cs#1)]
 [!code-vb[ScrollViewer#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewer/VisualBasic/ScrollViewer.vb#1)]
 [!code-xaml[ScrollViewer#1](~/samples/snippets/xaml/VS_Snippets_Wpf/ScrollViewer/XAML/Pane1.xaml#1)]  
  
<a name="scrollviewer_styling_scrollviewer"></a>   
## <a name="styling-a-scrollviewer"></a>Applicazione di uno stile a un elemento ScrollViewer  
 Come tutti i controlli in Windows Presentation Foundation, è possibile applicare uno stile al <xref:System.Windows.Controls.ScrollViewer> per modificare il comportamento di rendering predefinito del controllo. Per altre informazioni sull'applicazione di stili di controllo, vedere [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md).  
  
<a name="scrollviewer_scroll_vs_paginate"></a>   
## <a name="paginating-documents"></a>Paginazione di documenti  
 Per il contenuto del documento, un'alternativa alla visualizzazione a scorrimento consiste nello scegliere un contenitore di documenti che supporta l'impaginazione. <xref:System.Windows.Documents.FlowDocument> riguarda i documenti progettati per essere ospitati all'interno di un controllo di visualizzazione, ad esempio <xref:System.Windows.Controls.FlowDocumentPageViewer>, che supporta il contenuto paginazione in più pagine, evitando la necessità di scorrimento. <xref:System.Windows.Controls.DocumentViewer> fornisce una soluzione per la visualizzazione del contenuto <xref:System.Windows.Documents.FixedDocument>, che utilizza lo scorrimento tradizionale per visualizzare il contenuto all'esterno dell'area di visualizzazione.  
  
 Per altre informazioni sui formati di documento e sulle opzioni di presentazione, vedere [Documenti in WPF](../advanced/documents-in-wpf.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.Primitives.ScrollBar>
- <xref:System.Windows.Controls.Primitives.IScrollInfo>
- [Procedura: creare un visualizzatore di scorrimento](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752352(v=vs.90))
- [Documenti in WPF](../advanced/documents-in-wpf.md)
- [Stili e modelli di ScrollBar](scrollbar-styles-and-templates.md)
- [Controlli](../advanced/optimizing-performance-controls.md)
