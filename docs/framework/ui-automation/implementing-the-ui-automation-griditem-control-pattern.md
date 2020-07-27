---
title: Implementazione del pattern di controllo GridItem di automazione interfaccia utente
description: Informazioni sulle linee guida e le convenzioni per implementare il pattern di controllo GridItemPattern per gli elementi della griglia nell'automazione interfaccia utente. Vedere Membri obbligatori per IGridItemProvider.
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, GridItem
- UI Automation GridItem control pattern
- GridItem control pattern
ms.assetid: bffbae08-fe2a-42fd-ab84-f37187518916
ms.openlocfilehash: e0a0c616f3f0cf9bc091e4fbb496d71ab8550bd3
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165816"
---
# <a name="implementing-the-ui-automation-griditem-control-pattern"></a><span data-ttu-id="80e8d-104">Implementazione del pattern di controllo GridItem di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="80e8d-104">Implementing the UI Automation GridItem Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="80e8d-105">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="80e8d-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="80e8d-106">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="80e8d-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="80e8d-107">In questo argomento vengono presentate le linee guida e le convenzioni per l'implementazione di <xref:System.Windows.Automation.Provider.IGridItemProvider>, incluse le informazioni relative alle proprietà.</span><span class="sxs-lookup"><span data-stu-id="80e8d-107">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>, including information about properties.</span></span> <span data-ttu-id="80e8d-108">Alla fine della panoramica sono elencati collegamenti a ulteriore materiale di riferimento.</span><span class="sxs-lookup"><span data-stu-id="80e8d-108">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="80e8d-109">Il pattern di controllo <xref:System.Windows.Automation.GridItemPattern> viene usato per supportare singoli controlli figlio di contenitori che implementano <xref:System.Windows.Automation.Provider.IGridProvider>.</span><span class="sxs-lookup"><span data-stu-id="80e8d-109">The <xref:System.Windows.Automation.GridItemPattern> control pattern is used to support individual child controls of containers that implement <xref:System.Windows.Automation.Provider.IGridProvider>.</span></span> <span data-ttu-id="80e8d-110">Per esempi di controlli che implementano questo pattern di controllo, vedere [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="80e8d-110">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="80e8d-111">Linee guida e convenzioni di implementazione</span><span class="sxs-lookup"><span data-stu-id="80e8d-111">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="80e8d-112">Quando si implementa <xref:System.Windows.Automation.Provider.IGridProvider>, tenere presenti le linee guida e le convenzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="80e8d-112">When implementing <xref:System.Windows.Automation.Provider.IGridProvider>, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="80e8d-113">Le coordinate della griglia sono in base zero. Le coordinate della cella in alto a sinistra sono infatti (0, 0).</span><span class="sxs-lookup"><span data-stu-id="80e8d-113">Grid coordinates are zero-based with the upper left cell having coordinates (0, 0).</span></span>  
  
- <span data-ttu-id="80e8d-114">Le celle unite segnaleranno le proprietà <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> e <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> in base alla cella di aggancio sottostante, secondo quanto definito dal provider di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="80e8d-114">Merged cells will report their <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> and <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> properties based on their underlying anchor cell as defined by the UI Automation provider.</span></span> <span data-ttu-id="80e8d-115">In genere si tratterà della riga o della colonna più in alto e più a sinistra.</span><span class="sxs-lookup"><span data-stu-id="80e8d-115">Typically, it will be the topmost and leftmost row or column.</span></span>  
  
- <span data-ttu-id="80e8d-116"><xref:System.Windows.Automation.Provider.IGridItemProvider> non consente di apportare modifiche attive alla griglia, ad esempio l'unione o la separazione di celle.</span><span class="sxs-lookup"><span data-stu-id="80e8d-116"><xref:System.Windows.Automation.Provider.IGridItemProvider> does not provide for active manipulation of the grid such as merging or splitting cells.</span></span>  
  
- <span data-ttu-id="80e8d-117">I controlli che implementano <xref:System.Windows.Automation.Provider.IGridItemProvider> in genere possono essere attraversati (ovvero, il client di automazione interfaccia utente può passare ai controlli adiacenti) usando la tastiera.</span><span class="sxs-lookup"><span data-stu-id="80e8d-117">Controls that implement <xref:System.Windows.Automation.Provider.IGridItemProvider> can typically be traversed (that is, a UI Automation client can move to adjacent controls) by using the keyboard.</span></span>  
  
