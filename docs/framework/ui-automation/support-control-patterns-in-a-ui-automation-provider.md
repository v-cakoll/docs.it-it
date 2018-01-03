---
title: Supportare pattern di controllo in un provider di automazione interfaccia utente
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
- control patterns, supporting in UI Automation provider
- UI Automation, supporting control patterns in provider
ms.assetid: 0d635c35-ffa8-4dc8-bbc9-12fcd5445776
caps.latest.revision: "13"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 9e85aa2fe36ad6fab59ae071a662755219ccbbb8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="support-control-patterns-in-a-ui-automation-provider"></a><span data-ttu-id="8387e-102">Supportare pattern di controllo in un provider di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="8387e-102">Support Control Patterns in a UI Automation Provider</span></span>
> [!NOTE]
>  <span data-ttu-id="8387e-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="8387e-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="8387e-104">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere l'argomento sull' [API Automazione interfaccia utente di Windows](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="8387e-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="8387e-105">In questo argomento viene descritto come implementare uno o più pattern di controllo in un provider di automazione interfaccia utente in modo che le applicazioni client possano modificare i controlli e ottenere dati.</span><span class="sxs-lookup"><span data-stu-id="8387e-105">This topic shows how to implement one or more control patterns on a UI Automation provider so that client applications can manipulate controls and get data from them.</span></span>  
  
### <a name="support-control-patterns"></a><span data-ttu-id="8387e-106">Supportare i pattern di controllo</span><span class="sxs-lookup"><span data-stu-id="8387e-106">Support Control Patterns</span></span>  
  
1.  <span data-ttu-id="8387e-107">Implementare le interfacce appropriate per i pattern di controllo che l'elemento deve supportare, ad esempio <xref:System.Windows.Automation.Provider.IInvokeProvider> per <xref:System.Windows.Automation.InvokePattern>.</span><span class="sxs-lookup"><span data-stu-id="8387e-107">Implement the appropriate interfaces for the control patterns that the element should support, such as <xref:System.Windows.Automation.Provider.IInvokeProvider> for <xref:System.Windows.Automation.InvokePattern>.</span></span>  
  
2.  <span data-ttu-id="8387e-108">Restituire l'oggetto che contiene l'implementazione di ogni interfaccia di controllo nell'implementazione di<xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="8387e-108">Return the object containing your implementation of each control interface in your implementation of <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A?displayProperty=nameWithType></span></span>  
  
## <a name="example"></a><span data-ttu-id="8387e-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="8387e-109">Example</span></span>  
 <span data-ttu-id="8387e-110">Nell'esempio seguente viene illustrata un'implementazione di <xref:System.Windows.Automation.Provider.ISelectionProvider> per una casella di riepilogo personalizzata a selezione singola.</span><span class="sxs-lookup"><span data-stu-id="8387e-110">The following example shows an implementation of <xref:System.Windows.Automation.Provider.ISelectionProvider> for a single-selection custom list box.</span></span> <span data-ttu-id="8387e-111">Restituisce tre proprietà e ottiene l'elemento attualmente selezionato.</span><span class="sxs-lookup"><span data-stu-id="8387e-111">It returns three properties and gets the currently selected item.</span></span>  
  
 [!code-csharp[UIAFragmentProvider_snip#119](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListPattern.cs#119)]
 [!code-vb[UIAFragmentProvider_snip#119](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListPattern.vb#119)]  
  
## <a name="example"></a><span data-ttu-id="8387e-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="8387e-112">Example</span></span>  
 <span data-ttu-id="8387e-113">Nell'esempio seguente viene illustrata un'implementazione <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A> che restituisce la classe che implementa <xref:System.Windows.Automation.Provider.ISelectionProvider>.</span><span class="sxs-lookup"><span data-stu-id="8387e-113">The following example shows an implementation of <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A> that returns the class implementing <xref:System.Windows.Automation.Provider.ISelectionProvider>.</span></span> <span data-ttu-id="8387e-114">La maggior parte dei controlli casella di riepilogo supporta anche altri pattern, ma in questo esempio viene restituito un riferimento null (`Nothing` in [!INCLUDE[TLA#tla_visualbnet](../../../includes/tlasharptla-visualbnet-md.md)]) per tutti gli altri identificatori di pattern.</span><span class="sxs-lookup"><span data-stu-id="8387e-114">Most list box controls would support other patterns as well, but in this example a null reference (`Nothing` in [!INCLUDE[TLA#tla_visualbnet](../../../includes/tlasharptla-visualbnet-md.md)]) is returned for all other pattern identifiers.</span></span>  
  
 [!code-csharp[UIAFragmentProvider_snip#120](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#120)]
 [!code-vb[UIAFragmentProvider_snip#120](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#120)]  
  
## <a name="see-also"></a><span data-ttu-id="8387e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8387e-115">See Also</span></span>  
 [<span data-ttu-id="8387e-116">Panoramica dei provider di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="8387e-116">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)  
 [<span data-ttu-id="8387e-117">Implementazione del provider di automazione interfaccia utente lato server</span><span class="sxs-lookup"><span data-stu-id="8387e-117">Server-Side UI Automation Provider Implementation</span></span>](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)
