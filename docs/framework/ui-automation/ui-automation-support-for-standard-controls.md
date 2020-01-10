---
title: Supporto per automazione interfaccia utente dei controlli standard
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: ed5e4f6ab23fe9ae77c94616a668da8accb46d4b
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741709"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="0f144-102">Supporto per automazione interfaccia utente dei controlli standard</span><span class="sxs-lookup"><span data-stu-id="0f144-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="0f144-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="0f144-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="0f144-104">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="0f144-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="0f144-105">Questo argomento contiene informazioni sul supporto [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] per i controlli standard in applicazioni sviluppate per i Framework [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32 e [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f144-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32, and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="0f144-106">Controlli WPF (Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="0f144-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="0f144-107">Tutti gli elementi di controllo [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] che forniscono informazioni o supporto per l'interazione dell'utente dispongono di supporto nativo completo per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f144-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="0f144-108">Gli altri elementi, ad esempio i pannelli, non sono visibile per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f144-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="0f144-109">Controlli Win32</span><span class="sxs-lookup"><span data-stu-id="0f144-109">Win32 Controls</span></span>  
 <span data-ttu-id="0f144-110">La maggior parte dei controlli Win32 viene esposta a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tramite provider lato client in UIAutomationClientsideProviders. dll.</span><span class="sxs-lookup"><span data-stu-id="0f144-110">Most Win32 controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="0f144-111">Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="0f144-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="0f144-112">Il supporto completo viene fornito solo per i controlli della versione 6 di *ComCtrl32. dll*.</span><span class="sxs-lookup"><span data-stu-id="0f144-112">Full support is provided only for controls from version 6 of *ComCtrl32.dll*.</span></span>  
  
 <span data-ttu-id="0f144-113">I controlli seguenti sono supportati.</span><span class="sxs-lookup"><span data-stu-id="0f144-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="0f144-114">Nome della classe</span><span class="sxs-lookup"><span data-stu-id="0f144-114">Class name</span></span>|<span data-ttu-id="0f144-115">Tipo di controllo</span><span class="sxs-lookup"><span data-stu-id="0f144-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="0f144-116">Button</span><span class="sxs-lookup"><span data-stu-id="0f144-116">Button</span></span>|<span data-ttu-id="0f144-117">Button</span><span class="sxs-lookup"><span data-stu-id="0f144-117">Button</span></span>|  
