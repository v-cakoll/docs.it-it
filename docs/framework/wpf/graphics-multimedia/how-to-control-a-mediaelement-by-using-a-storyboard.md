---
title: 'Procedura: controllare un MediaElement utilizzando uno storyboard'
description: Controllare la riproduzione dei supporti usando uno storyboard in Windows Presentation Foundation (WPF). Si consideri questo esempio per la creazione di un semplice lettore multimediale.
ms.date: 03/30/2017
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
ms.openlocfilehash: 5a5e41b9a28211495fd3374c1a51a655dd867bca
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853729"
---
# <a name="how-to-control-a-mediaelement-by-using-a-storyboard"></a><span data-ttu-id="fcd4a-104">Procedura: controllare un MediaElement utilizzando uno storyboard</span><span class="sxs-lookup"><span data-stu-id="fcd4a-104">How to: Control a MediaElement by Using a Storyboard</span></span>
<span data-ttu-id="fcd4a-105">Questo esempio Mostra come controllare un oggetto <xref:System.Windows.Controls.MediaElement> usando un oggetto <xref:System.Windows.Media.MediaTimeline> in un oggetto <xref:System.Windows.Media.Animation.Storyboard> .</span><span class="sxs-lookup"><span data-stu-id="fcd4a-105">This example shows how to control a <xref:System.Windows.Controls.MediaElement> by using a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fcd4a-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="fcd4a-106">Example</span></span>  
 <span data-ttu-id="fcd4a-107">Quando si utilizza un oggetto <xref:System.Windows.Media.MediaTimeline> in un oggetto <xref:System.Windows.Media.Animation.Storyboard> per controllare l'intervallo di un oggetto <xref:System.Windows.Controls.MediaElement> , la funzionalità è identica alla funzionalità di altri <xref:System.Windows.Media.Animation.Timeline> oggetti, ad esempio le animazioni.</span><span class="sxs-lookup"><span data-stu-id="fcd4a-107">When you use a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard> to control the timing of a <xref:System.Windows.Controls.MediaElement>, the functionality is identical to the functionality of other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span> <span data-ttu-id="fcd4a-108">Un oggetto, ad esempio, <xref:System.Windows.Media.MediaTimeline> utilizza <xref:System.Windows.Media.Animation.Timeline> proprietà come la <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> proprietà per specificare quando avviare un <xref:System.Windows.Controls.MediaElement> (avvio della riproduzione multimediale).</span><span class="sxs-lookup"><span data-stu-id="fcd4a-108">For example, a <xref:System.Windows.Media.MediaTimeline> uses <xref:System.Windows.Media.Animation.Timeline> properties like the <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> property to specify when to start a <xref:System.Windows.Controls.MediaElement> (start media playback).</span></span> <span data-ttu-id="fcd4a-109">USA anche la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> proprietà per specificare per quanto tempo <xref:System.Windows.Controls.MediaElement> è attivo (durata della riproduzione dei supporti).</span><span class="sxs-lookup"><span data-stu-id="fcd4a-109">It also uses the <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property to specify how long the <xref:System.Windows.Controls.MediaElement> is active (duration of media playback).</span></span> <span data-ttu-id="fcd4a-110">Per ulteriori informazioni sull'utilizzo di <xref:System.Windows.Media.Animation.Timeline> oggetti con un <xref:System.Windows.Media.Animation.Storyboard> , vedere [Cenni preliminari sugli storyboard](storyboards-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fcd4a-110">For more information about using <xref:System.Windows.Media.Animation.Timeline> objects with a <xref:System.Windows.Media.Animation.Storyboard>, see [Storyboards Overview](storyboards-overview.md).</span></span>  
  
 <span data-ttu-id="fcd4a-111">Questo esempio illustra come creare un semplice lettore multimediale che usa un <xref:System.Windows.Media.MediaTimeline> per controllare la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="fcd4a-111">This example shows how to create a simple media player that uses a <xref:System.Windows.Media.MediaTimeline> to control playback.</span></span> <span data-ttu-id="fcd4a-112">Il lettore multimediale include i pulsanti Riproduci, Sospendi, Riprendi e arresta.</span><span class="sxs-lookup"><span data-stu-id="fcd4a-112">The media player includes play, pause, resume, and stop buttons.</span></span> <span data-ttu-id="fcd4a-113">Il lettore dispone anche di un <xref:System.Windows.Controls.Slider> controllo che funge da indicatore di stato.</span><span class="sxs-lookup"><span data-stu-id="fcd4a-113">The player also has a <xref:System.Windows.Controls.Slider> control that acts as a progress bar.</span></span>  
  
 <span data-ttu-id="fcd4a-114">Nell'esempio seguente viene creato [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] per il lettore multimediale.</span><span class="sxs-lookup"><span data-stu-id="fcd4a-114">The following example creates the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] for the media player.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 <span data-ttu-id="fcd4a-115">Nell'esempio seguente viene creata la funzionalità per l'indicatore di stato.</span><span class="sxs-lookup"><span data-stu-id="fcd4a-115">The following example creates the functionality for the progress bar.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaTimelineExample.xaml.cs#codebehindmediatimelineexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml.vb#codebehindmediatimelineexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="fcd4a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fcd4a-116">See also</span></span>

- <xref:System.Windows.Controls.MediaElement>
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [<span data-ttu-id="fcd4a-117">Controllare un oggetto MediaElement (riproduzione, sospensione, interruzione, volume e velocità)</span><span class="sxs-lookup"><span data-stu-id="fcd4a-117">Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)
- [<span data-ttu-id="fcd4a-118">Cenni preliminari sugli storyboard</span><span class="sxs-lookup"><span data-stu-id="fcd4a-118">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="fcd4a-119">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="fcd4a-119">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="fcd4a-120">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="fcd4a-120">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="fcd4a-121">Procedure</span><span class="sxs-lookup"><span data-stu-id="fcd4a-121">How-to Topics</span></span>](audio-and-video-how-to-topics.md)
- [<span data-ttu-id="fcd4a-122">Grafica e Multimedia</span><span class="sxs-lookup"><span data-stu-id="fcd4a-122">Graphics and Multimedia</span></span>](index.md)
