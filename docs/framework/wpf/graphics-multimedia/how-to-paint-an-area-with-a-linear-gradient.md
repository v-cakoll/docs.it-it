---
title: "Procedura: Disegnare un'area con una sfumatura lineare"
ms.date: 03/30/2017
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
ms.openlocfilehash: 92c9ccd846dbbce043d13e6ba82b9fa8e72fa8b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916168"
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a>Procedura: Disegnare un'area con una sfumatura lineare
Questo esempio illustra come usare la <xref:System.Windows.Media.LinearGradientBrush> classe per disegnare un'area con una sfumatura lineare. Nell'esempio seguente, l' <xref:System.Windows.Shapes.Shape.Fill%2A> oggetto di un oggetto <xref:System.Windows.Shapes.Rectangle> viene disegnato con una sfumatura lineare diagonale che passa da giallo a rosso a blu a verde limone.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 Nella figura seguente viene illustrata la sfumatura creata dall'esempio precedente.  
  
 ![Sfumatura lineare diagonale](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")  
  
 Per creare una sfumatura lineare orizzontale, modificare <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> e <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> di <xref:System.Windows.Media.LinearGradientBrush> in (0, 0,5) e (1, 0,5). Nell'esempio seguente viene disegnato un <xref:System.Windows.Shapes.Rectangle> oggetto con una sfumatura lineare orizzontale.  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 Nella figura seguente viene illustrata la sfumatura creata dall'esempio precedente.  
  
 ![Sfumatura lineare orizzontale](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")  
  
 Per creare una sfumatura lineare verticale, modificare <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> e <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> di <xref:System.Windows.Media.LinearGradientBrush> in (0,5, 0) e (0,5, 1). Nell'esempio seguente viene disegnato un <xref:System.Windows.Shapes.Rectangle> oggetto con una sfumatura lineare verticale.  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 Nella figura seguente viene illustrata la sfumatura creata dall'esempio precedente.  
  
 ![Sfumatura lineare verticale](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")  
  
> [!NOTE]
> Negli esempi di questo argomento viene utilizzato il sistema di coordinate predefinito per l'impostazione di punti di inizio e di fine. Il sistema di coordinate predefinito è relativo a un rettangolo di delimitazione: 0 indica lo 0% del riquadro e 1 indica il 100% del riquadro. È possibile modificare questo sistema di coordinate impostando <xref:System.Windows.Media.GradientBrush.MappingMode%2A> la proprietà sul valore <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>. Un sistema di coordinate assoluto non è relativo a un rettangolo di selezione. I valori vengono interpretati direttamente nello spazio locale.  
  
 Per altri esempi, vedere [esempio](https://go.microsoft.com/fwlink/?LinkID=159973)di pennelli. Per ulteriori informazioni sui gradienti e sugli altri tipi di pennelli, vedere [Cenni preliminari sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md).
