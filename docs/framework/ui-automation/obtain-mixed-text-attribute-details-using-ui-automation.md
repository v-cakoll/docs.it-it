---
title: Ottenere dettagli sugli attributi di testo misti utilizzando l'automazione interfaccia utente
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
ms.assetid: d0e4c005-abd1-42bb-92a4-5faf87097311
caps.latest.revision: "11"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 0588ec764aabf5aa0e88477838d949a294f3064e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="obtain-mixed-text-attribute-details-using-ui-automation"></a><span data-ttu-id="b55c5-102">Ottenere dettagli sugli attributi di testo misti utilizzando l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="b55c5-102">Obtain Mixed Text Attribute Details Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="b55c5-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="b55c5-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="b55c5-104">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="b55c5-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="b55c5-105">In questo argomento viene illustrato come usare [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] per ottenere dettagli sugli attributi di testo da un intervallo di testo che si estende su più valori di attributo.</span><span class="sxs-lookup"><span data-stu-id="b55c5-105">This topic shows how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to obtain text attribute details from a text range that spans multiple attribute values.</span></span> <span data-ttu-id="b55c5-106">Un intervallo di testo può corrispondere alla posizione corrente del punto di inserimento (o selezione degenere) all'interno di un documento, una selezione contigua di testo, un insieme di selezioni di testo non contigue o l'intero contenuto testuale di un documento.</span><span class="sxs-lookup"><span data-stu-id="b55c5-106">A text range can correspond to the current location of the caret (or degenerate selection) within a document, a contiguous selection of text, a collection of disjoint text selections, or the entire textual content of a document.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b55c5-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="b55c5-107">Example</span></span>  
 <span data-ttu-id="b55c5-108">Nell'esempio di codice seguente viene illustrato come ottenere <xref:System.Windows.Automation.TextPattern.FontNameAttribute> da un intervallo di testo, dove <xref:System.Windows.Automation.Text.TextPatternRange.GetAttributeValue%2A> restituisce un oggetto <xref:System.Windows.Automation.TextPattern.MixedAttributeValue> .</span><span class="sxs-lookup"><span data-stu-id="b55c5-108">The following code example demonstrates how to obtain the <xref:System.Windows.Automation.TextPattern.FontNameAttribute> from a text range where <xref:System.Windows.Automation.Text.TextPatternRange.GetAttributeValue%2A> returns a <xref:System.Windows.Automation.TextPattern.MixedAttributeValue> object.</span></span>  
  
 [!code-csharp[FindText#RetrieveMixedAttributes](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#retrievemixedattributes)]
 [!code-vb[FindText#RetrieveMixedAttributes](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#retrievemixedattributes)]  
  
 <span data-ttu-id="b55c5-109">Il pattern di controllo <xref:System.Windows.Automation.TextPattern> , in combinazione con la classe <xref:System.Windows.Automation.Text.TextPatternRange> , supporta gli attributi, le proprietà e i metodi di base del testo.</span><span class="sxs-lookup"><span data-stu-id="b55c5-109">The <xref:System.Windows.Automation.TextPattern> control pattern, in tandem with the <xref:System.Windows.Automation.Text.TextPatternRange> class, supports basic text attributes, properties, and methods.</span></span> <span data-ttu-id="b55c5-110">Per la funzionalità specifica del controllo non supportata da <xref:System.Windows.Automation.TextPattern> o <xref:System.Windows.Automation.Text.TextPatternRange>, la classe <xref:System.Windows.Automation.AutomationElement> implementa metodi per un client di automazione interfaccia utente per accedere al corrispondente modello a oggetti nativo.</span><span class="sxs-lookup"><span data-stu-id="b55c5-110">For control-specific functionality that is not supported by <xref:System.Windows.Automation.TextPattern> or <xref:System.Windows.Automation.Text.TextPatternRange>, the <xref:System.Windows.Automation.AutomationElement> class provides methods for a UI Automation client to access the corresponding native object model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b55c5-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b55c5-111">See Also</span></span>  
 [<span data-ttu-id="b55c5-112">Panoramica di TextPattern di automazione dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="b55c5-112">UI Automation TextPattern Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-textpattern-overview.md)  
 [<span data-ttu-id="b55c5-113">Aggiungere contenuto a una casella di testo utilizzando automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="b55c5-113">Add Content to a Text Box Using UI Automation</span></span>](../../../docs/framework/ui-automation/add-content-to-a-text-box-using-ui-automation.md)  
 [<span data-ttu-id="b55c5-114">Trovare ed evidenziare il testo utilizzando automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="b55c5-114">Find and Highlight Text Using UI Automation</span></span>](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)  
 [<span data-ttu-id="b55c5-115">Cenni preliminari sui pattern di controllo automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="b55c5-115">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="b55c5-116">Pattern di controllo di automazione interfaccia utente per i client</span><span class="sxs-lookup"><span data-stu-id="b55c5-116">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="b55c5-117">Ottenere attributi di testo utilizzando automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="b55c5-117">Obtain Text Attributes Using UI Automation</span></span>](../../../docs/framework/ui-automation/obtain-text-attributes-using-ui-automation.md)
