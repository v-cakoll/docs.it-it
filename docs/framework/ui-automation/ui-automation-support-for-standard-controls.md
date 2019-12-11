---
title: Supporto per automazione interfaccia utente dei controlli standard
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 314526c1164f70e6b261df1a6f11ddce2b5fa240
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960074"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="82977-102">Supporto per automazione interfaccia utente dei controlli standard</span><span class="sxs-lookup"><span data-stu-id="82977-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="82977-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="82977-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="82977-104">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere l'argomento sull' [API Automazione interfaccia utente di Windows](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="82977-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="82977-105">Questo argomento contiene informazioni sul supporto di [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] per i controlli standard in applicazioni sviluppate per i framework [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]e [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="82977-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="82977-106">Controlli WPF (Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="82977-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="82977-107">Tutti gli elementi di controllo [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] che forniscono informazioni o supporto per l'interazione dell'utente dispongono di supporto nativo completo per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82977-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="82977-108">Gli altri elementi, ad esempio i pannelli, non sono visibile per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82977-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="82977-109">Controlli Win32</span><span class="sxs-lookup"><span data-stu-id="82977-109">Win32 Controls</span></span>  
 <span data-ttu-id="82977-110">La maggior parte dei controlli [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] è esposta a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tramite provider lato client in UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="82977-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="82977-111">Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="82977-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="82977-112">Il supporto completo viene fornito solo per i controlli della versione 6 di *ComCtrl32. dll*.</span><span class="sxs-lookup"><span data-stu-id="82977-112">Full support is provided only for controls from version 6 of *ComCtrl32.dll*.</span></span>  
  
 <span data-ttu-id="82977-113">I controlli seguenti sono supportati.</span><span class="sxs-lookup"><span data-stu-id="82977-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="82977-114">Nome della classe</span><span class="sxs-lookup"><span data-stu-id="82977-114">Class name</span></span>|<span data-ttu-id="82977-115">Tipo di controllo</span><span class="sxs-lookup"><span data-stu-id="82977-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="82977-116">Button</span><span class="sxs-lookup"><span data-stu-id="82977-116">Button</span></span>|<span data-ttu-id="82977-117">Button</span><span class="sxs-lookup"><span data-stu-id="82977-117">Button</span></span>|  
|<span data-ttu-id="82977-118">Button</span><span class="sxs-lookup"><span data-stu-id="82977-118">Button</span></span>|<span data-ttu-id="82977-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="82977-119">RadioButton</span></span>|  
|<span data-ttu-id="82977-120">Button</span><span class="sxs-lookup"><span data-stu-id="82977-120">Button</span></span>|<span data-ttu-id="82977-121">Gruppo</span><span class="sxs-lookup"><span data-stu-id="82977-121">Group</span></span>|  
|<span data-ttu-id="82977-122">Button</span><span class="sxs-lookup"><span data-stu-id="82977-122">Button</span></span>|<span data-ttu-id="82977-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="82977-123">CheckBox</span></span>|  
|<span data-ttu-id="82977-124">Button</span><span class="sxs-lookup"><span data-stu-id="82977-124">Button</span></span>|<span data-ttu-id="82977-125">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="82977-125">Hyperlink</span></span>|  
|<span data-ttu-id="82977-126">Button</span><span class="sxs-lookup"><span data-stu-id="82977-126">Button</span></span>|<span data-ttu-id="82977-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="82977-127">SplitButton</span></span>|  
|<span data-ttu-id="82977-128">Button</span><span class="sxs-lookup"><span data-stu-id="82977-128">Button</span></span>|<span data-ttu-id="82977-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="82977-129">CheckBox</span></span>|  
|<span data-ttu-id="82977-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="82977-130">ComboBoxEx32</span></span>|<span data-ttu-id="82977-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="82977-131">ComboBox</span></span>|  
|<span data-ttu-id="82977-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="82977-132">ComboBox</span></span>|<span data-ttu-id="82977-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="82977-133">ComboBox</span></span>|  
|<span data-ttu-id="82977-134">Edit</span><span class="sxs-lookup"><span data-stu-id="82977-134">Edit</span></span>|<span data-ttu-id="82977-135">Document</span><span class="sxs-lookup"><span data-stu-id="82977-135">Document</span></span>|  
|<span data-ttu-id="82977-136">Edit</span><span class="sxs-lookup"><span data-stu-id="82977-136">Edit</span></span>|<span data-ttu-id="82977-137">Edit</span><span class="sxs-lookup"><span data-stu-id="82977-137">Edit</span></span>|  
|<span data-ttu-id="82977-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="82977-138">SysLink</span></span>|<span data-ttu-id="82977-139">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="82977-139">Hyperlink</span></span>|  
|<span data-ttu-id="82977-140">Static</span><span class="sxs-lookup"><span data-stu-id="82977-140">Static</span></span>|<span data-ttu-id="82977-141">Testo</span><span class="sxs-lookup"><span data-stu-id="82977-141">Text</span></span>|  
|<span data-ttu-id="82977-142">Static</span><span class="sxs-lookup"><span data-stu-id="82977-142">Static</span></span>|<span data-ttu-id="82977-143">Immagine</span><span class="sxs-lookup"><span data-stu-id="82977-143">Image</span></span>|  
|<span data-ttu-id="82977-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="82977-144">SysIPAddress32</span></span>|<span data-ttu-id="82977-145">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="82977-145">Custom</span></span>|  
|<span data-ttu-id="82977-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="82977-146">SysHeader32</span></span>|<span data-ttu-id="82977-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="82977-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="82977-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="82977-148">SysListView32</span></span>|<span data-ttu-id="82977-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="82977-149">DataGrid</span></span>|  
|<span data-ttu-id="82977-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="82977-150">SysListView32</span></span>|<span data-ttu-id="82977-151">Contiene un elenco di oggetti</span><span class="sxs-lookup"><span data-stu-id="82977-151">List</span></span>|  
|<span data-ttu-id="82977-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="82977-152">ListBox</span></span>|<span data-ttu-id="82977-153">Contiene un elenco di oggetti</span><span class="sxs-lookup"><span data-stu-id="82977-153">List</span></span>|  
|<span data-ttu-id="82977-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="82977-154">ListBox</span></span>|<span data-ttu-id="82977-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="82977-155">ListItem</span></span>|  
|<span data-ttu-id="82977-156">#32768</span><span class="sxs-lookup"><span data-stu-id="82977-156">#32768</span></span>|<span data-ttu-id="82977-157">Menu</span><span class="sxs-lookup"><span data-stu-id="82977-157">Menu</span></span>|  
|<span data-ttu-id="82977-158">#32768</span><span class="sxs-lookup"><span data-stu-id="82977-158">#32768</span></span>|<span data-ttu-id="82977-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="82977-159">MenuItem</span></span>|  
|<span data-ttu-id="82977-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="82977-160">msctls_progress32</span></span>|<span data-ttu-id="82977-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="82977-161">ProgressBar</span></span>|  
|<span data-ttu-id="82977-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="82977-162">RichEdit</span></span>|<span data-ttu-id="82977-163">Documento.</span><span class="sxs-lookup"><span data-stu-id="82977-163">Document.</span></span> <span data-ttu-id="82977-164">Vedere la nota.</span><span class="sxs-lookup"><span data-stu-id="82977-164">See note.</span></span>|  
|<span data-ttu-id="82977-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="82977-165">RichEdit20A</span></span>|<span data-ttu-id="82977-166">Document</span><span class="sxs-lookup"><span data-stu-id="82977-166">Document</span></span>|  
|<span data-ttu-id="82977-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="82977-167">RichEdit20W</span></span>|<span data-ttu-id="82977-168">Document</span><span class="sxs-lookup"><span data-stu-id="82977-168">Document</span></span>|  
|<span data-ttu-id="82977-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="82977-169">RichEdit50W</span></span>|<span data-ttu-id="82977-170">Document</span><span class="sxs-lookup"><span data-stu-id="82977-170">Document</span></span>|  
|<span data-ttu-id="82977-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="82977-171">ScrollBar</span></span>|<span data-ttu-id="82977-172">Slider</span><span class="sxs-lookup"><span data-stu-id="82977-172">Slider</span></span>|  
|<span data-ttu-id="82977-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="82977-173">msctls_trackbar32</span></span>|<span data-ttu-id="82977-174">Slider</span><span class="sxs-lookup"><span data-stu-id="82977-174">Slider</span></span>|  
|<span data-ttu-id="82977-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="82977-175">msctls_updown32</span></span>|<span data-ttu-id="82977-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="82977-176">Spinner</span></span>|  
|<span data-ttu-id="82977-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="82977-177">msctls_statusbar32</span></span>|<span data-ttu-id="82977-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="82977-178">StatusBar</span></span>|  
|<span data-ttu-id="82977-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="82977-179">SysTabControl32</span></span>|<span data-ttu-id="82977-180">Scheda</span><span class="sxs-lookup"><span data-stu-id="82977-180">Tab</span></span>|  
|<span data-ttu-id="82977-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="82977-181">SysTabControl32</span></span>|<span data-ttu-id="82977-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="82977-182">TabItem</span></span>|  
|<span data-ttu-id="82977-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="82977-183">ToolbarWindow32</span></span>|<span data-ttu-id="82977-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="82977-184">ToolBar</span></span>|  
|<span data-ttu-id="82977-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="82977-185">ToolbarWindow32</span></span>|<span data-ttu-id="82977-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="82977-186">MenuItem</span></span>|  
|<span data-ttu-id="82977-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="82977-187">ToolbarWindow32</span></span>|<span data-ttu-id="82977-188">Button</span><span class="sxs-lookup"><span data-stu-id="82977-188">Button</span></span>|  
|<span data-ttu-id="82977-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="82977-189">ToolbarWindow32</span></span>|<span data-ttu-id="82977-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="82977-190">CheckBox</span></span>|  
|<span data-ttu-id="82977-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="82977-191">ToolbarWindow32</span></span>|<span data-ttu-id="82977-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="82977-192">RadioButton</span></span>|  
|<span data-ttu-id="82977-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="82977-193">ToolbarWindow32</span></span>|<span data-ttu-id="82977-194">Separator</span><span class="sxs-lookup"><span data-stu-id="82977-194">Separator</span></span>|  
|<span data-ttu-id="82977-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="82977-195">tooltips_class32</span></span>|<span data-ttu-id="82977-196">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="82977-196">ToolTip</span></span>|  
|<span data-ttu-id="82977-197">#32774</span><span class="sxs-lookup"><span data-stu-id="82977-197">#32774</span></span>|<span data-ttu-id="82977-198">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="82977-198">ToolTip</span></span>|  
|<span data-ttu-id="82977-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="82977-199">ReBarWindow32</span></span>|<span data-ttu-id="82977-200">ToolBar</span><span class="sxs-lookup"><span data-stu-id="82977-200">Toolbar</span></span>|  
|<span data-ttu-id="82977-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="82977-201">SysTreeView32</span></span>|<span data-ttu-id="82977-202">Struttura ad albero</span><span class="sxs-lookup"><span data-stu-id="82977-202">Tree</span></span>|  
|<span data-ttu-id="82977-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="82977-203">SysTreeView32</span></span>|<span data-ttu-id="82977-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="82977-204">TreeItem</span></span>|  
  
 <span data-ttu-id="82977-205">**Nota** Il controllo RichEdit è supportato solo per le versioni fornite con Windows Vista (in RichEd20. dll versione 3,1 e successive e MsftEdit. dll versione 4,1 e successive).</span><span class="sxs-lookup"><span data-stu-id="82977-205">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="82977-206">I controlli seguenti non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="82977-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="82977-207">Nome della classe</span><span class="sxs-lookup"><span data-stu-id="82977-207">Class name</span></span>|<span data-ttu-id="82977-208">Tipo di controllo</span><span class="sxs-lookup"><span data-stu-id="82977-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="82977-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="82977-209">SysAnimate32</span></span>|<span data-ttu-id="82977-210">Immagine</span><span class="sxs-lookup"><span data-stu-id="82977-210">Image</span></span>|  
|<span data-ttu-id="82977-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="82977-211">SysPager</span></span>|<span data-ttu-id="82977-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="82977-212">Spinner</span></span>|  
|<span data-ttu-id="82977-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="82977-213">SysDateTimePick32</span></span>|<span data-ttu-id="82977-214">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="82977-214">Custom</span></span>|  
|<span data-ttu-id="82977-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="82977-215">SysMonthCal32</span></span>|<span data-ttu-id="82977-216">Calendar</span><span class="sxs-lookup"><span data-stu-id="82977-216">Calendar</span></span>|  
|<span data-ttu-id="82977-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="82977-217">MS_WINNOTE</span></span>|<span data-ttu-id="82977-218">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="82977-218">Tooltip</span></span>|  
|<span data-ttu-id="82977-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="82977-219">VBBubble</span></span>|<span data-ttu-id="82977-220">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="82977-220">Tooltip</span></span>|  
|<span data-ttu-id="82977-221">ScrollBar (se usato come controllo autonomo)</span><span class="sxs-lookup"><span data-stu-id="82977-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="82977-222">Slider</span><span class="sxs-lookup"><span data-stu-id="82977-222">Slider</span></span>|  
|<span data-ttu-id="82977-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="82977-223">SuperGrid</span></span>|<span data-ttu-id="82977-224">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="82977-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="82977-225">Controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="82977-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="82977-226">I controlli Windows Forms vengono esposti ai [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tramite provider lato client in UIAutomationClientsideProviders. dll.</span><span class="sxs-lookup"><span data-stu-id="82977-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="82977-227">Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="82977-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="82977-228">In genere, Windows Forms controlli che sono wrapper gestiti per [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controlli comuni sono supportati da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82977-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="82977-229">I controlli seguenti sono supportati.</span><span class="sxs-lookup"><span data-stu-id="82977-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="82977-230">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="82977-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="82977-231">Button</span><span class="sxs-lookup"><span data-stu-id="82977-231">Button</span></span>|  
|<span data-ttu-id="82977-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="82977-232">CheckBox</span></span>|  
|<span data-ttu-id="82977-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="82977-233">CheckedListBox</span></span>|  
|<span data-ttu-id="82977-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="82977-234">ColorDialog</span></span>|  
|<span data-ttu-id="82977-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="82977-235">ComboBox</span></span>|  
|<span data-ttu-id="82977-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="82977-236">FolderBrowser</span></span>|  
|<span data-ttu-id="82977-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="82977-237">FontDialog</span></span>|  
|<span data-ttu-id="82977-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="82977-238">GroupBox</span></span>|  
|<span data-ttu-id="82977-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="82977-239">HscrollBar</span></span>|  
|<span data-ttu-id="82977-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="82977-240">ImageList</span></span>|  
|<span data-ttu-id="82977-241">Label</span><span class="sxs-lookup"><span data-stu-id="82977-241">Label</span></span>|  
|<span data-ttu-id="82977-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="82977-242">ListBox</span></span>|  
|<span data-ttu-id="82977-243">ListView</span><span class="sxs-lookup"><span data-stu-id="82977-243">ListView</span></span>|  
|<span data-ttu-id="82977-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="82977-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="82977-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="82977-245">MonthCalendar</span></span>|  
|<span data-ttu-id="82977-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="82977-246">NotifyIcon</span></span>|  
|<span data-ttu-id="82977-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="82977-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="82977-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="82977-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="82977-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="82977-249">PrintDialog</span></span>|  
|<span data-ttu-id="82977-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="82977-250">ProgressBar</span></span>|  
|<span data-ttu-id="82977-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="82977-251">RadioButton</span></span>|  
|<span data-ttu-id="82977-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="82977-252">RichTextBox</span></span>|  
|<span data-ttu-id="82977-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="82977-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="82977-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="82977-254">ScrollableControl</span></span>|  
|<span data-ttu-id="82977-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="82977-255">SoundPlayer</span></span>|  
|<span data-ttu-id="82977-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="82977-256">StatusBar</span></span>|  
|<span data-ttu-id="82977-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="82977-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="82977-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="82977-258">TextBox</span></span>|  
|<span data-ttu-id="82977-259">Timer</span><span class="sxs-lookup"><span data-stu-id="82977-259">Timer</span></span>|  
|<span data-ttu-id="82977-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="82977-260">Toolbar</span></span>|  
|<span data-ttu-id="82977-261">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="82977-261">ToolTip</span></span>|  
|<span data-ttu-id="82977-262">Trackbar</span><span class="sxs-lookup"><span data-stu-id="82977-262">TrackBar</span></span>|  
|<span data-ttu-id="82977-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="82977-263">TreeView</span></span>|  
|<span data-ttu-id="82977-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="82977-264">VscrollBar</span></span>|  
|<span data-ttu-id="82977-265">WebBrowser</span><span class="sxs-lookup"><span data-stu-id="82977-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="82977-266">I controlli seguenti sono esposti a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] solo tramite il supporto per Microsoft Active Accessibility.</span><span class="sxs-lookup"><span data-stu-id="82977-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="82977-267">Alcune funzionalità potrebbero non essere disponibili.</span><span class="sxs-lookup"><span data-stu-id="82977-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="82977-268">Nome controllo</span><span class="sxs-lookup"><span data-stu-id="82977-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="82977-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="82977-269">BindingSource</span></span>|  
|<span data-ttu-id="82977-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="82977-270">DataGrid</span></span>|  
|<span data-ttu-id="82977-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="82977-271">DataGridView</span></span>|  
|<span data-ttu-id="82977-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="82977-272">DataNavigator</span></span>|  
|<span data-ttu-id="82977-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="82977-273">DomainUpDown</span></span>|  
|<span data-ttu-id="82977-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="82977-274">ErrorProvider</span></span>|  
|<span data-ttu-id="82977-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="82977-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="82977-276">Form</span><span class="sxs-lookup"><span data-stu-id="82977-276">Form</span></span>|  
|<span data-ttu-id="82977-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="82977-277">LinkLabel</span></span>|  
|<span data-ttu-id="82977-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="82977-278">HelpProvider</span></span>|  
|<span data-ttu-id="82977-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="82977-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="82977-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="82977-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="82977-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="82977-281">NumericUpDown</span></span>|  
|<span data-ttu-id="82977-282">Panel</span><span class="sxs-lookup"><span data-stu-id="82977-282">Panel</span></span>|  
|<span data-ttu-id="82977-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="82977-283">PictureBox</span></span>|  
|<span data-ttu-id="82977-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="82977-284">PrintDocument</span></span>|  
|<span data-ttu-id="82977-285">PrintPreviewControl</span><span class="sxs-lookup"><span data-stu-id="82977-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="82977-286">PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="82977-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="82977-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="82977-287">PropertyGrid</span></span>|  
|<span data-ttu-id="82977-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="82977-288">UserControl</span></span>|  
|<span data-ttu-id="82977-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="82977-289">ToolStrip</span></span>|  
|<span data-ttu-id="82977-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="82977-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="82977-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="82977-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="82977-292">Barra di divisione</span><span class="sxs-lookup"><span data-stu-id="82977-292">Splitter</span></span>|  
|<span data-ttu-id="82977-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="82977-293">RaftingContainer</span></span>|  
|<span data-ttu-id="82977-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="82977-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="82977-295">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82977-295">See also</span></span>

- [<span data-ttu-id="82977-296">Tipi di controllo per l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="82977-296">UI Automation Control Types</span></span>](ui-automation-control-types.md)
