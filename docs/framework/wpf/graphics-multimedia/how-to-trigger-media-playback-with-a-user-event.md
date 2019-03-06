---
title: 'Procedura: Attivare la riproduzione multimediale con un evento utente'
ms.date: 03/30/2017
helpviewer_keywords:
- synchronizing media playback with events [WPF]
- playback of media [WPF], synchronizing with events
- media [WPF], synchronizing playback with events
- multimedia [WPF], synchronizing media playback with events
ms.assetid: c4dbe632-6e7f-4d7f-9df5-98737a758bc3
ms.openlocfilehash: 1d71e69bcd0332ba7119977dcf67356a3d79a368
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377976"
---
# <a name="how-to-trigger-media-playback-with-a-user-event"></a>Procedura: Attivare la riproduzione multimediale con un evento utente
Questo esempio spiega come sincronizzare la riproduzione multimediale con un evento.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il <xref:System.Windows.Controls.MediaElement> controllo e il <xref:System.Windows.Media.MediaTimeline> classe per riprodurre un suono che si verifica quando l'utente fa clic su un <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[MediaGallery_snippet#SoundFromUserEventExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/SoundFromUserEventExample.xaml#soundfromusereventexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Controls.MediaElement>
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.EventTrigger.RoutedEvent%2A>
- <xref:System.Windows.Media.Animation.Storyboard>
- [Procedure relative alle proprietà](audio-and-video-how-to-topics.md)
- [Grafica e funzionalità multimediali](index.md)
