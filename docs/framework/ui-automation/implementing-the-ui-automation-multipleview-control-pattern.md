---
title: Implementazione del pattern di controllo MultipleView di automazione interfaccia utente
description: Esaminare le linee guida e le convenzioni per implementare il pattern di controllo MultipleView in automazione interfaccia utente. Vedere Membri obbligatori per l'interfaccia IMultipleViewProvider.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, MultipleView control pattern
- MultipleView control pattern
- control patterns, MultipleView
ms.assetid: 5bf1b248-ffee-48c8-9613-0b134bbe9f6a
ms.openlocfilehash: 0d65d57637891fcb1307f5ee83a417941ff323fb
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168223"
---
# <a name="implementing-the-ui-automation-multipleview-control-pattern"></a><span data-ttu-id="95a57-104">Implementazione del pattern di controllo MultipleView di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="95a57-104">Implementing the UI Automation MultipleView Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="95a57-105">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="95a57-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="95a57-106">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="95a57-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="95a57-107">In questo argomento vengono presentate le linee guida e le convenzioni per l'implementazione di <xref:System.Windows.Automation.Provider.IMultipleViewProvider>, incluse le informazioni relative a eventi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="95a57-107">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IMultipleViewProvider>, including information about events and properties.</span></span> <span data-ttu-id="95a57-108">Alla fine della panoramica sono elencati collegamenti ad altro materiale di riferimento.</span><span class="sxs-lookup"><span data-stu-id="95a57-108">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="95a57-109">Il pattern di controllo <xref:System.Windows.Automation.MultipleViewPattern> viene usato per supportare i controlli che implementano più rappresentazioni dello stesso set di informazioni o controlli figlio e che sono in grado di scorrere tali rappresentazioni.</span><span class="sxs-lookup"><span data-stu-id="95a57-109">The <xref:System.Windows.Automation.MultipleViewPattern> control pattern is used to support controls that provide, and are able to switch between, multiple representations of the same set of information or child controls.</span></span>  
  
 <span data-ttu-id="95a57-110">Esempi di controlli che possono presentare più viste includono la visualizzazione elenco, che può mostrare il contenuto come anteprime, riquadri, icone o dettagli), grafici di Microsoft Excel (a torta, a linee, a barre, valore della cella con una formula), documenti di Microsoft Word (normale, layout Web, layout di stampa, layout di lettura, struttura), calendario di Microsoft Outlook (anno, mese, settimana, giorno) e interfacce di Media Player di Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="95a57-110">Examples of controls that can present multiple views include the list view (which can show its contents as thumbnails, tiles, icons, or details), Microsoft Excel charts (pie, line, bar, cell value with a formula), Microsoft Word documents (normal, Web layout, print layout, reading layout, outline), Microsoft Outlook calendar (year, month, week, day), and Microsoft Windows Media Player skins.</span></span> <span data-ttu-id="95a57-111">Le visualizzazioni supportate sono determinate dallo sviluppatore del controllo e sono specifiche di ogni controllo.</span><span class="sxs-lookup"><span data-stu-id="95a57-111">The supported views are determined by the control developer and are specific to each control.</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="95a57-112">Linee guida e convenzioni di implementazione</span><span class="sxs-lookup"><span data-stu-id="95a57-112">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="95a57-113">Quando si implementa il pattern di controllo MultipleView, tenere presenti le linee guida e le convenzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="95a57-113">When implementing the Multiple View control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="95a57-114">Anche l'interfaccia<xref:System.Windows.Automation.Provider.IMultipleViewProvider> deve essere implementata in un contenitore che gestisce la visualizzazione corrente se è diversa da un controllo che fornisce la visualizzazione corrente.</span><span class="sxs-lookup"><span data-stu-id="95a57-114"><xref:System.Windows.Automation.Provider.IMultipleViewProvider> should also be implemented on a container that manages the current view if it is different from a control that provides the current view.</span></span> <span data-ttu-id="95a57-115">Ad esempio, Esplora risorse contiene un controllo elenco per il contenuto della cartella corrente, mentre la visualizzazione per il controllo viene gestita dall'applicazione Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="95a57-115">For example, Windows Explorer contains a List control for the current folder content while the view for the control is managed from the Windows Explorer application.</span></span>  
  
- <span data-ttu-id="95a57-116">Un controllo in grado di ordinare il relativo contenuto non supporta più visualizzazioni.</span><span class="sxs-lookup"><span data-stu-id="95a57-116">A control that is able to sort its content is not considered to support multiple views.</span></span>  
  
