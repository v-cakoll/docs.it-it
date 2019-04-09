---
title: "Procedura: Aggiungere un'animazione a un oggetto usando fotogrammi chiave"
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: 0b2b517410c6cbc4f3deca13e5948c8de583fd3d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59177801"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a><span data-ttu-id="0e914-102">Procedura: Aggiungere un'animazione a un oggetto usando fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="0e914-102">How to: Animate an Object by Using Key Frames</span></span>
<span data-ttu-id="0e914-103">In questo esempio illustra come animare un oggetto, che in questo esempio è il <xref:System.Windows.Controls.Page.Background%2A> proprietà di un <xref:System.Windows.Controls.Page> controllo, usando fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="0e914-103">This example shows how to animate an object, which in this example is the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e914-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="0e914-104">Example</span></span>  
 <span data-ttu-id="0e914-105">L'esempio seguente usa il <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> classe per animare il colore cambia per il <xref:System.Windows.Controls.Page.Background%2A> proprietà di un <xref:System.Windows.Controls.Page> controllo.</span><span class="sxs-lookup"><span data-stu-id="0e914-105">The following example uses the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class to animate color changes for the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control.</span></span> <span data-ttu-id="0e914-106">L'animazione di esempio modifica di un pennello di sfondo differente a intervalli regolari.</span><span class="sxs-lookup"><span data-stu-id="0e914-106">The example animation changes to a different background brush at regular intervals.</span></span> <span data-ttu-id="0e914-107">Questa animazione Usa il <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> classe per creare tre fotogrammi chiave diversi.</span><span class="sxs-lookup"><span data-stu-id="0e914-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> class to create three different key frames.</span></span> <span data-ttu-id="0e914-108">L'animazione Usa i fotogrammi chiave nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="0e914-108">The animation uses key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="0e914-109">Alla fine del secondo prima, aggiunge un'animazione a un'istanza di <xref:System.Windows.Media.LinearGradientBrush> classe.</span><span class="sxs-lookup"><span data-stu-id="0e914-109">At the end of the first second, animates an instance of the <xref:System.Windows.Media.LinearGradientBrush> class.</span></span> <span data-ttu-id="0e914-110">In questa sezione dell'esempio applica una sfumatura lineare per il colore di sfondo in modo che il colore di transizione da giallo a arancione e impostato su rosso.</span><span class="sxs-lookup"><span data-stu-id="0e914-110">This section of the example applies a linear gradient to the background color so that the color transitions from yellow to orange to red.</span></span>  
  
2.  <span data-ttu-id="0e914-111">Alla fine del secondo successivo, aggiunge un'animazione a un'istanza di <xref:System.Windows.Media.RadialGradientBrush> classe.</span><span class="sxs-lookup"><span data-stu-id="0e914-111">At the end of the next second, animates an instance of the <xref:System.Windows.Media.RadialGradientBrush> class.</span></span> <span data-ttu-id="0e914-112">In questa sezione dell'esempio applica una sfumatura radiale per il colore di sfondo in modo che passa il colore da bianco a blu su nero.</span><span class="sxs-lookup"><span data-stu-id="0e914-112">This section of the example applies a radial gradient to the background color so that the color transitions from white to blue to black.</span></span>  
  
3.  <span data-ttu-id="0e914-113">Alla fine del secondo terzo, aggiunge un'animazione a un'istanza di <xref:System.Windows.Media.DrawingBrush> classe.</span><span class="sxs-lookup"><span data-stu-id="0e914-113">At the end of the third second, animates an instance of the <xref:System.Windows.Media.DrawingBrush> class.</span></span> <span data-ttu-id="0e914-114">Questa sezione dell'esempio riguarda un motivo a scacchi allo sfondo.</span><span class="sxs-lookup"><span data-stu-id="0e914-114">This section of the example applies a checkerboard pattern to the background.</span></span>  
  
4.  <span data-ttu-id="0e914-115">L'animazione viene avviato nuovamente e viene ripetuta all'infinito.</span><span class="sxs-lookup"><span data-stu-id="0e914-115">The animation begins again and repeats indefinitely.</span></span>  
  
> [!NOTE]
>  <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> <span data-ttu-id="0e914-116">è l'unico tipo di fotogramma chiave che è possibile usare con il <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> classe.</span><span class="sxs-lookup"><span data-stu-id="0e914-116">is the only type of key frame that you can use with the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class.</span></span> <span data-ttu-id="0e914-117">Fotogrammi chiave, ad esempio <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> creano cambiamenti improvvisi nei valori, vale a dire, le modifiche di colore in questo esempio si verificano improvvisamente.</span><span class="sxs-lookup"><span data-stu-id="0e914-117">Key frames like <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> create sudden changes in values, that is, the color changes in this example occur suddenly.</span></span>  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="0e914-118">Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="0e914-118">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e914-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e914-119">See also</span></span>

- <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.Page.Background%2A>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>
- <xref:System.Windows.Media.LinearGradientBrush>
- <xref:System.Windows.Media.RadialGradientBrush>
- <xref:System.Windows.Media.DrawingBrush>
- [<span data-ttu-id="0e914-120">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="0e914-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="0e914-121">Procedure relative ai fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="0e914-121">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
