---
title: Supporto per automazione interfaccia utente dei controlli standard
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 3ccd6e1348125f5d901e0f093d2b5483b818719f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33409091"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="4816b-102">Supporto per automazione interfaccia utente dei controlli standard</span><span class="sxs-lookup"><span data-stu-id="4816b-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
>  <span data-ttu-id="4816b-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="4816b-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="4816b-104">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere l'argomento sull' [API Automazione interfaccia utente di Windows](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="4816b-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="4816b-105">Questo argomento contiene informazioni sul supporto di [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] per i controlli standard in applicazioni sviluppate per i framework [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]e [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4816b-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="4816b-106">Controlli WPF (Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="4816b-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="4816b-107">Tutti gli elementi di controllo [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] che forniscono informazioni o supporto per l'interazione dell'utente dispongono di supporto nativo completo per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4816b-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="4816b-108">Gli altri elementi, ad esempio i pannelli, non sono visibile per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4816b-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="4816b-109">Controlli Win32</span><span class="sxs-lookup"><span data-stu-id="4816b-109">Win32 Controls</span></span>  
 <span data-ttu-id="4816b-110">La maggior parte dei controlli [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] è esposta a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tramite provider lato client in UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="4816b-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="4816b-111">Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="4816b-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="4816b-112">Il supporto completo viene fornito solo per i controlli a partire dalla versione 6 di ComCtrl32.dll (disponibile con [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] e versioni successive).</span><span class="sxs-lookup"><span data-stu-id="4816b-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="4816b-113">I controlli seguenti sono supportati.</span><span class="sxs-lookup"><span data-stu-id="4816b-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="4816b-114">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="4816b-114">Class name</span></span>|<span data-ttu-id="4816b-115">Tipo di controllo</span><span class="sxs-lookup"><span data-stu-id="4816b-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="4816b-116">Button</span><span class="sxs-lookup"><span data-stu-id="4816b-116">Button</span></span>|<span data-ttu-id="4816b-117">Pulsante</span><span class="sxs-lookup"><span data-stu-id="4816b-117">Button</span></span>|  
|<span data-ttu-id="4816b-118">Button</span><span class="sxs-lookup"><span data-stu-id="4816b-118">Button</span></span>|<span data-ttu-id="4816b-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="4816b-119">RadioButton</span></span>|  
|<span data-ttu-id="4816b-120">Button</span><span class="sxs-lookup"><span data-stu-id="4816b-120">Button</span></span>|<span data-ttu-id="4816b-121">Group</span><span class="sxs-lookup"><span data-stu-id="4816b-121">Group</span></span>|  
|<span data-ttu-id="4816b-122">Button</span><span class="sxs-lookup"><span data-stu-id="4816b-122">Button</span></span>|<span data-ttu-id="4816b-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="4816b-123">CheckBox</span></span>|  
|<span data-ttu-id="4816b-124">Button</span><span class="sxs-lookup"><span data-stu-id="4816b-124">Button</span></span>|<span data-ttu-id="4816b-125">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="4816b-125">Hyperlink</span></span>|  
|<span data-ttu-id="4816b-126">Button</span><span class="sxs-lookup"><span data-stu-id="4816b-126">Button</span></span>|<span data-ttu-id="4816b-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="4816b-127">SplitButton</span></span>|  
|<span data-ttu-id="4816b-128">Button</span><span class="sxs-lookup"><span data-stu-id="4816b-128">Button</span></span>|<span data-ttu-id="4816b-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="4816b-129">CheckBox</span></span>|  
|<span data-ttu-id="4816b-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="4816b-130">ComboBoxEx32</span></span>|<span data-ttu-id="4816b-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="4816b-131">ComboBox</span></span>|  
|<span data-ttu-id="4816b-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="4816b-132">ComboBox</span></span>|<span data-ttu-id="4816b-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="4816b-133">ComboBox</span></span>|  
|<span data-ttu-id="4816b-134">Edit</span><span class="sxs-lookup"><span data-stu-id="4816b-134">Edit</span></span>|<span data-ttu-id="4816b-135">Document</span><span class="sxs-lookup"><span data-stu-id="4816b-135">Document</span></span>|  
|<span data-ttu-id="4816b-136">Edit</span><span class="sxs-lookup"><span data-stu-id="4816b-136">Edit</span></span>|<span data-ttu-id="4816b-137">Edit</span><span class="sxs-lookup"><span data-stu-id="4816b-137">Edit</span></span>|  
|<span data-ttu-id="4816b-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="4816b-138">SysLink</span></span>|<span data-ttu-id="4816b-139">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="4816b-139">Hyperlink</span></span>|  
|<span data-ttu-id="4816b-140">Static</span><span class="sxs-lookup"><span data-stu-id="4816b-140">Static</span></span>|<span data-ttu-id="4816b-141">Testo</span><span class="sxs-lookup"><span data-stu-id="4816b-141">Text</span></span>|  
|<span data-ttu-id="4816b-142">Static</span><span class="sxs-lookup"><span data-stu-id="4816b-142">Static</span></span>|<span data-ttu-id="4816b-143">Image</span><span class="sxs-lookup"><span data-stu-id="4816b-143">Image</span></span>|  
|<span data-ttu-id="4816b-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="4816b-144">SysIPAddress32</span></span>|<span data-ttu-id="4816b-145">Custom</span><span class="sxs-lookup"><span data-stu-id="4816b-145">Custom</span></span>|  
|<span data-ttu-id="4816b-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="4816b-146">SysHeader32</span></span>|<span data-ttu-id="4816b-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="4816b-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="4816b-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="4816b-148">SysListView32</span></span>|<span data-ttu-id="4816b-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="4816b-149">DataGrid</span></span>|  
|<span data-ttu-id="4816b-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="4816b-150">SysListView32</span></span>|<span data-ttu-id="4816b-151">List</span><span class="sxs-lookup"><span data-stu-id="4816b-151">List</span></span>|  
|<span data-ttu-id="4816b-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="4816b-152">ListBox</span></span>|<span data-ttu-id="4816b-153">List</span><span class="sxs-lookup"><span data-stu-id="4816b-153">List</span></span>|  
|<span data-ttu-id="4816b-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="4816b-154">ListBox</span></span>|<span data-ttu-id="4816b-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="4816b-155">ListItem</span></span>|  
|<span data-ttu-id="4816b-156">#32768</span><span class="sxs-lookup"><span data-stu-id="4816b-156">#32768</span></span>|<span data-ttu-id="4816b-157">Menu</span><span class="sxs-lookup"><span data-stu-id="4816b-157">Menu</span></span>|  
|<span data-ttu-id="4816b-158">#32768</span><span class="sxs-lookup"><span data-stu-id="4816b-158">#32768</span></span>|<span data-ttu-id="4816b-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="4816b-159">MenuItem</span></span>|  
|<span data-ttu-id="4816b-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="4816b-160">msctls_progress32</span></span>|<span data-ttu-id="4816b-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="4816b-161">ProgressBar</span></span>|  
|<span data-ttu-id="4816b-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="4816b-162">RichEdit</span></span>|<span data-ttu-id="4816b-163">Document</span><span class="sxs-lookup"><span data-stu-id="4816b-163">Document.</span></span> <span data-ttu-id="4816b-164">Vedere la nota.</span><span class="sxs-lookup"><span data-stu-id="4816b-164">See note.</span></span>|  
|<span data-ttu-id="4816b-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="4816b-165">RichEdit20A</span></span>|<span data-ttu-id="4816b-166">Document</span><span class="sxs-lookup"><span data-stu-id="4816b-166">Document</span></span>|  
|<span data-ttu-id="4816b-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="4816b-167">RichEdit20W</span></span>|<span data-ttu-id="4816b-168">Document</span><span class="sxs-lookup"><span data-stu-id="4816b-168">Document</span></span>|  
|<span data-ttu-id="4816b-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="4816b-169">RichEdit50W</span></span>|<span data-ttu-id="4816b-170">Document</span><span class="sxs-lookup"><span data-stu-id="4816b-170">Document</span></span>|  
|<span data-ttu-id="4816b-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="4816b-171">ScrollBar</span></span>|<span data-ttu-id="4816b-172">Slider</span><span class="sxs-lookup"><span data-stu-id="4816b-172">Slider</span></span>|  
|<span data-ttu-id="4816b-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="4816b-173">msctls_trackbar32</span></span>|<span data-ttu-id="4816b-174">Slider</span><span class="sxs-lookup"><span data-stu-id="4816b-174">Slider</span></span>|  
|<span data-ttu-id="4816b-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="4816b-175">msctls_updown32</span></span>|<span data-ttu-id="4816b-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="4816b-176">Spinner</span></span>|  
|<span data-ttu-id="4816b-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="4816b-177">msctls_statusbar32</span></span>|<span data-ttu-id="4816b-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="4816b-178">StatusBar</span></span>|  
|<span data-ttu-id="4816b-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="4816b-179">SysTabControl32</span></span>|<span data-ttu-id="4816b-180">Scheda</span><span class="sxs-lookup"><span data-stu-id="4816b-180">Tab</span></span>|  
|<span data-ttu-id="4816b-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="4816b-181">SysTabControl32</span></span>|<span data-ttu-id="4816b-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="4816b-182">TabItem</span></span>|  
|<span data-ttu-id="4816b-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="4816b-183">ToolbarWindow32</span></span>|<span data-ttu-id="4816b-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="4816b-184">ToolBar</span></span>|  
|<span data-ttu-id="4816b-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="4816b-185">ToolbarWindow32</span></span>|<span data-ttu-id="4816b-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="4816b-186">MenuItem</span></span>|  
|<span data-ttu-id="4816b-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="4816b-187">ToolbarWindow32</span></span>|<span data-ttu-id="4816b-188">Button</span><span class="sxs-lookup"><span data-stu-id="4816b-188">Button</span></span>|  
|<span data-ttu-id="4816b-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="4816b-189">ToolbarWindow32</span></span>|<span data-ttu-id="4816b-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="4816b-190">CheckBox</span></span>|  
|<span data-ttu-id="4816b-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="4816b-191">ToolbarWindow32</span></span>|<span data-ttu-id="4816b-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="4816b-192">RadioButton</span></span>|  
|<span data-ttu-id="4816b-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="4816b-193">ToolbarWindow32</span></span>|<span data-ttu-id="4816b-194">Separatore</span><span class="sxs-lookup"><span data-stu-id="4816b-194">Separator</span></span>|  
|<span data-ttu-id="4816b-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="4816b-195">tooltips_class32</span></span>|<span data-ttu-id="4816b-196">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="4816b-196">ToolTip</span></span>|  
|<span data-ttu-id="4816b-197">#32774</span><span class="sxs-lookup"><span data-stu-id="4816b-197">#32774</span></span>|<span data-ttu-id="4816b-198">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="4816b-198">ToolTip</span></span>|  
|<span data-ttu-id="4816b-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="4816b-199">ReBarWindow32</span></span>|<span data-ttu-id="4816b-200">ToolBar</span><span class="sxs-lookup"><span data-stu-id="4816b-200">Toolbar</span></span>|  
|<span data-ttu-id="4816b-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="4816b-201">SysTreeView32</span></span>|<span data-ttu-id="4816b-202">Tree</span><span class="sxs-lookup"><span data-stu-id="4816b-202">Tree</span></span>|  
|<span data-ttu-id="4816b-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="4816b-203">SysTreeView32</span></span>|<span data-ttu-id="4816b-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="4816b-204">TreeItem</span></span>|  
  
 <span data-ttu-id="4816b-205">**Nota** Il controllo RichEdit è supportato solo per le versioni fornite con [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in Riched20.dll versione 3.1 e successive e MsftEdit.dll versione 4.1 e successive).</span><span class="sxs-lookup"><span data-stu-id="4816b-205">**Note** The RichEdit control is supported only for versions shipped with [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="4816b-206">I controlli seguenti non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="4816b-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="4816b-207">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="4816b-207">Class name</span></span>|<span data-ttu-id="4816b-208">Tipo di controllo</span><span class="sxs-lookup"><span data-stu-id="4816b-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="4816b-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="4816b-209">SysAnimate32</span></span>|<span data-ttu-id="4816b-210">Image</span><span class="sxs-lookup"><span data-stu-id="4816b-210">Image</span></span>|  
|<span data-ttu-id="4816b-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="4816b-211">SysPager</span></span>|<span data-ttu-id="4816b-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="4816b-212">Spinner</span></span>|  
|<span data-ttu-id="4816b-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="4816b-213">SysDateTimePick32</span></span>|<span data-ttu-id="4816b-214">Custom (Personalizzati)</span><span class="sxs-lookup"><span data-stu-id="4816b-214">Custom</span></span>|  
|<span data-ttu-id="4816b-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="4816b-215">SysMonthCal32</span></span>|<span data-ttu-id="4816b-216">Calendar</span><span class="sxs-lookup"><span data-stu-id="4816b-216">Calendar</span></span>|  
|<span data-ttu-id="4816b-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="4816b-217">MS_WINNOTE</span></span>|<span data-ttu-id="4816b-218">ToolTip</span><span class="sxs-lookup"><span data-stu-id="4816b-218">Tooltip</span></span>|  
|<span data-ttu-id="4816b-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="4816b-219">VBBubble</span></span>|<span data-ttu-id="4816b-220">Tooltip</span><span class="sxs-lookup"><span data-stu-id="4816b-220">Tooltip</span></span>|  
|<span data-ttu-id="4816b-221">ScrollBar (se usato come controllo autonomo)</span><span class="sxs-lookup"><span data-stu-id="4816b-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="4816b-222">Slider</span><span class="sxs-lookup"><span data-stu-id="4816b-222">Slider</span></span>|  
|<span data-ttu-id="4816b-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="4816b-223">SuperGrid</span></span>|<span data-ttu-id="4816b-224">Custom (Personalizzati)</span><span class="sxs-lookup"><span data-stu-id="4816b-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="4816b-225">Controlli per Windows Form</span><span class="sxs-lookup"><span data-stu-id="4816b-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="4816b-226">Controlli Windows Form sono esposti a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tramite provider lato client in UIAutomationClientsideProviders.</span><span class="sxs-lookup"><span data-stu-id="4816b-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="4816b-227">Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="4816b-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="4816b-228">In genere, i controlli Windows Form che sono wrapper gestiti per [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controlli comuni supportati da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4816b-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="4816b-229">I controlli seguenti sono supportati.</span><span class="sxs-lookup"><span data-stu-id="4816b-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="4816b-230">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="4816b-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="4816b-231">Button</span><span class="sxs-lookup"><span data-stu-id="4816b-231">Button</span></span>|  
|<span data-ttu-id="4816b-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="4816b-232">CheckBox</span></span>|  
|<span data-ttu-id="4816b-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="4816b-233">CheckedListBox</span></span>|  
|<span data-ttu-id="4816b-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="4816b-234">ColorDialog</span></span>|  
|<span data-ttu-id="4816b-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="4816b-235">ComboBox</span></span>|  
|<span data-ttu-id="4816b-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="4816b-236">FolderBrowser</span></span>|  
|<span data-ttu-id="4816b-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="4816b-237">FontDialog</span></span>|  
|<span data-ttu-id="4816b-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="4816b-238">GroupBox</span></span>|  
|<span data-ttu-id="4816b-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="4816b-239">HscrollBar</span></span>|  
|<span data-ttu-id="4816b-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="4816b-240">ImageList</span></span>|  
|<span data-ttu-id="4816b-241">Label</span><span class="sxs-lookup"><span data-stu-id="4816b-241">Label</span></span>|  
|<span data-ttu-id="4816b-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="4816b-242">ListBox</span></span>|  
|<span data-ttu-id="4816b-243">ListView</span><span class="sxs-lookup"><span data-stu-id="4816b-243">ListView</span></span>|  
|<span data-ttu-id="4816b-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="4816b-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="4816b-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="4816b-245">MonthCalendar</span></span>|  
|<span data-ttu-id="4816b-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="4816b-246">NotifyIcon</span></span>|  
|<span data-ttu-id="4816b-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="4816b-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="4816b-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="4816b-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="4816b-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="4816b-249">PrintDialog</span></span>|  
|<span data-ttu-id="4816b-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="4816b-250">ProgressBar</span></span>|  
|<span data-ttu-id="4816b-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="4816b-251">RadioButton</span></span>|  
|<span data-ttu-id="4816b-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="4816b-252">RichTextBox</span></span>|  
|<span data-ttu-id="4816b-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="4816b-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="4816b-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="4816b-254">ScrollableControl</span></span>|  
|<span data-ttu-id="4816b-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="4816b-255">SoundPlayer</span></span>|  
|<span data-ttu-id="4816b-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="4816b-256">StatusBar</span></span>|  
|<span data-ttu-id="4816b-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="4816b-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="4816b-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="4816b-258">TextBox</span></span>|  
|<span data-ttu-id="4816b-259">Timer</span><span class="sxs-lookup"><span data-stu-id="4816b-259">Timer</span></span>|  
|<span data-ttu-id="4816b-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="4816b-260">Toolbar</span></span>|  
|<span data-ttu-id="4816b-261">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="4816b-261">ToolTip</span></span>|  
|<span data-ttu-id="4816b-262">Trackbar</span><span class="sxs-lookup"><span data-stu-id="4816b-262">TrackBar</span></span>|  
|<span data-ttu-id="4816b-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="4816b-263">TreeView</span></span>|  
|<span data-ttu-id="4816b-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="4816b-264">VscrollBar</span></span>|  
|<span data-ttu-id="4816b-265">WebBrowser</span><span class="sxs-lookup"><span data-stu-id="4816b-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="4816b-266">I seguenti controlli sono esposti a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] solo tramite il relativo supporto per [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4816b-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span></span> <span data-ttu-id="4816b-267">Alcune funzionalità potrebbero non essere disponibili.</span><span class="sxs-lookup"><span data-stu-id="4816b-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="4816b-268">Nome controllo</span><span class="sxs-lookup"><span data-stu-id="4816b-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="4816b-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="4816b-269">BindingSource</span></span>|  
|<span data-ttu-id="4816b-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="4816b-270">DataGrid</span></span>|  
|<span data-ttu-id="4816b-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="4816b-271">DataGridView</span></span>|  
|<span data-ttu-id="4816b-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="4816b-272">DataNavigator</span></span>|  
|<span data-ttu-id="4816b-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="4816b-273">DomainUpDown</span></span>|  
|<span data-ttu-id="4816b-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="4816b-274">ErrorProvider</span></span>|  
|<span data-ttu-id="4816b-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="4816b-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="4816b-276">Form</span><span class="sxs-lookup"><span data-stu-id="4816b-276">Form</span></span>|  
|<span data-ttu-id="4816b-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="4816b-277">LinkLabel</span></span>|  
|<span data-ttu-id="4816b-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="4816b-278">HelpProvider</span></span>|  
|<span data-ttu-id="4816b-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="4816b-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="4816b-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="4816b-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="4816b-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="4816b-281">NumericUpDown</span></span>|  
|<span data-ttu-id="4816b-282">Panel</span><span class="sxs-lookup"><span data-stu-id="4816b-282">Panel</span></span>|  
|<span data-ttu-id="4816b-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="4816b-283">PictureBox</span></span>|  
|<span data-ttu-id="4816b-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="4816b-284">PrintDocument</span></span>|  
|<span data-ttu-id="4816b-285">PrintPreviewControl</span><span class="sxs-lookup"><span data-stu-id="4816b-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="4816b-286">PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="4816b-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="4816b-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="4816b-287">PropertyGrid</span></span>|  
|<span data-ttu-id="4816b-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="4816b-288">UserControl</span></span>|  
|<span data-ttu-id="4816b-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="4816b-289">ToolStrip</span></span>|  
|<span data-ttu-id="4816b-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="4816b-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="4816b-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="4816b-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="4816b-292">Splitter</span><span class="sxs-lookup"><span data-stu-id="4816b-292">Splitter</span></span>|  
|<span data-ttu-id="4816b-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="4816b-293">RaftingContainer</span></span>|  
|<span data-ttu-id="4816b-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="4816b-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4816b-295">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4816b-295">See Also</span></span>  
 [<span data-ttu-id="4816b-296">Tipi di controllo per l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="4816b-296">UI Automation Control Types</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types.md)
