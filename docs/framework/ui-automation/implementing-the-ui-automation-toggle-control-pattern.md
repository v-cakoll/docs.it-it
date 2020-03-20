---
title: Implementazione del pattern di controllo Toggle di automazione interfaccia utente
ms.date: 03/30/2017
helpviewer_keywords:
- Toggle control pattern
- control patterns, Toggle
- UI Automation, Toggle control pattern
ms.assetid: 3cfe875f-b0c0-413d-9703-5f14e6a1a30e
ms.openlocfilehash: 5f64842d31d46af3d648b9b570d1cfb210e2910a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180056"
---
# <a name="implementing-the-ui-automation-toggle-control-pattern"></a><span data-ttu-id="bcbb7-102">Implementazione del pattern di controllo Toggle di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="bcbb7-102">Implementing the UI Automation Toggle Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="bcbb7-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="bcbb7-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="bcbb7-104">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="bcbb7-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="bcbb7-105">In questo argomento vengono presentate le linee guida e le convenzioni per l'implementazione di <xref:System.Windows.Automation.Provider.IToggleProvider>, incluse le informazioni relative a metodi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="bcbb7-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IToggleProvider>, including information about methods and properties.</span></span> <span data-ttu-id="bcbb7-106">Alla fine della panoramica sono elencati collegamenti ad altro materiale di riferimento.</span><span class="sxs-lookup"><span data-stu-id="bcbb7-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="bcbb7-107">Il pattern di controllo <xref:System.Windows.Automation.TogglePattern> viene usato per supportare i controlli che possono scorrere un insieme di stati e gestire uno stato impostato.</span><span class="sxs-lookup"><span data-stu-id="bcbb7-107">The <xref:System.Windows.Automation.TogglePattern> control pattern is used to support controls that can cycle through a set of states and maintain a state once set.</span></span> <span data-ttu-id="bcbb7-108">Per esempi di controlli che implementano questo pattern di controllo, vedere [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="bcbb7-108">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="bcbb7-109">Linee guida e convenzioni di implementazione</span><span class="sxs-lookup"><span data-stu-id="bcbb7-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="bcbb7-110">Quando si implementa il pattern di controllo Toggle, tenere presenti le linee guida e le convenzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bcbb7-110">When implementing the Toggle control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="bcbb7-111">I controlli che, una volta attivati, non mantengono lo stato, ad esempio pulsanti, pulsanti della barra degli strumenti e collegamenti ipertestuali, devono invece implementare <xref:System.Windows.Automation.Provider.IInvokeProvider> .</span><span class="sxs-lookup"><span data-stu-id="bcbb7-111">Controls that do not maintain state when activated, such as buttons, toolbar buttons, and hyperlinks, must implement <xref:System.Windows.Automation.Provider.IInvokeProvider> instead.</span></span>  
  
- <span data-ttu-id="bcbb7-112">Un controllo deve scorrere i relativi <xref:System.Windows.Automation.ToggleState> nell'ordine seguente: <xref:System.Windows.Automation.ToggleState.On>, <xref:System.Windows.Automation.ToggleState.Off> e, se supportato, <xref:System.Windows.Automation.ToggleState.Indeterminate>.</span><span class="sxs-lookup"><span data-stu-id="bcbb7-112">A control must cycle through its <xref:System.Windows.Automation.ToggleState> in the following order: <xref:System.Windows.Automation.ToggleState.On>, <xref:System.Windows.Automation.ToggleState.Off> and, if supported, <xref:System.Windows.Automation.ToggleState.Indeterminate>.</span></span>  
  
- <span data-ttu-id="bcbb7-113"><xref:System.Windows.Automation.TogglePattern> non implementa un metodo SetState(newState) a causa di problemi relativi all'impostazione diretta di una casella di controllo a tre stati senza la possibilità di scorrere la relativa sequenza <xref:System.Windows.Automation.ToggleState> appropriata.</span><span class="sxs-lookup"><span data-stu-id="bcbb7-113"><xref:System.Windows.Automation.TogglePattern> does not provide a SetState(newState) method due to issues surrounding the direct setting of a tri-state CheckBox without cycling through its appropriate <xref:System.Windows.Automation.ToggleState> sequence.</span></span>  
  
