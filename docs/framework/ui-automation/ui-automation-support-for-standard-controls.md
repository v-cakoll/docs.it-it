---
title: Supporto per automazione interfaccia utente dei controlli standard
description: Ottenere informazioni sul supporto di automazione interfaccia utente per i controlli standard in applicazioni sviluppate per Windows Presentation Foundation (WPF), Win32 e Windows Forms.
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 17916a6978008439e91caae00d8b6f26045f9018
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166125"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="fd304-103">Supporto per automazione interfaccia utente dei controlli standard</span><span class="sxs-lookup"><span data-stu-id="fd304-103">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="fd304-104">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="fd304-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="fd304-105">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="fd304-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="fd304-106">Questo argomento contiene informazioni sul [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] supporto di per i controlli standard in applicazioni sviluppate per i [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] Framework, Win32 e Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="fd304-106">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32, and Windows Forms frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="fd304-107">Controlli WPF (Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="fd304-107">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="fd304-108">Tutti gli elementi di controllo [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] che forniscono informazioni o supporto per l'interazione dell'utente dispongono di supporto nativo completo per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fd304-108">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="fd304-109">Gli altri elementi, ad esempio i pannelli, non sono visibile per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fd304-109">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>
## <a name="win32-controls"></a><span data-ttu-id="fd304-110">Controlli Win32</span><span class="sxs-lookup"><span data-stu-id="fd304-110">Win32 Controls</span></span>  
 <span data-ttu-id="fd304-111">La maggior parte dei controlli Win32 viene esposta a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tramite provider lato client in UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="fd304-111">Most Win32 controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="fd304-112">Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="fd304-112">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="fd304-113">Il supporto completo viene fornito solo per i controlli della versione 6 del *ComCtrl32.dll*.</span><span class="sxs-lookup"><span data-stu-id="fd304-113">Full support is provided only for controls from version 6 of *ComCtrl32.dll*.</span></span>  
  
 <span data-ttu-id="fd304-114">I controlli seguenti sono supportati.</span><span class="sxs-lookup"><span data-stu-id="fd304-114">The following controls are supported.</span></span>  
  
