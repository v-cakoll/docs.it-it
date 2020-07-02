---
title: 'Procedura: controllare un oggetto MediaElement (Play, Pause, Stop, Volume e Speed)'
description: Controllare la riproduzione dei contenuti multimediali in Windows Presentation Foundation (WPF). Avviare, arrestare, sospendere, spostarsi avanti e indietro e modificare il volume e la velocità.
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
ms.openlocfilehash: da846299eaa1e36b6e5caab08bc1f861e9f9c46d
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853606"
---
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a>Procedura: controllare un oggetto MediaElement (Play, Pause, Stop, Volume e Speed)
Nell'esempio seguente viene illustrato come controllare la riproduzione dei supporti utilizzando un oggetto <xref:System.Windows.Controls.MediaElement> . Nell'esempio viene creato un semplice lettore multimediale che consente di riprodurre, sospendere, arrestare e ignorare i supporti, nonché di modificare il volume e il rapporto di velocità.  
  
## <a name="example"></a>Esempio  
 Il codice seguente crea l'interfaccia utente.  
  
> [!NOTE]
> La <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> proprietà di <xref:System.Windows.Controls.MediaElement> deve essere impostata su per poter `Manual` arrestare, sospendere e riprodurre i file multimediali in modo interattivo.  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a>Esempio  
 Il codice seguente implementa la funzionalità dei controlli dell'interfaccia utente di esempio. I <xref:System.Windows.Controls.MediaElement.Play%2A> <xref:System.Windows.Controls.MediaElement.Pause%2A> metodi, e <xref:System.Windows.Controls.MediaElement.Stop%2A> vengono utilizzati rispettivamente per riprodurre, sospendere e arrestare il supporto. La modifica della <xref:System.Windows.Controls.MediaElement.Position%2A> proprietà del <xref:System.Windows.Controls.MediaElement> consente di ignorare il contenuto multimediale. Infine, le <xref:System.Windows.Controls.MediaElement.Volume%2A> <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> proprietà e vengono utilizzate per regolare la velocità del volume e della riproduzione del supporto.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Controllare un oggetto MediaElement usando uno storyboard](how-to-control-a-mediaelement-by-using-a-storyboard.md)
