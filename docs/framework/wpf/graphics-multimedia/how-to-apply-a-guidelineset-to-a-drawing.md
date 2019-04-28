---
title: 'Procedura: Applicare un GuidelineSet a un disegno'
ms.date: 03/30/2017
helpviewer_keywords:
- GuidelineSet property [WPF], applying to drawings
- graphics [WPF], GuidelineSet property
ms.assetid: 45f3e0b4-8820-45a7-b865-b8ea5b17b0c8
ms.openlocfilehash: 134236c5beca806b747d45f20764cc82ddd8a4e8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699053"
---
# <a name="how-to-apply-a-guidelineset-to-a-drawing"></a><span data-ttu-id="6a04e-102">Procedura: Applicare un GuidelineSet a un disegno</span><span class="sxs-lookup"><span data-stu-id="6a04e-102">How to: Apply a GuidelineSet to a Drawing</span></span>
<span data-ttu-id="6a04e-103">In questo esempio viene illustrato come applicare una <xref:System.Windows.Media.GuidelineSet> a un <xref:System.Windows.Media.DrawingGroup>.</span><span class="sxs-lookup"><span data-stu-id="6a04e-103">This example shows how to apply a <xref:System.Windows.Media.GuidelineSet> to a <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
 <span data-ttu-id="6a04e-104">Il <xref:System.Windows.Media.DrawingGroup> classe è l'unico tipo di <xref:System.Windows.Media.Drawing> che ha un <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="6a04e-104">The <xref:System.Windows.Media.DrawingGroup> class is the only type of <xref:System.Windows.Media.Drawing> that has a <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> property.</span></span> <span data-ttu-id="6a04e-105">Per applicare una <xref:System.Windows.Media.GuidelineSet> a un altro tipo di <xref:System.Windows.Media.Drawing>, aggiungerlo a un <xref:System.Windows.Media.DrawingGroup> e quindi applicare il <xref:System.Windows.Media.GuidelineSet> per il <xref:System.Windows.Media.DrawingGroup>.</span><span class="sxs-lookup"><span data-stu-id="6a04e-105">To apply a <xref:System.Windows.Media.GuidelineSet> to another type of <xref:System.Windows.Media.Drawing>, add it to a <xref:System.Windows.Media.DrawingGroup> and then apply the <xref:System.Windows.Media.GuidelineSet> to your <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a04e-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="6a04e-106">Example</span></span>  
 <span data-ttu-id="6a04e-107">L'esempio seguente crea due <xref:System.Windows.Media.DrawingGroup> gli oggetti che sono quasi identici; l'unica differenza è: il secondo <xref:System.Windows.Media.DrawingGroup> ha una <xref:System.Windows.Media.GuidelineSet> e non il primo.</span><span class="sxs-lookup"><span data-stu-id="6a04e-107">The following example creates two <xref:System.Windows.Media.DrawingGroup> objects that are almost identical; the only difference is: the second <xref:System.Windows.Media.DrawingGroup> has a <xref:System.Windows.Media.GuidelineSet> and the first does not.</span></span>  
  
 <span data-ttu-id="6a04e-108">L'immagine seguente illustra l'output dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="6a04e-108">The following illustration shows the output from the example.</span></span> <span data-ttu-id="6a04e-109">Poiché il rendering delle differenze tra le due <xref:System.Windows.Media.DrawingGroup> oggetti è minima, vengono ingrandite parti dei disegni.</span><span class="sxs-lookup"><span data-stu-id="6a04e-109">Because the rendering difference between the two <xref:System.Windows.Media.DrawingGroup> objects is so subtle, portions of the drawings are enlarged.</span></span>  
  
 <span data-ttu-id="6a04e-110">![Oggetto DrawingGroup con e senza un GuidelineSet](./media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")</span><span class="sxs-lookup"><span data-stu-id="6a04e-110">![A DrawingGroup with and without a GuidelineSet](./media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupGuidelineSetExample.cs#graphicsmmdrawinggroupguidelinesetexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupGuidelineSetExample.xaml#graphicsmmdrawinggroupguidelinesetexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="6a04e-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a04e-111">See also</span></span>

- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.GuidelineSet>
- [<span data-ttu-id="6a04e-112">Cenni preliminari sugli oggetti Drawing</span><span class="sxs-lookup"><span data-stu-id="6a04e-112">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
