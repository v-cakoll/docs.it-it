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
ms.openlocfilehash: 2ff0f134ea3174f7f034d47446aab782e2141916
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186979"
---
# <a name="scrollviewer-overview"></a>Cenni preliminari sull'elemento ScrollViewer
Il contenuto all'interno di un'interfaccia utente è spesso di dimensioni maggiori dell'area di visualizzazione dello schermo di un computer. Il <xref:System.Windows.Controls.ScrollViewer> controllo fornisce un modo pratico [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] per abilitare lo scorrimento del contenuto nelle applicazioni. In questo argomento <xref:System.Windows.Controls.ScrollViewer> viene presentato l'elemento e vengono forniti diversi esempi di utilizzo.  
  
<a name="what_is_a_scrollviewer_element"></a>
## <a name="the-scrollviewer-control"></a>Controllo ScrollViewer  
 Esistono due elementi predefiniti che consentono [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] lo <xref:System.Windows.Controls.Primitives.ScrollBar> <xref:System.Windows.Controls.ScrollViewer>scorrimento nelle applicazioni: e . Il <xref:System.Windows.Controls.ScrollViewer> controllo incapsula <xref:System.Windows.Controls.Primitives.ScrollBar> gli elementi orizzontali e <xref:System.Windows.Controls.Panel> verticali e un contenitore di contenuto (ad esempio un elemento) per visualizzare altri elementi visibili in un'area scorrevole. È necessario compilare un oggetto <xref:System.Windows.Controls.Primitives.ScrollBar> personalizzato per utilizzare l'elemento per lo scorrimento del contenuto. Tuttavia, è <xref:System.Windows.Controls.ScrollViewer> possibile utilizzare l'elemento da solo <xref:System.Windows.Controls.Primitives.ScrollBar> perché è un controllo composito che incapsula la funzionalità.  
  
 Il <xref:System.Windows.Controls.ScrollViewer> controllo risponde ai comandi del mouse e della tastiera e definisce numerosi metodi con cui scorrere il contenuto in base a incrementi predeterminati. È possibile <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> utilizzare l'evento per <xref:System.Windows.Controls.ScrollViewer> rilevare una modifica in uno stato.  
  
 Un <xref:System.Windows.Controls.ScrollViewer> può avere un solo <xref:System.Windows.Controls.Panel> elemento figlio, <xref:System.Windows.Controls.Panel.Children%2A> in genere un elemento che può ospitare una raccolta di elementi. La <xref:System.Windows.Controls.ContentPresenter.Content%2A> proprietà definisce l'unico elemento figlio dell'oggetto <xref:System.Windows.Controls.ScrollViewer>.  
  
<a name="scrollviewer_physical_vs_logical"></a>
## <a name="physical-vs-logical-scrolling"></a>Scorrimento fisico e logico  
 Si usa lo scorrimento fisico per scorrere il contenuto di un incremento fisico predeterminato, in genere un valore che viene dichiarato in pixel. Si usa lo scorrimento logico per passare all'elemento successivo nell'albero logico. Lo scorrimento fisico è il <xref:System.Windows.Controls.Panel> comportamento di scorrimento predefinito per la maggior parte degli elementi. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] supporta entrambi i tipi di scorrimento.  
  
