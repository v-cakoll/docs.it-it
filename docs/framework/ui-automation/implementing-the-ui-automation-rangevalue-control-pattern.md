---
title: Implementazione del pattern di controllo RangeValue di automazione interfaccia utente
description: Esaminare le linee guida e le convenzioni per l'implementazione del pattern di controllo RangeValue nell'automazione interfaccia utente. Vedere Membri obbligatori per l'interfaccia IRangeValueProvider.
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Range Value
- Range Value control pattern
- UI Automation, Range Value control pattern
ms.assetid: 225feaa4-918e-418b-938e-7389338d0a69
ms.openlocfilehash: ccb6aeb5f8451975d7e2e9649bbb82c0c3ae23d5
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164086"
---
# <a name="implementing-the-ui-automation-rangevalue-control-pattern"></a><span data-ttu-id="6e916-104">Implementazione del pattern di controllo RangeValue di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="6e916-104">Implementing the UI Automation RangeValue Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="6e916-105">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="6e916-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="6e916-106">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="6e916-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="6e916-107">In questo argomento vengono presentate le linee guida e le convenzioni per l'implementazione di <xref:System.Windows.Automation.Provider.IRangeValueProvider>, incluse le informazioni relative a eventi e proprietà.</span><span class="sxs-lookup"><span data-stu-id="6e916-107">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IRangeValueProvider>, including information about events and properties.</span></span> <span data-ttu-id="6e916-108">Alla fine della panoramica sono elencati collegamenti ad altro materiale di riferimento.</span><span class="sxs-lookup"><span data-stu-id="6e916-108">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="6e916-109">Il pattern di controllo <xref:System.Windows.Automation.RangeValuePattern> viene usato per supportare i controlli che possono impostare un valore in un intervallo.</span><span class="sxs-lookup"><span data-stu-id="6e916-109">The <xref:System.Windows.Automation.RangeValuePattern> control pattern is used to support controls that can be set to a value within a range.</span></span> <span data-ttu-id="6e916-110">Per esempi di controlli che implementano questo pattern di controllo, vedere [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span><span class="sxs-lookup"><span data-stu-id="6e916-110">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="6e916-111">Linee guida e convenzioni di implementazione</span><span class="sxs-lookup"><span data-stu-id="6e916-111">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="6e916-112">Quando si implementa il pattern di controllo RangeValue, tenere presenti le linee guida e le convenzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6e916-112">When implementing the Range Value control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="6e916-113">I controlli consentono la ricalibrazione delle relative proprietà supportate in base alle preferenze utente o alle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="6e916-113">Controls allow recalibration of their supported properties based upon locale or user preference.</span></span> <span data-ttu-id="6e916-114">Un esempio di questo è un controllo termometro che può essere impostato per visualizzare la temperatura in gradi Fahrenheit o Celsius.</span><span class="sxs-lookup"><span data-stu-id="6e916-114">An example of this is a thermometer control that can be set to display the temperature in Fahrenheit or Celsius.</span></span>  
  
- <span data-ttu-id="6e916-115">I controlli che dispongono di valori di intervallo ambigui, ad esempio le barre di avanzamento o i dispositivi di scorrimento, devono avere questi valori normalizzati.</span><span class="sxs-lookup"><span data-stu-id="6e916-115">Controls that have ambiguous range values, such as progress bars or sliders, should have those values normalized.</span></span>  
  
 <span data-ttu-id="6e916-116">![Indicatore di stato.](./media/uia-rangevaluepattern-progress-bar.PNG "UIA_RangeValuePattern_Progress_Bar")</span><span class="sxs-lookup"><span data-stu-id="6e916-116">![Progress bar.](./media/uia-rangevaluepattern-progress-bar.PNG "UIA_RangeValuePattern_Progress_Bar")</span></span>  
<span data-ttu-id="6e916-117">Esempio di un indicatore di stato in cui valore è di tipo Integer e i relativi valori di proprietà minimo e massimo sono normalizzati rispettivamente a 0 e 100</span><span class="sxs-lookup"><span data-stu-id="6e916-117">Example of a Progress Bar Where Value Is of Type Integer and Minimum and Maximum Property Values Are Normalized to 0 and 100, Respectively</span></span>  
  
<a name="Required_Members_for_the_IRangeValueProvider"></a>
## <a name="required-members-for-irangevalueprovider"></a><span data-ttu-id="6e916-118">Membri obbligatori per IRangeValueProvider</span><span class="sxs-lookup"><span data-stu-id="6e916-118">Required Members for IRangeValueProvider</span></span>  
  
