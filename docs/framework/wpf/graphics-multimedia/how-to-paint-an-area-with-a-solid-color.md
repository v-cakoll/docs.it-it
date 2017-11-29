---
title: 'Procedura: disegnare un''area con un colore a tinta unita'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cde7f7df5089806ffb3235393eacc855d137ee51
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a>Procedura: disegnare un'area con un colore a tinta unita
Per disegnare un'area con un colore a tinta unita, è possibile utilizzare un pennello di sistema predefinito, ad esempio <xref:System.Windows.Media.Brushes.Red%2A> o <xref:System.Windows.Media.Brushes.Blue%2A>, oppure è possibile creare un nuovo <xref:System.Windows.Media.SolidColorBrush> e una descrizione relativa <xref:System.Windows.Media.SolidColorBrush.Color%2A> utilizzando i valori alfa, rossi, verde e blu. In XAML è anche possibile disegnare un'area con un colore a tinta unita usando la notazione esadecimale.  
  
 Negli esempi seguenti viene utilizzata ognuna di queste tecniche per disegnare un <xref:System.Windows.Shapes.Rectangle> blu.  
  
## <a name="example"></a>Esempio  
 **Uso di un pennello predefinito**  
  
 Nell'esempio seguente viene utilizzato il pennello predefinito <xref:System.Windows.Media.Brushes.Blue%2A> per disegnare un rettangolo blu.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 **Uso della notazione esadecimale**  
  
 L'esempio successivo usa la notazione esadecimale a 8 cifre per disegnare un rettangolo blu.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 **Uso dei valori ARGB**  
  
 Nell'esempio successivo viene creato un <xref:System.Windows.Media.SolidColorBrush> e descrive il <xref:System.Windows.Media.SolidColorBrush.Color%2A> utilizzando i valori ARGB per il colore blu.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 Per altre modalità di descrizione del colore, vedere il <xref:System.Windows.Media.Color> struttura.  
  
 **Argomenti correlati**  
  
 Per ulteriori informazioni su <xref:System.Windows.Media.SolidColorBrush> e ulteriori esempi, vedere il [disegni con colori a tinta unita e sfumature Panoramica](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md) Panoramica.  
  
 Questo esempio di codice fa parte di un esempio più esaustivo disponibile per la <xref:System.Windows.Media.SolidColorBrush> classe. Per l'esempio completo, vedere [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973) (Esempio di pennelli).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.Brushes>