|<span data-ttu-id="0f144-118">Button</span><span class="sxs-lookup"><span data-stu-id="0f144-118">Button</span></span>|<span data-ttu-id="0f144-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="0f144-119">RadioButton</span></span>|  
|<span data-ttu-id="0f144-120">Button</span><span class="sxs-lookup"><span data-stu-id="0f144-120">Button</span></span>|<span data-ttu-id="0f144-121">Gruppo</span><span class="sxs-lookup"><span data-stu-id="0f144-121">Group</span></span>|  
|<span data-ttu-id="0f144-122">Button</span><span class="sxs-lookup"><span data-stu-id="0f144-122">Button</span></span>|<span data-ttu-id="0f144-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="0f144-123">CheckBox</span></span>|  
|<span data-ttu-id="0f144-124">Button</span><span class="sxs-lookup"><span data-stu-id="0f144-124">Button</span></span>|<span data-ttu-id="0f144-125">Collegamento ipertestuale</span><span class="sxs-lookup"><span data-stu-id="0f144-125">Hyperlink</span></span>|  
|<span data-ttu-id="0f144-126">Button</span><span class="sxs-lookup"><span data-stu-id="0f144-126">Button</span></span>|<span data-ttu-id="0f144-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="0f144-127">SplitButton</span></span>|  
|<span data-ttu-id="0f144-128">Button</span><span class="sxs-lookup"><span data-stu-id="0f144-128">Button</span></span>|<span data-ttu-id="0f144-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="0f144-129">CheckBox</span></span>|  
|<span data-ttu-id="0f144-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="0f144-130">ComboBoxEx32</span></span>|<span data-ttu-id="0f144-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="0f144-131">ComboBox</span></span>|  
|<span data-ttu-id="0f144-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="0f144-132">ComboBox</span></span>|<span data-ttu-id="0f144-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="0f144-133">ComboBox</span></span>|  
|<span data-ttu-id="0f144-134">Edit</span><span class="sxs-lookup"><span data-stu-id="0f144-134">Edit</span></span>|<span data-ttu-id="0f144-135">Documento</span><span class="sxs-lookup"><span data-stu-id="0f144-135">Document</span></span>|  
|<span data-ttu-id="0f144-136">Edit</span><span class="sxs-lookup"><span data-stu-id="0f144-136">Edit</span></span>|<span data-ttu-id="0f144-137">Edit</span><span class="sxs-lookup"><span data-stu-id="0f144-137">Edit</span></span>|  
|<span data-ttu-id="0f144-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="0f144-138">SysLink</span></span>|<span data-ttu-id="0f144-139">Collegamento ipertestuale</span><span class="sxs-lookup"><span data-stu-id="0f144-139">Hyperlink</span></span>|  
|<span data-ttu-id="0f144-140">Static</span><span class="sxs-lookup"><span data-stu-id="0f144-140">Static</span></span>|<span data-ttu-id="0f144-141">Testo</span><span class="sxs-lookup"><span data-stu-id="0f144-141">Text</span></span>|  
|<span data-ttu-id="0f144-142">Static</span><span class="sxs-lookup"><span data-stu-id="0f144-142">Static</span></span>|<span data-ttu-id="0f144-143">Immagine</span><span class="sxs-lookup"><span data-stu-id="0f144-143">Image</span></span>|  
|<span data-ttu-id="0f144-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="0f144-144">SysIPAddress32</span></span>|<span data-ttu-id="0f144-145">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="0f144-145">Custom</span></span>|  
|<span data-ttu-id="0f144-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="0f144-146">SysHeader32</span></span>|<span data-ttu-id="0f144-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="0f144-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="0f144-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="0f144-148">SysListView32</span></span>|<span data-ttu-id="0f144-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="0f144-149">DataGrid</span></span>|  
|<span data-ttu-id="0f144-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="0f144-150">SysListView32</span></span>|<span data-ttu-id="0f144-151">Contiene un elenco di oggetti</span><span class="sxs-lookup"><span data-stu-id="0f144-151">List</span></span>|  
|<span data-ttu-id="0f144-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="0f144-152">ListBox</span></span>|<span data-ttu-id="0f144-153">Contiene un elenco di oggetti</span><span class="sxs-lookup"><span data-stu-id="0f144-153">List</span></span>|  
|<span data-ttu-id="0f144-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="0f144-154">ListBox</span></span>|<span data-ttu-id="0f144-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="0f144-155">ListItem</span></span>|  
|<span data-ttu-id="0f144-156">#32768</span><span class="sxs-lookup"><span data-stu-id="0f144-156">#32768</span></span>|<span data-ttu-id="0f144-157">Menu</span><span class="sxs-lookup"><span data-stu-id="0f144-157">Menu</span></span>|  
|<span data-ttu-id="0f144-158">#32768</span><span class="sxs-lookup"><span data-stu-id="0f144-158">#32768</span></span>|<span data-ttu-id="0f144-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="0f144-159">MenuItem</span></span>|  
|<span data-ttu-id="0f144-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="0f144-160">msctls_progress32</span></span>|<span data-ttu-id="0f144-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="0f144-161">ProgressBar</span></span>|  
|<span data-ttu-id="0f144-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="0f144-162">RichEdit</span></span>|<span data-ttu-id="0f144-163">Document</span><span class="sxs-lookup"><span data-stu-id="0f144-163">Document.</span></span> <span data-ttu-id="0f144-164">Vedere la nota.</span><span class="sxs-lookup"><span data-stu-id="0f144-164">See note.</span></span>|  
|<span data-ttu-id="0f144-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="0f144-165">RichEdit20A</span></span>|<span data-ttu-id="0f144-166">Documento</span><span class="sxs-lookup"><span data-stu-id="0f144-166">Document</span></span>|  
|<span data-ttu-id="0f144-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="0f144-167">RichEdit20W</span></span>|<span data-ttu-id="0f144-168">Documento</span><span class="sxs-lookup"><span data-stu-id="0f144-168">Document</span></span>|  
|<span data-ttu-id="0f144-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="0f144-169">RichEdit50W</span></span>|<span data-ttu-id="0f144-170">Documento</span><span class="sxs-lookup"><span data-stu-id="0f144-170">Document</span></span>|  
|<span data-ttu-id="0f144-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="0f144-171">ScrollBar</span></span>|<span data-ttu-id="0f144-172">Slider</span><span class="sxs-lookup"><span data-stu-id="0f144-172">Slider</span></span>|  
|<span data-ttu-id="0f144-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="0f144-173">msctls_trackbar32</span></span>|<span data-ttu-id="0f144-174">Slider</span><span class="sxs-lookup"><span data-stu-id="0f144-174">Slider</span></span>|  
|<span data-ttu-id="0f144-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="0f144-175">msctls_updown32</span></span>|<span data-ttu-id="0f144-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="0f144-176">Spinner</span></span>|  
|<span data-ttu-id="0f144-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="0f144-177">msctls_statusbar32</span></span>|<span data-ttu-id="0f144-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="0f144-178">StatusBar</span></span>|  
|<span data-ttu-id="0f144-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="0f144-179">SysTabControl32</span></span>|<span data-ttu-id="0f144-180">Tab</span><span class="sxs-lookup"><span data-stu-id="0f144-180">Tab</span></span>|  
|<span data-ttu-id="0f144-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="0f144-181">SysTabControl32</span></span>|<span data-ttu-id="0f144-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="0f144-182">TabItem</span></span>|  
|<span data-ttu-id="0f144-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="0f144-183">ToolbarWindow32</span></span>|<span data-ttu-id="0f144-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="0f144-184">ToolBar</span></span>|  
|<span data-ttu-id="0f144-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="0f144-185">ToolbarWindow32</span></span>|<span data-ttu-id="0f144-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="0f144-186">MenuItem</span></span>|  
|<span data-ttu-id="0f144-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="0f144-187">ToolbarWindow32</span></span>|<span data-ttu-id="0f144-188">Button</span><span class="sxs-lookup"><span data-stu-id="0f144-188">Button</span></span>|  
|<span data-ttu-id="0f144-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="0f144-189">ToolbarWindow32</span></span>|<span data-ttu-id="0f144-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="0f144-190">CheckBox</span></span>|  
|<span data-ttu-id="0f144-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="0f144-191">ToolbarWindow32</span></span>|<span data-ttu-id="0f144-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="0f144-192">RadioButton</span></span>|  
|<span data-ttu-id="0f144-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="0f144-193">ToolbarWindow32</span></span>|<span data-ttu-id="0f144-194">Separator</span><span class="sxs-lookup"><span data-stu-id="0f144-194">Separator</span></span>|  
|<span data-ttu-id="0f144-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="0f144-195">tooltips_class32</span></span>|<span data-ttu-id="0f144-196">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="0f144-196">ToolTip</span></span>|  
|<span data-ttu-id="0f144-197">#32774</span><span class="sxs-lookup"><span data-stu-id="0f144-197">#32774</span></span>|<span data-ttu-id="0f144-198">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="0f144-198">ToolTip</span></span>|  
|<span data-ttu-id="0f144-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="0f144-199">ReBarWindow32</span></span>|<span data-ttu-id="0f144-200">ToolBar</span><span class="sxs-lookup"><span data-stu-id="0f144-200">Toolbar</span></span>|  
|<span data-ttu-id="0f144-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="0f144-201">SysTreeView32</span></span>|<span data-ttu-id="0f144-202">Tree</span><span class="sxs-lookup"><span data-stu-id="0f144-202">Tree</span></span>|  
|<span data-ttu-id="0f144-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="0f144-203">SysTreeView32</span></span>|<span data-ttu-id="0f144-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="0f144-204">TreeItem</span></span>|  
  
 <span data-ttu-id="0f144-205">**Nota** Il controllo RichEdit è supportato solo per le versioni fornite con Windows Vista (in RichEd20. dll versione 3,1 e successive e MsftEdit. dll versione 4,1 e successive).</span><span class="sxs-lookup"><span data-stu-id="0f144-205">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="0f144-206">I controlli seguenti non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="0f144-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="0f144-207">Nome della classe</span><span class="sxs-lookup"><span data-stu-id="0f144-207">Class name</span></span>|<span data-ttu-id="0f144-208">Tipo di controllo</span><span class="sxs-lookup"><span data-stu-id="0f144-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="0f144-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="0f144-209">SysAnimate32</span></span>|<span data-ttu-id="0f144-210">Immagine</span><span class="sxs-lookup"><span data-stu-id="0f144-210">Image</span></span>|  
