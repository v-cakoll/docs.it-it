---
title: Cenni preliminari sui tipi di controllo per l'automazione interfaccia utente
description: Leggere una panoramica dei tipi di controllo di automazione interfaccia utente, che sono identificatori noti che possono essere usati per indicare il tipo di controllo rappresentato da un elemento.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, control types
- control types, UI Automation
ms.assetid: 75159ef8-bd43-4d13-acb7-1f1fe9253160
ms.openlocfilehash: 204e950fca74c4f7bd2c13dc8a8891152954c071
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166129"
---
# <a name="ui-automation-control-types-overview"></a><span data-ttu-id="05819-103">Cenni preliminari sui tipi di controllo per l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="05819-103">UI Automation Control Types Overview</span></span>
> [!NOTE]
> <span data-ttu-id="05819-104">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="05819-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="05819-105">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="05819-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="05819-106">I tipi di controllo di[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] sono identificatori noti che possono essere usati per indicare quale tipo di controllo è rappresentato da un particolare elemento, ad esempio una casella combinata o un pulsante.</span><span class="sxs-lookup"><span data-stu-id="05819-106">[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] control types are well-known identifiers that can be used to indicate what kind of control a particular element represents, such as a combo box or a button.</span></span>  
  
 <span data-ttu-id="05819-107">Un identificatore noto rende più semplice per i dispositivi di assistive technology determinare quali tipi di controlli sono disponibili nell' [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] e come interagire con i controlli.</span><span class="sxs-lookup"><span data-stu-id="05819-107">Having a well-known identifier makes it easier for assistive technology devices to determine what types of controls are available in the [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] and how to interact with the controls.</span></span>  
  
<a name="UI_Automation_Control_Type_Requisites"></a>
## <a name="ui-automation-control-type-requisites"></a><span data-ttu-id="05819-108">Requisiti per i tipi di controllo per l'automazione dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="05819-108">UI Automation Control Type Requisites</span></span>  
 <span data-ttu-id="05819-109">I tipi di controllo per l'[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] forniscono una serie di condizioni che i provider devono soddisfare.</span><span class="sxs-lookup"><span data-stu-id="05819-109">[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] control types provide a set of conditions that providers must meet.</span></span> <span data-ttu-id="05819-110">Se queste condizioni sono soddisfatte, il controllo può usare il nome del tipo di controllo specifico.</span><span class="sxs-lookup"><span data-stu-id="05819-110">When these conditions are met, the control can use the specific control type name.</span></span> <span data-ttu-id="05819-111">Per tutti i tipi di controllo esistono condizioni relative agli aspetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="05819-111">Each control type has conditions for the following:</span></span>  
  
- <span data-ttu-id="05819-112">Pattern di controllo dell'[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] : i pattern di controllo devono essere supportati, i pattern facoltativi e quelli che non devono essere supportati dal controllo.</span><span class="sxs-lookup"><span data-stu-id="05819-112">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] control patterns—which control patterns must be supported, which control patterns are optional, and which control patterns must not be supported by the control.</span></span>  
  
- <span data-ttu-id="05819-113">Valori di proprietà dell'[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] : valori delle proprietà supportati.</span><span class="sxs-lookup"><span data-stu-id="05819-113">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] property values—which property values are supported.</span></span>  
  
- <span data-ttu-id="05819-114">Struttura ad albero dell'[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] : la struttura ad albero [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] necessaria per il controllo.</span><span class="sxs-lookup"><span data-stu-id="05819-114">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree structure—the required [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree structure for the control.</span></span>  
  
 <span data-ttu-id="05819-115">Se un controllo soddisfa le condizioni per un particolare tipo di controllo, il valore della proprietà <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> corrisponderà a tale tipo.</span><span class="sxs-lookup"><span data-stu-id="05819-115">When a control meets the conditions for a particular control type, the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> property value will indicate that control type.</span></span>  
  
