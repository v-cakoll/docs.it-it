---
title: Implementazione del pattern di controllo ScrollItem di automazione interfaccia utente
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Scroll Item
- UI Automation, Scroll Item control pattern
- Scroll Item control pattern
ms.assetid: 903bab5c-80c1-44d7-bdc2-0a418893b987
ms.openlocfilehash: c0bb852fa6c117ae8eb2644a0be75f20367b2054
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61983307"
---
# <a name="implementing-the-ui-automation-scrollitem-control-pattern"></a><span data-ttu-id="8123d-102">Implementazione del pattern di controllo ScrollItem di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="8123d-102">Implementing the UI Automation ScrollItem Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="8123d-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="8123d-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="8123d-104">Per informazioni aggiornate sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: Automazione interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="8123d-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="8123d-105">In questo argomento vengono presentate le linee guida e le convenzioni per l'implementazione di <xref:System.Windows.Automation.Provider.IScrollItemProvider>, incluse le informazioni relative a proprietà, metodi ed eventi.</span><span class="sxs-lookup"><span data-stu-id="8123d-105">This topic introduces guidelines and conventions for implementing the <xref:System.Windows.Automation.Provider.IScrollItemProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="8123d-106">Alla fine della panoramica sono elencati collegamenti ad altro materiale di riferimento.</span><span class="sxs-lookup"><span data-stu-id="8123d-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="8123d-107">Il pattern di controllo <xref:System.Windows.Automation.ScrollItemPattern> viene usato per supportare singoli controlli figlio di contenitori che implementano <xref:System.Windows.Automation.Provider.IScrollProvider>.</span><span class="sxs-lookup"><span data-stu-id="8123d-107">The <xref:System.Windows.Automation.ScrollItemPattern> control pattern is used to support individual child controls of containers that implement <xref:System.Windows.Automation.Provider.IScrollProvider>.</span></span> <span data-ttu-id="8123d-108">Questo pattern di controllo funge da canale di comunicazione tra un controllo figlio e il relativo contenitore per assicurarsi che il contenitore possa modificare il contenuto (o l'area) attualmente visibile nel relativo riquadro di visualizzazione per visualizzare il controllo figlio.</span><span class="sxs-lookup"><span data-stu-id="8123d-108">This control pattern acts as a communication channel between a child control and its container to ensure that the container can change the currently visible content (or region) within its viewport to display the child control.</span></span> <span data-ttu-id="8123d-109">Per esempi di controlli che implementano questo pattern di controllo, vedere [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="8123d-109">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="8123d-110">Linee guida e convenzioni di implementazione</span><span class="sxs-lookup"><span data-stu-id="8123d-110">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="8123d-111">Quando si implementa il pattern di controllo ScrollItem, tenere presenti le linee guida e le convenzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8123d-111">When implementing the Scroll Item control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="8123d-112">Gli elementi contenuti in un controllo finestra o area di disegno non devono implementare l'interfaccia IScrollItemProvider.</span><span class="sxs-lookup"><span data-stu-id="8123d-112">Items contained within a Window or Canvas control are not required to implement the IScrollItemProvider interface.</span></span> <span data-ttu-id="8123d-113">In alternativa, tuttavia, devono esporre una posizione valida per <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>.</span><span class="sxs-lookup"><span data-stu-id="8123d-113">As an alternative, however, they must expose a valid location for the <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>.</span></span> <span data-ttu-id="8123d-114">Ciò consentirà a un'applicazione client di automazione interfaccia utente di usare i metodi del pattern di controllo <xref:System.Windows.Automation.ScrollPattern> sul contenitore per visualizzare l'elemento figlio del controllo.</span><span class="sxs-lookup"><span data-stu-id="8123d-114">This will allow a UI Automation client application to use the <xref:System.Windows.Automation.ScrollPattern> control pattern methods on the container to display the child item.</span></span>  
  
<a name="Required_Members_for_IScrollItemProvider"></a>   
## <a name="required-members-for-iscrollitemprovider"></a><span data-ttu-id="8123d-115">Membri obbligatori per IScrollItemProvider</span><span class="sxs-lookup"><span data-stu-id="8123d-115">Required Members for IScrollItemProvider</span></span>  
 <span data-ttu-id="8123d-116">Il metodo seguente è necessario per l'implementazione dell'interfaccia IScrollProvider.</span><span class="sxs-lookup"><span data-stu-id="8123d-116">The following method is required for implementing the IScrollProvider interface.</span></span>  
  
|<span data-ttu-id="8123d-117">Membri obbligatori</span><span class="sxs-lookup"><span data-stu-id="8123d-117">Required members</span></span>|<span data-ttu-id="8123d-118">Tipo di membro</span><span class="sxs-lookup"><span data-stu-id="8123d-118">Member type</span></span>|<span data-ttu-id="8123d-119">Note</span><span class="sxs-lookup"><span data-stu-id="8123d-119">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollItemProvider.ScrollIntoView%2A>|<span data-ttu-id="8123d-120">-Metodo</span><span class="sxs-lookup"><span data-stu-id="8123d-120">-   Method</span></span>|<span data-ttu-id="8123d-121">nessuno</span><span class="sxs-lookup"><span data-stu-id="8123d-121">None</span></span>|  
  
 <span data-ttu-id="8123d-122">Questo pattern di controllo non è associato a proprietà o eventi.</span><span class="sxs-lookup"><span data-stu-id="8123d-122">This control pattern has no associated properties or events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="8123d-123">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="8123d-123">Exceptions</span></span>  
 <span data-ttu-id="8123d-124">I provider devono generare le eccezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="8123d-124">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="8123d-125">Tipo di eccezione</span><span class="sxs-lookup"><span data-stu-id="8123d-125">Exception Type</span></span>|<span data-ttu-id="8123d-126">Condizione</span><span class="sxs-lookup"><span data-stu-id="8123d-126">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<span data-ttu-id="8123d-127">Non è possibile visualizzare un elemento tramite lo scorrimento:</span><span class="sxs-lookup"><span data-stu-id="8123d-127">If an item cannot be scrolled into view:</span></span><br /><br /> -   <xref:System.Windows.Automation.ScrollItemPattern.ScrollIntoView%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="8123d-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8123d-128">See also</span></span>

- [<span data-ttu-id="8123d-129">Panoramica dei pattern di controllo per l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="8123d-129">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="8123d-130">Supportare pattern di controllo in un provider di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="8123d-130">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="8123d-131">Pattern di controllo di automazione interfaccia utente per i client</span><span class="sxs-lookup"><span data-stu-id="8123d-131">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="8123d-132">Panoramica dell'albero di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="8123d-132">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)
- [<span data-ttu-id="8123d-133">Usare la memorizzazione nella cache in automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="8123d-133">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
