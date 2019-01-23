---
title: 'Procedura: Modificare il colore di un elemento utilizzando eventi di stato attivo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus events [WPF], changing element color for
- colors of elements [WPF], changing
- elements [WPF], changing color of
ms.assetid: 7e246802-3625-47a7-ae9d-c8a2a40fd040
ms.openlocfilehash: ad5ba8490f4b98512d539f5ae9c72b03333aca69
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547014"
---
# <a name="how-to-change-the-color-of-an-element-using-focus-events"></a><span data-ttu-id="78da5-102">Procedura: Modificare il colore di un elemento utilizzando eventi di stato attivo</span><span class="sxs-lookup"><span data-stu-id="78da5-102">How to: Change the Color of an Element Using Focus Events</span></span>
<span data-ttu-id="78da5-103">In questo esempio viene illustrato come modificare il colore di un elemento quando si riceve e perde lo stato attivo tramite il <xref:System.Windows.UIElement.GotFocus> e <xref:System.Windows.UIElement.LostFocus> eventi.</span><span class="sxs-lookup"><span data-stu-id="78da5-103">This example shows how to change the color of an element when it gains and loses focus by using the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> events.</span></span>  
  
 <span data-ttu-id="78da5-104">In questo esempio è costituito un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file e un file code-behind.</span><span class="sxs-lookup"><span data-stu-id="78da5-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78da5-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="78da5-105">Example</span></span>  
 <span data-ttu-id="78da5-106">Quanto segue [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] crea l'interfaccia utente, che è costituito da due <xref:System.Windows.Controls.Button> gli oggetti e i gestori eventi per il <xref:System.Windows.UIElement.GotFocus> e <xref:System.Windows.UIElement.LostFocus> eventi per il <xref:System.Windows.Controls.Button> oggetti.</span><span class="sxs-lookup"><span data-stu-id="78da5-106">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the user interface, which consists of two <xref:System.Windows.Controls.Button> objects, and attaches event handlers for the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> events to the <xref:System.Windows.Controls.Button> objects.</span></span>  
  
 [!code-xaml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 <span data-ttu-id="78da5-107">Il codice seguente crea il <xref:System.Windows.UIElement.GotFocus> e <xref:System.Windows.UIElement.LostFocus> gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="78da5-107">The following code behind creates the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> event handlers.</span></span>  <span data-ttu-id="78da5-108">Quando la <xref:System.Windows.Controls.Button> riceve lo stato attivo, il <xref:System.Windows.Controls.Control.Background%2A> del <xref:System.Windows.Controls.Button> viene modificato e impostato su rosso.</span><span class="sxs-lookup"><span data-stu-id="78da5-108">When the <xref:System.Windows.Controls.Button> gains keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> of the <xref:System.Windows.Controls.Button> is changed to red.</span></span>  <span data-ttu-id="78da5-109">Quando la <xref:System.Windows.Controls.Button> perde lo stato attivo della tastiera, il <xref:System.Windows.Controls.Control.Background%2A> del <xref:System.Windows.Controls.Button> viene nuovamente impostato su bianco.</span><span class="sxs-lookup"><span data-stu-id="78da5-109">When the <xref:System.Windows.Controls.Button> loses keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> of the <xref:System.Windows.Controls.Button> is changed back to white.</span></span>  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## <a name="see-also"></a><span data-ttu-id="78da5-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78da5-110">See also</span></span>
- [<span data-ttu-id="78da5-111">Cenni preliminari sull'input</span><span class="sxs-lookup"><span data-stu-id="78da5-111">Input Overview</span></span>](../../../../docs/framework/wpf/advanced/input-overview.md)
