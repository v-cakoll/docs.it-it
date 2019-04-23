---
title: 'Procedura: Riprodurre contenuti multimediali con animazioni'
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF], playback with animations
- playback of media [WPF], with animations
- animation [WPF], media playback with
- media [WPF], playback with animations
ms.assetid: 8982b7b7-1c6c-4b24-8801-b328862975f5
ms.openlocfilehash: 200f9d62c67a02088fe5a5789cdb41a04837d430
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079903"
---
# <a name="how-to-play-media-with-animations"></a>Procedura: Riprodurre contenuti multimediali con animazioni
Questo esempio viene illustrato come riprodurre contenuto multimediale e animazioni allo stesso tempo tramite il <xref:System.Windows.Media.MediaTimeline> e <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> classi nello stesso <xref:System.Windows.Media.Animation.Storyboard>.  
  
## <a name="example"></a>Esempio  
 È possibile usare uno o più <xref:System.Windows.Media.MediaTimeline> oggetti un <xref:System.Windows.Media.Animation.Storyboard> insieme alle altre <xref:System.Windows.Media.Animation.Timeline> oggetti, ad esempio le animazioni.  
  
 L'esempio seguente imposta la <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> proprietà del <xref:System.Windows.Media.Animation.Storyboard> su un valore di `Slip`, che consente di specificare che l'animazione non avanza quando avanza il contenuto multimediale (video in questo esempio). Questa funzionalità potrebbe essere necessaria se la riproduzione multimediale viene ritardata a causa del tempo di caricamento.  
  
 [!code-xaml[MediaGallery_snippet#MediaTimelinePlusAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/MediaTimelinePlusAnimationExample.xaml#mediatimelineplusanimationexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>
- <xref:System.Windows.Media.Animation.Storyboard>
- <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>
- [Procedure relative alle proprietà](audio-and-video-how-to-topics.md)
- [Cenni preliminari sugli storyboard](storyboards-overview.md)
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Grafica e funzionalità multimediali](index.md)
