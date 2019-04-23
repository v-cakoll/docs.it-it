---
title: 'Procedura: Controllare un oggetto MediaElement (riproduzione, sospensione, interruzione, volume e velocità)'
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
ms.openlocfilehash: bb7319fc7ccec0220cbd79a32d5d015f9f2422d0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182858"
---
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a>Procedura: Controllare un oggetto MediaElement (riproduzione, sospensione, interruzione, volume e velocità)
Nell'esempio seguente viene illustrato come controllare la riproduzione dei supporti tramite un <xref:System.Windows.Controls.MediaElement>. Nell'esempio viene creato un semplice lettore multimediale che consente di riprodurre, sospendere, arrestare e andare avanti e indietro nei supporti, nonché imposta la proporzione di volume e velocità.  
  
## <a name="example"></a>Esempio  
 Il codice seguente crea l'interfaccia utente.  
  
> [!NOTE]
>  Il <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> proprietà di <xref:System.Windows.Controls.MediaElement> deve essere impostata su `Manual` affinché sia in grado di arrestare in modo interattivo, sospendere e riprodurre i contenuti multimediali.  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a>Esempio  
 Il codice seguente implementa la funzionalità dei controlli dell'interfaccia utente di esempio. Il <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, e <xref:System.Windows.Controls.MediaElement.Stop%2A> metodi vengono utilizzati rispettivamente play, sospendere e arrestare i contenuti multimediali. Modifica il <xref:System.Windows.Controls.MediaElement.Position%2A> proprietà del <xref:System.Windows.Controls.MediaElement> consente di spostarsi nel supporto. Infine, il <xref:System.Windows.Controls.MediaElement.Volume%2A> e <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> proprietà vengono utilizzate per regolare la velocità di volume e la riproduzione dei contenuti multimediali.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Controllare un MediaElement usando uno storyboard](how-to-control-a-mediaelement-by-using-a-storyboard.md)
