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
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a><span data-ttu-id="cfe14-102">Procedura: Controllare un oggetto MediaElement (riproduzione, sospensione, interruzione, volume e velocità)</span><span class="sxs-lookup"><span data-stu-id="cfe14-102">How to: Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>
<span data-ttu-id="cfe14-103">Nell'esempio seguente viene illustrato come controllare la riproduzione dei supporti utilizzando <xref:System.Windows.Controls.MediaElement>un oggetto.</span><span class="sxs-lookup"><span data-stu-id="cfe14-103">The following example shows how to control playback of media using a <xref:System.Windows.Controls.MediaElement>.</span></span> <span data-ttu-id="cfe14-104">Nell'esempio viene creato un semplice lettore multimediale che consente di riprodurre, sospendere, arrestare e ignorare i supporti, nonché di modificare il volume e il rapporto di velocità.</span><span class="sxs-lookup"><span data-stu-id="cfe14-104">The example creates a simple media player that allows you to play, pause, stop, and skip back and forth in the media as well as adjust the volume and speed ratio.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfe14-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="cfe14-105">Example</span></span>  
 <span data-ttu-id="cfe14-106">Il codice seguente crea l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="cfe14-106">The code below creates the UI.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cfe14-107">La <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> proprietà di <xref:System.Windows.Controls.MediaElement> deve essere impostata su `Manual` per poter arrestare, sospendere e riprodurre i file multimediali in modo interattivo.</span><span class="sxs-lookup"><span data-stu-id="cfe14-107">The <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> property of <xref:System.Windows.Controls.MediaElement> must be set to `Manual` in order to be able to interactively stop, pause, and play the media.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="cfe14-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="cfe14-108">Example</span></span>  
 <span data-ttu-id="cfe14-109">Il codice seguente implementa la funzionalità dei controlli dell'interfaccia utente di esempio.</span><span class="sxs-lookup"><span data-stu-id="cfe14-109">The code below implements the functionality of the sample UI controls.</span></span> <span data-ttu-id="cfe14-110">I <xref:System.Windows.Controls.MediaElement.Play%2A>metodi <xref:System.Windows.Controls.MediaElement.Pause%2A>, e<xref:System.Windows.Controls.MediaElement.Stop%2A> vengono utilizzati rispettivamente per riprodurre, sospendere e arrestare il supporto.</span><span class="sxs-lookup"><span data-stu-id="cfe14-110">The <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, and <xref:System.Windows.Controls.MediaElement.Stop%2A> methods are used to respectively play, pause and stop the media.</span></span> <span data-ttu-id="cfe14-111">La modifica <xref:System.Windows.Controls.MediaElement.Position%2A> della proprietà <xref:System.Windows.Controls.MediaElement> del consente di ignorare il contenuto multimediale.</span><span class="sxs-lookup"><span data-stu-id="cfe14-111">Changing the <xref:System.Windows.Controls.MediaElement.Position%2A> property of the <xref:System.Windows.Controls.MediaElement> allows you to skip around in the media.</span></span> <span data-ttu-id="cfe14-112">Infine, le <xref:System.Windows.Controls.MediaElement.Volume%2A> proprietà <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> e vengono utilizzate per regolare la velocità del volume e della riproduzione del supporto.</span><span class="sxs-lookup"><span data-stu-id="cfe14-112">Finally, the <xref:System.Windows.Controls.MediaElement.Volume%2A> and <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> properties are used to adjust the volume and playback speed of the media.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="cfe14-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cfe14-113">See also</span></span>

- [<span data-ttu-id="cfe14-114">Controllare un MediaElement usando uno storyboard</span><span class="sxs-lookup"><span data-stu-id="cfe14-114">Control a MediaElement by Using a Storyboard</span></span>](how-to-control-a-mediaelement-by-using-a-storyboard.md)
