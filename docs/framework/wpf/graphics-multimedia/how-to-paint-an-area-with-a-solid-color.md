---
title: "Procedura: disegnare un'area con un colore a tinta unita"
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
ms.openlocfilehash: be28a0af04c4e43cdf745a5429468aee99e34c40
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2020
ms.locfileid: "78849522"
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a>Procedura: disegnare un'area con un colore a tinta unita
Per disegnare un'area con un colore a tinta unita, è possibile utilizzare un pennello di sistema predefinito, ad <xref:System.Windows.Media.Brushes.Red%2A> esempio o <xref:System.Windows.Media.Brushes.Blue%2A>, oppure crearne uno nuovo <xref:System.Windows.Media.SolidColorBrush> e descriverne l'utilizzo <xref:System.Windows.Media.SolidColorBrush.Color%2A> di valori alfa, rosso, verde e blu. In XAML è anche possibile disegnare un'area con un colore a tinta unita usando la notazione esadecimale.  
  
 Negli esempi seguenti viene utilizzata ognuna di queste tecniche per disegnare un <xref:System.Windows.Shapes.Rectangle> blu.  
  
## <a name="example"></a>Esempio  
 **Uso di un pennello predefinito**  
  
 Nell'esempio seguente viene utilizzato <xref:System.Windows.Media.Brushes.Blue%2A> il pennello predefinito per disegnare un rettangolo blu.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 **Uso della notazione esadecimale**  
  
 L'esempio successivo usa la notazione esadecimale a 8 cifre per disegnare un rettangolo blu.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 **Uso dei valori ARGB**  
  
 Nell'esempio successivo <xref:System.Windows.Media.SolidColorBrush> viene creato <xref:System.Windows.Media.SolidColorBrush.Color%2A> un oggetto e ne viene descritto l'utilizzo dei valori ARGB per il colore blu.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 Per altri modi di descrivere <xref:System.Windows.Media.Color> il colore, vedere la struttura.  
  
 **Argomenti correlati**  
  
 Per ulteriori <xref:System.Windows.Media.SolidColorBrush> informazioni e esempi aggiuntivi, vedere la [panoramica di pittura con colori a](painting-with-solid-colors-and-gradients-overview.md) tinta unita e gradienti.  
  
 Questo esempio di codice fa parte <xref:System.Windows.Media.SolidColorBrush> di un esempio più esaustivo fornito per la classe. Per l'esempio completo, vedere [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes) (Esempio di pennelli).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Brushes>
