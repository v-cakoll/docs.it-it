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
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a><span data-ttu-id="93985-102">Procedura: controllare un oggetto MediaElement (Play, Pause, Stop, Volume e Speed)</span><span class="sxs-lookup"><span data-stu-id="93985-102">How to: Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>
<span data-ttu-id="93985-103">Nell'esempio seguente viene illustrato come controllare la riproduzione dei supporti tramite un <xref:System.Windows.Controls.MediaElement>.</span><span class="sxs-lookup"><span data-stu-id="93985-103">The following example shows how to control playback of media using a <xref:System.Windows.Controls.MediaElement>.</span></span> <span data-ttu-id="93985-104">Nell'esempio viene creato un lettore multimediale semplice che consente di riprodurre, sospendere, arrestare e andare avanti e indietro nei supporti, nonché modificare il rapporto di velocità e volume.</span><span class="sxs-lookup"><span data-stu-id="93985-104">The example creates a simple media player that allows you to play, pause, stop, and skip back and forth in the media as well as adjust the volume and speed ratio.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93985-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="93985-105">Example</span></span>  
 <span data-ttu-id="93985-106">Il codice seguente crea l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="93985-106">The code below creates the UI.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93985-107">Il <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> proprietà di <xref:System.Windows.Controls.MediaElement> deve essere impostato su `Manual` per essere in grado di arrestarsi in modo interattivo, sospendere e riprodurre i contenuti multimediali.</span><span class="sxs-lookup"><span data-stu-id="93985-107">The <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> property of <xref:System.Windows.Controls.MediaElement> must be set to `Manual` in order to be able to interactively stop, pause, and play the media.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="93985-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="93985-108">Example</span></span>  
 <span data-ttu-id="93985-109">Il codice seguente implementa la funzionalità dei controlli dell'interfaccia utente di esempio.</span><span class="sxs-lookup"><span data-stu-id="93985-109">The code below implements the functionality of the sample UI controls.</span></span> <span data-ttu-id="93985-110">Il <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, e <xref:System.Windows.Controls.MediaElement.Stop%2A> metodi vengono utilizzati rispettivamente riprodurre, sospendere e arrestare i contenuti multimediali.</span><span class="sxs-lookup"><span data-stu-id="93985-110">The <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, and <xref:System.Windows.Controls.MediaElement.Stop%2A> methods are used to respectively play, pause and stop the media.</span></span> <span data-ttu-id="93985-111">Modifica il <xref:System.Windows.Controls.MediaElement.Position%2A> proprietà del <xref:System.Windows.Controls.MediaElement> consente di spostarsi nel supporto.</span><span class="sxs-lookup"><span data-stu-id="93985-111">Changing the <xref:System.Windows.Controls.MediaElement.Position%2A> property of the <xref:System.Windows.Controls.MediaElement> allows you to skip around in the media.</span></span> <span data-ttu-id="93985-112">Infine, il <xref:System.Windows.Controls.MediaElement.Volume%2A> e <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> vengono utilizzate per regolare la velocità di riproduzione e volume dei supporti.</span><span class="sxs-lookup"><span data-stu-id="93985-112">Finally, the <xref:System.Windows.Controls.MediaElement.Volume%2A> and <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> properties are used to adjust the volume and playback speed of the media.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="93985-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93985-113">See Also</span></span>  
 [<span data-ttu-id="93985-114">Controllare un MediaElement usando uno storyboard</span><span class="sxs-lookup"><span data-stu-id="93985-114">Control a MediaElement by Using a Storyboard</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-by-using-a-storyboard.md)
