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
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 2fe7ecd84c6b88e6ccc81188235a6735b926a04b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401086"
---
# <a name="find-and-highlight-text-using-ui-automation"></a><span data-ttu-id="8a142-102">Trovare ed evidenziare il testo utilizzando l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="8a142-102">Find and Highlight Text Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="8a142-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="8a142-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="8a142-104">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere l'argomento sull' [API Automazione interfaccia utente di Windows](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="8a142-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="8a142-105">In questo argomento viene illustrato come sequenza cercare ed evidenziare ogni occorrenza di una stringa all'interno del contenuto di un controllo di testo utilizzando [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8a142-105">This topic demonstrates how to sequentially search for and highlight each occurrence of a string within the content of a text control using [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a142-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="8a142-106">Example</span></span>  
 <span data-ttu-id="8a142-107">Nell'esempio seguente viene ottenuto un <xref:System.Windows.Automation.TextPattern> oggetto da un controllo testo.</span><span class="sxs-lookup"><span data-stu-id="8a142-107">The following example obtains a <xref:System.Windows.Automation.TextPattern> object from a text control.</span></span> <span data-ttu-id="8a142-108">Oggetto <xref:System.Windows.Automation.Text.TextPatternRange> oggetto che rappresenta il contenuto testuale dell'intero documento, viene quindi creata utilizzando il <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> proprietà di questo <xref:System.Windows.Automation.TextPattern>.</span><span class="sxs-lookup"><span data-stu-id="8a142-108">A <xref:System.Windows.Automation.Text.TextPatternRange> object, representing the textual content of the entire document, is then created using the <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> property of this <xref:System.Windows.Automation.TextPattern>.</span></span> <span data-ttu-id="8a142-109">Altri due <xref:System.Windows.Automation.Text.TextPatternRange> gli oggetti vengono quindi creati per la ricerca sequenza ed evidenziare la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="8a142-109">Two additional <xref:System.Windows.Automation.Text.TextPatternRange> objects are then created for the sequential search and highlight functionality.</span></span>  
  
 [!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
 [!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#SearchTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#searchtarget)]
[!code-vb[FindText#SearchTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#searchtarget)]  
  
## <a name="see-also"></a><span data-ttu-id="8a142-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a142-110">See Also</span></span>  
 [<span data-ttu-id="8a142-111">Trovare ed evidenziare il testo usando l'automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="8a142-111">Find and Highlight Text Using UI Automation</span></span>](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)
