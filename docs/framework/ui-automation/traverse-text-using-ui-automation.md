---
title: Scorrere il testo utilizzando automazione interfaccia utente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, traversing text
- text, traversing
- traversing text
ms.assetid: 3ddb3b7b-1d6b-4dba-8678-5a68e868aadb
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 7353ad142bb276cde1c6fb0ff0c6dcf03b699aeb
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44217022"
---
# <a name="traverse-text-using-ui-automation"></a><span data-ttu-id="fe566-102">Scorrere il testo utilizzando automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="fe566-102">Traverse Text Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="fe566-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="fe566-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="fe566-104">Per informazioni aggiornate sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione dell'interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="fe566-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="fe566-105">In questo argomento viene illustrato come usare [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] per scorrere il contenuto testuale di un documento in base a incrementi definiti da <xref:System.Windows.Automation.Text.TextUnit> .</span><span class="sxs-lookup"><span data-stu-id="fe566-105">This topic shows how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to traverse the textual content of a document by <xref:System.Windows.Automation.Text.TextUnit> increments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe566-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="fe566-106">Example</span></span>  
 <span data-ttu-id="fe566-107">L'esempio di codice seguente illustra come scorrere il contenuto di un provider di testo di automazione interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="fe566-107">The following code example demonstrates how to traverse the content of a UI Automation text provider.</span></span> <span data-ttu-id="fe566-108">Il metodo <xref:System.Windows.Automation.Text.TextPatternRange.Move%2A> sposta gli endpoint <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.Start> e <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.End> di una classe <xref:System.Windows.Automation.Text.TextPatternRange>.</span><span class="sxs-lookup"><span data-stu-id="fe566-108">The <xref:System.Windows.Automation.Text.TextPatternRange.Move%2A> method moves the <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.Start> and <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint.End> endpoints of a <xref:System.Windows.Automation.Text.TextPatternRange>.</span></span> <span data-ttu-id="fe566-109">Questo intervallo di testo è in genere un intervallo degenere che rappresenta il punto di inserimento.</span><span class="sxs-lookup"><span data-stu-id="fe566-109">This text range is typically a degenerate range representing the text insertion point.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe566-110">Poiché solo gli oggetti incorporati basati su testo sono considerati parte del flusso di testo, gli oggetti incorporati, ad esempio le immagini, non interessano `Move` o il relativo valore restituito.</span><span class="sxs-lookup"><span data-stu-id="fe566-110">Since only text-based embedded objects are considered part of the text stream, embedded objects such as images do not affect `Move` or its return value.</span></span>  
  
 [!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
 [!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#Navigate](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#navigate)]
[!code-vb[FindText#Navigate](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#navigate)]  
  
 <span data-ttu-id="fe566-111">Qualsiasi metodo che usa <xref:System.Windows.Automation.Text.TextUnit> rinvia al successivo valore più grande di <xref:System.Windows.Automation.Text.TextUnit> supportato se il valore specificato di <xref:System.Windows.Automation.Text.TextUnit> non è supportato dal controllo.</span><span class="sxs-lookup"><span data-stu-id="fe566-111">Any method using <xref:System.Windows.Automation.Text.TextUnit> will defer to the next largest <xref:System.Windows.Automation.Text.TextUnit> supported if the given <xref:System.Windows.Automation.Text.TextUnit> is not supported by the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe566-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe566-112">See Also</span></span>  
 [<span data-ttu-id="fe566-113">Panoramica di TextPattern di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="fe566-113">UI Automation TextPattern Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-textpattern-overview.md)  
 [<span data-ttu-id="fe566-114">Aggiungere contenuto a una casella di testo usando l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="fe566-114">Add Content to a Text Box Using UI Automation</span></span>](../../../docs/framework/ui-automation/add-content-to-a-text-box-using-ui-automation.md)  
 [<span data-ttu-id="fe566-115">Trovare ed evidenziare il testo usando l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="fe566-115">Find and Highlight Text Using UI Automation</span></span>](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)  
 [<span data-ttu-id="fe566-116">Panoramica dei pattern di controllo per l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="fe566-116">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="fe566-117">Pattern di controllo di automazione interfaccia utente per i client</span><span class="sxs-lookup"><span data-stu-id="fe566-117">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
