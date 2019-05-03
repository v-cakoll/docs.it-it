---
title: 'Procedura: Riprodurre contenuti multimediali usando un oggetto VideoDrawing'
ms.date: 03/30/2017
helpviewer_keywords:
- playback of media [WPF]
- classes [WPF], MediaPlayer
ms.assetid: 165d47ed-22ce-4ded-aa6a-aa9b7467de87
ms.openlocfilehash: 186c9ae8167dafd09f029418c1d23f81f7a9e906
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61926067"
---
# <a name="how-to-play-media-using-a-videodrawing"></a>Procedura: Riprodurre contenuti multimediali usando un oggetto VideoDrawing
Per riprodurre un file audio o video, si utilizza un <xref:System.Windows.Media.VideoDrawing> e un <xref:System.Windows.Media.MediaPlayer>. È possibile caricare e riprodurre contenuti multimediali in due modi diversi. Il primo consiste nell'usare un <xref:System.Windows.Media.MediaPlayer> e una <xref:System.Windows.Media.VideoDrawing> da soli e il secondo modo consiste nel creare il proprio <xref:System.Windows.Media.MediaTimeline> da usare con il <xref:System.Windows.Media.MediaPlayer> e <xref:System.Windows.Media.VideoDrawing>.  
  
> [!NOTE]
>  Quando si distribuiscono contenuti multimediali con l'applicazione, non è possibile usare un file multimediale come risorsa di progetto, come avviene invece per un'immagine. È necessario invece impostare il tipo di contenuto multimediale su `Content` nel file del progetto e `CopyToOutputDirectory` su `PreserveNewest` o su `Always`.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa un' <xref:System.Windows.Media.VideoDrawing> e un <xref:System.Windows.Media.MediaPlayer> per riprodurre un file video sia una sola volta.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Per ottenere ulteriore controllo della durata dei contenuti multimediali, usare una <xref:System.Windows.Media.MediaTimeline> con il <xref:System.Windows.Media.MediaPlayer> e <xref:System.Windows.Media.VideoDrawing> oggetti. Il <xref:System.Windows.Media.MediaTimeline> consente di specificare se il video deve essere ripetuto.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa un' <xref:System.Windows.Media.MediaTimeline> con il <xref:System.Windows.Media.MediaPlayer> e <xref:System.Windows.Media.VideoDrawing> oggetti da riprodurre ripetutamente un video.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Si noti che, quando si usa una <xref:System.Windows.Media.MediaTimeline>, si usa l'oggetto interattivo <xref:System.Windows.Media.Animation.ClockController> restituiti dal <xref:System.Windows.Media.Animation.Clock.Controller%2A> proprietà del <xref:System.Windows.Media.MediaClock> per controllare la riproduzione multimediale anziché i metodi interattivi della <xref:System.Windows.Media.MediaPlayer>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.VideoDrawing>
- [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md)
