---
title: 'Procedura: applicare le proprietà Stretch al contenuto di un Viewbox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StretchDirection properties [WPF]
- Stretch properties [WPF]
- controls [WPF], Viewbox
- Viewbox control [WPF]
ms.assetid: b9c22ef4-bce4-4300-9e0c-8260b7db83cc
ms.openlocfilehash: 3e81ec9fd045bb3fcf359943e455d2cce94aec55
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552805"
---
# <a name="how-to-apply-stretch-properties-to-the-contents-of-a-viewbox"></a><span data-ttu-id="e49b4-102">Procedura: applicare le proprietà Stretch al contenuto di un Viewbox</span><span class="sxs-lookup"><span data-stu-id="e49b4-102">How to: Apply Stretch Properties to the Contents of a Viewbox</span></span>
## <a name="example"></a><span data-ttu-id="e49b4-103">Esempio</span><span class="sxs-lookup"><span data-stu-id="e49b4-103">Example</span></span>  
 <span data-ttu-id="e49b4-104">In questo esempio viene illustrato come modificare il valore di <xref:System.Windows.Controls.Viewbox.StretchDirection%2A> e <xref:System.Windows.Controls.Viewbox.Stretch%2A> le proprietà di un <xref:System.Windows.Controls.Viewbox>.</span><span class="sxs-lookup"><span data-stu-id="e49b4-104">This example shows how to change the value of the <xref:System.Windows.Controls.Viewbox.StretchDirection%2A> and <xref:System.Windows.Controls.Viewbox.Stretch%2A> properties of a <xref:System.Windows.Controls.Viewbox>.</span></span>  
  
 <span data-ttu-id="e49b4-105">Il primo esempio Usa [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] per definire un <xref:System.Windows.Controls.Viewbox> elemento.</span><span class="sxs-lookup"><span data-stu-id="e49b4-105">The first example uses [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to define a <xref:System.Windows.Controls.Viewbox> element.</span></span> <span data-ttu-id="e49b4-106">Assegna un <xref:System.Windows.FrameworkElement.MaxWidth%2A> e <xref:System.Windows.FrameworkElement.MaxHeight%2A> di 400.</span><span class="sxs-lookup"><span data-stu-id="e49b4-106">It assigns a <xref:System.Windows.FrameworkElement.MaxWidth%2A> and <xref:System.Windows.FrameworkElement.MaxHeight%2A> of 400.</span></span> <span data-ttu-id="e49b4-107">Viene annidato un <xref:System.Windows.Controls.Image> elemento all'interno di <xref:System.Windows.Controls.Viewbox>.</span><span class="sxs-lookup"><span data-stu-id="e49b4-107">The example nests an <xref:System.Windows.Controls.Image> element within the <xref:System.Windows.Controls.Viewbox>.</span></span> <span data-ttu-id="e49b4-108"><xref:System.Windows.Controls.Button> gli elementi che corrispondono ai valori della proprietà per il <xref:System.Windows.Controls.Viewbox.Stretch%2A> e <xref:System.Windows.Controls.StretchDirection> enumerazioni modificano il comportamento di adattamento di nidificata <xref:System.Windows.Controls.Image>.</span><span class="sxs-lookup"><span data-stu-id="e49b4-108"><xref:System.Windows.Controls.Button> elements that correspond to the property values for the <xref:System.Windows.Controls.Viewbox.Stretch%2A> and <xref:System.Windows.Controls.StretchDirection> enumerations manipulate the stretching behavior of the nested <xref:System.Windows.Controls.Image>.</span></span>  
  
 [!code-xaml[viewboxStretchLayoutSamp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="e49b4-109">Gli handle di file di codice seguente il <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gli eventi che precedente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] esempio viene definito.</span><span class="sxs-lookup"><span data-stu-id="e49b4-109">The following code-behind file handles the <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events that the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example defines.</span></span>  
  
 [!code-csharp[viewboxStretchLayoutSamp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[viewboxStretchLayoutSamp#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/viewboxStretchLayoutSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="e49b4-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e49b4-110">See Also</span></span>  
 <xref:System.Windows.Controls.Viewbox>  
 <xref:System.Windows.Media.Stretch>  
 <xref:System.Windows.Controls.StretchDirection>
