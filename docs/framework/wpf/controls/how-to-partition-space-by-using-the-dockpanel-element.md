---
title: 'Procedura: partizionare lo spazio utilizzando l''elemento DockPanel'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], partitioning space
- partitioning space [WPF]
ms.assetid: a219b9e5-b205-4438-89b5-0a137ac463ab
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 056aeaf1dfb7db420ce5359849a9a409dcd3fe13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-partition-space-by-using-the-dockpanel-element"></a><span data-ttu-id="80dd3-102">Procedura: partizionare lo spazio utilizzando l'elemento DockPanel</span><span class="sxs-lookup"><span data-stu-id="80dd3-102">How to: Partition Space by Using the DockPanel Element</span></span>
<span data-ttu-id="80dd3-103">Nell'esempio seguente viene creato un semplice [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] framework utilizzando un <xref:System.Windows.Controls.DockPanel> elemento.</span><span class="sxs-lookup"><span data-stu-id="80dd3-103">The following example creates a simple [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] framework using a <xref:System.Windows.Controls.DockPanel> element.</span></span> <span data-ttu-id="80dd3-104">Il <xref:System.Windows.Controls.DockPanel> partiziona lo spazio disponibile per i relativi elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="80dd3-104">The <xref:System.Windows.Controls.DockPanel> partitions available space to its child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80dd3-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="80dd3-105">Example</span></span>  
 <span data-ttu-id="80dd3-106">Questo esempio viene utilizzato il <xref:System.Windows.Controls.DockPanel.Dock%2A> proprietà, che è una proprietà associata, per ancorare due identici <xref:System.Windows.Controls.Border> gli elementi in corrispondenza di <xref:System.Windows.Controls.Dock.Top> dello spazio partizionato.</span><span class="sxs-lookup"><span data-stu-id="80dd3-106">This example uses the <xref:System.Windows.Controls.DockPanel.Dock%2A> property, which is an attached property, to dock two identical <xref:System.Windows.Controls.Border> elements at the <xref:System.Windows.Controls.Dock.Top> of the partitioned space.</span></span> <span data-ttu-id="80dd3-107">Una terza <xref:System.Windows.Controls.Border> per l'elemento è ancorato il <xref:System.Windows.Controls.Dock.Left>, con larghezza impostata su 200 pixel.</span><span class="sxs-lookup"><span data-stu-id="80dd3-107">A third <xref:System.Windows.Controls.Border> element is docked to the <xref:System.Windows.Controls.Dock.Left>, with its width set to 200 pixels.</span></span> <span data-ttu-id="80dd3-108">Un quarto <xref:System.Windows.Controls.Border> è ancorato il <xref:System.Windows.Controls.Dock.Bottom> dello schermo.</span><span class="sxs-lookup"><span data-stu-id="80dd3-108">A fourth <xref:System.Windows.Controls.Border> is docked to the <xref:System.Windows.Controls.Dock.Bottom> of the screen.</span></span> <span data-ttu-id="80dd3-109">L'ultimo <xref:System.Windows.Controls.Border> elemento riempie automaticamente lo spazio rimanente.</span><span class="sxs-lookup"><span data-stu-id="80dd3-109">The last <xref:System.Windows.Controls.Border> element automatically fills the remaining space.</span></span>  
  
 [!code-cpp[DockPanelOvwSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
>  <span data-ttu-id="80dd3-110">Per impostazione predefinita, l'ultimo elemento figlio di un <xref:System.Windows.Controls.DockPanel> elemento riempie il rimanente spazio non allocato.</span><span class="sxs-lookup"><span data-stu-id="80dd3-110">By default, the last child of a <xref:System.Windows.Controls.DockPanel> element fills the remaining unallocated space.</span></span> <span data-ttu-id="80dd3-111">Se non si desidera questo comportamento, impostare `LastChildFill="False"`.</span><span class="sxs-lookup"><span data-stu-id="80dd3-111">If you do not want this behavior, set `LastChildFill="False"`.</span></span>  
  
 <span data-ttu-id="80dd3-112">L'applicazione compilata crea una nuova interfaccia utente analoga alla seguente.</span><span class="sxs-lookup"><span data-stu-id="80dd3-112">The compiled application yields a new UI that looks like this.</span></span>  
  
 <span data-ttu-id="80dd3-113">![Scenario DockPanel tipico.](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span><span class="sxs-lookup"><span data-stu-id="80dd3-113">![A typical DockPanel scenario.](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80dd3-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80dd3-114">See Also</span></span>  
 <xref:System.Windows.Controls.DockPanel>  
 [<span data-ttu-id="80dd3-115">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="80dd3-115">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