|<span data-ttu-id="fd304-115">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="fd304-115">Class name</span></span>|<span data-ttu-id="fd304-116">Tipo di controllo</span><span class="sxs-lookup"><span data-stu-id="fd304-116">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="fd304-117">Button</span><span class="sxs-lookup"><span data-stu-id="fd304-117">Button</span></span>|<span data-ttu-id="fd304-118">Button</span><span class="sxs-lookup"><span data-stu-id="fd304-118">Button</span></span>|  
|<span data-ttu-id="fd304-119">Button</span><span class="sxs-lookup"><span data-stu-id="fd304-119">Button</span></span>|<span data-ttu-id="fd304-120">RadioButton</span><span class="sxs-lookup"><span data-stu-id="fd304-120">RadioButton</span></span>|  
|<span data-ttu-id="fd304-121">Pulsante</span><span class="sxs-lookup"><span data-stu-id="fd304-121">Button</span></span>|<span data-ttu-id="fd304-122">Group</span><span class="sxs-lookup"><span data-stu-id="fd304-122">Group</span></span>|  
|<span data-ttu-id="fd304-123">Pulsante</span><span class="sxs-lookup"><span data-stu-id="fd304-123">Button</span></span>|<span data-ttu-id="fd304-124">CheckBox</span><span class="sxs-lookup"><span data-stu-id="fd304-124">CheckBox</span></span>|  
|<span data-ttu-id="fd304-125">Pulsante</span><span class="sxs-lookup"><span data-stu-id="fd304-125">Button</span></span>|<span data-ttu-id="fd304-126">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="fd304-126">Hyperlink</span></span>|  
|<span data-ttu-id="fd304-127">Pulsante</span><span class="sxs-lookup"><span data-stu-id="fd304-127">Button</span></span>|<span data-ttu-id="fd304-128">SplitButton</span><span class="sxs-lookup"><span data-stu-id="fd304-128">SplitButton</span></span>|  
|<span data-ttu-id="fd304-129">Pulsante</span><span class="sxs-lookup"><span data-stu-id="fd304-129">Button</span></span>|<span data-ttu-id="fd304-130">CheckBox</span><span class="sxs-lookup"><span data-stu-id="fd304-130">CheckBox</span></span>|  
|<span data-ttu-id="fd304-131">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="fd304-131">ComboBoxEx32</span></span>|<span data-ttu-id="fd304-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="fd304-132">ComboBox</span></span>|  
|<span data-ttu-id="fd304-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="fd304-133">ComboBox</span></span>|<span data-ttu-id="fd304-134">ComboBox</span><span class="sxs-lookup"><span data-stu-id="fd304-134">ComboBox</span></span>|  
|<span data-ttu-id="fd304-135">Modifica</span><span class="sxs-lookup"><span data-stu-id="fd304-135">Edit</span></span>|<span data-ttu-id="fd304-136">Document</span><span class="sxs-lookup"><span data-stu-id="fd304-136">Document</span></span>|  
|<span data-ttu-id="fd304-137">Modifica</span><span class="sxs-lookup"><span data-stu-id="fd304-137">Edit</span></span>|<span data-ttu-id="fd304-138">Modifica</span><span class="sxs-lookup"><span data-stu-id="fd304-138">Edit</span></span>|  
|<span data-ttu-id="fd304-139">SysLink</span><span class="sxs-lookup"><span data-stu-id="fd304-139">SysLink</span></span>|<span data-ttu-id="fd304-140">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="fd304-140">Hyperlink</span></span>|  
|<span data-ttu-id="fd304-141">Statico</span><span class="sxs-lookup"><span data-stu-id="fd304-141">Static</span></span>|<span data-ttu-id="fd304-142">Testo</span><span class="sxs-lookup"><span data-stu-id="fd304-142">Text</span></span>|  
|<span data-ttu-id="fd304-143">Statico</span><span class="sxs-lookup"><span data-stu-id="fd304-143">Static</span></span>|<span data-ttu-id="fd304-144">Immagine</span><span class="sxs-lookup"><span data-stu-id="fd304-144">Image</span></span>|  
|<span data-ttu-id="fd304-145">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="fd304-145">SysIPAddress32</span></span>|<span data-ttu-id="fd304-146">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="fd304-146">Custom</span></span>|  
|<span data-ttu-id="fd304-147">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="fd304-147">SysHeader32</span></span>|<span data-ttu-id="fd304-148">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="fd304-148">Header/HeaderItem</span></span>|  
|<span data-ttu-id="fd304-149">SysListView32</span><span class="sxs-lookup"><span data-stu-id="fd304-149">SysListView32</span></span>|<span data-ttu-id="fd304-150">DataGrid</span><span class="sxs-lookup"><span data-stu-id="fd304-150">DataGrid</span></span>|  
|<span data-ttu-id="fd304-151">SysListView32</span><span class="sxs-lookup"><span data-stu-id="fd304-151">SysListView32</span></span>|<span data-ttu-id="fd304-152">Elenco</span><span class="sxs-lookup"><span data-stu-id="fd304-152">List</span></span>|  
|<span data-ttu-id="fd304-153">ListBox</span><span class="sxs-lookup"><span data-stu-id="fd304-153">ListBox</span></span>|<span data-ttu-id="fd304-154">Elenco</span><span class="sxs-lookup"><span data-stu-id="fd304-154">List</span></span>|  
|<span data-ttu-id="fd304-155">ListBox</span><span class="sxs-lookup"><span data-stu-id="fd304-155">ListBox</span></span>|<span data-ttu-id="fd304-156">ListItem</span><span class="sxs-lookup"><span data-stu-id="fd304-156">ListItem</span></span>|  
|<span data-ttu-id="fd304-157">#32768</span><span class="sxs-lookup"><span data-stu-id="fd304-157">#32768</span></span>|<span data-ttu-id="fd304-158">Menu</span><span class="sxs-lookup"><span data-stu-id="fd304-158">Menu</span></span>|  
|<span data-ttu-id="fd304-159">#32768</span><span class="sxs-lookup"><span data-stu-id="fd304-159">#32768</span></span>|<span data-ttu-id="fd304-160">MenuItem</span><span class="sxs-lookup"><span data-stu-id="fd304-160">MenuItem</span></span>|  
|<span data-ttu-id="fd304-161">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="fd304-161">msctls_progress32</span></span>|<span data-ttu-id="fd304-162">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="fd304-162">ProgressBar</span></span>|  
|<span data-ttu-id="fd304-163">RichEdit</span><span class="sxs-lookup"><span data-stu-id="fd304-163">RichEdit</span></span>|<span data-ttu-id="fd304-164">Documento.</span><span class="sxs-lookup"><span data-stu-id="fd304-164">Document.</span></span> <span data-ttu-id="fd304-165">Vedere la nota.</span><span class="sxs-lookup"><span data-stu-id="fd304-165">See note.</span></span>|  
|<span data-ttu-id="fd304-166">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="fd304-166">RichEdit20A</span></span>|<span data-ttu-id="fd304-167">Document</span><span class="sxs-lookup"><span data-stu-id="fd304-167">Document</span></span>|  
|<span data-ttu-id="fd304-168">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="fd304-168">RichEdit20W</span></span>|<span data-ttu-id="fd304-169">Document</span><span class="sxs-lookup"><span data-stu-id="fd304-169">Document</span></span>|  
|<span data-ttu-id="fd304-170">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="fd304-170">RichEdit50W</span></span>|<span data-ttu-id="fd304-171">Document</span><span class="sxs-lookup"><span data-stu-id="fd304-171">Document</span></span>|  
|<span data-ttu-id="fd304-172">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="fd304-172">ScrollBar</span></span>|<span data-ttu-id="fd304-173">Dispositivo di scorrimento</span><span class="sxs-lookup"><span data-stu-id="fd304-173">Slider</span></span>|  
|<span data-ttu-id="fd304-174">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="fd304-174">msctls_trackbar32</span></span>|<span data-ttu-id="fd304-175">Dispositivo di scorrimento</span><span class="sxs-lookup"><span data-stu-id="fd304-175">Slider</span></span>|  
|<span data-ttu-id="fd304-176">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="fd304-176">msctls_updown32</span></span>|<span data-ttu-id="fd304-177">Spinner</span><span class="sxs-lookup"><span data-stu-id="fd304-177">Spinner</span></span>|  
|<span data-ttu-id="fd304-178">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="fd304-178">msctls_statusbar32</span></span>|<span data-ttu-id="fd304-179">StatusBar</span><span class="sxs-lookup"><span data-stu-id="fd304-179">StatusBar</span></span>|  
|<span data-ttu-id="fd304-180">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="fd304-180">SysTabControl32</span></span>|<span data-ttu-id="fd304-181">Scheda</span><span class="sxs-lookup"><span data-stu-id="fd304-181">Tab</span></span>|  
|<span data-ttu-id="fd304-182">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="fd304-182">SysTabControl32</span></span>|<span data-ttu-id="fd304-183">TabItem</span><span class="sxs-lookup"><span data-stu-id="fd304-183">TabItem</span></span>|  
|<span data-ttu-id="fd304-184">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="fd304-184">ToolbarWindow32</span></span>|<span data-ttu-id="fd304-185">ToolBar</span><span class="sxs-lookup"><span data-stu-id="fd304-185">ToolBar</span></span>|  
|<span data-ttu-id="fd304-186">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="fd304-186">ToolbarWindow32</span></span>|<span data-ttu-id="fd304-187">MenuItem</span><span class="sxs-lookup"><span data-stu-id="fd304-187">MenuItem</span></span>|  
|<span data-ttu-id="fd304-188">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="fd304-188">ToolbarWindow32</span></span>|<span data-ttu-id="fd304-189">Pulsante</span><span class="sxs-lookup"><span data-stu-id="fd304-189">Button</span></span>|  
|<span data-ttu-id="fd304-190">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="fd304-190">ToolbarWindow32</span></span>|<span data-ttu-id="fd304-191">CheckBox</span><span class="sxs-lookup"><span data-stu-id="fd304-191">CheckBox</span></span>|  
|<span data-ttu-id="fd304-192">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="fd304-192">ToolbarWindow32</span></span>|<span data-ttu-id="fd304-193">RadioButton</span><span class="sxs-lookup"><span data-stu-id="fd304-193">RadioButton</span></span>|  
|<span data-ttu-id="fd304-194">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="fd304-194">ToolbarWindow32</span></span>|<span data-ttu-id="fd304-195">Separatore</span><span class="sxs-lookup"><span data-stu-id="fd304-195">Separator</span></span>|  
|<span data-ttu-id="fd304-196">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="fd304-196">tooltips_class32</span></span>|<span data-ttu-id="fd304-197">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="fd304-197">ToolTip</span></span>|  
|<span data-ttu-id="fd304-198">#32774</span><span class="sxs-lookup"><span data-stu-id="fd304-198">#32774</span></span>|<span data-ttu-id="fd304-199">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="fd304-199">ToolTip</span></span>|  
|<span data-ttu-id="fd304-200">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="fd304-200">ReBarWindow32</span></span>|<span data-ttu-id="fd304-201">Barra degli strumenti</span><span class="sxs-lookup"><span data-stu-id="fd304-201">Toolbar</span></span>|  
|<span data-ttu-id="fd304-202">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="fd304-202">SysTreeView32</span></span>|<span data-ttu-id="fd304-203">Albero</span><span class="sxs-lookup"><span data-stu-id="fd304-203">Tree</span></span>|  
|<span data-ttu-id="fd304-204">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="fd304-204">SysTreeView32</span></span>|<span data-ttu-id="fd304-205">TreeItem</span><span class="sxs-lookup"><span data-stu-id="fd304-205">TreeItem</span></span>|  
  
 <span data-ttu-id="fd304-206">**Nota** Il controllo RichEdit è supportato solo per le versioni fornite con Windows Vista (in RichEd20.dll versione 3,1 e successive e MsftEdit.dll versione 4,1 e successive).</span><span class="sxs-lookup"><span data-stu-id="fd304-206">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="fd304-207">I controlli seguenti non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="fd304-207">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="fd304-208">Nome di classe</span><span class="sxs-lookup"><span data-stu-id="fd304-208">Class name</span></span>|<span data-ttu-id="fd304-209">Tipo di controllo</span><span class="sxs-lookup"><span data-stu-id="fd304-209">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="fd304-210">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="fd304-210">SysAnimate32</span></span>|<span data-ttu-id="fd304-211">Immagine</span><span class="sxs-lookup"><span data-stu-id="fd304-211">Image</span></span>|  
