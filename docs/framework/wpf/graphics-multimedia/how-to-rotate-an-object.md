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
ms.openlocfilehash: b5a954158388e8b85589042e9d1f3b82c1747e30
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2018
ms.locfileid: "45591503"
---
# <a name="how-to-rotate-an-object"></a>Procedura: ruotare un oggetto
Questo esempio spiega come ruotare un oggetto. Nell'esempio viene creata una <xref:System.Windows.Media.RotateTransform> e quindi specifica relativa <xref:System.Windows.Media.RotateTransform.Angle%2A> espresso in gradi.  
  
 L'esempio seguente ruota un <xref:System.Windows.Shapes.Polyline> 45 gradi rispetto all'angolo superiore sinistro dell'oggetto.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[Transforms_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 Il <xref:System.Windows.Media.RotateTransform.CenterX%2A> e <xref:System.Windows.Media.RotateTransform.CenterY%2A> delle proprietà del <xref:System.Windows.Media.RotateTransform> specificare il punto in cui viene ruotato l'oggetto. Il punto centrale viene espresso nello spazio delle coordinate dell'elemento trasformato. Per impostazione predefinita, la rotazione viene applicata a (0,0), ovvero l'angolo superiore sinistro dell'oggetto da trasformare.  
  
 L'esempio seguente ruota un <xref:System.Windows.Shapes.Polyline> oggetto in senso orario 45 gradi intorno al punto (25,50).  
  
 [!code-xaml[Transforms_snip#RotatePolylineAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 La figura seguente mostra il risultato ottenuto applicando una <xref:System.Windows.Media.Transform> ai due oggetti.  
  
 ![45 degree rotations with different center points](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")  
Due oggetti che ruotano di 45 gradi da centri di rotazione diversi  
  
 Il <xref:System.Windows.Shapes.Polyline> negli esempi precedenti è un <xref:System.Windows.UIElement>. Quando si applica una <xref:System.Windows.Media.Transform> per il <xref:System.Windows.UIElement.RenderTransform%2A> proprietà di un <xref:System.Windows.UIElement>, è possibile usare i <xref:System.Windows.UIElement.RenderTransformOrigin%2A> proprietà per specificare un'origine per ogni <xref:System.Windows.Media.Transform> che applicano all'elemento. Poiché il <xref:System.Windows.UIElement.RenderTransformOrigin%2A> proprietà utilizza coordinate relative, è possibile applicare una trasformazione al centro dell'elemento, anche se non si conosce la dimensione. Per altre informazioni e per un esempio, vedere [specificare l'origine di una trasformazione utilizzando valori relativi](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).  
  
 Per l'esempio completo, vedere [2-D Transforms Sample (Esempio di trasformazioni 2D)](https://go.microsoft.com/fwlink/?LinkID=158252).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.Transform>  
 [Cenni preliminari sulle trasformazioni](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
