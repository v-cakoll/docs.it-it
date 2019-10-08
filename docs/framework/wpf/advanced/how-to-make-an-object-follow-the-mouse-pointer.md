---
title: 'Procedura: Fare in modo che un oggetto segua il puntatore del mouse'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- following the mouse pointer (cursor)
- mouse pointer (cursor), making objects follow
- cursor (mouse pointer), making objects follow
ms.assetid: 50b20415-14bc-405c-baf3-2fb254fffde3
ms.openlocfilehash: 4ef3028b6c71b94a593d168ad6570c4aec12b86b
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005071"
---
# <a name="how-to-make-an-object-follow-the-mouse-pointer"></a><span data-ttu-id="4bbae-102">Procedura: Fare in modo che un oggetto segua il puntatore del mouse</span><span class="sxs-lookup"><span data-stu-id="4bbae-102">How to: Make an Object Follow the Mouse Pointer</span></span>
<span data-ttu-id="4bbae-103">Questo esempio Mostra come modificare le dimensioni di un oggetto quando il puntatore del mouse viene spostato sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="4bbae-103">This example shows how to change the dimensions of an object when the mouse pointer moves on the screen.</span></span>  
  
 <span data-ttu-id="4bbae-104">Nell'esempio è incluso un file [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] che crea il [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] e un file code-behind che crea il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="4bbae-104">The example includes an [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file that creates the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] and a code-behind file that creates the event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4bbae-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="4bbae-105">Example</span></span>  
 <span data-ttu-id="4bbae-106">Il codice XAML seguente crea il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], che è costituito da un <xref:System.Windows.Shapes.Ellipse> all'interno di un <xref:System.Windows.Controls.StackPanel> e connette il gestore eventi per l'evento <xref:System.Windows.UIElement.MouseMove>.</span><span class="sxs-lookup"><span data-stu-id="4bbae-106">The following XAML creates the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], which consists of an <xref:System.Windows.Shapes.Ellipse> inside of a <xref:System.Windows.Controls.StackPanel>, and attaches the event handler for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>  
  
 [!code-xaml[mouseMoveWithPointer#MouseMoveWithPointerXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 <span data-ttu-id="4bbae-107">Il codice sottostante seguente crea il gestore dell'evento <xref:System.Windows.UIElement.MouseMove>.</span><span class="sxs-lookup"><span data-stu-id="4bbae-107">The following code behind creates the <xref:System.Windows.UIElement.MouseMove> event handler.</span></span>  <span data-ttu-id="4bbae-108">Quando il puntatore del mouse viene spostato, l'altezza e la larghezza del <xref:System.Windows.Shapes.Ellipse> vengono aumentate e diminuite.</span><span class="sxs-lookup"><span data-stu-id="4bbae-108">When the mouse pointer moves, the height and the width of the <xref:System.Windows.Shapes.Ellipse> are increased and decreased.</span></span>  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## <a name="see-also"></a><span data-ttu-id="4bbae-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4bbae-109">See also</span></span>

- [<span data-ttu-id="4bbae-110">Cenni preliminari sull'input</span><span class="sxs-lookup"><span data-stu-id="4bbae-110">Input Overview</span></span>](input-overview.md)