<a name="Current_UI_Automation_Control_Types"></a>
## <a name="current-ui-automation-control-types"></a><span data-ttu-id="05819-116">Tipi di controllo correnti per l'automazione dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="05819-116">Current UI Automation Control Types</span></span>  
 <span data-ttu-id="05819-117">Nell'elenco seguente è riportato il set corrente di tipi di controllo per l' [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="05819-117">The following list contains the current set of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] control types:</span></span>  
  
- [<span data-ttu-id="05819-118">Supporto per automazione interfaccia utente del tipo di controllo Button</span><span class="sxs-lookup"><span data-stu-id="05819-118">UI Automation Support for the Button Control Type</span></span>](ui-automation-support-for-the-button-control-type.md)  
  
- [<span data-ttu-id="05819-119">Supporto di automazione interfaccia utente per il tipo di controllo Calendar</span><span class="sxs-lookup"><span data-stu-id="05819-119">UI Automation Support for the Calendar Control Type</span></span>](ui-automation-support-for-the-calendar-control-type.md)  
  
- [<span data-ttu-id="05819-120">Supporto di automazione interfaccia utente per il tipo di controllo CheckBox</span><span class="sxs-lookup"><span data-stu-id="05819-120">UI Automation Support for the CheckBox Control Type</span></span>](ui-automation-support-for-the-checkbox-control-type.md)  
  
- [<span data-ttu-id="05819-121">Supporto di automazione interfaccia utente per il tipo di controllo ComboBox</span><span class="sxs-lookup"><span data-stu-id="05819-121">UI Automation Support for the ComboBox Control Type</span></span>](ui-automation-support-for-the-combobox-control-type.md)  
  
- [<span data-ttu-id="05819-122">Supporto di automazione interfaccia utente per il tipo di controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="05819-122">UI Automation Support for the DataGrid Control Type</span></span>](ui-automation-support-for-the-datagrid-control-type.md)  
  
- [<span data-ttu-id="05819-123">Supporto per automazione interfaccia utente del tipo di controllo DataItem</span><span class="sxs-lookup"><span data-stu-id="05819-123">UI Automation Support for the DataItem Control Type</span></span>](ui-automation-support-for-the-dataitem-control-type.md)  
  
- [<span data-ttu-id="05819-124">Supporto di automazione interfaccia utente per il tipo di controllo Document</span><span class="sxs-lookup"><span data-stu-id="05819-124">UI Automation Support for the Document Control Type</span></span>](ui-automation-support-for-the-document-control-type.md)  
  
- [<span data-ttu-id="05819-125">Supporto di automazione interfaccia utente per il tipo di controllo Edit</span><span class="sxs-lookup"><span data-stu-id="05819-125">UI Automation Support for the Edit Control Type</span></span>](ui-automation-support-for-the-edit-control-type.md)  
  
- [<span data-ttu-id="05819-126">Supporto per automazione interfaccia utente del tipo di controllo Group</span><span class="sxs-lookup"><span data-stu-id="05819-126">UI Automation Support for the Group Control Type</span></span>](ui-automation-support-for-the-group-control-type.md)  
  
- [<span data-ttu-id="05819-127">Supporto di automazione interfaccia utente per il tipo di controllo Header</span><span class="sxs-lookup"><span data-stu-id="05819-127">UI Automation Support for the Header Control Type</span></span>](ui-automation-support-for-the-header-control-type.md)  
  
- [<span data-ttu-id="05819-128">Supporto per automazione interfaccia utente del tipo di controllo HeaderItem</span><span class="sxs-lookup"><span data-stu-id="05819-128">UI Automation Support for the HeaderItem Control Type</span></span>](ui-automation-support-for-the-headeritem-control-type.md)  
  
- [<span data-ttu-id="05819-129">Supporto per automazione interfaccia utente del tipo di controllo Hyperlink</span><span class="sxs-lookup"><span data-stu-id="05819-129">UI Automation Support for the Hyperlink Control Type</span></span>](ui-automation-support-for-the-hyperlink-control-type.md)  
  
