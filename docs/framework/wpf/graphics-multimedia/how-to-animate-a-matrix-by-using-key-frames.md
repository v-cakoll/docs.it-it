---
title: 'Procedura: animare una matrice utilizzando fotogrammi chiave'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 862e1afdcd823181dff0948fab43b1656b85f721
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a><span data-ttu-id="7950a-102">Procedura: animare una matrice utilizzando fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="7950a-102">How to: Animate a Matrix by Using Key Frames</span></span>
<span data-ttu-id="7950a-103">In questo esempio viene illustrato come animare la <xref:System.Windows.Media.MatrixTransform.Matrix%2A> proprietà di un <xref:System.Windows.Media.MatrixTransform> utilizzando fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="7950a-103">This example shows how to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7950a-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="7950a-104">Example</span></span>  
 <span data-ttu-id="7950a-105">L'esempio seguente usa il <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> classe da cui iniziare l'animazione di <xref:System.Windows.Media.MatrixTransform.Matrix%2A> proprietà di un <xref:System.Windows.Media.MatrixTransform>.</span><span class="sxs-lookup"><span data-stu-id="7950a-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="7950a-106">Nell'esempio viene utilizzato il <xref:System.Windows.Media.MatrixTransform> oggetto per trasformare l'aspetto e la posizione di un <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="7950a-106">The example uses the <xref:System.Windows.Media.MatrixTransform> object to transform the appearance and position of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="7950a-107">Viene utilizzata la <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> classe per creare due fotogrammi chiave ed esegue le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="7950a-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> class to create two key frames and does the following with them:</span></span>  
  
1.  <span data-ttu-id="7950a-108">Aggiunge un'animazione prima <xref:System.Windows.Media.Matrix> durante i primi 0,2 secondi.</span><span class="sxs-lookup"><span data-stu-id="7950a-108">Animates the first <xref:System.Windows.Media.Matrix> during the first 0.2 seconds.</span></span> <span data-ttu-id="7950a-109">Le modifiche di esempio di <xref:System.Windows.Media.Matrix.M11%2A> e <xref:System.Windows.Media.Matrix.M12%2A> le proprietà del <xref:System.Windows.Media.Matrix>.</span><span class="sxs-lookup"><span data-stu-id="7950a-109">The example changes the <xref:System.Windows.Media.Matrix.M11%2A> and <xref:System.Windows.Media.Matrix.M12%2A> properties of the <xref:System.Windows.Media.Matrix>.</span></span> <span data-ttu-id="7950a-110">Questa modifica, il pulsante per l'estensione e diventano asimmetrica.</span><span class="sxs-lookup"><span data-stu-id="7950a-110">This change causes the button to stretch and become skewed.</span></span> <span data-ttu-id="7950a-111">Nell'esempio viene modificato anche il <xref:System.Windows.Media.Matrix.OffsetX%2A> e <xref:System.Windows.Media.Matrix.OffsetY%2A> proprietà in modo che il pulsante Cambia posizione.</span><span class="sxs-lookup"><span data-stu-id="7950a-111">The example also changes the <xref:System.Windows.Media.Matrix.OffsetX%2A> and <xref:System.Windows.Media.Matrix.OffsetY%2A> properties so that the button changes position.</span></span>  
  
2.  <span data-ttu-id="7950a-112">Aggiunge un'animazione secondo <xref:System.Windows.Media.Matrix> a 1,0 secondi.</span><span class="sxs-lookup"><span data-stu-id="7950a-112">Animates the second <xref:System.Windows.Media.Matrix> at 1.0 seconds.</span></span> <span data-ttu-id="7950a-113">Pulsante Sposta in un'altra posizione, mentre il pulsante non è più appropriato o estesa.</span><span class="sxs-lookup"><span data-stu-id="7950a-113">The button moves to another position while the button is no longer skewed or stretched.</span></span>  
  
3.  <span data-ttu-id="7950a-114">Ripete l'animazione per un periodo illimitato.</span><span class="sxs-lookup"><span data-stu-id="7950a-114">Repeats the animation indefinitely.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7950a-115">Fotogrammi chiave che derivano dal <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> oggetto creano improvvisi tra due valori, vale a dire lo spostamento dell'animazione scatti.</span><span class="sxs-lookup"><span data-stu-id="7950a-115">Key frames that derive from the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> object create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="7950a-116">Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](http://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="7950a-116">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7950a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7950a-117">See Also</span></span>  
 <xref:System.Windows.Media.MatrixTransform.Matrix%2A>  
 <xref:System.Windows.Media.MatrixTransform>  
 [<span data-ttu-id="7950a-118">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="7950a-118">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="7950a-119">Procedure relative ai fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="7950a-119">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
