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
ms.openlocfilehash: 2457bdb794d81e7c482f735cad4ade34564328e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559324"
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a><span data-ttu-id="ac5a2-102">Procedura: aggiungere un'animazione al colore o all'opacità di un oggetto SolidColorBrush</span><span class="sxs-lookup"><span data-stu-id="ac5a2-102">How to: Animate the Color or Opacity of a SolidColorBrush</span></span>
<span data-ttu-id="ac5a2-103">In questo esempio viene illustrato come animare la <xref:System.Windows.Media.SolidColorBrush.Color%2A> e <xref:System.Windows.Media.Brush.Opacity%2A> di un <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="ac5a2-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac5a2-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="ac5a2-104">Example</span></span>  
 <span data-ttu-id="ac5a2-105">L'esempio seguente usa tre animazioni per animare la <xref:System.Windows.Media.SolidColorBrush.Color%2A> e <xref:System.Windows.Media.Brush.Opacity%2A> di un <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="ac5a2-105">The following example uses three animations to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
-   <span data-ttu-id="ac5a2-106">La prima animazione, un <xref:System.Windows.Media.Animation.ColorAnimation>, modifica il colore del pennello per <xref:System.Windows.Media.Colors.Gray%2A> quando il mouse viene spostato il rettangolo.</span><span class="sxs-lookup"><span data-stu-id="ac5a2-106">The first animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Gray%2A> when the mouse enters the rectangle.</span></span>  
  
-   <span data-ttu-id="ac5a2-107">La successiva animazione, un altro <xref:System.Windows.Media.Animation.ColorAnimation>, modifica il colore del pennello per <xref:System.Windows.Media.Colors.Orange%2A> quando il puntatore del mouse esce dall'area del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="ac5a2-107">The next animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Orange%2A> when the mouse leaves the rectangle.</span></span>  
  
-   <span data-ttu-id="ac5a2-108">L'ultima animazione, un <xref:System.Windows.Media.Animation.DoubleAnimation>, cambia l'opacità del pennello in 0,0 quando viene premuto il pulsante sinistro del mouse.</span><span class="sxs-lookup"><span data-stu-id="ac5a2-108">The final animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, changes the brush's opacity to 0.0 when the left mouse button is pressed.</span></span>  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 <span data-ttu-id="ac5a2-109">Per un esempio più completo che illustra come aggiungere un'animazione a tipi diversi di pennelli, vedere il [esempio](http://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="ac5a2-109">For a more complete sample, which shows how to animate different types of brushes, see the [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="ac5a2-110">Per ulteriori informazioni sull'animazione, vedere il [panoramica dell'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ac5a2-110">For more information about animation, see the [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span>  
  
 <span data-ttu-id="ac5a2-111">Per coerenza con gli altri esempi di animazione, nelle versioni del codice di questo esempio viene utilizzato un <xref:System.Windows.Media.Animation.Storyboard> oggetto a cui applicare le animazioni.</span><span class="sxs-lookup"><span data-stu-id="ac5a2-111">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply their animations.</span></span> <span data-ttu-id="ac5a2-112">Tuttavia, quando si applica un'animazione sola nel codice, è più semplice l'utilizzo di <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo anziché un <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="ac5a2-112">However, when applying a single animation in code, it's simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="ac5a2-113">Per un esempio, vedere [Animare una proprietà senza utilizzare uno storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="ac5a2-113">For an example, see [Animate a Property Without Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac5a2-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac5a2-114">See Also</span></span>  
 [<span data-ttu-id="ac5a2-115">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="ac5a2-115">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="ac5a2-116">Cenni preliminari sugli storyboard</span><span class="sxs-lookup"><span data-stu-id="ac5a2-116">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 <span data-ttu-id="ac5a2-117">[Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973) (Esempio di pennelli)</span><span class="sxs-lookup"><span data-stu-id="ac5a2-117">[Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973)</span></span>
