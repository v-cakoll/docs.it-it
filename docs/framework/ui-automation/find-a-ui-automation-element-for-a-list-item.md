---
title: Trovare un elemento di automazione interfaccia utente per l'elemento di un elenco
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items, finding elements for
- elements, finding for list items
- UI Automation, finding elements for List items
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
caps.latest.revision: "5"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 16016f5e5b0ab9633f9f8e4ac662838dd7936b18
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a><span data-ttu-id="45e04-102">Trovare un elemento di automazione interfaccia utente per l'elemento di un elenco</span><span class="sxs-lookup"><span data-stu-id="45e04-102">Find a UI Automation Element for a List Item</span></span>
> [!NOTE]
>  <span data-ttu-id="45e04-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="45e04-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="45e04-104">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere l'argomento sull' [API Automazione interfaccia utente di Windows](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="45e04-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="45e04-105">In questo argomento viene illustrato come recuperare un <xref:System.Windows.Automation.AutomationElement> per un elemento all'interno di un elenco quando l'indice dell'elemento è noto.</span><span class="sxs-lookup"><span data-stu-id="45e04-105">This topic shows how to retrieve an <xref:System.Windows.Automation.AutomationElement> for an item within a list when the index of the item is known.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45e04-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="45e04-106">Example</span></span>  
 <span data-ttu-id="45e04-107">L'esempio seguente mostra due modalità di recupero di un elemento specificato da un elenco, uno usando <xref:System.Windows.Automation.TreeWalker> e l'altro tramite <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.</span><span class="sxs-lookup"><span data-stu-id="45e04-107">The following example shows two ways of retrieving a specified item from a list, one using <xref:System.Windows.Automation.TreeWalker> and the other using <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.</span></span>  
  
 <span data-ttu-id="45e04-108">La prima tecnica tende a essere più veloce per [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controlli, mentre la seconda è più veloce per [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)] controlli.</span><span class="sxs-lookup"><span data-stu-id="45e04-108">The first technique tends to be faster for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls, but the second is faster for [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)] controls.</span></span>  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a><span data-ttu-id="45e04-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45e04-109">See Also</span></span>  
 [<span data-ttu-id="45e04-110">Ottenere gli elementi di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="45e04-110">Obtaining UI Automation Elements</span></span>](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)
