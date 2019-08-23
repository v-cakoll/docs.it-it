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
ms.openlocfilehash: 8987526a572d3c9a239885407c19bd1ad3674f0e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968983"
---
# <a name="get-supported-ui-automation-control-patterns"></a><span data-ttu-id="171ac-102">Ottenere pattern di controllo supportati per automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="171ac-102">Get Supported UI Automation Control Patterns</span></span>
> [!NOTE]
> <span data-ttu-id="171ac-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="171ac-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="171ac-104">Per informazioni aggiornate su, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]vedere [API di automazione di Windows: Automazione](https://go.microsoft.com/fwlink/?LinkID=156746)interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="171ac-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="171ac-105">In questo argomento viene illustrato come recuperare oggetti del pattern di controllo dagli elementi di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="171ac-105">This topic shows how to retrieve control pattern objects from [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elements.</span></span>  
  
### <a name="obtain-all-control-patterns"></a><span data-ttu-id="171ac-106">Ottenere tutti i pattern di controllo</span><span class="sxs-lookup"><span data-stu-id="171ac-106">Obtain All Control Patterns</span></span>  
  
1. <span data-ttu-id="171ac-107">Ottenere <xref:System.Windows.Automation.AutomationElement> contenente i pattern di controllo interessati.</span><span class="sxs-lookup"><span data-stu-id="171ac-107">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2. <span data-ttu-id="171ac-108">Chiamare <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> per ottenere tutti i pattern di controllo dall'elemento.</span><span class="sxs-lookup"><span data-stu-id="171ac-108">Call <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> to get all control patterns from the element.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="171ac-109">È consigliabile che un client non usi <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>.</span><span class="sxs-lookup"><span data-stu-id="171ac-109">It is strongly recommended that a client not use <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>.</span></span> <span data-ttu-id="171ac-110">Le prestazioni possono venire influenzate in modo significativo poiché questo metodo chiama <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> internamente per ogni pattern di controllo esistente.</span><span class="sxs-lookup"><span data-stu-id="171ac-110">Performance can be severely affected as this method calls <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> internally for each existing control pattern.</span></span> <span data-ttu-id="171ac-111">Se possibile, un client deve chiamare <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> per i principali pattern di interesse.</span><span class="sxs-lookup"><span data-stu-id="171ac-111">If possible, a client should call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> for the key patterns of interest.</span></span>  
  
### <a name="obtain-a-specific-control-pattern"></a><span data-ttu-id="171ac-112">Ottenere un pattern di controllo specifico</span><span class="sxs-lookup"><span data-stu-id="171ac-112">Obtain a Specific Control Pattern</span></span>  
  
1. <span data-ttu-id="171ac-113">Ottenere <xref:System.Windows.Automation.AutomationElement> contenente i pattern di controllo interessati.</span><span class="sxs-lookup"><span data-stu-id="171ac-113">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2. <span data-ttu-id="171ac-114">Chiamare <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> o <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> per eseguire query per un pattern specifico.</span><span class="sxs-lookup"><span data-stu-id="171ac-114">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> or <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> to query for a specific pattern.</span></span> <span data-ttu-id="171ac-115">Questi metodi sono simili, ma se il pattern non viene trovato, <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> genera un'eccezione e <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="171ac-115">These methods are similar, but if the pattern is not found, <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> raises an exception, and <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> returns `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="171ac-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="171ac-116">Example</span></span>  
 <span data-ttu-id="171ac-117">Nell'esempio seguente viene recuperato un <xref:System.Windows.Automation.AutomationElement> per una voce di elenco e viene ottenuto un <xref:System.Windows.Automation.SelectionItemPattern> da tale elemento.</span><span class="sxs-lookup"><span data-stu-id="171ac-117">The following example retrieves an <xref:System.Windows.Automation.AutomationElement> for a list item and obtains a <xref:System.Windows.Automation.SelectionItemPattern> from that element.</span></span>  
  
 [!code-csharp[UIAClient_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#103)]
 [!code-vb[UIAClient_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="171ac-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="171ac-118">See also</span></span>

- [<span data-ttu-id="171ac-119">Pattern di controllo di automazione interfaccia utente per i client</span><span class="sxs-lookup"><span data-stu-id="171ac-119">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
