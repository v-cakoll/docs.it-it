---
title: 'Procedura: Eseguire un hit test della geometria in un oggetto Visual'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects comprising Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], visual objects comprising
ms.assetid: 8bf2643f-d7f9-4cb4-9ea6-5b893c23200d
ms.openlocfilehash: e51dd73a65666ffee5958325079e8f06f13ac61b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363800"
---
# <a name="how-to-hit-test-geometry-in-a-visual"></a>Procedura: Eseguire un hit test della geometria in un oggetto Visual
In questo esempio illustra come eseguire un hit test su un oggetto visivo costituito da uno o più <xref:System.Windows.Media.Geometry> oggetti.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come recuperare il <xref:System.Windows.Media.DrawingGroup> da un oggetto visivo che usa il <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> (metodo). Viene quindi eseguito un hit test sul contenuto di cui viene eseguito rendering di ogni disegno nel <xref:System.Windows.Media.DrawingGroup> per determinare la geometria raggiunta.  
  
> [!NOTE]
>  Nella maggior parte dei casi, utilizzerebbe il <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> metodo per determinare se un punto interseca un contenuto di cui viene eseguito il rendering di un oggetto visivo.  
  
 [!code-csharp[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#visualsoverviewsnippet4)]
 [!code-vb[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#visualsoverviewsnippet4)]  
  
 Il <xref:System.Windows.Media.Geometry.FillContains%2A> metodo è un metodo di overload che consente di eseguire un hit test utilizzando un oggetto specificato <xref:System.Windows.Point> o <xref:System.Windows.Media.Geometry>. Se viene tracciata una geometria, il tratto può estendersi oltre i limiti del riempimento. In questo caso, è possibile chiamare <xref:System.Windows.Media.Geometry.StrokeContains%2A> oltre a <xref:System.Windows.Media.Geometry.FillContains%2A>.  
  
 È anche possibile fornire un <xref:System.Windows.Media.ToleranceType> usato ai fini di appiattimento di Bézier.  
  
> [!NOTE]
>  Questo esempio non prende in considerazione eventuali trasformazioni o ritagli applicabili alla geometria. L'esempio, inoltre, non funziona con un controllo con stili, poiché a esso non saranno direttamente associati disegni.  
  
## <a name="see-also"></a>Vedere anche
- [Hit testing a livello visivo](hit-testing-in-the-visual-layer.md)
- [Eseguire un hit test utilizzando la geometria come parametro](how-to-hit-test-using-geometry-as-a-parameter.md)
