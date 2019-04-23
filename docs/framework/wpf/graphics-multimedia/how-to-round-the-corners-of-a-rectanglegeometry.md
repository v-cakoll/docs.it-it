---
title: 'Procedura: Arrotondare gli angoli di un oggetto RectangleGeometry'
ms.date: 03/30/2017
helpviewer_keywords:
- corners [WPF], rounding
- RectangleGeometry class [WPF], rounding corners
- graphics [WPF], rounding corners of RectangleGeometry objects [WPF]
- rounding corners of RectangleGeometry objects [WPF]
ms.assetid: 926644bc-1357-4c0b-ac81-694bd090ae87
ms.openlocfilehash: eb2f173bedb903e12b2795264c684524cfa09825
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59089133"
---
# <a name="how-to-round-the-corners-of-a-rectanglegeometry"></a><span data-ttu-id="a7664-102">Procedura: Arrotondare gli angoli di un oggetto RectangleGeometry</span><span class="sxs-lookup"><span data-stu-id="a7664-102">How to: Round the Corners of a RectangleGeometry</span></span>
<span data-ttu-id="a7664-103">Per arrotondare gli angoli di un <xref:System.Windows.Media.RectangleGeometry>, impostare il <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> e <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> proprietà su un valore maggiore di zero.</span><span class="sxs-lookup"><span data-stu-id="a7664-103">To round the corners of a <xref:System.Windows.Media.RectangleGeometry>, set its <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> properties to a value greater than zero.</span></span> <span data-ttu-id="a7664-104">Più valori, più rotondi sono angoli del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="a7664-104">The larger the values, the rounder the rectangle's corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7664-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="a7664-105">Example</span></span>  
 <span data-ttu-id="a7664-106">L'esempio seguente illustra vari <xref:System.Windows.Media.RectangleGeometry> gli oggetti con diverse <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> e <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> impostazioni.</span><span class="sxs-lookup"><span data-stu-id="a7664-106">The following example shows several <xref:System.Windows.Media.RectangleGeometry> objects with different <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> settings.</span></span> <span data-ttu-id="a7664-107">Il <xref:System.Windows.Media.RectangleGeometry> gli oggetti vengono visualizzati utilizzando <xref:System.Windows.Shapes.Path> elementi.</span><span class="sxs-lookup"><span data-stu-id="a7664-107">The <xref:System.Windows.Media.RectangleGeometry> objects are displayed using <xref:System.Windows.Shapes.Path> elements.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRoundedRectangleGeometryExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/RectangleGeometryRoundedCornerExample.xaml#graphicsmmroundedrectanglegeometryexamplewholepage)]  
  
 <span data-ttu-id="a7664-108">![Rettangoli con RadiusX diversi&#47;impostazioni RadiusY](./media/graphicsmm-rounded.png "graphicsmm_rounded")</span><span class="sxs-lookup"><span data-stu-id="a7664-108">![Rectangles with different RadiusX&#47;RadiusY settings](./media/graphicsmm-rounded.png "graphicsmm_rounded")</span></span>  
<span data-ttu-id="a7664-109">Rettangoli con angoli arrotondati</span><span class="sxs-lookup"><span data-stu-id="a7664-109">Rectangles with Rounded Corners</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7664-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7664-110">See also</span></span>

- [<span data-ttu-id="a7664-111">Cenni preliminari sulle classi Geometry</span><span class="sxs-lookup"><span data-stu-id="a7664-111">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="a7664-112">Creare una forma composta</span><span class="sxs-lookup"><span data-stu-id="a7664-112">Create a Composite Shape</span></span>](how-to-create-a-composite-shape.md)
- [<span data-ttu-id="a7664-113">Creare una forma usando un oggetto PathGeometry</span><span class="sxs-lookup"><span data-stu-id="a7664-113">Create a Shape by Using a PathGeometry</span></span>](how-to-create-a-shape-by-using-a-pathgeometry.md)
