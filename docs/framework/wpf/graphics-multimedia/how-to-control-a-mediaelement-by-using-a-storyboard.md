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
ms.openlocfilehash: 2341d2814e5bd42c652865c76d115defcc5b15b2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-a-mediaelement-by-using-a-storyboard"></a>Procedura: controllare un MediaElement utilizzando uno storyboard
In questo esempio viene illustrato come controllare un <xref:System.Windows.Controls.MediaElement> utilizzando un <xref:System.Windows.Media.MediaTimeline> in un <xref:System.Windows.Media.Animation.Storyboard>.  
  
## <a name="example"></a>Esempio  
 Quando si utilizza un <xref:System.Windows.Media.MediaTimeline> in un <xref:System.Windows.Media.Animation.Storyboard> per controllare l'intervallo di un <xref:System.Windows.Controls.MediaElement>, la funzionalità è identica alla funzionalità di altri <xref:System.Windows.Media.Animation.Timeline> oggetti, ad esempio animazioni. Ad esempio, un <xref:System.Windows.Media.MediaTimeline> Usa <xref:System.Windows.Media.Animation.Timeline> proprietà quali il <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> proprietà per specificare quando avviare un <xref:System.Windows.Controls.MediaElement> (avvio riproduzione). Utilizza inoltre il <xref:System.Windows.Media.Animation.Timeline.Duration%2A> proprietà per specificare il tempo <xref:System.Windows.Controls.MediaElement> è attivo (durata della riproduzione). Per ulteriori informazioni sull'utilizzo <xref:System.Windows.Media.Animation.Timeline> gli oggetti con un <xref:System.Windows.Media.Animation.Storyboard>, vedere [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
 In questo esempio viene illustrato come creare un lettore multimediale semplice che utilizza un <xref:System.Windows.Media.MediaTimeline> per controllare la riproduzione. Il lettore multimediale include play, sospendere, riprendere e arrestare i pulsanti. Il lettore ha anche un <xref:System.Windows.Controls.Slider> controllo che funge da una barra di stato.  
  
 Nell'esempio seguente viene creata la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] per il lettore multimediale.  
  
 [!code-xaml[MediaGallery_snip#MediaTimelineExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 Nell'esempio seguente viene creata la funzionalità per l'indicatore di stato.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaTimelineExample.xaml.cs#codebehindmediatimelineexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml.vb#codebehindmediatimelineexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.MediaElement>  
 <xref:System.Windows.Media.MediaTimeline>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 [Controllare un oggetto MediaElement (riproduzione, sospensione, interruzione, volume e velocità)](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)  
 [Cenni preliminari sugli storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [Cenni preliminari sulle animazioni con fotogrammi chiave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Procedure relative](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)  
 [Grafica e funzionalità multimediali](../../../../docs/framework/wpf/graphics-multimedia/index.md)
