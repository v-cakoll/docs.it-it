---
title: 'Procedura: Controllare un oggetto MediaElement usando uno storyboard'
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
ms.openlocfilehash: ae785e11b1da0f2c408b24021ad46ab071419378
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59100314"
---
# <a name="how-to-control-a-mediaelement-by-using-a-storyboard"></a><span data-ttu-id="d33fd-102">Procedura: Controllare un oggetto MediaElement usando uno storyboard</span><span class="sxs-lookup"><span data-stu-id="d33fd-102">How to: Control a MediaElement by Using a Storyboard</span></span>
<span data-ttu-id="d33fd-103">In questo esempio viene illustrato come controllare un <xref:System.Windows.Controls.MediaElement> tramite un <xref:System.Windows.Media.MediaTimeline> in un <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="d33fd-103">This example shows how to control a <xref:System.Windows.Controls.MediaElement> by using a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d33fd-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="d33fd-104">Example</span></span>  
 <span data-ttu-id="d33fd-105">Quando si usa un' <xref:System.Windows.Media.MediaTimeline> in un <xref:System.Windows.Media.Animation.Storyboard> per controllare l'intervallo di un <xref:System.Windows.Controls.MediaElement>, la funzionalità è identica alla funzionalità di altri <xref:System.Windows.Media.Animation.Timeline> oggetti, ad esempio le animazioni.</span><span class="sxs-lookup"><span data-stu-id="d33fd-105">When you use a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard> to control the timing of a <xref:System.Windows.Controls.MediaElement>, the functionality is identical to the functionality of other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span> <span data-ttu-id="d33fd-106">Ad esempio, un <xref:System.Windows.Media.MediaTimeline> Usa <xref:System.Windows.Media.Animation.Timeline> le proprietà come il <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> proprietà per specificare quando deve essere avviata una <xref:System.Windows.Controls.MediaElement> (Avvia la riproduzione multimediale).</span><span class="sxs-lookup"><span data-stu-id="d33fd-106">For example, a <xref:System.Windows.Media.MediaTimeline> uses <xref:System.Windows.Media.Animation.Timeline> properties like the <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> property to specify when to start a <xref:System.Windows.Controls.MediaElement> (start media playback).</span></span> <span data-ttu-id="d33fd-107">Viene inoltre utilizzata la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> proprietà per specificare quanto tempo il <xref:System.Windows.Controls.MediaElement> è attivo (durata della riproduzione di contenuti multimediali).</span><span class="sxs-lookup"><span data-stu-id="d33fd-107">It also uses the <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property to specify how long the <xref:System.Windows.Controls.MediaElement> is active (duration of media playback).</span></span> <span data-ttu-id="d33fd-108">Per altre informazioni sull'uso <xref:System.Windows.Media.Animation.Timeline> gli oggetti con un <xref:System.Windows.Media.Animation.Storyboard>, vedere [Cenni preliminari sugli storyboard](storyboards-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d33fd-108">For more information about using <xref:System.Windows.Media.Animation.Timeline> objects with a <xref:System.Windows.Media.Animation.Storyboard>, see [Storyboards Overview](storyboards-overview.md).</span></span>  
  
 <span data-ttu-id="d33fd-109">In questo esempio viene illustrato come creare un semplice lettore multimediale che usa un <xref:System.Windows.Media.MediaTimeline> per controllare la riproduzione.</span><span class="sxs-lookup"><span data-stu-id="d33fd-109">This example shows how to create a simple media player that uses a <xref:System.Windows.Media.MediaTimeline> to control playback.</span></span> <span data-ttu-id="d33fd-110">Media player include riproduzione, pausa, riprendere e arrestare i pulsanti.</span><span class="sxs-lookup"><span data-stu-id="d33fd-110">The media player includes play, pause, resume, and stop buttons.</span></span> <span data-ttu-id="d33fd-111">Il giocatore ha anche un <xref:System.Windows.Controls.Slider> controllo che agisce come un indicatore di stato.</span><span class="sxs-lookup"><span data-stu-id="d33fd-111">The player also has a <xref:System.Windows.Controls.Slider> control that acts as a progress bar.</span></span>  
  
 <span data-ttu-id="d33fd-112">L'esempio seguente crea il [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] per il lettore multimediale.</span><span class="sxs-lookup"><span data-stu-id="d33fd-112">The following example creates the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] for the media player.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 <span data-ttu-id="d33fd-113">L'esempio seguente crea la funzionalità per l'indicatore di stato.</span><span class="sxs-lookup"><span data-stu-id="d33fd-113">The following example creates the functionality for the progress bar.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaTimelineExample.xaml.cs#codebehindmediatimelineexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml.vb#codebehindmediatimelineexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="d33fd-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d33fd-114">See also</span></span>

- <xref:System.Windows.Controls.MediaElement>
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [<span data-ttu-id="d33fd-115">Controllare un oggetto MediaElement (riproduzione, sospensione, interruzione, volume e velocità)</span><span class="sxs-lookup"><span data-stu-id="d33fd-115">Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)
- [<span data-ttu-id="d33fd-116">Cenni preliminari sugli storyboard</span><span class="sxs-lookup"><span data-stu-id="d33fd-116">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="d33fd-117">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="d33fd-117">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="d33fd-118">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="d33fd-118">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="d33fd-119">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="d33fd-119">How-to Topics</span></span>](audio-and-video-how-to-topics.md)
- [<span data-ttu-id="d33fd-120">Grafica e funzionalità multimediali</span><span class="sxs-lookup"><span data-stu-id="d33fd-120">Graphics and Multimedia</span></span>](index.md)
