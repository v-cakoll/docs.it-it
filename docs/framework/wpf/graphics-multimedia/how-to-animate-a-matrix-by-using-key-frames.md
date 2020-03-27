---
title: 'Procedura: animare una matrice utilizzando fotogrammi chiave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: eb596cf728f8a7cc1964963b8509f42bdd7a392a
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344910"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a><span data-ttu-id="3f05c-102">Procedura: animare una matrice utilizzando fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="3f05c-102">How to: Animate a Matrix by Using Key Frames</span></span>
<span data-ttu-id="3f05c-103">In questo esempio viene <xref:System.Windows.Media.MatrixTransform.Matrix%2A> illustrato <xref:System.Windows.Media.MatrixTransform> come animare la proprietà di un utilizzando fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="3f05c-103">This example shows how to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f05c-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="3f05c-104">Example</span></span>  
 <span data-ttu-id="3f05c-105">Nell'esempio riportato di seguito viene utilizzata la <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> classe per animare la <xref:System.Windows.Media.MatrixTransform.Matrix%2A> proprietà di un <xref:System.Windows.Media.MatrixTransform>oggetto .</span><span class="sxs-lookup"><span data-stu-id="3f05c-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="3f05c-106">Nell'esempio <xref:System.Windows.Media.MatrixTransform> viene utilizzato l'oggetto per <xref:System.Windows.Controls.Button>trasformare l'aspetto e la posizione di un oggetto .</span><span class="sxs-lookup"><span data-stu-id="3f05c-106">The example uses the <xref:System.Windows.Media.MatrixTransform> object to transform the appearance and position of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="3f05c-107">Questa animazione <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> usa la classe per creare due fotogrammi chiave ed esegue le operazioni seguenti:This animation uses the class to create two key frames and does the following with them:</span><span class="sxs-lookup"><span data-stu-id="3f05c-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> class to create two key frames and does the following with them:</span></span>  
  
1. <span data-ttu-id="3f05c-108">Aggiunge un'animazione al primo <xref:System.Windows.Media.Matrix> durante i primi 0,2 secondi.</span><span class="sxs-lookup"><span data-stu-id="3f05c-108">Animates the first <xref:System.Windows.Media.Matrix> during the first 0.2 seconds.</span></span> <span data-ttu-id="3f05c-109">Nell'esempio <xref:System.Windows.Media.Matrix.M11%2A> vengono <xref:System.Windows.Media.Matrix.M12%2A> modificate <xref:System.Windows.Media.Matrix>le proprietà e dell'oggetto .</span><span class="sxs-lookup"><span data-stu-id="3f05c-109">The example changes the <xref:System.Windows.Media.Matrix.M11%2A> and <xref:System.Windows.Media.Matrix.M12%2A> properties of the <xref:System.Windows.Media.Matrix>.</span></span> <span data-ttu-id="3f05c-110">Questa modifica fa sì che il pulsante si allunghi e diventi inclinato.</span><span class="sxs-lookup"><span data-stu-id="3f05c-110">This change causes the button to stretch and become skewed.</span></span> <span data-ttu-id="3f05c-111">Nell'esempio vengono <xref:System.Windows.Media.Matrix.OffsetX%2A> <xref:System.Windows.Media.Matrix.OffsetY%2A> modificate anche le proprietà e in modo che il pulsante cambi posizione.</span><span class="sxs-lookup"><span data-stu-id="3f05c-111">The example also changes the <xref:System.Windows.Media.Matrix.OffsetX%2A> and <xref:System.Windows.Media.Matrix.OffsetY%2A> properties so that the button changes position.</span></span>  
  
2. <span data-ttu-id="3f05c-112">Aggiunge un'animazione al secondo <xref:System.Windows.Media.Matrix> a 1,0 secondi.</span><span class="sxs-lookup"><span data-stu-id="3f05c-112">Animates the second <xref:System.Windows.Media.Matrix> at 1.0 seconds.</span></span> <span data-ttu-id="3f05c-113">Il pulsante si sposta in un'altra posizione mentre il pulsante non è più inclinato o allungato.</span><span class="sxs-lookup"><span data-stu-id="3f05c-113">The button moves to another position while the button is no longer skewed or stretched.</span></span>  
  
3. <span data-ttu-id="3f05c-114">Ripete l'animazione all'infinito.</span><span class="sxs-lookup"><span data-stu-id="3f05c-114">Repeats the animation indefinitely.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f05c-115">I fotogrammi chiave <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> che derivano dall'oggetto creano salti improvvisi tra i valori, ovvero il movimento dell'animazione è a scatti.</span><span class="sxs-lookup"><span data-stu-id="3f05c-115">Key frames that derive from the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> object create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="3f05c-116">Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="3f05c-116">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f05c-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f05c-117">See also</span></span>

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [<span data-ttu-id="3f05c-118">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="3f05c-118">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="3f05c-119">Procedure relative ai fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="3f05c-119">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
