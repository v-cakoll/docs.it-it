---
title: Supporto per automazione interfaccia utente dei controlli standard
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 68fa7753be76b0681c40e540e86b11c89e7a8ca1
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47157025"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="97659-102">Supporto per automazione interfaccia utente dei controlli standard</span><span class="sxs-lookup"><span data-stu-id="97659-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
>  <span data-ttu-id="97659-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="97659-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="97659-104">Per informazioni aggiornate sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione dell'interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="97659-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="97659-105">Questo argomento contiene informazioni sul supporto di [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] per i controlli standard in applicazioni sviluppate per i framework [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]e [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="97659-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="97659-106">Controlli WPF (Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="97659-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="97659-107">Tutti gli elementi di controllo [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] che forniscono informazioni o supporto per l'interazione dell'utente dispongono di supporto nativo completo per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97659-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="97659-108">Gli altri elementi, ad esempio i pannelli, non sono visibile per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97659-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="97659-109">Controlli Win32</span><span class="sxs-lookup"><span data-stu-id="97659-109">Win32 Controls</span></span>  
 <span data-ttu-id="97659-110">La maggior parte dei controlli [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] è esposta a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tramite provider lato client in UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="97659-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="97659-111">Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="97659-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="97659-112">Il supporto completo viene fornito solo per i controlli a partire dalla versione 6 di ComCtrl32.dll (disponibile con [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] e versioni successive).</span><span class="sxs-lookup"><span data-stu-id="97659-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="97659-113">I controlli seguenti sono supportati.</span><span class="sxs-lookup"><span data-stu-id="97659-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="97659-114">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="97659-114">Class name</span></span>|<span data-ttu-id="97659-115">Tipo di controllo</span><span class="sxs-lookup"><span data-stu-id="97659-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="97659-116">Button</span><span class="sxs-lookup"><span data-stu-id="97659-116">Button</span></span>|<span data-ttu-id="97659-117">Pulsante</span><span class="sxs-lookup"><span data-stu-id="97659-117">Button</span></span>|  
