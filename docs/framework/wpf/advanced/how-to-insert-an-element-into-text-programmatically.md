---
title: 'Procedura: Inserire un elemento in un testo a livello di codice'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Text Animation sample [WPF]
- elements [WPF], inserting into text
- inserting elements into text [WPF]
- TextPointer objects [WPF]
- text [WPF], inserting elements
ms.assetid: 97bd950a-25ac-4e42-a311-94b6420d4136
ms.openlocfilehash: c93a1c7542a4ddb33b3880de423c256adcc3f1c3
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378561"
---
# <a name="how-to-insert-an-element-into-text-programmatically"></a><span data-ttu-id="a66de-102">Procedura: Inserire un elemento in un testo a livello di codice</span><span class="sxs-lookup"><span data-stu-id="a66de-102">How to: Insert an Element Into Text Programmatically</span></span>
<span data-ttu-id="a66de-103">Nell'esempio seguente viene illustrato come usare due <xref:System.Windows.Documents.TextPointer> gli oggetti per specificare un intervallo all'interno del testo per applicare un <xref:System.Windows.Documents.Span> elemento.</span><span class="sxs-lookup"><span data-stu-id="a66de-103">The following example shows how to use two <xref:System.Windows.Documents.TextPointer> objects to specify a range within text to apply a <xref:System.Windows.Documents.Span> element to.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a66de-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="a66de-104">Example</span></span>  
 [!code-csharp[FlowMiscSnippets_procedural_snip#InsertInlineIntoTextExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowMiscSnippets_procedural_snip/CSharp/InsertInlineIntoTextExample.cs#insertinlineintotextexamplewholepage)]
 [!code-vb[FlowMiscSnippets_procedural_snip#InsertInlineIntoTextExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowMiscSnippets_procedural_snip/VisualBasic/InsertInlineIntoTextExample.vb#insertinlineintotextexamplewholepage)]  
  
 <span data-ttu-id="a66de-105">Nella figura riportata di seguito viene illustrato l'esempio in questione.</span><span class="sxs-lookup"><span data-stu-id="a66de-105">The illustration below shows what this example looks like.</span></span>  
  
 <span data-ttu-id="a66de-106">![Elemento Span applicato a un intervallo di testo](./media/flow-insertelementintotextprogrammatically.png "Flow_InsertElementIntoTextProgrammatically")</span><span class="sxs-lookup"><span data-stu-id="a66de-106">![A Span element applied to a range of text](./media/flow-insertelementintotextprogrammatically.png "Flow_InsertElementIntoTextProgrammatically")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a66de-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a66de-107">See also</span></span>
- [<span data-ttu-id="a66de-108">Cenni preliminari sui documenti dinamici</span><span class="sxs-lookup"><span data-stu-id="a66de-108">Flow Document Overview</span></span>](flow-document-overview.md)
