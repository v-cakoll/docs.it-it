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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651397"
---
# <a name="how-to-round-the-corners-of-a-rectanglegeometry"></a>Procedura: Arrotondare gli angoli di un oggetto RectangleGeometry
Per arrotondare gli angoli di un <xref:System.Windows.Media.RectangleGeometry>, impostare il <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> e <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> proprietà su un valore maggiore di zero. Più valori, più rotondi sono angoli del rettangolo.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra vari <xref:System.Windows.Media.RectangleGeometry> gli oggetti con diverse <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> e <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> impostazioni. Il <xref:System.Windows.Media.RectangleGeometry> gli oggetti vengono visualizzati utilizzando <xref:System.Windows.Shapes.Path> elementi.  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRoundedRectangleGeometryExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/RectangleGeometryRoundedCornerExample.xaml#graphicsmmroundedrectanglegeometryexamplewholepage)]  
  
 ![Rettangoli con RadiusX diversi&#47;impostazioni RadiusY](./media/graphicsmm-rounded.png "graphicsmm_rounded")  
Rettangoli con angoli arrotondati  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulle classi Geometry](geometry-overview.md)
- [Creare una forma composta](how-to-create-a-composite-shape.md)
- [Creare una forma usando un oggetto PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md)
