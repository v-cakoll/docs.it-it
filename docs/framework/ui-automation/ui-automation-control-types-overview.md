---
title: Cenni preliminari sui tipi di controllo per l'automazione interfaccia utente
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, control types
- control types, UI Automation
ms.assetid: 75159ef8-bd43-4d13-acb7-1f1fe9253160
ms.openlocfilehash: e9cbff2ec6496cabe827e075b737a8c6f16fee93
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59147719"
---
# <a name="ui-automation-control-types-overview"></a><span data-ttu-id="aacc6-102">Cenni preliminari sui tipi di controllo per l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="aacc6-102">UI Automation Control Types Overview</span></span>
> [!NOTE]
>  <span data-ttu-id="aacc6-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="aacc6-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="aacc6-104">Per informazioni aggiornate sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: Automazione interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="aacc6-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] <span data-ttu-id="aacc6-105">tipi di controllo sono identificatori noti che possono essere utilizzati per indicare quale tipo di controllo un particolare elemento rappresentato, ad esempio una casella combinata o un pulsante.</span><span class="sxs-lookup"><span data-stu-id="aacc6-105">control types are well-known identifiers that can be used to indicate what kind of control a particular element represents, such as a combo box or a button.</span></span>  
  
 <span data-ttu-id="aacc6-106">Un identificatore noto rende più semplice per i dispositivi di assistive technology determinare quali tipi di controlli sono disponibili nell' [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] e come interagire con i controlli.</span><span class="sxs-lookup"><span data-stu-id="aacc6-106">Having a well-known identifier makes it easier for assistive technology devices to determine what types of controls are available in the [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] and how to interact with the controls.</span></span>  
  
<a name="UI_Automation_Control_Type_Requisites"></a>   
## <a name="ui-automation-control-type-requisites"></a><span data-ttu-id="aacc6-107">Requisiti per i tipi di controllo per l'automazione dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="aacc6-107">UI Automation Control Type Requisites</span></span>  
 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] <span data-ttu-id="aacc6-108">tipi di controllo offrono un set di condizioni che i provider devono soddisfare.</span><span class="sxs-lookup"><span data-stu-id="aacc6-108">control types provide a set of conditions that providers must meet.</span></span> <span data-ttu-id="aacc6-109">Se queste condizioni sono soddisfatte, il controllo può usare il nome del tipo di controllo specifico.</span><span class="sxs-lookup"><span data-stu-id="aacc6-109">When these conditions are met, the control can use the specific control type name.</span></span> <span data-ttu-id="aacc6-110">Per tutti i tipi di controllo esistono condizioni relative agli aspetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="aacc6-110">Each control type has conditions for the following:</span></span>  
  
-   [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] <span data-ttu-id="aacc6-111">pattern di controllo, ovvero i pattern di controllo devono essere supportati, quale controllo sono facoltativi e i pattern di controllo non devono essere supportati dal controllo.</span><span class="sxs-lookup"><span data-stu-id="aacc6-111">control patterns—which control patterns must be supported, which control patterns are optional, and which control patterns must not be supported by the control.</span></span>  
  
-   [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] <span data-ttu-id="aacc6-112">i valori delle proprietà, sono supportati i valori della proprietà.</span><span class="sxs-lookup"><span data-stu-id="aacc6-112">property values—which property values are supported.</span></span>  
  
