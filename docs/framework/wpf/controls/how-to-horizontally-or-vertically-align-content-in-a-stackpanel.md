---
title: 'Procedura: allineare orizzontalmente o verticalmente il contenuto in un elemento StackPanel'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StackPanel control [WPF], content alignment [WPF]
- content alignment [WPF]
- aligning [WPF], content
ms.assetid: c1e8f962-72c8-4e7a-8670-7a2d7e021791
ms.openlocfilehash: a03cb1ed9b3e5bd42b28e37f5bbb3e1d0446a4ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33550754"
---
# <a name="how-to-horizontally-or-vertically-align-content-in-a-stackpanel"></a><span data-ttu-id="88a8a-102">Procedura: allineare orizzontalmente o verticalmente il contenuto in un elemento StackPanel</span><span class="sxs-lookup"><span data-stu-id="88a8a-102">How to: Horizontally or Vertically Align Content in a StackPanel</span></span>
<span data-ttu-id="88a8a-103">In questo esempio viene illustrato come modificare il <xref:System.Windows.Controls.StackPanel.Orientation%2A> del contenuto all'interno di un <xref:System.Windows.Controls.StackPanel> elemento e come modificare il <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> e <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> del contenuto figlio.</span><span class="sxs-lookup"><span data-stu-id="88a8a-103">This example shows how to adjust the <xref:System.Windows.Controls.StackPanel.Orientation%2A> of content within a <xref:System.Windows.Controls.StackPanel> element, and also how to adjust the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> of child content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88a8a-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="88a8a-104">Example</span></span>  
 <span data-ttu-id="88a8a-105">L'esempio seguente crea tre <xref:System.Windows.Controls.ListBox> elementi [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88a8a-105">The following example creates three <xref:System.Windows.Controls.ListBox> elements in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="88a8a-106">Ogni <xref:System.Windows.Controls.ListBox> rappresenta i valori possibili del <xref:System.Windows.Controls.StackPanel.Orientation%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, e <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> le proprietà di un <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="88a8a-106">Each <xref:System.Windows.Controls.ListBox> represents the possible values of the <xref:System.Windows.Controls.StackPanel.Orientation%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> properties of a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="88a8a-107">Quando un utente seleziona un valore in uno del <xref:System.Windows.Controls.ListBox> elementi, la proprietà associata del <xref:System.Windows.Controls.StackPanel> e del relativo figlio <xref:System.Windows.Controls.Button> modificare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="88a8a-107">When a user selects a value in any of the <xref:System.Windows.Controls.ListBox> elements, the associated property of the <xref:System.Windows.Controls.StackPanel> and its child <xref:System.Windows.Controls.Button> elements change.</span></span>  
  
 [!code-xaml[StackPanelIntroSamp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="88a8a-108">Il file code-behind seguente definisce le modifiche agli eventi che sono associati le <xref:System.Windows.Controls.ListBox> di selezione cambia.</span><span class="sxs-lookup"><span data-stu-id="88a8a-108">The following code-behind file defines the changes to the events that are associated with the <xref:System.Windows.Controls.ListBox> selection changes.</span></span> <span data-ttu-id="88a8a-109"><xref:System.Windows.Controls.StackPanel> è identificato dal <xref:System.Windows.FrameworkElement.Name%2A> `sp1`.</span><span class="sxs-lookup"><span data-stu-id="88a8a-109"><xref:System.Windows.Controls.StackPanel> is identified by the <xref:System.Windows.FrameworkElement.Name%2A> `sp1`.</span></span>  
  
 [!code-csharp[StackPanelIntroSamp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[StackPanelIntroSamp#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelIntroSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="88a8a-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88a8a-110">See Also</span></span>  
 <xref:System.Windows.Controls.StackPanel>  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>  
 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>  
 [<span data-ttu-id="88a8a-111">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="88a8a-111">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
