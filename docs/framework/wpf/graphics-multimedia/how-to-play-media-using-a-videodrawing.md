---
title: 'Procedura: riprodurre contenuti multimediali utilizzando un oggetto VideoDrawing'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- playback of media [WPF]
- classes [WPF], MediaPlayer
ms.assetid: 165d47ed-22ce-4ded-aa6a-aa9b7467de87
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2753db8e06c8c1b50c6e5cee17330d421e88511f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-play-media-using-a-videodrawing"></a>Procedura: riprodurre contenuti multimediali utilizzando un oggetto VideoDrawing
Per riprodurre un file audio o video, si utilizza un <xref:System.Windows.Media.VideoDrawing> e <xref:System.Windows.Media.MediaPlayer>. È possibile caricare e riprodurre contenuti multimediali in due modi diversi. Il primo consiste nell'usare un <xref:System.Windows.Media.MediaPlayer> e <xref:System.Windows.Media.VideoDrawing> da se stessi, mentre la seconda consiste nel crearne di proprie <xref:System.Windows.Media.MediaTimeline> da utilizzare con il <xref:System.Windows.Media.MediaPlayer> e <xref:System.Windows.Media.VideoDrawing>.  
  
> [!NOTE]
>  Quando si distribuiscono contenuti multimediali con l'applicazione, non è possibile usare un file multimediale come risorsa di progetto, come avviene invece per un'immagine. È necessario invece impostare il tipo di contenuto multimediale su `Content` nel file del progetto e `CopyToOutputDirectory` su `PreserveNewest` o su `Always`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.VideoDrawing> e <xref:System.Windows.Media.MediaPlayer> per riprodurre un file video, una volta.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Per un ulteriore controllo della durata dei contenuti multimediali, utilizzare un <xref:System.Windows.Media.MediaTimeline> con il <xref:System.Windows.Media.MediaPlayer> e <xref:System.Windows.Media.VideoDrawing> oggetti. Il <xref:System.Windows.Media.MediaTimeline> consente di specificare se deve essere ripetuto il video.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.MediaTimeline> con il <xref:System.Windows.Media.MediaPlayer> e <xref:System.Windows.Media.VideoDrawing> oggetti venga eseguita più volte un video.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Si noti che, quando si utilizza un <xref:System.Windows.Media.MediaTimeline>, utilizzare l'oggetto interattivo <xref:System.Windows.Media.Animation.ClockController> restituito dal <xref:System.Windows.Media.Animation.Clock.Controller%2A> proprietà del <xref:System.Windows.Media.MediaClock> per controllare la riproduzione multimediale anziché i metodi interattivi di <xref:System.Windows.Media.MediaPlayer>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.VideoDrawing>  
 [Cenni preliminari sugli oggetti Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