<a name="Required_Members_for_IGridItemProvider"></a>
## <a name="required-members-for-igriditemprovider"></a><span data-ttu-id="80e8d-118">Membri obbligatori per IGridItemProvider</span><span class="sxs-lookup"><span data-stu-id="80e8d-118">Required Members for IGridItemProvider</span></span>  
 <span data-ttu-id="80e8d-119">Le proprietà e i metodi seguenti sono obbligatori per l'implementazione di <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span><span class="sxs-lookup"><span data-stu-id="80e8d-119">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span></span>  
  
|<span data-ttu-id="80e8d-120">Membri obbligatori</span><span class="sxs-lookup"><span data-stu-id="80e8d-120">Required members</span></span>|<span data-ttu-id="80e8d-121">Tipo di membro</span><span class="sxs-lookup"><span data-stu-id="80e8d-121">Member type</span></span>|<span data-ttu-id="80e8d-122">Note</span><span class="sxs-lookup"><span data-stu-id="80e8d-122">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A>|<span data-ttu-id="80e8d-123">Proprietà</span><span class="sxs-lookup"><span data-stu-id="80e8d-123">Property</span></span>|<span data-ttu-id="80e8d-124">Nessuno</span><span class="sxs-lookup"><span data-stu-id="80e8d-124">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A>|<span data-ttu-id="80e8d-125">Proprietà</span><span class="sxs-lookup"><span data-stu-id="80e8d-125">Property</span></span>|<span data-ttu-id="80e8d-126">Nessuno</span><span class="sxs-lookup"><span data-stu-id="80e8d-126">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.RowSpan%2A>|<span data-ttu-id="80e8d-127">Proprietà</span><span class="sxs-lookup"><span data-stu-id="80e8d-127">Property</span></span>|<span data-ttu-id="80e8d-128">Nessuno</span><span class="sxs-lookup"><span data-stu-id="80e8d-128">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ColumnSpan%2A>|<span data-ttu-id="80e8d-129">Proprietà</span><span class="sxs-lookup"><span data-stu-id="80e8d-129">Property</span></span>|<span data-ttu-id="80e8d-130">Nessuno</span><span class="sxs-lookup"><span data-stu-id="80e8d-130">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ContainingGrid%2A>|<span data-ttu-id="80e8d-131">Proprietà</span><span class="sxs-lookup"><span data-stu-id="80e8d-131">Property</span></span>|<span data-ttu-id="80e8d-132">Nessuno</span><span class="sxs-lookup"><span data-stu-id="80e8d-132">None</span></span>|  
  
 <span data-ttu-id="80e8d-133">Questo pattern di controllo non è associato a metodi o eventi.</span><span class="sxs-lookup"><span data-stu-id="80e8d-133">This control pattern has no associated methods or events.</span></span>  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a><span data-ttu-id="80e8d-134">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="80e8d-134">Exceptions</span></span>  
 <span data-ttu-id="80e8d-135">Questo pattern di controllo non è associato a eccezioni.</span><span class="sxs-lookup"><span data-stu-id="80e8d-135">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80e8d-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80e8d-136">See also</span></span>

- [<span data-ttu-id="80e8d-137">Cenni preliminari sui pattern di controllo per l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="80e8d-137">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="80e8d-138">Supportare pattern di controllo in un provider di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="80e8d-138">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="80e8d-139">Pattern di controllo di automazione interfaccia utente per i client</span><span class="sxs-lookup"><span data-stu-id="80e8d-139">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="80e8d-140">Implementazione del pattern di controllo Grid di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="80e8d-140">Implementing the UI Automation Grid Control Pattern</span></span>](implementing-the-ui-automation-grid-control-pattern.md)
- [<span data-ttu-id="80e8d-141">Panoramica dell'albero di automazione dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="80e8d-141">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="80e8d-142">Utilizzare la memorizzazione nella cache per l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="80e8d-142">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
