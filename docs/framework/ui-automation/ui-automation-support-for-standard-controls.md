---
title: Supporto per automazione interfaccia utente dei controlli standard
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: c59352f908c5f4a1fd2ca6dd631d26bb5d69f09a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441218"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="b197b-102">Supporto per automazione interfaccia utente dei controlli standard</span><span class="sxs-lookup"><span data-stu-id="b197b-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="b197b-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="b197b-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="b197b-104">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere l'argomento sull' [API Automazione interfaccia utente di Windows](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="b197b-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="b197b-105">Questo argomento contiene informazioni sul supporto di [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] per i controlli standard in applicazioni sviluppate per i framework [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]e [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b197b-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="b197b-106">Controlli WPF (Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="b197b-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="b197b-107">Tutti gli elementi di controllo [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] che forniscono informazioni o supporto per l'interazione dell'utente dispongono di supporto nativo completo per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b197b-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="b197b-108">Gli altri elementi, ad esempio i pannelli, non sono visibile per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b197b-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="b197b-109">Controlli Win32</span><span class="sxs-lookup"><span data-stu-id="b197b-109">Win32 Controls</span></span>  
 <span data-ttu-id="b197b-110">La maggior parte dei controlli [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] è esposta a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tramite provider lato client in UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="b197b-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="b197b-111">Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="b197b-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="b197b-112">Il supporto completo viene fornito solo per i controlli a partire dalla versione 6 di ComCtrl32.dll (disponibile con [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] e versioni successive).</span><span class="sxs-lookup"><span data-stu-id="b197b-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="b197b-113">I controlli seguenti sono supportati.</span><span class="sxs-lookup"><span data-stu-id="b197b-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="b197b-114">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="b197b-114">Class name</span></span>|<span data-ttu-id="b197b-115">Tipo di controllo</span><span class="sxs-lookup"><span data-stu-id="b197b-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="b197b-116">Button</span><span class="sxs-lookup"><span data-stu-id="b197b-116">Button</span></span>|<span data-ttu-id="b197b-117">Button</span><span class="sxs-lookup"><span data-stu-id="b197b-117">Button</span></span>|  
|<span data-ttu-id="b197b-118">Button</span><span class="sxs-lookup"><span data-stu-id="b197b-118">Button</span></span>|<span data-ttu-id="b197b-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="b197b-119">RadioButton</span></span>|  
|<span data-ttu-id="b197b-120">Button</span><span class="sxs-lookup"><span data-stu-id="b197b-120">Button</span></span>|<span data-ttu-id="b197b-121">Raggruppa</span><span class="sxs-lookup"><span data-stu-id="b197b-121">Group</span></span>|  
|<span data-ttu-id="b197b-122">Button</span><span class="sxs-lookup"><span data-stu-id="b197b-122">Button</span></span>|<span data-ttu-id="b197b-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="b197b-123">CheckBox</span></span>|  
|<span data-ttu-id="b197b-124">Button</span><span class="sxs-lookup"><span data-stu-id="b197b-124">Button</span></span>|<span data-ttu-id="b197b-125">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="b197b-125">Hyperlink</span></span>|  
|<span data-ttu-id="b197b-126">Button</span><span class="sxs-lookup"><span data-stu-id="b197b-126">Button</span></span>|<span data-ttu-id="b197b-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="b197b-127">SplitButton</span></span>|  
|<span data-ttu-id="b197b-128">Button</span><span class="sxs-lookup"><span data-stu-id="b197b-128">Button</span></span>|<span data-ttu-id="b197b-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="b197b-129">CheckBox</span></span>|  
|<span data-ttu-id="b197b-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="b197b-130">ComboBoxEx32</span></span>|<span data-ttu-id="b197b-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="b197b-131">ComboBox</span></span>|  
|<span data-ttu-id="b197b-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="b197b-132">ComboBox</span></span>|<span data-ttu-id="b197b-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="b197b-133">ComboBox</span></span>|  
|<span data-ttu-id="b197b-134">Edit</span><span class="sxs-lookup"><span data-stu-id="b197b-134">Edit</span></span>|<span data-ttu-id="b197b-135">Document</span><span class="sxs-lookup"><span data-stu-id="b197b-135">Document</span></span>|  
|<span data-ttu-id="b197b-136">Edit</span><span class="sxs-lookup"><span data-stu-id="b197b-136">Edit</span></span>|<span data-ttu-id="b197b-137">Edit</span><span class="sxs-lookup"><span data-stu-id="b197b-137">Edit</span></span>|  
|<span data-ttu-id="b197b-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="b197b-138">SysLink</span></span>|<span data-ttu-id="b197b-139">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="b197b-139">Hyperlink</span></span>|  
|<span data-ttu-id="b197b-140">Static</span><span class="sxs-lookup"><span data-stu-id="b197b-140">Static</span></span>|<span data-ttu-id="b197b-141">Testo</span><span class="sxs-lookup"><span data-stu-id="b197b-141">Text</span></span>|  
|<span data-ttu-id="b197b-142">Static</span><span class="sxs-lookup"><span data-stu-id="b197b-142">Static</span></span>|<span data-ttu-id="b197b-143">Immagine</span><span class="sxs-lookup"><span data-stu-id="b197b-143">Image</span></span>|  
|<span data-ttu-id="b197b-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="b197b-144">SysIPAddress32</span></span>|<span data-ttu-id="b197b-145">Custom (Personalizzati)</span><span class="sxs-lookup"><span data-stu-id="b197b-145">Custom</span></span>|  
|<span data-ttu-id="b197b-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="b197b-146">SysHeader32</span></span>|<span data-ttu-id="b197b-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="b197b-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="b197b-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="b197b-148">SysListView32</span></span>|<span data-ttu-id="b197b-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="b197b-149">DataGrid</span></span>|  
|<span data-ttu-id="b197b-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="b197b-150">SysListView32</span></span>|<span data-ttu-id="b197b-151">List</span><span class="sxs-lookup"><span data-stu-id="b197b-151">List</span></span>|  
|<span data-ttu-id="b197b-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="b197b-152">ListBox</span></span>|<span data-ttu-id="b197b-153">List</span><span class="sxs-lookup"><span data-stu-id="b197b-153">List</span></span>|  
|<span data-ttu-id="b197b-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="b197b-154">ListBox</span></span>|<span data-ttu-id="b197b-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="b197b-155">ListItem</span></span>|  
|<span data-ttu-id="b197b-156">#32768</span><span class="sxs-lookup"><span data-stu-id="b197b-156">#32768</span></span>|<span data-ttu-id="b197b-157">Menu</span><span class="sxs-lookup"><span data-stu-id="b197b-157">Menu</span></span>|  
|<span data-ttu-id="b197b-158">#32768</span><span class="sxs-lookup"><span data-stu-id="b197b-158">#32768</span></span>|<span data-ttu-id="b197b-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="b197b-159">MenuItem</span></span>|  
|<span data-ttu-id="b197b-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="b197b-160">msctls_progress32</span></span>|<span data-ttu-id="b197b-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="b197b-161">ProgressBar</span></span>|  
|<span data-ttu-id="b197b-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="b197b-162">RichEdit</span></span>|<span data-ttu-id="b197b-163">Document</span><span class="sxs-lookup"><span data-stu-id="b197b-163">Document.</span></span> <span data-ttu-id="b197b-164">Vedere la nota.</span><span class="sxs-lookup"><span data-stu-id="b197b-164">See note.</span></span>|  
|<span data-ttu-id="b197b-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="b197b-165">RichEdit20A</span></span>|<span data-ttu-id="b197b-166">Document</span><span class="sxs-lookup"><span data-stu-id="b197b-166">Document</span></span>|  
|<span data-ttu-id="b197b-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="b197b-167">RichEdit20W</span></span>|<span data-ttu-id="b197b-168">Document</span><span class="sxs-lookup"><span data-stu-id="b197b-168">Document</span></span>|  
|<span data-ttu-id="b197b-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="b197b-169">RichEdit50W</span></span>|<span data-ttu-id="b197b-170">Document</span><span class="sxs-lookup"><span data-stu-id="b197b-170">Document</span></span>|  
|<span data-ttu-id="b197b-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="b197b-171">ScrollBar</span></span>|<span data-ttu-id="b197b-172">Slider</span><span class="sxs-lookup"><span data-stu-id="b197b-172">Slider</span></span>|  
|<span data-ttu-id="b197b-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="b197b-173">msctls_trackbar32</span></span>|<span data-ttu-id="b197b-174">Slider</span><span class="sxs-lookup"><span data-stu-id="b197b-174">Slider</span></span>|  
|<span data-ttu-id="b197b-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="b197b-175">msctls_updown32</span></span>|<span data-ttu-id="b197b-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="b197b-176">Spinner</span></span>|  
|<span data-ttu-id="b197b-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="b197b-177">msctls_statusbar32</span></span>|<span data-ttu-id="b197b-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="b197b-178">StatusBar</span></span>|  
|<span data-ttu-id="b197b-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="b197b-179">SysTabControl32</span></span>|<span data-ttu-id="b197b-180">Scheda</span><span class="sxs-lookup"><span data-stu-id="b197b-180">Tab</span></span>|  
|<span data-ttu-id="b197b-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="b197b-181">SysTabControl32</span></span>|<span data-ttu-id="b197b-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="b197b-182">TabItem</span></span>|  
|<span data-ttu-id="b197b-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="b197b-183">ToolbarWindow32</span></span>|<span data-ttu-id="b197b-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="b197b-184">ToolBar</span></span>|  
|<span data-ttu-id="b197b-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="b197b-185">ToolbarWindow32</span></span>|<span data-ttu-id="b197b-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="b197b-186">MenuItem</span></span>|  
|<span data-ttu-id="b197b-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="b197b-187">ToolbarWindow32</span></span>|<span data-ttu-id="b197b-188">Button</span><span class="sxs-lookup"><span data-stu-id="b197b-188">Button</span></span>|  
|<span data-ttu-id="b197b-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="b197b-189">ToolbarWindow32</span></span>|<span data-ttu-id="b197b-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="b197b-190">CheckBox</span></span>|  
|<span data-ttu-id="b197b-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="b197b-191">ToolbarWindow32</span></span>|<span data-ttu-id="b197b-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="b197b-192">RadioButton</span></span>|  
|<span data-ttu-id="b197b-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="b197b-193">ToolbarWindow32</span></span>|<span data-ttu-id="b197b-194">Separator</span><span class="sxs-lookup"><span data-stu-id="b197b-194">Separator</span></span>|  
|<span data-ttu-id="b197b-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="b197b-195">tooltips_class32</span></span>|<span data-ttu-id="b197b-196">ToolTip</span><span class="sxs-lookup"><span data-stu-id="b197b-196">ToolTip</span></span>|  
|<span data-ttu-id="b197b-197">#32774</span><span class="sxs-lookup"><span data-stu-id="b197b-197">#32774</span></span>|<span data-ttu-id="b197b-198">ToolTip</span><span class="sxs-lookup"><span data-stu-id="b197b-198">ToolTip</span></span>|  
|<span data-ttu-id="b197b-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="b197b-199">ReBarWindow32</span></span>|<span data-ttu-id="b197b-200">ToolBar</span><span class="sxs-lookup"><span data-stu-id="b197b-200">Toolbar</span></span>|  
|<span data-ttu-id="b197b-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="b197b-201">SysTreeView32</span></span>|<span data-ttu-id="b197b-202">Struttura ad albero</span><span class="sxs-lookup"><span data-stu-id="b197b-202">Tree</span></span>|  
|<span data-ttu-id="b197b-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="b197b-203">SysTreeView32</span></span>|<span data-ttu-id="b197b-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="b197b-204">TreeItem</span></span>|  
  
 <span data-ttu-id="b197b-205">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span><span class="sxs-lookup"><span data-stu-id="b197b-205">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="b197b-206">I controlli seguenti non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="b197b-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="b197b-207">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="b197b-207">Class name</span></span>|<span data-ttu-id="b197b-208">Tipo di controllo</span><span class="sxs-lookup"><span data-stu-id="b197b-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="b197b-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="b197b-209">SysAnimate32</span></span>|<span data-ttu-id="b197b-210">Immagine</span><span class="sxs-lookup"><span data-stu-id="b197b-210">Image</span></span>|  
|<span data-ttu-id="b197b-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="b197b-211">SysPager</span></span>|<span data-ttu-id="b197b-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="b197b-212">Spinner</span></span>|  
|<span data-ttu-id="b197b-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="b197b-213">SysDateTimePick32</span></span>|<span data-ttu-id="b197b-214">Custom (Personalizzati)</span><span class="sxs-lookup"><span data-stu-id="b197b-214">Custom</span></span>|  
|<span data-ttu-id="b197b-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="b197b-215">SysMonthCal32</span></span>|<span data-ttu-id="b197b-216">Calendar</span><span class="sxs-lookup"><span data-stu-id="b197b-216">Calendar</span></span>|  
|<span data-ttu-id="b197b-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="b197b-217">MS_WINNOTE</span></span>|<span data-ttu-id="b197b-218">ToolTip</span><span class="sxs-lookup"><span data-stu-id="b197b-218">Tooltip</span></span>|  
|<span data-ttu-id="b197b-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="b197b-219">VBBubble</span></span>|<span data-ttu-id="b197b-220">ToolTip</span><span class="sxs-lookup"><span data-stu-id="b197b-220">Tooltip</span></span>|  
|<span data-ttu-id="b197b-221">ScrollBar (se usato come controllo autonomo)</span><span class="sxs-lookup"><span data-stu-id="b197b-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="b197b-222">Slider</span><span class="sxs-lookup"><span data-stu-id="b197b-222">Slider</span></span>|  
|<span data-ttu-id="b197b-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="b197b-223">SuperGrid</span></span>|<span data-ttu-id="b197b-224">Custom (Personalizzati)</span><span class="sxs-lookup"><span data-stu-id="b197b-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="b197b-225">Controlli per Windows Form</span><span class="sxs-lookup"><span data-stu-id="b197b-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="b197b-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="b197b-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="b197b-227">Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="b197b-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="b197b-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b197b-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="b197b-229">I controlli seguenti sono supportati.</span><span class="sxs-lookup"><span data-stu-id="b197b-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="b197b-230">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="b197b-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="b197b-231">Button</span><span class="sxs-lookup"><span data-stu-id="b197b-231">Button</span></span>|  
|<span data-ttu-id="b197b-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="b197b-232">CheckBox</span></span>|  
|<span data-ttu-id="b197b-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="b197b-233">CheckedListBox</span></span>|  
|<span data-ttu-id="b197b-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="b197b-234">ColorDialog</span></span>|  
|<span data-ttu-id="b197b-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="b197b-235">ComboBox</span></span>|  
|<span data-ttu-id="b197b-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="b197b-236">FolderBrowser</span></span>|  
|<span data-ttu-id="b197b-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="b197b-237">FontDialog</span></span>|  
|<span data-ttu-id="b197b-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="b197b-238">GroupBox</span></span>|  
|<span data-ttu-id="b197b-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="b197b-239">HscrollBar</span></span>|  
|<span data-ttu-id="b197b-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="b197b-240">ImageList</span></span>|  
|<span data-ttu-id="b197b-241">Label</span><span class="sxs-lookup"><span data-stu-id="b197b-241">Label</span></span>|  
|<span data-ttu-id="b197b-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="b197b-242">ListBox</span></span>|  
|<span data-ttu-id="b197b-243">ListView</span><span class="sxs-lookup"><span data-stu-id="b197b-243">ListView</span></span>|  
|<span data-ttu-id="b197b-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="b197b-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="b197b-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="b197b-245">MonthCalendar</span></span>|  
|<span data-ttu-id="b197b-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="b197b-246">NotifyIcon</span></span>|  
|<span data-ttu-id="b197b-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="b197b-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="b197b-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="b197b-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="b197b-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="b197b-249">PrintDialog</span></span>|  
|<span data-ttu-id="b197b-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="b197b-250">ProgressBar</span></span>|  
|<span data-ttu-id="b197b-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="b197b-251">RadioButton</span></span>|  
|<span data-ttu-id="b197b-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="b197b-252">RichTextBox</span></span>|  
|<span data-ttu-id="b197b-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="b197b-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="b197b-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="b197b-254">ScrollableControl</span></span>|  
|<span data-ttu-id="b197b-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="b197b-255">SoundPlayer</span></span>|  
|<span data-ttu-id="b197b-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="b197b-256">StatusBar</span></span>|  
|<span data-ttu-id="b197b-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="b197b-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="b197b-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="b197b-258">TextBox</span></span>|  
|<span data-ttu-id="b197b-259">Timer</span><span class="sxs-lookup"><span data-stu-id="b197b-259">Timer</span></span>|  
|<span data-ttu-id="b197b-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="b197b-260">Toolbar</span></span>|  
|<span data-ttu-id="b197b-261">ToolTip</span><span class="sxs-lookup"><span data-stu-id="b197b-261">ToolTip</span></span>|  
|<span data-ttu-id="b197b-262">Trackbar</span><span class="sxs-lookup"><span data-stu-id="b197b-262">TrackBar</span></span>|  
|<span data-ttu-id="b197b-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="b197b-263">TreeView</span></span>|  
|<span data-ttu-id="b197b-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="b197b-264">VscrollBar</span></span>|  
|<span data-ttu-id="b197b-265">WebBrowser</span><span class="sxs-lookup"><span data-stu-id="b197b-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="b197b-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span><span class="sxs-lookup"><span data-stu-id="b197b-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="b197b-267">Alcune funzionalità potrebbero non essere disponibili.</span><span class="sxs-lookup"><span data-stu-id="b197b-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="b197b-268">Nome controllo</span><span class="sxs-lookup"><span data-stu-id="b197b-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="b197b-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="b197b-269">BindingSource</span></span>|  
|<span data-ttu-id="b197b-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="b197b-270">DataGrid</span></span>|  
|<span data-ttu-id="b197b-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="b197b-271">DataGridView</span></span>|  
|<span data-ttu-id="b197b-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="b197b-272">DataNavigator</span></span>|  
|<span data-ttu-id="b197b-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="b197b-273">DomainUpDown</span></span>|  
|<span data-ttu-id="b197b-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="b197b-274">ErrorProvider</span></span>|  
|<span data-ttu-id="b197b-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="b197b-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="b197b-276">Form</span><span class="sxs-lookup"><span data-stu-id="b197b-276">Form</span></span>|  
|<span data-ttu-id="b197b-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="b197b-277">LinkLabel</span></span>|  
|<span data-ttu-id="b197b-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="b197b-278">HelpProvider</span></span>|  
|<span data-ttu-id="b197b-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="b197b-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="b197b-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="b197b-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="b197b-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="b197b-281">NumericUpDown</span></span>|  
|<span data-ttu-id="b197b-282">Panel</span><span class="sxs-lookup"><span data-stu-id="b197b-282">Panel</span></span>|  
|<span data-ttu-id="b197b-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="b197b-283">PictureBox</span></span>|  
|<span data-ttu-id="b197b-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="b197b-284">PrintDocument</span></span>|  
|<span data-ttu-id="b197b-285">PrintPreviewControl</span><span class="sxs-lookup"><span data-stu-id="b197b-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="b197b-286">PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="b197b-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="b197b-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="b197b-287">PropertyGrid</span></span>|  
|<span data-ttu-id="b197b-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="b197b-288">UserControl</span></span>|  
|<span data-ttu-id="b197b-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="b197b-289">ToolStrip</span></span>|  
|<span data-ttu-id="b197b-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="b197b-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="b197b-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="b197b-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="b197b-292">Splitter</span><span class="sxs-lookup"><span data-stu-id="b197b-292">Splitter</span></span>|  
|<span data-ttu-id="b197b-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="b197b-293">RaftingContainer</span></span>|  
|<span data-ttu-id="b197b-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="b197b-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b197b-295">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b197b-295">See also</span></span>

- [<span data-ttu-id="b197b-296">Tipi di controllo per l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="b197b-296">UI Automation Control Types</span></span>](ui-automation-control-types.md)