- <span data-ttu-id="95a57-117">La raccolta di visualizzazioni deve essere identica tra istanze.</span><span class="sxs-lookup"><span data-stu-id="95a57-117">The collection of views must be identical across instances.</span></span>  
  
- <span data-ttu-id="95a57-118">I nomi delle visualizzazioni devono essere adatti all'uso nelle applicazioni di sintesi vocale o nelle altre applicazioni per la lettura in Braille e altri metodi di lettura.</span><span class="sxs-lookup"><span data-stu-id="95a57-118">View names must be suitable for use in Text to Speech, Braille, and other human-readable applications.</span></span>  
  
<a name="Required_Members_for_IMultipleViewProvider"></a>
## <a name="required-members-for-imultipleviewprovider"></a><span data-ttu-id="95a57-119">Membri obbligatori per IMultipleViewProvider</span><span class="sxs-lookup"><span data-stu-id="95a57-119">Required Members for IMultipleViewProvider</span></span>  
 <span data-ttu-id="95a57-120">Le proprietà e i metodi seguenti sono obbligatori per l'implementazione di IMultipleViewProvider.</span><span class="sxs-lookup"><span data-stu-id="95a57-120">The following properties and methods are required for implementing IMultipleViewProvider.</span></span>  
  
|<span data-ttu-id="95a57-121">Membri obbligatori</span><span class="sxs-lookup"><span data-stu-id="95a57-121">Required members</span></span>|<span data-ttu-id="95a57-122">Tipo di membro</span><span class="sxs-lookup"><span data-stu-id="95a57-122">Member type</span></span>|<span data-ttu-id="95a57-123">Note</span><span class="sxs-lookup"><span data-stu-id="95a57-123">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.CurrentView%2A>|<span data-ttu-id="95a57-124">Proprietà</span><span class="sxs-lookup"><span data-stu-id="95a57-124">Property</span></span>|<span data-ttu-id="95a57-125">Nessuno</span><span class="sxs-lookup"><span data-stu-id="95a57-125">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetSupportedViews%2A>|<span data-ttu-id="95a57-126">Metodo</span><span class="sxs-lookup"><span data-stu-id="95a57-126">Method</span></span>|<span data-ttu-id="95a57-127">Nessuno</span><span class="sxs-lookup"><span data-stu-id="95a57-127">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A>|<span data-ttu-id="95a57-128">Metodo</span><span class="sxs-lookup"><span data-stu-id="95a57-128">Method</span></span>|<span data-ttu-id="95a57-129">Nessuno</span><span class="sxs-lookup"><span data-stu-id="95a57-129">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A>|<span data-ttu-id="95a57-130">Metodo</span><span class="sxs-lookup"><span data-stu-id="95a57-130">Method</span></span>|<span data-ttu-id="95a57-131">Nessuno</span><span class="sxs-lookup"><span data-stu-id="95a57-131">None</span></span>|  
  
 <span data-ttu-id="95a57-132">Non sono presenti eventi associati a questo pattern di controllo.</span><span class="sxs-lookup"><span data-stu-id="95a57-132">There are no events associated with this control pattern.</span></span>  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a><span data-ttu-id="95a57-133">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="95a57-133">Exceptions</span></span>  
 <span data-ttu-id="95a57-134">I provider devono generare le eccezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="95a57-134">Provider must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="95a57-135">Tipo di eccezione</span><span class="sxs-lookup"><span data-stu-id="95a57-135">Exception type</span></span>|<span data-ttu-id="95a57-136">Condizione</span><span class="sxs-lookup"><span data-stu-id="95a57-136">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="95a57-137">Viene eseguita una chiamata a <xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> o <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> con un parametro che non è un membro della raccolta delle visualizzazioni supportate.</span><span class="sxs-lookup"><span data-stu-id="95a57-137">When either <xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> or <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> is called with a parameter that is not a member of the supported views collection.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="95a57-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95a57-138">See also</span></span>

- [<span data-ttu-id="95a57-139">Cenni preliminari sui pattern di controllo per l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="95a57-139">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="95a57-140">Supportare pattern di controllo in un provider di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="95a57-140">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="95a57-141">Pattern di controllo di automazione interfaccia utente per i client</span><span class="sxs-lookup"><span data-stu-id="95a57-141">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="95a57-142">Panoramica dell'albero di automazione dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="95a57-142">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="95a57-143">Utilizzare la memorizzazione nella cache per l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="95a57-143">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
