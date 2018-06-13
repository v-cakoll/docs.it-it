---
title: 'Procedura: fare in modo che un oggetto segua il puntatore del mouse'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- following the mouse pointer (cursor)
- mouse pointer (cursor), making objects follow
- cursor (mouse pointer), making objects follow
ms.assetid: 50b20415-14bc-405c-baf3-2fb254fffde3
ms.openlocfilehash: 860b42f4dc068bc3063001e25e8b012c50b59213
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543872"
---
# <a name="how-to-make-an-object-follow-the-mouse-pointer"></a><span data-ttu-id="0aa42-102">Procedura: fare in modo che un oggetto segua il puntatore del mouse</span><span class="sxs-lookup"><span data-stu-id="0aa42-102">How to: Make an Object Follow the Mouse Pointer</span></span>
<span data-ttu-id="0aa42-103">In questo esempio viene illustrato come modificare le dimensioni di un oggetto quando si sposta il puntatore del mouse sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="0aa42-103">This example shows how to change the dimensions of an object when the mouse pointer moves on the screen.</span></span>  
  
 <span data-ttu-id="0aa42-104">L'esempio include un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file che crea il [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] e un file code-behind che crea il gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="0aa42-104">The example includes an [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file that creates the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] and a code-behind file that creates the event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0aa42-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="0aa42-105">Example</span></span>  
 <span data-ttu-id="0aa42-106">Le operazioni seguenti [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] crea il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], che include un <xref:System.Windows.Shapes.Ellipse> all'interno di un <xref:System.Windows.Controls.StackPanel>e associa il gestore eventi per il <xref:System.Windows.UIElement.MouseMove> evento.</span><span class="sxs-lookup"><span data-stu-id="0aa42-106">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], which consists of an <xref:System.Windows.Shapes.Ellipse> inside of a <xref:System.Windows.Controls.StackPanel>, and attaches the event handler for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>  
  
 [!code-xaml[mouseMoveWithPointer#MouseMoveWithPointerXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 <span data-ttu-id="0aa42-107">Il codice seguente crea il <xref:System.Windows.UIElement.MouseMove> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="0aa42-107">The following code behind creates the <xref:System.Windows.UIElement.MouseMove> event handler.</span></span>  <span data-ttu-id="0aa42-108">Quando il puntatore del mouse viene spostato, l'altezza e larghezza di <xref:System.Windows.Shapes.Ellipse> vengono aumentate e ridotte.</span><span class="sxs-lookup"><span data-stu-id="0aa42-108">When the mouse pointer moves, the height and the width of the <xref:System.Windows.Shapes.Ellipse> are increased and decreased.</span></span>  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## <a name="see-also"></a><span data-ttu-id="0aa42-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0aa42-109">See Also</span></span>  
 [<span data-ttu-id="0aa42-110">Cenni preliminari sull'input</span><span class="sxs-lookup"><span data-stu-id="0aa42-110">Input Overview</span></span>](../../../../docs/framework/wpf/advanced/input-overview.md)
