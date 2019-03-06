---
title: 'Procedura: Riprodurre contenuti multimediali utilizzando un oggetto VideoDrawing'
ms.date: 03/30/2017
helpviewer_keywords:
- playback of media [WPF]
- classes [WPF], MediaPlayer
ms.assetid: 165d47ed-22ce-4ded-aa6a-aa9b7467de87
ms.openlocfilehash: 2397662c79af208f2528f6eedcd5995cfac9526c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363098"
---
# <a name="how-to-play-media-using-a-videodrawing"></a><span data-ttu-id="e3005-102">Procedura: Riprodurre contenuti multimediali utilizzando un oggetto VideoDrawing</span><span class="sxs-lookup"><span data-stu-id="e3005-102">How to: Play Media using a VideoDrawing</span></span>
<span data-ttu-id="e3005-103">Per riprodurre un file audio o video, si utilizza un <xref:System.Windows.Media.VideoDrawing> e un <xref:System.Windows.Media.MediaPlayer>.</span><span class="sxs-lookup"><span data-stu-id="e3005-103">To play an audio or video file, you use a <xref:System.Windows.Media.VideoDrawing> and a <xref:System.Windows.Media.MediaPlayer>.</span></span> <span data-ttu-id="e3005-104">È possibile caricare e riprodurre contenuti multimediali in due modi diversi.</span><span class="sxs-lookup"><span data-stu-id="e3005-104">There are two ways to load and play media.</span></span> <span data-ttu-id="e3005-105">Il primo consiste nell'usare un <xref:System.Windows.Media.MediaPlayer> e una <xref:System.Windows.Media.VideoDrawing> da soli e il secondo modo consiste nel creare il proprio <xref:System.Windows.Media.MediaTimeline> da usare con il <xref:System.Windows.Media.MediaPlayer> e <xref:System.Windows.Media.VideoDrawing>.</span><span class="sxs-lookup"><span data-stu-id="e3005-105">The first is to use a <xref:System.Windows.Media.MediaPlayer> and a <xref:System.Windows.Media.VideoDrawing> by themselves, and the second way is to create your own <xref:System.Windows.Media.MediaTimeline> to use with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e3005-106">Quando si distribuiscono contenuti multimediali con l'applicazione, non è possibile usare un file multimediale come risorsa di progetto, come avviene invece per un'immagine.</span><span class="sxs-lookup"><span data-stu-id="e3005-106">When distributing media with your application, you cannot use a media file as a project resource, like you would an image.</span></span> <span data-ttu-id="e3005-107">È necessario invece impostare il tipo di contenuto multimediale su `Content` nel file del progetto e `CopyToOutputDirectory` su `PreserveNewest` o su `Always`.</span><span class="sxs-lookup"><span data-stu-id="e3005-107">In your project file, you must instead set the media type to `Content` and set `CopyToOutputDirectory` to `PreserveNewest` or `Always`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3005-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="e3005-108">Example</span></span>  
 <span data-ttu-id="e3005-109">L'esempio seguente usa un' <xref:System.Windows.Media.VideoDrawing> e un <xref:System.Windows.Media.MediaPlayer> per riprodurre un file video sia una sola volta.</span><span class="sxs-lookup"><span data-stu-id="e3005-109">The following example uses a <xref:System.Windows.Media.VideoDrawing> and a <xref:System.Windows.Media.MediaPlayer> to play a video file once.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 <span data-ttu-id="e3005-110">Per ottenere ulteriore controllo della durata dei contenuti multimediali, usare una <xref:System.Windows.Media.MediaTimeline> con il <xref:System.Windows.Media.MediaPlayer> e <xref:System.Windows.Media.VideoDrawing> oggetti.</span><span class="sxs-lookup"><span data-stu-id="e3005-110">To gain additional timing control over the media, use a <xref:System.Windows.Media.MediaTimeline> with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing> objects.</span></span> <span data-ttu-id="e3005-111">Il <xref:System.Windows.Media.MediaTimeline> consente di specificare se il video deve essere ripetuto.</span><span class="sxs-lookup"><span data-stu-id="e3005-111">The <xref:System.Windows.Media.MediaTimeline> enables you to specify whether the video should repeat.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3005-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="e3005-112">Example</span></span>  
 <span data-ttu-id="e3005-113">L'esempio seguente usa un' <xref:System.Windows.Media.MediaTimeline> con il <xref:System.Windows.Media.MediaPlayer> e <xref:System.Windows.Media.VideoDrawing> oggetti da riprodurre ripetutamente un video.</span><span class="sxs-lookup"><span data-stu-id="e3005-113">The following example uses a <xref:System.Windows.Media.MediaTimeline> with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing> objects to play a video repeatedly.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 <span data-ttu-id="e3005-114">Si noti che, quando si usa una <xref:System.Windows.Media.MediaTimeline>, si usa l'oggetto interattivo <xref:System.Windows.Media.Animation.ClockController> restituiti dal <xref:System.Windows.Media.Animation.Clock.Controller%2A> proprietà del <xref:System.Windows.Media.MediaClock> per controllare la riproduzione multimediale anziché i metodi interattivi della <xref:System.Windows.Media.MediaPlayer>.</span><span class="sxs-lookup"><span data-stu-id="e3005-114">Note that, when you use a <xref:System.Windows.Media.MediaTimeline>, you use the interactive <xref:System.Windows.Media.Animation.ClockController> returned from the <xref:System.Windows.Media.Animation.Clock.Controller%2A> property of the <xref:System.Windows.Media.MediaClock> to control media playback instead of the interactive methods of <xref:System.Windows.Media.MediaPlayer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3005-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3005-115">See also</span></span>
- <xref:System.Windows.Media.VideoDrawing>
- [<span data-ttu-id="e3005-116">Cenni preliminari sugli oggetti Drawing</span><span class="sxs-lookup"><span data-stu-id="e3005-116">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
