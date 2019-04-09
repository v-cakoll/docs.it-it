---
title: "Procedura: Usare le proprietà associate di un'area di disegno per posizionare gli elementi figlio"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- attached properties [WPF Designer]
- Canvas control [WPF], attached properties
ms.assetid: 48f1d25d-3820-4107-a4cc-d6c1e5664a44
ms.openlocfilehash: 347c8502bd4c5fafcde7a142327f85bfb75b9954
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159627"
---
# <a name="how-to-use-the-attached-properties-of-canvas-to-position-child-elements"></a><span data-ttu-id="e3ac7-102">Procedura: Usare le proprietà associate di un'area di disegno per posizionare gli elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e3ac7-102">How to: Use the Attached Properties of Canvas to Position Child Elements</span></span>
<span data-ttu-id="e3ac7-103">In questo esempio viene illustrato come utilizzare le proprietà associate di <xref:System.Windows.Controls.Canvas> per posizionare elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="e3ac7-103">This example shows how to use the attached properties of <xref:System.Windows.Controls.Canvas> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3ac7-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="e3ac7-104">Example</span></span>  
 <span data-ttu-id="e3ac7-105">L'esempio seguente aggiunge quattro <xref:System.Windows.Controls.Button> elementi come elementi figlio di un elemento padre <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="e3ac7-105">The following example adds four <xref:System.Windows.Controls.Button> elements as child elements of a parent <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="e3ac7-106">Ogni elemento è rappresentato da un <xref:System.Windows.Controls.Canvas.Bottom%2A>, <xref:System.Windows.Controls.Canvas.Left%2A>, <xref:System.Windows.Controls.Canvas.Right%2A>, e <xref:System.Windows.Controls.Canvas.Top%2A>.</span><span class="sxs-lookup"><span data-stu-id="e3ac7-106">Each element is represented by a <xref:System.Windows.Controls.Canvas.Bottom%2A>, <xref:System.Windows.Controls.Canvas.Left%2A>, <xref:System.Windows.Controls.Canvas.Right%2A>, and <xref:System.Windows.Controls.Canvas.Top%2A>.</span></span>
<span data-ttu-id="e3ac7-107">Ciascuna <xref:System.Windows.Controls.Button> viene posizionata in relazione padre <xref:System.Windows.Controls.Canvas> e in base al valore di proprietà assegnato.</span><span class="sxs-lookup"><span data-stu-id="e3ac7-107">Each <xref:System.Windows.Controls.Button> is positioned relative to the parent <xref:System.Windows.Controls.Canvas> and according to its assigned property value.</span></span>  
  
 [!code-cpp[CanvasAttachedProperties#1](~/samples/snippets/cpp/VS_Snippets_Wpf/CanvasAttachedProperties/CPP/CanvasAttachedProps.cpp#1)]
 [!code-csharp[CanvasAttachedProperties#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasAttachedProperties/CSharp/CanvasAttachedProps.cs#1)]
 [!code-vb[CanvasAttachedProperties#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasAttachedProperties/VisualBasic/CanvasAttachedProps.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e3ac7-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3ac7-108">See also</span></span>

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.Canvas.Bottom%2A>
- <xref:System.Windows.Controls.Canvas.Left%2A>
- <xref:System.Windows.Controls.Canvas.Right%2A>
- <xref:System.Windows.Controls.Canvas.Top%2A>
- <xref:System.Windows.Controls.Button>
- [<span data-ttu-id="e3ac7-109">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="e3ac7-109">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="e3ac7-110">Procedure relative</span><span class="sxs-lookup"><span data-stu-id="e3ac7-110">How-to Topics</span></span>](canvas-how-to-topics.md)
- [<span data-ttu-id="e3ac7-111">Cenni preliminari sulle proprietà associate</span><span class="sxs-lookup"><span data-stu-id="e3ac7-111">Attached Properties Overview</span></span>](../advanced/attached-properties-overview.md)
