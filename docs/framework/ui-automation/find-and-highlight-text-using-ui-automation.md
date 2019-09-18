---
title: Trovare ed evidenziare il testo utilizzando l'automazione interfaccia utente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text, highlighting
- finding text
- text, finding
- UI automation, highlighting text
- UI automation, finding text
- highlighting text
ms.assetid: b77693f5-87bb-4b29-a297-05ff882e2044
ms.openlocfilehash: 084a9cdeaf17d7456116c56e9a12115b478f7384
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71043633"
---
# <a name="find-and-highlight-text-using-ui-automation"></a><span data-ttu-id="c6746-102">Trovare ed evidenziare il testo utilizzando l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="c6746-102">Find and Highlight Text Using UI Automation</span></span>
> [!NOTE]
> <span data-ttu-id="c6746-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="c6746-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="c6746-104">Per informazioni aggiornate su, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]vedere [API di automazione di Windows: Automazione](https://go.microsoft.com/fwlink/?LinkID=156746)interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="c6746-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="c6746-105">In questo argomento viene illustrato come eseguire una ricerca sequenziale ed evidenziare ogni occorrenza di una stringa all'interno del contenuto di [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]un controllo di testo utilizzando.</span><span class="sxs-lookup"><span data-stu-id="c6746-105">This topic demonstrates how to sequentially search for and highlight each occurrence of a string within the content of a text control using [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6746-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="c6746-106">Example</span></span>  
 <span data-ttu-id="c6746-107">Nell'esempio seguente viene ottenuto un <xref:System.Windows.Automation.TextPattern> oggetto da un controllo di testo.</span><span class="sxs-lookup"><span data-stu-id="c6746-107">The following example obtains a <xref:System.Windows.Automation.TextPattern> object from a text control.</span></span> <span data-ttu-id="c6746-108">Un <xref:System.Windows.Automation.Text.TextPatternRange> oggetto che rappresenta il contenuto testuale dell'intero documento viene quindi creato utilizzando la <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> proprietà dell' <xref:System.Windows.Automation.TextPattern>oggetto.</span><span class="sxs-lookup"><span data-stu-id="c6746-108">A <xref:System.Windows.Automation.Text.TextPatternRange> object, representing the textual content of the entire document, is then created using the <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> property of this <xref:System.Windows.Automation.TextPattern>.</span></span> <span data-ttu-id="c6746-109">Vengono quindi <xref:System.Windows.Automation.Text.TextPatternRange> creati due oggetti aggiuntivi per la funzionalità di ricerca sequenziale e di evidenziazione.</span><span class="sxs-lookup"><span data-stu-id="c6746-109">Two additional <xref:System.Windows.Automation.Text.TextPatternRange> objects are then created for the sequential search and highlight functionality.</span></span>  
  
[!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
[!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#SearchTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#searchtarget)]
[!code-vb[FindText#SearchTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#searchtarget)]  
  
## <a name="see-also"></a><span data-ttu-id="c6746-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6746-110">See also</span></span>

- [<span data-ttu-id="c6746-111">Trovare ed evidenziare il testo usando l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="c6746-111">Find and Highlight Text Using UI Automation</span></span>](find-and-highlight-text-using-ui-automation.md)
