---
title: "Procedura: Partizionare lo spazio usando l'elemento DockPanel"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], partitioning space
- partitioning space [WPF]
ms.assetid: a219b9e5-b205-4438-89b5-0a137ac463ab
ms.openlocfilehash: ab51270644bf370944ebc933c765b40c528681c5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158886"
---
# <a name="how-to-partition-space-by-using-the-dockpanel-element"></a><span data-ttu-id="3ffbb-102">Procedura: Partizionare lo spazio usando l'elemento DockPanel</span><span class="sxs-lookup"><span data-stu-id="3ffbb-102">How to: Partition Space by Using the DockPanel Element</span></span>
<span data-ttu-id="3ffbb-103">L'esempio seguente crea una semplice [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] framework usando un <xref:System.Windows.Controls.DockPanel> elemento.</span><span class="sxs-lookup"><span data-stu-id="3ffbb-103">The following example creates a simple [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] framework using a <xref:System.Windows.Controls.DockPanel> element.</span></span> <span data-ttu-id="3ffbb-104">Il <xref:System.Windows.Controls.DockPanel> partiziona lo spazio disponibile per i relativi elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="3ffbb-104">The <xref:System.Windows.Controls.DockPanel> partitions available space to its child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ffbb-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="3ffbb-105">Example</span></span>  
 <span data-ttu-id="3ffbb-106">Questo esempio Usa la <xref:System.Windows.Controls.DockPanel.Dock%2A> proprietà, ovvero una proprietà associata, per ancorare due identici <xref:System.Windows.Controls.Border> elementi nel <xref:System.Windows.Controls.Dock.Top> dello spazio partizionato.</span><span class="sxs-lookup"><span data-stu-id="3ffbb-106">This example uses the <xref:System.Windows.Controls.DockPanel.Dock%2A> property, which is an attached property, to dock two identical <xref:System.Windows.Controls.Border> elements at the <xref:System.Windows.Controls.Dock.Top> of the partitioned space.</span></span> <span data-ttu-id="3ffbb-107">Una terza <xref:System.Windows.Controls.Border> per l'elemento è ancorato il <xref:System.Windows.Controls.Dock.Left>, con una larghezza di 200 pixel.</span><span class="sxs-lookup"><span data-stu-id="3ffbb-107">A third <xref:System.Windows.Controls.Border> element is docked to the <xref:System.Windows.Controls.Dock.Left>, with its width set to 200 pixels.</span></span> <span data-ttu-id="3ffbb-108">Un quarto <xref:System.Windows.Controls.Border> è ancorato il <xref:System.Windows.Controls.Dock.Bottom> dello schermo.</span><span class="sxs-lookup"><span data-stu-id="3ffbb-108">A fourth <xref:System.Windows.Controls.Border> is docked to the <xref:System.Windows.Controls.Dock.Bottom> of the screen.</span></span> <span data-ttu-id="3ffbb-109">L'ultimo <xref:System.Windows.Controls.Border> elemento riempie automaticamente lo spazio rimanente.</span><span class="sxs-lookup"><span data-stu-id="3ffbb-109">The last <xref:System.Windows.Controls.Border> element automatically fills the remaining space.</span></span>  
  
 [!code-cpp[DockPanelOvwSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
>  <span data-ttu-id="3ffbb-110">Per impostazione predefinita, l'ultimo elemento figlio di un <xref:System.Windows.Controls.DockPanel> elemento riempie il rimanente spazio non allocato.</span><span class="sxs-lookup"><span data-stu-id="3ffbb-110">By default, the last child of a <xref:System.Windows.Controls.DockPanel> element fills the remaining unallocated space.</span></span> <span data-ttu-id="3ffbb-111">Se non si desidera questo comportamento, impostare `LastChildFill="False"`.</span><span class="sxs-lookup"><span data-stu-id="3ffbb-111">If you do not want this behavior, set `LastChildFill="False"`.</span></span>  
  
 <span data-ttu-id="3ffbb-112">L'applicazione compilata crea una nuova interfaccia utente analoga alla seguente.</span><span class="sxs-lookup"><span data-stu-id="3ffbb-112">The compiled application yields a new UI that looks like this.</span></span>  
  
 <span data-ttu-id="3ffbb-113">![Scenario DockPanel tipico.](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span><span class="sxs-lookup"><span data-stu-id="3ffbb-113">![A typical DockPanel scenario.](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ffbb-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ffbb-114">See also</span></span>

- <xref:System.Windows.Controls.DockPanel>
- [<span data-ttu-id="3ffbb-115">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="3ffbb-115">Panels Overview</span></span>](panels-overview.md)