#### <a name="the-iscrollinfo-interface"></a>Interfaccia IScrollInfo  
 L'interfaccia <xref:System.Windows.Controls.Primitives.IScrollInfo> rappresenta l'area <xref:System.Windows.Controls.ScrollViewer> di scorrimento principale all'interno di un controllo o derivato. L'interfaccia definisce le proprietà e i <xref:System.Windows.Controls.Panel> metodi di scorrimento che possono essere implementati da elementi che richiedono lo scorrimento in base all'unità logica, anziché in base a un incremento fisico. Il cast <xref:System.Windows.Controls.Primitives.IScrollInfo> di un'istanza di a un oggetto derivato <xref:System.Windows.Controls.Panel> e quindi l'utilizzo dei relativi metodi di scorrimento fornisce un modo utile per scorrere l'unità logica successiva in una raccolta figlio, anziché in base all'incremento dei pixel. Per impostazione <xref:System.Windows.Controls.ScrollViewer> predefinita, il controllo supporta lo scorrimento in base alle unità fisiche.  
  
 <xref:System.Windows.Controls.StackPanel>e <xref:System.Windows.Controls.VirtualizingStackPanel> sia <xref:System.Windows.Controls.Primitives.IScrollInfo> l'implementazione che lo scorrimento logico in modo nativo. Per i controlli di layout che supportano in modo nativo lo <xref:System.Windows.Controls.Panel> scorrimento <xref:System.Windows.Controls.ScrollViewer> logico, <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> è `false`comunque possibile ottenere lo scorrimento fisico eseguendo il wrapping dell'elemento host in a e impostando la proprietà su .  
  
 Nell'esempio di codice riportato <xref:System.Windows.Controls.Primitives.IScrollInfo> di <xref:System.Windows.Controls.StackPanel> seguito viene illustrato come<xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>eseguire il cast di un'istanza di in un oggetto e utilizzare i metodi di scorrimento del contenuto ( e ) definiti dall'interfaccia .  
  
 [!code-csharp[IScrollInfoMethods#3](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
<a name="scrollviewer_markup_syntax_and_sample"></a>
## <a name="defining-and-using-a-scrollviewer-element"></a>Definizione e uso di un elemento ScrollViewer  
 Nell'esempio seguente <xref:System.Windows.Controls.ScrollViewer> viene creata una finestra in una finestra che contiene del testo e un rettangolo. <xref:System.Windows.Controls.Primitives.ScrollBar>elementi vengono visualizzati solo quando sono necessari. Quando si ridimensiona la <xref:System.Windows.Controls.Primitives.ScrollBar> finestra, gli elementi vengono visualizzati e scompaiono, a causa dei valori aggiornati delle proprietà <xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A> e <xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A> .  
  
 [!code-cpp[ScrollViewer#1](~/samples/snippets/cpp/VS_Snippets_Wpf/ScrollViewer/CPP/ScrollViewer_wcp.cpp#1)]
 [!code-csharp[ScrollViewer#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewer/CSharp/ScrollViewer_wcp.cs#1)]
 [!code-vb[ScrollViewer#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewer/VisualBasic/ScrollViewer.vb#1)]
 [!code-xaml[ScrollViewer#1](~/samples/snippets/xaml/VS_Snippets_Wpf/ScrollViewer/XAML/Pane1.xaml#1)]  
  
<a name="scrollviewer_styling_scrollviewer"></a>
## <a name="styling-a-scrollviewer"></a>Applicazione di uno stile a un elemento ScrollViewer  
 Come tutti i controlli in <xref:System.Windows.Controls.ScrollViewer> Windows Presentation Foundation, è possibile applicare uno stile a uno stile per modificare il comportamento di rendering predefinito del controllo. Per altre informazioni sull'applicazione di stili di controllo, vedere [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md).  
  
<a name="scrollviewer_scroll_vs_paginate"></a>
## <a name="paginating-documents"></a>Paginazione di documenti  
 Per il contenuto del documento, un'alternativa alla visualizzazione a scorrimento consiste nello scegliere un contenitore di documenti che supporta l'impaginazione. <xref:System.Windows.Documents.FlowDocument>è per i documenti progettati per essere ospitati <xref:System.Windows.Controls.FlowDocumentPageViewer>all'interno di un controllo di visualizzazione, ad esempio , che supporta l'impaginazione del contenuto su più pagine, evitando la necessità di scorrimento. <xref:System.Windows.Controls.DocumentViewer>fornisce una soluzione <xref:System.Windows.Documents.FixedDocument> per la visualizzazione del contenuto, che utilizza lo scorrimento tradizionale per visualizzare il contenuto al di fuori dell'area di autenticazione dell'area di visualizzazione.  
  
 Per altre informazioni sui formati di documento e sulle opzioni di presentazione, vedere [Documenti in WPF](../advanced/documents-in-wpf.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.Primitives.ScrollBar>
- <xref:System.Windows.Controls.Primitives.IScrollInfo>
- [Procedura: creare un visualizzatore di scorrimentoHow to: Create a Scroll Viewer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752352(v=vs.90))
- [Documenti in WPF](../advanced/documents-in-wpf.md)
- [Stili e modelli di ScrollBar](scrollbar-styles-and-templates.md)
- [Controlli](../advanced/optimizing-performance-controls.md)
