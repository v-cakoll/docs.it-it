---
title: 'Procedura: controllare un oggetto MediaElement (Play, Pause, Stop, Volume e Speed)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- playback of media [WPF], controlling
- controlling playback of media [WPF]
- multimedia [WPF], controlling playback of media
- media [WPF], controlling playback of
ms.assetid: 6885a730-e054-4c16-8c1e-ffe17b1f7c32
ms.openlocfilehash: beeddc658f16d8b52142a8a79f9c61e4f7070b01
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561391"
---
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a>Procedura: controllare un oggetto MediaElement (Play, Pause, Stop, Volume e Speed)
Nell'esempio seguente viene illustrato come controllare la riproduzione dei supporti tramite un <xref:System.Windows.Controls.MediaElement>. Nell'esempio viene creato un lettore multimediale semplice che consente di riprodurre, sospendere, arrestare e andare avanti e indietro nei supporti, nonché modificare il rapporto di velocità e volume.  
  
## <a name="example"></a>Esempio  
 Il codice seguente crea l'interfaccia utente.  
  
> [!NOTE]
>  Il <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> proprietà di <xref:System.Windows.Controls.MediaElement> deve essere impostato su `Manual` per essere in grado di arrestarsi in modo interattivo, sospendere e riprodurre i contenuti multimediali.  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a>Esempio  
 Il codice seguente implementa la funzionalità dei controlli dell'interfaccia utente di esempio. Il <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, e <xref:System.Windows.Controls.MediaElement.Stop%2A> metodi vengono utilizzati rispettivamente riprodurre, sospendere e arrestare i contenuti multimediali. Modifica il <xref:System.Windows.Controls.MediaElement.Position%2A> proprietà del <xref:System.Windows.Controls.MediaElement> consente di spostarsi nel supporto. Infine, il <xref:System.Windows.Controls.MediaElement.Volume%2A> e <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> vengono utilizzate per regolare la velocità di riproduzione e volume dei supporti.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche  
 [Controllare un MediaElement usando uno storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-by-using-a-storyboard.md)