|<span data-ttu-id="97659-118">Button</span><span class="sxs-lookup"><span data-stu-id="97659-118">Button</span></span>|<span data-ttu-id="97659-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="97659-119">RadioButton</span></span>|  
|<span data-ttu-id="97659-120">Button</span><span class="sxs-lookup"><span data-stu-id="97659-120">Button</span></span>|<span data-ttu-id="97659-121">Group</span><span class="sxs-lookup"><span data-stu-id="97659-121">Group</span></span>|  
|<span data-ttu-id="97659-122">Button</span><span class="sxs-lookup"><span data-stu-id="97659-122">Button</span></span>|<span data-ttu-id="97659-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="97659-123">CheckBox</span></span>|  
|<span data-ttu-id="97659-124">Button</span><span class="sxs-lookup"><span data-stu-id="97659-124">Button</span></span>|<span data-ttu-id="97659-125">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="97659-125">Hyperlink</span></span>|  
|<span data-ttu-id="97659-126">Button</span><span class="sxs-lookup"><span data-stu-id="97659-126">Button</span></span>|<span data-ttu-id="97659-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="97659-127">SplitButton</span></span>|  
|<span data-ttu-id="97659-128">Button</span><span class="sxs-lookup"><span data-stu-id="97659-128">Button</span></span>|<span data-ttu-id="97659-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="97659-129">CheckBox</span></span>|  
|<span data-ttu-id="97659-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="97659-130">ComboBoxEx32</span></span>|<span data-ttu-id="97659-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="97659-131">ComboBox</span></span>|  
|<span data-ttu-id="97659-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="97659-132">ComboBox</span></span>|<span data-ttu-id="97659-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="97659-133">ComboBox</span></span>|  
|<span data-ttu-id="97659-134">Edit</span><span class="sxs-lookup"><span data-stu-id="97659-134">Edit</span></span>|<span data-ttu-id="97659-135">Document</span><span class="sxs-lookup"><span data-stu-id="97659-135">Document</span></span>|  
|<span data-ttu-id="97659-136">Edit</span><span class="sxs-lookup"><span data-stu-id="97659-136">Edit</span></span>|<span data-ttu-id="97659-137">Edit</span><span class="sxs-lookup"><span data-stu-id="97659-137">Edit</span></span>|  
|<span data-ttu-id="97659-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="97659-138">SysLink</span></span>|<span data-ttu-id="97659-139">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="97659-139">Hyperlink</span></span>|  
|<span data-ttu-id="97659-140">Static</span><span class="sxs-lookup"><span data-stu-id="97659-140">Static</span></span>|<span data-ttu-id="97659-141">Testo</span><span class="sxs-lookup"><span data-stu-id="97659-141">Text</span></span>|  
|<span data-ttu-id="97659-142">Static</span><span class="sxs-lookup"><span data-stu-id="97659-142">Static</span></span>|<span data-ttu-id="97659-143">Image</span><span class="sxs-lookup"><span data-stu-id="97659-143">Image</span></span>|  
|<span data-ttu-id="97659-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="97659-144">SysIPAddress32</span></span>|<span data-ttu-id="97659-145">Custom</span><span class="sxs-lookup"><span data-stu-id="97659-145">Custom</span></span>|  
|<span data-ttu-id="97659-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="97659-146">SysHeader32</span></span>|<span data-ttu-id="97659-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="97659-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="97659-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="97659-148">SysListView32</span></span>|<span data-ttu-id="97659-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="97659-149">DataGrid</span></span>|  
|<span data-ttu-id="97659-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="97659-150">SysListView32</span></span>|<span data-ttu-id="97659-151">List</span><span class="sxs-lookup"><span data-stu-id="97659-151">List</span></span>|  
|<span data-ttu-id="97659-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="97659-152">ListBox</span></span>|<span data-ttu-id="97659-153">List</span><span class="sxs-lookup"><span data-stu-id="97659-153">List</span></span>|  
|<span data-ttu-id="97659-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="97659-154">ListBox</span></span>|<span data-ttu-id="97659-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="97659-155">ListItem</span></span>|  
|<span data-ttu-id="97659-156">#32768</span><span class="sxs-lookup"><span data-stu-id="97659-156">#32768</span></span>|<span data-ttu-id="97659-157">Menu</span><span class="sxs-lookup"><span data-stu-id="97659-157">Menu</span></span>|  
|<span data-ttu-id="97659-158">#32768</span><span class="sxs-lookup"><span data-stu-id="97659-158">#32768</span></span>|<span data-ttu-id="97659-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="97659-159">MenuItem</span></span>|  
|<span data-ttu-id="97659-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="97659-160">msctls_progress32</span></span>|<span data-ttu-id="97659-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="97659-161">ProgressBar</span></span>|  
|<span data-ttu-id="97659-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="97659-162">RichEdit</span></span>|<span data-ttu-id="97659-163">Document</span><span class="sxs-lookup"><span data-stu-id="97659-163">Document.</span></span> <span data-ttu-id="97659-164">Vedere la nota.</span><span class="sxs-lookup"><span data-stu-id="97659-164">See note.</span></span>|  
|<span data-ttu-id="97659-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="97659-165">RichEdit20A</span></span>|<span data-ttu-id="97659-166">Document</span><span class="sxs-lookup"><span data-stu-id="97659-166">Document</span></span>|  
|<span data-ttu-id="97659-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="97659-167">RichEdit20W</span></span>|<span data-ttu-id="97659-168">Document</span><span class="sxs-lookup"><span data-stu-id="97659-168">Document</span></span>|  
|<span data-ttu-id="97659-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="97659-169">RichEdit50W</span></span>|<span data-ttu-id="97659-170">Document</span><span class="sxs-lookup"><span data-stu-id="97659-170">Document</span></span>|  
|<span data-ttu-id="97659-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="97659-171">ScrollBar</span></span>|<span data-ttu-id="97659-172">Slider</span><span class="sxs-lookup"><span data-stu-id="97659-172">Slider</span></span>|  
|<span data-ttu-id="97659-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="97659-173">msctls_trackbar32</span></span>|<span data-ttu-id="97659-174">Slider</span><span class="sxs-lookup"><span data-stu-id="97659-174">Slider</span></span>|  
|<span data-ttu-id="97659-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="97659-175">msctls_updown32</span></span>|<span data-ttu-id="97659-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="97659-176">Spinner</span></span>|  
|<span data-ttu-id="97659-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="97659-177">msctls_statusbar32</span></span>|<span data-ttu-id="97659-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="97659-178">StatusBar</span></span>|  
|<span data-ttu-id="97659-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="97659-179">SysTabControl32</span></span>|<span data-ttu-id="97659-180">Scheda</span><span class="sxs-lookup"><span data-stu-id="97659-180">Tab</span></span>|  
|<span data-ttu-id="97659-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="97659-181">SysTabControl32</span></span>|<span data-ttu-id="97659-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="97659-182">TabItem</span></span>|  
|<span data-ttu-id="97659-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="97659-183">ToolbarWindow32</span></span>|<span data-ttu-id="97659-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="97659-184">ToolBar</span></span>|  
|<span data-ttu-id="97659-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="97659-185">ToolbarWindow32</span></span>|<span data-ttu-id="97659-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="97659-186">MenuItem</span></span>|  
|<span data-ttu-id="97659-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="97659-187">ToolbarWindow32</span></span>|<span data-ttu-id="97659-188">Button</span><span class="sxs-lookup"><span data-stu-id="97659-188">Button</span></span>|  
|<span data-ttu-id="97659-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="97659-189">ToolbarWindow32</span></span>|<span data-ttu-id="97659-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="97659-190">CheckBox</span></span>|  
|<span data-ttu-id="97659-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="97659-191">ToolbarWindow32</span></span>|<span data-ttu-id="97659-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="97659-192">RadioButton</span></span>|  
|<span data-ttu-id="97659-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="97659-193">ToolbarWindow32</span></span>|<span data-ttu-id="97659-194">Separatore</span><span class="sxs-lookup"><span data-stu-id="97659-194">Separator</span></span>|  
|<span data-ttu-id="97659-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="97659-195">tooltips_class32</span></span>|<span data-ttu-id="97659-196">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="97659-196">ToolTip</span></span>|  
|<span data-ttu-id="97659-197">#32774</span><span class="sxs-lookup"><span data-stu-id="97659-197">#32774</span></span>|<span data-ttu-id="97659-198">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="97659-198">ToolTip</span></span>|  
|<span data-ttu-id="97659-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="97659-199">ReBarWindow32</span></span>|<span data-ttu-id="97659-200">ToolBar</span><span class="sxs-lookup"><span data-stu-id="97659-200">Toolbar</span></span>|  
|<span data-ttu-id="97659-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="97659-201">SysTreeView32</span></span>|<span data-ttu-id="97659-202">Tree</span><span class="sxs-lookup"><span data-stu-id="97659-202">Tree</span></span>|  
|<span data-ttu-id="97659-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="97659-203">SysTreeView32</span></span>|<span data-ttu-id="97659-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="97659-204">TreeItem</span></span>|  
  
 <span data-ttu-id="97659-205">**Nota** Il controllo RichEdit è supportato solo per le versioni fornite con [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in Riched20.dll versione 3.1 e successive e MsftEdit.dll versione 4.1 e successive).</span><span class="sxs-lookup"><span data-stu-id="97659-205">**Note** The RichEdit control is supported only for versions shipped with [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="97659-206">I controlli seguenti non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="97659-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="97659-207">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="97659-207">Class name</span></span>|<span data-ttu-id="97659-208">Tipo di controllo</span><span class="sxs-lookup"><span data-stu-id="97659-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="97659-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="97659-209">SysAnimate32</span></span>|<span data-ttu-id="97659-210">Image</span><span class="sxs-lookup"><span data-stu-id="97659-210">Image</span></span>|  
|<span data-ttu-id="97659-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="97659-211">SysPager</span></span>|<span data-ttu-id="97659-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="97659-212">Spinner</span></span>|  
|<span data-ttu-id="97659-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="97659-213">SysDateTimePick32</span></span>|<span data-ttu-id="97659-214">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="97659-214">Custom</span></span>|  
|<span data-ttu-id="97659-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="97659-215">SysMonthCal32</span></span>|<span data-ttu-id="97659-216">Calendar</span><span class="sxs-lookup"><span data-stu-id="97659-216">Calendar</span></span>|  
|<span data-ttu-id="97659-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="97659-217">MS_WINNOTE</span></span>|<span data-ttu-id="97659-218">ToolTip</span><span class="sxs-lookup"><span data-stu-id="97659-218">Tooltip</span></span>|  
|<span data-ttu-id="97659-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="97659-219">VBBubble</span></span>|<span data-ttu-id="97659-220">Tooltip</span><span class="sxs-lookup"><span data-stu-id="97659-220">Tooltip</span></span>|  
|<span data-ttu-id="97659-221">ScrollBar (se usato come controllo autonomo)</span><span class="sxs-lookup"><span data-stu-id="97659-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="97659-222">Slider</span><span class="sxs-lookup"><span data-stu-id="97659-222">Slider</span></span>|  
|<span data-ttu-id="97659-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="97659-223">SuperGrid</span></span>|<span data-ttu-id="97659-224">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="97659-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="97659-225">Controlli per Windows Form</span><span class="sxs-lookup"><span data-stu-id="97659-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="97659-226">Controlli Windows Form sono esposti a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tramite provider lato client in UIAutomationClientsideProviders.</span><span class="sxs-lookup"><span data-stu-id="97659-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="97659-227">Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="97659-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="97659-228">In genere, i controlli Windows Form che sono wrapper gestiti per [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controlli comuni supportati da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97659-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="97659-229">I controlli seguenti sono supportati.</span><span class="sxs-lookup"><span data-stu-id="97659-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="97659-230">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="97659-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="97659-231">Button</span><span class="sxs-lookup"><span data-stu-id="97659-231">Button</span></span>|  
|<span data-ttu-id="97659-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="97659-232">CheckBox</span></span>|  
|<span data-ttu-id="97659-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="97659-233">CheckedListBox</span></span>|  
|<span data-ttu-id="97659-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="97659-234">ColorDialog</span></span>|  
|<span data-ttu-id="97659-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="97659-235">ComboBox</span></span>|  
|<span data-ttu-id="97659-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="97659-236">FolderBrowser</span></span>|  
|<span data-ttu-id="97659-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="97659-237">FontDialog</span></span>|  
|<span data-ttu-id="97659-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="97659-238">GroupBox</span></span>|  
|<span data-ttu-id="97659-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="97659-239">HscrollBar</span></span>|  
|<span data-ttu-id="97659-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="97659-240">ImageList</span></span>|  
|<span data-ttu-id="97659-241">Label</span><span class="sxs-lookup"><span data-stu-id="97659-241">Label</span></span>|  
|<span data-ttu-id="97659-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="97659-242">ListBox</span></span>|  
|<span data-ttu-id="97659-243">ListView</span><span class="sxs-lookup"><span data-stu-id="97659-243">ListView</span></span>|  
|<span data-ttu-id="97659-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="97659-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="97659-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="97659-245">MonthCalendar</span></span>|  
|<span data-ttu-id="97659-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="97659-246">NotifyIcon</span></span>|  
|<span data-ttu-id="97659-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="97659-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="97659-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="97659-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="97659-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="97659-249">PrintDialog</span></span>|  
|<span data-ttu-id="97659-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="97659-250">ProgressBar</span></span>|  
|<span data-ttu-id="97659-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="97659-251">RadioButton</span></span>|  
|<span data-ttu-id="97659-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="97659-252">RichTextBox</span></span>|  
|<span data-ttu-id="97659-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="97659-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="97659-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="97659-254">ScrollableControl</span></span>|  
|<span data-ttu-id="97659-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="97659-255">SoundPlayer</span></span>|  
|<span data-ttu-id="97659-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="97659-256">StatusBar</span></span>|  
|<span data-ttu-id="97659-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="97659-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="97659-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="97659-258">TextBox</span></span>|  
|<span data-ttu-id="97659-259">Timer</span><span class="sxs-lookup"><span data-stu-id="97659-259">Timer</span></span>|  
|<span data-ttu-id="97659-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="97659-260">Toolbar</span></span>|  
|<span data-ttu-id="97659-261">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="97659-261">ToolTip</span></span>|  
|<span data-ttu-id="97659-262">Trackbar</span><span class="sxs-lookup"><span data-stu-id="97659-262">TrackBar</span></span>|  
|<span data-ttu-id="97659-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="97659-263">TreeView</span></span>|  
|<span data-ttu-id="97659-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="97659-264">VscrollBar</span></span>|  
|<span data-ttu-id="97659-265">WebBrowser</span><span class="sxs-lookup"><span data-stu-id="97659-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="97659-266">I seguenti controlli sono esposti a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] solo tramite il relativo supporto per [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97659-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span></span> <span data-ttu-id="97659-267">Alcune funzionalità potrebbero non essere disponibili.</span><span class="sxs-lookup"><span data-stu-id="97659-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="97659-268">Nome controllo</span><span class="sxs-lookup"><span data-stu-id="97659-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="97659-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="97659-269">BindingSource</span></span>|  
|<span data-ttu-id="97659-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="97659-270">DataGrid</span></span>|  
|<span data-ttu-id="97659-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="97659-271">DataGridView</span></span>|  
|<span data-ttu-id="97659-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="97659-272">DataNavigator</span></span>|  
|<span data-ttu-id="97659-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="97659-273">DomainUpDown</span></span>|  
|<span data-ttu-id="97659-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="97659-274">ErrorProvider</span></span>|  
|<span data-ttu-id="97659-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="97659-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="97659-276">Form</span><span class="sxs-lookup"><span data-stu-id="97659-276">Form</span></span>|  
|<span data-ttu-id="97659-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="97659-277">LinkLabel</span></span>|  
|<span data-ttu-id="97659-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="97659-278">HelpProvider</span></span>|  
|<span data-ttu-id="97659-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="97659-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="97659-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="97659-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="97659-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="97659-281">NumericUpDown</span></span>|  
|<span data-ttu-id="97659-282">Panel</span><span class="sxs-lookup"><span data-stu-id="97659-282">Panel</span></span>|  
|<span data-ttu-id="97659-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="97659-283">PictureBox</span></span>|  
|<span data-ttu-id="97659-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="97659-284">PrintDocument</span></span>|  
|<span data-ttu-id="97659-285">PrintPreviewControl</span><span class="sxs-lookup"><span data-stu-id="97659-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="97659-286">PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="97659-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="97659-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="97659-287">PropertyGrid</span></span>|  
|<span data-ttu-id="97659-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="97659-288">UserControl</span></span>|  
|<span data-ttu-id="97659-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="97659-289">ToolStrip</span></span>|  
|<span data-ttu-id="97659-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="97659-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="97659-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="97659-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="97659-292">Splitter</span><span class="sxs-lookup"><span data-stu-id="97659-292">Splitter</span></span>|  
|<span data-ttu-id="97659-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="97659-293">RaftingContainer</span></span>|  
|<span data-ttu-id="97659-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="97659-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="97659-295">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97659-295">See Also</span></span>  
 [<span data-ttu-id="97659-296">Tipi di controllo per l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="97659-296">UI Automation Control Types</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types.md)
