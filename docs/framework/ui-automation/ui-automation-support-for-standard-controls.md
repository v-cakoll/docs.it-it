---
title: Supporto per automazione interfaccia utente dei controlli standard
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 9c5e4133a3bc1f019ada00299df929c2e3915880
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54726585"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="5ae40-102">Supporto per automazione interfaccia utente dei controlli standard</span><span class="sxs-lookup"><span data-stu-id="5ae40-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
>  <span data-ttu-id="5ae40-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="5ae40-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="5ae40-104">Per informazioni aggiornate sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: Automazione interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="5ae40-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="5ae40-105">Questo argomento contiene informazioni sul supporto di [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] per i controlli standard in applicazioni sviluppate per i framework [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]e [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5ae40-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="5ae40-106">Controlli WPF (Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="5ae40-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="5ae40-107">Tutti gli elementi di controllo [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] che forniscono informazioni o supporto per l'interazione dell'utente dispongono di supporto nativo completo per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ae40-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="5ae40-108">Gli altri elementi, ad esempio i pannelli, non sono visibile per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ae40-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="5ae40-109">Controlli Win32</span><span class="sxs-lookup"><span data-stu-id="5ae40-109">Win32 Controls</span></span>  
 <span data-ttu-id="5ae40-110">La maggior parte dei controlli [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] è esposta a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tramite provider lato client in UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="5ae40-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="5ae40-111">Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="5ae40-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="5ae40-112">Il supporto completo viene fornito solo per i controlli a partire dalla versione 6 di ComCtrl32.dll (disponibile con [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] e versioni successive).</span><span class="sxs-lookup"><span data-stu-id="5ae40-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="5ae40-113">I controlli seguenti sono supportati.</span><span class="sxs-lookup"><span data-stu-id="5ae40-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="5ae40-114">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="5ae40-114">Class name</span></span>|<span data-ttu-id="5ae40-115">Tipo di controllo</span><span class="sxs-lookup"><span data-stu-id="5ae40-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="5ae40-116">Button</span><span class="sxs-lookup"><span data-stu-id="5ae40-116">Button</span></span>|<span data-ttu-id="5ae40-117">Pulsante</span><span class="sxs-lookup"><span data-stu-id="5ae40-117">Button</span></span>|  
