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
# <a name="how-to-play-media-using-a-videodrawing"></a>Procedura: Riprodurre contenuti multimediali usando un oggetto VideoDrawing
Per riprodurre un file audio o video, è possibile usare <xref:System.Windows.Media.VideoDrawing> un oggetto <xref:System.Windows.Media.MediaPlayer>e un oggetto. È possibile caricare e riprodurre contenuti multimediali in due modi diversi. Il primo consiste nell'usare un <xref:System.Windows.Media.MediaPlayer> oggetto e <xref:System.Windows.Media.VideoDrawing> un autonomo e il secondo modo consiste nel creare un oggetto <xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.MediaPlayer> personalizzato da usare con e <xref:System.Windows.Media.VideoDrawing>.  
  
> [!NOTE]
> Quando si distribuiscono contenuti multimediali con l'applicazione, non è possibile usare un file multimediale come risorsa di progetto, come avviene invece per un'immagine. È necessario invece impostare il tipo di contenuto multimediale su `Content` nel file del progetto e `CopyToOutputDirectory` su `PreserveNewest` o su `Always`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono utilizzati <xref:System.Windows.Media.VideoDrawing> un oggetto <xref:System.Windows.Media.MediaPlayer> e un oggetto per riprodurre un file video una sola volta.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Per ottenere un controllo temporale aggiuntivo sui supporti, utilizzare un <xref:System.Windows.Media.MediaTimeline> oggetto con <xref:System.Windows.Media.MediaPlayer> gli <xref:System.Windows.Media.VideoDrawing> oggetti e. <xref:System.Windows.Media.MediaTimeline> Consente di specificare se il video deve essere ripetuto.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato <xref:System.Windows.Media.MediaTimeline> un oggetto <xref:System.Windows.Media.MediaPlayer> con <xref:System.Windows.Media.VideoDrawing> gli oggetti e per riprodurre un video ripetutamente.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Si noti che, quando si usa <xref:System.Windows.Media.MediaTimeline>un, si usa l' <xref:System.Windows.Media.Animation.ClockController> elemento interattivo restituito <xref:System.Windows.Media.Animation.Clock.Controller%2A> <xref:System.Windows.Media.MediaClock> dalla proprietà di per controllare la riproduzione dei supporti anziché i metodi interattivi di <xref:System.Windows.Media.MediaPlayer>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.VideoDrawing>
- [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md)
