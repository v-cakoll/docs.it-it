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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032231"
---
# <a name="how-to-control-a-mediaelement-by-using-a-storyboard"></a>Procedura: Controllare un oggetto MediaElement usando uno storyboard
In questo esempio viene illustrato come controllare un <xref:System.Windows.Controls.MediaElement> tramite un <xref:System.Windows.Media.MediaTimeline> in un <xref:System.Windows.Media.Animation.Storyboard>.  
  
## <a name="example"></a>Esempio  
 Quando si usa un' <xref:System.Windows.Media.MediaTimeline> in un <xref:System.Windows.Media.Animation.Storyboard> per controllare l'intervallo di un <xref:System.Windows.Controls.MediaElement>, la funzionalità è identica alla funzionalità di altri <xref:System.Windows.Media.Animation.Timeline> oggetti, ad esempio le animazioni. Ad esempio, un <xref:System.Windows.Media.MediaTimeline> Usa <xref:System.Windows.Media.Animation.Timeline> le proprietà come il <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> proprietà per specificare quando deve essere avviata una <xref:System.Windows.Controls.MediaElement> (Avvia la riproduzione multimediale). Viene inoltre utilizzata la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> proprietà per specificare quanto tempo il <xref:System.Windows.Controls.MediaElement> è attivo (durata della riproduzione di contenuti multimediali). Per altre informazioni sull'uso <xref:System.Windows.Media.Animation.Timeline> gli oggetti con un <xref:System.Windows.Media.Animation.Storyboard>, vedere [Cenni preliminari sugli storyboard](storyboards-overview.md).  
  
 In questo esempio viene illustrato come creare un semplice lettore multimediale che usa un <xref:System.Windows.Media.MediaTimeline> per controllare la riproduzione. Media player include riproduzione, pausa, riprendere e arrestare i pulsanti. Il giocatore ha anche un <xref:System.Windows.Controls.Slider> controllo che agisce come un indicatore di stato.  
  
 L'esempio seguente crea il [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] per il lettore multimediale.  
  
 [!code-xaml[MediaGallery_snip#MediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 L'esempio seguente crea la funzionalità per l'indicatore di stato.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaTimelineExample.xaml.cs#codebehindmediatimelineexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml.vb#codebehindmediatimelineexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.MediaElement>
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [Controllare un oggetto MediaElement (riproduzione, sospensione, interruzione, volume e velocità)](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)
- [Cenni preliminari sugli storyboard](storyboards-overview.md)
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Procedure relative alle proprietà](audio-and-video-how-to-topics.md)
- [Grafica e funzionalità multimediali](index.md)
