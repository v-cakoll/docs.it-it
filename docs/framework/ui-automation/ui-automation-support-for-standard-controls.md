---
title: Supporto per automazione interfaccia utente dei controlli standard
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 36028d589e98177f6a0e83092edd656860b1a8d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179859"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="979fd-102">Supporto per automazione interfaccia utente dei controlli standard</span><span class="sxs-lookup"><span data-stu-id="979fd-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="979fd-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="979fd-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="979fd-104">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="979fd-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="979fd-105">In questo argomento [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] sono contenute informazioni sul [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]supporto per i controlli standard nelle applicazioni sviluppate per i framework Win32 e Windows Form.</span><span class="sxs-lookup"><span data-stu-id="979fd-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32, and Windows Forms frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="979fd-106">Controlli WPF (Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="979fd-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="979fd-107">Tutti gli elementi di controllo [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] che forniscono informazioni o supporto per l'interazione dell'utente dispongono di supporto nativo completo per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="979fd-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="979fd-108">Gli altri elementi, ad esempio i pannelli, non sono visibile per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="979fd-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>
## <a name="win32-controls"></a><span data-ttu-id="979fd-109">Controlli Win32</span><span class="sxs-lookup"><span data-stu-id="979fd-109">Win32 Controls</span></span>  
 <span data-ttu-id="979fd-110">La maggior parte dei [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] controlli Win32 sono esposti a tramite provider sul lato client in UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="979fd-110">Most Win32 controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="979fd-111">Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="979fd-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="979fd-112">Il supporto completo viene fornito solo per i controlli della versione 6 di *ComCtrl32.dll*.</span><span class="sxs-lookup"><span data-stu-id="979fd-112">Full support is provided only for controls from version 6 of *ComCtrl32.dll*.</span></span>  
  
 <span data-ttu-id="979fd-113">I controlli seguenti sono supportati.</span><span class="sxs-lookup"><span data-stu-id="979fd-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="979fd-114">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="979fd-114">Class name</span></span>|<span data-ttu-id="979fd-115">Tipo di controllo</span><span class="sxs-lookup"><span data-stu-id="979fd-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="979fd-116">Pulsante</span><span class="sxs-lookup"><span data-stu-id="979fd-116">Button</span></span>|<span data-ttu-id="979fd-117">Pulsante</span><span class="sxs-lookup"><span data-stu-id="979fd-117">Button</span></span>|  
|<span data-ttu-id="979fd-118">Pulsante</span><span class="sxs-lookup"><span data-stu-id="979fd-118">Button</span></span>|<span data-ttu-id="979fd-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="979fd-119">RadioButton</span></span>|  
|<span data-ttu-id="979fd-120">Pulsante</span><span class="sxs-lookup"><span data-stu-id="979fd-120">Button</span></span>|<span data-ttu-id="979fd-121">Gruppo</span><span class="sxs-lookup"><span data-stu-id="979fd-121">Group</span></span>|  
|<span data-ttu-id="979fd-122">Pulsante</span><span class="sxs-lookup"><span data-stu-id="979fd-122">Button</span></span>|<span data-ttu-id="979fd-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="979fd-123">CheckBox</span></span>|  
|<span data-ttu-id="979fd-124">Pulsante</span><span class="sxs-lookup"><span data-stu-id="979fd-124">Button</span></span>|<span data-ttu-id="979fd-125">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="979fd-125">Hyperlink</span></span>|  
|<span data-ttu-id="979fd-126">Pulsante</span><span class="sxs-lookup"><span data-stu-id="979fd-126">Button</span></span>|<span data-ttu-id="979fd-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="979fd-127">SplitButton</span></span>|  
|<span data-ttu-id="979fd-128">Pulsante</span><span class="sxs-lookup"><span data-stu-id="979fd-128">Button</span></span>|<span data-ttu-id="979fd-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="979fd-129">CheckBox</span></span>|  
|<span data-ttu-id="979fd-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="979fd-130">ComboBoxEx32</span></span>|<span data-ttu-id="979fd-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="979fd-131">ComboBox</span></span>|  
|<span data-ttu-id="979fd-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="979fd-132">ComboBox</span></span>|<span data-ttu-id="979fd-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="979fd-133">ComboBox</span></span>|  
|<span data-ttu-id="979fd-134">Modifica</span><span class="sxs-lookup"><span data-stu-id="979fd-134">Edit</span></span>|<span data-ttu-id="979fd-135">Document</span><span class="sxs-lookup"><span data-stu-id="979fd-135">Document</span></span>|  
|<span data-ttu-id="979fd-136">Modifica</span><span class="sxs-lookup"><span data-stu-id="979fd-136">Edit</span></span>|<span data-ttu-id="979fd-137">Modifica</span><span class="sxs-lookup"><span data-stu-id="979fd-137">Edit</span></span>|  
|<span data-ttu-id="979fd-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="979fd-138">SysLink</span></span>|<span data-ttu-id="979fd-139">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="979fd-139">Hyperlink</span></span>|  
|<span data-ttu-id="979fd-140">Statico</span><span class="sxs-lookup"><span data-stu-id="979fd-140">Static</span></span>|<span data-ttu-id="979fd-141">Text</span><span class="sxs-lookup"><span data-stu-id="979fd-141">Text</span></span>|  
|<span data-ttu-id="979fd-142">Statico</span><span class="sxs-lookup"><span data-stu-id="979fd-142">Static</span></span>|<span data-ttu-id="979fd-143">Immagine</span><span class="sxs-lookup"><span data-stu-id="979fd-143">Image</span></span>|  
|<span data-ttu-id="979fd-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="979fd-144">SysIPAddress32</span></span>|<span data-ttu-id="979fd-145">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="979fd-145">Custom</span></span>|  
|<span data-ttu-id="979fd-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="979fd-146">SysHeader32</span></span>|<span data-ttu-id="979fd-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="979fd-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="979fd-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="979fd-148">SysListView32</span></span>|<span data-ttu-id="979fd-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="979fd-149">DataGrid</span></span>|  
|<span data-ttu-id="979fd-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="979fd-150">SysListView32</span></span>|<span data-ttu-id="979fd-151">Elenco</span><span class="sxs-lookup"><span data-stu-id="979fd-151">List</span></span>|  
|<span data-ttu-id="979fd-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="979fd-152">ListBox</span></span>|<span data-ttu-id="979fd-153">Elenco</span><span class="sxs-lookup"><span data-stu-id="979fd-153">List</span></span>|  
|<span data-ttu-id="979fd-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="979fd-154">ListBox</span></span>|<span data-ttu-id="979fd-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="979fd-155">ListItem</span></span>|  
|<span data-ttu-id="979fd-156">#32768</span><span class="sxs-lookup"><span data-stu-id="979fd-156">#32768</span></span>|<span data-ttu-id="979fd-157">Menu</span><span class="sxs-lookup"><span data-stu-id="979fd-157">Menu</span></span>|  
|<span data-ttu-id="979fd-158">#32768</span><span class="sxs-lookup"><span data-stu-id="979fd-158">#32768</span></span>|<span data-ttu-id="979fd-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="979fd-159">MenuItem</span></span>|  
|<span data-ttu-id="979fd-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="979fd-160">msctls_progress32</span></span>|<span data-ttu-id="979fd-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="979fd-161">ProgressBar</span></span>|  
|<span data-ttu-id="979fd-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="979fd-162">RichEdit</span></span>|<span data-ttu-id="979fd-163">Documento.</span><span class="sxs-lookup"><span data-stu-id="979fd-163">Document.</span></span> <span data-ttu-id="979fd-164">Vedere la nota.</span><span class="sxs-lookup"><span data-stu-id="979fd-164">See note.</span></span>|  
|<span data-ttu-id="979fd-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="979fd-165">RichEdit20A</span></span>|<span data-ttu-id="979fd-166">Document</span><span class="sxs-lookup"><span data-stu-id="979fd-166">Document</span></span>|  
|<span data-ttu-id="979fd-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="979fd-167">RichEdit20W</span></span>|<span data-ttu-id="979fd-168">Document</span><span class="sxs-lookup"><span data-stu-id="979fd-168">Document</span></span>|  
|<span data-ttu-id="979fd-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="979fd-169">RichEdit50W</span></span>|<span data-ttu-id="979fd-170">Document</span><span class="sxs-lookup"><span data-stu-id="979fd-170">Document</span></span>|  
|<span data-ttu-id="979fd-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="979fd-171">ScrollBar</span></span>|<span data-ttu-id="979fd-172">Dispositivo di scorrimento</span><span class="sxs-lookup"><span data-stu-id="979fd-172">Slider</span></span>|  
|<span data-ttu-id="979fd-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="979fd-173">msctls_trackbar32</span></span>|<span data-ttu-id="979fd-174">Dispositivo di scorrimento</span><span class="sxs-lookup"><span data-stu-id="979fd-174">Slider</span></span>|  
|<span data-ttu-id="979fd-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="979fd-175">msctls_updown32</span></span>|<span data-ttu-id="979fd-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="979fd-176">Spinner</span></span>|  
|<span data-ttu-id="979fd-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="979fd-177">msctls_statusbar32</span></span>|<span data-ttu-id="979fd-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="979fd-178">StatusBar</span></span>|  
|<span data-ttu-id="979fd-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="979fd-179">SysTabControl32</span></span>|<span data-ttu-id="979fd-180">Scheda</span><span class="sxs-lookup"><span data-stu-id="979fd-180">Tab</span></span>|  
|<span data-ttu-id="979fd-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="979fd-181">SysTabControl32</span></span>|<span data-ttu-id="979fd-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="979fd-182">TabItem</span></span>|  
|<span data-ttu-id="979fd-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="979fd-183">ToolbarWindow32</span></span>|<span data-ttu-id="979fd-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="979fd-184">ToolBar</span></span>|  
|<span data-ttu-id="979fd-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="979fd-185">ToolbarWindow32</span></span>|<span data-ttu-id="979fd-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="979fd-186">MenuItem</span></span>|  
|<span data-ttu-id="979fd-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="979fd-187">ToolbarWindow32</span></span>|<span data-ttu-id="979fd-188">Pulsante</span><span class="sxs-lookup"><span data-stu-id="979fd-188">Button</span></span>|  
|<span data-ttu-id="979fd-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="979fd-189">ToolbarWindow32</span></span>|<span data-ttu-id="979fd-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="979fd-190">CheckBox</span></span>|  
|<span data-ttu-id="979fd-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="979fd-191">ToolbarWindow32</span></span>|<span data-ttu-id="979fd-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="979fd-192">RadioButton</span></span>|  
|<span data-ttu-id="979fd-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="979fd-193">ToolbarWindow32</span></span>|<span data-ttu-id="979fd-194">Separatore</span><span class="sxs-lookup"><span data-stu-id="979fd-194">Separator</span></span>|  
|<span data-ttu-id="979fd-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="979fd-195">tooltips_class32</span></span>|<span data-ttu-id="979fd-196">ToolTip</span><span class="sxs-lookup"><span data-stu-id="979fd-196">ToolTip</span></span>|  
|<span data-ttu-id="979fd-197">#32774</span><span class="sxs-lookup"><span data-stu-id="979fd-197">#32774</span></span>|<span data-ttu-id="979fd-198">ToolTip</span><span class="sxs-lookup"><span data-stu-id="979fd-198">ToolTip</span></span>|  
|<span data-ttu-id="979fd-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="979fd-199">ReBarWindow32</span></span>|<span data-ttu-id="979fd-200">Barra degli strumenti</span><span class="sxs-lookup"><span data-stu-id="979fd-200">Toolbar</span></span>|  
|<span data-ttu-id="979fd-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="979fd-201">SysTreeView32</span></span>|<span data-ttu-id="979fd-202">Albero</span><span class="sxs-lookup"><span data-stu-id="979fd-202">Tree</span></span>|  
|<span data-ttu-id="979fd-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="979fd-203">SysTreeView32</span></span>|<span data-ttu-id="979fd-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="979fd-204">TreeItem</span></span>|  
  
 <span data-ttu-id="979fd-205">**Nota:** Il controllo RichEdit è supportato solo per le versioni fornite con Windows Vista (in RichEd20.dll versione 3.1 e successive e MsftEdit.dll versione 4.1 e successive).</span><span class="sxs-lookup"><span data-stu-id="979fd-205">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="979fd-206">I controlli seguenti non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="979fd-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="979fd-207">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="979fd-207">Class name</span></span>|<span data-ttu-id="979fd-208">Tipo di controllo</span><span class="sxs-lookup"><span data-stu-id="979fd-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="979fd-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="979fd-209">SysAnimate32</span></span>|<span data-ttu-id="979fd-210">Immagine</span><span class="sxs-lookup"><span data-stu-id="979fd-210">Image</span></span>|  
|<span data-ttu-id="979fd-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="979fd-211">SysPager</span></span>|<span data-ttu-id="979fd-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="979fd-212">Spinner</span></span>|  
|<span data-ttu-id="979fd-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="979fd-213">SysDateTimePick32</span></span>|<span data-ttu-id="979fd-214">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="979fd-214">Custom</span></span>|  
|<span data-ttu-id="979fd-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="979fd-215">SysMonthCal32</span></span>|<span data-ttu-id="979fd-216">Calendario</span><span class="sxs-lookup"><span data-stu-id="979fd-216">Calendar</span></span>|  
|<span data-ttu-id="979fd-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="979fd-217">MS_WINNOTE</span></span>|<span data-ttu-id="979fd-218">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="979fd-218">Tooltip</span></span>|  
|<span data-ttu-id="979fd-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="979fd-219">VBBubble</span></span>|<span data-ttu-id="979fd-220">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="979fd-220">Tooltip</span></span>|  
|<span data-ttu-id="979fd-221">ScrollBar (se usato come controllo autonomo)</span><span class="sxs-lookup"><span data-stu-id="979fd-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="979fd-222">Dispositivo di scorrimento</span><span class="sxs-lookup"><span data-stu-id="979fd-222">Slider</span></span>|  
|<span data-ttu-id="979fd-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="979fd-223">SuperGrid</span></span>|<span data-ttu-id="979fd-224">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="979fd-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>
## <a name="windows-forms-controls"></a><span data-ttu-id="979fd-225">Controlli per Windows Form</span><span class="sxs-lookup"><span data-stu-id="979fd-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="979fd-226">I controlli Windows [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Form vengono esposti tramite provider sul lato client in UIAutomationClientsideProviders.dll.Windows Forms controls are exposed to through client-side providers in UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="979fd-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="979fd-227">Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="979fd-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="979fd-228">In genere, i controlli Windows Form che sono wrapper [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]gestiti per i controlli comuni Win32 sono supportati da .</span><span class="sxs-lookup"><span data-stu-id="979fd-228">Typically, Windows Forms controls that are managed wrappers for Win32 common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="979fd-229">I controlli seguenti sono supportati.</span><span class="sxs-lookup"><span data-stu-id="979fd-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="979fd-230">Nome della classe</span><span class="sxs-lookup"><span data-stu-id="979fd-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="979fd-231">Pulsante</span><span class="sxs-lookup"><span data-stu-id="979fd-231">Button</span></span>|  
|<span data-ttu-id="979fd-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="979fd-232">CheckBox</span></span>|  
|<span data-ttu-id="979fd-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="979fd-233">CheckedListBox</span></span>|  
|<span data-ttu-id="979fd-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="979fd-234">ColorDialog</span></span>|  
|<span data-ttu-id="979fd-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="979fd-235">ComboBox</span></span>|  
|<span data-ttu-id="979fd-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="979fd-236">FolderBrowser</span></span>|  
|<span data-ttu-id="979fd-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="979fd-237">FontDialog</span></span>|  
|<span data-ttu-id="979fd-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="979fd-238">GroupBox</span></span>|  
|<span data-ttu-id="979fd-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="979fd-239">HscrollBar</span></span>|  
|<span data-ttu-id="979fd-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="979fd-240">ImageList</span></span>|  
|<span data-ttu-id="979fd-241">Etichetta</span><span class="sxs-lookup"><span data-stu-id="979fd-241">Label</span></span>|  
|<span data-ttu-id="979fd-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="979fd-242">ListBox</span></span>|  
|<span data-ttu-id="979fd-243">ListView</span><span class="sxs-lookup"><span data-stu-id="979fd-243">ListView</span></span>|  
|<span data-ttu-id="979fd-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="979fd-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="979fd-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="979fd-245">MonthCalendar</span></span>|  
|<span data-ttu-id="979fd-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="979fd-246">NotifyIcon</span></span>|  
|<span data-ttu-id="979fd-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="979fd-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="979fd-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="979fd-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="979fd-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="979fd-249">PrintDialog</span></span>|  
|<span data-ttu-id="979fd-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="979fd-250">ProgressBar</span></span>|  
|<span data-ttu-id="979fd-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="979fd-251">RadioButton</span></span>|  
|<span data-ttu-id="979fd-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="979fd-252">RichTextBox</span></span>|  
|<span data-ttu-id="979fd-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="979fd-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="979fd-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="979fd-254">ScrollableControl</span></span>|  
|<span data-ttu-id="979fd-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="979fd-255">SoundPlayer</span></span>|  
|<span data-ttu-id="979fd-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="979fd-256">StatusBar</span></span>|  
|<span data-ttu-id="979fd-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="979fd-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="979fd-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="979fd-258">TextBox</span></span>|  
|<span data-ttu-id="979fd-259">Timer</span><span class="sxs-lookup"><span data-stu-id="979fd-259">Timer</span></span>|  
|<span data-ttu-id="979fd-260">Barra degli strumenti</span><span class="sxs-lookup"><span data-stu-id="979fd-260">Toolbar</span></span>|  
|<span data-ttu-id="979fd-261">ToolTip</span><span class="sxs-lookup"><span data-stu-id="979fd-261">ToolTip</span></span>|  
|<span data-ttu-id="979fd-262">Trackbar</span><span class="sxs-lookup"><span data-stu-id="979fd-262">TrackBar</span></span>|  
|<span data-ttu-id="979fd-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="979fd-263">TreeView</span></span>|  
|<span data-ttu-id="979fd-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="979fd-264">VscrollBar</span></span>|  
|<span data-ttu-id="979fd-265">WebBrowser</span><span class="sxs-lookup"><span data-stu-id="979fd-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="979fd-266">I controlli seguenti [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] vengono esposti solo tramite il supporto per Microsoft Active Accessibility.</span><span class="sxs-lookup"><span data-stu-id="979fd-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="979fd-267">Alcune funzionalità potrebbero non essere disponibili.</span><span class="sxs-lookup"><span data-stu-id="979fd-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="979fd-268">Nome del controllo</span><span class="sxs-lookup"><span data-stu-id="979fd-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="979fd-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="979fd-269">BindingSource</span></span>|  
|<span data-ttu-id="979fd-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="979fd-270">DataGrid</span></span>|  
|<span data-ttu-id="979fd-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="979fd-271">DataGridView</span></span>|  
|<span data-ttu-id="979fd-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="979fd-272">DataNavigator</span></span>|  
|<span data-ttu-id="979fd-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="979fd-273">DomainUpDown</span></span>|  
|<span data-ttu-id="979fd-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="979fd-274">ErrorProvider</span></span>|  
|<span data-ttu-id="979fd-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="979fd-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="979fd-276">Form</span><span class="sxs-lookup"><span data-stu-id="979fd-276">Form</span></span>|  
|<span data-ttu-id="979fd-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="979fd-277">LinkLabel</span></span>|  
|<span data-ttu-id="979fd-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="979fd-278">HelpProvider</span></span>|  
|<span data-ttu-id="979fd-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="979fd-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="979fd-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="979fd-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="979fd-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="979fd-281">NumericUpDown</span></span>|  
|<span data-ttu-id="979fd-282">Panel</span><span class="sxs-lookup"><span data-stu-id="979fd-282">Panel</span></span>|  
|<span data-ttu-id="979fd-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="979fd-283">PictureBox</span></span>|  
|<span data-ttu-id="979fd-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="979fd-284">PrintDocument</span></span>|  
|<span data-ttu-id="979fd-285">PrintPreviewControl</span><span class="sxs-lookup"><span data-stu-id="979fd-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="979fd-286">PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="979fd-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="979fd-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="979fd-287">PropertyGrid</span></span>|  
|<span data-ttu-id="979fd-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="979fd-288">UserControl</span></span>|  
|<span data-ttu-id="979fd-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="979fd-289">ToolStrip</span></span>|  
|<span data-ttu-id="979fd-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="979fd-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="979fd-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="979fd-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="979fd-292">Splitter</span><span class="sxs-lookup"><span data-stu-id="979fd-292">Splitter</span></span>|  
|<span data-ttu-id="979fd-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="979fd-293">RaftingContainer</span></span>|  
|<span data-ttu-id="979fd-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="979fd-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="979fd-295">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="979fd-295">See also</span></span>

- [<span data-ttu-id="979fd-296">Tipi di controllo per l'automazione dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="979fd-296">UI Automation Control Types</span></span>](ui-automation-control-types.md)
