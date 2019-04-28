---
title: 'Procedura: Regolare la spaziatura tra i paragrafi'
ms.date: 03/30/2017
helpviewer_keywords:
- spacing between paragraphs [WPF]
- paragraphs [WPF], spacing between
- documents [WPF], adjusting spacing between paragraphs
ms.assetid: 7cd2f2ac-0e19-4587-bfb6-7f5b18c9536e
ms.openlocfilehash: e2a6ba34e3ab15eb316671fef7c11bea03d53c73
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777013"
---
# <a name="how-to-adjust-spacing-between-paragraphs"></a><span data-ttu-id="4bf27-102">Procedura: Regolare la spaziatura tra i paragrafi</span><span class="sxs-lookup"><span data-stu-id="4bf27-102">How to: Adjust Spacing Between Paragraphs</span></span>
<span data-ttu-id="4bf27-103">In questo esempio viene illustrato come modificare o eliminare la spaziatura tra paragrafi nel contenuto dinamico.</span><span class="sxs-lookup"><span data-stu-id="4bf27-103">This example shows how to adjust or eliminate spacing between paragraphs in flow content.</span></span>  
  
 <span data-ttu-id="4bf27-104">Nel contenuto dinamico, lo spazio aggiuntivo che viene visualizzato tra i paragrafi è il risultato dei margini impostati per queste paragrafi. di conseguenza, la spaziatura tra paragrafi può essere controllata regolando i margini in paragrafi.</span><span class="sxs-lookup"><span data-stu-id="4bf27-104">In flow content, extra space that appears between paragraphs is the result of margins set on these paragraphs; thus, the spacing between paragraphs can be controlled by adjusting the margins on those paragraphs.</span></span>  <span data-ttu-id="4bf27-105">Per eliminare completamente la spaziatura aggiuntiva tra due paragrafi, impostare i margini di paragrafi vengano **0**.</span><span class="sxs-lookup"><span data-stu-id="4bf27-105">To eliminate extra spacing between two paragraphs altogether, set the margins for the paragraphs to **0**.</span></span>  <span data-ttu-id="4bf27-106">Per ottenere la spaziatura uniforme tra i paragrafi di un intero <xref:System.Windows.Documents.FlowDocument>, applicare uno stile per impostare un valore di un margine uniforme per tutti i paragrafi di <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="4bf27-106">To achieve uniform spacing between paragraphs throughout an entire <xref:System.Windows.Documents.FlowDocument>, use styling to set a uniform margin value for all paragraphs in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 <span data-ttu-id="4bf27-107">È importante notare che i margini per due paragrafi adiacenti "comprimerà" per il valore più grande tra i due margini, anziché raddoppiati.</span><span class="sxs-lookup"><span data-stu-id="4bf27-107">It is important to note that the margins for two adjacent paragraphs will "collapse" to the larger of the two margins, rather than doubling up.</span></span> <span data-ttu-id="4bf27-108">Pertanto, se due paragrafi adiacenti presentano il margine di 20 e 40 pixel rispettivamente, lo spazio tra i paragrafi 40 pixel, il più elevato tra i valori per i due margini.</span><span class="sxs-lookup"><span data-stu-id="4bf27-108">So, if two adjacent paragraphs have margins of 20 pixels and 40 pixels respectively, the resulting space between the paragraphs is 40 pixels, the larger of the two margin values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4bf27-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="4bf27-109">Example</span></span>  
 <span data-ttu-id="4bf27-110">L'esempio seguente usa lo stile per impostare il margine per tutti <xref:System.Windows.Documents.Paragraph> elementi in un <xref:System.Windows.Documents.FlowDocument> al **0**, che elimina in modo efficace la spaziatura tra paragrafi nel <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="4bf27-110">The following example uses styling to set the margin for all <xref:System.Windows.Documents.Paragraph> elements in a <xref:System.Windows.Documents.FlowDocument> to **0**, which effectively eliminates extra spacing between paragraphs in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-xaml[BlockSnippets#_ParagraphSpacingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/BlockSnippets/CSharp/Window1.xaml#_paragraphspacingxaml)]
