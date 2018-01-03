---
title: Supporto per automazione interfaccia utente dei controlli standard
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
caps.latest.revision: "11"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: f7529c68e96f93ebbba9fc5e750e09331bda9699
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="24dc6-102">Supporto per automazione interfaccia utente dei controlli standard</span><span class="sxs-lookup"><span data-stu-id="24dc6-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
>  <span data-ttu-id="24dc6-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="24dc6-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="24dc6-104">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere l'argomento sull' [API Automazione interfaccia utente di Windows](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="24dc6-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="24dc6-105">Questo argomento contiene informazioni sul supporto di [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] per i controlli standard in applicazioni sviluppate per i framework [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]e [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="24dc6-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="24dc6-106">Controlli WPF (Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="24dc6-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="24dc6-107">Tutti gli elementi di controllo [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] che forniscono informazioni o supporto per l'interazione dell'utente dispongono di supporto nativo completo per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24dc6-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="24dc6-108">Gli altri elementi, ad esempio i pannelli, non sono visibile per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24dc6-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="24dc6-109">Controlli Win32</span><span class="sxs-lookup"><span data-stu-id="24dc6-109">Win32 Controls</span></span>  
 <span data-ttu-id="24dc6-110">La maggior parte dei controlli [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] è esposta a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tramite provider lato client in UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="24dc6-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="24dc6-111">Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="24dc6-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="24dc6-112">Il supporto completo viene fornito solo per i controlli a partire dalla versione 6 di ComCtrl32.dll (disponibile con [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] e versioni successive).</span><span class="sxs-lookup"><span data-stu-id="24dc6-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="24dc6-113">I controlli seguenti sono supportati.</span><span class="sxs-lookup"><span data-stu-id="24dc6-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="24dc6-114">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="24dc6-114">Class name</span></span>|<span data-ttu-id="24dc6-115">Tipo di controllo</span><span class="sxs-lookup"><span data-stu-id="24dc6-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="24dc6-116">Button</span><span class="sxs-lookup"><span data-stu-id="24dc6-116">Button</span></span>|<span data-ttu-id="24dc6-117">Button</span><span class="sxs-lookup"><span data-stu-id="24dc6-117">Button</span></span>|  
|<span data-ttu-id="24dc6-118">Button</span><span class="sxs-lookup"><span data-stu-id="24dc6-118">Button</span></span>|<span data-ttu-id="24dc6-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="24dc6-119">RadioButton</span></span>|  
|<span data-ttu-id="24dc6-120">Button</span><span class="sxs-lookup"><span data-stu-id="24dc6-120">Button</span></span>|<span data-ttu-id="24dc6-121">Group</span><span class="sxs-lookup"><span data-stu-id="24dc6-121">Group</span></span>|  
|<span data-ttu-id="24dc6-122">Button</span><span class="sxs-lookup"><span data-stu-id="24dc6-122">Button</span></span>|<span data-ttu-id="24dc6-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="24dc6-123">CheckBox</span></span>|  
|<span data-ttu-id="24dc6-124">Button</span><span class="sxs-lookup"><span data-stu-id="24dc6-124">Button</span></span>|<span data-ttu-id="24dc6-125">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="24dc6-125">Hyperlink</span></span>|  
|<span data-ttu-id="24dc6-126">Button</span><span class="sxs-lookup"><span data-stu-id="24dc6-126">Button</span></span>|<span data-ttu-id="24dc6-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="24dc6-127">SplitButton</span></span>|  
|<span data-ttu-id="24dc6-128">Button</span><span class="sxs-lookup"><span data-stu-id="24dc6-128">Button</span></span>|<span data-ttu-id="24dc6-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="24dc6-129">CheckBox</span></span>|  
|<span data-ttu-id="24dc6-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="24dc6-130">ComboBoxEx32</span></span>|<span data-ttu-id="24dc6-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="24dc6-131">ComboBox</span></span>|  
|<span data-ttu-id="24dc6-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="24dc6-132">ComboBox</span></span>|<span data-ttu-id="24dc6-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="24dc6-133">ComboBox</span></span>|  
|<span data-ttu-id="24dc6-134">Edit</span><span class="sxs-lookup"><span data-stu-id="24dc6-134">Edit</span></span>|<span data-ttu-id="24dc6-135">Document</span><span class="sxs-lookup"><span data-stu-id="24dc6-135">Document</span></span>|  
|<span data-ttu-id="24dc6-136">Edit</span><span class="sxs-lookup"><span data-stu-id="24dc6-136">Edit</span></span>|<span data-ttu-id="24dc6-137">Edit</span><span class="sxs-lookup"><span data-stu-id="24dc6-137">Edit</span></span>|  
|<span data-ttu-id="24dc6-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="24dc6-138">SysLink</span></span>|<span data-ttu-id="24dc6-139">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="24dc6-139">Hyperlink</span></span>|  
|<span data-ttu-id="24dc6-140">Static</span><span class="sxs-lookup"><span data-stu-id="24dc6-140">Static</span></span>|<span data-ttu-id="24dc6-141">Testo</span><span class="sxs-lookup"><span data-stu-id="24dc6-141">Text</span></span>|  
|<span data-ttu-id="24dc6-142">Static</span><span class="sxs-lookup"><span data-stu-id="24dc6-142">Static</span></span>|<span data-ttu-id="24dc6-143">Image</span><span class="sxs-lookup"><span data-stu-id="24dc6-143">Image</span></span>|  
|<span data-ttu-id="24dc6-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="24dc6-144">SysIPAddress32</span></span>|<span data-ttu-id="24dc6-145">Custom</span><span class="sxs-lookup"><span data-stu-id="24dc6-145">Custom</span></span>|  
|<span data-ttu-id="24dc6-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="24dc6-146">SysHeader32</span></span>|<span data-ttu-id="24dc6-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="24dc6-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="24dc6-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="24dc6-148">SysListView32</span></span>|<span data-ttu-id="24dc6-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="24dc6-149">DataGrid</span></span>|  
|<span data-ttu-id="24dc6-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="24dc6-150">SysListView32</span></span>|<span data-ttu-id="24dc6-151">List</span><span class="sxs-lookup"><span data-stu-id="24dc6-151">List</span></span>|  
|<span data-ttu-id="24dc6-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="24dc6-152">ListBox</span></span>|<span data-ttu-id="24dc6-153">List</span><span class="sxs-lookup"><span data-stu-id="24dc6-153">List</span></span>|  
|<span data-ttu-id="24dc6-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="24dc6-154">ListBox</span></span>|<span data-ttu-id="24dc6-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="24dc6-155">ListItem</span></span>|  
|<span data-ttu-id="24dc6-156">#32768</span><span class="sxs-lookup"><span data-stu-id="24dc6-156">#32768</span></span>|<span data-ttu-id="24dc6-157">Menu</span><span class="sxs-lookup"><span data-stu-id="24dc6-157">Menu</span></span>|  
|<span data-ttu-id="24dc6-158">#32768</span><span class="sxs-lookup"><span data-stu-id="24dc6-158">#32768</span></span>|<span data-ttu-id="24dc6-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="24dc6-159">MenuItem</span></span>|  
|<span data-ttu-id="24dc6-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="24dc6-160">msctls_progress32</span></span>|<span data-ttu-id="24dc6-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="24dc6-161">ProgressBar</span></span>|  
|<span data-ttu-id="24dc6-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="24dc6-162">RichEdit</span></span>|<span data-ttu-id="24dc6-163">Document</span><span class="sxs-lookup"><span data-stu-id="24dc6-163">Document.</span></span> <span data-ttu-id="24dc6-164">Vedere la nota.</span><span class="sxs-lookup"><span data-stu-id="24dc6-164">See note.</span></span>|  
|<span data-ttu-id="24dc6-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="24dc6-165">RichEdit20A</span></span>|<span data-ttu-id="24dc6-166">Document</span><span class="sxs-lookup"><span data-stu-id="24dc6-166">Document</span></span>|  
|<span data-ttu-id="24dc6-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="24dc6-167">RichEdit20W</span></span>|<span data-ttu-id="24dc6-168">Document</span><span class="sxs-lookup"><span data-stu-id="24dc6-168">Document</span></span>|  
|<span data-ttu-id="24dc6-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="24dc6-169">RichEdit50W</span></span>|<span data-ttu-id="24dc6-170">Document</span><span class="sxs-lookup"><span data-stu-id="24dc6-170">Document</span></span>|  
|<span data-ttu-id="24dc6-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="24dc6-171">ScrollBar</span></span>|<span data-ttu-id="24dc6-172">Slider</span><span class="sxs-lookup"><span data-stu-id="24dc6-172">Slider</span></span>|  
|<span data-ttu-id="24dc6-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="24dc6-173">msctls_trackbar32</span></span>|<span data-ttu-id="24dc6-174">Slider</span><span class="sxs-lookup"><span data-stu-id="24dc6-174">Slider</span></span>|  
|<span data-ttu-id="24dc6-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="24dc6-175">msctls_updown32</span></span>|<span data-ttu-id="24dc6-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="24dc6-176">Spinner</span></span>|  
|<span data-ttu-id="24dc6-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="24dc6-177">msctls_statusbar32</span></span>|<span data-ttu-id="24dc6-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="24dc6-178">StatusBar</span></span>|  
|<span data-ttu-id="24dc6-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="24dc6-179">SysTabControl32</span></span>|<span data-ttu-id="24dc6-180">Tab</span><span class="sxs-lookup"><span data-stu-id="24dc6-180">Tab</span></span>|  
|<span data-ttu-id="24dc6-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="24dc6-181">SysTabControl32</span></span>|<span data-ttu-id="24dc6-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="24dc6-182">TabItem</span></span>|  
|<span data-ttu-id="24dc6-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="24dc6-183">ToolbarWindow32</span></span>|<span data-ttu-id="24dc6-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="24dc6-184">ToolBar</span></span>|  
|<span data-ttu-id="24dc6-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="24dc6-185">ToolbarWindow32</span></span>|<span data-ttu-id="24dc6-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="24dc6-186">MenuItem</span></span>|  
|<span data-ttu-id="24dc6-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="24dc6-187">ToolbarWindow32</span></span>|<span data-ttu-id="24dc6-188">Button</span><span class="sxs-lookup"><span data-stu-id="24dc6-188">Button</span></span>|  
|<span data-ttu-id="24dc6-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="24dc6-189">ToolbarWindow32</span></span>|<span data-ttu-id="24dc6-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="24dc6-190">CheckBox</span></span>|  
|<span data-ttu-id="24dc6-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="24dc6-191">ToolbarWindow32</span></span>|<span data-ttu-id="24dc6-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="24dc6-192">RadioButton</span></span>|  
|<span data-ttu-id="24dc6-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="24dc6-193">ToolbarWindow32</span></span>|<span data-ttu-id="24dc6-194">Separatore</span><span class="sxs-lookup"><span data-stu-id="24dc6-194">Separator</span></span>|  
|<span data-ttu-id="24dc6-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="24dc6-195">tooltips_class32</span></span>|<span data-ttu-id="24dc6-196">ToolTip</span><span class="sxs-lookup"><span data-stu-id="24dc6-196">ToolTip</span></span>|  
|<span data-ttu-id="24dc6-197">#32774</span><span class="sxs-lookup"><span data-stu-id="24dc6-197">#32774</span></span>|<span data-ttu-id="24dc6-198">ToolTip</span><span class="sxs-lookup"><span data-stu-id="24dc6-198">ToolTip</span></span>|  
|<span data-ttu-id="24dc6-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="24dc6-199">ReBarWindow32</span></span>|<span data-ttu-id="24dc6-200">ToolBar</span><span class="sxs-lookup"><span data-stu-id="24dc6-200">Toolbar</span></span>|  
|<span data-ttu-id="24dc6-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="24dc6-201">SysTreeView32</span></span>|<span data-ttu-id="24dc6-202">Tree</span><span class="sxs-lookup"><span data-stu-id="24dc6-202">Tree</span></span>|  
|<span data-ttu-id="24dc6-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="24dc6-203">SysTreeView32</span></span>|<span data-ttu-id="24dc6-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="24dc6-204">TreeItem</span></span>|  
  
 <span data-ttu-id="24dc6-205">**Nota** Il controllo RichEdit è supportato solo per le versioni fornite con [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in Riched20.dll versione 3.1 e successive e MsftEdit.dll versione 4.1 e successive).</span><span class="sxs-lookup"><span data-stu-id="24dc6-205">**Note** The RichEdit control is supported only for versions shipped with [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="24dc6-206">I controlli seguenti non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="24dc6-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="24dc6-207">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="24dc6-207">Class name</span></span>|<span data-ttu-id="24dc6-208">Tipo di controllo</span><span class="sxs-lookup"><span data-stu-id="24dc6-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="24dc6-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="24dc6-209">SysAnimate32</span></span>|<span data-ttu-id="24dc6-210">Image</span><span class="sxs-lookup"><span data-stu-id="24dc6-210">Image</span></span>|  
|<span data-ttu-id="24dc6-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="24dc6-211">SysPager</span></span>|<span data-ttu-id="24dc6-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="24dc6-212">Spinner</span></span>|  
|<span data-ttu-id="24dc6-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="24dc6-213">SysDateTimePick32</span></span>|<span data-ttu-id="24dc6-214">Custom</span><span class="sxs-lookup"><span data-stu-id="24dc6-214">Custom</span></span>|  
|<span data-ttu-id="24dc6-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="24dc6-215">SysMonthCal32</span></span>|<span data-ttu-id="24dc6-216">Calendar</span><span class="sxs-lookup"><span data-stu-id="24dc6-216">Calendar</span></span>|  
|<span data-ttu-id="24dc6-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="24dc6-217">MS_WINNOTE</span></span>|<span data-ttu-id="24dc6-218">ToolTip</span><span class="sxs-lookup"><span data-stu-id="24dc6-218">Tooltip</span></span>|  
|<span data-ttu-id="24dc6-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="24dc6-219">VBBubble</span></span>|<span data-ttu-id="24dc6-220">Tooltip</span><span class="sxs-lookup"><span data-stu-id="24dc6-220">Tooltip</span></span>|  
|<span data-ttu-id="24dc6-221">ScrollBar (se usato come controllo autonomo)</span><span class="sxs-lookup"><span data-stu-id="24dc6-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="24dc6-222">Slider</span><span class="sxs-lookup"><span data-stu-id="24dc6-222">Slider</span></span>|  
|<span data-ttu-id="24dc6-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="24dc6-223">SuperGrid</span></span>|<span data-ttu-id="24dc6-224">Custom</span><span class="sxs-lookup"><span data-stu-id="24dc6-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="24dc6-225">Controlli per Windows Form</span><span class="sxs-lookup"><span data-stu-id="24dc6-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="24dc6-226">I controlli[!INCLUDE[TLA2#tla_winforms](../../../includes/tla2sharptla-winforms-md.md)] sono esposti a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tramite provider lato client in UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="24dc6-226">[!INCLUDE[TLA2#tla_winforms](../../../includes/tla2sharptla-winforms-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="24dc6-227">Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="24dc6-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="24dc6-228">In genere, i controlli [!INCLUDE[TLA2#tla_winforms](../../../includes/tla2sharptla-winforms-md.md)] che sono wrapper gestiti per i controlli comuni [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] sono supportati da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24dc6-228">Typically, [!INCLUDE[TLA2#tla_winforms](../../../includes/tla2sharptla-winforms-md.md)] controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="24dc6-229">I controlli seguenti sono supportati.</span><span class="sxs-lookup"><span data-stu-id="24dc6-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="24dc6-230">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="24dc6-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="24dc6-231">Button</span><span class="sxs-lookup"><span data-stu-id="24dc6-231">Button</span></span>|  
|<span data-ttu-id="24dc6-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="24dc6-232">CheckBox</span></span>|  
|<span data-ttu-id="24dc6-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="24dc6-233">CheckedListBox</span></span>|  
|<span data-ttu-id="24dc6-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="24dc6-234">ColorDialog</span></span>|  
|<span data-ttu-id="24dc6-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="24dc6-235">ComboBox</span></span>|  
|<span data-ttu-id="24dc6-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="24dc6-236">FolderBrowser</span></span>|  
|<span data-ttu-id="24dc6-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="24dc6-237">FontDialog</span></span>|  
|<span data-ttu-id="24dc6-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="24dc6-238">GroupBox</span></span>|  
|<span data-ttu-id="24dc6-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="24dc6-239">HscrollBar</span></span>|  
|<span data-ttu-id="24dc6-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="24dc6-240">ImageList</span></span>|  
|<span data-ttu-id="24dc6-241">Label</span><span class="sxs-lookup"><span data-stu-id="24dc6-241">Label</span></span>|  
|<span data-ttu-id="24dc6-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="24dc6-242">ListBox</span></span>|  
|<span data-ttu-id="24dc6-243">ListView</span><span class="sxs-lookup"><span data-stu-id="24dc6-243">ListView</span></span>|  
|<span data-ttu-id="24dc6-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="24dc6-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="24dc6-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="24dc6-245">MonthCalendar</span></span>|  
|<span data-ttu-id="24dc6-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="24dc6-246">NotifyIcon</span></span>|  
|<span data-ttu-id="24dc6-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="24dc6-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="24dc6-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="24dc6-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="24dc6-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="24dc6-249">PrintDialog</span></span>|  
|<span data-ttu-id="24dc6-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="24dc6-250">ProgressBar</span></span>|  
|<span data-ttu-id="24dc6-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="24dc6-251">RadioButton</span></span>|  
|<span data-ttu-id="24dc6-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="24dc6-252">RichTextBox</span></span>|  
|<span data-ttu-id="24dc6-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="24dc6-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="24dc6-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="24dc6-254">ScrollableControl</span></span>|  
|<span data-ttu-id="24dc6-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="24dc6-255">SoundPlayer</span></span>|  
|<span data-ttu-id="24dc6-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="24dc6-256">StatusBar</span></span>|  
|<span data-ttu-id="24dc6-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="24dc6-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="24dc6-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="24dc6-258">TextBox</span></span>|  
|<span data-ttu-id="24dc6-259">Timer</span><span class="sxs-lookup"><span data-stu-id="24dc6-259">Timer</span></span>|  
|<span data-ttu-id="24dc6-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="24dc6-260">Toolbar</span></span>|  
|<span data-ttu-id="24dc6-261">ToolTip</span><span class="sxs-lookup"><span data-stu-id="24dc6-261">ToolTip</span></span>|  
|<span data-ttu-id="24dc6-262">Trackbar</span><span class="sxs-lookup"><span data-stu-id="24dc6-262">TrackBar</span></span>|  
|<span data-ttu-id="24dc6-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="24dc6-263">TreeView</span></span>|  
|<span data-ttu-id="24dc6-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="24dc6-264">VscrollBar</span></span>|  
|<span data-ttu-id="24dc6-265">WebBrowser</span><span class="sxs-lookup"><span data-stu-id="24dc6-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="24dc6-266">I seguenti controlli sono esposti a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] solo tramite il relativo supporto per [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24dc6-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span></span> <span data-ttu-id="24dc6-267">Alcune funzionalità potrebbero non essere disponibili.</span><span class="sxs-lookup"><span data-stu-id="24dc6-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="24dc6-268">Nome controllo</span><span class="sxs-lookup"><span data-stu-id="24dc6-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="24dc6-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="24dc6-269">BindingSource</span></span>|  
|<span data-ttu-id="24dc6-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="24dc6-270">DataGrid</span></span>|  
|<span data-ttu-id="24dc6-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="24dc6-271">DataGridView</span></span>|  
|<span data-ttu-id="24dc6-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="24dc6-272">DataNavigator</span></span>|  
|<span data-ttu-id="24dc6-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="24dc6-273">DomainUpDown</span></span>|  
|<span data-ttu-id="24dc6-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="24dc6-274">ErrorProvider</span></span>|  
|<span data-ttu-id="24dc6-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="24dc6-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="24dc6-276">Form</span><span class="sxs-lookup"><span data-stu-id="24dc6-276">Form</span></span>|  
|<span data-ttu-id="24dc6-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="24dc6-277">LinkLabel</span></span>|  
|<span data-ttu-id="24dc6-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="24dc6-278">HelpProvider</span></span>|  
|<span data-ttu-id="24dc6-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="24dc6-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="24dc6-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="24dc6-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="24dc6-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="24dc6-281">NumericUpDown</span></span>|  
|<span data-ttu-id="24dc6-282">Panel</span><span class="sxs-lookup"><span data-stu-id="24dc6-282">Panel</span></span>|  
|<span data-ttu-id="24dc6-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="24dc6-283">PictureBox</span></span>|  
|<span data-ttu-id="24dc6-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="24dc6-284">PrintDocument</span></span>|  
|<span data-ttu-id="24dc6-285">PrintPreviewControl</span><span class="sxs-lookup"><span data-stu-id="24dc6-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="24dc6-286">PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="24dc6-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="24dc6-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="24dc6-287">PropertyGrid</span></span>|  
|<span data-ttu-id="24dc6-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="24dc6-288">UserControl</span></span>|  
|<span data-ttu-id="24dc6-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="24dc6-289">ToolStrip</span></span>|  
|<span data-ttu-id="24dc6-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="24dc6-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="24dc6-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="24dc6-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="24dc6-292">Splitter</span><span class="sxs-lookup"><span data-stu-id="24dc6-292">Splitter</span></span>|  
|<span data-ttu-id="24dc6-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="24dc6-293">RaftingContainer</span></span>|  
|<span data-ttu-id="24dc6-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="24dc6-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="24dc6-295">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24dc6-295">See Also</span></span>  
 [<span data-ttu-id="24dc6-296">Tipi di controllo per l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="24dc6-296">UI Automation Control Types</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types.md)
