---
title: Cenni preliminari sulle proprietà di automazione interfaccia utente
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, properties
- properties, UI Automation
ms.assetid: a6c31d7b-b33e-49b3-b5c1-31a345f9b7c8
ms.openlocfilehash: 2f96f3c7261882af58cd10038d729c4e723d6fa0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447958"
---
# <a name="ui-automation-properties-overview"></a><span data-ttu-id="6205b-102">Cenni preliminari sulle proprietà di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="6205b-102">UI Automation Properties Overview</span></span>
> [!NOTE]
> <span data-ttu-id="6205b-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="6205b-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="6205b-104">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere l'argomento sull' [API Automazione interfaccia utente di Windows](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="6205b-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="6205b-105">I provider di automazione interfaccia utente espongono le proprietà negli elementi di [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6205b-105">UI Automation providers expose properties on [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elements.</span></span> <span data-ttu-id="6205b-106">Queste proprietà consentono alle applicazioni client di automazione interfaccia utente di individuare informazioni su parti dell' [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)], soprattutto i controlli, inclusi i dati sia statici che dinamici.</span><span class="sxs-lookup"><span data-stu-id="6205b-106">These properties enable UI Automation client applications to discover information about pieces of the [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)], especially controls, including both static and dynamic data.</span></span>  
  
 <span data-ttu-id="6205b-107">Questa sezione offre un'ampia panoramica delle proprietà di [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6205b-107">This section gives a broad overview of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] properties.</span></span> <span data-ttu-id="6205b-108">Informazioni più specifiche sono disponibili negli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="6205b-108">More specific information is given in the following topics:</span></span>  
  
- [<span data-ttu-id="6205b-109">Proprietà di automazione interfaccia utente per i client</span><span class="sxs-lookup"><span data-stu-id="6205b-109">UI Automation Properties for Clients</span></span>](ui-automation-properties-for-clients.md)  
  
- [<span data-ttu-id="6205b-110">Implementazione del provider di automazione interfaccia utente lato server</span><span class="sxs-lookup"><span data-stu-id="6205b-110">Server-Side UI Automation Provider Implementation</span></span>](server-side-ui-automation-provider-implementation.md)  
  
<a name="Property_Identifiers"></a>   
## <a name="property-identifiers"></a><span data-ttu-id="6205b-111">Identificatori di proprietà</span><span class="sxs-lookup"><span data-stu-id="6205b-111">Property Identifiers</span></span>  
 <span data-ttu-id="6205b-112">Ogni proprietà è identificata da un numero e da un nome.</span><span class="sxs-lookup"><span data-stu-id="6205b-112">Every property is identified by a number and a name.</span></span> <span data-ttu-id="6205b-113">I nomi delle proprietà vengono usati solo per il debug e la diagnosi.</span><span class="sxs-lookup"><span data-stu-id="6205b-113">The names of properties are used only for debugging and diagnosis.</span></span> <span data-ttu-id="6205b-114">Providers use the numeric IDs to identify incoming property requests.</span><span class="sxs-lookup"><span data-stu-id="6205b-114">Providers use the numeric IDs to identify incoming property requests.</span></span> <span data-ttu-id="6205b-115">Le applicazioni client, tuttavia, usano solo <xref:System.Windows.Automation.AutomationProperty>, che incapsula il numero e il nome, per identificare le proprietà che vogliono recuperare.</span><span class="sxs-lookup"><span data-stu-id="6205b-115">Client applications, however, only use <xref:System.Windows.Automation.AutomationProperty>, which encapsulates the number and name, to identify properties they wish to retrieve.</span></span>  
  
 <span data-ttu-id="6205b-116">Gli oggetti<xref:System.Windows.Automation.AutomationProperty> che rappresentano particolari proprietà sono disponibili come campi in diverse classi.</span><span class="sxs-lookup"><span data-stu-id="6205b-116"><xref:System.Windows.Automation.AutomationProperty> objects representing particular properties are available as fields in various classes.</span></span> <span data-ttu-id="6205b-117">Per motivi di sicurezza, i provider di automazione interfaccia utente ottengono questi oggetti da un set separato di classi contenute in Uiautomationtypes.dll.</span><span class="sxs-lookup"><span data-stu-id="6205b-117">For security reasons, UI Automation providers obtain these objects from a separate set of classes that are contained in Uiautomationtypes.dll.</span></span>  
  
 <span data-ttu-id="6205b-118">The following table categorizes properties by the classes that contain the <xref:System.Windows.Automation.AutomationProperty>IDs.</span><span class="sxs-lookup"><span data-stu-id="6205b-118">The following table categorizes properties by the classes that contain the <xref:System.Windows.Automation.AutomationProperty>IDs.</span></span>  
  
|<span data-ttu-id="6205b-119">Tipologie di proprietà</span><span class="sxs-lookup"><span data-stu-id="6205b-119">Kinds of properties</span></span>|<span data-ttu-id="6205b-120">I client ottengono gli ID da</span><span class="sxs-lookup"><span data-stu-id="6205b-120">Clients get IDs from</span></span>|<span data-ttu-id="6205b-121">I provider ottengono gli ID da</span><span class="sxs-lookup"><span data-stu-id="6205b-121">Providers get IDs from</span></span>|  
|-------------------------|--------------------------|----------------------------|  
|<span data-ttu-id="6205b-122">Proprietà comuni a tutti gli elementi (vedere le tabelle seguenti)</span><span class="sxs-lookup"><span data-stu-id="6205b-122">Properties common to all elements (see following tables)</span></span>|<xref:System.Windows.Automation.AutomationElement>|<xref:System.Windows.Automation.AutomationElementIdentifiers>|  
|<span data-ttu-id="6205b-123">Posizione di una finestra di ancoraggio</span><span class="sxs-lookup"><span data-stu-id="6205b-123">Position of a docking window</span></span>|<xref:System.Windows.Automation.DockPattern>|<xref:System.Windows.Automation.DockPatternIdentifiers>|  
|<span data-ttu-id="6205b-124">Stato di un elemento che può essere espanso e compresso</span><span class="sxs-lookup"><span data-stu-id="6205b-124">State of an element that can expand and collapse</span></span>|<xref:System.Windows.Automation.ExpandCollapsePattern>|<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers>|  
|<span data-ttu-id="6205b-125">Proprietà di un elemento in una griglia</span><span class="sxs-lookup"><span data-stu-id="6205b-125">Properties of an item in a grid</span></span>|<xref:System.Windows.Automation.GridItemPattern>|<xref:System.Windows.Automation.GridItemPatternIdentifiers>|  
|<span data-ttu-id="6205b-126">Proprietà di una griglia</span><span class="sxs-lookup"><span data-stu-id="6205b-126">Properties of a grid</span></span>|<xref:System.Windows.Automation.GridPattern>|<xref:System.Windows.Automation.GridPatternIdentifiers>|  
|<span data-ttu-id="6205b-127">Visualizzazione corrente e supportata di un elemento con più visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="6205b-127">Current and supported view of an element that has multiple views</span></span>|<xref:System.Windows.Automation.MultipleViewPattern>|<xref:System.Windows.Automation.MultipleViewPatternIdentifiers>|  
|<span data-ttu-id="6205b-128">Proprietà di un elemento che viene spostato su un intervallo di valori, ad esempio un dispositivo di scorrimento</span><span class="sxs-lookup"><span data-stu-id="6205b-128">Properties of an element that moves over a range of values, such as a slider</span></span>|<xref:System.Windows.Automation.RangeValuePattern>|<xref:System.Windows.Automation.RangeValuePatternIdentifiers>|  
|<span data-ttu-id="6205b-129">Proprietà di una finestra di scorrimento</span><span class="sxs-lookup"><span data-stu-id="6205b-129">Properties of a scrolling window</span></span>|<xref:System.Windows.Automation.ScrollPattern>|<xref:System.Windows.Automation.ScrollPatternIdentifiers>|  
|<span data-ttu-id="6205b-130">Stato e contenitore di un elemento che può essere selezionato, ad esempio in un elenco</span><span class="sxs-lookup"><span data-stu-id="6205b-130">Status and container of an item that can be selected, as in a list</span></span>|<xref:System.Windows.Automation.SelectionItemPattern>|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers>|  
|<span data-ttu-id="6205b-131">Proprietà di un controllo contenente gli elementi della selezione</span><span class="sxs-lookup"><span data-stu-id="6205b-131">Properties of a control that contains selection items</span></span>|<xref:System.Windows.Automation.SelectionPattern>|<xref:System.Windows.Automation.SelectionPatternIdentifiers>|  
|<span data-ttu-id="6205b-132">Intestazioni di colonna e di riga di un elemento in una tabella</span><span class="sxs-lookup"><span data-stu-id="6205b-132">Column and row headers of an item in a table</span></span>|<xref:System.Windows.Automation.TableItemPattern>|<xref:System.Windows.Automation.TableItemPatternIdentifiers>|  
|<span data-ttu-id="6205b-133">Intestazioni di colonna e di riga e orientamento di una tabella</span><span class="sxs-lookup"><span data-stu-id="6205b-133">Column and row headers, and orientation, of a table</span></span>|<xref:System.Windows.Automation.TablePattern>|<xref:System.Windows.Automation.TablePatternIdentifiers>|  
|<span data-ttu-id="6205b-134">Stato di un controllo di attivazione/disattivazione</span><span class="sxs-lookup"><span data-stu-id="6205b-134">State of a toggle control</span></span>|<xref:System.Windows.Automation.TogglePattern>|<xref:System.Windows.Automation.TogglePatternIdentifiers>|  
|<span data-ttu-id="6205b-135">Funzionalità di un elemento che può essere spostato, ruotato o ridimensionato</span><span class="sxs-lookup"><span data-stu-id="6205b-135">Capabilities of an element that can be moved, rotated, or resized</span></span>|<xref:System.Windows.Automation.TransformPattern>|<xref:System.Windows.Automation.TransformPatternIdentifiers>|  
|<span data-ttu-id="6205b-136">Valore e funzionalità di lettura/scrittura di un elemento con un valore</span><span class="sxs-lookup"><span data-stu-id="6205b-136">Value and read/write capabilities of an element that has a value</span></span>|<xref:System.Windows.Automation.ValuePattern>|<xref:System.Windows.Automation.ValuePatternIdentifiers>|  
|<span data-ttu-id="6205b-137">Funzionalità e stato di una finestra</span><span class="sxs-lookup"><span data-stu-id="6205b-137">Capabilities and state of a window</span></span>|<xref:System.Windows.Automation.WindowPattern>|<xref:System.Windows.Automation.WindowPatternIdentifiers>|  
  
<a name="Properties_by_Category"></a>   
## <a name="properties-by-category"></a><span data-ttu-id="6205b-138">Proprietà per categoria</span><span class="sxs-lookup"><span data-stu-id="6205b-138">Properties by Category</span></span>  
 <span data-ttu-id="6205b-139">The following tables categorize the properties whose IDs are found in <xref:System.Windows.Automation.AutomationElement> and <xref:System.Windows.Automation.AutomationElementIdentifiers>.</span><span class="sxs-lookup"><span data-stu-id="6205b-139">The following tables categorize the properties whose IDs are found in <xref:System.Windows.Automation.AutomationElement> and <xref:System.Windows.Automation.AutomationElementIdentifiers>.</span></span> <span data-ttu-id="6205b-140">Queste proprietà sono comuni a tutti i controlli.</span><span class="sxs-lookup"><span data-stu-id="6205b-140">These properties are common to all controls.</span></span> <span data-ttu-id="6205b-141">È probabile che quasi tutte siano statiche per tutto il ciclo di vita dell'applicazione del provider. Le proprietà più dinamiche sono associate ai pattern di controllo.</span><span class="sxs-lookup"><span data-stu-id="6205b-141">All but a few of them are likely to be static over the lifetime of the provider application; most dynamic properties are associated with control patterns.</span></span>  
  
 <span data-ttu-id="6205b-142">La colonna **Accesso a proprietà** elenca tutte le altre funzioni di accesso per ogni proprietà, oltre a <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> e <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="6205b-142">The **Property Access** column lists any other accessors for each property, in addition to <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> and <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>.</span></span> <span data-ttu-id="6205b-143">Per altre informazioni su come ottenere le proprietà in un'applicazione client, vedere [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="6205b-143">For more information on getting properties in a client application, see [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6205b-144">Per informazioni specifiche su ogni proprietà, seguire il collegamento nella colonna **Accesso a proprietà** .</span><span class="sxs-lookup"><span data-stu-id="6205b-144">For specific information about each property, follow the link in the **Property Access** column.</span></span>  
  
### <a name="display-characteristics"></a><span data-ttu-id="6205b-145">Caratteristiche dello schermo</span><span class="sxs-lookup"><span data-stu-id="6205b-145">Display Characteristics</span></span>  
  
|<span data-ttu-id="6205b-146">Identificatore di proprietà</span><span class="sxs-lookup"><span data-stu-id="6205b-146">Property identifier</span></span>|<span data-ttu-id="6205b-147">Accesso a proprietà</span><span class="sxs-lookup"><span data-stu-id="6205b-147">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.BoundingRectangle%2A>|  
|<xref:System.Windows.Automation.AutomationElement.CultureProperty>|<span data-ttu-id="6205b-148">N/D</span><span class="sxs-lookup"><span data-stu-id="6205b-148">n/a</span></span>|  
|<xref:System.Windows.Automation.AutomationElement.HelpTextProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HelpText%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsOffscreen%2A>|  
|<xref:System.Windows.Automation.AutomationElement.OrientationProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Orientation%2A>|  
  
### <a name="element-type"></a><span data-ttu-id="6205b-149">Tipo di elemento</span><span class="sxs-lookup"><span data-stu-id="6205b-149">Element Type</span></span>  
  
|<span data-ttu-id="6205b-150">Identificatore di proprietà</span><span class="sxs-lookup"><span data-stu-id="6205b-150">Property identifier</span></span>|<span data-ttu-id="6205b-151">Accesso a proprietà</span><span class="sxs-lookup"><span data-stu-id="6205b-151">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsContentElementProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsContentElement%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsControlElementProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsControlElement%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ItemTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ItemType%2A>|  
|<xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.LocalizedControlType%2A>|  
  
### <a name="identification"></a><span data-ttu-id="6205b-152">Identification</span><span class="sxs-lookup"><span data-stu-id="6205b-152">Identification</span></span>  
  
|<span data-ttu-id="6205b-153">Identificatore di proprietà</span><span class="sxs-lookup"><span data-stu-id="6205b-153">Property identifier</span></span>|<span data-ttu-id="6205b-154">Accesso a proprietà</span><span class="sxs-lookup"><span data-stu-id="6205b-154">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.AutomationIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AutomationId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ClassNameProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ClassName%2A>|  
|<xref:System.Windows.Automation.AutomationElement.FrameworkIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.FrameworkId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.LabeledByProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.LabeledBy%2A>|  
|<xref:System.Windows.Automation.AutomationElement.NameProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ProcessIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ProcessId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.RuntimeIdProperty>|<xref:System.Windows.Automation.AutomationElement.GetRuntimeId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.NativeWindowHandleProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.NativeWindowHandle%2A>|  
  
### <a name="interaction"></a><span data-ttu-id="6205b-155">Interazione</span><span class="sxs-lookup"><span data-stu-id="6205b-155">Interaction</span></span>  
  
|<span data-ttu-id="6205b-156">Identificatore di proprietà</span><span class="sxs-lookup"><span data-stu-id="6205b-156">Property identifier</span></span>|<span data-ttu-id="6205b-157">Accesso a proprietà</span><span class="sxs-lookup"><span data-stu-id="6205b-157">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AcceleratorKey%2A>|  
|<xref:System.Windows.Automation.AutomationElement.AccessKeyProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AccessKey%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ClickablePointProperty>|<xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A>|  
|<xref:System.Windows.Automation.AutomationElement.HasKeyboardFocusProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HasKeyboardFocus%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsEnabled%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsKeyboardFocusableProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsKeyboardFocusable%2A>|  
  
### <a name="support-for-patterns"></a><span data-ttu-id="6205b-158">Supporto per pattern</span><span class="sxs-lookup"><span data-stu-id="6205b-158">Support for Patterns</span></span>  
  
|<span data-ttu-id="6205b-159">Identificatore di proprietà</span><span class="sxs-lookup"><span data-stu-id="6205b-159">Property identifier</span></span>|<span data-ttu-id="6205b-160">Accesso a proprietà</span><span class="sxs-lookup"><span data-stu-id="6205b-160">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.IsDockPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsExpandCollapsePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsGridItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsGridPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsInvokePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsMultipleViewPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsRangeValuePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsScrollItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsScrollPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsSelectionItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsSelectionPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTableItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTablePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTextPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTogglePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTransformPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsValuePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsWindowPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
  
### <a name="miscellaneous"></a><span data-ttu-id="6205b-161">Varie</span><span class="sxs-lookup"><span data-stu-id="6205b-161">Miscellaneous</span></span>  
  
|<span data-ttu-id="6205b-162">Identificatore di proprietà</span><span class="sxs-lookup"><span data-stu-id="6205b-162">Property identifier</span></span>|<span data-ttu-id="6205b-163">Accesso a proprietà</span><span class="sxs-lookup"><span data-stu-id="6205b-163">Property access</span></span>|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.IsRequiredForFormProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsRequiredForForm%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsPasswordProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsPassword%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ItemStatusProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ItemStatus%2A>|  
  
<a name="Localization"></a>   
## <a name="localization"></a><span data-ttu-id="6205b-164">Localizzazione</span><span class="sxs-lookup"><span data-stu-id="6205b-164">Localization</span></span>  
 <span data-ttu-id="6205b-165">I provider di[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] devono presentare le proprietà seguenti nella lingua del sistema operativo:</span><span class="sxs-lookup"><span data-stu-id="6205b-165">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] providers should present the following properties in the language of the operating system:</span></span>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.AcceleratorKeyProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.AccessKeyProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>  
  
<a name="Properties_and_Events"></a>   
## <a name="properties-and-events"></a><span data-ttu-id="6205b-166">Proprietà ed eventi</span><span class="sxs-lookup"><span data-stu-id="6205b-166">Properties and Events</span></span>  
 <span data-ttu-id="6205b-167">In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] il concetto di eventi di modifica di proprietà è strettamente collegato alle proprietà.</span><span class="sxs-lookup"><span data-stu-id="6205b-167">Closely tied in with the properties in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] is the concept of property-changed events.</span></span> <span data-ttu-id="6205b-168">Per le proprietà dinamiche, l'applicazione client deve venire a conoscenza del fatto che il valore di una proprietà è cambiato, per poter aggiornare la cache delle informazioni o rispondere in altro modo alle nuove informazioni.</span><span class="sxs-lookup"><span data-stu-id="6205b-168">For dynamic properties, the client application needs a way to know that a property value has changed, so that it can update its cache of information or react to the new information in some other way.</span></span>  
  
 <span data-ttu-id="6205b-169">I provider generano eventi quando vengono apportate modifiche all' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6205b-169">Providers raise events when something in the [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] changes.</span></span> <span data-ttu-id="6205b-170">Se, ad esempio, una casella di controllo viene selezionata o deselezionata, un evento di modificata di proprietà viene generato dall'implementazione del pattern Toggle da parte del provider.</span><span class="sxs-lookup"><span data-stu-id="6205b-170">For example, if a check box is selected or cleared, a property-changed event is raised by the provider's implementation of the Toggle pattern.</span></span> <span data-ttu-id="6205b-171">I provider possono generare gli eventi in modo selettivo, a seconda che i client siano in ascolto di eventi oppure di eventi specifici.</span><span class="sxs-lookup"><span data-stu-id="6205b-171">Providers can raise events selectively, depending on whether any clients are listening for events, or listening for specific events.</span></span>  
  
 <span data-ttu-id="6205b-172">Non tutte le modifiche di proprietà generano eventi. Questo dipende totalmente dall'implementazione del provider di automazione interfaccia utente per l'elemento.</span><span class="sxs-lookup"><span data-stu-id="6205b-172">Not all property changes raise events; that is entirely up to the implementation of the UI Automation provider for the element.</span></span> <span data-ttu-id="6205b-173">Ad esempio, i provider di proxy standard per le caselle di riepilogo non generano un evento quando <xref:System.Windows.Automation.SelectionPattern.SelectionProperty> cambia.</span><span class="sxs-lookup"><span data-stu-id="6205b-173">For example, the standard proxy providers for list boxes do not raise an event when the <xref:System.Windows.Automation.SelectionPattern.SelectionProperty> changes.</span></span> <span data-ttu-id="6205b-174">In questo caso, l'applicazione è invece in ascolto di un evento <xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent>.</span><span class="sxs-lookup"><span data-stu-id="6205b-174">In this case, the application instead must listen for an <xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent>.</span></span>  
  
 <span data-ttu-id="6205b-175">I client restano in ascolto degli eventi sottoscrivendoli.</span><span class="sxs-lookup"><span data-stu-id="6205b-175">Clients listen for events by subscribing to them.</span></span> <span data-ttu-id="6205b-176">Sottoscrivere gli eventi significa creare metodi delegati che possono gestire gli eventi e quindi passare i metodi ad [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] insieme agli eventi specifici che verranno gestiti da tali metodi.</span><span class="sxs-lookup"><span data-stu-id="6205b-176">Subscribing to events means creating delegate methods that can handle the events, and then passing the methods to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] along with the specific events that will be dealt with in those methods.</span></span> <span data-ttu-id="6205b-177">In particolare, per gli eventi di modifica di proprietà i client devono implementare <xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="6205b-177">For property-changed events in particular, clients must implement <xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6205b-178">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6205b-178">See also</span></span>

