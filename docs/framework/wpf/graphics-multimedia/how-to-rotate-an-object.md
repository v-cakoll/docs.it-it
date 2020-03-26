---
title: 'Procedura: ruotare un oggetto'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rotating objects [WPF]
- rotating objects [WPF]
ms.assetid: ee3466cd-e66f-4e8f-8a5a-71d77bc1e390
ms.openlocfilehash: e17d3b7b9986b477df198480129edaf4c139c6bc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112063"
---
# <a name="how-to-rotate-an-object"></a>Procedura: ruotare un oggetto
Questo esempio spiega come ruotare un oggetto. L'esempio crea <xref:System.Windows.Media.RotateTransform> innanzitutto un <xref:System.Windows.Media.RotateTransform.Angle%2A> oggetto e ne specifica i in gradi.  
  
 Nell'esempio seguente <xref:System.Windows.Shapes.Polyline> un oggetto ruota di 45 gradi intorno all'angolo superiore sinistro.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[Transforms_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 Le <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> proprietà e <xref:System.Windows.Media.RotateTransform> dell'oggetto specificano il punto attorno al quale l'oggetto viene ruotato. Il punto centrale viene espresso nello spazio delle coordinate dell'elemento trasformato. Per impostazione predefinita, la rotazione viene applicata a (0,0), ovvero l'angolo superiore sinistro dell'oggetto da trasformare.  
  
 L'esempio successivo <xref:System.Windows.Shapes.Polyline> ruota un oggetto in senso orario di 45 gradi intorno al punto (25,50).  
  
 [!code-xaml[Transforms_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 Nella figura seguente vengono illustrati <xref:System.Windows.Media.Transform> i risultati dell'applicazione di un oggetto ai due oggetti.  
  
 ![Rotazioni di 45 gradi con punti centrali diversi](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")  
Due oggetti che ruotano di 45 gradi da centri di rotazione diversi  
  
 Negli <xref:System.Windows.Shapes.Polyline> esempi precedenti è <xref:System.Windows.UIElement>un oggetto . Quando si <xref:System.Windows.Media.Transform> applica <xref:System.Windows.UIElement.RenderTransform%2A> un alla <xref:System.Windows.UIElement>proprietà di <xref:System.Windows.UIElement.RenderTransformOrigin%2A> un oggetto , è <xref:System.Windows.Media.Transform> possibile utilizzare la proprietà per specificare un'origine per ogni applicazione all'elemento. Poiché <xref:System.Windows.UIElement.RenderTransformOrigin%2A> la proprietà utilizza coordinate relative, è possibile applicare una trasformazione al centro dell'elemento anche se non si conoscono le dimensioni. Per ulteriori informazioni e per un esempio, vedere [Specificare l'origine di una trasformazione tramite valori relativi](how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).  
  
 Per l'esempio completo, vedere Esempio di [trasformazioni 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Transform>
- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
- [Procedure relative](transformations-how-to-topics.md)
