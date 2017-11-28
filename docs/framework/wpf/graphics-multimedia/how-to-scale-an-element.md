---
title: 'Procedura: ridimensionare un elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 23b3086452526e804bfdbe50bb0c134f33158f5d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-scale-an-element"></a><span data-ttu-id="7ff3c-102">Procedura: ridimensionare un elemento</span><span class="sxs-lookup"><span data-stu-id="7ff3c-102">How to: Scale an Element</span></span>
<span data-ttu-id="7ff3c-103">In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Media.ScaleTransform> per ridimensionare un elemento.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to scale an element.</span></span>  
  
 <span data-ttu-id="7ff3c-104">Utilizzare il <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> e <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> proprietà per ridimensionare l'elemento con il fattore specificato.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-104">Use the <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> properties to resize the element by the factor you specify.</span></span> <span data-ttu-id="7ff3c-105">Ad esempio, un <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> valore pari a 1,5 estende l'elemento per 150% della larghezza originale.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-105">For example, a <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> value of 1.5 stretches the element to 150 percent of its original width.</span></span> <span data-ttu-id="7ff3c-106">Oggetto <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> valore pari a 0,5 riduce l'altezza di un elemento del 50%.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-106">A <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> value of 0.5 shrinks the height of an element by 50 percent.</span></span>  
  
 <span data-ttu-id="7ff3c-107">Utilizzare il <xref:System.Windows.Media.ScaleTransform.CenterX%2A> e <xref:System.Windows.Media.ScaleTransform.CenterY%2A> le proprietà per specificare il punto centrale dell'operazione di ridimensionamento.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-107">Use the <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> properties to specify the point that is the center of the scale operation.</span></span> <span data-ttu-id="7ff3c-108">Per impostazione predefinita, un <xref:System.Windows.Media.ScaleTransform> viene centrata in corrispondenza del punto (0,0), che corrisponde all'angolo superiore sinistro del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-108">By default, a <xref:System.Windows.Media.ScaleTransform> is centered at the point (0,0), which corresponds to the upper-left corner of the rectangle.</span></span> <span data-ttu-id="7ff3c-109">Questo ha l'effetto di spostare l'elemento e anche appare più grande, poiché quando si applica un <xref:System.Windows.Media.Transform>, si modifica lo spazio delle coordinate in cui si trova l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-109">This has the effect of moving the element and also of making it appear larger, because when you apply a <xref:System.Windows.Media.Transform>, you change the coordinate space in which the object resides.</span></span>  
  
 <span data-ttu-id="7ff3c-110">Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.ScaleTransform> a raddoppiare le dimensioni di 50 x 50 <xref:System.Windows.Shapes.Rectangle>.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-110">The following example uses a <xref:System.Windows.Media.ScaleTransform> to double the size of a 50-by-50 <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="7ff3c-111">Il <xref:System.Windows.Media.ScaleTransform> ha un valore pari a 0 (impostazione predefinita) per entrambi <xref:System.Windows.Media.ScaleTransform.CenterX%2A> e <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-111">The <xref:System.Windows.Media.ScaleTransform> has a value of 0 (the default) for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ff3c-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="7ff3c-112">Example</span></span>  
 [!code-xaml[transformsSample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 <span data-ttu-id="7ff3c-113">In genere, si imposta <xref:System.Windows.Media.ScaleTransform.CenterX%2A> e <xref:System.Windows.Media.ScaleTransform.CenterY%2A> al centro dell'oggetto che viene ridimensionato: (<xref:System.Windows.FrameworkElement.Width%2A>/2,  <xref:System.Windows.FrameworkElement.Height%2A> /2).</span><span class="sxs-lookup"><span data-stu-id="7ff3c-113">Typically, you set <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> to the center of the object that is scaled: (<xref:System.Windows.FrameworkElement.Width%2A>/2, <xref:System.Windows.FrameworkElement.Height%2A>/2).</span></span>  
  
 <span data-ttu-id="7ff3c-114">Nell'esempio seguente viene illustrata un'altra <xref:System.Windows.Shapes.Rectangle> che è raddoppiato nelle dimensioni; tuttavia, questo <xref:System.Windows.Media.ScaleTransform> ha un valore pari a 25 per entrambi <xref:System.Windows.Media.ScaleTransform.CenterX%2A> e <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, che corrisponde al centro del rettangolo.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-114">The following example shows another <xref:System.Windows.Shapes.Rectangle> that is doubled in size; however, this <xref:System.Windows.Media.ScaleTransform> has a value of 25 for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, which corresponds to the center of the rectangle.</span></span>  
  
 [!code-xaml[transformsSample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 <span data-ttu-id="7ff3c-115">Nella figura seguente mostra la differenza tra i due <xref:System.Windows.Media.ScaleTransform> operazioni.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-115">The following illustration shows the difference between the two <xref:System.Windows.Media.ScaleTransform> operations.</span></span> <span data-ttu-id="7ff3c-116">La linea punteggiata indica le dimensioni e posizione del rettangolo prima del ridimensionamento.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-116">The dotted line shows the size and position of the rectangle before scaling.</span></span>  
  
 <span data-ttu-id="7ff3c-117">![Scale 2x con punti centrali diversi](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span><span class="sxs-lookup"><span data-stu-id="7ff3c-117">![2x scales with different center points](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span></span>  
<span data-ttu-id="7ff3c-118">Due operazioni ScaleTransform con valori di ScaleX e ScaleY identici, ma con centri diversi</span><span class="sxs-lookup"><span data-stu-id="7ff3c-118">Two ScaleTransform operations with identical ScaleX and ScaleY values but different centers</span></span>  
  
 <span data-ttu-id="7ff3c-119">Per l'esempio completo, vedere [2-D Transforms Sample (Esempio di trasformazioni 2D)](http://go.microsoft.com/fwlink/?LinkID=158252).</span><span class="sxs-lookup"><span data-stu-id="7ff3c-119">For the complete sample, see [2-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ff3c-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ff3c-120">See Also</span></span>  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.ScaleTransform>  
 [<span data-ttu-id="7ff3c-121">Cenni preliminari sulle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="7ff3c-121">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [<span data-ttu-id="7ff3c-122">Procedure relative</span><span class="sxs-lookup"><span data-stu-id="7ff3c-122">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
