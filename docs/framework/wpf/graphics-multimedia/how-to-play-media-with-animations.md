---
title: 'Procedura: Riprodurre contenuti multimediali con animazioni'
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF], playback with animations
- playback of media [WPF], with animations
- animation [WPF], media playback with
- media [WPF], playback with animations
ms.assetid: 8982b7b7-1c6c-4b24-8801-b328862975f5
ms.openlocfilehash: 0dc39d08ef17a628675018c17602623f2efd0173
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372906"
---
# <a name="how-to-play-media-with-animations"></a><span data-ttu-id="a20ea-102">Procedura: Riprodurre contenuti multimediali con animazioni</span><span class="sxs-lookup"><span data-stu-id="a20ea-102">How to: Play Media with Animations</span></span>
<span data-ttu-id="a20ea-103">Questo esempio viene illustrato come riprodurre contenuto multimediale e animazioni allo stesso tempo tramite il <xref:System.Windows.Media.MediaTimeline> e <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> classi nello stesso <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="a20ea-103">This example shows how to play media and animations at the same time by using the <xref:System.Windows.Media.MediaTimeline> and <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> classes in the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a20ea-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="a20ea-104">Example</span></span>  
 <span data-ttu-id="a20ea-105">È possibile usare uno o più <xref:System.Windows.Media.MediaTimeline> oggetti un <xref:System.Windows.Media.Animation.Storyboard> insieme alle altre <xref:System.Windows.Media.Animation.Timeline> oggetti, ad esempio le animazioni.</span><span class="sxs-lookup"><span data-stu-id="a20ea-105">You can use one or more <xref:System.Windows.Media.MediaTimeline> objects in a <xref:System.Windows.Media.Animation.Storyboard> together with other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span>  
  
 <span data-ttu-id="a20ea-106">L'esempio seguente imposta la <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> proprietà del <xref:System.Windows.Media.Animation.Storyboard> su un valore di `Slip`, che consente di specificare che l'animazione non avanza quando avanza il contenuto multimediale (video in questo esempio).</span><span class="sxs-lookup"><span data-stu-id="a20ea-106">The following example sets the <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> property of the <xref:System.Windows.Media.Animation.Storyboard> to a value of `Slip`, which specifies that the animation does not progress until the media (video in this example) progresses.</span></span> <span data-ttu-id="a20ea-107">Questa funzionalità potrebbe essere necessaria se la riproduzione multimediale viene ritardata a causa del tempo di caricamento.</span><span class="sxs-lookup"><span data-stu-id="a20ea-107">This functionality might be needed if media playback is delayed because of loading time.</span></span>  
  
 [!code-xaml[MediaGallery_snippet#MediaTimelinePlusAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/MediaTimelinePlusAnimationExample.xaml#mediatimelineplusanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="a20ea-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a20ea-108">See also</span></span>
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>
- <xref:System.Windows.Media.Animation.Storyboard>
- <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>
- [<span data-ttu-id="a20ea-109">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="a20ea-109">How-to Topics</span></span>](audio-and-video-how-to-topics.md)
- [<span data-ttu-id="a20ea-110">Cenni preliminari sugli storyboard</span><span class="sxs-lookup"><span data-stu-id="a20ea-110">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="a20ea-111">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="a20ea-111">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="a20ea-112">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="a20ea-112">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="a20ea-113">Grafica e funzionalità multimediali</span><span class="sxs-lookup"><span data-stu-id="a20ea-113">Graphics and Multimedia</span></span>](index.md)
