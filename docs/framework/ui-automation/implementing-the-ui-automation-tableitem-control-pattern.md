---
title: Implementazione del pattern di controllo TableItem di automazione interfaccia utente
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- control patterns, Table Item
- UI Automation, Table Item control pattern
- TableItem control pattern
ms.assetid: ac178408-1485-436f-8d3e-eee3bf80cb24
caps.latest.revision: "14"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: caf2a6983ba7a6a993424eadec7d700fb30db57c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="implementing-the-ui-automation-tableitem-control-pattern"></a><span data-ttu-id="dbfa3-102">Implementazione del pattern di controllo TableItem di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="dbfa3-102">Implementing the UI Automation TableItem Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="dbfa3-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="dbfa3-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="dbfa3-104">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere l'argomento sull' [API Automazione interfaccia utente di Windows](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="dbfa3-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="dbfa3-105">Questo argomento vengono presentate le linee guida e convenzioni per l'implementazione <xref:System.Windows.Automation.Provider.ITableItemProvider>, incluse le informazioni relative a eventi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="dbfa3-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITableItemProvider>, including information about events and properties.</span></span> <span data-ttu-id="dbfa3-106">Alla fine della panoramica sono elencati collegamenti a ulteriore materiale di riferimento.</span><span class="sxs-lookup"><span data-stu-id="dbfa3-106">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="dbfa3-107">Il <xref:System.Windows.Automation.TableItemPattern> pattern di controllo viene utilizzato per supportare i controlli figlio di contenitori che implementano <xref:System.Windows.Automation.Provider.ITableProvider>.</span><span class="sxs-lookup"><span data-stu-id="dbfa3-107">The <xref:System.Windows.Automation.TableItemPattern> control pattern is used to support child controls of containers that implement <xref:System.Windows.Automation.Provider.ITableProvider>.</span></span> <span data-ttu-id="dbfa3-108">Viene fornito accesso alle funzionalità delle singole celle dall'implementazione simultanea obbligatoria di <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span><span class="sxs-lookup"><span data-stu-id="dbfa3-108">Access to individual cell functionality is provided by the required concurrent implementation of <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span></span> <span data-ttu-id="dbfa3-109">Questo pattern di controllo è analogo a <xref:System.Windows.Automation.Provider.IGridItemProvider> con la differenza che qualsiasi controllo che implementa <xref:System.Windows.Automation.Provider.ITableItemProvider> deve esporre a livello di codice la relazione tra la singola cella e le relative informazioni di riga e colonna.</span><span class="sxs-lookup"><span data-stu-id="dbfa3-109">This control pattern is analogous to <xref:System.Windows.Automation.Provider.IGridItemProvider> with the distinction that any control implementing <xref:System.Windows.Automation.Provider.ITableItemProvider> must programmatically expose the relationship between the individual cell and its row and column information.</span></span> <span data-ttu-id="dbfa3-110">Per esempi di controlli che implementano questo pattern di controllo, vedere [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="dbfa3-110">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="dbfa3-111">Linee guida e convenzioni di implementazione</span><span class="sxs-lookup"><span data-stu-id="dbfa3-111">Implementation Guidelines and Conventions</span></span>  
  
-   <span data-ttu-id="dbfa3-112">Per la funzionalità di elemento griglia correlata, vedere [che implementa il Pattern di controllo GridItem di automazione interfaccia utente](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="dbfa3-112">For related grid item functionality, see [Implementing the UI Automation GridItem Control Pattern](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md).</span></span>  
  
<a name="Required_Members_for_ITableItemProvider"></a>   
## <a name="required-members-for-itableitemprovider"></a><span data-ttu-id="dbfa3-113">Membri obbligatori per ITableItemProvider</span><span class="sxs-lookup"><span data-stu-id="dbfa3-113">Required Members for ITableItemProvider</span></span>  
  
|<span data-ttu-id="dbfa3-114">Membro obbligatorio</span><span class="sxs-lookup"><span data-stu-id="dbfa3-114">Required member</span></span>|<span data-ttu-id="dbfa3-115">Tipo di membro</span><span class="sxs-lookup"><span data-stu-id="dbfa3-115">Member type</span></span>|<span data-ttu-id="dbfa3-116">Note</span><span class="sxs-lookup"><span data-stu-id="dbfa3-116">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetColumnHeaderItems%2A>|<span data-ttu-id="dbfa3-117">Metodo</span><span class="sxs-lookup"><span data-stu-id="dbfa3-117">Method</span></span>|<span data-ttu-id="dbfa3-118">nessuno</span><span class="sxs-lookup"><span data-stu-id="dbfa3-118">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetRowHeaderItems%2A>|<span data-ttu-id="dbfa3-119">Metodo</span><span class="sxs-lookup"><span data-stu-id="dbfa3-119">Method</span></span>|<span data-ttu-id="dbfa3-120">None</span><span class="sxs-lookup"><span data-stu-id="dbfa3-120">None</span></span>|  
  
 <span data-ttu-id="dbfa3-121">Questo pattern di controllo non è associato a proprietà o eventi.</span><span class="sxs-lookup"><span data-stu-id="dbfa3-121">This control pattern has no associated properties or events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="dbfa3-122">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="dbfa3-122">Exceptions</span></span>  
 <span data-ttu-id="dbfa3-123">Questo pattern di controllo non è associato a eccezioni.</span><span class="sxs-lookup"><span data-stu-id="dbfa3-123">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbfa3-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dbfa3-124">See Also</span></span>  
 [<span data-ttu-id="dbfa3-125">Panoramica dei pattern di controllo per l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="dbfa3-125">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="dbfa3-126">Supportare pattern di controllo in un provider di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="dbfa3-126">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="dbfa3-127">Pattern di controllo di automazione interfaccia utente per i client</span><span class="sxs-lookup"><span data-stu-id="dbfa3-127">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="dbfa3-128">Implementazione del pattern di controllo Table di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="dbfa3-128">Implementing the UI Automation Table Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-table-control-pattern.md)  
 [<span data-ttu-id="dbfa3-129">Implementazione del pattern di controllo GridItem di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="dbfa3-129">Implementing the UI Automation GridItem Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md)  
 [<span data-ttu-id="dbfa3-130">Panoramica dell'albero di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="dbfa3-130">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="dbfa3-131">Usare la memorizzazione nella cache in automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="dbfa3-131">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
