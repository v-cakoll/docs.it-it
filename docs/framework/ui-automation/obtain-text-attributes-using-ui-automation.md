---
title: Ottenere attributi di testo mediante l'automazione interfaccia utente
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting, text attributes
- UI Automation, getting text attributes
- text attributes, getting
ms.assetid: fdefc6c3-b836-4cfe-8dec-1484bfdc5551
caps.latest.revision: "13"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 099ce10a5c0f05e95652f3d384628d4d2fac8208
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="obtain-text-attributes-using-ui-automation"></a><span data-ttu-id="2c654-102">Ottenere attributi di testo mediante l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="2c654-102">Obtain Text Attributes Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="2c654-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="2c654-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="2c654-104">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere l'argomento sull' [API Automazione interfaccia utente di Windows](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="2c654-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="2c654-105">In questo argomento viene illustrato come usare [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] per ottenere gli attributi di testo da un intervallo di testo.</span><span class="sxs-lookup"><span data-stu-id="2c654-105">This topic shows how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to obtain text attributes from a text range.</span></span> <span data-ttu-id="2c654-106">Un intervallo di testo può corrispondere alla posizione corrente del punto di inserimento (o selezione degenere) all'interno di un documento, una selezione contigua di testo, un insieme di selezioni di testo non contigue o l'intero contenuto testuale di un documento.</span><span class="sxs-lookup"><span data-stu-id="2c654-106">A text range can correspond to the current location of the caret (or degenerate selection) within a document, a contiguous selection of text, a collection of disjoint text selections, or the entire textual content of a document.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c654-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="2c654-107">Example</span></span>  
 <span data-ttu-id="2c654-108">Nell'esempio di codice seguente viene illustrato come ottenere <xref:System.Windows.Automation.TextPattern.FontNameAttribute> da un intervallo di testo.</span><span class="sxs-lookup"><span data-stu-id="2c654-108">The following code example demonstrates how to obtain the <xref:System.Windows.Automation.TextPattern.FontNameAttribute> from a text range.</span></span>  
  
 [!code-csharp[UIATextPattern_snip#StartTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#starttarget)]
 [!code-vb[UIATextPattern_snip#StartTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#starttarget)]  
[!code-csharp[UIATextPattern_snip#GetTextElement](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#gettextelement)]
[!code-vb[UIATextPattern_snip#GetTextElement](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#gettextelement)]  
[!code-csharp[UIATextPattern_snip#FontName](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#fontname)]
[!code-vb[UIATextPattern_snip#FontName](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#fontname)]  
  
 <span data-ttu-id="2c654-109">Il pattern di controllo <xref:System.Windows.Automation.TextPattern> , in combinazione con la classe <xref:System.Windows.Automation.Text.TextPatternRange> , supporta gli attributi, le proprietà e i metodi di base del testo.</span><span class="sxs-lookup"><span data-stu-id="2c654-109">The <xref:System.Windows.Automation.TextPattern> control pattern, in tandem with the <xref:System.Windows.Automation.Text.TextPatternRange> class, supports basic text attributes, properties, and methods.</span></span> <span data-ttu-id="2c654-110">Per la funzionalità specifica del controllo non supportata da <xref:System.Windows.Automation.TextPattern> o <xref:System.Windows.Automation.Text.TextPatternRange> , la classe <xref:System.Windows.Automation.AutomationElement>implementa metodi per un client di automazione interfaccia utente per accedere al corrispondente modello a oggetti nativo.</span><span class="sxs-lookup"><span data-stu-id="2c654-110">For control-specific functionality that is not supported by <xref:System.Windows.Automation.TextPattern> or <xref:System.Windows.Automation.Text.TextPatternRange> the <xref:System.Windows.Automation.AutomationElement>, class provides methods for a UI Automation client to access the corresponding native object model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c654-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c654-111">See Also</span></span>  
 [<span data-ttu-id="2c654-112">Panoramica di TextPattern di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="2c654-112">UI Automation TextPattern Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-textpattern-overview.md)  
 [<span data-ttu-id="2c654-113">Aggiungere contenuto a una casella di testo usando l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="2c654-113">Add Content to a Text Box Using UI Automation</span></span>](../../../docs/framework/ui-automation/add-content-to-a-text-box-using-ui-automation.md)  
 [<span data-ttu-id="2c654-114">Trovare ed evidenziare il testo usando l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="2c654-114">Find and Highlight Text Using UI Automation</span></span>](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)  
 [<span data-ttu-id="2c654-115">Panoramica dei pattern di controllo per l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="2c654-115">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="2c654-116">Pattern di controllo di automazione interfaccia utente per i client</span><span class="sxs-lookup"><span data-stu-id="2c654-116">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="2c654-117">Ottenere dettagli sugli attributi di testo misti usando l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="2c654-117">Obtain Mixed Text Attribute Details Using UI Automation</span></span>](../../../docs/framework/ui-automation/obtain-mixed-text-attribute-details-using-ui-automation.md)
