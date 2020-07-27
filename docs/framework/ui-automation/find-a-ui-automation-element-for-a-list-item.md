---
title: Trovare un elemento di automazione interfaccia utente per l'elemento di un elenco
description: Vedere un esempio in cui viene illustrato come trovare un elemento di automazione interfaccia utente per un elemento elenco quando l'indice dell'elemento è noto.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items, finding elements for
- elements, finding for list items
- UI Automation, finding elements for List items
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
ms.openlocfilehash: ec6464bc0ec504fd34ed113c9bed1a54a7d4eaec
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168406"
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a><span data-ttu-id="e6ee5-103">Trovare un elemento di automazione interfaccia utente per l'elemento di un elenco</span><span class="sxs-lookup"><span data-stu-id="e6ee5-103">Find a UI Automation Element for a List Item</span></span>
> [!NOTE]
> <span data-ttu-id="e6ee5-104">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="e6ee5-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="e6ee5-105">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="e6ee5-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="e6ee5-106">In questo argomento viene illustrato come recuperare un oggetto <xref:System.Windows.Automation.AutomationElement> per un elemento all'interno di un elenco quando l'indice dell'elemento è noto.</span><span class="sxs-lookup"><span data-stu-id="e6ee5-106">This topic shows how to retrieve an <xref:System.Windows.Automation.AutomationElement> for an item within a list when the index of the item is known.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6ee5-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="e6ee5-107">Example</span></span>  
 <span data-ttu-id="e6ee5-108">Nell'esempio seguente vengono illustrati due modi per recuperare un elemento specificato da un elenco, uno usando <xref:System.Windows.Automation.TreeWalker> e l'altro usando <xref:System.Windows.Automation.AutomationElement.FindAll%2A> .</span><span class="sxs-lookup"><span data-stu-id="e6ee5-108">The following example shows two ways of retrieving a specified item from a list, one using <xref:System.Windows.Automation.TreeWalker> and the other using <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.</span></span>  
  
 <span data-ttu-id="e6ee5-109">La prima tecnica tende a essere più veloce per i controlli Win32, ma la seconda è più veloce per i controlli Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="e6ee5-109">The first technique tends to be faster for Win32 controls, but the second is faster for Windows Presentation Foundation (WPF) controls.</span></span>  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a><span data-ttu-id="e6ee5-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6ee5-110">See also</span></span>

- [<span data-ttu-id="e6ee5-111">Ottenere elementi di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="e6ee5-111">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
