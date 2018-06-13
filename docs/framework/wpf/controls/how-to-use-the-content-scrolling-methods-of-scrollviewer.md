---
title: 'Procedura: utilizzare i metodi di scorrimento del contenuto di ScrollViewer'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- IScrollInfo interface [WPF]
- scrolling methods [WPF]
- ScrollViewer control [WPF], scrolling methods
ms.assetid: 4708cc65-6510-45f8-82e6-30b0d3e30045
ms.openlocfilehash: b4da666934be7dd182838d870e54e496b2646901
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552766"
---
# <a name="how-to-use-the-content-scrolling-methods-of-scrollviewer"></a><span data-ttu-id="a505f-102">Procedura: utilizzare i metodi di scorrimento del contenuto di ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="a505f-102">How to: Use the Content-Scrolling Methods of ScrollViewer</span></span>
<span data-ttu-id="a505f-103">In questo esempio viene illustrato come utilizzare i metodi di scorrimento di <xref:System.Windows.Controls.ScrollViewer> elemento.</span><span class="sxs-lookup"><span data-stu-id="a505f-103">This example shows how to use the scrolling methods of the <xref:System.Windows.Controls.ScrollViewer> element.</span></span> <span data-ttu-id="a505f-104">Questi metodi consentono lo scorrimento incrementale del contenuto, tramite la riga o pagina, in un <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="a505f-104">These methods provide incremental scrolling of content, either by line or by page, in a <xref:System.Windows.Controls.ScrollViewer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a505f-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="a505f-105">Example</span></span>  
 <span data-ttu-id="a505f-106">Nell'esempio seguente viene creato un <xref:System.Windows.Controls.ScrollViewer> denominato `sv1`, che ospita un elemento figlio <xref:System.Windows.Controls.TextBlock> elemento.</span><span class="sxs-lookup"><span data-stu-id="a505f-106">The following example creates a <xref:System.Windows.Controls.ScrollViewer> named `sv1`, which hosts a child <xref:System.Windows.Controls.TextBlock> element.</span></span> <span data-ttu-id="a505f-107">Poiché il <xref:System.Windows.Controls.TextBlock> è più grande del padre <xref:System.Windows.Controls.ScrollViewer>, vengono visualizzate le barre di scorrimento per consentire lo scorrimento.</span><span class="sxs-lookup"><span data-stu-id="a505f-107">Because the <xref:System.Windows.Controls.TextBlock> is larger than the parent <xref:System.Windows.Controls.ScrollViewer>, scroll bars appear in order to enable scrolling.</span></span> <span data-ttu-id="a505f-108"><xref:System.Windows.Controls.Button> gli elementi che rappresentano i diversi metodi di scorrimento sono ancorati a sinistra in un apposito <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="a505f-108"><xref:System.Windows.Controls.Button> elements that represent the various scrolling methods are docked on the left in a separate <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="a505f-109">Ogni <xref:System.Windows.Controls.Button> nel [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file chiama un metodo personalizzato correlato che controlla il comportamento di scorrimento in <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="a505f-109">Each <xref:System.Windows.Controls.Button> in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file calls a related custom method that controls scrolling behavior in <xref:System.Windows.Controls.ScrollViewer>.</span></span>  
  
 [!code-xaml[ScrollViewerMethods#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="a505f-110">L'esempio seguente usa il <xref:System.Windows.Controls.ScrollViewer.LineUp%2A> e <xref:System.Windows.Controls.ScrollViewer.LineDown%2A> metodi.</span><span class="sxs-lookup"><span data-stu-id="a505f-110">The following example uses the <xref:System.Windows.Controls.ScrollViewer.LineUp%2A> and <xref:System.Windows.Controls.ScrollViewer.LineDown%2A> methods.</span></span>  
  
 [!code-csharp[ScrollViewerMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ScrollViewerMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewerMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="a505f-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a505f-111">See Also</span></span>  
 <xref:System.Windows.Controls.ScrollViewer>  
 <xref:System.Windows.Controls.StackPanel>
