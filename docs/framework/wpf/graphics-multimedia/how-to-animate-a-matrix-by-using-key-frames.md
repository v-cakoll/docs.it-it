---
title: "Procedura: Aggiungere un'animazione a una matrice usando fotogrammi chiave"
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: 8cc94117cc26f44288835fd85c6ded429124d3c6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107926"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a><span data-ttu-id="d795c-102">Procedura: Aggiungere un'animazione a una matrice usando fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="d795c-102">How to: Animate a Matrix by Using Key Frames</span></span>
<span data-ttu-id="d795c-103">In questo esempio illustra come animare la <xref:System.Windows.Media.MatrixTransform.Matrix%2A> proprietà di un <xref:System.Windows.Media.MatrixTransform> usando fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="d795c-103">This example shows how to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d795c-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="d795c-104">Example</span></span>  
 <span data-ttu-id="d795c-105">L'esempio seguente usa il <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> classe per animare la <xref:System.Windows.Media.MatrixTransform.Matrix%2A> proprietà di un <xref:System.Windows.Media.MatrixTransform>.</span><span class="sxs-lookup"><span data-stu-id="d795c-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="d795c-106">L'esempio Usa la <xref:System.Windows.Media.MatrixTransform> oggetto da trasformare l'aspetto e la posizione di un <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="d795c-106">The example uses the <xref:System.Windows.Media.MatrixTransform> object to transform the appearance and position of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="d795c-107">Questa animazione Usa il <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> classe per creare due fotogrammi chiave ed esegue le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="d795c-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> class to create two key frames and does the following with them:</span></span>  
  
1.  <span data-ttu-id="d795c-108">Aggiunge un'animazione prima <xref:System.Windows.Media.Matrix> durante i primi secondi 0,2.</span><span class="sxs-lookup"><span data-stu-id="d795c-108">Animates the first <xref:System.Windows.Media.Matrix> during the first 0.2 seconds.</span></span> <span data-ttu-id="d795c-109">Le modifiche di esempio il <xref:System.Windows.Media.Matrix.M11%2A> e <xref:System.Windows.Media.Matrix.M12%2A> delle proprietà del <xref:System.Windows.Media.Matrix>.</span><span class="sxs-lookup"><span data-stu-id="d795c-109">The example changes the <xref:System.Windows.Media.Matrix.M11%2A> and <xref:System.Windows.Media.Matrix.M12%2A> properties of the <xref:System.Windows.Media.Matrix>.</span></span> <span data-ttu-id="d795c-110">Questa modifica fa sì che il pulsante per l'estensione e diventare asimmetrici.</span><span class="sxs-lookup"><span data-stu-id="d795c-110">This change causes the button to stretch and become skewed.</span></span> <span data-ttu-id="d795c-111">Nell'esempio viene modificato anche il <xref:System.Windows.Media.Matrix.OffsetX%2A> e <xref:System.Windows.Media.Matrix.OffsetY%2A> proprietà in modo che il pulsante Cambia posizione.</span><span class="sxs-lookup"><span data-stu-id="d795c-111">The example also changes the <xref:System.Windows.Media.Matrix.OffsetX%2A> and <xref:System.Windows.Media.Matrix.OffsetY%2A> properties so that the button changes position.</span></span>  
  
2.  <span data-ttu-id="d795c-112">Aggiunge un'animazione secondo <xref:System.Windows.Media.Matrix> a 1,0 secondi.</span><span class="sxs-lookup"><span data-stu-id="d795c-112">Animates the second <xref:System.Windows.Media.Matrix> at 1.0 seconds.</span></span> <span data-ttu-id="d795c-113">Il pulsante si sposta in una posizione diversa mentre il pulsante non è più inclinato o esteso.</span><span class="sxs-lookup"><span data-stu-id="d795c-113">The button moves to another position while the button is no longer skewed or stretched.</span></span>  
  
3.  <span data-ttu-id="d795c-114">Si ripete per un periodo illimitato l'animazione.</span><span class="sxs-lookup"><span data-stu-id="d795c-114">Repeats the animation indefinitely.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d795c-115">Fotogrammi chiave che derivano dal <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> oggetto creano salti improvvisi tra valori, vale a dire lo spostamento dell'animazione è a scatti.</span><span class="sxs-lookup"><span data-stu-id="d795c-115">Key frames that derive from the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> object create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="d795c-116">Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="d795c-116">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d795c-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d795c-117">See also</span></span>

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [<span data-ttu-id="d795c-118">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="d795c-118">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="d795c-119">Procedure relative ai fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="d795c-119">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
