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
ms.openlocfilehash: d22a808ce3ab95e3b351408bf4cc372a335da553
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960193"
---
# <a name="how-to-partition-space-by-using-the-dockpanel-element"></a><span data-ttu-id="35c17-102">Procedura: Partizionare lo spazio usando l'elemento DockPanel</span><span class="sxs-lookup"><span data-stu-id="35c17-102">How to: Partition Space by Using the DockPanel Element</span></span>
<span data-ttu-id="35c17-103">Nell'esempio seguente viene creato un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Framework semplice utilizzando <xref:System.Windows.Controls.DockPanel> un elemento.</span><span class="sxs-lookup"><span data-stu-id="35c17-103">The following example creates a simple [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] framework using a <xref:System.Windows.Controls.DockPanel> element.</span></span> <span data-ttu-id="35c17-104">Spazio <xref:System.Windows.Controls.DockPanel> disponibile nelle partizioni per i relativi elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="35c17-104">The <xref:System.Windows.Controls.DockPanel> partitions available space to its child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35c17-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="35c17-105">Example</span></span>  
 <span data-ttu-id="35c17-106">In questo esempio viene <xref:System.Windows.Controls.DockPanel.Dock%2A> utilizzata la proprietà, che è una proprietà associata, per ancorare due elementi <xref:System.Windows.Controls.Dock.Top> identici <xref:System.Windows.Controls.Border> all'oggetto dello spazio partizionato.</span><span class="sxs-lookup"><span data-stu-id="35c17-106">This example uses the <xref:System.Windows.Controls.DockPanel.Dock%2A> property, which is an attached property, to dock two identical <xref:System.Windows.Controls.Border> elements at the <xref:System.Windows.Controls.Dock.Top> of the partitioned space.</span></span> <span data-ttu-id="35c17-107">Un terzo <xref:System.Windows.Controls.Border> elemento è ancorato <xref:System.Windows.Controls.Dock.Left>a, con larghezza impostata su 200 pixel.</span><span class="sxs-lookup"><span data-stu-id="35c17-107">A third <xref:System.Windows.Controls.Border> element is docked to the <xref:System.Windows.Controls.Dock.Left>, with its width set to 200 pixels.</span></span> <span data-ttu-id="35c17-108">Un quarto <xref:System.Windows.Controls.Border> è ancorato all'oggetto <xref:System.Windows.Controls.Dock.Bottom> dello schermo.</span><span class="sxs-lookup"><span data-stu-id="35c17-108">A fourth <xref:System.Windows.Controls.Border> is docked to the <xref:System.Windows.Controls.Dock.Bottom> of the screen.</span></span> <span data-ttu-id="35c17-109">L'ultimo <xref:System.Windows.Controls.Border> elemento riempie automaticamente lo spazio rimanente.</span><span class="sxs-lookup"><span data-stu-id="35c17-109">The last <xref:System.Windows.Controls.Border> element automatically fills the remaining space.</span></span>  
  
 [!code-cpp[DockPanelOvwSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
> <span data-ttu-id="35c17-110">Per impostazione predefinita, l'ultimo elemento figlio <xref:System.Windows.Controls.DockPanel> di un elemento riempie lo spazio rimanente non allocato.</span><span class="sxs-lookup"><span data-stu-id="35c17-110">By default, the last child of a <xref:System.Windows.Controls.DockPanel> element fills the remaining unallocated space.</span></span> <span data-ttu-id="35c17-111">Se non si desidera questo comportamento, impostare `LastChildFill="False"`.</span><span class="sxs-lookup"><span data-stu-id="35c17-111">If you do not want this behavior, set `LastChildFill="False"`.</span></span>  
  
 <span data-ttu-id="35c17-112">L'applicazione compilata crea una nuova interfaccia utente analoga alla seguente.</span><span class="sxs-lookup"><span data-stu-id="35c17-112">The compiled application yields a new UI that looks like this.</span></span>  
  
 <span data-ttu-id="35c17-113">![Scenario DockPanel tipico.](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span><span class="sxs-lookup"><span data-stu-id="35c17-113">![A typical DockPanel scenario.](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35c17-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35c17-114">See also</span></span>

- <xref:System.Windows.Controls.DockPanel>
- [<span data-ttu-id="35c17-115">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="35c17-115">Panels Overview</span></span>](panels-overview.md)
