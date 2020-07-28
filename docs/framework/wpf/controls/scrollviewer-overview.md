---
title: Cenni preliminari sull'elemento ScrollViewer
description: Informazioni sul controllo ScrollViewer, che consente lo scorrimento del contenuto nelle applicazioni Windows Presentation Foundation. Vedere esempi di utilizzo.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], ScrollViewer
- ScrollViewer control [WPF], about ScrollViewer control
ms.assetid: 94a13b94-cfdf-4b12-a1aa-90cb50c6e9b9
ms.openlocfilehash: 1ef680bb004315a2b523814714d5533535d044e5
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164644"
---
# <a name="scrollviewer-overview"></a>Cenni preliminari sull'elemento ScrollViewer
Il contenuto all'interno di un'interfaccia utente è spesso di dimensioni maggiori dell'area di visualizzazione dello schermo di un computer. Il <xref:System.Windows.Controls.ScrollViewer> controllo rappresenta un metodo pratico per consentire lo scorrimento del contenuto nelle [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] applicazioni. Questo argomento introduce l' <xref:System.Windows.Controls.ScrollViewer> elemento e fornisce diversi esempi di utilizzo.  
  
<a name="what_is_a_scrollviewer_element"></a>
## <a name="the-scrollviewer-control"></a>Controllo ScrollViewer  
 Sono disponibili due elementi predefiniti che consentono lo scorrimento nelle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazioni: <xref:System.Windows.Controls.Primitives.ScrollBar> e <xref:System.Windows.Controls.ScrollViewer> . Il <xref:System.Windows.Controls.ScrollViewer> controllo incapsula elementi orizzontali e verticali <xref:System.Windows.Controls.Primitives.ScrollBar> e un contenitore di contenuto (ad esempio un <xref:System.Windows.Controls.Panel> elemento) per visualizzare altri elementi visibili in un'area scorrevole. Per usare l' <xref:System.Windows.Controls.Primitives.ScrollBar> elemento per lo scorrimento del contenuto, è necessario compilare un oggetto personalizzato. Tuttavia, è possibile usare l' <xref:System.Windows.Controls.ScrollViewer> elemento da solo perché si tratta di un controllo composito che incapsula la <xref:System.Windows.Controls.Primitives.ScrollBar> funzionalità.  
  
 Il <xref:System.Windows.Controls.ScrollViewer> controllo risponde ai comandi del mouse e della tastiera e definisce diversi metodi con cui scorrere il contenuto in base a incrementi predeterminati. È possibile utilizzare l' <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> evento per rilevare una modifica in uno <xref:System.Windows.Controls.ScrollViewer> stato.  
  
 Un oggetto <xref:System.Windows.Controls.ScrollViewer> può avere un solo elemento figlio, in genere un <xref:System.Windows.Controls.Panel> elemento che può ospitare una <xref:System.Windows.Controls.Panel.Children%2A> raccolta di elementi. La <xref:System.Windows.Controls.ContentPresenter.Content%2A> proprietà definisce l'unico elemento figlio dell'oggetto <xref:System.Windows.Controls.ScrollViewer> .  
  
<a name="scrollviewer_physical_vs_logical"></a>
## <a name="physical-vs-logical-scrolling"></a>Scorrimento fisico rispetto a scorrimento logico  
 Si usa lo scorrimento fisico per scorrere il contenuto di un incremento fisico predeterminato, in genere un valore che viene dichiarato in pixel. Si usa lo scorrimento logico per passare all'elemento successivo nell'albero logico. Lo scorrimento fisico è il comportamento di scorrimento predefinito per la maggior parte <xref:System.Windows.Controls.Panel> degli elementi. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] supporta entrambi i tipi di scorrimento.  
  
