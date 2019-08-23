---
title: 'Procedura: Riprodurre contenuti multimediali usando un oggetto VideoDrawing'
ms.date: 03/30/2017
helpviewer_keywords:
- playback of media [WPF]
- classes [WPF], MediaPlayer
ms.assetid: 165d47ed-22ce-4ded-aa6a-aa9b7467de87
ms.openlocfilehash: 2e2007525be770186a17cf9d2d42a7c52ba93fba
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956960"
---
# <a name="how-to-play-media-using-a-videodrawing"></a><span data-ttu-id="190d8-102">Procedura: Riprodurre contenuti multimediali usando un oggetto VideoDrawing</span><span class="sxs-lookup"><span data-stu-id="190d8-102">How to: Play Media using a VideoDrawing</span></span>
<span data-ttu-id="190d8-103">Per riprodurre un file audio o video, è possibile usare <xref:System.Windows.Media.VideoDrawing> un oggetto <xref:System.Windows.Media.MediaPlayer>e un oggetto.</span><span class="sxs-lookup"><span data-stu-id="190d8-103">To play an audio or video file, you use a <xref:System.Windows.Media.VideoDrawing> and a <xref:System.Windows.Media.MediaPlayer>.</span></span> <span data-ttu-id="190d8-104">È possibile caricare e riprodurre contenuti multimediali in due modi diversi.</span><span class="sxs-lookup"><span data-stu-id="190d8-104">There are two ways to load and play media.</span></span> <span data-ttu-id="190d8-105">Il primo consiste nell'usare un <xref:System.Windows.Media.MediaPlayer> oggetto e <xref:System.Windows.Media.VideoDrawing> un autonomo e il secondo modo consiste nel creare un oggetto <xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.MediaPlayer> personalizzato da usare con e <xref:System.Windows.Media.VideoDrawing>.</span><span class="sxs-lookup"><span data-stu-id="190d8-105">The first is to use a <xref:System.Windows.Media.MediaPlayer> and a <xref:System.Windows.Media.VideoDrawing> by themselves, and the second way is to create your own <xref:System.Windows.Media.MediaTimeline> to use with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="190d8-106">Quando si distribuiscono contenuti multimediali con l'applicazione, non è possibile usare un file multimediale come risorsa di progetto, come avviene invece per un'immagine.</span><span class="sxs-lookup"><span data-stu-id="190d8-106">When distributing media with your application, you cannot use a media file as a project resource, like you would an image.</span></span> <span data-ttu-id="190d8-107">È necessario invece impostare il tipo di contenuto multimediale su `Content` nel file del progetto e `CopyToOutputDirectory` su `PreserveNewest` o su `Always`.</span><span class="sxs-lookup"><span data-stu-id="190d8-107">In your project file, you must instead set the media type to `Content` and set `CopyToOutputDirectory` to `PreserveNewest` or `Always`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="190d8-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="190d8-108">Example</span></span>  
 <span data-ttu-id="190d8-109">Nell'esempio seguente vengono utilizzati <xref:System.Windows.Media.VideoDrawing> un oggetto <xref:System.Windows.Media.MediaPlayer> e un oggetto per riprodurre un file video una sola volta.</span><span class="sxs-lookup"><span data-stu-id="190d8-109">The following example uses a <xref:System.Windows.Media.VideoDrawing> and a <xref:System.Windows.Media.MediaPlayer> to play a video file once.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 <span data-ttu-id="190d8-110">Per ottenere un controllo temporale aggiuntivo sui supporti, utilizzare un <xref:System.Windows.Media.MediaTimeline> oggetto con <xref:System.Windows.Media.MediaPlayer> gli <xref:System.Windows.Media.VideoDrawing> oggetti e.</span><span class="sxs-lookup"><span data-stu-id="190d8-110">To gain additional timing control over the media, use a <xref:System.Windows.Media.MediaTimeline> with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing> objects.</span></span> <span data-ttu-id="190d8-111"><xref:System.Windows.Media.MediaTimeline> Consente di specificare se il video deve essere ripetuto.</span><span class="sxs-lookup"><span data-stu-id="190d8-111">The <xref:System.Windows.Media.MediaTimeline> enables you to specify whether the video should repeat.</span></span>  
  
## <a name="example"></a><span data-ttu-id="190d8-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="190d8-112">Example</span></span>  
 <span data-ttu-id="190d8-113">Nell'esempio seguente viene usato <xref:System.Windows.Media.MediaTimeline> un oggetto <xref:System.Windows.Media.MediaPlayer> con <xref:System.Windows.Media.VideoDrawing> gli oggetti e per riprodurre un video ripetutamente.</span><span class="sxs-lookup"><span data-stu-id="190d8-113">The following example uses a <xref:System.Windows.Media.MediaTimeline> with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing> objects to play a video repeatedly.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 <span data-ttu-id="190d8-114">Si noti che, quando si usa <xref:System.Windows.Media.MediaTimeline>un, si usa l' <xref:System.Windows.Media.Animation.ClockController> elemento interattivo restituito <xref:System.Windows.Media.Animation.Clock.Controller%2A> <xref:System.Windows.Media.MediaClock> dalla proprietà di per controllare la riproduzione dei supporti anziché i metodi interattivi di <xref:System.Windows.Media.MediaPlayer>.</span><span class="sxs-lookup"><span data-stu-id="190d8-114">Note that, when you use a <xref:System.Windows.Media.MediaTimeline>, you use the interactive <xref:System.Windows.Media.Animation.ClockController> returned from the <xref:System.Windows.Media.Animation.Clock.Controller%2A> property of the <xref:System.Windows.Media.MediaClock> to control media playback instead of the interactive methods of <xref:System.Windows.Media.MediaPlayer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="190d8-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="190d8-115">See also</span></span>

- <xref:System.Windows.Media.VideoDrawing>
- [<span data-ttu-id="190d8-116">Cenni preliminari sugli oggetti Drawing</span><span class="sxs-lookup"><span data-stu-id="190d8-116">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
