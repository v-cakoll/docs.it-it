---
title: "Procedura: disegnare un'area con una sfumatura lineare"
ms.date: 03/30/2017
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
ms.openlocfilehash: ec07a0c33468681f67d086ec3d1d58b378412ff9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560877"
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a>Procedura: disegnare un'area con una sfumatura lineare
In questo esempio viene illustrato come utilizzare la <xref:System.Windows.Media.LinearGradientBrush> classe per disegnare un'area con una sfumatura lineare. Nell'esempio seguente, il <xref:System.Windows.Shapes.Shape.Fill%2A> di un <xref:System.Windows.Shapes.Rectangle> di disegno con sfumatura lineare diagonale che effettua la transizione da giallo a rosso blu per verde limone.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 Nella figura seguente mostra la sfumatura creata nell'esempio precedente.  
  
 ![Sfumatura lineare diagonale](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")  
  
 Per creare una sfumatura lineare orizzontale, modificare il <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> e <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> del <xref:System.Windows.Media.LinearGradientBrush> su (0, 0.5) e (1, 0.5). Nell'esempio seguente, un <xref:System.Windows.Shapes.Rectangle> viene disegnato con una sfumatura lineare orizzontale.  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 Nella figura seguente mostra la sfumatura creata nell'esempio precedente.  
  
 ![Sfumatura lineare orizzontale](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")  
  
 Per creare una sfumatura lineare verticale, modificare il <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> e <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> del <xref:System.Windows.Media.LinearGradientBrush> su (0.5,0) e (0.5,1). Nell'esempio seguente, un <xref:System.Windows.Shapes.Rectangle> viene disegnato con una sfumatura lineare verticale.  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 Nella figura seguente mostra la sfumatura creata nell'esempio precedente.  
  
 ![Sfumatura lineare verticale](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")  
  
> [!NOTE]
>  Gli esempi in questo argomento usano il sistema di coordinate per l'impostazione di punti di inizio e di punti di fine. Il sistema di coordinate è relativo a un rettangolo di selezione: 0 indica 0 percento del rettangolo di selezione, mentre 1 indica 100% del rettangolo di selezione. È possibile modificare il sistema di coordinate impostando il <xref:System.Windows.Media.GradientBrush.MappingMode%2A> il valore della proprietà <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>. Un sistema di coordinate assoluto non è relativo a un rettangolo di selezione. I valori vengono interpretati direttamente nello spazio locale.  
  
 Per ulteriori esempi, vedere [esempio](http://go.microsoft.com/fwlink/?LinkID=159973). Per ulteriori informazioni sulle sfumature e altri tipi di pennelli, vedere [disegni con colori a tinta unita e sfumature Panoramica](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).
