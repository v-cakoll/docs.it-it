---
title: 'Procedura: Creare un effetto di attivazione utilizzando gli eventi'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors of elements [WPF], changing
- rollover effect [WPF]
- element colors [WPF], changing
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
ms.openlocfilehash: 806056397200fa5c567e83227499ba721544f523
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005183"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a><span data-ttu-id="5f3d9-102">Procedura: Creare un effetto di attivazione utilizzando gli eventi</span><span class="sxs-lookup"><span data-stu-id="5f3d9-102">How to: Create a Rollover Effect Using Events</span></span>
<span data-ttu-id="5f3d9-103">Questo esempio Mostra come modificare il colore di un elemento quando il puntatore del mouse entra e lascia l'area occupata dall'elemento.</span><span class="sxs-lookup"><span data-stu-id="5f3d9-103">This example shows how to change the color of an element as the mouse pointer enters and leaves the area occupied by the element.</span></span>  
  
 <span data-ttu-id="5f3d9-104">Questo esempio è costituito da un file [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] e da un file code-behind.</span><span class="sxs-lookup"><span data-stu-id="5f3d9-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5f3d9-105">In questo esempio viene illustrato come utilizzare gli eventi, ma il metodo consigliato per ottenere questo risultato consiste nell'utilizzare un <xref:System.Windows.Trigger> in uno stile.</span><span class="sxs-lookup"><span data-stu-id="5f3d9-105">This example demonstrates how to use events, but the recommended way to achieve this same effect is to use a <xref:System.Windows.Trigger> in a style.</span></span> <span data-ttu-id="5f3d9-106">Per altre informazioni, vedere [Applicazione di stili e modelli](../controls/styling-and-templating.md).</span><span class="sxs-lookup"><span data-stu-id="5f3d9-106">For more information, see [Styling and Templating](../controls/styling-and-templating.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f3d9-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="5f3d9-107">Example</span></span>  
 <span data-ttu-id="5f3d9-108">Il codice XAML seguente crea l'interfaccia utente, che è costituita da <xref:System.Windows.Controls.Border> intorno a un <xref:System.Windows.Controls.TextBlock>, e connette i gestori eventi <xref:System.Windows.Input.Mouse.MouseEnter> e <xref:System.Windows.UIElement.MouseLeave> a <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="5f3d9-108">The following XAML creates the user interface, which consists of <xref:System.Windows.Controls.Border> around a <xref:System.Windows.Controls.TextBlock>, and attaches the <xref:System.Windows.Input.Mouse.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers to the <xref:System.Windows.Controls.Border>.</span></span>  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 <span data-ttu-id="5f3d9-109">Il codice sottostante seguente consente di creare i gestori eventi <xref:System.Windows.UIElement.MouseEnter> e <xref:System.Windows.UIElement.MouseLeave>.</span><span class="sxs-lookup"><span data-stu-id="5f3d9-109">The following code behind creates the <xref:System.Windows.UIElement.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers.</span></span>  <span data-ttu-id="5f3d9-110">Quando il puntatore del mouse entra nell'<xref:System.Windows.Controls.Border>, lo sfondo del <xref:System.Windows.Controls.Border> viene modificato in rosso.</span><span class="sxs-lookup"><span data-stu-id="5f3d9-110">When the mouse pointer enters the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed to red.</span></span>  <span data-ttu-id="5f3d9-111">Quando il puntatore del mouse esce dalla <xref:System.Windows.Controls.Border>, lo sfondo del <xref:System.Windows.Controls.Border> viene modificato di nuovo in bianco.</span><span class="sxs-lookup"><span data-stu-id="5f3d9-111">When the mouse pointer leaves the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed back to white.</span></span>  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
