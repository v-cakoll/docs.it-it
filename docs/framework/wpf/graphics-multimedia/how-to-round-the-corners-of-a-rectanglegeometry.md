---
title: 'Procedura: arrotondare gli angoli di un oggetto RectangleGeometry'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- corners [WPF], rounding
- RectangleGeometry class [WPF], rounding corners
- graphics [WPF], rounding corners of RectangleGeometry objects [WPF]
- rounding corners of RectangleGeometry objects [WPF]
ms.assetid: 926644bc-1357-4c0b-ac81-694bd090ae87
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4cd857f7ce886095bcbe92ae57c350ce83bb5c7d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-round-the-corners-of-a-rectanglegeometry"></a><span data-ttu-id="47fae-102">Procedura: arrotondare gli angoli di un oggetto RectangleGeometry</span><span class="sxs-lookup"><span data-stu-id="47fae-102">How to: Round the Corners of a RectangleGeometry</span></span>
<span data-ttu-id="47fae-103">Per arrotondare gli angoli di un <xref:System.Windows.Media.RectangleGeometry>, impostare il relativo <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> e <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> proprietà su un valore maggiore di zero.</span><span class="sxs-lookup"><span data-stu-id="47fae-103">To round the corners of a <xref:System.Windows.Media.RectangleGeometry>, set its <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> properties to a value greater than zero.</span></span> <span data-ttu-id="47fae-104">Più valori, più rotondi sono angoli del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="47fae-104">The larger the values, the rounder the rectangle's corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47fae-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="47fae-105">Example</span></span>  
 <span data-ttu-id="47fae-106">Nell'esempio seguente vengono mostrate diverse <xref:System.Windows.Media.RectangleGeometry> oggetti con diversi <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> e <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> impostazioni.</span><span class="sxs-lookup"><span data-stu-id="47fae-106">The following example shows several <xref:System.Windows.Media.RectangleGeometry> objects with different <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> settings.</span></span> <span data-ttu-id="47fae-107">Il <xref:System.Windows.Media.RectangleGeometry> gli oggetti vengono visualizzati utilizzando <xref:System.Windows.Shapes.Path> elementi.</span><span class="sxs-lookup"><span data-stu-id="47fae-107">The <xref:System.Windows.Media.RectangleGeometry> objects are displayed using <xref:System.Windows.Shapes.Path> elements.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRoundedRectangleGeometryExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/RectangleGeometryRoundedCornerExample.xaml#graphicsmmroundedrectanglegeometryexamplewholepage)]  
  
 <span data-ttu-id="47fae-108">![Rettangoli con diversi RadiusX &#47; Impostazioni radiusY](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rounded.png "graphicsmm_rounded")</span><span class="sxs-lookup"><span data-stu-id="47fae-108">![Rectangles with different RadiusX&#47;RadiusY settings](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rounded.png "graphicsmm_rounded")</span></span>  
<span data-ttu-id="47fae-109">Rettangoli con angoli arrotondati</span><span class="sxs-lookup"><span data-stu-id="47fae-109">Rectangles with Rounded Corners</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47fae-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47fae-110">See Also</span></span>  
 [<span data-ttu-id="47fae-111">Cenni preliminari sulle classi Geometry</span><span class="sxs-lookup"><span data-stu-id="47fae-111">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="47fae-112">Creare una forma composta</span><span class="sxs-lookup"><span data-stu-id="47fae-112">Create a Composite Shape</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [<span data-ttu-id="47fae-113">Creare una forma usando un oggetto PathGeometry</span><span class="sxs-lookup"><span data-stu-id="47fae-113">Create a Shape by Using a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
