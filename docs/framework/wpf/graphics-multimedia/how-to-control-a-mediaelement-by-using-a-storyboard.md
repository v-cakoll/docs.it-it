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
# <a name="how-to-control-a-mediaelement-by-using-a-storyboard"></a>Procedura: controllare un MediaElement utilizzando uno storyboard
Questo esempio Mostra come controllare un oggetto <xref:System.Windows.Controls.MediaElement> usando un oggetto <xref:System.Windows.Media.MediaTimeline> in un oggetto <xref:System.Windows.Media.Animation.Storyboard> .  
  
## <a name="example"></a>Esempio  
 Quando si utilizza un oggetto <xref:System.Windows.Media.MediaTimeline> in un oggetto <xref:System.Windows.Media.Animation.Storyboard> per controllare l'intervallo di un oggetto <xref:System.Windows.Controls.MediaElement> , la funzionalità è identica alla funzionalità di altri <xref:System.Windows.Media.Animation.Timeline> oggetti, ad esempio le animazioni. Un oggetto, ad esempio, <xref:System.Windows.Media.MediaTimeline> utilizza <xref:System.Windows.Media.Animation.Timeline> proprietà come la <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> proprietà per specificare quando avviare un <xref:System.Windows.Controls.MediaElement> (avvio della riproduzione multimediale). USA anche la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> proprietà per specificare per quanto tempo <xref:System.Windows.Controls.MediaElement> è attivo (durata della riproduzione dei supporti). Per ulteriori informazioni sull'utilizzo di <xref:System.Windows.Media.Animation.Timeline> oggetti con un <xref:System.Windows.Media.Animation.Storyboard> , vedere [Cenni preliminari sugli storyboard](storyboards-overview.md).  
  
 Questo esempio illustra come creare un semplice lettore multimediale che usa un <xref:System.Windows.Media.MediaTimeline> per controllare la riproduzione. Il lettore multimediale include i pulsanti Riproduci, Sospendi, Riprendi e arresta. Il lettore dispone anche di un <xref:System.Windows.Controls.Slider> controllo che funge da indicatore di stato.  
  
 Nell'esempio seguente viene creato [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] per il lettore multimediale.  
  
 [!code-xaml[MediaGallery_snip#MediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 Nell'esempio seguente viene creata la funzionalità per l'indicatore di stato.  
  
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
- [Procedure](audio-and-video-how-to-topics.md)
- [Grafica e Multimedia](index.md)
