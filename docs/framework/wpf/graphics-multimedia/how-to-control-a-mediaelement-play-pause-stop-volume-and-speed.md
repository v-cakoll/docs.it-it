---
title: 'Procedura: controllare un oggetto MediaElement (Play, Pause, Stop, Volume e Speed)'
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
- playback of media [WPF], controlling
- controlling playback of media [WPF]
- multimedia [WPF], controlling playback of media
- media [WPF], controlling playback of
ms.assetid: 6885a730-e054-4c16-8c1e-ffe17b1f7c32
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 57b140391526c5b2a0e73a8bab2355ae445b395b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a><span data-ttu-id="17846-102">Procedura: controllare un oggetto MediaElement (Play, Pause, Stop, Volume e Speed)</span><span class="sxs-lookup"><span data-stu-id="17846-102">How to: Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>
<span data-ttu-id="17846-103">Nell'esempio seguente viene illustrato come controllare la riproduzione dei supporti tramite un <xref:System.Windows.Controls.MediaElement>.</span><span class="sxs-lookup"><span data-stu-id="17846-103">The following example shows how to control playback of media using a <xref:System.Windows.Controls.MediaElement>.</span></span> <span data-ttu-id="17846-104">Nell'esempio viene creato un lettore multimediale semplice che consente di riprodurre, sospendere, arrestare e andare avanti e indietro nei supporti, nonché modificare il rapporto di velocità e volume.</span><span class="sxs-lookup"><span data-stu-id="17846-104">The example creates a simple media player that allows you to play, pause, stop, and skip back and forth in the media as well as adjust the volume and speed ratio.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17846-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="17846-105">Example</span></span>  
 <span data-ttu-id="17846-106">Il codice seguente crea l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="17846-106">The code below creates the UI.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="17846-107">Il <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> proprietà di <xref:System.Windows.Controls.MediaElement> deve essere impostato su `Manual` per essere in grado di arrestarsi in modo interattivo, sospendere e riprodurre i contenuti multimediali.</span><span class="sxs-lookup"><span data-stu-id="17846-107">The <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> property of <xref:System.Windows.Controls.MediaElement> must be set to `Manual` in order to be able to interactively stop, pause, and play the media.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="17846-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="17846-108">Example</span></span>  
 <span data-ttu-id="17846-109">Il codice seguente implementa la funzionalità dei controlli dell'interfaccia utente di esempio.</span><span class="sxs-lookup"><span data-stu-id="17846-109">The code below implements the functionality of the sample UI controls.</span></span> <span data-ttu-id="17846-110">Il <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, e <xref:System.Windows.Controls.MediaElement.Stop%2A> metodi vengono utilizzati rispettivamente riprodurre, sospendere e arrestare i contenuti multimediali.</span><span class="sxs-lookup"><span data-stu-id="17846-110">The <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, and <xref:System.Windows.Controls.MediaElement.Stop%2A> methods are used to respectively play, pause and stop the media.</span></span> <span data-ttu-id="17846-111">Modifica il <xref:System.Windows.Controls.MediaElement.Position%2A> proprietà del <xref:System.Windows.Controls.MediaElement> consente di spostarsi nel supporto.</span><span class="sxs-lookup"><span data-stu-id="17846-111">Changing the <xref:System.Windows.Controls.MediaElement.Position%2A> property of the <xref:System.Windows.Controls.MediaElement> allows you to skip around in the media.</span></span> <span data-ttu-id="17846-112">Infine, il <xref:System.Windows.Controls.MediaElement.Volume%2A> e <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> vengono utilizzate per regolare la velocità di riproduzione e volume dei supporti.</span><span class="sxs-lookup"><span data-stu-id="17846-112">Finally, the <xref:System.Windows.Controls.MediaElement.Volume%2A> and <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> properties are used to adjust the volume and playback speed of the media.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="17846-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17846-113">See Also</span></span>  
 [<span data-ttu-id="17846-114">Controllare un MediaElement usando uno storyboard</span><span class="sxs-lookup"><span data-stu-id="17846-114">Control a MediaElement by Using a Storyboard</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-by-using-a-storyboard.md)