-   [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] <span data-ttu-id="aacc6-113">struttura ad albero, ovvero la necessaria [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] struttura ad albero per il controllo.</span><span class="sxs-lookup"><span data-stu-id="aacc6-113">tree structure—the required [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree structure for the control.</span></span>  
  
 <span data-ttu-id="aacc6-114">Se un controllo soddisfa le condizioni per un particolare tipo di controllo, il valore della proprietà <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> corrisponderà a tale tipo.</span><span class="sxs-lookup"><span data-stu-id="aacc6-114">When a control meets the conditions for a particular control type, the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> property value will indicate that control type.</span></span>  
  
<a name="Current_UI_Automation_Control_Types"></a>   
## <a name="current-ui-automation-control-types"></a><span data-ttu-id="aacc6-115">Tipi di controllo correnti per l'automazione dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="aacc6-115">Current UI Automation Control Types</span></span>  
 <span data-ttu-id="aacc6-116">Nell'elenco seguente è riportato il set corrente di tipi di controllo per l' [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="aacc6-116">The following list contains the current set of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] control types:</span></span>  
  
-   [<span data-ttu-id="aacc6-117">Supporto per automazione interfaccia utente del tipo di controllo Button</span><span class="sxs-lookup"><span data-stu-id="aacc6-117">UI Automation Support for the Button Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-button-control-type.md)  
  
-   [<span data-ttu-id="aacc6-118">Supporto di automazione interfaccia utente per il tipo di controllo Calendar</span><span class="sxs-lookup"><span data-stu-id="aacc6-118">UI Automation Support for the Calendar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-calendar-control-type.md)  
  
-   [<span data-ttu-id="aacc6-119">Supporto di automazione interfaccia utente per il tipo di controllo CheckBox</span><span class="sxs-lookup"><span data-stu-id="aacc6-119">UI Automation Support for the CheckBox Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-checkbox-control-type.md)  
  
-   [<span data-ttu-id="aacc6-120">Supporto di automazione interfaccia utente per il tipo di controllo ComboBox</span><span class="sxs-lookup"><span data-stu-id="aacc6-120">UI Automation Support for the ComboBox Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-combobox-control-type.md)  
  
-   [<span data-ttu-id="aacc6-121">Supporto di automazione interfaccia utente per il tipo di controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="aacc6-121">UI Automation Support for the DataGrid Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-datagrid-control-type.md)  
  
-   [<span data-ttu-id="aacc6-122">Supporto per automazione interfaccia utente del tipo di controllo DataItem</span><span class="sxs-lookup"><span data-stu-id="aacc6-122">UI Automation Support for the DataItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-dataitem-control-type.md)  
  
-   [<span data-ttu-id="aacc6-123">Supporto di automazione interfaccia utente per il tipo di controllo Document</span><span class="sxs-lookup"><span data-stu-id="aacc6-123">UI Automation Support for the Document Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-document-control-type.md)  
  
-   [<span data-ttu-id="aacc6-124">Supporto di automazione interfaccia utente per il tipo di controllo Edit</span><span class="sxs-lookup"><span data-stu-id="aacc6-124">UI Automation Support for the Edit Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-edit-control-type.md)  
  
-   [<span data-ttu-id="aacc6-125">Supporto per automazione interfaccia utente del tipo di controllo Group</span><span class="sxs-lookup"><span data-stu-id="aacc6-125">UI Automation Support for the Group Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-group-control-type.md)  
  
-   [<span data-ttu-id="aacc6-126">Supporto di automazione interfaccia utente per il tipo di controllo Header</span><span class="sxs-lookup"><span data-stu-id="aacc6-126">UI Automation Support for the Header Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-header-control-type.md)  
  
-   [<span data-ttu-id="aacc6-127">Supporto per automazione interfaccia utente del tipo di controllo HeaderItem</span><span class="sxs-lookup"><span data-stu-id="aacc6-127">UI Automation Support for the HeaderItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-headeritem-control-type.md)  
  
-   [<span data-ttu-id="aacc6-128">Supporto per automazione interfaccia utente del tipo di controllo Hyperlink</span><span class="sxs-lookup"><span data-stu-id="aacc6-128">UI Automation Support for the Hyperlink Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-hyperlink-control-type.md)  
  
-   [<span data-ttu-id="aacc6-129">Supporto per automazione interfaccia utente del tipo di controllo Image</span><span class="sxs-lookup"><span data-stu-id="aacc6-129">UI Automation Support for the Image Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-image-control-type.md)  
  
-   [<span data-ttu-id="aacc6-130">Supporto per automazione interfaccia utente del tipo di controllo List</span><span class="sxs-lookup"><span data-stu-id="aacc6-130">UI Automation Support for the List Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-list-control-type.md)  
  
-   [<span data-ttu-id="aacc6-131">Supporto per automazione interfaccia utente del tipo di controllo ListItem</span><span class="sxs-lookup"><span data-stu-id="aacc6-131">UI Automation Support for the ListItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-listitem-control-type.md)  
  
-   [<span data-ttu-id="aacc6-132">Supporto per l'automazione dell'interfaccia utente del tipo di controllo Menu</span><span class="sxs-lookup"><span data-stu-id="aacc6-132">UI Automation Support for the Menu Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-menu-control-type.md)  
  
-   [<span data-ttu-id="aacc6-133">Supporto di automazione interfaccia utente per il tipo di controllo MenuBar</span><span class="sxs-lookup"><span data-stu-id="aacc6-133">UI Automation Support for the MenuBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md)  
  
-   [<span data-ttu-id="aacc6-134">Supporto per automazione interfaccia utente del tipo di controllo MenuItem</span><span class="sxs-lookup"><span data-stu-id="aacc6-134">UI Automation Support for the MenuItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-menuitem-control-type.md)  
  
-   [<span data-ttu-id="aacc6-135">Supporto di automazione interfaccia utente per il tipo di controllo Pane</span><span class="sxs-lookup"><span data-stu-id="aacc6-135">UI Automation Support for the Pane Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-pane-control-type.md)  
  
-   [<span data-ttu-id="aacc6-136">Supporto per automazione interfaccia utente del tipo di controllo ProgressBar</span><span class="sxs-lookup"><span data-stu-id="aacc6-136">UI Automation Support for the ProgressBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-progressbar-control-type.md)  
  
-   [<span data-ttu-id="aacc6-137">Supporto di automazione interfaccia utente per il tipo di controllo RadioButton</span><span class="sxs-lookup"><span data-stu-id="aacc6-137">UI Automation Support for the RadioButton Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-radiobutton-control-type.md)  
  
-   [<span data-ttu-id="aacc6-138">Supporto per automazione interfaccia utente del tipo di controllo ScrollBar</span><span class="sxs-lookup"><span data-stu-id="aacc6-138">UI Automation Support for the ScrollBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-scrollbar-control-type.md)  
  
-   [<span data-ttu-id="aacc6-139">Supporto per l'automazione interfaccia utente del tipo di controllo Separator</span><span class="sxs-lookup"><span data-stu-id="aacc6-139">UI Automation Support for the Separator Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-separator-control-type.md)  
  
-   [<span data-ttu-id="aacc6-140">Supporto per automazione interfaccia utente del tipo di controllo Slider</span><span class="sxs-lookup"><span data-stu-id="aacc6-140">UI Automation Support for the Slider Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-slider-control-type.md)  
  
-   [<span data-ttu-id="aacc6-141">Supporto per automazione interfaccia utente del tipo di controllo Spinner</span><span class="sxs-lookup"><span data-stu-id="aacc6-141">UI Automation Support for the Spinner Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-spinner-control-type.md)  
  
-   [<span data-ttu-id="aacc6-142">Supporto per l'automazione interfaccia utente del tipo di controllo SplitButton</span><span class="sxs-lookup"><span data-stu-id="aacc6-142">UI Automation Support for the SplitButton Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-splitbutton-control-type.md)  
  
-   [<span data-ttu-id="aacc6-143">Supporto per automazione interfaccia utente del tipo di controllo StatusBar</span><span class="sxs-lookup"><span data-stu-id="aacc6-143">UI Automation Support for the StatusBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-statusbar-control-type.md)  
  
-   [<span data-ttu-id="aacc6-144">Supporto di automazione interfaccia utente per il tipo di controllo Tab</span><span class="sxs-lookup"><span data-stu-id="aacc6-144">UI Automation Support for the Tab Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-tab-control-type.md)  
  
-   [<span data-ttu-id="aacc6-145">Supporto di automazione interfaccia utente per il tipo di controllo TabItem</span><span class="sxs-lookup"><span data-stu-id="aacc6-145">UI Automation Support for the TabItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-tabitem-control-type.md)  
  
-   [<span data-ttu-id="aacc6-146">Supporto per automazione interfaccia utente del tipo di controllo Table</span><span class="sxs-lookup"><span data-stu-id="aacc6-146">UI Automation Support for the Table Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-table-control-type.md)  
  
-   [<span data-ttu-id="aacc6-147">Supporto di automazione interfaccia utente per il tipo di controllo Text</span><span class="sxs-lookup"><span data-stu-id="aacc6-147">UI Automation Support for the Text Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-text-control-type.md)  
  
-   [<span data-ttu-id="aacc6-148">Supporto per l'automazione interfaccia utente del tipo di controllo Thumb</span><span class="sxs-lookup"><span data-stu-id="aacc6-148">UI Automation Support for the Thumb Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-thumb-control-type.md)  
  
-   [<span data-ttu-id="aacc6-149">Supporto per l'automazione interfaccia utente del tipo di controllo TitleBar</span><span class="sxs-lookup"><span data-stu-id="aacc6-149">UI Automation Support for the TitleBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-titlebar-control-type.md)  
  
-   [<span data-ttu-id="aacc6-150">Supporto per l'automazione interfaccia utente del tipo di controllo ToolBar</span><span class="sxs-lookup"><span data-stu-id="aacc6-150">UI Automation Support for the ToolBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-toolbar-control-type.md)  
  
-   [<span data-ttu-id="aacc6-151">Supporto per l'automazione dell'interfaccia utente del tipo di controllo ToolTip</span><span class="sxs-lookup"><span data-stu-id="aacc6-151">UI Automation Support for the ToolTip Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-tooltip-control-type.md)  
  
-   [<span data-ttu-id="aacc6-152">Supporto per automazione interfaccia utente del tipo di controllo Tree</span><span class="sxs-lookup"><span data-stu-id="aacc6-152">UI Automation Support for the Tree Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-tree-control-type.md)  
  
-   [<span data-ttu-id="aacc6-153">Supporto per automazione interfaccia utente del tipo di controllo TreeItem</span><span class="sxs-lookup"><span data-stu-id="aacc6-153">UI Automation Support for the TreeItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-treeitem-control-type.md)  
  
-   [<span data-ttu-id="aacc6-154">Supporto per l'automazione interfaccia utente del tipo di controllo Window</span><span class="sxs-lookup"><span data-stu-id="aacc6-154">UI Automation Support for the Window Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-window-control-type.md)  
  
## <a name="see-also"></a><span data-ttu-id="aacc6-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aacc6-155">See also</span></span>

- <xref:System.Windows.Automation.ControlType>
