---
title: 'Procedura: regolare la spaziatura tra paragrafi'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- spacing between paragraphs [WPF]
- paragraphs [WPF], spacing between
- documents [WPF], adjusting spacing between paragraphs
ms.assetid: 7cd2f2ac-0e19-4587-bfb6-7f5b18c9536e
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8b2d02e1513a0d8a3c31e4a13c9599666a4122a3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-adjust-spacing-between-paragraphs"></a><span data-ttu-id="bfea4-102">Procedura: regolare la spaziatura tra paragrafi</span><span class="sxs-lookup"><span data-stu-id="bfea4-102">How to: Adjust Spacing Between Paragraphs</span></span>
<span data-ttu-id="bfea4-103">In questo esempio viene illustrato come modificare o eliminare la spaziatura tra i paragrafi nel contenuto del flusso.</span><span class="sxs-lookup"><span data-stu-id="bfea4-103">This example shows how to adjust or eliminate spacing between paragraphs in flow content.</span></span>  
  
 <span data-ttu-id="bfea4-104">Nel contenuto del flusso, lo spazio aggiuntivo che viene visualizzato tra i paragrafi è il risultato dei margini impostati per tali paragrafi. di conseguenza, è possibile controllare la spaziatura tra i paragrafi regolando i margini su paragrafi.</span><span class="sxs-lookup"><span data-stu-id="bfea4-104">In flow content, extra space that appears between paragraphs is the result of margins set on these paragraphs; thus, the spacing between paragraphs can be controlled by adjusting the margins on those paragraphs.</span></span>  <span data-ttu-id="bfea4-105">Per eliminare completamente la spaziatura tra i due paragrafi, impostare i margini per i paragrafi a **0**.</span><span class="sxs-lookup"><span data-stu-id="bfea4-105">To eliminate extra spacing between two paragraphs altogether, set the margins for the paragraphs to **0**.</span></span>  <span data-ttu-id="bfea4-106">Per ottenere una spaziatura uniforme tra i paragrafi di un intero <xref:System.Windows.Documents.FlowDocument>, applicare uno stile per impostare un valore di un margine uniforme per tutti i paragrafi di <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="bfea4-106">To achieve uniform spacing between paragraphs throughout an entire <xref:System.Windows.Documents.FlowDocument>, use styling to set a uniform margin value for all paragraphs in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 <span data-ttu-id="bfea4-107">È importante notare che i margini per due paragrafi adiacenti "compressi" per il più elevato tra i due margini, anziché raddoppiati.</span><span class="sxs-lookup"><span data-stu-id="bfea4-107">It is important to note that the margins for two adjacent paragraphs will "collapse" to the larger of the two margins, rather than doubling up.</span></span> <span data-ttu-id="bfea4-108">Pertanto, se due paragrafi adiacenti hanno rispettivamente i margini di 20 e 40 pixel, lo spazio tra i paragrafi 40 pixel, il più elevato tra i valori dei margini di due.</span><span class="sxs-lookup"><span data-stu-id="bfea4-108">So, if two adjacent paragraphs have margins of 20 pixels and 40 pixels respectively, the resulting space between the paragraphs is 40 pixels, the larger of the two margin values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bfea4-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="bfea4-109">Example</span></span>  
 <span data-ttu-id="bfea4-110">Nell'esempio seguente viene utilizzato lo stile per impostare il margine per tutti <xref:System.Windows.Documents.Paragraph> elementi in un <xref:System.Windows.Documents.FlowDocument> a **0**, eliminando effettivamente la spaziatura tra i paragrafi di <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="bfea4-110">The following example uses styling to set the margin for all <xref:System.Windows.Documents.Paragraph> elements in a <xref:System.Windows.Documents.FlowDocument> to **0**, which effectively eliminates extra spacing between paragraphs in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-xaml[BlockSnippets#_ParagraphSpacingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BlockSnippets/CSharp/Window1.xaml#_paragraphspacingxaml)]
