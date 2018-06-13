---
title: 'Procedura: riprodurre contenuto multimediale con animazioni'
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF], playback with animations
- playback of media [WPF], with animations
- animation [WPF], media playback with
- media [WPF], playback with animations
ms.assetid: 8982b7b7-1c6c-4b24-8801-b328862975f5
ms.openlocfilehash: 21c9b35828dca03c05def11cff22f1f1e33d45cc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560272"
---
# <a name="how-to-play-media-with-animations"></a><span data-ttu-id="d73e9-102">Procedura: riprodurre contenuto multimediale con animazioni</span><span class="sxs-lookup"><span data-stu-id="d73e9-102">How to: Play Media with Animations</span></span>
<span data-ttu-id="d73e9-103">In questo esempio viene illustrato come riprodurre i supporti e le animazioni contemporaneamente utilizzando il <xref:System.Windows.Media.MediaTimeline> e <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> classi nella stessa <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="d73e9-103">This example shows how to play media and animations at the same time by using the <xref:System.Windows.Media.MediaTimeline> and <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> classes in the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d73e9-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="d73e9-104">Example</span></span>  
 <span data-ttu-id="d73e9-105">È possibile utilizzare uno o più <xref:System.Windows.Media.MediaTimeline> gli oggetti in un <xref:System.Windows.Media.Animation.Storyboard> insieme alle altre <xref:System.Windows.Media.Animation.Timeline> oggetti, ad esempio animazioni.</span><span class="sxs-lookup"><span data-stu-id="d73e9-105">You can use one or more <xref:System.Windows.Media.MediaTimeline> objects in a <xref:System.Windows.Media.Animation.Storyboard> together with other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span>  
  
 <span data-ttu-id="d73e9-106">L'esempio seguente imposta il <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> proprietà del <xref:System.Windows.Media.Animation.Storyboard> su un valore di `Slip`, che specifica che l'animazione non quando avanza il contenuto multimediale (video in questo esempio).</span><span class="sxs-lookup"><span data-stu-id="d73e9-106">The following example sets the <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> property of the <xref:System.Windows.Media.Animation.Storyboard> to a value of `Slip`, which specifies that the animation does not progress until the media (video in this example) progresses.</span></span> <span data-ttu-id="d73e9-107">Questa funzionalità potrebbe essere necessaria se la riproduzione multimediale viene ritardata a causa del tempo di caricamento.</span><span class="sxs-lookup"><span data-stu-id="d73e9-107">This functionality might be needed if media playback is delayed because of loading time.</span></span>  
  
 [!code-xaml[MediaGallery_snippet#MediaTimelinePlusAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/MediaTimelinePlusAnimationExample.xaml#mediatimelineplusanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="d73e9-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d73e9-108">See Also</span></span>  
 <xref:System.Windows.Media.MediaTimeline>  
 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>  
 [<span data-ttu-id="d73e9-109">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="d73e9-109">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)  
 [<span data-ttu-id="d73e9-110">Cenni preliminari sugli storyboard</span><span class="sxs-lookup"><span data-stu-id="d73e9-110">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [<span data-ttu-id="d73e9-111">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="d73e9-111">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="d73e9-112">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="d73e9-112">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="d73e9-113">Grafica e funzionalità multimediali</span><span class="sxs-lookup"><span data-stu-id="d73e9-113">Graphics and Multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)
