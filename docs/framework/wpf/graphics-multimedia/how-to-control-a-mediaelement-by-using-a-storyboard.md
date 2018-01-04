---
title: 'Procedura: controllare un MediaElement utilizzando uno storyboard'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- multimedia [WPF], controlling playback of media with Storyboards
- controlling playback of media [WPF], with Storyboards
- Storyboards [WPF], controlling playback of media with
- media [WPF], controlling playback with Storyboards
- playback of media [WPF], controlling with Storyboards
ms.assetid: 6128ca77-b826-4e36-b968-6f237157c543
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f52801ee3704c13ec5213cfc54b6392baa97e245
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-control-a-mediaelement-by-using-a-storyboard"></a><span data-ttu-id="a0221-102">Procedura: controllare un MediaElement utilizzando uno storyboard</span><span class="sxs-lookup"><span data-stu-id="a0221-102">How to: Control a MediaElement by Using a Storyboard</span></span>
<span data-ttu-id="a0221-103">In questo esempio viene illustrato come controllare un <xref:System.Windows.Controls.MediaElement> utilizzando un <xref:System.Windows.Media.MediaTimeline> in un <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="a0221-103">This example shows how to control a <xref:System.Windows.Controls.MediaElement> by using a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0221-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="a0221-104">Example</span></span>  
 <span data-ttu-id="a0221-105">Quando si utilizza un <xref:System.Windows.Media.MediaTimeline> in un <xref:System.Windows.Media.Animation.Storyboard> per controllare l'intervallo di un <xref:System.Windows.Controls.MediaElement>, la funzionalità è identica alla funzionalità di altri <xref:System.Windows.Media.Animation.Timeline> oggetti, ad esempio animazioni.</span><span class="sxs-lookup"><span data-stu-id="a0221-105">When you use a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard> to control the timing of a <xref:System.Windows.Controls.MediaElement>, the functionality is identical to the functionality of other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span> <span data-ttu-id="a0221-106">Ad esempio, un <xref:System.Windows.Media.MediaTimeline> Usa <xref:System.Windows.Media.Animation.Timeline> proprietà quali il <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> proprietà per specificare quando avviare un <xref:System.Windows.Controls.MediaElement> (avvio riproduzione).</span><span class="sxs-lookup"><span data-stu-id="a0221-106">For example, a <xref:System.Windows.Media.MediaTimeline> uses <xref:System.Windows.Media.Animation.Timeline> properties like the <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> property to specify when to start a <xref:System.Windows.Controls.MediaElement> (start media playback).</span></span> <span data-ttu-id="a0221-107">Utilizza inoltre il <xref:System.Windows.Media.Animation.Timeline.Duration%2A> proprietà per specificare il tempo <xref:System.Windows.Controls.MediaElement> è attivo (durata della riproduzione).</span><span class="sxs-lookup"><span data-stu-id="a0221-107">It also uses the <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property to specify how long the <xref:System.Windows.Controls.MediaElement> is active (duration of media playback).</span></span> <span data-ttu-id="a0221-108">Per ulteriori informazioni sull'utilizzo <xref:System.Windows.Media.Animation.Timeline> gli oggetti con un <xref:System.Windows.Media.Animation.Storyboard>, vedere [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a0221-108">For more information about using <xref:System.Windows.Media.Animation.Timeline> objects with a <xref:System.Windows.Media.Animation.Storyboard>, see [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).</span></span>  
  
 <span data-ttu-id="a0221-109">In questo esempio viene illustrato come creare un lettore multimediale semplice che utilizza un <xref:System.Windows.Media.MediaTimeline> per controllare la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="a0221-109">This example shows how to create a simple media player that uses a <xref:System.Windows.Media.MediaTimeline> to control playback.</span></span> <span data-ttu-id="a0221-110">Il lettore multimediale include play, sospendere, riprendere e arrestare i pulsanti.</span><span class="sxs-lookup"><span data-stu-id="a0221-110">The media player includes play, pause, resume, and stop buttons.</span></span> <span data-ttu-id="a0221-111">Il lettore ha anche un <xref:System.Windows.Controls.Slider> controllo che funge da una barra di stato.</span><span class="sxs-lookup"><span data-stu-id="a0221-111">The player also has a <xref:System.Windows.Controls.Slider> control that acts as a progress bar.</span></span>  
  
 <span data-ttu-id="a0221-112">Nell'esempio seguente viene creata la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] per il lettore multimediale.</span><span class="sxs-lookup"><span data-stu-id="a0221-112">The following example creates the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] for the media player.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaTimelineExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 <span data-ttu-id="a0221-113">Nell'esempio seguente viene creata la funzionalità per l'indicatore di stato.</span><span class="sxs-lookup"><span data-stu-id="a0221-113">The following example creates the functionality for the progress bar.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaTimelineExample.xaml.cs#codebehindmediatimelineexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml.vb#codebehindmediatimelineexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="a0221-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0221-114">See Also</span></span>  
 <xref:System.Windows.Controls.MediaElement>  
 <xref:System.Windows.Media.MediaTimeline>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 [<span data-ttu-id="a0221-115">Controllare un oggetto MediaElement (riproduzione, sospensione, interruzione, volume e velocità)</span><span class="sxs-lookup"><span data-stu-id="a0221-115">Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)  
 [<span data-ttu-id="a0221-116">Cenni preliminari sugli storyboard</span><span class="sxs-lookup"><span data-stu-id="a0221-116">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [<span data-ttu-id="a0221-117">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="a0221-117">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="a0221-118">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="a0221-118">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="a0221-119">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="a0221-119">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)  
 [<span data-ttu-id="a0221-120">Grafica e funzionalità multimediali</span><span class="sxs-lookup"><span data-stu-id="a0221-120">Graphics and Multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)
