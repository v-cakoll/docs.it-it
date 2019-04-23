---
title: 'Procedura: Ottenere o impostare un valore Dock'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dock values [WPF], setting
- Dock values [WPF], getting
ms.assetid: fcf4ab8a-c7cd-4835-8d04-de1c999ab4a8
ms.openlocfilehash: fb6c8a7d62aa09a6e1d82cb4079d1425a7f39f8c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59160739"
---
# <a name="how-to-get-or-set-a-dock-value"></a><span data-ttu-id="54ca3-102">Procedura: Ottenere o impostare un valore Dock</span><span class="sxs-lookup"><span data-stu-id="54ca3-102">How to: Get or Set a Dock Value</span></span>
<span data-ttu-id="54ca3-103">Nell'esempio seguente viene illustrato come assegnare un <xref:System.Windows.Controls.Dock> valore per un oggetto.</span><span class="sxs-lookup"><span data-stu-id="54ca3-103">The following example shows how to assign a <xref:System.Windows.Controls.Dock> value for an object.</span></span> <span data-ttu-id="54ca3-104">L'esempio Usa la <xref:System.Windows.Controls.DockPanel.GetDock%2A> e <xref:System.Windows.Controls.DockPanel.SetDock%2A> metodi <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="54ca3-104">The example uses the <xref:System.Windows.Controls.DockPanel.GetDock%2A> and <xref:System.Windows.Controls.DockPanel.SetDock%2A> methods of <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54ca3-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="54ca3-105">Example</span></span>  
 <span data-ttu-id="54ca3-106">L'esempio crea un'istanza del <xref:System.Windows.Controls.TextBlock> elemento `txt1`e assegna un <xref:System.Windows.Controls.Dock> pari a `Top` utilizzando il <xref:System.Windows.Controls.DockPanel.SetDock%2A> metodo di <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="54ca3-106">The example creates an instance of the <xref:System.Windows.Controls.TextBlock> element, `txt1`, and assigns a <xref:System.Windows.Controls.Dock> value of `Top` by using the <xref:System.Windows.Controls.DockPanel.SetDock%2A> method of <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="54ca3-107">Aggiunge quindi il valore del <xref:System.Windows.Controls.Dock> proprietà per il <xref:System.Windows.Controls.TextBlock.Text%2A> del <xref:System.Windows.Controls.TextBlock> elemento usando la <xref:System.Windows.Controls.DockPanel.GetDock%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="54ca3-107">It then appends the value of the <xref:System.Windows.Controls.Dock> property to the <xref:System.Windows.Controls.TextBlock.Text%2A> of the <xref:System.Windows.Controls.TextBlock> element by using the <xref:System.Windows.Controls.DockPanel.GetDock%2A> method.</span></span> <span data-ttu-id="54ca3-108">Infine, l'esempio aggiunge il <xref:System.Windows.Controls.TextBlock> elemento padre <xref:System.Windows.Controls.DockPanel>, `dp1`.</span><span class="sxs-lookup"><span data-stu-id="54ca3-108">Finally, the example adds the <xref:System.Windows.Controls.TextBlock> element to the parent <xref:System.Windows.Controls.DockPanel>, `dp1`.</span></span>  
  
 [!code-csharp[DockPanelSetDock#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelSetDock/CSharp/DockPanel_SetDock.cs#1)]
 [!code-vb[DockPanelSetDock#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelSetDock/VisualBasic/DockPanel_SetDock.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="54ca3-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54ca3-109">See also</span></span>

- <xref:System.Windows.Controls.DockPanel>
- <xref:System.Windows.Controls.DockPanel.GetDock%2A>
- <xref:System.Windows.Controls.DockPanel.SetDock%2A>
- [<span data-ttu-id="54ca3-110">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="54ca3-110">Panels Overview</span></span>](panels-overview.md)