- [<span data-ttu-id="6205b-179">Memorizzazione nella cache di client di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="6205b-179">Caching in UI Automation Clients</span></span>](caching-in-ui-automation-clients.md)
- [<span data-ttu-id="6205b-180">Proprietà di automazione interfaccia utente per i client</span><span class="sxs-lookup"><span data-stu-id="6205b-180">UI Automation Properties for Clients</span></span>](ui-automation-properties-for-clients.md)
- [<span data-ttu-id="6205b-181">Implementazione del provider di automazione interfaccia utente lato server</span><span class="sxs-lookup"><span data-stu-id="6205b-181">Server-Side UI Automation Provider Implementation</span></span>](server-side-ui-automation-provider-implementation.md)
- [<span data-ttu-id="6205b-182">Trovare un elemento di automazione interfaccia utente in base a una condizione proprietà</span><span class="sxs-lookup"><span data-stu-id="6205b-182">Find a UI Automation Element Based on a Property Condition</span></span>](find-a-ui-automation-element-based-on-a-property-condition.md)
- [<span data-ttu-id="6205b-183">Restituire proprietà da un provider di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="6205b-183">Return Properties from a UI Automation Provider</span></span>](return-properties-from-a-ui-automation-provider.md)
- [<span data-ttu-id="6205b-184">Generare eventi da un provider di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="6205b-184">Raise Events from a UI Automation Provider</span></span>](raise-events-from-a-ui-automation-provider.md)
