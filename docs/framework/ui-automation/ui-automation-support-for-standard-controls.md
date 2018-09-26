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
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47193885"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="892c4-102">Supporto per automazione interfaccia utente dei controlli standard</span><span class="sxs-lookup"><span data-stu-id="892c4-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
>  <span data-ttu-id="892c4-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="892c4-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="892c4-104">Per informazioni aggiornate sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione dell'interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="892c4-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="892c4-105">Questo argomento contiene informazioni sul supporto di [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] per i controlli standard in applicazioni sviluppate per i framework [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]e [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="892c4-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="892c4-106">Controlli WPF (Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="892c4-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="892c4-107">Tutti gli elementi di controllo [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] che forniscono informazioni o supporto per l'interazione dell'utente dispongono di supporto nativo completo per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="892c4-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="892c4-108">Gli altri elementi, ad esempio i pannelli, non sono visibile per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="892c4-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="892c4-109">Controlli Win32</span><span class="sxs-lookup"><span data-stu-id="892c4-109">Win32 Controls</span></span>  
 <span data-ttu-id="892c4-110">La maggior parte dei controlli [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] è esposta a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tramite provider lato client in UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="892c4-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="892c4-111">Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="892c4-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="892c4-112">Il supporto completo viene fornito solo per i controlli a partire dalla versione 6 di ComCtrl32.dll (disponibile con [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] e versioni successive).</span><span class="sxs-lookup"><span data-stu-id="892c4-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="892c4-113">I controlli seguenti sono supportati.</span><span class="sxs-lookup"><span data-stu-id="892c4-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="892c4-114">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="892c4-114">Class name</span></span>|<span data-ttu-id="892c4-115">Tipo di controllo</span><span class="sxs-lookup"><span data-stu-id="892c4-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="892c4-116">Button</span><span class="sxs-lookup"><span data-stu-id="892c4-116">Button</span></span>|<span data-ttu-id="892c4-117">Pulsante</span><span class="sxs-lookup"><span data-stu-id="892c4-117">Button</span></span>|  
