---
title: Trovare un elemento di automazione interfaccia utente per l'elemento di un elenco
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items, finding elements for
- elements, finding for list items
- UI Automation, finding elements for List items
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
ms.openlocfilehash: 2b9fb1ffe4b20074de66afe6d418a7cf5d39be0c
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71043721"
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a><span data-ttu-id="8e74c-102">Trovare un elemento di automazione interfaccia utente per l'elemento di un elenco</span><span class="sxs-lookup"><span data-stu-id="8e74c-102">Find a UI Automation Element for a List Item</span></span>
> [!NOTE]
> <span data-ttu-id="8e74c-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="8e74c-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="8e74c-104">Per informazioni aggiornate su, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]vedere [API di automazione di Windows: Automazione](https://go.microsoft.com/fwlink/?LinkID=156746)interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="8e74c-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="8e74c-105">In questo argomento viene illustrato come recuperare <xref:System.Windows.Automation.AutomationElement> un oggetto per un elemento all'interno di un elenco quando l'indice dell'elemento è noto.</span><span class="sxs-lookup"><span data-stu-id="8e74c-105">This topic shows how to retrieve an <xref:System.Windows.Automation.AutomationElement> for an item within a list when the index of the item is known.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e74c-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="8e74c-106">Example</span></span>  
 <span data-ttu-id="8e74c-107">Nell'esempio seguente vengono illustrati due modi per recuperare un elemento specificato da un elenco, uno <xref:System.Windows.Automation.TreeWalker> usando e l'altro <xref:System.Windows.Automation.AutomationElement.FindAll%2A>usando.</span><span class="sxs-lookup"><span data-stu-id="8e74c-107">The following example shows two ways of retrieving a specified item from a list, one using <xref:System.Windows.Automation.TreeWalker> and the other using <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.</span></span>  
  
 <span data-ttu-id="8e74c-108">La prima tecnica tende a essere più veloce [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] per i controlli, ma la seconda è più veloce per i controlli Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="8e74c-108">The first technique tends to be faster for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls, but the second is faster for Windows Presentation Foundation (WPF) controls.</span></span>  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a><span data-ttu-id="8e74c-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e74c-109">See also</span></span>

- [<span data-ttu-id="8e74c-110">Ottenere elementi di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="8e74c-110">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