#### <a name="the-iscrollinfo-interface"></a>Interfaccia IScrollInfo  
 L' <xref:System.Windows.Controls.Primitives.IScrollInfo> interfaccia rappresenta l'area di scorrimento principale in un <xref:System.Windows.Controls.ScrollViewer> controllo derivato o. L'interfaccia definisce le proprietà e i metodi di scorrimento che possono essere implementati da <xref:System.Windows.Controls.Panel> elementi che richiedono lo scorrimento in base a un'unità logica, anziché a un incremento fisico. Il cast di un'istanza di <xref:System.Windows.Controls.Primitives.IScrollInfo> a un oggetto derivato <xref:System.Windows.Controls.Panel> e quindi l'uso dei metodi di scorrimento fornisce un modo utile per scorrere fino all'unità logica successiva in una raccolta figlio, anziché in base all'incremento del pixel. Per impostazione predefinita, il <xref:System.Windows.Controls.ScrollViewer> controllo supporta lo scorrimento in base alle unità fisiche.  
  
 <xref:System.Windows.Controls.StackPanel>e <xref:System.Windows.Controls.VirtualizingStackPanel> implementano <xref:System.Windows.Controls.Primitives.IScrollInfo> e supportano in modo nativo lo scorrimento logico. Per i controlli di layout che supportano a livello nativo lo scorrimento logico, è comunque possibile ottenere lo scorrimento fisico eseguendo il wrapping dell' <xref:System.Windows.Controls.Panel> elemento host in un oggetto <xref:System.Windows.Controls.ScrollViewer> e impostando la <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> proprietà su `false` .  
  
 Nell'esempio di codice riportato di seguito viene illustrato come eseguire il cast di un'istanza di <xref:System.Windows.Controls.Primitives.IScrollInfo> a un oggetto <xref:System.Windows.Controls.StackPanel> e utilizzare i metodi di scorrimento del contenuto ( <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> e <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> ) definiti dall'interfaccia.  
  
 [!code-csharp[IScrollInfoMethods#3](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
<a name="scrollviewer_markup_syntax_and_sample"></a>
## <a name="defining-and-using-a-scrollviewer-element"></a>Definizione e uso di un elemento ScrollViewer  
 Nell'esempio seguente viene creato un oggetto <xref:System.Windows.Controls.ScrollViewer> in una finestra contenente testo e un rettangolo. <xref:System.Windows.Controls.Primitives.ScrollBar>gli elementi vengono visualizzati solo quando sono necessari. Quando si ridimensiona la finestra, gli <xref:System.Windows.Controls.Primitives.ScrollBar> elementi vengono visualizzati e scompaiono a causa dei valori aggiornati delle <xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A> <xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A> proprietà e.  
  
 [!code-cpp[ScrollViewer#1](~/samples/snippets/cpp/VS_Snippets_Wpf/ScrollViewer/CPP/ScrollViewer_wcp.cpp#1)]
 [!code-csharp[ScrollViewer#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewer/CSharp/ScrollViewer_wcp.cs#1)]
 [!code-vb[ScrollViewer#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewer/VisualBasic/ScrollViewer.vb#1)]
 [!code-xaml[ScrollViewer#1](~/samples/snippets/xaml/VS_Snippets_Wpf/ScrollViewer/XAML/Pane1.xaml#1)]  
  
<a name="scrollviewer_styling_scrollviewer"></a>
## <a name="styling-a-scrollviewer"></a>Applicazione di uno stile a un elemento ScrollViewer  
 Come tutti i controlli in Windows Presentation Foundation, <xref:System.Windows.Controls.ScrollViewer> è possibile applicare uno stile al per modificare il comportamento di rendering predefinito del controllo. Per altre informazioni sull'applicazione di stili di controllo, vedere [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md).  
  
<a name="scrollviewer_scroll_vs_paginate"></a>
## <a name="paginating-documents"></a>Paginazione di documenti  
 Per il contenuto del documento, un'alternativa alla visualizzazione a scorrimento consiste nello scegliere un contenitore di documenti che supporta l'impaginazione. <xref:System.Windows.Documents.FlowDocument>è per i documenti progettati per essere ospitati all'interno di un controllo di visualizzazione, ad esempio <xref:System.Windows.Controls.FlowDocumentPageViewer> , che supporta il contenuto paginazione in più pagine, evitando la necessità di scorrimento. <xref:System.Windows.Controls.DocumentViewer>fornisce una soluzione per la visualizzazione del <xref:System.Windows.Documents.FixedDocument> contenuto, che usa lo scorrimento tradizionale per visualizzare il contenuto all'esterno dell'area di autenticazione dell'area di visualizzazione.  
  
 Per altre informazioni sui formati di documento e sulle opzioni di presentazione, vedere [Documenti in WPF](../advanced/documents-in-wpf.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.Primitives.ScrollBar>
- <xref:System.Windows.Controls.Primitives.IScrollInfo>
- [Procedura: creare un visualizzatore di scorrimento](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752352(v=vs.90))
- [Documenti in WPF](../advanced/documents-in-wpf.md)
- [Stili e modelli di ScrollBar](scrollbar-styles-and-templates.md)
- [Controlli](../advanced/optimizing-performance-controls.md)
