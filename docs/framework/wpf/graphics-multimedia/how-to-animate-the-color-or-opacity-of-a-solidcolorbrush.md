---
title: "Procedura: aggiungere un'animazione al colore o all'opacità di un oggetto SolidColorBrush"
ms.date: 03/30/2017
helpviewer_keywords:
- SolidColorBrush [WPF], animating color of
- colors [WPF], animating
- opacity [WPF], animating
- animation [WPF], color of SolidColorBrush
- animation [WPF], opacity of SolidColorBrush
- SolidColorBrush [WPF], animating opacity of
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
ms.openlocfilehash: 08b85935e0cb1ababd1fb63b9d02518ea3fcfa17
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452883"
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a><span data-ttu-id="ba355-102">Procedura: aggiungere un'animazione al colore o all'opacità di un oggetto SolidColorBrush</span><span class="sxs-lookup"><span data-stu-id="ba355-102">How to: Animate the Color or Opacity of a SolidColorBrush</span></span>
<span data-ttu-id="ba355-103">Questo esempio illustra come animare il <xref:System.Windows.Media.SolidColorBrush.Color%2A> e <xref:System.Windows.Media.Brush.Opacity%2A> di un <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="ba355-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba355-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="ba355-104">Example</span></span>  
 <span data-ttu-id="ba355-105">Nell'esempio seguente vengono usate tre animazioni per animare il <xref:System.Windows.Media.SolidColorBrush.Color%2A> e <xref:System.Windows.Media.Brush.Opacity%2A> di un <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="ba355-105">The following example uses three animations to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
- <span data-ttu-id="ba355-106">La prima animazione, una <xref:System.Windows.Media.Animation.ColorAnimation>, cambia il colore del pennello in <xref:System.Windows.Media.Colors.Gray%2A> quando il mouse entra nel rettangolo.</span><span class="sxs-lookup"><span data-stu-id="ba355-106">The first animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Gray%2A> when the mouse enters the rectangle.</span></span>  
  
- <span data-ttu-id="ba355-107">L'animazione successiva, un'altra <xref:System.Windows.Media.Animation.ColorAnimation>, cambia il colore del pennello in <xref:System.Windows.Media.Colors.Orange%2A> quando il mouse esce dal rettangolo.</span><span class="sxs-lookup"><span data-stu-id="ba355-107">The next animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Orange%2A> when the mouse leaves the rectangle.</span></span>  
  
- <span data-ttu-id="ba355-108">L'animazione finale, una <xref:System.Windows.Media.Animation.DoubleAnimation>, imposta l'opacità del pennello su 0,0 quando viene premuto il pulsante sinistro del mouse.</span><span class="sxs-lookup"><span data-stu-id="ba355-108">The final animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, changes the brush's opacity to 0.0 when the left mouse button is pressed.</span></span>  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](~/samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 <span data-ttu-id="ba355-109">Per un esempio più completo che illustra come animare tipi diversi di pennelli, vedere l' [esempio di pennelli](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span><span class="sxs-lookup"><span data-stu-id="ba355-109">For a more complete sample, which shows how to animate different types of brushes, see the [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span> <span data-ttu-id="ba355-110">Per ulteriori informazioni sulle animazioni, vedere [Cenni preliminari sull'animazione](animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ba355-110">For more information about animation, see the [Animation Overview](animation-overview.md).</span></span>  
  
 <span data-ttu-id="ba355-111">Per coerenza con altri esempi di animazione, nelle versioni del codice di questo esempio viene usato un oggetto <xref:System.Windows.Media.Animation.Storyboard> per applicare le animazioni.</span><span class="sxs-lookup"><span data-stu-id="ba355-111">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply their animations.</span></span> <span data-ttu-id="ba355-112">Tuttavia, quando si applica un'unica animazione nel codice, è più semplice usare il metodo <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> invece di usare una <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="ba355-112">However, when applying a single animation in code, it's simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="ba355-113">Per un esempio, vedere [Animare una proprietà senza utilizzare uno storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="ba355-113">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba355-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba355-114">See also</span></span>

- [<span data-ttu-id="ba355-115">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="ba355-115">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="ba355-116">Cenni preliminari sugli storyboard</span><span class="sxs-lookup"><span data-stu-id="ba355-116">Storyboards Overview</span></span>](storyboards-overview.md)
- <span data-ttu-id="ba355-117">[Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes) (Esempio di pennelli)</span><span class="sxs-lookup"><span data-stu-id="ba355-117">[Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)</span></span>
