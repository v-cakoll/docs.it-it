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
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a><span data-ttu-id="61cc6-104">Procedura: controllare un oggetto MediaElement (Play, Pause, Stop, Volume e Speed)</span><span class="sxs-lookup"><span data-stu-id="61cc6-104">How to: Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>
<span data-ttu-id="61cc6-105">Nell'esempio seguente viene illustrato come controllare la riproduzione dei supporti utilizzando un oggetto <xref:System.Windows.Controls.MediaElement> .</span><span class="sxs-lookup"><span data-stu-id="61cc6-105">The following example shows how to control playback of media using a <xref:System.Windows.Controls.MediaElement>.</span></span> <span data-ttu-id="61cc6-106">Nell'esempio viene creato un semplice lettore multimediale che consente di riprodurre, sospendere, arrestare e ignorare i supporti, nonché di modificare il volume e il rapporto di velocità.</span><span class="sxs-lookup"><span data-stu-id="61cc6-106">The example creates a simple media player that allows you to play, pause, stop, and skip back and forth in the media as well as adjust the volume and speed ratio.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61cc6-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="61cc6-107">Example</span></span>  
 <span data-ttu-id="61cc6-108">Il codice seguente crea l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="61cc6-108">The code below creates the UI.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="61cc6-109">La <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> proprietà di <xref:System.Windows.Controls.MediaElement> deve essere impostata su per poter `Manual` arrestare, sospendere e riprodurre i file multimediali in modo interattivo.</span><span class="sxs-lookup"><span data-stu-id="61cc6-109">The <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> property of <xref:System.Windows.Controls.MediaElement> must be set to `Manual` in order to be able to interactively stop, pause, and play the media.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="61cc6-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="61cc6-110">Example</span></span>  
 <span data-ttu-id="61cc6-111">Il codice seguente implementa la funzionalità dei controlli dell'interfaccia utente di esempio.</span><span class="sxs-lookup"><span data-stu-id="61cc6-111">The code below implements the functionality of the sample UI controls.</span></span> <span data-ttu-id="61cc6-112">I <xref:System.Windows.Controls.MediaElement.Play%2A> <xref:System.Windows.Controls.MediaElement.Pause%2A> metodi, e <xref:System.Windows.Controls.MediaElement.Stop%2A> vengono utilizzati rispettivamente per riprodurre, sospendere e arrestare il supporto.</span><span class="sxs-lookup"><span data-stu-id="61cc6-112">The <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, and <xref:System.Windows.Controls.MediaElement.Stop%2A> methods are used to respectively play, pause and stop the media.</span></span> <span data-ttu-id="61cc6-113">La modifica della <xref:System.Windows.Controls.MediaElement.Position%2A> proprietà del <xref:System.Windows.Controls.MediaElement> consente di ignorare il contenuto multimediale.</span><span class="sxs-lookup"><span data-stu-id="61cc6-113">Changing the <xref:System.Windows.Controls.MediaElement.Position%2A> property of the <xref:System.Windows.Controls.MediaElement> allows you to skip around in the media.</span></span> <span data-ttu-id="61cc6-114">Infine, le <xref:System.Windows.Controls.MediaElement.Volume%2A> <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> proprietà e vengono utilizzate per regolare la velocità del volume e della riproduzione del supporto.</span><span class="sxs-lookup"><span data-stu-id="61cc6-114">Finally, the <xref:System.Windows.Controls.MediaElement.Volume%2A> and <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> properties are used to adjust the volume and playback speed of the media.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="61cc6-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61cc6-115">See also</span></span>

- [<span data-ttu-id="61cc6-116">Controllare un oggetto MediaElement usando uno storyboard</span><span class="sxs-lookup"><span data-stu-id="61cc6-116">Control a MediaElement by Using a Storyboard</span></span>](how-to-control-a-mediaelement-by-using-a-storyboard.md)