|<span data-ttu-id="0f144-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="0f144-211">SysPager</span></span>|<span data-ttu-id="0f144-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="0f144-212">Spinner</span></span>|  
|<span data-ttu-id="0f144-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="0f144-213">SysDateTimePick32</span></span>|<span data-ttu-id="0f144-214">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="0f144-214">Custom</span></span>|  
|<span data-ttu-id="0f144-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="0f144-215">SysMonthCal32</span></span>|<span data-ttu-id="0f144-216">Calendar</span><span class="sxs-lookup"><span data-stu-id="0f144-216">Calendar</span></span>|  
|<span data-ttu-id="0f144-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="0f144-217">MS_WINNOTE</span></span>|<span data-ttu-id="0f144-218">ToolTip</span><span class="sxs-lookup"><span data-stu-id="0f144-218">Tooltip</span></span>|  
|<span data-ttu-id="0f144-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="0f144-219">VBBubble</span></span>|<span data-ttu-id="0f144-220">ToolTip</span><span class="sxs-lookup"><span data-stu-id="0f144-220">Tooltip</span></span>|  
|<span data-ttu-id="0f144-221">ScrollBar (se usato come controllo autonomo)</span><span class="sxs-lookup"><span data-stu-id="0f144-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="0f144-222">Slider</span><span class="sxs-lookup"><span data-stu-id="0f144-222">Slider</span></span>|  
|<span data-ttu-id="0f144-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="0f144-223">SuperGrid</span></span>|<span data-ttu-id="0f144-224">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="0f144-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="0f144-225">Controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="0f144-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="0f144-226">I controlli Windows Forms vengono esposti ai [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tramite provider lato client in UIAutomationClientsideProviders. dll.</span><span class="sxs-lookup"><span data-stu-id="0f144-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="0f144-227">Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="0f144-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="0f144-228">In genere, Windows Forms controlli che sono wrapper gestiti per i controlli comuni Win32 sono supportati da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f144-228">Typically, Windows Forms controls that are managed wrappers for Win32 common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="0f144-229">I controlli seguenti sono supportati.</span><span class="sxs-lookup"><span data-stu-id="0f144-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="0f144-230">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="0f144-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="0f144-231">Button</span><span class="sxs-lookup"><span data-stu-id="0f144-231">Button</span></span>|  
|<span data-ttu-id="0f144-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="0f144-232">CheckBox</span></span>|  
|<span data-ttu-id="0f144-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="0f144-233">CheckedListBox</span></span>|  
|<span data-ttu-id="0f144-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="0f144-234">ColorDialog</span></span>|  
|<span data-ttu-id="0f144-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="0f144-235">ComboBox</span></span>|  
|<span data-ttu-id="0f144-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="0f144-236">FolderBrowser</span></span>|  
|<span data-ttu-id="0f144-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="0f144-237">FontDialog</span></span>|  
|<span data-ttu-id="0f144-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="0f144-238">GroupBox</span></span>|  
|<span data-ttu-id="0f144-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="0f144-239">HscrollBar</span></span>|  
|<span data-ttu-id="0f144-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="0f144-240">ImageList</span></span>|  
|<span data-ttu-id="0f144-241">Label</span><span class="sxs-lookup"><span data-stu-id="0f144-241">Label</span></span>|  
|<span data-ttu-id="0f144-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="0f144-242">ListBox</span></span>|  
|<span data-ttu-id="0f144-243">ListView</span><span class="sxs-lookup"><span data-stu-id="0f144-243">ListView</span></span>|  
|<span data-ttu-id="0f144-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="0f144-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="0f144-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="0f144-245">MonthCalendar</span></span>|  
|<span data-ttu-id="0f144-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="0f144-246">NotifyIcon</span></span>|  
|<span data-ttu-id="0f144-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="0f144-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="0f144-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="0f144-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="0f144-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="0f144-249">PrintDialog</span></span>|  
|<span data-ttu-id="0f144-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="0f144-250">ProgressBar</span></span>|  
|<span data-ttu-id="0f144-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="0f144-251">RadioButton</span></span>|  
|<span data-ttu-id="0f144-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="0f144-252">RichTextBox</span></span>|  
|<span data-ttu-id="0f144-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="0f144-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="0f144-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="0f144-254">ScrollableControl</span></span>|  
|<span data-ttu-id="0f144-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="0f144-255">SoundPlayer</span></span>|  
|<span data-ttu-id="0f144-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="0f144-256">StatusBar</span></span>|  
|<span data-ttu-id="0f144-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="0f144-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="0f144-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="0f144-258">TextBox</span></span>|  
|<span data-ttu-id="0f144-259">Timer</span><span class="sxs-lookup"><span data-stu-id="0f144-259">Timer</span></span>|  
|<span data-ttu-id="0f144-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="0f144-260">Toolbar</span></span>|  
|<span data-ttu-id="0f144-261">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="0f144-261">ToolTip</span></span>|  
|<span data-ttu-id="0f144-262">Trackbar</span><span class="sxs-lookup"><span data-stu-id="0f144-262">TrackBar</span></span>|  
|<span data-ttu-id="0f144-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="0f144-263">TreeView</span></span>|  
|<span data-ttu-id="0f144-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="0f144-264">VscrollBar</span></span>|  
|<span data-ttu-id="0f144-265">WebBrowser</span><span class="sxs-lookup"><span data-stu-id="0f144-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="0f144-266">I controlli seguenti sono esposti a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] solo tramite il supporto per Microsoft Active Accessibility.</span><span class="sxs-lookup"><span data-stu-id="0f144-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="0f144-267">Alcune funzionalità potrebbero non essere disponibili.</span><span class="sxs-lookup"><span data-stu-id="0f144-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="0f144-268">Nome controllo</span><span class="sxs-lookup"><span data-stu-id="0f144-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="0f144-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="0f144-269">BindingSource</span></span>|  
|<span data-ttu-id="0f144-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="0f144-270">DataGrid</span></span>|  
|<span data-ttu-id="0f144-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="0f144-271">DataGridView</span></span>|  
|<span data-ttu-id="0f144-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="0f144-272">DataNavigator</span></span>|  
|<span data-ttu-id="0f144-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="0f144-273">DomainUpDown</span></span>|  
|<span data-ttu-id="0f144-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="0f144-274">ErrorProvider</span></span>|  
|<span data-ttu-id="0f144-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="0f144-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="0f144-276">Form</span><span class="sxs-lookup"><span data-stu-id="0f144-276">Form</span></span>|  
|<span data-ttu-id="0f144-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="0f144-277">LinkLabel</span></span>|  
|<span data-ttu-id="0f144-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="0f144-278">HelpProvider</span></span>|  
|<span data-ttu-id="0f144-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="0f144-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="0f144-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="0f144-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="0f144-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="0f144-281">NumericUpDown</span></span>|  
|<span data-ttu-id="0f144-282">Panel</span><span class="sxs-lookup"><span data-stu-id="0f144-282">Panel</span></span>|  
|<span data-ttu-id="0f144-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="0f144-283">PictureBox</span></span>|  
|<span data-ttu-id="0f144-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="0f144-284">PrintDocument</span></span>|  
|<span data-ttu-id="0f144-285">PrintPreviewControl</span><span class="sxs-lookup"><span data-stu-id="0f144-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="0f144-286">PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="0f144-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="0f144-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="0f144-287">PropertyGrid</span></span>|  
|<span data-ttu-id="0f144-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="0f144-288">UserControl</span></span>|  
|<span data-ttu-id="0f144-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="0f144-289">ToolStrip</span></span>|  
|<span data-ttu-id="0f144-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="0f144-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="0f144-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="0f144-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="0f144-292">Barra di divisione</span><span class="sxs-lookup"><span data-stu-id="0f144-292">Splitter</span></span>|  
|<span data-ttu-id="0f144-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="0f144-293">RaftingContainer</span></span>|  
|<span data-ttu-id="0f144-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="0f144-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0f144-295">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f144-295">See also</span></span>

- [<span data-ttu-id="0f144-296">UI Automation Control Types</span><span class="sxs-lookup"><span data-stu-id="0f144-296">UI Automation Control Types</span></span>](ui-automation-control-types.md)
