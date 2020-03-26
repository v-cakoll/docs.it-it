---
title: 'Procedura: ridimensionare un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
ms.openlocfilehash: 34d954f68747be9eedc0ef71634e0c18b411d260
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112050"
---
# <a name="how-to-scale-an-element"></a><span data-ttu-id="add5e-102">Procedura: ridimensionare un elemento</span><span class="sxs-lookup"><span data-stu-id="add5e-102">How to: Scale an Element</span></span>
<span data-ttu-id="add5e-103">In questo esempio viene <xref:System.Windows.Media.ScaleTransform> illustrato come utilizzare un oggetto per ridimensionare un elemento.</span><span class="sxs-lookup"><span data-stu-id="add5e-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to scale an element.</span></span>  
  
 <span data-ttu-id="add5e-104">Utilizzare <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> le <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> proprietà e per ridimensionare l'elemento in base al fattore specificato.</span><span class="sxs-lookup"><span data-stu-id="add5e-104">Use the <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> properties to resize the element by the factor you specify.</span></span> <span data-ttu-id="add5e-105">Ad esempio, <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> un valore pari a 1,5 estende l'elemento fino al 150% della larghezza originale.</span><span class="sxs-lookup"><span data-stu-id="add5e-105">For example, a <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> value of 1.5 stretches the element to 150 percent of its original width.</span></span> <span data-ttu-id="add5e-106">Un <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> valore pari a 0,5 riduce l'altezza di un elemento del 50%.</span><span class="sxs-lookup"><span data-stu-id="add5e-106">A <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> value of 0.5 shrinks the height of an element by 50 percent.</span></span>  
  
 <span data-ttu-id="add5e-107">Utilizzare <xref:System.Windows.Media.ScaleTransform.CenterX%2A> le <xref:System.Windows.Media.ScaleTransform.CenterY%2A> proprietà e per specificare il punto che è il centro dell'operazione di scala.</span><span class="sxs-lookup"><span data-stu-id="add5e-107">Use the <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> properties to specify the point that is the center of the scale operation.</span></span> <span data-ttu-id="add5e-108">Per impostazione <xref:System.Windows.Media.ScaleTransform> predefinita, un oggetto è centrato nel punto (0,0), che corrisponde all'angolo superiore sinistro del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="add5e-108">By default, a <xref:System.Windows.Media.ScaleTransform> is centered at the point (0,0), which corresponds to the upper-left corner of the rectangle.</span></span> <span data-ttu-id="add5e-109">Questo ha l'effetto di spostare l'elemento e anche <xref:System.Windows.Media.Transform>di farlo apparire più grande, perché quando si applica un , si modifica lo spazio delle coordinate in cui si trova l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="add5e-109">This has the effect of moving the element and also of making it appear larger, because when you apply a <xref:System.Windows.Media.Transform>, you change the coordinate space in which the object resides.</span></span>  
  
 <span data-ttu-id="add5e-110">Nell'esempio riportato di seguito viene utilizzato un <xref:System.Windows.Media.ScaleTransform> per <xref:System.Windows.Shapes.Rectangle>raddoppiare le dimensioni di un oggetto 50 per 50.</span><span class="sxs-lookup"><span data-stu-id="add5e-110">The following example uses a <xref:System.Windows.Media.ScaleTransform> to double the size of a 50-by-50 <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="add5e-111">Il <xref:System.Windows.Media.ScaleTransform> ha un valore pari a <xref:System.Windows.Media.ScaleTransform.CenterX%2A> 0 <xref:System.Windows.Media.ScaleTransform.CenterY%2A>(impostazione predefinita) per entrambi e .</span><span class="sxs-lookup"><span data-stu-id="add5e-111">The <xref:System.Windows.Media.ScaleTransform> has a value of 0 (the default) for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="add5e-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="add5e-112">Example</span></span>  
 [!code-xaml[transformsSample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 <span data-ttu-id="add5e-113">In genere, <xref:System.Windows.Media.ScaleTransform.CenterX%2A> <xref:System.Windows.Media.ScaleTransform.CenterY%2A> si imposta e al centro dell'oggetto che viene ridimensionato: (<xref:System.Windows.FrameworkElement.Width%2A>/2, <xref:System.Windows.FrameworkElement.Height%2A>/2).</span><span class="sxs-lookup"><span data-stu-id="add5e-113">Typically, you set <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> to the center of the object that is scaled: (<xref:System.Windows.FrameworkElement.Width%2A>/2, <xref:System.Windows.FrameworkElement.Height%2A>/2).</span></span>  
  
 <span data-ttu-id="add5e-114">Nell'esempio seguente <xref:System.Windows.Shapes.Rectangle> viene illustrato un altro che è raddoppiato nelle dimensioni; tuttavia, <xref:System.Windows.Media.ScaleTransform> questo ha un valore <xref:System.Windows.Media.ScaleTransform.CenterX%2A> <xref:System.Windows.Media.ScaleTransform.CenterY%2A>di 25 per entrambi e , che corrisponde al centro del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="add5e-114">The following example shows another <xref:System.Windows.Shapes.Rectangle> that is doubled in size; however, this <xref:System.Windows.Media.ScaleTransform> has a value of 25 for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, which corresponds to the center of the rectangle.</span></span>  
  
 [!code-xaml[transformsSample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 <span data-ttu-id="add5e-115">Nella figura seguente viene illustrata la differenza tra le due <xref:System.Windows.Media.ScaleTransform> operazioni.</span><span class="sxs-lookup"><span data-stu-id="add5e-115">The following illustration shows the difference between the two <xref:System.Windows.Media.ScaleTransform> operations.</span></span> <span data-ttu-id="add5e-116">La linea punteggiata indica le dimensioni e posizione del rettangolo prima del ridimensionamento.</span><span class="sxs-lookup"><span data-stu-id="add5e-116">The dotted line shows the size and position of the rectangle before scaling.</span></span>  
  
 <span data-ttu-id="add5e-117">![Ridimensionamenti con raddoppiamento di valore con punti centrali diversi](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span><span class="sxs-lookup"><span data-stu-id="add5e-117">![2x scales with different center points](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span></span>  
<span data-ttu-id="add5e-118">Due operazioni ScaleTransform con valori di ScaleX e ScaleY identici, ma con centri diversi</span><span class="sxs-lookup"><span data-stu-id="add5e-118">Two ScaleTransform operations with identical ScaleX and ScaleY values but different centers</span></span>  
  
 <span data-ttu-id="add5e-119">Per l'esempio completo, vedere Esempio di [trasformazioni 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span><span class="sxs-lookup"><span data-stu-id="add5e-119">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="add5e-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="add5e-120">See also</span></span>

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [<span data-ttu-id="add5e-121">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="add5e-121">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="add5e-122">Procedure relative</span><span class="sxs-lookup"><span data-stu-id="add5e-122">How-to Topics</span></span>](transformations-how-to-topics.md)
