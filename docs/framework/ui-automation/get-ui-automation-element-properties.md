---
title: "Ottenere le proprietà degli elementi di automazione dell'interfaccia utente"
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
- properties, retrieving
- UI Automation, retrieving properties of elements
ms.assetid: 09576b1a-291f-435c-980e-dee32d899ae1
caps.latest.revision: "5"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 2b9e1f24a6384cd052dd7b15c7afb3facac05c57
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="get-ui-automation-element-properties"></a><span data-ttu-id="a6642-102">Ottenere le proprietà degli elementi di automazione dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="a6642-102">Get UI Automation Element Properties</span></span>
> [!NOTE]
>  <span data-ttu-id="a6642-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="a6642-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="a6642-104">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere l'argomento sull' [API Automazione interfaccia utente di Windows](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="a6642-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="a6642-105">In questo argomento viene illustrato come recuperare le proprietà di un [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elemento.</span><span class="sxs-lookup"><span data-stu-id="a6642-105">This topic shows how to retrieve properties of a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element.</span></span>  
  
### <a name="get-a-current-property-value"></a><span data-ttu-id="a6642-106">Ottenere un valore della proprietà corrente</span><span class="sxs-lookup"><span data-stu-id="a6642-106">Get a Current Property Value</span></span>  
  
1.  <span data-ttu-id="a6642-107">Ottenere il <xref:System.Windows.Automation.AutomationElement> la cui proprietà si desidera ottenere.</span><span class="sxs-lookup"><span data-stu-id="a6642-107">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span>  
  
2.  <span data-ttu-id="a6642-108">Chiamare <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, o recuperare il <xref:System.Windows.Automation.AutomationElement.Current%2A> struttura di proprietà e ottenere il valore da uno dei relativi membri.</span><span class="sxs-lookup"><span data-stu-id="a6642-108">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Current%2A> property structure and get the value from one of its members.</span></span>  
  
### <a name="get-a-cached-property-value"></a><span data-ttu-id="a6642-109">Ottiene un valore di proprietà memorizzate nella cache</span><span class="sxs-lookup"><span data-stu-id="a6642-109">Get a Cached Property Value</span></span>  
  
1.  <span data-ttu-id="a6642-110">Ottenere il <xref:System.Windows.Automation.AutomationElement> la cui proprietà si desidera ottenere.</span><span class="sxs-lookup"><span data-stu-id="a6642-110">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span> <span data-ttu-id="a6642-111">La proprietà deve specificata nel <xref:System.Windows.Automation.CacheRequest>.</span><span class="sxs-lookup"><span data-stu-id="a6642-111">The property must have been specified in the <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
2.  <span data-ttu-id="a6642-112">Chiamare <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, o recuperare il <xref:System.Windows.Automation.AutomationElement.Cached%2A> struttura di proprietà e ottenere il valore da uno dei relativi membri.</span><span class="sxs-lookup"><span data-stu-id="a6642-112">Call <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property structure and get the value from one of its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6642-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="a6642-113">Example</span></span>  
 <span data-ttu-id="a6642-114">Nell'esempio seguente illustra vari modi per recuperare le proprietà correnti di un <xref:System.Windows.Automation.AutomationElement>.</span><span class="sxs-lookup"><span data-stu-id="a6642-114">The following example shows various ways to retrieve current properties of an <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a><span data-ttu-id="a6642-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6642-115">See Also</span></span>  
 [<span data-ttu-id="a6642-116">UI Automation Properties for Clients</span><span class="sxs-lookup"><span data-stu-id="a6642-116">UI Automation Properties for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)  
 [<span data-ttu-id="a6642-117">Utilizzare la memorizzazione nella cache in automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="a6642-117">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)  
 [<span data-ttu-id="a6642-118">La memorizzazione nella cache nel client di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="a6642-118">Caching in UI Automation Clients</span></span>](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)
