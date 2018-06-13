---
title: "Procedura: scorrere il contenuto mediante l'interfaccia IScrollInfo"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ScrollViewer control [WPF], scrolling content
- scrolling content [WPF]
- IScrollInfo interface [WPF]
ms.assetid: d8700bef-a3f8-4c12-9de2-fc3b79f32cd3
ms.openlocfilehash: 8154a626c6bf48a59be0540f857c0c51d59a26c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552883"
---
# <a name="how-to-scroll-content-by-using-the-iscrollinfo-interface"></a><span data-ttu-id="07c2d-102">Procedura: scorrere il contenuto mediante l'interfaccia IScrollInfo</span><span class="sxs-lookup"><span data-stu-id="07c2d-102">How to: Scroll Content by Using the IScrollInfo Interface</span></span>
<span data-ttu-id="07c2d-103">In questo esempio viene illustrato come scorrere il contenuto utilizzando il <xref:System.Windows.Controls.Primitives.IScrollInfo> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="07c2d-103">This example shows how to scroll content by using the <xref:System.Windows.Controls.Primitives.IScrollInfo> interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07c2d-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="07c2d-104">Example</span></span>  
 <span data-ttu-id="07c2d-105">L'esempio seguente illustra le funzionalità del <xref:System.Windows.Controls.Primitives.IScrollInfo> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="07c2d-105">The following example demonstrates the features of the <xref:System.Windows.Controls.Primitives.IScrollInfo> interface.</span></span> <span data-ttu-id="07c2d-106">Nell'esempio viene creato un <xref:System.Windows.Controls.StackPanel> elemento [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] annidato in un elemento padre <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="07c2d-106">The example creates a <xref:System.Windows.Controls.StackPanel> element in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that is nested in a parent <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="07c2d-107">Gli elementi figlio del <xref:System.Windows.Controls.StackPanel> è possibile scorrere in modo logico utilizzando i metodi definiti per il <xref:System.Windows.Controls.Primitives.IScrollInfo> interfaccia ed eseguire il cast all'istanza di <xref:System.Windows.Controls.StackPanel> (`sp1`) nel codice.</span><span class="sxs-lookup"><span data-stu-id="07c2d-107">The child elements of the <xref:System.Windows.Controls.StackPanel> can be scrolled logically by using the methods defined by the <xref:System.Windows.Controls.Primitives.IScrollInfo> interface and cast to the instance of <xref:System.Windows.Controls.StackPanel> (`sp1`) in code.</span></span>  
  
 [!code-xaml[IScrollInfoMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="07c2d-108">Ogni <xref:System.Windows.Controls.Button> nel [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file attiva un metodo personalizzato associato che controlla il comportamento di scorrimento in <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="07c2d-108">Each <xref:System.Windows.Controls.Button> in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file triggers an associated custom method that controls scrolling behavior in <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="07c2d-109">Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> e <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> metodi; viene inoltre genericamente illustrato come utilizzare tutti i metodi di posizionamento che la <xref:System.Windows.Controls.Primitives.IScrollInfo> classe definisce.</span><span class="sxs-lookup"><span data-stu-id="07c2d-109">The following example shows how to use the <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> and <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> methods; it also generically shows how to use all the positioning methods that the <xref:System.Windows.Controls.Primitives.IScrollInfo> class defines.</span></span>  
  
 [!code-csharp[IScrollInfoMethods#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="07c2d-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07c2d-110">See Also</span></span>  
 <xref:System.Windows.Controls.ScrollViewer>  
 <xref:System.Windows.Controls.Primitives.IScrollInfo>  
 <xref:System.Windows.Controls.StackPanel>  
 [<span data-ttu-id="07c2d-111">Panoramica sull'elemento ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="07c2d-111">ScrollViewer Overview</span></span>](../../../../docs/framework/wpf/controls/scrollviewer-overview.md)  
 [<span data-ttu-id="07c2d-112">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="07c2d-112">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/scrollviewer-how-to-topics.md)  
 [<span data-ttu-id="07c2d-113">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="07c2d-113">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
