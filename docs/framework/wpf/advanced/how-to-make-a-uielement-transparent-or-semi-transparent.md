---
title: 'Procedura: Rendere trasparente o semitrasparente un oggetto UIElement'
ms.date: 03/30/2017
helpviewer_keywords:
- UIElements [WPF], transparency
- opacity [WPF], of UIElements
- transparency of UIElements [WPF]
- UIElements [WPF], opacity
ms.assetid: a49fc8d6-7b32-4f28-9122-39b632a19b4b
ms.openlocfilehash: 1de9a7e11fee241ecb71242e9808e77b7e5e63b0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942870"
---
# <a name="how-to-make-a-uielement-transparent-or-semi-transparent"></a>Procedura: Rendere trasparente o semitrasparente un oggetto UIElement
In questo esempio viene illustrato come effettuare una <xref:System.Windows.UIElement> trasparente o semitrasparente. Per rendere un elemento trasparente o semitrasparente, impostare il <xref:System.Windows.UIElement.Opacity%2A> proprietà. Un valore pari `0.0` l'elemento viene reso completamente trasparente, mentre un valore di `1.0` l'elemento viene reso completamente opaco. Un valore di `0.5` rende l'elemento 50% e così via. Un elemento <xref:System.Windows.UIElement.Opacity%2A> è impostata su `1.0` per impostazione predefinita.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente imposta la <xref:System.Windows.UIElement.Opacity%2A> di un pulsante su `0.25`, rendendo opaco l'oggetto e relativo contenuto (in questo caso, il testo del pulsante) al 25%.  
  
 [!code-xaml[brushsamples_snip#2](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#2)]  
  
 [!code-csharp[brushsamples_procedural_snip#2](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#2)]  
  
 Se il contenuto di un elemento dispone di propri <xref:System.Windows.UIElement.Opacity%2A> le impostazioni, tali valori vengono moltiplicate per gli elementi che lo contiene <xref:System.Windows.UIElement.Opacity%2A>.  
  
 L'esempio seguente imposta un pulsante <xref:System.Windows.UIElement.Opacity%2A> al `0.25`e il <xref:System.Windows.UIElement.Opacity%2A> di un <xref:System.Windows.Controls.Image> controllo contenuto all'interno del pulsante su `0.5`. Di conseguenza, l'immagine viene visualizzata 12,5% opaco: 0.25 * 0.5 = 0.125.  
  
 [!code-xaml[brushsamples_snip#3](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#3)]  
  
 [!code-csharp[brushsamples_procedural_snip#3](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#3)]  
  
 Un altro modo per controllare l'opacità di un elemento consiste nell'impostare l'opacità del <xref:System.Windows.Media.Brush> che disegna l'elemento. Questo approccio consente di modificare in modo selettivo l'opacità delle porzioni di un elemento e offre vantaggi nelle prestazioni rispetto all'uso dell'elemento <xref:System.Windows.UIElement.Opacity%2A> proprietà. L'esempio seguente imposta la <xref:System.Windows.Media.Brush.Opacity%2A> di un <xref:System.Windows.Media.SolidColorBrush> utilizzato per disegnare il pulsante <xref:System.Windows.Controls.Control.Background%2A> è impostata su `0.25`. Di conseguenza, lo sfondo del pennello è opaca al 25%, ma il relativo contenuto (testo del pulsante) rimane opache al 100%.  
  
 [!code-xaml[brushsamples_snip#4](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#4)]  
  
 [!code-csharp[brushsamples_procedural_snip#4](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#4)]  
  
 È inoltre possibile controllare l'opacità di colori singoli all'interno di un pennello. Per altre informazioni sui colori e pennelli, vedere [disegno con colori a tinta unita e sfumature Panoramica](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md). Per un esempio che illustra come animare l'opacità di un elemento, vedere [animare l'opacità di un elemento o un pennello](../graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md).
