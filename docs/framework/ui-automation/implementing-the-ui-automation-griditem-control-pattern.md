---
title: Implementazione del pattern di controllo GridItem di automazione interfaccia utente
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- control patterns, GridItem
- UI Automation GridItem control pattern
- GridItem control pattern
ms.assetid: bffbae08-fe2a-42fd-ab84-f37187518916
caps.latest.revision: "15"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: daaffd02eaaf7fcb0e64dbcda4bd2ee155163f4f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="implementing-the-ui-automation-griditem-control-pattern"></a><span data-ttu-id="4d0c2-102">Implementazione del pattern di controllo GridItem di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="4d0c2-102">Implementing the UI Automation GridItem Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="4d0c2-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="4d0c2-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="4d0c2-104">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="4d0c2-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="4d0c2-105">Questo argomento vengono presentate le linee guida e convenzioni per l'implementazione <xref:System.Windows.Automation.Provider.IGridItemProvider>, incluse le informazioni sulle proprietà.</span><span class="sxs-lookup"><span data-stu-id="4d0c2-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>, including information about properties.</span></span> <span data-ttu-id="4d0c2-106">Alla fine della panoramica sono elencati collegamenti a ulteriore materiale di riferimento.</span><span class="sxs-lookup"><span data-stu-id="4d0c2-106">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="4d0c2-107">Il <xref:System.Windows.Automation.GridItemPattern> pattern di controllo viene usato per supportare singoli controlli figlio di contenitori che implementano <xref:System.Windows.Automation.Provider.IGridProvider>.</span><span class="sxs-lookup"><span data-stu-id="4d0c2-107">The <xref:System.Windows.Automation.GridItemPattern> control pattern is used to support individual child controls of containers that implement <xref:System.Windows.Automation.Provider.IGridProvider>.</span></span> <span data-ttu-id="4d0c2-108">Per esempi di controlli che implementano questo pattern di controllo, vedere [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="4d0c2-108">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="4d0c2-109">Linee guida e convenzioni di implementazione</span><span class="sxs-lookup"><span data-stu-id="4d0c2-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="4d0c2-110">Quando si implementa <xref:System.Windows.Automation.Provider.IGridProvider>, tenere presente le linee guida e le convenzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d0c2-110">When implementing <xref:System.Windows.Automation.Provider.IGridProvider>, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="4d0c2-111">Le coordinate della griglia sono in base zero. Le coordinate della cella in alto a sinistra sono infatti (0, 0).</span><span class="sxs-lookup"><span data-stu-id="4d0c2-111">Grid coordinates are zero-based with the upper left cell having coordinates (0, 0).</span></span>  
  
-   <span data-ttu-id="4d0c2-112">Celle unite segnaleranno le <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> e <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> proprietà in base alla cella di aggancio sottostante come definito dal provider di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="4d0c2-112">Merged cells will report their <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> and <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> properties based on their underlying anchor cell as defined by the UI Automation provider.</span></span> <span data-ttu-id="4d0c2-113">In genere si tratterà della riga o della colonna più in alto e più a sinistra.</span><span class="sxs-lookup"><span data-stu-id="4d0c2-113">Typically, it will be the topmost and leftmost row or column.</span></span>  
  
-   <span data-ttu-id="4d0c2-114"><xref:System.Windows.Automation.Provider.IGridItemProvider>non consente la modifica attiva della griglia, ad esempio l'unione o di divisione delle celle.</span><span class="sxs-lookup"><span data-stu-id="4d0c2-114"><xref:System.Windows.Automation.Provider.IGridItemProvider> does not provide for active manipulation of the grid such as merging or splitting cells.</span></span>  
  
-   <span data-ttu-id="4d0c2-115">I controlli che implementano <xref:System.Windows.Automation.Provider.IGridItemProvider> in genere può essere attraversato (ovvero, un client di automazione interfaccia utente può spostarsi sui controlli adiacenti) usando la tastiera.</span><span class="sxs-lookup"><span data-stu-id="4d0c2-115">Controls that implement <xref:System.Windows.Automation.Provider.IGridItemProvider> can typically be traversed (that is, a UI Automation client can move to adjacent controls) by using the keyboard.</span></span>  
  
<a name="Required_Members_for_IGridItemProvider"></a>   
## <a name="required-members-for-igriditemprovider"></a><span data-ttu-id="4d0c2-116">Membri obbligatori per IGridItemProvider</span><span class="sxs-lookup"><span data-stu-id="4d0c2-116">Required Members for IGridItemProvider</span></span>  
 <span data-ttu-id="4d0c2-117">Le proprietà e i metodi seguenti sono obbligatori per l'implementazione di <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span><span class="sxs-lookup"><span data-stu-id="4d0c2-117">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span></span>  
  
|<span data-ttu-id="4d0c2-118">Membri obbligatori</span><span class="sxs-lookup"><span data-stu-id="4d0c2-118">Required members</span></span>|<span data-ttu-id="4d0c2-119">Tipo di membro</span><span class="sxs-lookup"><span data-stu-id="4d0c2-119">Member type</span></span>|<span data-ttu-id="4d0c2-120">Note</span><span class="sxs-lookup"><span data-stu-id="4d0c2-120">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A>|<span data-ttu-id="4d0c2-121">Proprietà</span><span class="sxs-lookup"><span data-stu-id="4d0c2-121">Property</span></span>|<span data-ttu-id="4d0c2-122">Nessuna</span><span class="sxs-lookup"><span data-stu-id="4d0c2-122">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A>|<span data-ttu-id="4d0c2-123">Proprietà</span><span class="sxs-lookup"><span data-stu-id="4d0c2-123">Property</span></span>|<span data-ttu-id="4d0c2-124">Nessuna</span><span class="sxs-lookup"><span data-stu-id="4d0c2-124">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.RowSpan%2A>|<span data-ttu-id="4d0c2-125">Proprietà</span><span class="sxs-lookup"><span data-stu-id="4d0c2-125">Property</span></span>|<span data-ttu-id="4d0c2-126">Nessuna</span><span class="sxs-lookup"><span data-stu-id="4d0c2-126">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ColumnSpan%2A>|<span data-ttu-id="4d0c2-127">Proprietà</span><span class="sxs-lookup"><span data-stu-id="4d0c2-127">Property</span></span>|<span data-ttu-id="4d0c2-128">Nessuna</span><span class="sxs-lookup"><span data-stu-id="4d0c2-128">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ContainingGrid%2A>|<span data-ttu-id="4d0c2-129">Proprietà</span><span class="sxs-lookup"><span data-stu-id="4d0c2-129">Property</span></span>|<span data-ttu-id="4d0c2-130">None</span><span class="sxs-lookup"><span data-stu-id="4d0c2-130">None</span></span>|  
  
 <span data-ttu-id="4d0c2-131">Questo pattern di controllo non è associato a metodi o eventi.</span><span class="sxs-lookup"><span data-stu-id="4d0c2-131">This control pattern has no associated methods or events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="4d0c2-132">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="4d0c2-132">Exceptions</span></span>  
 <span data-ttu-id="4d0c2-133">Questo pattern di controllo non è associato a eccezioni.</span><span class="sxs-lookup"><span data-stu-id="4d0c2-133">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d0c2-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d0c2-134">See Also</span></span>  
 [<span data-ttu-id="4d0c2-135">Cenni preliminari sui pattern di controllo automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="4d0c2-135">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="4d0c2-136">Supportare pattern di controllo in un Provider di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="4d0c2-136">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="4d0c2-137">Pattern di controllo di automazione interfaccia utente per i client</span><span class="sxs-lookup"><span data-stu-id="4d0c2-137">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="4d0c2-138">Implementa il Pattern di controllo Grid di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="4d0c2-138">Implementing the UI Automation Grid Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)  
 [<span data-ttu-id="4d0c2-139">Panoramica dell'albero di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="4d0c2-139">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="4d0c2-140">Utilizzare la memorizzazione nella cache in automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="4d0c2-140">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
