---
title: 'Procedura: Ridimensionare un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
ms.openlocfilehash: 607b3a11085f746503c1b82552f1740b49d9ef5d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59131703"
---
# <a name="how-to-scale-an-element"></a><span data-ttu-id="b70a2-102">Procedura: Ridimensionare un elemento</span><span class="sxs-lookup"><span data-stu-id="b70a2-102">How to: Scale an Element</span></span>
<span data-ttu-id="b70a2-103">In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.ScaleTransform> per ridimensionare un elemento.</span><span class="sxs-lookup"><span data-stu-id="b70a2-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to scale an element.</span></span>  
  
 <span data-ttu-id="b70a2-104">Usare la <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> e <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> proprietà per ridimensionare l'elemento in base al fattore specificato.</span><span class="sxs-lookup"><span data-stu-id="b70a2-104">Use the <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> properties to resize the element by the factor you specify.</span></span> <span data-ttu-id="b70a2-105">Ad esempio, un <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> valore pari a 1,5 adatta l'elemento al 150% della sua larghezza originale.</span><span class="sxs-lookup"><span data-stu-id="b70a2-105">For example, a <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> value of 1.5 stretches the element to 150 percent of its original width.</span></span> <span data-ttu-id="b70a2-106">Oggetto <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> valore pari a 0,5 riduce l'altezza di un elemento del 50%.</span><span class="sxs-lookup"><span data-stu-id="b70a2-106">A <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> value of 0.5 shrinks the height of an element by 50 percent.</span></span>  
  
 <span data-ttu-id="b70a2-107">Usare la <xref:System.Windows.Media.ScaleTransform.CenterX%2A> e <xref:System.Windows.Media.ScaleTransform.CenterY%2A> proprietà per specificare il punto centrale dell'operazione di ridimensionamento.</span><span class="sxs-lookup"><span data-stu-id="b70a2-107">Use the <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> properties to specify the point that is the center of the scale operation.</span></span> <span data-ttu-id="b70a2-108">Per impostazione predefinita, un <xref:System.Windows.Media.ScaleTransform> è centrato al punto (0,0), che corrisponde all'angolo superiore sinistro del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="b70a2-108">By default, a <xref:System.Windows.Media.ScaleTransform> is centered at the point (0,0), which corresponds to the upper-left corner of the rectangle.</span></span> <span data-ttu-id="b70a2-109">Questo ha l'effetto dello spostamento dell'elemento e anche fare in modo che vengono visualizzati maggiori, perché quando si applica un <xref:System.Windows.Media.Transform>, si modifica lo spazio delle coordinate in cui risiede l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="b70a2-109">This has the effect of moving the element and also of making it appear larger, because when you apply a <xref:System.Windows.Media.Transform>, you change the coordinate space in which the object resides.</span></span>  
  
 <span data-ttu-id="b70a2-110">L'esempio seguente usa un' <xref:System.Windows.Media.ScaleTransform> raddoppiare le dimensioni di 50 per 50 <xref:System.Windows.Shapes.Rectangle>.</span><span class="sxs-lookup"><span data-stu-id="b70a2-110">The following example uses a <xref:System.Windows.Media.ScaleTransform> to double the size of a 50-by-50 <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="b70a2-111">Il <xref:System.Windows.Media.ScaleTransform> ha un valore pari a 0 (impostazione predefinita) per entrambi <xref:System.Windows.Media.ScaleTransform.CenterX%2A> e <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.</span><span class="sxs-lookup"><span data-stu-id="b70a2-111">The <xref:System.Windows.Media.ScaleTransform> has a value of 0 (the default) for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b70a2-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="b70a2-112">Example</span></span>  
 [!code-xaml[transformsSample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 <span data-ttu-id="b70a2-113">In genere, si imposta <xref:System.Windows.Media.ScaleTransform.CenterX%2A> e <xref:System.Windows.Media.ScaleTransform.CenterY%2A> al centro dell'oggetto che viene ridimensionato: (<xref:System.Windows.FrameworkElement.Width%2A>/2,  <xref:System.Windows.FrameworkElement.Height%2A> /2).</span><span class="sxs-lookup"><span data-stu-id="b70a2-113">Typically, you set <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> to the center of the object that is scaled: (<xref:System.Windows.FrameworkElement.Width%2A>/2, <xref:System.Windows.FrameworkElement.Height%2A>/2).</span></span>  
  
 <span data-ttu-id="b70a2-114">L'esempio seguente illustra un altro <xref:System.Windows.Shapes.Rectangle> raddoppiate dimensioni; tuttavia, ciò <xref:System.Windows.Media.ScaleTransform> ha un valore pari a 25 per entrambi <xref:System.Windows.Media.ScaleTransform.CenterX%2A> e <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, che corrisponde al centro del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="b70a2-114">The following example shows another <xref:System.Windows.Shapes.Rectangle> that is doubled in size; however, this <xref:System.Windows.Media.ScaleTransform> has a value of 25 for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, which corresponds to the center of the rectangle.</span></span>  
  
 [!code-xaml[transformsSample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 <span data-ttu-id="b70a2-115">La figura seguente mostra la differenza tra i due <xref:System.Windows.Media.ScaleTransform> operazioni.</span><span class="sxs-lookup"><span data-stu-id="b70a2-115">The following illustration shows the difference between the two <xref:System.Windows.Media.ScaleTransform> operations.</span></span> <span data-ttu-id="b70a2-116">La linea punteggiata indica le dimensioni e posizione del rettangolo prima del ridimensionamento.</span><span class="sxs-lookup"><span data-stu-id="b70a2-116">The dotted line shows the size and position of the rectangle before scaling.</span></span>  
  
 <span data-ttu-id="b70a2-117">![Scale 2x con punti centrali diversi](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span><span class="sxs-lookup"><span data-stu-id="b70a2-117">![2x scales with different center points](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span></span>  
<span data-ttu-id="b70a2-118">Due operazioni ScaleTransform con valori di ScaleX e ScaleY identici, ma con centri diversi</span><span class="sxs-lookup"><span data-stu-id="b70a2-118">Two ScaleTransform operations with identical ScaleX and ScaleY values but different centers</span></span>  
  
 <span data-ttu-id="b70a2-119">Per l'esempio completo, vedere [2-D Transforms Sample (Esempio di trasformazioni 2D)](https://go.microsoft.com/fwlink/?LinkID=158252).</span><span class="sxs-lookup"><span data-stu-id="b70a2-119">For the complete sample, see [2-D Transforms Sample](https://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b70a2-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b70a2-120">See also</span></span>

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [<span data-ttu-id="b70a2-121">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="b70a2-121">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="b70a2-122">Procedure relative</span><span class="sxs-lookup"><span data-stu-id="b70a2-122">How-to Topics</span></span>](transformations-how-to-topics.md)