|<span data-ttu-id="fd304-212">SysPager</span><span class="sxs-lookup"><span data-stu-id="fd304-212">SysPager</span></span>|<span data-ttu-id="fd304-213">Spinner</span><span class="sxs-lookup"><span data-stu-id="fd304-213">Spinner</span></span>|  
|<span data-ttu-id="fd304-214">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="fd304-214">SysDateTimePick32</span></span>|<span data-ttu-id="fd304-215">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="fd304-215">Custom</span></span>|  
|<span data-ttu-id="fd304-216">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="fd304-216">SysMonthCal32</span></span>|<span data-ttu-id="fd304-217">Calendario</span><span class="sxs-lookup"><span data-stu-id="fd304-217">Calendar</span></span>|  
|<span data-ttu-id="fd304-218">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="fd304-218">MS_WINNOTE</span></span>|<span data-ttu-id="fd304-219">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="fd304-219">Tooltip</span></span>|  
|<span data-ttu-id="fd304-220">VBBubble</span><span class="sxs-lookup"><span data-stu-id="fd304-220">VBBubble</span></span>|<span data-ttu-id="fd304-221">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="fd304-221">Tooltip</span></span>|  
|<span data-ttu-id="fd304-222">ScrollBar (se usato come controllo autonomo)</span><span class="sxs-lookup"><span data-stu-id="fd304-222">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="fd304-223">Dispositivo di scorrimento</span><span class="sxs-lookup"><span data-stu-id="fd304-223">Slider</span></span>|  
|<span data-ttu-id="fd304-224">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="fd304-224">SuperGrid</span></span>|<span data-ttu-id="fd304-225">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="fd304-225">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>
## <a name="windows-forms-controls"></a><span data-ttu-id="fd304-226">Controlli per Windows Form</span><span class="sxs-lookup"><span data-stu-id="fd304-226">Windows Forms Controls</span></span>  
 <span data-ttu-id="fd304-227">Windows Forms controlli sono esposti a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tramite provider lato client in UIAutomationClientsideProviders.dll.</span><span class="sxs-lookup"><span data-stu-id="fd304-227">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="fd304-228">Questo assembly viene automaticamente registrato per l'uso con applicazioni client di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="fd304-228">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="fd304-229">In genere, Windows Forms controlli che sono wrapper gestiti per i controlli comuni Win32 sono supportati da [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fd304-229">Typically, Windows Forms controls that are managed wrappers for Win32 common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="fd304-230">I controlli seguenti sono supportati.</span><span class="sxs-lookup"><span data-stu-id="fd304-230">The following controls are supported.</span></span>  
  