|<span data-ttu-id="892c4-118">Button</span><span class="sxs-lookup"><span data-stu-id="892c4-118">Button</span></span>|<span data-ttu-id="892c4-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="892c4-119">RadioButton</span></span>|  
|<span data-ttu-id="892c4-120">Button</span><span class="sxs-lookup"><span data-stu-id="892c4-120">Button</span></span>|<span data-ttu-id="892c4-121">Group</span><span class="sxs-lookup"><span data-stu-id="892c4-121">Group</span></span>|  
|<span data-ttu-id="892c4-122">Button</span><span class="sxs-lookup"><span data-stu-id="892c4-122">Button</span></span>|<span data-ttu-id="892c4-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="892c4-123">CheckBox</span></span>|  
|<span data-ttu-id="892c4-124">Button</span><span class="sxs-lookup"><span data-stu-id="892c4-124">Button</span></span>|<span data-ttu-id="892c4-125">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="892c4-125">Hyperlink</span></span>|  
|<span data-ttu-id="892c4-126">Button</span><span class="sxs-lookup"><span data-stu-id="892c4-126">Button</span></span>|<span data-ttu-id="892c4-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="892c4-127">SplitButton</span></span>|  
|<span data-ttu-id="892c4-128">Button</span><span class="sxs-lookup"><span data-stu-id="892c4-128">Button</span></span>|<span data-ttu-id="892c4-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="892c4-129">CheckBox</span></span>|  
|<span data-ttu-id="892c4-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="892c4-130">ComboBoxEx32</span></span>|<span data-ttu-id="892c4-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="892c4-131">ComboBox</span></span>|  
|<span data-ttu-id="892c4-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="892c4-132">ComboBox</span></span>|<span data-ttu-id="892c4-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="892c4-133">ComboBox</span></span>|  
|<span data-ttu-id="892c4-134">Edit</span><span class="sxs-lookup"><span data-stu-id="892c4-134">Edit</span></span>|<span data-ttu-id="892c4-135">Document</span><span class="sxs-lookup"><span data-stu-id="892c4-135">Document</span></span>|  
|<span data-ttu-id="892c4-136">Edit</span><span class="sxs-lookup"><span data-stu-id="892c4-136">Edit</span></span>|<span data-ttu-id="892c4-137">Edit</span><span class="sxs-lookup"><span data-stu-id="892c4-137">Edit</span></span>|  
|<span data-ttu-id="892c4-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="892c4-138">SysLink</span></span>|<span data-ttu-id="892c4-139">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="892c4-139">Hyperlink</span></span>|  
|<span data-ttu-id="892c4-140">Static</span><span class="sxs-lookup"><span data-stu-id="892c4-140">Static</span></span>|<span data-ttu-id="892c4-141">Testo</span><span class="sxs-lookup"><span data-stu-id="892c4-141">Text</span></span>|  
|<span data-ttu-id="892c4-142">Static</span><span class="sxs-lookup"><span data-stu-id="892c4-142">Static</span></span>|<span data-ttu-id="892c4-143">Image</span><span class="sxs-lookup"><span data-stu-id="892c4-143">Image</span></span>|  
|<span data-ttu-id="892c4-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="892c4-144">SysIPAddress32</span></span>|<span data-ttu-id="892c4-145">Custom</span><span class="sxs-lookup"><span data-stu-id="892c4-145">Custom</span></span>|  
|<span data-ttu-id="892c4-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="892c4-146">SysHeader32</span></span>|<span data-ttu-id="892c4-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="892c4-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="892c4-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="892c4-148">SysListView32</span></span>|<span data-ttu-id="892c4-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="892c4-149">DataGrid</span></span>|  
|<span data-ttu-id="892c4-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="892c4-150">SysListView32</span></span>|<span data-ttu-id="892c4-151">List</span><span class="sxs-lookup"><span data-stu-id="892c4-151">List</span></span>|  
|<span data-ttu-id="892c4-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="892c4-152">ListBox</span></span>|<span data-ttu-id="892c4-153">List</span><span class="sxs-lookup"><span data-stu-id="892c4-153">List</span></span>|  
|<span data-ttu-id="892c4-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="892c4-154">ListBox</span></span>|<span data-ttu-id="892c4-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="892c4-155">ListItem</span></span>|  
|<span data-ttu-id="892c4-156">#32768</span><span class="sxs-lookup"><span data-stu-id="892c4-156">#32768</span></span>|<span data-ttu-id="892c4-157">Menu</span><span class="sxs-lookup"><span data-stu-id="892c4-157">Menu</span></span>|  
|<span data-ttu-id="892c4-158">#32768</span><span class="sxs-lookup"><span data-stu-id="892c4-158">#32768</span></span>|<span data-ttu-id="892c4-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="892c4-159">MenuItem</span></span>|  
|<span data-ttu-id="892c4-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="892c4-160">msctls_progress32</span></span>|<span data-ttu-id="892c4-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="892c4-161">ProgressBar</span></span>|  
|<span data-ttu-id="892c4-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="892c4-162">RichEdit</span></span>|<span data-ttu-id="892c4-163">Document</span><span class="sxs-lookup"><span data-stu-id="892c4-163">Document.</span></span> <span data-ttu-id="892c4-164">Vedere la nota.</span><span class="sxs-lookup"><span data-stu-id="892c4-164">See note.</span></span>|  
|<span data-ttu-id="892c4-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="892c4-165">RichEdit20A</span></span>|<span data-ttu-id="892c4-166">Document</span><span class="sxs-lookup"><span data-stu-id="892c4-166">Document</span></span>|  
|<span data-ttu-id="892c4-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="892c4-167">RichEdit20W</span></span>|<span data-ttu-id="892c4-168">Document</span><span class="sxs-lookup"><span data-stu-id="892c4-168">Document</span></span>|  
|<span data-ttu-id="892c4-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="892c4-169">RichEdit50W</span></span>|<span data-ttu-id="892c4-170">Document</span><span class="sxs-lookup"><span data-stu-id="892c4-170">Document</span></span>|  
|<span data-ttu-id="892c4-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="892c4-171">ScrollBar</span></span>|<span data-ttu-id="892c4-172">Slider</span><span class="sxs-lookup"><span data-stu-id="892c4-172">Slider</span></span>|  
|<span data-ttu-id="892c4-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="892c4-173">msctls_trackbar32</span></span>|<span data-ttu-id="892c4-174">Slider</span><span class="sxs-lookup"><span data-stu-id="892c4-174">Slider</span></span>|  
|<span data-ttu-id="892c4-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="892c4-175">msctls_updown32</span></span>|<span data-ttu-id="892c4-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="892c4-176">Spinner</span></span>|  
|<span data-ttu-id="892c4-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="892c4-177">msctls_statusbar32</span></span>|<span data-ttu-id="892c4-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="892c4-178">StatusBar</span></span>|  
|<span data-ttu-id="892c4-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="892c4-179">SysTabControl32</span></span>|<span data-ttu-id="892c4-180">Scheda</span><span class="sxs-lookup"><span data-stu-id="892c4-180">Tab</span></span>|  
|<span data-ttu-id="892c4-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="892c4-181">SysTabControl32</span></span>|<span data-ttu-id="892c4-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="892c4-182">TabItem</span></span>|  
|<span data-ttu-id="892c4-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="892c4-183">ToolbarWindow32</span></span>|<span data-ttu-id="892c4-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="892c4-184">ToolBar</span></span>|  
|<span data-ttu-id="892c4-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="892c4-185">ToolbarWindow32</span></span>|<span data-ttu-id="892c4-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="892c4-186">MenuItem</span></span>|  
|<span data-ttu-id="892c4-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="892c4-187">ToolbarWindow32</span></span>|<span data-ttu-id="892c4-188">Button</span><span class="sxs-lookup"><span data-stu-id="892c4-188">Button</span></span>|  
|<span data-ttu-id="892c4-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="892c4-189">ToolbarWindow32</span></span>|<span data-ttu-id="892c4-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="892c4-190">CheckBox</span></span>|  
|<span data-ttu-id="892c4-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="892c4-191">ToolbarWindow32</span></span>|<span data-ttu-id="892c4-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="892c4-192">RadioButton</span></span>|  
|<span data-ttu-id="892c4-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="892c4-193">ToolbarWindow32</span></span>|<span data-ttu-id="892c4-194">Separatore</span><span class="sxs-lookup"><span data-stu-id="892c4-194">Separator</span></span>|  
|<span data-ttu-id="892c4-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="892c4-195">tooltips_class32</span></span>|<span data-ttu-id="892c4-196">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="892c4-196">ToolTip</span></span>|  
|<span data-ttu-id="892c4-197">#32774</span><span class="sxs-lookup"><span data-stu-id="892c4-197">#32774</span></span>|<span data-ttu-id="892c4-198">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="892c4-198">ToolTip</span></span>|  
|<span data-ttu-id="892c4-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="892c4-199">ReBarWindow32</span></span>|<span data-ttu-id="892c4-200">ToolBar</span><span class="sxs-lookup"><span data-stu-id="892c4-200">Toolbar</span></span>|  
|<span data-ttu-id="892c4-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="892c4-201">SysTreeView32</span></span>|<span data-ttu-id="892c4-202">Tree</span><span class="sxs-lookup"><span data-stu-id="892c4-202">Tree</span></span>|  
|<span data-ttu-id="892c4-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="892c4-203">SysTreeView32</span></span>|<span data-ttu-id="892c4-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="892c4-204">TreeItem</span></span>|  
  
 <span data-ttu-id="892c4-205">**Nota** Il controllo RichEdit è supportato solo per le versioni fornite con [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in Riched20.dll versione 3.1 e successive e MsftEdit.dll versione 4.1 e successive).</span><span class="sxs-lookup"><span data-stu-id="892c4-205">**Note** The RichEdit control is supported only for versions shipped with [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="892c4-206">I controlli seguenti non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="892c4-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="892c4-207">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="892c4-207">Class name</span></span>|<span data-ttu-id="892c4-208">Tipo di controllo</span><span class="sxs-lookup"><span data-stu-id="892c4-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="892c4-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="892c4-209">SysAnimate32</span></span>|<span data-ttu-id="892c4-210">Image</span><span class="sxs-lookup"><span data-stu-id="892c4-210">Image</span></span>|  
|<span data-ttu-id="892c4-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="892c4-211">SysPager</span></span>|<span data-ttu-id="892c4-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="892c4-212">Spinner</span></span>|  
|<span data-ttu-id="892c4-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="892c4-213">SysDateTimePick32</span></span>|<span data-ttu-id="892c4-214">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="892c4-214">Custom</span></span>|  
|<span data-ttu-id="892c4-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="892c4-215">SysMonthCal32</span></span>|<span data-ttu-id="892c4-216">Calendar</span><span class="sxs-lookup"><span data-stu-id="892c4-216">Calendar</span></span>|  
|<span data-ttu-id="892c4-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="892c4-217">MS_WINNOTE</span></span>|<span data-ttu-id="892c4-218">ToolTip</span><span class="sxs-lookup"><span data-stu-id="892c4-218">Tooltip</span></span>|  
|<span data-ttu-id="892c4-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="892c4-219">VBBubble</span></span>|<span data-ttu-id="892c4-220">Tooltip</span><span class="sxs-lookup"><span data-stu-id="892c4-220">Tooltip</span></span>|  
|<span data-ttu-id="892c4-221">ScrollBar (se usato come controllo autonomo)</span><span class="sxs-lookup"><span data-stu-id="892c4-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="892c4-222">Slider</span><span class="sxs-lookup"><span data-stu-id="892c4-222">Slider</span></span>|  
|<span data-ttu-id="892c4-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="892c4-223">SuperGrid</span></span>|<span data-ttu-id="892c4-224">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="892c4-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="892c4-225">Controlli per Windows Form</span><span class="sxs-lookup"><span data-stu-id="892c4-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="892c4-226">Controlli Windows Form sono esposti a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tramite provider lato client in UIAutomationClientsideProviders.</span><span class="sxs-lookup"><span data-stu-id="892c4-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="892c4-227">Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="892c4-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="892c4-228">In genere, i controlli Windows Form che sono wrapper gestiti per [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controlli comuni supportati da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="892c4-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="892c4-229">I controlli seguenti sono supportati.</span><span class="sxs-lookup"><span data-stu-id="892c4-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="892c4-230">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="892c4-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="892c4-231">Button</span><span class="sxs-lookup"><span data-stu-id="892c4-231">Button</span></span>|  
|<span data-ttu-id="892c4-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="892c4-232">CheckBox</span></span>|  
|<span data-ttu-id="892c4-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="892c4-233">CheckedListBox</span></span>|  
|<span data-ttu-id="892c4-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="892c4-234">ColorDialog</span></span>|  
|<span data-ttu-id="892c4-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="892c4-235">ComboBox</span></span>|  
|<span data-ttu-id="892c4-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="892c4-236">FolderBrowser</span></span>|  
|<span data-ttu-id="892c4-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="892c4-237">FontDialog</span></span>|  
|<span data-ttu-id="892c4-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="892c4-238">GroupBox</span></span>|  
|<span data-ttu-id="892c4-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="892c4-239">HscrollBar</span></span>|  
|<span data-ttu-id="892c4-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="892c4-240">ImageList</span></span>|  
|<span data-ttu-id="892c4-241">Label</span><span class="sxs-lookup"><span data-stu-id="892c4-241">Label</span></span>|  
|<span data-ttu-id="892c4-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="892c4-242">ListBox</span></span>|  
|<span data-ttu-id="892c4-243">ListView</span><span class="sxs-lookup"><span data-stu-id="892c4-243">ListView</span></span>|  
|<span data-ttu-id="892c4-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="892c4-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="892c4-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="892c4-245">MonthCalendar</span></span>|  
|<span data-ttu-id="892c4-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="892c4-246">NotifyIcon</span></span>|  
|<span data-ttu-id="892c4-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="892c4-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="892c4-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="892c4-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="892c4-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="892c4-249">PrintDialog</span></span>|  
|<span data-ttu-id="892c4-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="892c4-250">ProgressBar</span></span>|  
|<span data-ttu-id="892c4-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="892c4-251">RadioButton</span></span>|  
|<span data-ttu-id="892c4-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="892c4-252">RichTextBox</span></span>|  
|<span data-ttu-id="892c4-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="892c4-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="892c4-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="892c4-254">ScrollableControl</span></span>|  
|<span data-ttu-id="892c4-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="892c4-255">SoundPlayer</span></span>|  
|<span data-ttu-id="892c4-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="892c4-256">StatusBar</span></span>|  
|<span data-ttu-id="892c4-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="892c4-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="892c4-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="892c4-258">TextBox</span></span>|  
|<span data-ttu-id="892c4-259">Timer</span><span class="sxs-lookup"><span data-stu-id="892c4-259">Timer</span></span>|  
|<span data-ttu-id="892c4-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="892c4-260">Toolbar</span></span>|  
|<span data-ttu-id="892c4-261">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="892c4-261">ToolTip</span></span>|  
|<span data-ttu-id="892c4-262">Trackbar</span><span class="sxs-lookup"><span data-stu-id="892c4-262">TrackBar</span></span>|  
|<span data-ttu-id="892c4-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="892c4-263">TreeView</span></span>|  
|<span data-ttu-id="892c4-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="892c4-264">VscrollBar</span></span>|  
|<span data-ttu-id="892c4-265">WebBrowser</span><span class="sxs-lookup"><span data-stu-id="892c4-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="892c4-266">I seguenti controlli sono esposti a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] solo tramite il relativo supporto per [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span><span class="sxs-lookup"><span data-stu-id="892c4-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span></span> <span data-ttu-id="892c4-267">Alcune funzionalità potrebbero non essere disponibili.</span><span class="sxs-lookup"><span data-stu-id="892c4-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="892c4-268">Nome controllo</span><span class="sxs-lookup"><span data-stu-id="892c4-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="892c4-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="892c4-269">BindingSource</span></span>|  
|<span data-ttu-id="892c4-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="892c4-270">DataGrid</span></span>|  
|<span data-ttu-id="892c4-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="892c4-271">DataGridView</span></span>|  
|<span data-ttu-id="892c4-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="892c4-272">DataNavigator</span></span>|  
|<span data-ttu-id="892c4-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="892c4-273">DomainUpDown</span></span>|  
|<span data-ttu-id="892c4-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="892c4-274">ErrorProvider</span></span>|  
|<span data-ttu-id="892c4-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="892c4-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="892c4-276">Form</span><span class="sxs-lookup"><span data-stu-id="892c4-276">Form</span></span>|  
|<span data-ttu-id="892c4-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="892c4-277">LinkLabel</span></span>|  
|<span data-ttu-id="892c4-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="892c4-278">HelpProvider</span></span>|  
|<span data-ttu-id="892c4-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="892c4-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="892c4-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="892c4-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="892c4-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="892c4-281">NumericUpDown</span></span>|  
|<span data-ttu-id="892c4-282">Panel</span><span class="sxs-lookup"><span data-stu-id="892c4-282">Panel</span></span>|  
|<span data-ttu-id="892c4-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="892c4-283">PictureBox</span></span>|  
|<span data-ttu-id="892c4-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="892c4-284">PrintDocument</span></span>|  
|<span data-ttu-id="892c4-285">PrintPreviewControl</span><span class="sxs-lookup"><span data-stu-id="892c4-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="892c4-286">PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="892c4-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="892c4-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="892c4-287">PropertyGrid</span></span>|  
|<span data-ttu-id="892c4-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="892c4-288">UserControl</span></span>|  
|<span data-ttu-id="892c4-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="892c4-289">ToolStrip</span></span>|  
|<span data-ttu-id="892c4-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="892c4-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="892c4-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="892c4-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="892c4-292">Splitter</span><span class="sxs-lookup"><span data-stu-id="892c4-292">Splitter</span></span>|  
|<span data-ttu-id="892c4-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="892c4-293">RaftingContainer</span></span>|  
|<span data-ttu-id="892c4-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="892c4-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="892c4-295">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="892c4-295">See Also</span></span>  
 [<span data-ttu-id="892c4-296">Tipi di controllo per l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="892c4-296">UI Automation Control Types</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types.md)
