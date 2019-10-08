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
ms.openlocfilehash: 5c59dc5f2f8f26fac69933f9ef641a3a51306619
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004830"
---
# <a name="how-to-change-the-color-of-an-element-using-focus-events"></a><span data-ttu-id="9d960-102">Procedura: Modificare il colore di un elemento utilizzando eventi di stato attivo</span><span class="sxs-lookup"><span data-stu-id="9d960-102">How to: Change the Color of an Element Using Focus Events</span></span>
<span data-ttu-id="9d960-103">In questo esempio viene illustrato come modificare il colore di un elemento quando si ottiene e perde lo stato attivo usando gli eventi <xref:System.Windows.UIElement.GotFocus> e <xref:System.Windows.UIElement.LostFocus>.</span><span class="sxs-lookup"><span data-stu-id="9d960-103">This example shows how to change the color of an element when it gains and loses focus by using the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> events.</span></span>  
  
 <span data-ttu-id="9d960-104">Questo esempio è costituito da un file [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] e da un file code-behind.</span><span class="sxs-lookup"><span data-stu-id="9d960-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d960-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="9d960-105">Example</span></span>  
 <span data-ttu-id="9d960-106">Il codice XAML seguente crea l'interfaccia utente, che è costituita da due oggetti <xref:System.Windows.Controls.Button> e connette i gestori eventi per gli eventi <xref:System.Windows.UIElement.GotFocus> e <xref:System.Windows.UIElement.LostFocus> agli oggetti <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="9d960-106">The following XAML creates the user interface, which consists of two <xref:System.Windows.Controls.Button> objects, and attaches event handlers for the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> events to the <xref:System.Windows.Controls.Button> objects.</span></span>  
  
 [!code-xaml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 <span data-ttu-id="9d960-107">Il codice sottostante seguente consente di creare i gestori eventi <xref:System.Windows.UIElement.GotFocus> e <xref:System.Windows.UIElement.LostFocus>.</span><span class="sxs-lookup"><span data-stu-id="9d960-107">The following code behind creates the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> event handlers.</span></span>  <span data-ttu-id="9d960-108">Quando il <xref:System.Windows.Controls.Button> Ottiene lo stato attivo della tastiera, il <xref:System.Windows.Controls.Control.Background%2A> del <xref:System.Windows.Controls.Button> viene modificato in rosso.</span><span class="sxs-lookup"><span data-stu-id="9d960-108">When the <xref:System.Windows.Controls.Button> gains keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> of the <xref:System.Windows.Controls.Button> is changed to red.</span></span>  <span data-ttu-id="9d960-109">Quando il <xref:System.Windows.Controls.Button> perde lo stato attivo della tastiera, il <xref:System.Windows.Controls.Control.Background%2A> del <xref:System.Windows.Controls.Button> viene modificato di nuovo in bianco.</span><span class="sxs-lookup"><span data-stu-id="9d960-109">When the <xref:System.Windows.Controls.Button> loses keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> of the <xref:System.Windows.Controls.Button> is changed back to white.</span></span>  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## <a name="see-also"></a><span data-ttu-id="9d960-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d960-110">See also</span></span>

- [<span data-ttu-id="9d960-111">Cenni preliminari sull'input</span><span class="sxs-lookup"><span data-stu-id="9d960-111">Input Overview</span></span>](input-overview.md)
