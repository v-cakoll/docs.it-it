---
title: Supporto per automazione interfaccia utente dei controlli standard
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 49277073706444fd611ae41e762442388ac50b71
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789612"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="aeb90-102">Supporto per automazione interfaccia utente dei controlli standard</span><span class="sxs-lookup"><span data-stu-id="aeb90-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="aeb90-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="aeb90-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="aeb90-104">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="aeb90-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="aeb90-105">Questo argomento contiene informazioni sul supporto [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] per i controlli standard in applicazioni sviluppate per i Framework [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32 e Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="aeb90-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32, and Windows Forms frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="aeb90-106">Controlli WPF (Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="aeb90-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="aeb90-107">Tutti gli elementi di controllo [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] che forniscono informazioni o supporto per l'interazione dell'utente dispongono di supporto nativo completo per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aeb90-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="aeb90-108">Gli altri elementi, ad esempio i pannelli, non sono visibile per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aeb90-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="aeb90-109">Controlli Win32</span><span class="sxs-lookup"><span data-stu-id="aeb90-109">Win32 Controls</span></span>  
 <span data-ttu-id="aeb90-110">La maggior parte dei controlli Win32 viene esposta a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tramite provider lato client in UIAutomationClientsideProviders. dll.</span><span class="sxs-lookup"><span data-stu-id="aeb90-110">Most Win32 controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="aeb90-111">Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="aeb90-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="aeb90-112">Il supporto completo viene fornito solo per i controlli della versione 6 di *ComCtrl32. dll*.</span><span class="sxs-lookup"><span data-stu-id="aeb90-112">Full support is provided only for controls from version 6 of *ComCtrl32.dll*.</span></span>  
  
 <span data-ttu-id="aeb90-113">I controlli seguenti sono supportati.</span><span class="sxs-lookup"><span data-stu-id="aeb90-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="aeb90-114">Nome della classe</span><span class="sxs-lookup"><span data-stu-id="aeb90-114">Class name</span></span>|<span data-ttu-id="aeb90-115">Tipo di controllo</span><span class="sxs-lookup"><span data-stu-id="aeb90-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="aeb90-116">Button</span><span class="sxs-lookup"><span data-stu-id="aeb90-116">Button</span></span>|<span data-ttu-id="aeb90-117">Button</span><span class="sxs-lookup"><span data-stu-id="aeb90-117">Button</span></span>|  
|<span data-ttu-id="aeb90-118">Button</span><span class="sxs-lookup"><span data-stu-id="aeb90-118">Button</span></span>|<span data-ttu-id="aeb90-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="aeb90-119">RadioButton</span></span>|  
|<span data-ttu-id="aeb90-120">Button</span><span class="sxs-lookup"><span data-stu-id="aeb90-120">Button</span></span>|<span data-ttu-id="aeb90-121">Gruppo</span><span class="sxs-lookup"><span data-stu-id="aeb90-121">Group</span></span>|  
|<span data-ttu-id="aeb90-122">Button</span><span class="sxs-lookup"><span data-stu-id="aeb90-122">Button</span></span>|<span data-ttu-id="aeb90-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="aeb90-123">CheckBox</span></span>|  
|<span data-ttu-id="aeb90-124">Button</span><span class="sxs-lookup"><span data-stu-id="aeb90-124">Button</span></span>|<span data-ttu-id="aeb90-125">Collegamento ipertestuale</span><span class="sxs-lookup"><span data-stu-id="aeb90-125">Hyperlink</span></span>|  
|<span data-ttu-id="aeb90-126">Button</span><span class="sxs-lookup"><span data-stu-id="aeb90-126">Button</span></span>|<span data-ttu-id="aeb90-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="aeb90-127">SplitButton</span></span>|  
|<span data-ttu-id="aeb90-128">Button</span><span class="sxs-lookup"><span data-stu-id="aeb90-128">Button</span></span>|<span data-ttu-id="aeb90-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="aeb90-129">CheckBox</span></span>|  
|<span data-ttu-id="aeb90-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="aeb90-130">ComboBoxEx32</span></span>|<span data-ttu-id="aeb90-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="aeb90-131">ComboBox</span></span>|  
|<span data-ttu-id="aeb90-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="aeb90-132">ComboBox</span></span>|<span data-ttu-id="aeb90-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="aeb90-133">ComboBox</span></span>|  
|<span data-ttu-id="aeb90-134">Edit</span><span class="sxs-lookup"><span data-stu-id="aeb90-134">Edit</span></span>|<span data-ttu-id="aeb90-135">Documento</span><span class="sxs-lookup"><span data-stu-id="aeb90-135">Document</span></span>|  
|<span data-ttu-id="aeb90-136">Edit</span><span class="sxs-lookup"><span data-stu-id="aeb90-136">Edit</span></span>|<span data-ttu-id="aeb90-137">Edit</span><span class="sxs-lookup"><span data-stu-id="aeb90-137">Edit</span></span>|  
|<span data-ttu-id="aeb90-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="aeb90-138">SysLink</span></span>|<span data-ttu-id="aeb90-139">Collegamento ipertestuale</span><span class="sxs-lookup"><span data-stu-id="aeb90-139">Hyperlink</span></span>|  
|<span data-ttu-id="aeb90-140">Static</span><span class="sxs-lookup"><span data-stu-id="aeb90-140">Static</span></span>|<span data-ttu-id="aeb90-141">Testo</span><span class="sxs-lookup"><span data-stu-id="aeb90-141">Text</span></span>|  
|<span data-ttu-id="aeb90-142">Static</span><span class="sxs-lookup"><span data-stu-id="aeb90-142">Static</span></span>|<span data-ttu-id="aeb90-143">Immagine</span><span class="sxs-lookup"><span data-stu-id="aeb90-143">Image</span></span>|  
|<span data-ttu-id="aeb90-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="aeb90-144">SysIPAddress32</span></span>|<span data-ttu-id="aeb90-145">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="aeb90-145">Custom</span></span>|  
|<span data-ttu-id="aeb90-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="aeb90-146">SysHeader32</span></span>|<span data-ttu-id="aeb90-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="aeb90-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="aeb90-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="aeb90-148">SysListView32</span></span>|<span data-ttu-id="aeb90-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="aeb90-149">DataGrid</span></span>|  
|<span data-ttu-id="aeb90-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="aeb90-150">SysListView32</span></span>|<span data-ttu-id="aeb90-151">Contiene un elenco di oggetti</span><span class="sxs-lookup"><span data-stu-id="aeb90-151">List</span></span>|  
|<span data-ttu-id="aeb90-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="aeb90-152">ListBox</span></span>|<span data-ttu-id="aeb90-153">Contiene un elenco di oggetti</span><span class="sxs-lookup"><span data-stu-id="aeb90-153">List</span></span>|  
|<span data-ttu-id="aeb90-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="aeb90-154">ListBox</span></span>|<span data-ttu-id="aeb90-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="aeb90-155">ListItem</span></span>|  
|<span data-ttu-id="aeb90-156">#32768</span><span class="sxs-lookup"><span data-stu-id="aeb90-156">#32768</span></span>|<span data-ttu-id="aeb90-157">Menu</span><span class="sxs-lookup"><span data-stu-id="aeb90-157">Menu</span></span>|  
|<span data-ttu-id="aeb90-158">#32768</span><span class="sxs-lookup"><span data-stu-id="aeb90-158">#32768</span></span>|<span data-ttu-id="aeb90-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="aeb90-159">MenuItem</span></span>|  
|<span data-ttu-id="aeb90-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="aeb90-160">msctls_progress32</span></span>|<span data-ttu-id="aeb90-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="aeb90-161">ProgressBar</span></span>|  
|<span data-ttu-id="aeb90-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="aeb90-162">RichEdit</span></span>|<span data-ttu-id="aeb90-163">Document</span><span class="sxs-lookup"><span data-stu-id="aeb90-163">Document.</span></span> <span data-ttu-id="aeb90-164">Vedere la nota.</span><span class="sxs-lookup"><span data-stu-id="aeb90-164">See note.</span></span>|  
|<span data-ttu-id="aeb90-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="aeb90-165">RichEdit20A</span></span>|<span data-ttu-id="aeb90-166">Documento</span><span class="sxs-lookup"><span data-stu-id="aeb90-166">Document</span></span>|  
|<span data-ttu-id="aeb90-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="aeb90-167">RichEdit20W</span></span>|<span data-ttu-id="aeb90-168">Documento</span><span class="sxs-lookup"><span data-stu-id="aeb90-168">Document</span></span>|  
|<span data-ttu-id="aeb90-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="aeb90-169">RichEdit50W</span></span>|<span data-ttu-id="aeb90-170">Documento</span><span class="sxs-lookup"><span data-stu-id="aeb90-170">Document</span></span>|  
|<span data-ttu-id="aeb90-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="aeb90-171">ScrollBar</span></span>|<span data-ttu-id="aeb90-172">Slider</span><span class="sxs-lookup"><span data-stu-id="aeb90-172">Slider</span></span>|  
|<span data-ttu-id="aeb90-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="aeb90-173">msctls_trackbar32</span></span>|<span data-ttu-id="aeb90-174">Slider</span><span class="sxs-lookup"><span data-stu-id="aeb90-174">Slider</span></span>|  
|<span data-ttu-id="aeb90-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="aeb90-175">msctls_updown32</span></span>|<span data-ttu-id="aeb90-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="aeb90-176">Spinner</span></span>|  
|<span data-ttu-id="aeb90-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="aeb90-177">msctls_statusbar32</span></span>|<span data-ttu-id="aeb90-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="aeb90-178">StatusBar</span></span>|  
|<span data-ttu-id="aeb90-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="aeb90-179">SysTabControl32</span></span>|<span data-ttu-id="aeb90-180">Tab</span><span class="sxs-lookup"><span data-stu-id="aeb90-180">Tab</span></span>|  
|<span data-ttu-id="aeb90-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="aeb90-181">SysTabControl32</span></span>|<span data-ttu-id="aeb90-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="aeb90-182">TabItem</span></span>|  
|<span data-ttu-id="aeb90-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="aeb90-183">ToolbarWindow32</span></span>|<span data-ttu-id="aeb90-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="aeb90-184">ToolBar</span></span>|  
|<span data-ttu-id="aeb90-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="aeb90-185">ToolbarWindow32</span></span>|<span data-ttu-id="aeb90-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="aeb90-186">MenuItem</span></span>|  
|<span data-ttu-id="aeb90-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="aeb90-187">ToolbarWindow32</span></span>|<span data-ttu-id="aeb90-188">Button</span><span class="sxs-lookup"><span data-stu-id="aeb90-188">Button</span></span>|  
|<span data-ttu-id="aeb90-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="aeb90-189">ToolbarWindow32</span></span>|<span data-ttu-id="aeb90-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="aeb90-190">CheckBox</span></span>|  
|<span data-ttu-id="aeb90-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="aeb90-191">ToolbarWindow32</span></span>|<span data-ttu-id="aeb90-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="aeb90-192">RadioButton</span></span>|  
|<span data-ttu-id="aeb90-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="aeb90-193">ToolbarWindow32</span></span>|<span data-ttu-id="aeb90-194">Separator</span><span class="sxs-lookup"><span data-stu-id="aeb90-194">Separator</span></span>|  
|<span data-ttu-id="aeb90-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="aeb90-195">tooltips_class32</span></span>|<span data-ttu-id="aeb90-196">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="aeb90-196">ToolTip</span></span>|  
|<span data-ttu-id="aeb90-197">#32774</span><span class="sxs-lookup"><span data-stu-id="aeb90-197">#32774</span></span>|<span data-ttu-id="aeb90-198">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="aeb90-198">ToolTip</span></span>|  
|<span data-ttu-id="aeb90-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="aeb90-199">ReBarWindow32</span></span>|<span data-ttu-id="aeb90-200">ToolBar</span><span class="sxs-lookup"><span data-stu-id="aeb90-200">Toolbar</span></span>|  
|<span data-ttu-id="aeb90-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="aeb90-201">SysTreeView32</span></span>|<span data-ttu-id="aeb90-202">Tree</span><span class="sxs-lookup"><span data-stu-id="aeb90-202">Tree</span></span>|  
|<span data-ttu-id="aeb90-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="aeb90-203">SysTreeView32</span></span>|<span data-ttu-id="aeb90-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="aeb90-204">TreeItem</span></span>|  
  
 <span data-ttu-id="aeb90-205">**Nota** Il controllo RichEdit è supportato solo per le versioni fornite con Windows Vista (in RichEd20. dll versione 3,1 e successive e MsftEdit. dll versione 4,1 e successive).</span><span class="sxs-lookup"><span data-stu-id="aeb90-205">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="aeb90-206">I controlli seguenti non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="aeb90-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="aeb90-207">Nome della classe</span><span class="sxs-lookup"><span data-stu-id="aeb90-207">Class name</span></span>|<span data-ttu-id="aeb90-208">Tipo di controllo</span><span class="sxs-lookup"><span data-stu-id="aeb90-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="aeb90-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="aeb90-209">SysAnimate32</span></span>|<span data-ttu-id="aeb90-210">Immagine</span><span class="sxs-lookup"><span data-stu-id="aeb90-210">Image</span></span>|  
|<span data-ttu-id="aeb90-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="aeb90-211">SysPager</span></span>|<span data-ttu-id="aeb90-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="aeb90-212">Spinner</span></span>|  
|<span data-ttu-id="aeb90-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="aeb90-213">SysDateTimePick32</span></span>|<span data-ttu-id="aeb90-214">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="aeb90-214">Custom</span></span>|  
|<span data-ttu-id="aeb90-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="aeb90-215">SysMonthCal32</span></span>|<span data-ttu-id="aeb90-216">Calendar</span><span class="sxs-lookup"><span data-stu-id="aeb90-216">Calendar</span></span>|  
|<span data-ttu-id="aeb90-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="aeb90-217">MS_WINNOTE</span></span>|<span data-ttu-id="aeb90-218">ToolTip</span><span class="sxs-lookup"><span data-stu-id="aeb90-218">Tooltip</span></span>|  
|<span data-ttu-id="aeb90-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="aeb90-219">VBBubble</span></span>|<span data-ttu-id="aeb90-220">ToolTip</span><span class="sxs-lookup"><span data-stu-id="aeb90-220">Tooltip</span></span>|  
|<span data-ttu-id="aeb90-221">ScrollBar (se usato come controllo autonomo)</span><span class="sxs-lookup"><span data-stu-id="aeb90-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="aeb90-222">Slider</span><span class="sxs-lookup"><span data-stu-id="aeb90-222">Slider</span></span>|  
|<span data-ttu-id="aeb90-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="aeb90-223">SuperGrid</span></span>|<span data-ttu-id="aeb90-224">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="aeb90-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="aeb90-225">Controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="aeb90-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="aeb90-226">I controlli Windows Forms vengono esposti ai [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tramite provider lato client in UIAutomationClientsideProviders. dll.</span><span class="sxs-lookup"><span data-stu-id="aeb90-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="aeb90-227">Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="aeb90-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="aeb90-228">In genere, Windows Forms controlli che sono wrapper gestiti per i controlli comuni Win32 sono supportati da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aeb90-228">Typically, Windows Forms controls that are managed wrappers for Win32 common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="aeb90-229">I controlli seguenti sono supportati.</span><span class="sxs-lookup"><span data-stu-id="aeb90-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="aeb90-230">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="aeb90-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="aeb90-231">Button</span><span class="sxs-lookup"><span data-stu-id="aeb90-231">Button</span></span>|  
|<span data-ttu-id="aeb90-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="aeb90-232">CheckBox</span></span>|  
|<span data-ttu-id="aeb90-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="aeb90-233">CheckedListBox</span></span>|  
|<span data-ttu-id="aeb90-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="aeb90-234">ColorDialog</span></span>|  
|<span data-ttu-id="aeb90-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="aeb90-235">ComboBox</span></span>|  
|<span data-ttu-id="aeb90-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="aeb90-236">FolderBrowser</span></span>|  
|<span data-ttu-id="aeb90-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="aeb90-237">FontDialog</span></span>|  
|<span data-ttu-id="aeb90-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="aeb90-238">GroupBox</span></span>|  
|<span data-ttu-id="aeb90-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="aeb90-239">HscrollBar</span></span>|  
|<span data-ttu-id="aeb90-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="aeb90-240">ImageList</span></span>|  
|<span data-ttu-id="aeb90-241">Label</span><span class="sxs-lookup"><span data-stu-id="aeb90-241">Label</span></span>|  
|<span data-ttu-id="aeb90-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="aeb90-242">ListBox</span></span>|  
|<span data-ttu-id="aeb90-243">ListView</span><span class="sxs-lookup"><span data-stu-id="aeb90-243">ListView</span></span>|  
|<span data-ttu-id="aeb90-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="aeb90-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="aeb90-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="aeb90-245">MonthCalendar</span></span>|  
|<span data-ttu-id="aeb90-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="aeb90-246">NotifyIcon</span></span>|  
|<span data-ttu-id="aeb90-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="aeb90-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="aeb90-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="aeb90-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="aeb90-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="aeb90-249">PrintDialog</span></span>|  
|<span data-ttu-id="aeb90-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="aeb90-250">ProgressBar</span></span>|  
|<span data-ttu-id="aeb90-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="aeb90-251">RadioButton</span></span>|  
|<span data-ttu-id="aeb90-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="aeb90-252">RichTextBox</span></span>|  
|<span data-ttu-id="aeb90-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="aeb90-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="aeb90-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="aeb90-254">ScrollableControl</span></span>|  
|<span data-ttu-id="aeb90-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="aeb90-255">SoundPlayer</span></span>|  
|<span data-ttu-id="aeb90-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="aeb90-256">StatusBar</span></span>|  
|<span data-ttu-id="aeb90-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="aeb90-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="aeb90-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="aeb90-258">TextBox</span></span>|  
|<span data-ttu-id="aeb90-259">Timer</span><span class="sxs-lookup"><span data-stu-id="aeb90-259">Timer</span></span>|  
|<span data-ttu-id="aeb90-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="aeb90-260">Toolbar</span></span>|  
|<span data-ttu-id="aeb90-261">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="aeb90-261">ToolTip</span></span>|  
|<span data-ttu-id="aeb90-262">Trackbar</span><span class="sxs-lookup"><span data-stu-id="aeb90-262">TrackBar</span></span>|  
|<span data-ttu-id="aeb90-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="aeb90-263">TreeView</span></span>|  
|<span data-ttu-id="aeb90-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="aeb90-264">VscrollBar</span></span>|  
|<span data-ttu-id="aeb90-265">WebBrowser</span><span class="sxs-lookup"><span data-stu-id="aeb90-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="aeb90-266">I controlli seguenti sono esposti a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] solo tramite il supporto per Microsoft Active Accessibility.</span><span class="sxs-lookup"><span data-stu-id="aeb90-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="aeb90-267">Alcune funzionalità potrebbero non essere disponibili.</span><span class="sxs-lookup"><span data-stu-id="aeb90-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="aeb90-268">Nome controllo</span><span class="sxs-lookup"><span data-stu-id="aeb90-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="aeb90-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="aeb90-269">BindingSource</span></span>|  
|<span data-ttu-id="aeb90-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="aeb90-270">DataGrid</span></span>|  
|<span data-ttu-id="aeb90-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="aeb90-271">DataGridView</span></span>|  
|<span data-ttu-id="aeb90-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="aeb90-272">DataNavigator</span></span>|  
|<span data-ttu-id="aeb90-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="aeb90-273">DomainUpDown</span></span>|  
|<span data-ttu-id="aeb90-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="aeb90-274">ErrorProvider</span></span>|  
|<span data-ttu-id="aeb90-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="aeb90-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="aeb90-276">Form</span><span class="sxs-lookup"><span data-stu-id="aeb90-276">Form</span></span>|  
|<span data-ttu-id="aeb90-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="aeb90-277">LinkLabel</span></span>|  
|<span data-ttu-id="aeb90-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="aeb90-278">HelpProvider</span></span>|  
|<span data-ttu-id="aeb90-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="aeb90-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="aeb90-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="aeb90-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="aeb90-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="aeb90-281">NumericUpDown</span></span>|  
|<span data-ttu-id="aeb90-282">Panel</span><span class="sxs-lookup"><span data-stu-id="aeb90-282">Panel</span></span>|  
|<span data-ttu-id="aeb90-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="aeb90-283">PictureBox</span></span>|  
|<span data-ttu-id="aeb90-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="aeb90-284">PrintDocument</span></span>|  
|<span data-ttu-id="aeb90-285">PrintPreviewControl</span><span class="sxs-lookup"><span data-stu-id="aeb90-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="aeb90-286">PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="aeb90-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="aeb90-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="aeb90-287">PropertyGrid</span></span>|  
|<span data-ttu-id="aeb90-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="aeb90-288">UserControl</span></span>|  
|<span data-ttu-id="aeb90-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="aeb90-289">ToolStrip</span></span>|  
|<span data-ttu-id="aeb90-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="aeb90-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="aeb90-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="aeb90-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="aeb90-292">Barra di divisione</span><span class="sxs-lookup"><span data-stu-id="aeb90-292">Splitter</span></span>|  
|<span data-ttu-id="aeb90-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="aeb90-293">RaftingContainer</span></span>|  
|<span data-ttu-id="aeb90-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="aeb90-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aeb90-295">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aeb90-295">See also</span></span>

- [<span data-ttu-id="aeb90-296">UI Automation Control Types</span><span class="sxs-lookup"><span data-stu-id="aeb90-296">UI Automation Control Types</span></span>](ui-automation-control-types.md)
