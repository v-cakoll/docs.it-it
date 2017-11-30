---
title: 'Procedura: modificare il colore di un elemento utilizzando eventi di stato attivo'
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
helpviewer_keywords:
- focus events [WPF], changing element color for
- colors of elements [WPF], changing
- elements [WPF], changing color of
ms.assetid: 7e246802-3625-47a7-ae9d-c8a2a40fd040
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 64b1b788ddebe77704a7d34f31ad82b10da34a5a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-change-the-color-of-an-element-using-focus-events"></a><span data-ttu-id="3192f-102">Procedura: modificare il colore di un elemento utilizzando eventi di stato attivo</span><span class="sxs-lookup"><span data-stu-id="3192f-102">How to: Change the Color of an Element Using Focus Events</span></span>
<span data-ttu-id="3192f-103">In questo esempio viene illustrato come modificare il colore di un elemento quando riceve e perde lo stato attivo tramite il <xref:System.Windows.UIElement.GotFocus> e <xref:System.Windows.UIElement.LostFocus> eventi.</span><span class="sxs-lookup"><span data-stu-id="3192f-103">This example shows how to change the color of an element when it gains and loses focus by using the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> events.</span></span>  
  
 <span data-ttu-id="3192f-104">In questo esempio è costituito un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file e un file code-behind.</span><span class="sxs-lookup"><span data-stu-id="3192f-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3192f-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="3192f-105">Example</span></span>  
 <span data-ttu-id="3192f-106">Le operazioni seguenti [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] viene creata l'interfaccia utente, costituita da due <xref:System.Windows.Controls.Button> degli oggetti e i gestori eventi per il <xref:System.Windows.UIElement.GotFocus> e <xref:System.Windows.UIElement.LostFocus> eventi per il <xref:System.Windows.Controls.Button> oggetti.</span><span class="sxs-lookup"><span data-stu-id="3192f-106">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the user interface, which consists of two <xref:System.Windows.Controls.Button> objects, and attaches event handlers for the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> events to the <xref:System.Windows.Controls.Button> objects.</span></span>  
  
 [!code-xaml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 <span data-ttu-id="3192f-107">Il codice seguente crea il <xref:System.Windows.UIElement.GotFocus> e <xref:System.Windows.UIElement.LostFocus> gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="3192f-107">The following code behind creates the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> event handlers.</span></span>  <span data-ttu-id="3192f-108">Quando il <xref:System.Windows.Controls.Button> riceve lo stato attivo, il <xref:System.Windows.Controls.Control.Background%2A> del <xref:System.Windows.Controls.Button> diventa rosso.</span><span class="sxs-lookup"><span data-stu-id="3192f-108">When the <xref:System.Windows.Controls.Button> gains keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> of the <xref:System.Windows.Controls.Button> is changed to red.</span></span>  <span data-ttu-id="3192f-109">Quando il <xref:System.Windows.Controls.Button> perde lo stato attivo della tastiera, il <xref:System.Windows.Controls.Control.Background%2A> del <xref:System.Windows.Controls.Button> ritorna bianco.</span><span class="sxs-lookup"><span data-stu-id="3192f-109">When the <xref:System.Windows.Controls.Button> loses keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> of the <xref:System.Windows.Controls.Button> is changed back to white.</span></span>  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## <a name="see-also"></a><span data-ttu-id="3192f-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3192f-110">See Also</span></span>  
 [<span data-ttu-id="3192f-111">Cenni preliminari sull'input</span><span class="sxs-lookup"><span data-stu-id="3192f-111">Input Overview</span></span>](../../../../docs/framework/wpf/advanced/input-overview.md)