|<span data-ttu-id="fd304-231">Nome della classe</span><span class="sxs-lookup"><span data-stu-id="fd304-231">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="fd304-232">Pulsante</span><span class="sxs-lookup"><span data-stu-id="fd304-232">Button</span></span>|  
|<span data-ttu-id="fd304-233">CheckBox</span><span class="sxs-lookup"><span data-stu-id="fd304-233">CheckBox</span></span>|  
|<span data-ttu-id="fd304-234">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="fd304-234">CheckedListBox</span></span>|  
|<span data-ttu-id="fd304-235">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="fd304-235">ColorDialog</span></span>|  
|<span data-ttu-id="fd304-236">ComboBox</span><span class="sxs-lookup"><span data-stu-id="fd304-236">ComboBox</span></span>|  
|<span data-ttu-id="fd304-237">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="fd304-237">FolderBrowser</span></span>|  
|<span data-ttu-id="fd304-238">FontDialog</span><span class="sxs-lookup"><span data-stu-id="fd304-238">FontDialog</span></span>|  
|<span data-ttu-id="fd304-239">GroupBox</span><span class="sxs-lookup"><span data-stu-id="fd304-239">GroupBox</span></span>|  
|<span data-ttu-id="fd304-240">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="fd304-240">HscrollBar</span></span>|  
|<span data-ttu-id="fd304-241">ImageList</span><span class="sxs-lookup"><span data-stu-id="fd304-241">ImageList</span></span>|  
|<span data-ttu-id="fd304-242">Label</span><span class="sxs-lookup"><span data-stu-id="fd304-242">Label</span></span>|  
|<span data-ttu-id="fd304-243">ListBox</span><span class="sxs-lookup"><span data-stu-id="fd304-243">ListBox</span></span>|  
|<span data-ttu-id="fd304-244">ListView</span><span class="sxs-lookup"><span data-stu-id="fd304-244">ListView</span></span>|  
|<span data-ttu-id="fd304-245">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="fd304-245">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="fd304-246">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="fd304-246">MonthCalendar</span></span>|  
|<span data-ttu-id="fd304-247">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="fd304-247">NotifyIcon</span></span>|  
|<span data-ttu-id="fd304-248">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="fd304-248">OpenFileDialog</span></span>|  
|<span data-ttu-id="fd304-249">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="fd304-249">PageSetupDialog</span></span>|  
|<span data-ttu-id="fd304-250">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="fd304-250">PrintDialog</span></span>|  
|<span data-ttu-id="fd304-251">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="fd304-251">ProgressBar</span></span>|  
|<span data-ttu-id="fd304-252">RadioButton</span><span class="sxs-lookup"><span data-stu-id="fd304-252">RadioButton</span></span>|  
|<span data-ttu-id="fd304-253">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="fd304-253">RichTextBox</span></span>|  
|<span data-ttu-id="fd304-254">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="fd304-254">SaveFileDialog</span></span>|  
|<span data-ttu-id="fd304-255">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="fd304-255">ScrollableControl</span></span>|  
|<span data-ttu-id="fd304-256">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="fd304-256">SoundPlayer</span></span>|  
|<span data-ttu-id="fd304-257">StatusBar</span><span class="sxs-lookup"><span data-stu-id="fd304-257">StatusBar</span></span>|  
|<span data-ttu-id="fd304-258">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="fd304-258">TabControl/TabPage</span></span>|  
|<span data-ttu-id="fd304-259">TextBox</span><span class="sxs-lookup"><span data-stu-id="fd304-259">TextBox</span></span>|  
|<span data-ttu-id="fd304-260">Timer</span><span class="sxs-lookup"><span data-stu-id="fd304-260">Timer</span></span>|  
|<span data-ttu-id="fd304-261">Barra degli strumenti</span><span class="sxs-lookup"><span data-stu-id="fd304-261">Toolbar</span></span>|  
|<span data-ttu-id="fd304-262">Descrizione comando</span><span class="sxs-lookup"><span data-stu-id="fd304-262">ToolTip</span></span>|  
|<span data-ttu-id="fd304-263">Trackbar</span><span class="sxs-lookup"><span data-stu-id="fd304-263">TrackBar</span></span>|  
|<span data-ttu-id="fd304-264">TreeView</span><span class="sxs-lookup"><span data-stu-id="fd304-264">TreeView</span></span>|  
|<span data-ttu-id="fd304-265">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="fd304-265">VscrollBar</span></span>|  
|<span data-ttu-id="fd304-266">WebBrowser</span><span class="sxs-lookup"><span data-stu-id="fd304-266">WebBrowser</span></span>|  
  
 <span data-ttu-id="fd304-267">I controlli seguenti sono esposti a [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] solo tramite il supporto di Microsoft Active Accessibility.</span><span class="sxs-lookup"><span data-stu-id="fd304-267">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="fd304-268">Alcune funzionalità potrebbero non essere disponibili.</span><span class="sxs-lookup"><span data-stu-id="fd304-268">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="fd304-269">Nome del controllo</span><span class="sxs-lookup"><span data-stu-id="fd304-269">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="fd304-270">BindingSource</span><span class="sxs-lookup"><span data-stu-id="fd304-270">BindingSource</span></span>|  
