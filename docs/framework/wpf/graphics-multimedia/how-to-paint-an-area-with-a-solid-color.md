---
title: "Procedura: Disegnare un'area con un colore a tinta unita"
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
ms.openlocfilehash: ae6be062313e9340edefd86c15b7a044996fe280
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373110"
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a>Procedura: Disegnare un'area con un colore a tinta unita
Per disegnare un'area con colori a tinta unita, è possibile usare un pennello di sistema predefiniti, ad esempio <xref:System.Windows.Media.Brushes.Red%2A> oppure <xref:System.Windows.Media.Brushes.Blue%2A>, oppure è possibile creare un nuovo <xref:System.Windows.Media.SolidColorBrush> e una descrizione relativa <xref:System.Windows.Media.SolidColorBrush.Color%2A> usando i valori alfa, rossi, verdi e blu. In XAML è anche possibile disegnare un'area con un colore a tinta unita usando la notazione esadecimale.  
  
 Nell'esempio seguente usa ognuna di queste tecniche per disegnare un <xref:System.Windows.Shapes.Rectangle> blu.  
  
## <a name="example"></a>Esempio  
 **Uso di un pennello predefinito**  
  
 Nell'esempio seguente usa il pennello predefinito <xref:System.Windows.Media.Brushes.Blue%2A> per disegnare un rettangolo blu.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 **Uso della notazione esadecimale**  
  
 L'esempio successivo usa la notazione esadecimale a 8 cifre per disegnare un rettangolo blu.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 **Uso dei valori ARGB**  
  
 L'esempio successivo crea un <xref:System.Windows.Media.SolidColorBrush> e viene descritto il <xref:System.Windows.Media.SolidColorBrush.Color%2A> usando i valori ARGB per il colore blu.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 Per altri modi per descrivere il colore, vedere il <xref:System.Windows.Media.Color> struttura.  
  
 **Argomenti correlati**  
  
 Per altre informazioni sulle <xref:System.Windows.Media.SolidColorBrush> e altri esempi, vedere la [disegno con colori a tinta unita e sfumature Panoramica](painting-with-solid-colors-and-gradients-overview.md) Panoramica.  
  
 Questo esempio di codice è parte di un esempio più esaustivo disponibile per il <xref:System.Windows.Media.SolidColorBrush> classe. Per l'esempio completo, vedere [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973) (Esempio di pennelli).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Media.Brushes>
