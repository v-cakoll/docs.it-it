---
title: Ottenere le proprietà degli elementi di automazione dell'interfaccia utente
description: Vedere le istruzioni e un esempio che illustra come recuperare le proprietà correnti o memorizzate nella cache di un elemento di automazione interfaccia utente.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties, retrieving
- UI Automation, retrieving properties of elements
ms.assetid: 09576b1a-291f-435c-980e-dee32d899ae1
ms.openlocfilehash: 277822c9d89046bfbad50df16bce83da7dd45b3b
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164106"
---
# <a name="get-ui-automation-element-properties"></a><span data-ttu-id="db838-103">Ottenere le proprietà degli elementi di automazione dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="db838-103">Get UI Automation Element Properties</span></span>
> [!NOTE]
> <span data-ttu-id="db838-104">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="db838-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="db838-105">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="db838-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="db838-106">In questo argomento viene illustrato come recuperare le proprietà di un [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elemento.</span><span class="sxs-lookup"><span data-stu-id="db838-106">This topic shows how to retrieve properties of a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element.</span></span>  
  
### <a name="get-a-current-property-value"></a><span data-ttu-id="db838-107">Ottenere un valore della proprietà corrente</span><span class="sxs-lookup"><span data-stu-id="db838-107">Get a Current Property Value</span></span>  
  
1. <span data-ttu-id="db838-108">Ottenere l'oggetto <xref:System.Windows.Automation.AutomationElement> di cui si desidera ottenere la proprietà.</span><span class="sxs-lookup"><span data-stu-id="db838-108">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span>  
  
2. <span data-ttu-id="db838-109">Chiamare <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> o recuperare la <xref:System.Windows.Automation.AutomationElement.Current%2A> struttura di proprietà e ottenere il valore da uno dei relativi membri.</span><span class="sxs-lookup"><span data-stu-id="db838-109">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Current%2A> property structure and get the value from one of its members.</span></span>  
  
### <a name="get-a-cached-property-value"></a><span data-ttu-id="db838-110">Ottenere un valore della proprietà memorizzato nella cache</span><span class="sxs-lookup"><span data-stu-id="db838-110">Get a Cached Property Value</span></span>  
  
1. <span data-ttu-id="db838-111">Ottenere l'oggetto <xref:System.Windows.Automation.AutomationElement> di cui si desidera ottenere la proprietà.</span><span class="sxs-lookup"><span data-stu-id="db838-111">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span> <span data-ttu-id="db838-112">È necessario specificare la proprietà in <xref:System.Windows.Automation.CacheRequest> .</span><span class="sxs-lookup"><span data-stu-id="db838-112">The property must have been specified in the <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
2. <span data-ttu-id="db838-113">Chiamare <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A> o recuperare la <xref:System.Windows.Automation.AutomationElement.Cached%2A> struttura di proprietà e ottenere il valore da uno dei relativi membri.</span><span class="sxs-lookup"><span data-stu-id="db838-113">Call <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property structure and get the value from one of its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db838-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="db838-114">Example</span></span>  
 <span data-ttu-id="db838-115">Nell'esempio seguente vengono illustrati vari modi per recuperare le proprietà correnti di un oggetto <xref:System.Windows.Automation.AutomationElement> .</span><span class="sxs-lookup"><span data-stu-id="db838-115">The following example shows various ways to retrieve current properties of an <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a><span data-ttu-id="db838-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db838-116">See also</span></span>

- [<span data-ttu-id="db838-117">Proprietà di automazione interfaccia utente per i client</span><span class="sxs-lookup"><span data-stu-id="db838-117">UI Automation Properties for Clients</span></span>](ui-automation-properties-for-clients.md)
- [<span data-ttu-id="db838-118">Utilizzare la memorizzazione nella cache per l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="db838-118">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
- [<span data-ttu-id="db838-119">Memorizzazione nella cache dei client di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="db838-119">Caching in UI Automation Clients</span></span>](caching-in-ui-automation-clients.md)