- [<span data-ttu-id="05819-130">Supporto per automazione interfaccia utente del tipo di controllo Image</span><span class="sxs-lookup"><span data-stu-id="05819-130">UI Automation Support for the Image Control Type</span></span>](ui-automation-support-for-the-image-control-type.md)  
  
- [<span data-ttu-id="05819-131">Supporto per automazione interfaccia utente del tipo di controllo List</span><span class="sxs-lookup"><span data-stu-id="05819-131">UI Automation Support for the List Control Type</span></span>](ui-automation-support-for-the-list-control-type.md)  
  
- [<span data-ttu-id="05819-132">Supporto per automazione interfaccia utente del tipo di controllo ListItem</span><span class="sxs-lookup"><span data-stu-id="05819-132">UI Automation Support for the ListItem Control Type</span></span>](ui-automation-support-for-the-listitem-control-type.md)  
  
- [<span data-ttu-id="05819-133">Supporto per l'automazione dell'interfaccia utente del tipo di controllo Menu</span><span class="sxs-lookup"><span data-stu-id="05819-133">UI Automation Support for the Menu Control Type</span></span>](ui-automation-support-for-the-menu-control-type.md)  
  
- [<span data-ttu-id="05819-134">Supporto di automazione interfaccia utente per il tipo di controllo MenuBar</span><span class="sxs-lookup"><span data-stu-id="05819-134">UI Automation Support for the MenuBar Control Type</span></span>](ui-automation-support-for-the-menubar-control-type.md)  
  
- [<span data-ttu-id="05819-135">Supporto per automazione interfaccia utente del tipo di controllo MenuItem</span><span class="sxs-lookup"><span data-stu-id="05819-135">UI Automation Support for the MenuItem Control Type</span></span>](ui-automation-support-for-the-menuitem-control-type.md)  
  
- [<span data-ttu-id="05819-136">Supporto di automazione interfaccia utente per il tipo di controllo Pane</span><span class="sxs-lookup"><span data-stu-id="05819-136">UI Automation Support for the Pane Control Type</span></span>](ui-automation-support-for-the-pane-control-type.md)  
  
- [<span data-ttu-id="05819-137">Supporto per automazione interfaccia utente del tipo di controllo ProgressBar</span><span class="sxs-lookup"><span data-stu-id="05819-137">UI Automation Support for the ProgressBar Control Type</span></span>](ui-automation-support-for-the-progressbar-control-type.md)  
  
- [<span data-ttu-id="05819-138">Supporto di automazione interfaccia utente per il tipo di controllo RadioButton</span><span class="sxs-lookup"><span data-stu-id="05819-138">UI Automation Support for the RadioButton Control Type</span></span>](ui-automation-support-for-the-radiobutton-control-type.md)  
  
- [<span data-ttu-id="05819-139">Supporto per automazione interfaccia utente del tipo di controllo ScrollBar</span><span class="sxs-lookup"><span data-stu-id="05819-139">UI Automation Support for the ScrollBar Control Type</span></span>](ui-automation-support-for-the-scrollbar-control-type.md)  
  
