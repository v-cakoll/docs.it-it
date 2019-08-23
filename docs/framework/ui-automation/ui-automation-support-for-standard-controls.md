---
title: Supporto per automazione interfaccia utente dei controlli standard
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: d83713a81e7675a68482890c2401f1a0a6803abc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914224"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="5bcdf-102">Supporto per automazione interfaccia utente dei controlli standard</span><span class="sxs-lookup"><span data-stu-id="5bcdf-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="5bcdf-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="5bcdf-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="5bcdf-104">Per informazioni aggiornate su, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]vedere [API di automazione di Windows: Automazione](https://go.microsoft.com/fwlink/?LinkID=156746)interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="5bcdf-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="5bcdf-105">Questo argomento contiene informazioni sul supporto di [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] per i controlli standard in applicazioni sviluppate per i framework [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]e [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5bcdf-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="5bcdf-106">Controlli WPF (Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="5bcdf-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="5bcdf-107">Tutti gli elementi di controllo [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] che forniscono informazioni o supporto per l'interazione dell'utente dispongono di supporto nativo completo per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5bcdf-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="5bcdf-108">Gli altri elementi, ad esempio i pannelli, non sono visibile per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5bcdf-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="5bcdf-109">Controlli Win32</span><span class="sxs-lookup"><span data-stu-id="5bcdf-109">Win32 Controls</span></span>  
 <span data-ttu-id="5bcdf-110">La maggior parte dei controlli [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] è esposta a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tramite provider lato client in UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="5bcdf-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="5bcdf-111">Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="5bcdf-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="5bcdf-112">Il supporto completo viene fornito solo per i controlli a partire dalla versione 6 di ComCtrl32.dll (disponibile con [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] e versioni successive).</span><span class="sxs-lookup"><span data-stu-id="5bcdf-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="5bcdf-113">I controlli seguenti sono supportati.</span><span class="sxs-lookup"><span data-stu-id="5bcdf-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="5bcdf-114">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="5bcdf-114">Class name</span></span>|<span data-ttu-id="5bcdf-115">Tipo di controllo</span><span class="sxs-lookup"><span data-stu-id="5bcdf-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="5bcdf-116">Button</span><span class="sxs-lookup"><span data-stu-id="5bcdf-116">Button</span></span>|<span data-ttu-id="5bcdf-117">Button</span><span class="sxs-lookup"><span data-stu-id="5bcdf-117">Button</span></span>|  
|<span data-ttu-id="5bcdf-118">Button</span><span class="sxs-lookup"><span data-stu-id="5bcdf-118">Button</span></span>|<span data-ttu-id="5bcdf-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="5bcdf-119">RadioButton</span></span>|  
|<span data-ttu-id="5bcdf-120">Button</span><span class="sxs-lookup"><span data-stu-id="5bcdf-120">Button</span></span>|<span data-ttu-id="5bcdf-121">Group</span><span class="sxs-lookup"><span data-stu-id="5bcdf-121">Group</span></span>|  
|<span data-ttu-id="5bcdf-122">Button</span><span class="sxs-lookup"><span data-stu-id="5bcdf-122">Button</span></span>|<span data-ttu-id="5bcdf-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="5bcdf-123">CheckBox</span></span>|  
|<span data-ttu-id="5bcdf-124">Button</span><span class="sxs-lookup"><span data-stu-id="5bcdf-124">Button</span></span>|<span data-ttu-id="5bcdf-125">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="5bcdf-125">Hyperlink</span></span>|  
|<span data-ttu-id="5bcdf-126">Button</span><span class="sxs-lookup"><span data-stu-id="5bcdf-126">Button</span></span>|<span data-ttu-id="5bcdf-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="5bcdf-127">SplitButton</span></span>|  
|<span data-ttu-id="5bcdf-128">Button</span><span class="sxs-lookup"><span data-stu-id="5bcdf-128">Button</span></span>|<span data-ttu-id="5bcdf-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="5bcdf-129">CheckBox</span></span>|  
|<span data-ttu-id="5bcdf-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="5bcdf-130">ComboBoxEx32</span></span>|<span data-ttu-id="5bcdf-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="5bcdf-131">ComboBox</span></span>|  
|<span data-ttu-id="5bcdf-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="5bcdf-132">ComboBox</span></span>|<span data-ttu-id="5bcdf-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="5bcdf-133">ComboBox</span></span>|  
|<span data-ttu-id="5bcdf-134">Edit</span><span class="sxs-lookup"><span data-stu-id="5bcdf-134">Edit</span></span>|<span data-ttu-id="5bcdf-135">Documento</span><span class="sxs-lookup"><span data-stu-id="5bcdf-135">Document</span></span>|  
|<span data-ttu-id="5bcdf-136">Edit</span><span class="sxs-lookup"><span data-stu-id="5bcdf-136">Edit</span></span>|<span data-ttu-id="5bcdf-137">Edit</span><span class="sxs-lookup"><span data-stu-id="5bcdf-137">Edit</span></span>|  
|<span data-ttu-id="5bcdf-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="5bcdf-138">SysLink</span></span>|<span data-ttu-id="5bcdf-139">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="5bcdf-139">Hyperlink</span></span>|  
|<span data-ttu-id="5bcdf-140">statico</span><span class="sxs-lookup"><span data-stu-id="5bcdf-140">Static</span></span>|<span data-ttu-id="5bcdf-141">Text</span><span class="sxs-lookup"><span data-stu-id="5bcdf-141">Text</span></span>|  
|<span data-ttu-id="5bcdf-142">statico</span><span class="sxs-lookup"><span data-stu-id="5bcdf-142">Static</span></span>|<span data-ttu-id="5bcdf-143">Image</span><span class="sxs-lookup"><span data-stu-id="5bcdf-143">Image</span></span>|  
|<span data-ttu-id="5bcdf-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="5bcdf-144">SysIPAddress32</span></span>|<span data-ttu-id="5bcdf-145">Custom</span><span class="sxs-lookup"><span data-stu-id="5bcdf-145">Custom</span></span>|  
|<span data-ttu-id="5bcdf-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="5bcdf-146">SysHeader32</span></span>|<span data-ttu-id="5bcdf-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="5bcdf-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="5bcdf-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="5bcdf-148">SysListView32</span></span>|<span data-ttu-id="5bcdf-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="5bcdf-149">DataGrid</span></span>|  
|<span data-ttu-id="5bcdf-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="5bcdf-150">SysListView32</span></span>|<span data-ttu-id="5bcdf-151">List</span><span class="sxs-lookup"><span data-stu-id="5bcdf-151">List</span></span>|  
|<span data-ttu-id="5bcdf-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="5bcdf-152">ListBox</span></span>|<span data-ttu-id="5bcdf-153">List</span><span class="sxs-lookup"><span data-stu-id="5bcdf-153">List</span></span>|  
|<span data-ttu-id="5bcdf-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="5bcdf-154">ListBox</span></span>|<span data-ttu-id="5bcdf-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="5bcdf-155">ListItem</span></span>|  
|<span data-ttu-id="5bcdf-156">#32768</span><span class="sxs-lookup"><span data-stu-id="5bcdf-156">#32768</span></span>|<span data-ttu-id="5bcdf-157">Menu</span><span class="sxs-lookup"><span data-stu-id="5bcdf-157">Menu</span></span>|  
|<span data-ttu-id="5bcdf-158">#32768</span><span class="sxs-lookup"><span data-stu-id="5bcdf-158">#32768</span></span>|<span data-ttu-id="5bcdf-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="5bcdf-159">MenuItem</span></span>|  
|<span data-ttu-id="5bcdf-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="5bcdf-160">msctls_progress32</span></span>|<span data-ttu-id="5bcdf-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="5bcdf-161">ProgressBar</span></span>|  
|<span data-ttu-id="5bcdf-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="5bcdf-162">RichEdit</span></span>|<span data-ttu-id="5bcdf-163">Document</span><span class="sxs-lookup"><span data-stu-id="5bcdf-163">Document.</span></span> <span data-ttu-id="5bcdf-164">Vedere la nota.</span><span class="sxs-lookup"><span data-stu-id="5bcdf-164">See note.</span></span>|  
|<span data-ttu-id="5bcdf-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="5bcdf-165">RichEdit20A</span></span>|<span data-ttu-id="5bcdf-166">Documento</span><span class="sxs-lookup"><span data-stu-id="5bcdf-166">Document</span></span>|  
|<span data-ttu-id="5bcdf-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="5bcdf-167">RichEdit20W</span></span>|<span data-ttu-id="5bcdf-168">Document</span><span class="sxs-lookup"><span data-stu-id="5bcdf-168">Document</span></span>|  
|<span data-ttu-id="5bcdf-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="5bcdf-169">RichEdit50W</span></span>|<span data-ttu-id="5bcdf-170">Documento</span><span class="sxs-lookup"><span data-stu-id="5bcdf-170">Document</span></span>|  
|<span data-ttu-id="5bcdf-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="5bcdf-171">ScrollBar</span></span>|<span data-ttu-id="5bcdf-172">Slider</span><span class="sxs-lookup"><span data-stu-id="5bcdf-172">Slider</span></span>|  
|<span data-ttu-id="5bcdf-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="5bcdf-173">msctls_trackbar32</span></span>|<span data-ttu-id="5bcdf-174">Slider</span><span class="sxs-lookup"><span data-stu-id="5bcdf-174">Slider</span></span>|  
|<span data-ttu-id="5bcdf-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="5bcdf-175">msctls_updown32</span></span>|<span data-ttu-id="5bcdf-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="5bcdf-176">Spinner</span></span>|  
|<span data-ttu-id="5bcdf-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="5bcdf-177">msctls_statusbar32</span></span>|<span data-ttu-id="5bcdf-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="5bcdf-178">StatusBar</span></span>|  
|<span data-ttu-id="5bcdf-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="5bcdf-179">SysTabControl32</span></span>|<span data-ttu-id="5bcdf-180">TAB</span><span class="sxs-lookup"><span data-stu-id="5bcdf-180">Tab</span></span>|  
|<span data-ttu-id="5bcdf-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="5bcdf-181">SysTabControl32</span></span>|<span data-ttu-id="5bcdf-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="5bcdf-182">TabItem</span></span>|  
|<span data-ttu-id="5bcdf-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5bcdf-183">ToolbarWindow32</span></span>|<span data-ttu-id="5bcdf-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="5bcdf-184">ToolBar</span></span>|  
|<span data-ttu-id="5bcdf-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5bcdf-185">ToolbarWindow32</span></span>|<span data-ttu-id="5bcdf-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="5bcdf-186">MenuItem</span></span>|  
|<span data-ttu-id="5bcdf-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5bcdf-187">ToolbarWindow32</span></span>|<span data-ttu-id="5bcdf-188">Button</span><span class="sxs-lookup"><span data-stu-id="5bcdf-188">Button</span></span>|  
|<span data-ttu-id="5bcdf-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5bcdf-189">ToolbarWindow32</span></span>|<span data-ttu-id="5bcdf-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="5bcdf-190">CheckBox</span></span>|  
|<span data-ttu-id="5bcdf-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5bcdf-191">ToolbarWindow32</span></span>|<span data-ttu-id="5bcdf-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="5bcdf-192">RadioButton</span></span>|  
|<span data-ttu-id="5bcdf-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5bcdf-193">ToolbarWindow32</span></span>|<span data-ttu-id="5bcdf-194">Separatore</span><span class="sxs-lookup"><span data-stu-id="5bcdf-194">Separator</span></span>|  
|<span data-ttu-id="5bcdf-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="5bcdf-195">tooltips_class32</span></span>|<span data-ttu-id="5bcdf-196">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="5bcdf-196">ToolTip</span></span>|  
|<span data-ttu-id="5bcdf-197">#32774</span><span class="sxs-lookup"><span data-stu-id="5bcdf-197">#32774</span></span>|<span data-ttu-id="5bcdf-198">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="5bcdf-198">ToolTip</span></span>|  
|<span data-ttu-id="5bcdf-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="5bcdf-199">ReBarWindow32</span></span>|<span data-ttu-id="5bcdf-200">ToolBar</span><span class="sxs-lookup"><span data-stu-id="5bcdf-200">Toolbar</span></span>|  
|<span data-ttu-id="5bcdf-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="5bcdf-201">SysTreeView32</span></span>|<span data-ttu-id="5bcdf-202">Struttura ad albero</span><span class="sxs-lookup"><span data-stu-id="5bcdf-202">Tree</span></span>|  
|<span data-ttu-id="5bcdf-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="5bcdf-203">SysTreeView32</span></span>|<span data-ttu-id="5bcdf-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="5bcdf-204">TreeItem</span></span>|  
  
 <span data-ttu-id="5bcdf-205">**Nota** Il controllo RichEdit è supportato solo per le versioni fornite con [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in Riched20.dll versione 3.1 e successive e MsftEdit.dll versione 4.1 e successive).</span><span class="sxs-lookup"><span data-stu-id="5bcdf-205">**Note** The RichEdit control is supported only for versions shipped with [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="5bcdf-206">I controlli seguenti non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="5bcdf-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="5bcdf-207">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="5bcdf-207">Class name</span></span>|<span data-ttu-id="5bcdf-208">Tipo di controllo</span><span class="sxs-lookup"><span data-stu-id="5bcdf-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="5bcdf-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="5bcdf-209">SysAnimate32</span></span>|<span data-ttu-id="5bcdf-210">Image</span><span class="sxs-lookup"><span data-stu-id="5bcdf-210">Image</span></span>|  
|<span data-ttu-id="5bcdf-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="5bcdf-211">SysPager</span></span>|<span data-ttu-id="5bcdf-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="5bcdf-212">Spinner</span></span>|  
|<span data-ttu-id="5bcdf-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="5bcdf-213">SysDateTimePick32</span></span>|<span data-ttu-id="5bcdf-214">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="5bcdf-214">Custom</span></span>|  
|<span data-ttu-id="5bcdf-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="5bcdf-215">SysMonthCal32</span></span>|<span data-ttu-id="5bcdf-216">Calendar</span><span class="sxs-lookup"><span data-stu-id="5bcdf-216">Calendar</span></span>|  
|<span data-ttu-id="5bcdf-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="5bcdf-217">MS_WINNOTE</span></span>|<span data-ttu-id="5bcdf-218">ToolTip</span><span class="sxs-lookup"><span data-stu-id="5bcdf-218">Tooltip</span></span>|  
|<span data-ttu-id="5bcdf-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="5bcdf-219">VBBubble</span></span>|<span data-ttu-id="5bcdf-220">ToolTip</span><span class="sxs-lookup"><span data-stu-id="5bcdf-220">Tooltip</span></span>|  
|<span data-ttu-id="5bcdf-221">ScrollBar (se usato come controllo autonomo)</span><span class="sxs-lookup"><span data-stu-id="5bcdf-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="5bcdf-222">Slider</span><span class="sxs-lookup"><span data-stu-id="5bcdf-222">Slider</span></span>|  
|<span data-ttu-id="5bcdf-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="5bcdf-223">SuperGrid</span></span>|<span data-ttu-id="5bcdf-224">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="5bcdf-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="5bcdf-225">Controlli per Windows Form</span><span class="sxs-lookup"><span data-stu-id="5bcdf-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="5bcdf-226">Windows Forms controlli sono esposti a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tramite provider lato client in UIAutomationClientsideProviders. dll.</span><span class="sxs-lookup"><span data-stu-id="5bcdf-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="5bcdf-227">Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="5bcdf-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="5bcdf-228">In genere, Windows Forms controlli che sono wrapper gestiti per [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] i controlli comuni sono supportati [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]da.</span><span class="sxs-lookup"><span data-stu-id="5bcdf-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="5bcdf-229">I controlli seguenti sono supportati.</span><span class="sxs-lookup"><span data-stu-id="5bcdf-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="5bcdf-230">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="5bcdf-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="5bcdf-231">Button</span><span class="sxs-lookup"><span data-stu-id="5bcdf-231">Button</span></span>|  
|<span data-ttu-id="5bcdf-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="5bcdf-232">CheckBox</span></span>|  
|<span data-ttu-id="5bcdf-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="5bcdf-233">CheckedListBox</span></span>|  
|<span data-ttu-id="5bcdf-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="5bcdf-234">ColorDialog</span></span>|  
|<span data-ttu-id="5bcdf-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="5bcdf-235">ComboBox</span></span>|  
|<span data-ttu-id="5bcdf-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="5bcdf-236">FolderBrowser</span></span>|  
|<span data-ttu-id="5bcdf-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="5bcdf-237">FontDialog</span></span>|  
|<span data-ttu-id="5bcdf-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="5bcdf-238">GroupBox</span></span>|  
|<span data-ttu-id="5bcdf-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="5bcdf-239">HscrollBar</span></span>|  
|<span data-ttu-id="5bcdf-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="5bcdf-240">ImageList</span></span>|  
|<span data-ttu-id="5bcdf-241">Label</span><span class="sxs-lookup"><span data-stu-id="5bcdf-241">Label</span></span>|  
|<span data-ttu-id="5bcdf-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="5bcdf-242">ListBox</span></span>|  
|<span data-ttu-id="5bcdf-243">ListView</span><span class="sxs-lookup"><span data-stu-id="5bcdf-243">ListView</span></span>|  
|<span data-ttu-id="5bcdf-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="5bcdf-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="5bcdf-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="5bcdf-245">MonthCalendar</span></span>|  
|<span data-ttu-id="5bcdf-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="5bcdf-246">NotifyIcon</span></span>|  
|<span data-ttu-id="5bcdf-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="5bcdf-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="5bcdf-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="5bcdf-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="5bcdf-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="5bcdf-249">PrintDialog</span></span>|  
|<span data-ttu-id="5bcdf-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="5bcdf-250">ProgressBar</span></span>|  
|<span data-ttu-id="5bcdf-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="5bcdf-251">RadioButton</span></span>|  
|<span data-ttu-id="5bcdf-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="5bcdf-252">RichTextBox</span></span>|  
|<span data-ttu-id="5bcdf-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="5bcdf-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="5bcdf-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="5bcdf-254">ScrollableControl</span></span>|  
|<span data-ttu-id="5bcdf-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="5bcdf-255">SoundPlayer</span></span>|  
|<span data-ttu-id="5bcdf-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="5bcdf-256">StatusBar</span></span>|  
|<span data-ttu-id="5bcdf-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="5bcdf-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="5bcdf-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="5bcdf-258">TextBox</span></span>|  
|<span data-ttu-id="5bcdf-259">Timer</span><span class="sxs-lookup"><span data-stu-id="5bcdf-259">Timer</span></span>|  
|<span data-ttu-id="5bcdf-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="5bcdf-260">Toolbar</span></span>|  
|<span data-ttu-id="5bcdf-261">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="5bcdf-261">ToolTip</span></span>|  
|<span data-ttu-id="5bcdf-262">Trackbar</span><span class="sxs-lookup"><span data-stu-id="5bcdf-262">TrackBar</span></span>|  
|<span data-ttu-id="5bcdf-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="5bcdf-263">TreeView</span></span>|  
|<span data-ttu-id="5bcdf-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="5bcdf-264">VscrollBar</span></span>|  
|<span data-ttu-id="5bcdf-265">WebBrowser</span><span class="sxs-lookup"><span data-stu-id="5bcdf-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="5bcdf-266">I controlli seguenti sono esposti a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] solo tramite il supporto di Microsoft Active Accessibility.</span><span class="sxs-lookup"><span data-stu-id="5bcdf-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="5bcdf-267">Alcune funzionalità potrebbero non essere disponibili.</span><span class="sxs-lookup"><span data-stu-id="5bcdf-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="5bcdf-268">Nome controllo</span><span class="sxs-lookup"><span data-stu-id="5bcdf-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="5bcdf-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="5bcdf-269">BindingSource</span></span>|  
|<span data-ttu-id="5bcdf-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="5bcdf-270">DataGrid</span></span>|  
|<span data-ttu-id="5bcdf-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="5bcdf-271">DataGridView</span></span>|  
|<span data-ttu-id="5bcdf-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="5bcdf-272">DataNavigator</span></span>|  
|<span data-ttu-id="5bcdf-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="5bcdf-273">DomainUpDown</span></span>|  
|<span data-ttu-id="5bcdf-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="5bcdf-274">ErrorProvider</span></span>|  
|<span data-ttu-id="5bcdf-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="5bcdf-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="5bcdf-276">Form</span><span class="sxs-lookup"><span data-stu-id="5bcdf-276">Form</span></span>|  
|<span data-ttu-id="5bcdf-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="5bcdf-277">LinkLabel</span></span>|  
|<span data-ttu-id="5bcdf-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="5bcdf-278">HelpProvider</span></span>|  
|<span data-ttu-id="5bcdf-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="5bcdf-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="5bcdf-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="5bcdf-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="5bcdf-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="5bcdf-281">NumericUpDown</span></span>|  
|<span data-ttu-id="5bcdf-282">Panel</span><span class="sxs-lookup"><span data-stu-id="5bcdf-282">Panel</span></span>|  
|<span data-ttu-id="5bcdf-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="5bcdf-283">PictureBox</span></span>|  
|<span data-ttu-id="5bcdf-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="5bcdf-284">PrintDocument</span></span>|  
|<span data-ttu-id="5bcdf-285">PrintPreviewControl</span><span class="sxs-lookup"><span data-stu-id="5bcdf-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="5bcdf-286">PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="5bcdf-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="5bcdf-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="5bcdf-287">PropertyGrid</span></span>|  
|<span data-ttu-id="5bcdf-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="5bcdf-288">UserControl</span></span>|  
|<span data-ttu-id="5bcdf-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="5bcdf-289">ToolStrip</span></span>|  
|<span data-ttu-id="5bcdf-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="5bcdf-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="5bcdf-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="5bcdf-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="5bcdf-292">Splitter</span><span class="sxs-lookup"><span data-stu-id="5bcdf-292">Splitter</span></span>|  
|<span data-ttu-id="5bcdf-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="5bcdf-293">RaftingContainer</span></span>|  
|<span data-ttu-id="5bcdf-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="5bcdf-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5bcdf-295">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5bcdf-295">See also</span></span>

- [<span data-ttu-id="5bcdf-296">Tipi di controllo per l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="5bcdf-296">UI Automation Control Types</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types.md)
