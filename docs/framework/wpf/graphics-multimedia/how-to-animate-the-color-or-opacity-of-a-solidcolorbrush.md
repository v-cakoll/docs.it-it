---
title: "Procedura: Aggiungere un'animazione al colore o all'opacità di un oggetto SolidColorBrush"
ms.date: 03/30/2017
helpviewer_keywords:
- SolidColorBrush [WPF], animating color of
- colors [WPF], animating
- opacity [WPF], animating
- animation [WPF], color of SolidColorBrush
- animation [WPF], opacity of SolidColorBrush
- SolidColorBrush [WPF], animating opacity of
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
ms.openlocfilehash: e440cf49b8b16051361650f9659dc6006c2e7b56
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59072159"
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a><span data-ttu-id="bb5e1-102">Procedura: Aggiungere un'animazione al colore o all'opacità di un oggetto SolidColorBrush</span><span class="sxs-lookup"><span data-stu-id="bb5e1-102">How to: Animate the Color or Opacity of a SolidColorBrush</span></span>
<span data-ttu-id="bb5e1-103">In questo esempio illustra come animare la <xref:System.Windows.Media.SolidColorBrush.Color%2A> e <xref:System.Windows.Media.Brush.Opacity%2A> di un <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="bb5e1-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb5e1-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="bb5e1-104">Example</span></span>  
 <span data-ttu-id="bb5e1-105">Nell'esempio seguente usa tre animazioni per animare la <xref:System.Windows.Media.SolidColorBrush.Color%2A> e <xref:System.Windows.Media.Brush.Opacity%2A> di un <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="bb5e1-105">The following example uses three animations to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
-   <span data-ttu-id="bb5e1-106">La prima animazione, un <xref:System.Windows.Media.Animation.ColorAnimation>, viene modificato il colore del pennello per <xref:System.Windows.Media.Colors.Gray%2A> quando il mouse viene spostato il rettangolo.</span><span class="sxs-lookup"><span data-stu-id="bb5e1-106">The first animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Gray%2A> when the mouse enters the rectangle.</span></span>  
  
-   <span data-ttu-id="bb5e1-107">La successiva animazione, un'altra <xref:System.Windows.Media.Animation.ColorAnimation>, viene modificato il colore del pennello per <xref:System.Windows.Media.Colors.Orange%2A> quando il mouse lascia il rettangolo.</span><span class="sxs-lookup"><span data-stu-id="bb5e1-107">The next animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Orange%2A> when the mouse leaves the rectangle.</span></span>  
  
-   <span data-ttu-id="bb5e1-108">L'ultima animazione, un <xref:System.Windows.Media.Animation.DoubleAnimation>, cambia l'opacità del pennello in 0,0 quando viene premuto il pulsante sinistro del mouse.</span><span class="sxs-lookup"><span data-stu-id="bb5e1-108">The final animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, changes the brush's opacity to 0.0 when the left mouse button is pressed.</span></span>  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](~/samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 <span data-ttu-id="bb5e1-109">Per un esempio più completo, che mostra come aggiungere un'animazione di diversi tipi di pennelli, vedere la [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="bb5e1-109">For a more complete sample, which shows how to animate different types of brushes, see the [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="bb5e1-110">Per altre informazioni sulle animazioni, vedere la [Cenni preliminari sull'animazione](animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bb5e1-110">For more information about animation, see the [Animation Overview](animation-overview.md).</span></span>  
  
 <span data-ttu-id="bb5e1-111">Per coerenza con altri esempi di animazione, nelle versioni del codice di questo esempio viene usano un <xref:System.Windows.Media.Animation.Storyboard> oggetto per applicare le animazioni.</span><span class="sxs-lookup"><span data-stu-id="bb5e1-111">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply their animations.</span></span> <span data-ttu-id="bb5e1-112">Tuttavia, quando si applica una sola animazione al codice, è più semplice usare il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo invece di usare un <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="bb5e1-112">However, when applying a single animation in code, it's simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="bb5e1-113">Per un esempio, vedere [Animare una proprietà senza utilizzare uno storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="bb5e1-113">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb5e1-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb5e1-114">See also</span></span>

- [<span data-ttu-id="bb5e1-115">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="bb5e1-115">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="bb5e1-116">Cenni preliminari sugli storyboard</span><span class="sxs-lookup"><span data-stu-id="bb5e1-116">Storyboards Overview</span></span>](storyboards-overview.md)
- <span data-ttu-id="bb5e1-117">[Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973) (Esempio di pennelli)</span><span class="sxs-lookup"><span data-stu-id="bb5e1-117">[Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973)</span></span>