- [<span data-ttu-id="05819-140">Supporto per l'automazione interfaccia utente del tipo di controllo Separator</span><span class="sxs-lookup"><span data-stu-id="05819-140">UI Automation Support for the Separator Control Type</span></span>](ui-automation-support-for-the-separator-control-type.md)  
  
- [<span data-ttu-id="05819-141">Supporto per automazione interfaccia utente del tipo di controllo Slider</span><span class="sxs-lookup"><span data-stu-id="05819-141">UI Automation Support for the Slider Control Type</span></span>](ui-automation-support-for-the-slider-control-type.md)  
  
- [<span data-ttu-id="05819-142">Supporto per automazione interfaccia utente del tipo di controllo Spinner</span><span class="sxs-lookup"><span data-stu-id="05819-142">UI Automation Support for the Spinner Control Type</span></span>](ui-automation-support-for-the-spinner-control-type.md)  
  
- [<span data-ttu-id="05819-143">Supporto per l'automazione interfaccia utente del tipo di controllo SplitButton</span><span class="sxs-lookup"><span data-stu-id="05819-143">UI Automation Support for the SplitButton Control Type</span></span>](ui-automation-support-for-the-splitbutton-control-type.md)  
  
- [<span data-ttu-id="05819-144">Supporto per automazione interfaccia utente del tipo di controllo StatusBar</span><span class="sxs-lookup"><span data-stu-id="05819-144">UI Automation Support for the StatusBar Control Type</span></span>](ui-automation-support-for-the-statusbar-control-type.md)  
  
- [<span data-ttu-id="05819-145">Supporto di automazione interfaccia utente per il tipo di controllo Tab</span><span class="sxs-lookup"><span data-stu-id="05819-145">UI Automation Support for the Tab Control Type</span></span>](ui-automation-support-for-the-tab-control-type.md)  
  
- [<span data-ttu-id="05819-146">Supporto di automazione interfaccia utente per il tipo di controllo TabItem</span><span class="sxs-lookup"><span data-stu-id="05819-146">UI Automation Support for the TabItem Control Type</span></span>](ui-automation-support-for-the-tabitem-control-type.md)  
  
- [<span data-ttu-id="05819-147">Supporto per automazione interfaccia utente del tipo di controllo Table</span><span class="sxs-lookup"><span data-stu-id="05819-147">UI Automation Support for the Table Control Type</span></span>](ui-automation-support-for-the-table-control-type.md)  
  
- [<span data-ttu-id="05819-148">Supporto di automazione interfaccia utente per il tipo di controllo Text</span><span class="sxs-lookup"><span data-stu-id="05819-148">UI Automation Support for the Text Control Type</span></span>](ui-automation-support-for-the-text-control-type.md)  
  
- [<span data-ttu-id="05819-149">Supporto per l'automazione interfaccia utente del tipo di controllo Thumb</span><span class="sxs-lookup"><span data-stu-id="05819-149">UI Automation Support for the Thumb Control Type</span></span>](ui-automation-support-for-the-thumb-control-type.md)  
  
- [<span data-ttu-id="05819-150">Supporto per l'automazione interfaccia utente del tipo di controllo TitleBar</span><span class="sxs-lookup"><span data-stu-id="05819-150">UI Automation Support for the TitleBar Control Type</span></span>](ui-automation-support-for-the-titlebar-control-type.md)  
  
- [<span data-ttu-id="05819-151">Supporto per l'automazione interfaccia utente del tipo di controllo ToolBar</span><span class="sxs-lookup"><span data-stu-id="05819-151">UI Automation Support for the ToolBar Control Type</span></span>](ui-automation-support-for-the-toolbar-control-type.md)  
  
- [<span data-ttu-id="05819-152">Supporto per l'automazione dell'interfaccia utente del tipo di controllo ToolTip</span><span class="sxs-lookup"><span data-stu-id="05819-152">UI Automation Support for the ToolTip Control Type</span></span>](ui-automation-support-for-the-tooltip-control-type.md)  
  
- [<span data-ttu-id="05819-153">Supporto per automazione interfaccia utente del tipo di controllo Tree</span><span class="sxs-lookup"><span data-stu-id="05819-153">UI Automation Support for the Tree Control Type</span></span>](ui-automation-support-for-the-tree-control-type.md)  
  
- [<span data-ttu-id="05819-154">Supporto per automazione interfaccia utente del tipo di controllo TreeItem</span><span class="sxs-lookup"><span data-stu-id="05819-154">UI Automation Support for the TreeItem Control Type</span></span>](ui-automation-support-for-the-treeitem-control-type.md)  
  
- [<span data-ttu-id="05819-155">Supporto per l'automazione interfaccia utente del tipo di controllo Window</span><span class="sxs-lookup"><span data-stu-id="05819-155">UI Automation Support for the Window Control Type</span></span>](ui-automation-support-for-the-window-control-type.md)  
  
## <a name="see-also"></a><span data-ttu-id="05819-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05819-156">See also</span></span>

- <xref:System.Windows.Automation.ControlType>
