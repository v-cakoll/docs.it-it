---
title: 'Procedura: riprodurre contenuti multimediali utilizzando un oggetto VideoDrawing'
ms.date: 03/30/2017
helpviewer_keywords:
- playback of media [WPF]
- classes [WPF], MediaPlayer
ms.assetid: 165d47ed-22ce-4ded-aa6a-aa9b7467de87
ms.openlocfilehash: 27959cc967eac0a0f642da079f8758b0f756800e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560971"
---
# <a name="how-to-play-media-using-a-videodrawing"></a><span data-ttu-id="9c5e7-102">Procedura: riprodurre contenuti multimediali utilizzando un oggetto VideoDrawing</span><span class="sxs-lookup"><span data-stu-id="9c5e7-102">How to: Play Media using a VideoDrawing</span></span>
<span data-ttu-id="9c5e7-103">Per riprodurre un file audio o video, si utilizza un <xref:System.Windows.Media.VideoDrawing> e <xref:System.Windows.Media.MediaPlayer>.</span><span class="sxs-lookup"><span data-stu-id="9c5e7-103">To play an audio or video file, you use a <xref:System.Windows.Media.VideoDrawing> and a <xref:System.Windows.Media.MediaPlayer>.</span></span> <span data-ttu-id="9c5e7-104">È possibile caricare e riprodurre contenuti multimediali in due modi diversi.</span><span class="sxs-lookup"><span data-stu-id="9c5e7-104">There are two ways to load and play media.</span></span> <span data-ttu-id="9c5e7-105">Il primo consiste nell'usare un <xref:System.Windows.Media.MediaPlayer> e <xref:System.Windows.Media.VideoDrawing> da se stessi, mentre la seconda consiste nel crearne di proprie <xref:System.Windows.Media.MediaTimeline> da utilizzare con il <xref:System.Windows.Media.MediaPlayer> e <xref:System.Windows.Media.VideoDrawing>.</span><span class="sxs-lookup"><span data-stu-id="9c5e7-105">The first is to use a <xref:System.Windows.Media.MediaPlayer> and a <xref:System.Windows.Media.VideoDrawing> by themselves, and the second way is to create your own <xref:System.Windows.Media.MediaTimeline> to use with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9c5e7-106">Quando si distribuiscono contenuti multimediali con l'applicazione, non è possibile usare un file multimediale come risorsa di progetto, come avviene invece per un'immagine.</span><span class="sxs-lookup"><span data-stu-id="9c5e7-106">When distributing media with your application, you cannot use a media file as a project resource, like you would an image.</span></span> <span data-ttu-id="9c5e7-107">È necessario invece impostare il tipo di contenuto multimediale su `Content` nel file del progetto e `CopyToOutputDirectory` su `PreserveNewest` o su `Always`.</span><span class="sxs-lookup"><span data-stu-id="9c5e7-107">In your project file, you must instead set the media type to `Content` and set `CopyToOutputDirectory` to `PreserveNewest` or `Always`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c5e7-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="9c5e7-108">Example</span></span>  
 <span data-ttu-id="9c5e7-109">Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.VideoDrawing> e <xref:System.Windows.Media.MediaPlayer> per riprodurre un file video, una volta.</span><span class="sxs-lookup"><span data-stu-id="9c5e7-109">The following example uses a <xref:System.Windows.Media.VideoDrawing> and a <xref:System.Windows.Media.MediaPlayer> to play a video file once.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 <span data-ttu-id="9c5e7-110">Per un ulteriore controllo della durata dei contenuti multimediali, utilizzare un <xref:System.Windows.Media.MediaTimeline> con il <xref:System.Windows.Media.MediaPlayer> e <xref:System.Windows.Media.VideoDrawing> oggetti.</span><span class="sxs-lookup"><span data-stu-id="9c5e7-110">To gain additional timing control over the media, use a <xref:System.Windows.Media.MediaTimeline> with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing> objects.</span></span> <span data-ttu-id="9c5e7-111">Il <xref:System.Windows.Media.MediaTimeline> consente di specificare se deve essere ripetuto il video.</span><span class="sxs-lookup"><span data-stu-id="9c5e7-111">The <xref:System.Windows.Media.MediaTimeline> enables you to specify whether the video should repeat.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c5e7-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="9c5e7-112">Example</span></span>  
 <span data-ttu-id="9c5e7-113">Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.MediaTimeline> con il <xref:System.Windows.Media.MediaPlayer> e <xref:System.Windows.Media.VideoDrawing> oggetti venga eseguita più volte un video.</span><span class="sxs-lookup"><span data-stu-id="9c5e7-113">The following example uses a <xref:System.Windows.Media.MediaTimeline> with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing> objects to play a video repeatedly.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 <span data-ttu-id="9c5e7-114">Si noti che, quando si utilizza un <xref:System.Windows.Media.MediaTimeline>, utilizzare l'oggetto interattivo <xref:System.Windows.Media.Animation.ClockController> restituito dal <xref:System.Windows.Media.Animation.Clock.Controller%2A> proprietà del <xref:System.Windows.Media.MediaClock> per controllare la riproduzione multimediale anziché i metodi interattivi di <xref:System.Windows.Media.MediaPlayer>.</span><span class="sxs-lookup"><span data-stu-id="9c5e7-114">Note that, when you use a <xref:System.Windows.Media.MediaTimeline>, you use the interactive <xref:System.Windows.Media.Animation.ClockController> returned from the <xref:System.Windows.Media.Animation.Clock.Controller%2A> property of the <xref:System.Windows.Media.MediaClock> to control media playback instead of the interactive methods of <xref:System.Windows.Media.MediaPlayer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c5e7-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c5e7-115">See Also</span></span>  
 <xref:System.Windows.Media.VideoDrawing>  
 [<span data-ttu-id="9c5e7-116">Cenni preliminari sugli oggetti Drawing</span><span class="sxs-lookup"><span data-stu-id="9c5e7-116">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