|<span data-ttu-id="fd304-271">DataGrid</span><span class="sxs-lookup"><span data-stu-id="fd304-271">DataGrid</span></span>|  
|<span data-ttu-id="fd304-272">DataGridView</span><span class="sxs-lookup"><span data-stu-id="fd304-272">DataGridView</span></span>|  
|<span data-ttu-id="fd304-273">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="fd304-273">DataNavigator</span></span>|  
|<span data-ttu-id="fd304-274">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="fd304-274">DomainUpDown</span></span>|  
|<span data-ttu-id="fd304-275">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="fd304-275">ErrorProvider</span></span>|  
|<span data-ttu-id="fd304-276">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="fd304-276">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="fd304-277">Form</span><span class="sxs-lookup"><span data-stu-id="fd304-277">Form</span></span>|  
|<span data-ttu-id="fd304-278">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="fd304-278">LinkLabel</span></span>|  
|<span data-ttu-id="fd304-279">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="fd304-279">HelpProvider</span></span>|  
|<span data-ttu-id="fd304-280">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="fd304-280">MaskedTextBox</span></span>|  
|<span data-ttu-id="fd304-281">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="fd304-281">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="fd304-282">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="fd304-282">NumericUpDown</span></span>|  
|<span data-ttu-id="fd304-283">Panel</span><span class="sxs-lookup"><span data-stu-id="fd304-283">Panel</span></span>|  
|<span data-ttu-id="fd304-284">PictureBox</span><span class="sxs-lookup"><span data-stu-id="fd304-284">PictureBox</span></span>|  
|<span data-ttu-id="fd304-285">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="fd304-285">PrintDocument</span></span>|  
|<span data-ttu-id="fd304-286">PrintPreviewControl</span><span class="sxs-lookup"><span data-stu-id="fd304-286">PrintPreview-Control</span></span>|  
|<span data-ttu-id="fd304-287">PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="fd304-287">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="fd304-288">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="fd304-288">PropertyGrid</span></span>|  
|<span data-ttu-id="fd304-289">UserControl</span><span class="sxs-lookup"><span data-stu-id="fd304-289">UserControl</span></span>|  
|<span data-ttu-id="fd304-290">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="fd304-290">ToolStrip</span></span>|  
|<span data-ttu-id="fd304-291">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="fd304-291">TableLayoutPanel</span></span>|  
|<span data-ttu-id="fd304-292">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="fd304-292">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="fd304-293">Splitter</span><span class="sxs-lookup"><span data-stu-id="fd304-293">Splitter</span></span>|  
|<span data-ttu-id="fd304-294">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="fd304-294">RaftingContainer</span></span>|  
|<span data-ttu-id="fd304-295">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="fd304-295">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fd304-296">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd304-296">See also</span></span>

- [<span data-ttu-id="fd304-297">Tipi di controllo per l'automazione dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="fd304-297">UI Automation Control Types</span></span>](ui-automation-control-types.md)
