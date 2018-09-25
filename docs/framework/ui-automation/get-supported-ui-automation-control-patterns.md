---
title: Ottenere pattern di controllo supportati per automazione interfaccia utente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control patterns, getting
- UI Automation, getting control patterns
- getting, control patterns
ms.assetid: 006c54c9-50bf-48d9-a855-9d62eb95603a
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: d948ff2f71ff7d4335cacc0fa3815dd75af4ad45
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47115048"
---
# <a name="get-supported-ui-automation-control-patterns"></a><span data-ttu-id="93ef8-102">Ottenere pattern di controllo supportati per automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="93ef8-102">Get Supported UI Automation Control Patterns</span></span>
> [!NOTE]
>  <span data-ttu-id="93ef8-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="93ef8-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="93ef8-104">Per informazioni aggiornate sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione dell'interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="93ef8-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="93ef8-105">Questo argomento viene illustrato come recuperare gli oggetti pattern di controllo da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elementi.</span><span class="sxs-lookup"><span data-stu-id="93ef8-105">This topic shows how to retrieve control pattern objects from [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elements.</span></span>  
  
### <a name="obtain-all-control-patterns"></a><span data-ttu-id="93ef8-106">Ottenere tutti i pattern di controllo</span><span class="sxs-lookup"><span data-stu-id="93ef8-106">Obtain All Control Patterns</span></span>  
  
1.  <span data-ttu-id="93ef8-107">Ottenere il <xref:System.Windows.Automation.AutomationElement> pattern di controllo cui si è interessati.</span><span class="sxs-lookup"><span data-stu-id="93ef8-107">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2.  <span data-ttu-id="93ef8-108">Chiamare <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> per ottenere tutti i pattern di controllo dall'elemento.</span><span class="sxs-lookup"><span data-stu-id="93ef8-108">Call <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> to get all control patterns from the element.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="93ef8-109">È consigliabile che un client non usi <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>.</span><span class="sxs-lookup"><span data-stu-id="93ef8-109">It is strongly recommended that a client not use <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>.</span></span> <span data-ttu-id="93ef8-110">Prestazioni possono essere influenzate gravi poiché questo metodo chiama <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> internamente per ogni pattern di controllo esistente.</span><span class="sxs-lookup"><span data-stu-id="93ef8-110">Performance can be severely affected as this method calls <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> internally for each existing control pattern.</span></span> <span data-ttu-id="93ef8-111">Se possibile, un client deve chiamare <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> per i principali pattern di interesse.</span><span class="sxs-lookup"><span data-stu-id="93ef8-111">If possible, a client should call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> for the key patterns of interest.</span></span>  
  
### <a name="obtain-a-specific-control-pattern"></a><span data-ttu-id="93ef8-112">Ottenere un pattern di controllo specifico</span><span class="sxs-lookup"><span data-stu-id="93ef8-112">Obtain a Specific Control Pattern</span></span>  
  
1.  <span data-ttu-id="93ef8-113">Ottenere il <xref:System.Windows.Automation.AutomationElement> pattern di controllo cui si è interessati.</span><span class="sxs-lookup"><span data-stu-id="93ef8-113">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2.  <span data-ttu-id="93ef8-114">Chiamare <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> o <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> per eseguire query per un modello specifico.</span><span class="sxs-lookup"><span data-stu-id="93ef8-114">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> or <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> to query for a specific pattern.</span></span> <span data-ttu-id="93ef8-115">Questi metodi sono simili, se il modello non viene trovato, tuttavia <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> genera un'eccezione, e <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="93ef8-115">These methods are similar, but if the pattern is not found, <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> raises an exception, and <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> returns `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93ef8-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="93ef8-116">Example</span></span>  
 <span data-ttu-id="93ef8-117">Nell'esempio seguente recupera un' <xref:System.Windows.Automation.AutomationElement> per un elemento dell'elenco e ottiene un <xref:System.Windows.Automation.SelectionItemPattern> da tale elemento.</span><span class="sxs-lookup"><span data-stu-id="93ef8-117">The following example retrieves an <xref:System.Windows.Automation.AutomationElement> for a list item and obtains a <xref:System.Windows.Automation.SelectionItemPattern> from that element.</span></span>  
  
 [!code-csharp[UIAClient_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#103)]
 [!code-vb[UIAClient_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="93ef8-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93ef8-118">See Also</span></span>  
 [<span data-ttu-id="93ef8-119">Pattern di controllo di automazione interfaccia utente per i client</span><span class="sxs-lookup"><span data-stu-id="93ef8-119">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
