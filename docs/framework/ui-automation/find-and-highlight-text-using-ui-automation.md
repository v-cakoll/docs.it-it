---
title: Trovare ed evidenziare il testo utilizzando l'automazione interfaccia utente
description: Trovare ed evidenziare il testo usando l'automazione interfaccia utente. Un esempio cerca in modo sequenziale ed evidenzia ogni occorrenza di una stringa all'interno del contenuto del controllo di testo.
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
ms.openlocfilehash: e4aca4b5ccdbc429a3d6267afc09b9f8b99cd7e9
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164195"
---
# <a name="find-and-highlight-text-using-ui-automation"></a><span data-ttu-id="c1911-104">Trovare ed evidenziare il testo utilizzando l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="c1911-104">Find and Highlight Text Using UI Automation</span></span>
> [!NOTE]
> <span data-ttu-id="c1911-105">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="c1911-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="c1911-106">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="c1911-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="c1911-107">In questo argomento viene illustrato come eseguire una ricerca sequenziale ed evidenziare ogni occorrenza di una stringa all'interno del contenuto di un controllo di testo utilizzando [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c1911-107">This topic demonstrates how to sequentially search for and highlight each occurrence of a string within the content of a text control using [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1911-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="c1911-108">Example</span></span>  
 <span data-ttu-id="c1911-109">Nell'esempio seguente viene ottenuto un <xref:System.Windows.Automation.TextPattern> oggetto da un controllo di testo.</span><span class="sxs-lookup"><span data-stu-id="c1911-109">The following example obtains a <xref:System.Windows.Automation.TextPattern> object from a text control.</span></span> <span data-ttu-id="c1911-110">Un <xref:System.Windows.Automation.Text.TextPatternRange> oggetto che rappresenta il contenuto testuale dell'intero documento viene quindi creato utilizzando la <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> proprietà dell'oggetto <xref:System.Windows.Automation.TextPattern> .</span><span class="sxs-lookup"><span data-stu-id="c1911-110">A <xref:System.Windows.Automation.Text.TextPatternRange> object, representing the textual content of the entire document, is then created using the <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> property of this <xref:System.Windows.Automation.TextPattern>.</span></span> <span data-ttu-id="c1911-111"><xref:System.Windows.Automation.Text.TextPatternRange>Vengono quindi creati due oggetti aggiuntivi per la funzionalità di ricerca sequenziale e di evidenziazione.</span><span class="sxs-lookup"><span data-stu-id="c1911-111">Two additional <xref:System.Windows.Automation.Text.TextPatternRange> objects are then created for the sequential search and highlight functionality.</span></span>  
  
[!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
[!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#SearchTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#searchtarget)]
[!code-vb[FindText#SearchTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#searchtarget)]  
  
## <a name="see-also"></a><span data-ttu-id="c1911-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1911-112">See also</span></span>

- [<span data-ttu-id="c1911-113">Trovare ed evidenziare il testo utilizzando l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="c1911-113">Find and Highlight Text Using UI Automation</span></span>](find-and-highlight-text-using-ui-automation.md)