- <span data-ttu-id="bcbb7-114">Il controllo RadioButton non implementa <xref:System.Windows.Automation.Provider.IToggleProvider>perché non è in grado di eseguire lo scorrimento tra gli stati validi.</span><span class="sxs-lookup"><span data-stu-id="bcbb7-114">The RadioButton control does not implement <xref:System.Windows.Automation.Provider.IToggleProvider>, as it is not capable of cycling through its valid states.</span></span>  
  
<a name="Required_Members_for_IToggleProvider"></a>
## <a name="required-members-for-itoggleprovider"></a><span data-ttu-id="bcbb7-115">Membri obbligatori per IToggleProvider</span><span class="sxs-lookup"><span data-stu-id="bcbb7-115">Required Members for IToggleProvider</span></span>  
 <span data-ttu-id="bcbb7-116">Le proprietà e i metodi seguenti sono obbligatori per l'implementazione di <xref:System.Windows.Automation.Provider.IToggleProvider>.</span><span class="sxs-lookup"><span data-stu-id="bcbb7-116">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IToggleProvider>.</span></span>  
  
|<span data-ttu-id="bcbb7-117">Membro obbligatorio</span><span class="sxs-lookup"><span data-stu-id="bcbb7-117">Required member</span></span>|<span data-ttu-id="bcbb7-118">Tipo di membro</span><span class="sxs-lookup"><span data-stu-id="bcbb7-118">Member type</span></span>|<span data-ttu-id="bcbb7-119">Note</span><span class="sxs-lookup"><span data-stu-id="bcbb7-119">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.TogglePattern.Toggle%2A>|<span data-ttu-id="bcbb7-120">Metodo</span><span class="sxs-lookup"><span data-stu-id="bcbb7-120">Method</span></span>|<span data-ttu-id="bcbb7-121">nessuno</span><span class="sxs-lookup"><span data-stu-id="bcbb7-121">None</span></span>|  
|<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty>|<span data-ttu-id="bcbb7-122">Proprietà</span><span class="sxs-lookup"><span data-stu-id="bcbb7-122">Property</span></span>|<span data-ttu-id="bcbb7-123">nessuno</span><span class="sxs-lookup"><span data-stu-id="bcbb7-123">None</span></span>|  
  
 <span data-ttu-id="bcbb7-124">Questo pattern di controllo non è associato a eventi.</span><span class="sxs-lookup"><span data-stu-id="bcbb7-124">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a><span data-ttu-id="bcbb7-125">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="bcbb7-125">Exceptions</span></span>  
 <span data-ttu-id="bcbb7-126">Questo pattern di controllo non è associato a eccezioni.</span><span class="sxs-lookup"><span data-stu-id="bcbb7-126">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcbb7-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bcbb7-127">See also</span></span>

- [<span data-ttu-id="bcbb7-128">UI Automation Control Patterns Overview</span><span class="sxs-lookup"><span data-stu-id="bcbb7-128">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="bcbb7-129">Supportare pattern di controllo in un provider di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="bcbb7-129">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="bcbb7-130">Pattern di controllo di automazione interfaccia utente per i client</span><span class="sxs-lookup"><span data-stu-id="bcbb7-130">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="bcbb7-131">Ottenere lo stato di attivazione/disattivazione di una casella di controllo utilizzando l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="bcbb7-131">Get the Toggle State of a Check Box Using UI Automation</span></span>](get-the-toggle-state-of-a-check-box-using-ui-automation.md)
- [<span data-ttu-id="bcbb7-132">UI Automation Tree Overview</span><span class="sxs-lookup"><span data-stu-id="bcbb7-132">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="bcbb7-133">Utilizzare la memorizzazione nella cache per l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="bcbb7-133">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
