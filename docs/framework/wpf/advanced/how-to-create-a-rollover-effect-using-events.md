---
title: 'Procedura: Creare un effetto di attivazione usando gli eventi'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors of elements [WPF], changing
- rollover effect [WPF]
- element colors [WPF], changing
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
ms.openlocfilehash: 3996a3b9bb976dd5f2e5b675de3894bbaba7d9d3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960379"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a><span data-ttu-id="c8ba9-102">Procedura: Creare un effetto di attivazione usando gli eventi</span><span class="sxs-lookup"><span data-stu-id="c8ba9-102">How to: Create a Rollover Effect Using Events</span></span>
<span data-ttu-id="c8ba9-103">Questo esempio Mostra come modificare il colore di un elemento quando il puntatore del mouse entra e lascia l'area occupata dall'elemento.</span><span class="sxs-lookup"><span data-stu-id="c8ba9-103">This example shows how to change the color of an element as the mouse pointer enters and leaves the area occupied by the element.</span></span>  
  
 <span data-ttu-id="c8ba9-104">Questo esempio è costituito [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] da un file e da un file code-behind.</span><span class="sxs-lookup"><span data-stu-id="c8ba9-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c8ba9-105">Questo esempio illustra come usare gli eventi, ma la modalità consigliata per ottenere questo risultato consiste nell'usare un <xref:System.Windows.Trigger> oggetto in uno stile.</span><span class="sxs-lookup"><span data-stu-id="c8ba9-105">This example demonstrates how to use events, but the recommended way to achieve this same effect is to use a <xref:System.Windows.Trigger> in a style.</span></span> <span data-ttu-id="c8ba9-106">Per altre informazioni, vedere [Applicazione di stili e modelli](../controls/styling-and-templating.md).</span><span class="sxs-lookup"><span data-stu-id="c8ba9-106">For more information, see [Styling and Templating](../controls/styling-and-templating.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8ba9-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="c8ba9-107">Example</span></span>  
 <span data-ttu-id="c8ba9-108">Nell'esempio [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] seguente viene creata l'interfaccia utente che <xref:System.Windows.Controls.Border> è costituita <xref:System.Windows.Controls.TextBlock>da un oggetto e i <xref:System.Windows.Input.Mouse.MouseEnter> gestori <xref:System.Windows.UIElement.MouseLeave> eventi e vengono collegati a <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="c8ba9-108">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the user interface, which consists of <xref:System.Windows.Controls.Border> around a <xref:System.Windows.Controls.TextBlock>, and attaches the <xref:System.Windows.Input.Mouse.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers to the <xref:System.Windows.Controls.Border>.</span></span>  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 <span data-ttu-id="c8ba9-109">Il codice sottostante seguente consente di <xref:System.Windows.UIElement.MouseEnter> creare <xref:System.Windows.UIElement.MouseLeave> i gestori eventi e.</span><span class="sxs-lookup"><span data-stu-id="c8ba9-109">The following code behind creates the <xref:System.Windows.UIElement.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers.</span></span>  <span data-ttu-id="c8ba9-110">Quando il puntatore del mouse entra <xref:System.Windows.Controls.Border>in, lo sfondo <xref:System.Windows.Controls.Border> di viene modificato in rosso.</span><span class="sxs-lookup"><span data-stu-id="c8ba9-110">When the mouse pointer enters the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed to red.</span></span>  <span data-ttu-id="c8ba9-111">Quando il puntatore del mouse esce <xref:System.Windows.Controls.Border>dall'oggetto, lo sfondo <xref:System.Windows.Controls.Border> di viene modificato di nuovo in bianco.</span><span class="sxs-lookup"><span data-stu-id="c8ba9-111">When the mouse pointer leaves the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed back to white.</span></span>  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
