---
title: Supporto per automazione interfaccia utente dei controlli standard
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
caps.latest.revision: 11
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: af46a984f1b4c2577daee120752590ff18b9d1d8
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2018
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="8c05e-102">Supporto per automazione interfaccia utente dei controlli standard</span><span class="sxs-lookup"><span data-stu-id="8c05e-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
>  <span data-ttu-id="8c05e-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="8c05e-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="8c05e-104">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere l'argomento sull' [API Automazione interfaccia utente di Windows](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="8c05e-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="8c05e-105">Questo argomento contiene informazioni sul supporto di [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] per i controlli standard in applicazioni sviluppate per i framework [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]e [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8c05e-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="8c05e-106">Controlli WPF (Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="8c05e-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="8c05e-107">Tutti gli elementi di controllo [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] che forniscono informazioni o supporto per l'interazione dell'utente dispongono di supporto nativo completo per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c05e-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="8c05e-108">Gli altri elementi, ad esempio i pannelli, non sono visibile per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c05e-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="8c05e-109">Controlli Win32</span><span class="sxs-lookup"><span data-stu-id="8c05e-109">Win32 Controls</span></span>  
 <span data-ttu-id="8c05e-110">La maggior parte dei controlli [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] è esposta a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tramite provider lato client in UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="8c05e-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="8c05e-111">Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="8c05e-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="8c05e-112">Il supporto completo viene fornito solo per i controlli a partire dalla versione 6 di ComCtrl32.dll (disponibile con [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] e versioni successive).</span><span class="sxs-lookup"><span data-stu-id="8c05e-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="8c05e-113">I controlli seguenti sono supportati.</span><span class="sxs-lookup"><span data-stu-id="8c05e-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="8c05e-114">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="8c05e-114">Class name</span></span>|<span data-ttu-id="8c05e-115">Tipo di controllo</span><span class="sxs-lookup"><span data-stu-id="8c05e-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="8c05e-116">Button</span><span class="sxs-lookup"><span data-stu-id="8c05e-116">Button</span></span>|<span data-ttu-id="8c05e-117">Pulsante</span><span class="sxs-lookup"><span data-stu-id="8c05e-117">Button</span></span>|  
|<span data-ttu-id="8c05e-118">Button</span><span class="sxs-lookup"><span data-stu-id="8c05e-118">Button</span></span>|<span data-ttu-id="8c05e-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="8c05e-119">RadioButton</span></span>|  
|<span data-ttu-id="8c05e-120">Button</span><span class="sxs-lookup"><span data-stu-id="8c05e-120">Button</span></span>|<span data-ttu-id="8c05e-121">Group</span><span class="sxs-lookup"><span data-stu-id="8c05e-121">Group</span></span>|  
|<span data-ttu-id="8c05e-122">Button</span><span class="sxs-lookup"><span data-stu-id="8c05e-122">Button</span></span>|<span data-ttu-id="8c05e-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="8c05e-123">CheckBox</span></span>|  
|<span data-ttu-id="8c05e-124">Button</span><span class="sxs-lookup"><span data-stu-id="8c05e-124">Button</span></span>|<span data-ttu-id="8c05e-125">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="8c05e-125">Hyperlink</span></span>|  
|<span data-ttu-id="8c05e-126">Button</span><span class="sxs-lookup"><span data-stu-id="8c05e-126">Button</span></span>|<span data-ttu-id="8c05e-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="8c05e-127">SplitButton</span></span>|  
|<span data-ttu-id="8c05e-128">Button</span><span class="sxs-lookup"><span data-stu-id="8c05e-128">Button</span></span>|<span data-ttu-id="8c05e-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="8c05e-129">CheckBox</span></span>|  
|<span data-ttu-id="8c05e-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="8c05e-130">ComboBoxEx32</span></span>|<span data-ttu-id="8c05e-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="8c05e-131">ComboBox</span></span>|  
|<span data-ttu-id="8c05e-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="8c05e-132">ComboBox</span></span>|<span data-ttu-id="8c05e-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="8c05e-133">ComboBox</span></span>|  
|<span data-ttu-id="8c05e-134">Edit</span><span class="sxs-lookup"><span data-stu-id="8c05e-134">Edit</span></span>|<span data-ttu-id="8c05e-135">Document</span><span class="sxs-lookup"><span data-stu-id="8c05e-135">Document</span></span>|  
|<span data-ttu-id="8c05e-136">Edit</span><span class="sxs-lookup"><span data-stu-id="8c05e-136">Edit</span></span>|<span data-ttu-id="8c05e-137">Edit</span><span class="sxs-lookup"><span data-stu-id="8c05e-137">Edit</span></span>|  
|<span data-ttu-id="8c05e-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="8c05e-138">SysLink</span></span>|<span data-ttu-id="8c05e-139">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="8c05e-139">Hyperlink</span></span>|  
|<span data-ttu-id="8c05e-140">Static</span><span class="sxs-lookup"><span data-stu-id="8c05e-140">Static</span></span>|<span data-ttu-id="8c05e-141">Testo</span><span class="sxs-lookup"><span data-stu-id="8c05e-141">Text</span></span>|  
|<span data-ttu-id="8c05e-142">Static</span><span class="sxs-lookup"><span data-stu-id="8c05e-142">Static</span></span>|<span data-ttu-id="8c05e-143">Image</span><span class="sxs-lookup"><span data-stu-id="8c05e-143">Image</span></span>|  
|<span data-ttu-id="8c05e-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="8c05e-144">SysIPAddress32</span></span>|<span data-ttu-id="8c05e-145">Custom</span><span class="sxs-lookup"><span data-stu-id="8c05e-145">Custom</span></span>|  
|<span data-ttu-id="8c05e-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="8c05e-146">SysHeader32</span></span>|<span data-ttu-id="8c05e-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="8c05e-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="8c05e-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="8c05e-148">SysListView32</span></span>|<span data-ttu-id="8c05e-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="8c05e-149">DataGrid</span></span>|  
|<span data-ttu-id="8c05e-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="8c05e-150">SysListView32</span></span>|<span data-ttu-id="8c05e-151">List</span><span class="sxs-lookup"><span data-stu-id="8c05e-151">List</span></span>|  
|<span data-ttu-id="8c05e-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="8c05e-152">ListBox</span></span>|<span data-ttu-id="8c05e-153">List</span><span class="sxs-lookup"><span data-stu-id="8c05e-153">List</span></span>|  
|<span data-ttu-id="8c05e-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="8c05e-154">ListBox</span></span>|<span data-ttu-id="8c05e-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="8c05e-155">ListItem</span></span>|  
|<span data-ttu-id="8c05e-156">#32768</span><span class="sxs-lookup"><span data-stu-id="8c05e-156">#32768</span></span>|<span data-ttu-id="8c05e-157">Menu</span><span class="sxs-lookup"><span data-stu-id="8c05e-157">Menu</span></span>|  
|<span data-ttu-id="8c05e-158">#32768</span><span class="sxs-lookup"><span data-stu-id="8c05e-158">#32768</span></span>|<span data-ttu-id="8c05e-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="8c05e-159">MenuItem</span></span>|  
|<span data-ttu-id="8c05e-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="8c05e-160">msctls_progress32</span></span>|<span data-ttu-id="8c05e-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="8c05e-161">ProgressBar</span></span>|  
|<span data-ttu-id="8c05e-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="8c05e-162">RichEdit</span></span>|<span data-ttu-id="8c05e-163">Document</span><span class="sxs-lookup"><span data-stu-id="8c05e-163">Document.</span></span> <span data-ttu-id="8c05e-164">Vedere la nota.</span><span class="sxs-lookup"><span data-stu-id="8c05e-164">See note.</span></span>|  
|<span data-ttu-id="8c05e-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="8c05e-165">RichEdit20A</span></span>|<span data-ttu-id="8c05e-166">Document</span><span class="sxs-lookup"><span data-stu-id="8c05e-166">Document</span></span>|  
|<span data-ttu-id="8c05e-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="8c05e-167">RichEdit20W</span></span>|<span data-ttu-id="8c05e-168">Document</span><span class="sxs-lookup"><span data-stu-id="8c05e-168">Document</span></span>|  
|<span data-ttu-id="8c05e-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="8c05e-169">RichEdit50W</span></span>|<span data-ttu-id="8c05e-170">Document</span><span class="sxs-lookup"><span data-stu-id="8c05e-170">Document</span></span>|  
|<span data-ttu-id="8c05e-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="8c05e-171">ScrollBar</span></span>|<span data-ttu-id="8c05e-172">Slider</span><span class="sxs-lookup"><span data-stu-id="8c05e-172">Slider</span></span>|  
|<span data-ttu-id="8c05e-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="8c05e-173">msctls_trackbar32</span></span>|<span data-ttu-id="8c05e-174">Slider</span><span class="sxs-lookup"><span data-stu-id="8c05e-174">Slider</span></span>|  
|<span data-ttu-id="8c05e-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="8c05e-175">msctls_updown32</span></span>|<span data-ttu-id="8c05e-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="8c05e-176">Spinner</span></span>|  
|<span data-ttu-id="8c05e-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="8c05e-177">msctls_statusbar32</span></span>|<span data-ttu-id="8c05e-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="8c05e-178">StatusBar</span></span>|  
|<span data-ttu-id="8c05e-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="8c05e-179">SysTabControl32</span></span>|<span data-ttu-id="8c05e-180">Scheda</span><span class="sxs-lookup"><span data-stu-id="8c05e-180">Tab</span></span>|  
|<span data-ttu-id="8c05e-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="8c05e-181">SysTabControl32</span></span>|<span data-ttu-id="8c05e-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="8c05e-182">TabItem</span></span>|  
|<span data-ttu-id="8c05e-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="8c05e-183">ToolbarWindow32</span></span>|<span data-ttu-id="8c05e-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="8c05e-184">ToolBar</span></span>|  
|<span data-ttu-id="8c05e-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="8c05e-185">ToolbarWindow32</span></span>|<span data-ttu-id="8c05e-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="8c05e-186">MenuItem</span></span>|  
|<span data-ttu-id="8c05e-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="8c05e-187">ToolbarWindow32</span></span>|<span data-ttu-id="8c05e-188">Button</span><span class="sxs-lookup"><span data-stu-id="8c05e-188">Button</span></span>|  
|<span data-ttu-id="8c05e-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="8c05e-189">ToolbarWindow32</span></span>|<span data-ttu-id="8c05e-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="8c05e-190">CheckBox</span></span>|  
|<span data-ttu-id="8c05e-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="8c05e-191">ToolbarWindow32</span></span>|<span data-ttu-id="8c05e-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="8c05e-192">RadioButton</span></span>|  
|<span data-ttu-id="8c05e-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="8c05e-193">ToolbarWindow32</span></span>|<span data-ttu-id="8c05e-194">Separatore</span><span class="sxs-lookup"><span data-stu-id="8c05e-194">Separator</span></span>|  
|<span data-ttu-id="8c05e-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="8c05e-195">tooltips_class32</span></span>|<span data-ttu-id="8c05e-196">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="8c05e-196">ToolTip</span></span>|  
|<span data-ttu-id="8c05e-197">#32774</span><span class="sxs-lookup"><span data-stu-id="8c05e-197">#32774</span></span>|<span data-ttu-id="8c05e-198">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="8c05e-198">ToolTip</span></span>|  
|<span data-ttu-id="8c05e-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="8c05e-199">ReBarWindow32</span></span>|<span data-ttu-id="8c05e-200">ToolBar</span><span class="sxs-lookup"><span data-stu-id="8c05e-200">Toolbar</span></span>|  
|<span data-ttu-id="8c05e-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="8c05e-201">SysTreeView32</span></span>|<span data-ttu-id="8c05e-202">Tree</span><span class="sxs-lookup"><span data-stu-id="8c05e-202">Tree</span></span>|  
|<span data-ttu-id="8c05e-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="8c05e-203">SysTreeView32</span></span>|<span data-ttu-id="8c05e-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="8c05e-204">TreeItem</span></span>|  
  
 <span data-ttu-id="8c05e-205">**Nota** Il controllo RichEdit è supportato solo per le versioni fornite con [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in Riched20.dll versione 3.1 e successive e MsftEdit.dll versione 4.1 e successive).</span><span class="sxs-lookup"><span data-stu-id="8c05e-205">**Note** The RichEdit control is supported only for versions shipped with [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="8c05e-206">I controlli seguenti non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="8c05e-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="8c05e-207">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="8c05e-207">Class name</span></span>|<span data-ttu-id="8c05e-208">Tipo di controllo</span><span class="sxs-lookup"><span data-stu-id="8c05e-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="8c05e-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="8c05e-209">SysAnimate32</span></span>|<span data-ttu-id="8c05e-210">Image</span><span class="sxs-lookup"><span data-stu-id="8c05e-210">Image</span></span>|  
|<span data-ttu-id="8c05e-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="8c05e-211">SysPager</span></span>|<span data-ttu-id="8c05e-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="8c05e-212">Spinner</span></span>|  
|<span data-ttu-id="8c05e-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="8c05e-213">SysDateTimePick32</span></span>|<span data-ttu-id="8c05e-214">Custom (Personalizzati)</span><span class="sxs-lookup"><span data-stu-id="8c05e-214">Custom</span></span>|  
|<span data-ttu-id="8c05e-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="8c05e-215">SysMonthCal32</span></span>|<span data-ttu-id="8c05e-216">Calendar</span><span class="sxs-lookup"><span data-stu-id="8c05e-216">Calendar</span></span>|  
|<span data-ttu-id="8c05e-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="8c05e-217">MS_WINNOTE</span></span>|<span data-ttu-id="8c05e-218">ToolTip</span><span class="sxs-lookup"><span data-stu-id="8c05e-218">Tooltip</span></span>|  
|<span data-ttu-id="8c05e-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="8c05e-219">VBBubble</span></span>|<span data-ttu-id="8c05e-220">Tooltip</span><span class="sxs-lookup"><span data-stu-id="8c05e-220">Tooltip</span></span>|  
|<span data-ttu-id="8c05e-221">ScrollBar (se usato come controllo autonomo)</span><span class="sxs-lookup"><span data-stu-id="8c05e-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="8c05e-222">Slider</span><span class="sxs-lookup"><span data-stu-id="8c05e-222">Slider</span></span>|  
|<span data-ttu-id="8c05e-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="8c05e-223">SuperGrid</span></span>|<span data-ttu-id="8c05e-224">Custom (Personalizzati)</span><span class="sxs-lookup"><span data-stu-id="8c05e-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="8c05e-225">Controlli per Windows Form</span><span class="sxs-lookup"><span data-stu-id="8c05e-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="8c05e-226">Controlli Windows Form sono esposti a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tramite provider lato client in UIAutomationClientsideProviders.</span><span class="sxs-lookup"><span data-stu-id="8c05e-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="8c05e-227">Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="8c05e-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="8c05e-228">In genere, i controlli Windows Form che sono wrapper gestiti per [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controlli comuni supportati da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c05e-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="8c05e-229">I controlli seguenti sono supportati.</span><span class="sxs-lookup"><span data-stu-id="8c05e-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="8c05e-230">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="8c05e-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="8c05e-231">Button</span><span class="sxs-lookup"><span data-stu-id="8c05e-231">Button</span></span>|  
|<span data-ttu-id="8c05e-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="8c05e-232">CheckBox</span></span>|  
|<span data-ttu-id="8c05e-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="8c05e-233">CheckedListBox</span></span>|  
|<span data-ttu-id="8c05e-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="8c05e-234">ColorDialog</span></span>|  
|<span data-ttu-id="8c05e-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="8c05e-235">ComboBox</span></span>|  
|<span data-ttu-id="8c05e-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="8c05e-236">FolderBrowser</span></span>|  
|<span data-ttu-id="8c05e-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="8c05e-237">FontDialog</span></span>|  
|<span data-ttu-id="8c05e-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="8c05e-238">GroupBox</span></span>|  
|<span data-ttu-id="8c05e-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="8c05e-239">HscrollBar</span></span>|  
|<span data-ttu-id="8c05e-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="8c05e-240">ImageList</span></span>|  
|<span data-ttu-id="8c05e-241">Label</span><span class="sxs-lookup"><span data-stu-id="8c05e-241">Label</span></span>|  
|<span data-ttu-id="8c05e-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="8c05e-242">ListBox</span></span>|  
|<span data-ttu-id="8c05e-243">ListView</span><span class="sxs-lookup"><span data-stu-id="8c05e-243">ListView</span></span>|  
|<span data-ttu-id="8c05e-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="8c05e-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="8c05e-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="8c05e-245">MonthCalendar</span></span>|  
|<span data-ttu-id="8c05e-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="8c05e-246">NotifyIcon</span></span>|  
|<span data-ttu-id="8c05e-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="8c05e-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="8c05e-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="8c05e-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="8c05e-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="8c05e-249">PrintDialog</span></span>|  
|<span data-ttu-id="8c05e-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="8c05e-250">ProgressBar</span></span>|  
|<span data-ttu-id="8c05e-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="8c05e-251">RadioButton</span></span>|  
|<span data-ttu-id="8c05e-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="8c05e-252">RichTextBox</span></span>|  
|<span data-ttu-id="8c05e-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="8c05e-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="8c05e-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="8c05e-254">ScrollableControl</span></span>|  
|<span data-ttu-id="8c05e-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="8c05e-255">SoundPlayer</span></span>|  
|<span data-ttu-id="8c05e-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="8c05e-256">StatusBar</span></span>|  
|<span data-ttu-id="8c05e-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="8c05e-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="8c05e-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="8c05e-258">TextBox</span></span>|  
|<span data-ttu-id="8c05e-259">Timer</span><span class="sxs-lookup"><span data-stu-id="8c05e-259">Timer</span></span>|  
|<span data-ttu-id="8c05e-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="8c05e-260">Toolbar</span></span>|  
|<span data-ttu-id="8c05e-261">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="8c05e-261">ToolTip</span></span>|  
|<span data-ttu-id="8c05e-262">Trackbar</span><span class="sxs-lookup"><span data-stu-id="8c05e-262">TrackBar</span></span>|  
|<span data-ttu-id="8c05e-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="8c05e-263">TreeView</span></span>|  
|<span data-ttu-id="8c05e-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="8c05e-264">VscrollBar</span></span>|  
|<span data-ttu-id="8c05e-265">WebBrowser</span><span class="sxs-lookup"><span data-stu-id="8c05e-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="8c05e-266">I seguenti controlli sono esposti a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] solo tramite il relativo supporto per [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c05e-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span></span> <span data-ttu-id="8c05e-267">Alcune funzionalità potrebbero non essere disponibili.</span><span class="sxs-lookup"><span data-stu-id="8c05e-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="8c05e-268">Nome controllo</span><span class="sxs-lookup"><span data-stu-id="8c05e-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="8c05e-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="8c05e-269">BindingSource</span></span>|  
|<span data-ttu-id="8c05e-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="8c05e-270">DataGrid</span></span>|  
|<span data-ttu-id="8c05e-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="8c05e-271">DataGridView</span></span>|  
|<span data-ttu-id="8c05e-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="8c05e-272">DataNavigator</span></span>|  
|<span data-ttu-id="8c05e-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="8c05e-273">DomainUpDown</span></span>|  
|<span data-ttu-id="8c05e-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="8c05e-274">ErrorProvider</span></span>|  
|<span data-ttu-id="8c05e-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="8c05e-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="8c05e-276">Form</span><span class="sxs-lookup"><span data-stu-id="8c05e-276">Form</span></span>|  
|<span data-ttu-id="8c05e-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="8c05e-277">LinkLabel</span></span>|  
|<span data-ttu-id="8c05e-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="8c05e-278">HelpProvider</span></span>|  
|<span data-ttu-id="8c05e-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="8c05e-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="8c05e-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="8c05e-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="8c05e-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="8c05e-281">NumericUpDown</span></span>|  
|<span data-ttu-id="8c05e-282">Panel</span><span class="sxs-lookup"><span data-stu-id="8c05e-282">Panel</span></span>|  
|<span data-ttu-id="8c05e-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="8c05e-283">PictureBox</span></span>|  
|<span data-ttu-id="8c05e-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="8c05e-284">PrintDocument</span></span>|  
|<span data-ttu-id="8c05e-285">PrintPreviewControl</span><span class="sxs-lookup"><span data-stu-id="8c05e-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="8c05e-286">PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="8c05e-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="8c05e-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="8c05e-287">PropertyGrid</span></span>|  
|<span data-ttu-id="8c05e-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="8c05e-288">UserControl</span></span>|  
|<span data-ttu-id="8c05e-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="8c05e-289">ToolStrip</span></span>|  
|<span data-ttu-id="8c05e-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="8c05e-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="8c05e-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="8c05e-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="8c05e-292">Splitter</span><span class="sxs-lookup"><span data-stu-id="8c05e-292">Splitter</span></span>|  
|<span data-ttu-id="8c05e-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="8c05e-293">RaftingContainer</span></span>|  
|<span data-ttu-id="8c05e-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="8c05e-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8c05e-295">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c05e-295">See Also</span></span>  
 [<span data-ttu-id="8c05e-296">Tipi di controllo per l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="8c05e-296">UI Automation Control Types</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types.md)