|<span data-ttu-id="6e916-119">Membro obbligatorio</span><span class="sxs-lookup"><span data-stu-id="6e916-119">Required member</span></span>|<span data-ttu-id="6e916-120">Tipo di membro</span><span class="sxs-lookup"><span data-stu-id="6e916-120">Member type</span></span>|<span data-ttu-id="6e916-121">Note</span><span class="sxs-lookup"><span data-stu-id="6e916-121">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.RangeValuePattern.IsReadOnlyProperty>|<span data-ttu-id="6e916-122">Proprietà</span><span class="sxs-lookup"><span data-stu-id="6e916-122">Property</span></span>|<span data-ttu-id="6e916-123">Nessuno</span><span class="sxs-lookup"><span data-stu-id="6e916-123">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.ValueProperty>|<span data-ttu-id="6e916-124">Proprietà</span><span class="sxs-lookup"><span data-stu-id="6e916-124">Property</span></span>|<span data-ttu-id="6e916-125">Nessuno</span><span class="sxs-lookup"><span data-stu-id="6e916-125">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.LargeChangeProperty>|<span data-ttu-id="6e916-126">Proprietà</span><span class="sxs-lookup"><span data-stu-id="6e916-126">Property</span></span>|<span data-ttu-id="6e916-127">Nessuno</span><span class="sxs-lookup"><span data-stu-id="6e916-127">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.SmallChangeProperty>|<span data-ttu-id="6e916-128">Proprietà</span><span class="sxs-lookup"><span data-stu-id="6e916-128">Property</span></span>|<span data-ttu-id="6e916-129">Nessuno</span><span class="sxs-lookup"><span data-stu-id="6e916-129">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.MaximumProperty>|<span data-ttu-id="6e916-130">Proprietà</span><span class="sxs-lookup"><span data-stu-id="6e916-130">Property</span></span>|<span data-ttu-id="6e916-131">Nessuno</span><span class="sxs-lookup"><span data-stu-id="6e916-131">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.MinimumProperty>|<span data-ttu-id="6e916-132">Proprietà</span><span class="sxs-lookup"><span data-stu-id="6e916-132">Property</span></span>|<span data-ttu-id="6e916-133">Nessuno</span><span class="sxs-lookup"><span data-stu-id="6e916-133">None</span></span>|  
|<xref:System.Windows.Automation.RangeValuePattern.SetValue%2A>|<span data-ttu-id="6e916-134">Metodi</span><span class="sxs-lookup"><span data-stu-id="6e916-134">Methods</span></span>|<span data-ttu-id="6e916-135">Nessuno</span><span class="sxs-lookup"><span data-stu-id="6e916-135">None</span></span>|  
  
 <span data-ttu-id="6e916-136">Questo pattern di controllo non è associato a eventi.</span><span class="sxs-lookup"><span data-stu-id="6e916-136">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a><span data-ttu-id="6e916-137">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="6e916-137">Exceptions</span></span>  
 <span data-ttu-id="6e916-138">I provider devono generare le eccezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="6e916-138">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="6e916-139">Tipo di eccezione</span><span class="sxs-lookup"><span data-stu-id="6e916-139">Exception type</span></span>|<span data-ttu-id="6e916-140">Condizione</span><span class="sxs-lookup"><span data-stu-id="6e916-140">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentOutOfRangeException>|<span data-ttu-id="6e916-141"><xref:System.Windows.Automation.RangeValuePattern.SetValue%2A> viene chiamato con un valore che è maggiore di <xref:System.Windows.Automation.RangeValuePattern.MaximumProperty> o minore di <xref:System.Windows.Automation.RangeValuePattern.MinimumProperty>.</span><span class="sxs-lookup"><span data-stu-id="6e916-141"><xref:System.Windows.Automation.RangeValuePattern.SetValue%2A> is called with a value that is either greater than <xref:System.Windows.Automation.RangeValuePattern.MaximumProperty> or less than <xref:System.Windows.Automation.RangeValuePattern.MinimumProperty>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6e916-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e916-142">See also</span></span>

- [<span data-ttu-id="6e916-143">Cenni preliminari sui pattern di controllo per l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="6e916-143">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="6e916-144">Supportare pattern di controllo in un provider di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="6e916-144">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="6e916-145">Pattern di controllo di automazione interfaccia utente per i client</span><span class="sxs-lookup"><span data-stu-id="6e916-145">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="6e916-146">Panoramica dell'albero di automazione dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="6e916-146">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="6e916-147">Utilizzare la memorizzazione nella cache per l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="6e916-147">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
