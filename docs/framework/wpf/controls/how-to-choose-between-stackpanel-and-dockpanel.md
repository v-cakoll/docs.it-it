---
title: 'Procedura: scegliere tra StackPanel e DockPanel'
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
- DockPanel control [WPF], StackPanel control compared to
- StackPanel control [WPF], DockPanel control compared to
- controls [WPF], StackPanel
ms.assetid: f9239086-451f-42e6-81f7-ef89ef349742
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0274a0f078c378a101bdf4a4ae456fd2ce9f4185
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-choose-between-stackpanel-and-dockpanel"></a><span data-ttu-id="6b05c-102">Procedura: scegliere tra StackPanel e DockPanel</span><span class="sxs-lookup"><span data-stu-id="6b05c-102">How to: Choose Between StackPanel and DockPanel</span></span>
<span data-ttu-id="6b05c-103">In questo esempio viene illustrato come scegliere tra l'utilizzo di un <xref:System.Windows.Controls.StackPanel> o <xref:System.Windows.Controls.DockPanel> per lo stack di contenuto in un <xref:System.Windows.Controls.Panel>.</span><span class="sxs-lookup"><span data-stu-id="6b05c-103">This example shows how to choose between using a <xref:System.Windows.Controls.StackPanel> or a <xref:System.Windows.Controls.DockPanel> when you stack content in a <xref:System.Windows.Controls.Panel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b05c-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="6b05c-104">Example</span></span>  
 <span data-ttu-id="6b05c-105">Anche se è possibile utilizzare <xref:System.Windows.Controls.DockPanel> o <xref:System.Windows.Controls.StackPanel> per stack di elementi figlio, i due controlli non producono sempre gli stessi risultati.</span><span class="sxs-lookup"><span data-stu-id="6b05c-105">Although you can use either <xref:System.Windows.Controls.DockPanel> or <xref:System.Windows.Controls.StackPanel> to stack child elements, the two controls do not always produce the same results.</span></span> <span data-ttu-id="6b05c-106">Ad esempio, l'ordine che si posizionano gli elementi figlio può influenzare le dimensioni degli elementi figlio in un <xref:System.Windows.Controls.DockPanel> ma non in un <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="6b05c-106">For example, the order that you place child elements can affect the size of child elements in a <xref:System.Windows.Controls.DockPanel> but not in a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="6b05c-107">Si verifica un comportamento diverso perché <xref:System.Windows.Controls.StackPanel> misura la direzione dello stack in corrispondenza <xref:System.Double>.<xref:System.Double.PositiveInfinity>; tuttavia, <xref:System.Windows.Controls.DockPanel> misura solo le dimensioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="6b05c-107">This different behavior occurs because <xref:System.Windows.Controls.StackPanel> measures in the direction of stacking at <xref:System.Double>.<xref:System.Double.PositiveInfinity>; however, <xref:System.Windows.Controls.DockPanel> measures only the available size.</span></span>  
  
 <span data-ttu-id="6b05c-108">Nell'esempio seguente viene illustrata questa differenza fondamentale tra <xref:System.Windows.Controls.DockPanel> e <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="6b05c-108">The following example demonstrates this key difference between <xref:System.Windows.Controls.DockPanel> and <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
 [!code-cpp[StackPanelOvw4#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6b05c-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b05c-109">See Also</span></span>  
 <xref:System.Windows.Controls.StackPanel>  
 <xref:System.Windows.Controls.DockPanel>  
 [<span data-ttu-id="6b05c-110">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="6b05c-110">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
