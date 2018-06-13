---
title: 'Procedura: rendere trasparente o semitrasparente un oggetto UIElement'
ms.date: 03/30/2017
helpviewer_keywords:
- UIElements [WPF], transparency
- opacity [WPF], of UIElements
- transparency of UIElements [WPF]
- UIElements [WPF], opacity
ms.assetid: a49fc8d6-7b32-4f28-9122-39b632a19b4b
ms.openlocfilehash: 7bf79848edb84a5bd93d1196fbe0b3196d159ff3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545311"
---
# <a name="how-to-make-a-uielement-transparent-or-semi-transparent"></a>Procedura: rendere trasparente o semitrasparente un oggetto UIElement
Questo esempio viene illustrato come rendere un <xref:System.Windows.UIElement> trasparente o semitrasparente. Per rendere un elemento trasparente o semitrasparente, impostare il relativo <xref:System.Windows.UIElement.Opacity%2A> proprietà. Il valore `0.0` l'elemento viene reso completamente trasparente, mentre un valore di `1.0` l'elemento viene reso completamente opaco. Il valore `0.5` l'elemento viene reso 50% e così via. Un elemento <xref:System.Windows.UIElement.Opacity%2A> è impostato su `1.0` per impostazione predefinita.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente imposta il <xref:System.Windows.UIElement.Opacity%2A> di un pulsante per `0.25`, rendendo opaco l'oggetto e il relativo contenuto (in questo caso, il testo del pulsante) al 25%.  
  
 [!code-xaml[brushsamples_snip#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#2)]  
  
 [!code-csharp[brushsamples_procedural_snip#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#2)]  
  
 Se il contenuto di un elemento dispone delle proprie <xref:System.Windows.UIElement.Opacity%2A> impostazioni, tali valori vengono moltiplicate per gli elementi contenitori <xref:System.Windows.UIElement.Opacity%2A>.  
  
 Nell'esempio seguente imposta un pulsante <xref:System.Windows.UIElement.Opacity%2A> a `0.25`e <xref:System.Windows.UIElement.Opacity%2A> di un <xref:System.Windows.Controls.Image> controllo contenuto all'interno del pulsante su `0.5`. Di conseguenza, l'immagine viene visualizzata 12,5% opaco: 0,25 * 0,5 = 0,125.  
  
 [!code-xaml[brushsamples_snip#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#3)]  
  
 [!code-csharp[brushsamples_procedural_snip#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#3)]  
  
 Un altro modo per controllare l'opacità di un elemento consiste nell'impostare l'opacità del <xref:System.Windows.Media.Brush> che disegna l'elemento. Questo approccio consente di modificare in modo selettivo l'opacità di parti di un elemento e offre vantaggi nelle prestazioni rispetto all'uso dell'elemento <xref:System.Windows.UIElement.Opacity%2A> proprietà. L'esempio seguente imposta il <xref:System.Windows.Media.Brush.Opacity%2A> di un <xref:System.Windows.Media.SolidColorBrush> usato per disegnare il pulsante <xref:System.Windows.Controls.Control.Background%2A> è impostato su `0.25`. Di conseguenza, lo sfondo del pennello è opaco al 25%, ma il relativo contenuto (testo del pulsante) rimane opaca al 100%.  
  
 [!code-xaml[brushsamples_snip#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#4)]  
  
 [!code-csharp[brushsamples_procedural_snip#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#4)]  
  
 È inoltre possibile controllare l'opacità di colori singoli all'interno di un pennello. Per ulteriori informazioni sui colori e pennelli, vedere [disegni con colori a tinta unita e sfumature Panoramica](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md). Per un esempio che illustra come aggiungere un'animazione opacità di un elemento, vedere [animare l'opacità di un elemento o un pennello](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md).
