---
title: 'Procedura: Eseguire un hit test della geometria in un oggetto visivo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects comprising Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], visual objects comprising
ms.assetid: 8bf2643f-d7f9-4cb4-9ea6-5b893c23200d
ms.openlocfilehash: 52b9b99b0af38d797e4a3c98dc0979211c930c1f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923375"
---
# <a name="how-to-hit-test-geometry-in-a-visual"></a>Procedura: Eseguire un hit test della geometria in un oggetto visivo
Questo esempio illustra come eseguire un hit test su un oggetto visivo composto da uno o più <xref:System.Windows.Media.Geometry> oggetti.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come recuperare <xref:System.Windows.Media.DrawingGroup> da un oggetto visivo che utilizza il <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> metodo. Viene quindi eseguito un hit test sul contenuto sottoposto a rendering di ogni disegno <xref:System.Windows.Media.DrawingGroup> nell'oggetto per determinare quale geometria è stata raggiunta.  
  
> [!NOTE]
> Nella maggior parte dei casi, si utilizzerà il <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> metodo per determinare se un punto interseca qualsiasi contenuto sottoposto a rendering di un oggetto visivo.  
  
 [!code-csharp[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#visualsoverviewsnippet4)]
 [!code-vb[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#visualsoverviewsnippet4)]  
  
 Il <xref:System.Windows.Media.Geometry.FillContains%2A> metodo è un metodo di overload che consente di eseguire un hit test usando un oggetto o <xref:System.Windows.Point> <xref:System.Windows.Media.Geometry>specificato. Se viene tracciata una geometria, il tratto può estendersi oltre i limiti del riempimento. In tal caso, è consigliabile chiamare <xref:System.Windows.Media.Geometry.StrokeContains%2A> oltre a. <xref:System.Windows.Media.Geometry.FillContains%2A>  
  
 È anche possibile specificare un <xref:System.Windows.Media.ToleranceType> oggetto che viene usato ai fini dell'appiattimento di Bezier.  
  
> [!NOTE]
> Questo esempio non prende in considerazione eventuali trasformazioni o ritagli applicabili alla geometria. L'esempio, inoltre, non funziona con un controllo con stili, poiché a esso non saranno direttamente associati disegni.  
  
## <a name="see-also"></a>Vedere anche

- [Hit testing a livello visivo](hit-testing-in-the-visual-layer.md)
- [Eseguire un hit test utilizzando la geometria come parametro](how-to-hit-test-using-geometry-as-a-parameter.md)
