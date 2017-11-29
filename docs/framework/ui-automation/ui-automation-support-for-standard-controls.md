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
ms.openlocfilehash: 71a5a2e4319debf1a4d8ddd08d7f0979443682b9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="22005-102">Supporto per automazione interfaccia utente dei controlli standard</span><span class="sxs-lookup"><span data-stu-id="22005-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
>  <span data-ttu-id="22005-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="22005-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="22005-104">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="22005-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="22005-105">Questo argomento contiene informazioni sul supporto di [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] per i controlli standard in applicazioni sviluppate per i framework [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]e [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="22005-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="22005-106">Controlli WPF (Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="22005-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="22005-107">Tutti gli elementi di controllo [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] che forniscono informazioni o supporto per l'interazione dell'utente dispongono di supporto nativo completo per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22005-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="22005-108">Gli altri elementi, ad esempio i pannelli, non sono visibile per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22005-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="22005-109">Controlli Win32</span><span class="sxs-lookup"><span data-stu-id="22005-109">Win32 Controls</span></span>  
 <span data-ttu-id="22005-110">La maggior parte dei controlli [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] è esposta a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tramite provider lato client in UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="22005-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="22005-111">Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="22005-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="22005-112">Il supporto completo viene fornito solo per i controlli a partire dalla versione 6 di ComCtrl32.dll (disponibile con [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] e versioni successive).</span><span class="sxs-lookup"><span data-stu-id="22005-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="22005-113">I controlli seguenti sono supportati.</span><span class="sxs-lookup"><span data-stu-id="22005-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="22005-114">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="22005-114">Class name</span></span>|<span data-ttu-id="22005-115">Tipo di controllo</span><span class="sxs-lookup"><span data-stu-id="22005-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="22005-116">Button</span><span class="sxs-lookup"><span data-stu-id="22005-116">Button</span></span>|<span data-ttu-id="22005-117">Button</span><span class="sxs-lookup"><span data-stu-id="22005-117">Button</span></span>|  
|<span data-ttu-id="22005-118">Button</span><span class="sxs-lookup"><span data-stu-id="22005-118">Button</span></span>|<span data-ttu-id="22005-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="22005-119">RadioButton</span></span>|  
|<span data-ttu-id="22005-120">Button</span><span class="sxs-lookup"><span data-stu-id="22005-120">Button</span></span>|<span data-ttu-id="22005-121">Group</span><span class="sxs-lookup"><span data-stu-id="22005-121">Group</span></span>|  
|<span data-ttu-id="22005-122">Button</span><span class="sxs-lookup"><span data-stu-id="22005-122">Button</span></span>|<span data-ttu-id="22005-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="22005-123">CheckBox</span></span>|  
|<span data-ttu-id="22005-124">Button</span><span class="sxs-lookup"><span data-stu-id="22005-124">Button</span></span>|<span data-ttu-id="22005-125">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="22005-125">Hyperlink</span></span>|  
|<span data-ttu-id="22005-126">Button</span><span class="sxs-lookup"><span data-stu-id="22005-126">Button</span></span>|<span data-ttu-id="22005-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="22005-127">SplitButton</span></span>|  
|<span data-ttu-id="22005-128">Button</span><span class="sxs-lookup"><span data-stu-id="22005-128">Button</span></span>|<span data-ttu-id="22005-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="22005-129">CheckBox</span></span>|  
|<span data-ttu-id="22005-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="22005-130">ComboBoxEx32</span></span>|<span data-ttu-id="22005-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="22005-131">ComboBox</span></span>|  
|<span data-ttu-id="22005-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="22005-132">ComboBox</span></span>|<span data-ttu-id="22005-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="22005-133">ComboBox</span></span>|  
|<span data-ttu-id="22005-134">Edit</span><span class="sxs-lookup"><span data-stu-id="22005-134">Edit</span></span>|<span data-ttu-id="22005-135">Document</span><span class="sxs-lookup"><span data-stu-id="22005-135">Document</span></span>|  
|<span data-ttu-id="22005-136">Edit</span><span class="sxs-lookup"><span data-stu-id="22005-136">Edit</span></span>|<span data-ttu-id="22005-137">Edit</span><span class="sxs-lookup"><span data-stu-id="22005-137">Edit</span></span>|  
|<span data-ttu-id="22005-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="22005-138">SysLink</span></span>|<span data-ttu-id="22005-139">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="22005-139">Hyperlink</span></span>|  
|<span data-ttu-id="22005-140">Static</span><span class="sxs-lookup"><span data-stu-id="22005-140">Static</span></span>|<span data-ttu-id="22005-141">Text</span><span class="sxs-lookup"><span data-stu-id="22005-141">Text</span></span>|  
|<span data-ttu-id="22005-142">Static</span><span class="sxs-lookup"><span data-stu-id="22005-142">Static</span></span>|<span data-ttu-id="22005-143">Image</span><span class="sxs-lookup"><span data-stu-id="22005-143">Image</span></span>|  
|<span data-ttu-id="22005-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="22005-144">SysIPAddress32</span></span>|<span data-ttu-id="22005-145">Custom</span><span class="sxs-lookup"><span data-stu-id="22005-145">Custom</span></span>|  
|<span data-ttu-id="22005-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="22005-146">SysHeader32</span></span>|<span data-ttu-id="22005-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="22005-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="22005-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="22005-148">SysListView32</span></span>|<span data-ttu-id="22005-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="22005-149">DataGrid</span></span>|  
|<span data-ttu-id="22005-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="22005-150">SysListView32</span></span>|<span data-ttu-id="22005-151">List</span><span class="sxs-lookup"><span data-stu-id="22005-151">List</span></span>|  
|<span data-ttu-id="22005-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="22005-152">ListBox</span></span>|<span data-ttu-id="22005-153">List</span><span class="sxs-lookup"><span data-stu-id="22005-153">List</span></span>|  
|<span data-ttu-id="22005-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="22005-154">ListBox</span></span>|<span data-ttu-id="22005-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="22005-155">ListItem</span></span>|  
|<span data-ttu-id="22005-156">#32768</span><span class="sxs-lookup"><span data-stu-id="22005-156">#32768</span></span>|<span data-ttu-id="22005-157">Menu</span><span class="sxs-lookup"><span data-stu-id="22005-157">Menu</span></span>|  
|<span data-ttu-id="22005-158">#32768</span><span class="sxs-lookup"><span data-stu-id="22005-158">#32768</span></span>|<span data-ttu-id="22005-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="22005-159">MenuItem</span></span>|  
|<span data-ttu-id="22005-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="22005-160">msctls_progress32</span></span>|<span data-ttu-id="22005-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="22005-161">ProgressBar</span></span>|  
|<span data-ttu-id="22005-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="22005-162">RichEdit</span></span>|<span data-ttu-id="22005-163">Document</span><span class="sxs-lookup"><span data-stu-id="22005-163">Document.</span></span> <span data-ttu-id="22005-164">Vedere la nota.</span><span class="sxs-lookup"><span data-stu-id="22005-164">See note.</span></span>|  
|<span data-ttu-id="22005-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="22005-165">RichEdit20A</span></span>|<span data-ttu-id="22005-166">Document</span><span class="sxs-lookup"><span data-stu-id="22005-166">Document</span></span>|  
|<span data-ttu-id="22005-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="22005-167">RichEdit20W</span></span>|<span data-ttu-id="22005-168">Document</span><span class="sxs-lookup"><span data-stu-id="22005-168">Document</span></span>|  
|<span data-ttu-id="22005-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="22005-169">RichEdit50W</span></span>|<span data-ttu-id="22005-170">Document</span><span class="sxs-lookup"><span data-stu-id="22005-170">Document</span></span>|  
|<span data-ttu-id="22005-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="22005-171">ScrollBar</span></span>|<span data-ttu-id="22005-172">Slider</span><span class="sxs-lookup"><span data-stu-id="22005-172">Slider</span></span>|  
|<span data-ttu-id="22005-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="22005-173">msctls_trackbar32</span></span>|<span data-ttu-id="22005-174">Slider</span><span class="sxs-lookup"><span data-stu-id="22005-174">Slider</span></span>|  
|<span data-ttu-id="22005-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="22005-175">msctls_updown32</span></span>|<span data-ttu-id="22005-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="22005-176">Spinner</span></span>|  
|<span data-ttu-id="22005-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="22005-177">msctls_statusbar32</span></span>|<span data-ttu-id="22005-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="22005-178">StatusBar</span></span>|  
|<span data-ttu-id="22005-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="22005-179">SysTabControl32</span></span>|<span data-ttu-id="22005-180">Tab</span><span class="sxs-lookup"><span data-stu-id="22005-180">Tab</span></span>|  
|<span data-ttu-id="22005-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="22005-181">SysTabControl32</span></span>|<span data-ttu-id="22005-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="22005-182">TabItem</span></span>|  
|<span data-ttu-id="22005-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="22005-183">ToolbarWindow32</span></span>|<span data-ttu-id="22005-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="22005-184">ToolBar</span></span>|  
|<span data-ttu-id="22005-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="22005-185">ToolbarWindow32</span></span>|<span data-ttu-id="22005-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="22005-186">MenuItem</span></span>|  
|<span data-ttu-id="22005-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="22005-187">ToolbarWindow32</span></span>|<span data-ttu-id="22005-188">Button</span><span class="sxs-lookup"><span data-stu-id="22005-188">Button</span></span>|  
|<span data-ttu-id="22005-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="22005-189">ToolbarWindow32</span></span>|<span data-ttu-id="22005-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="22005-190">CheckBox</span></span>|  
|<span data-ttu-id="22005-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="22005-191">ToolbarWindow32</span></span>|<span data-ttu-id="22005-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="22005-192">RadioButton</span></span>|  
|<span data-ttu-id="22005-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="22005-193">ToolbarWindow32</span></span>|<span data-ttu-id="22005-194">Separator</span><span class="sxs-lookup"><span data-stu-id="22005-194">Separator</span></span>|  
|<span data-ttu-id="22005-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="22005-195">tooltips_class32</span></span>|<span data-ttu-id="22005-196">ToolTip</span><span class="sxs-lookup"><span data-stu-id="22005-196">ToolTip</span></span>|  
|<span data-ttu-id="22005-197">#32774</span><span class="sxs-lookup"><span data-stu-id="22005-197">#32774</span></span>|<span data-ttu-id="22005-198">ToolTip</span><span class="sxs-lookup"><span data-stu-id="22005-198">ToolTip</span></span>|  
|<span data-ttu-id="22005-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="22005-199">ReBarWindow32</span></span>|<span data-ttu-id="22005-200">ToolBar</span><span class="sxs-lookup"><span data-stu-id="22005-200">Toolbar</span></span>|  
|<span data-ttu-id="22005-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="22005-201">SysTreeView32</span></span>|<span data-ttu-id="22005-202">Tree</span><span class="sxs-lookup"><span data-stu-id="22005-202">Tree</span></span>|  
|<span data-ttu-id="22005-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="22005-203">SysTreeView32</span></span>|<span data-ttu-id="22005-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="22005-204">TreeItem</span></span>|  
  
 <span data-ttu-id="22005-205">**Nota** Il controllo RichEdit è supportato solo per le versioni fornite con [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in Riched20.dll versione 3.1 e successive e MsftEdit.dll versione 4.1 e successive).</span><span class="sxs-lookup"><span data-stu-id="22005-205">**Note** The RichEdit control is supported only for versions shipped with [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="22005-206">I controlli seguenti non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="22005-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="22005-207">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="22005-207">Class name</span></span>|<span data-ttu-id="22005-208">Tipo di controllo</span><span class="sxs-lookup"><span data-stu-id="22005-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="22005-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="22005-209">SysAnimate32</span></span>|<span data-ttu-id="22005-210">Image</span><span class="sxs-lookup"><span data-stu-id="22005-210">Image</span></span>|  
|<span data-ttu-id="22005-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="22005-211">SysPager</span></span>|<span data-ttu-id="22005-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="22005-212">Spinner</span></span>|  
|<span data-ttu-id="22005-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="22005-213">SysDateTimePick32</span></span>|<span data-ttu-id="22005-214">Custom</span><span class="sxs-lookup"><span data-stu-id="22005-214">Custom</span></span>|  
|<span data-ttu-id="22005-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="22005-215">SysMonthCal32</span></span>|<span data-ttu-id="22005-216">Calendar</span><span class="sxs-lookup"><span data-stu-id="22005-216">Calendar</span></span>|  
|<span data-ttu-id="22005-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="22005-217">MS_WINNOTE</span></span>|<span data-ttu-id="22005-218">ToolTip</span><span class="sxs-lookup"><span data-stu-id="22005-218">Tooltip</span></span>|  
|<span data-ttu-id="22005-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="22005-219">VBBubble</span></span>|<span data-ttu-id="22005-220">ToolTip</span><span class="sxs-lookup"><span data-stu-id="22005-220">Tooltip</span></span>|  
|<span data-ttu-id="22005-221">ScrollBar (se usato come controllo autonomo)</span><span class="sxs-lookup"><span data-stu-id="22005-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="22005-222">Slider</span><span class="sxs-lookup"><span data-stu-id="22005-222">Slider</span></span>|  
|<span data-ttu-id="22005-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="22005-223">SuperGrid</span></span>|<span data-ttu-id="22005-224">Custom</span><span class="sxs-lookup"><span data-stu-id="22005-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="22005-225">Controlli per Windows Form</span><span class="sxs-lookup"><span data-stu-id="22005-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="22005-226">I controlli[!INCLUDE[TLA2#tla_winforms](../../../includes/tla2sharptla-winforms-md.md)] sono esposti a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tramite provider lato client in UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="22005-226">[!INCLUDE[TLA2#tla_winforms](../../../includes/tla2sharptla-winforms-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="22005-227">Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="22005-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="22005-228">In genere, i controlli [!INCLUDE[TLA2#tla_winforms](../../../includes/tla2sharptla-winforms-md.md)] che sono wrapper gestiti per i controlli comuni [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] sono supportati da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22005-228">Typically, [!INCLUDE[TLA2#tla_winforms](../../../includes/tla2sharptla-winforms-md.md)] controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="22005-229">I controlli seguenti sono supportati.</span><span class="sxs-lookup"><span data-stu-id="22005-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="22005-230">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="22005-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="22005-231">Button</span><span class="sxs-lookup"><span data-stu-id="22005-231">Button</span></span>|  
|<span data-ttu-id="22005-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="22005-232">CheckBox</span></span>|  
|<span data-ttu-id="22005-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="22005-233">CheckedListBox</span></span>|  
|<span data-ttu-id="22005-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="22005-234">ColorDialog</span></span>|  
|<span data-ttu-id="22005-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="22005-235">ComboBox</span></span>|  
|<span data-ttu-id="22005-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="22005-236">FolderBrowser</span></span>|  
|<span data-ttu-id="22005-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="22005-237">FontDialog</span></span>|  
|<span data-ttu-id="22005-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="22005-238">GroupBox</span></span>|  
|<span data-ttu-id="22005-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="22005-239">HscrollBar</span></span>|  
|<span data-ttu-id="22005-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="22005-240">ImageList</span></span>|  
|<span data-ttu-id="22005-241">Label</span><span class="sxs-lookup"><span data-stu-id="22005-241">Label</span></span>|  
|<span data-ttu-id="22005-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="22005-242">ListBox</span></span>|  
|<span data-ttu-id="22005-243">ListView</span><span class="sxs-lookup"><span data-stu-id="22005-243">ListView</span></span>|  
|<span data-ttu-id="22005-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="22005-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="22005-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="22005-245">MonthCalendar</span></span>|  
|<span data-ttu-id="22005-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="22005-246">NotifyIcon</span></span>|  
|<span data-ttu-id="22005-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="22005-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="22005-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="22005-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="22005-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="22005-249">PrintDialog</span></span>|  
|<span data-ttu-id="22005-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="22005-250">ProgressBar</span></span>|  
|<span data-ttu-id="22005-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="22005-251">RadioButton</span></span>|  
|<span data-ttu-id="22005-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="22005-252">RichTextBox</span></span>|  
|<span data-ttu-id="22005-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="22005-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="22005-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="22005-254">ScrollableControl</span></span>|  
|<span data-ttu-id="22005-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="22005-255">SoundPlayer</span></span>|  
|<span data-ttu-id="22005-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="22005-256">StatusBar</span></span>|  
|<span data-ttu-id="22005-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="22005-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="22005-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="22005-258">TextBox</span></span>|  
|<span data-ttu-id="22005-259">Timer</span><span class="sxs-lookup"><span data-stu-id="22005-259">Timer</span></span>|  
|<span data-ttu-id="22005-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="22005-260">Toolbar</span></span>|  
|<span data-ttu-id="22005-261">ToolTip</span><span class="sxs-lookup"><span data-stu-id="22005-261">ToolTip</span></span>|  
|<span data-ttu-id="22005-262">Trackbar</span><span class="sxs-lookup"><span data-stu-id="22005-262">TrackBar</span></span>|  
|<span data-ttu-id="22005-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="22005-263">TreeView</span></span>|  
|<span data-ttu-id="22005-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="22005-264">VscrollBar</span></span>|  
|<span data-ttu-id="22005-265">WebBrowser</span><span class="sxs-lookup"><span data-stu-id="22005-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="22005-266">I seguenti controlli sono esposti a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] solo tramite il relativo supporto per [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22005-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span></span> <span data-ttu-id="22005-267">Alcune funzionalità potrebbero non essere disponibili.</span><span class="sxs-lookup"><span data-stu-id="22005-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="22005-268">Nome controllo</span><span class="sxs-lookup"><span data-stu-id="22005-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="22005-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="22005-269">BindingSource</span></span>|  
|<span data-ttu-id="22005-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="22005-270">DataGrid</span></span>|  
|<span data-ttu-id="22005-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="22005-271">DataGridView</span></span>|  
|<span data-ttu-id="22005-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="22005-272">DataNavigator</span></span>|  
|<span data-ttu-id="22005-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="22005-273">DomainUpDown</span></span>|  
|<span data-ttu-id="22005-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="22005-274">ErrorProvider</span></span>|  
|<span data-ttu-id="22005-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="22005-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="22005-276">Form</span><span class="sxs-lookup"><span data-stu-id="22005-276">Form</span></span>|  
|<span data-ttu-id="22005-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="22005-277">LinkLabel</span></span>|  
|<span data-ttu-id="22005-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="22005-278">HelpProvider</span></span>|  
|<span data-ttu-id="22005-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="22005-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="22005-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="22005-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="22005-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="22005-281">NumericUpDown</span></span>|  
|<span data-ttu-id="22005-282">Panel</span><span class="sxs-lookup"><span data-stu-id="22005-282">Panel</span></span>|  
|<span data-ttu-id="22005-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="22005-283">PictureBox</span></span>|  
|<span data-ttu-id="22005-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="22005-284">PrintDocument</span></span>|  
|<span data-ttu-id="22005-285">PrintPreviewControl</span><span class="sxs-lookup"><span data-stu-id="22005-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="22005-286">PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="22005-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="22005-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="22005-287">PropertyGrid</span></span>|  
|<span data-ttu-id="22005-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="22005-288">UserControl</span></span>|  
|<span data-ttu-id="22005-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="22005-289">ToolStrip</span></span>|  
|<span data-ttu-id="22005-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="22005-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="22005-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="22005-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="22005-292">Splitter</span><span class="sxs-lookup"><span data-stu-id="22005-292">Splitter</span></span>|  
|<span data-ttu-id="22005-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="22005-293">RaftingContainer</span></span>|  
|<span data-ttu-id="22005-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="22005-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="22005-295">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22005-295">See Also</span></span>  
 [<span data-ttu-id="22005-296">UI Automation Control Types</span><span class="sxs-lookup"><span data-stu-id="22005-296">UI Automation Control Types</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types.md)