|<span data-ttu-id="5ae40-118">Button</span><span class="sxs-lookup"><span data-stu-id="5ae40-118">Button</span></span>|<span data-ttu-id="5ae40-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="5ae40-119">RadioButton</span></span>|  
|<span data-ttu-id="5ae40-120">Button</span><span class="sxs-lookup"><span data-stu-id="5ae40-120">Button</span></span>|<span data-ttu-id="5ae40-121">Raggruppa</span><span class="sxs-lookup"><span data-stu-id="5ae40-121">Group</span></span>|  
|<span data-ttu-id="5ae40-122">Button</span><span class="sxs-lookup"><span data-stu-id="5ae40-122">Button</span></span>|<span data-ttu-id="5ae40-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="5ae40-123">CheckBox</span></span>|  
|<span data-ttu-id="5ae40-124">Button</span><span class="sxs-lookup"><span data-stu-id="5ae40-124">Button</span></span>|<span data-ttu-id="5ae40-125">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="5ae40-125">Hyperlink</span></span>|  
|<span data-ttu-id="5ae40-126">Button</span><span class="sxs-lookup"><span data-stu-id="5ae40-126">Button</span></span>|<span data-ttu-id="5ae40-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="5ae40-127">SplitButton</span></span>|  
|<span data-ttu-id="5ae40-128">Button</span><span class="sxs-lookup"><span data-stu-id="5ae40-128">Button</span></span>|<span data-ttu-id="5ae40-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="5ae40-129">CheckBox</span></span>|  
|<span data-ttu-id="5ae40-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="5ae40-130">ComboBoxEx32</span></span>|<span data-ttu-id="5ae40-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="5ae40-131">ComboBox</span></span>|  
|<span data-ttu-id="5ae40-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="5ae40-132">ComboBox</span></span>|<span data-ttu-id="5ae40-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="5ae40-133">ComboBox</span></span>|  
|<span data-ttu-id="5ae40-134">Edit</span><span class="sxs-lookup"><span data-stu-id="5ae40-134">Edit</span></span>|<span data-ttu-id="5ae40-135">Document</span><span class="sxs-lookup"><span data-stu-id="5ae40-135">Document</span></span>|  
|<span data-ttu-id="5ae40-136">Edit</span><span class="sxs-lookup"><span data-stu-id="5ae40-136">Edit</span></span>|<span data-ttu-id="5ae40-137">Edit</span><span class="sxs-lookup"><span data-stu-id="5ae40-137">Edit</span></span>|  
|<span data-ttu-id="5ae40-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="5ae40-138">SysLink</span></span>|<span data-ttu-id="5ae40-139">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="5ae40-139">Hyperlink</span></span>|  
|<span data-ttu-id="5ae40-140">Static</span><span class="sxs-lookup"><span data-stu-id="5ae40-140">Static</span></span>|<span data-ttu-id="5ae40-141">Testo</span><span class="sxs-lookup"><span data-stu-id="5ae40-141">Text</span></span>|  
|<span data-ttu-id="5ae40-142">Static</span><span class="sxs-lookup"><span data-stu-id="5ae40-142">Static</span></span>|<span data-ttu-id="5ae40-143">Image</span><span class="sxs-lookup"><span data-stu-id="5ae40-143">Image</span></span>|  
|<span data-ttu-id="5ae40-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="5ae40-144">SysIPAddress32</span></span>|<span data-ttu-id="5ae40-145">Custom</span><span class="sxs-lookup"><span data-stu-id="5ae40-145">Custom</span></span>|  
|<span data-ttu-id="5ae40-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="5ae40-146">SysHeader32</span></span>|<span data-ttu-id="5ae40-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="5ae40-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="5ae40-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="5ae40-148">SysListView32</span></span>|<span data-ttu-id="5ae40-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="5ae40-149">DataGrid</span></span>|  
|<span data-ttu-id="5ae40-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="5ae40-150">SysListView32</span></span>|<span data-ttu-id="5ae40-151">List</span><span class="sxs-lookup"><span data-stu-id="5ae40-151">List</span></span>|  
|<span data-ttu-id="5ae40-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="5ae40-152">ListBox</span></span>|<span data-ttu-id="5ae40-153">List</span><span class="sxs-lookup"><span data-stu-id="5ae40-153">List</span></span>|  
|<span data-ttu-id="5ae40-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="5ae40-154">ListBox</span></span>|<span data-ttu-id="5ae40-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="5ae40-155">ListItem</span></span>|  
|<span data-ttu-id="5ae40-156">#32768</span><span class="sxs-lookup"><span data-stu-id="5ae40-156">#32768</span></span>|<span data-ttu-id="5ae40-157">Menu</span><span class="sxs-lookup"><span data-stu-id="5ae40-157">Menu</span></span>|  
|<span data-ttu-id="5ae40-158">#32768</span><span class="sxs-lookup"><span data-stu-id="5ae40-158">#32768</span></span>|<span data-ttu-id="5ae40-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="5ae40-159">MenuItem</span></span>|  
|<span data-ttu-id="5ae40-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="5ae40-160">msctls_progress32</span></span>|<span data-ttu-id="5ae40-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="5ae40-161">ProgressBar</span></span>|  
|<span data-ttu-id="5ae40-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="5ae40-162">RichEdit</span></span>|<span data-ttu-id="5ae40-163">Document</span><span class="sxs-lookup"><span data-stu-id="5ae40-163">Document.</span></span> <span data-ttu-id="5ae40-164">Vedere la nota.</span><span class="sxs-lookup"><span data-stu-id="5ae40-164">See note.</span></span>|  
|<span data-ttu-id="5ae40-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="5ae40-165">RichEdit20A</span></span>|<span data-ttu-id="5ae40-166">Document</span><span class="sxs-lookup"><span data-stu-id="5ae40-166">Document</span></span>|  
|<span data-ttu-id="5ae40-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="5ae40-167">RichEdit20W</span></span>|<span data-ttu-id="5ae40-168">Document</span><span class="sxs-lookup"><span data-stu-id="5ae40-168">Document</span></span>|  
|<span data-ttu-id="5ae40-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="5ae40-169">RichEdit50W</span></span>|<span data-ttu-id="5ae40-170">Document</span><span class="sxs-lookup"><span data-stu-id="5ae40-170">Document</span></span>|  
|<span data-ttu-id="5ae40-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="5ae40-171">ScrollBar</span></span>|<span data-ttu-id="5ae40-172">Slider</span><span class="sxs-lookup"><span data-stu-id="5ae40-172">Slider</span></span>|  
|<span data-ttu-id="5ae40-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="5ae40-173">msctls_trackbar32</span></span>|<span data-ttu-id="5ae40-174">Slider</span><span class="sxs-lookup"><span data-stu-id="5ae40-174">Slider</span></span>|  
|<span data-ttu-id="5ae40-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="5ae40-175">msctls_updown32</span></span>|<span data-ttu-id="5ae40-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="5ae40-176">Spinner</span></span>|  
|<span data-ttu-id="5ae40-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="5ae40-177">msctls_statusbar32</span></span>|<span data-ttu-id="5ae40-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="5ae40-178">StatusBar</span></span>|  
|<span data-ttu-id="5ae40-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="5ae40-179">SysTabControl32</span></span>|<span data-ttu-id="5ae40-180">Scheda</span><span class="sxs-lookup"><span data-stu-id="5ae40-180">Tab</span></span>|  
|<span data-ttu-id="5ae40-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="5ae40-181">SysTabControl32</span></span>|<span data-ttu-id="5ae40-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="5ae40-182">TabItem</span></span>|  
|<span data-ttu-id="5ae40-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5ae40-183">ToolbarWindow32</span></span>|<span data-ttu-id="5ae40-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="5ae40-184">ToolBar</span></span>|  
|<span data-ttu-id="5ae40-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5ae40-185">ToolbarWindow32</span></span>|<span data-ttu-id="5ae40-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="5ae40-186">MenuItem</span></span>|  
|<span data-ttu-id="5ae40-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5ae40-187">ToolbarWindow32</span></span>|<span data-ttu-id="5ae40-188">Button</span><span class="sxs-lookup"><span data-stu-id="5ae40-188">Button</span></span>|  
|<span data-ttu-id="5ae40-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5ae40-189">ToolbarWindow32</span></span>|<span data-ttu-id="5ae40-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="5ae40-190">CheckBox</span></span>|  
|<span data-ttu-id="5ae40-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5ae40-191">ToolbarWindow32</span></span>|<span data-ttu-id="5ae40-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="5ae40-192">RadioButton</span></span>|  
|<span data-ttu-id="5ae40-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5ae40-193">ToolbarWindow32</span></span>|<span data-ttu-id="5ae40-194">Separatore</span><span class="sxs-lookup"><span data-stu-id="5ae40-194">Separator</span></span>|  
|<span data-ttu-id="5ae40-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="5ae40-195">tooltips_class32</span></span>|<span data-ttu-id="5ae40-196">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="5ae40-196">ToolTip</span></span>|  
|<span data-ttu-id="5ae40-197">#32774</span><span class="sxs-lookup"><span data-stu-id="5ae40-197">#32774</span></span>|<span data-ttu-id="5ae40-198">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="5ae40-198">ToolTip</span></span>|  
|<span data-ttu-id="5ae40-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="5ae40-199">ReBarWindow32</span></span>|<span data-ttu-id="5ae40-200">ToolBar</span><span class="sxs-lookup"><span data-stu-id="5ae40-200">Toolbar</span></span>|  
|<span data-ttu-id="5ae40-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="5ae40-201">SysTreeView32</span></span>|<span data-ttu-id="5ae40-202">Struttura ad albero</span><span class="sxs-lookup"><span data-stu-id="5ae40-202">Tree</span></span>|  
|<span data-ttu-id="5ae40-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="5ae40-203">SysTreeView32</span></span>|<span data-ttu-id="5ae40-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="5ae40-204">TreeItem</span></span>|  
  
 <span data-ttu-id="5ae40-205">**Nota** Il controllo RichEdit è supportato solo per le versioni fornite con [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in Riched20.dll versione 3.1 e successive e MsftEdit.dll versione 4.1 e successive).</span><span class="sxs-lookup"><span data-stu-id="5ae40-205">**Note** The RichEdit control is supported only for versions shipped with [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="5ae40-206">I controlli seguenti non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="5ae40-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="5ae40-207">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="5ae40-207">Class name</span></span>|<span data-ttu-id="5ae40-208">Tipo di controllo</span><span class="sxs-lookup"><span data-stu-id="5ae40-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="5ae40-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="5ae40-209">SysAnimate32</span></span>|<span data-ttu-id="5ae40-210">Image</span><span class="sxs-lookup"><span data-stu-id="5ae40-210">Image</span></span>|  
|<span data-ttu-id="5ae40-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="5ae40-211">SysPager</span></span>|<span data-ttu-id="5ae40-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="5ae40-212">Spinner</span></span>|  
|<span data-ttu-id="5ae40-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="5ae40-213">SysDateTimePick32</span></span>|<span data-ttu-id="5ae40-214">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="5ae40-214">Custom</span></span>|  
|<span data-ttu-id="5ae40-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="5ae40-215">SysMonthCal32</span></span>|<span data-ttu-id="5ae40-216">Calendar</span><span class="sxs-lookup"><span data-stu-id="5ae40-216">Calendar</span></span>|  
|<span data-ttu-id="5ae40-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="5ae40-217">MS_WINNOTE</span></span>|<span data-ttu-id="5ae40-218">ToolTip</span><span class="sxs-lookup"><span data-stu-id="5ae40-218">Tooltip</span></span>|  
|<span data-ttu-id="5ae40-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="5ae40-219">VBBubble</span></span>|<span data-ttu-id="5ae40-220">ToolTip</span><span class="sxs-lookup"><span data-stu-id="5ae40-220">Tooltip</span></span>|  
|<span data-ttu-id="5ae40-221">ScrollBar (se usato come controllo autonomo)</span><span class="sxs-lookup"><span data-stu-id="5ae40-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="5ae40-222">Slider</span><span class="sxs-lookup"><span data-stu-id="5ae40-222">Slider</span></span>|  
|<span data-ttu-id="5ae40-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="5ae40-223">SuperGrid</span></span>|<span data-ttu-id="5ae40-224">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="5ae40-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="5ae40-225">Controlli per Windows Form</span><span class="sxs-lookup"><span data-stu-id="5ae40-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="5ae40-226">Controlli Windows Form sono esposti a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tramite provider lato client in UIAutomationClientsideProviders.</span><span class="sxs-lookup"><span data-stu-id="5ae40-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="5ae40-227">Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="5ae40-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="5ae40-228">In genere, i controlli Windows Form che sono wrapper gestiti per [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controlli comuni supportati da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ae40-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="5ae40-229">I controlli seguenti sono supportati.</span><span class="sxs-lookup"><span data-stu-id="5ae40-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="5ae40-230">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="5ae40-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="5ae40-231">Button</span><span class="sxs-lookup"><span data-stu-id="5ae40-231">Button</span></span>|  
|<span data-ttu-id="5ae40-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="5ae40-232">CheckBox</span></span>|  
|<span data-ttu-id="5ae40-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="5ae40-233">CheckedListBox</span></span>|  
|<span data-ttu-id="5ae40-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="5ae40-234">ColorDialog</span></span>|  
|<span data-ttu-id="5ae40-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="5ae40-235">ComboBox</span></span>|  
|<span data-ttu-id="5ae40-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="5ae40-236">FolderBrowser</span></span>|  
|<span data-ttu-id="5ae40-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="5ae40-237">FontDialog</span></span>|  
|<span data-ttu-id="5ae40-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="5ae40-238">GroupBox</span></span>|  
|<span data-ttu-id="5ae40-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="5ae40-239">HscrollBar</span></span>|  
|<span data-ttu-id="5ae40-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="5ae40-240">ImageList</span></span>|  
|<span data-ttu-id="5ae40-241">Label</span><span class="sxs-lookup"><span data-stu-id="5ae40-241">Label</span></span>|  
|<span data-ttu-id="5ae40-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="5ae40-242">ListBox</span></span>|  
|<span data-ttu-id="5ae40-243">ListView</span><span class="sxs-lookup"><span data-stu-id="5ae40-243">ListView</span></span>|  
|<span data-ttu-id="5ae40-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="5ae40-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="5ae40-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="5ae40-245">MonthCalendar</span></span>|  
|<span data-ttu-id="5ae40-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="5ae40-246">NotifyIcon</span></span>|  
|<span data-ttu-id="5ae40-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="5ae40-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="5ae40-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="5ae40-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="5ae40-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="5ae40-249">PrintDialog</span></span>|  
|<span data-ttu-id="5ae40-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="5ae40-250">ProgressBar</span></span>|  
|<span data-ttu-id="5ae40-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="5ae40-251">RadioButton</span></span>|  
|<span data-ttu-id="5ae40-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="5ae40-252">RichTextBox</span></span>|  
|<span data-ttu-id="5ae40-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="5ae40-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="5ae40-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="5ae40-254">ScrollableControl</span></span>|  
|<span data-ttu-id="5ae40-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="5ae40-255">SoundPlayer</span></span>|  
|<span data-ttu-id="5ae40-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="5ae40-256">StatusBar</span></span>|  
|<span data-ttu-id="5ae40-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="5ae40-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="5ae40-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="5ae40-258">TextBox</span></span>|  
|<span data-ttu-id="5ae40-259">Timer</span><span class="sxs-lookup"><span data-stu-id="5ae40-259">Timer</span></span>|  
|<span data-ttu-id="5ae40-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="5ae40-260">Toolbar</span></span>|  
|<span data-ttu-id="5ae40-261">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="5ae40-261">ToolTip</span></span>|  
|<span data-ttu-id="5ae40-262">Trackbar</span><span class="sxs-lookup"><span data-stu-id="5ae40-262">TrackBar</span></span>|  
|<span data-ttu-id="5ae40-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="5ae40-263">TreeView</span></span>|  
|<span data-ttu-id="5ae40-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="5ae40-264">VscrollBar</span></span>|  
|<span data-ttu-id="5ae40-265">WebBrowser</span><span class="sxs-lookup"><span data-stu-id="5ae40-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="5ae40-266">I seguenti controlli sono esposti a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] solo tramite il relativo supporto per [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ae40-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span></span> <span data-ttu-id="5ae40-267">Alcune funzionalità potrebbero non essere disponibili.</span><span class="sxs-lookup"><span data-stu-id="5ae40-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="5ae40-268">Nome controllo</span><span class="sxs-lookup"><span data-stu-id="5ae40-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="5ae40-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="5ae40-269">BindingSource</span></span>|  
|<span data-ttu-id="5ae40-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="5ae40-270">DataGrid</span></span>|  
|<span data-ttu-id="5ae40-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="5ae40-271">DataGridView</span></span>|  
|<span data-ttu-id="5ae40-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="5ae40-272">DataNavigator</span></span>|  
|<span data-ttu-id="5ae40-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="5ae40-273">DomainUpDown</span></span>|  
|<span data-ttu-id="5ae40-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="5ae40-274">ErrorProvider</span></span>|  
|<span data-ttu-id="5ae40-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="5ae40-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="5ae40-276">Form</span><span class="sxs-lookup"><span data-stu-id="5ae40-276">Form</span></span>|  
|<span data-ttu-id="5ae40-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="5ae40-277">LinkLabel</span></span>|  
|<span data-ttu-id="5ae40-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="5ae40-278">HelpProvider</span></span>|  
|<span data-ttu-id="5ae40-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="5ae40-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="5ae40-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="5ae40-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="5ae40-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="5ae40-281">NumericUpDown</span></span>|  
|<span data-ttu-id="5ae40-282">Panel</span><span class="sxs-lookup"><span data-stu-id="5ae40-282">Panel</span></span>|  
|<span data-ttu-id="5ae40-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="5ae40-283">PictureBox</span></span>|  
|<span data-ttu-id="5ae40-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="5ae40-284">PrintDocument</span></span>|  
|<span data-ttu-id="5ae40-285">PrintPreviewControl</span><span class="sxs-lookup"><span data-stu-id="5ae40-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="5ae40-286">PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="5ae40-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="5ae40-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="5ae40-287">PropertyGrid</span></span>|  
|<span data-ttu-id="5ae40-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="5ae40-288">UserControl</span></span>|  
|<span data-ttu-id="5ae40-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="5ae40-289">ToolStrip</span></span>|  
|<span data-ttu-id="5ae40-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="5ae40-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="5ae40-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="5ae40-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="5ae40-292">Splitter</span><span class="sxs-lookup"><span data-stu-id="5ae40-292">Splitter</span></span>|  
|<span data-ttu-id="5ae40-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="5ae40-293">RaftingContainer</span></span>|  
|<span data-ttu-id="5ae40-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="5ae40-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5ae40-295">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ae40-295">See also</span></span>
- [<span data-ttu-id="5ae40-296">Tipi di controllo per l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="5ae40-296">UI Automation Control Types</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types.md)
