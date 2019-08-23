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
ms.openlocfilehash: cde7c32b48dff3d6d054e700b2f95771ba3b3773
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930155"
---
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a>Procedura: Controllare un oggetto MediaElement (riproduzione, sospensione, interruzione, volume e velocità)
Nell'esempio seguente viene illustrato come controllare la riproduzione dei supporti utilizzando <xref:System.Windows.Controls.MediaElement>un oggetto. Nell'esempio viene creato un semplice lettore multimediale che consente di riprodurre, sospendere, arrestare e ignorare i supporti, nonché di modificare il volume e il rapporto di velocità.  
  
## <a name="example"></a>Esempio  
 Il codice seguente crea l'interfaccia utente.  
  
> [!NOTE]
> La <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> proprietà di <xref:System.Windows.Controls.MediaElement> deve essere impostata su `Manual` per poter arrestare, sospendere e riprodurre i file multimediali in modo interattivo.  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a>Esempio  
 Il codice seguente implementa la funzionalità dei controlli dell'interfaccia utente di esempio. I <xref:System.Windows.Controls.MediaElement.Play%2A>metodi <xref:System.Windows.Controls.MediaElement.Pause%2A>, e<xref:System.Windows.Controls.MediaElement.Stop%2A> vengono utilizzati rispettivamente per riprodurre, sospendere e arrestare il supporto. La modifica <xref:System.Windows.Controls.MediaElement.Position%2A> della proprietà <xref:System.Windows.Controls.MediaElement> del consente di ignorare il contenuto multimediale. Infine, le <xref:System.Windows.Controls.MediaElement.Volume%2A> proprietà <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> e vengono utilizzate per regolare la velocità del volume e della riproduzione del supporto.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Controllare un MediaElement usando uno storyboard](how-to-control-a-mediaelement-by-using-a-storyboard.md)
