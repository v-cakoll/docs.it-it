---
title: 'Procedura: animare una stringa utilizzando fotogrammi chiave'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f8947669178de1252c10b6a8b2c01a6b55baa424
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a><span data-ttu-id="a0467-102">Procedura: animare una stringa utilizzando fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="a0467-102">How to: Animate a String by Using Key Frames</span></span>
<span data-ttu-id="a0467-103">In questo esempio viene illustrato come aggiungere un'animazione a una stringa, che in questo esempio è la <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà di un <xref:System.Windows.Controls.Button> controllo, usando i fotogrammi chiave.</span><span class="sxs-lookup"><span data-stu-id="a0467-103">This example shows how to animate a string, which in this example is the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0467-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="a0467-104">Example</span></span>  
 <span data-ttu-id="a0467-105">L'esempio seguente usa il <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> classe da cui iniziare l'animazione di <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà di un <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="a0467-105">The following example uses the <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="a0467-106">Tutti i fotogrammi chiave in questo esempio utilizzano un'istanza di <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> classe perché un'animazione stringa creata con i fotogrammi chiave può usare solo i fotogrammi chiave discreti.</span><span class="sxs-lookup"><span data-stu-id="a0467-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> class because a string animation that is created with key frames can only use discrete key frames.</span></span> <span data-ttu-id="a0467-107">Fotogrammi chiave discreti come <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> creare improvvisi tra due valori, ovvero le modifiche dell'animazione si verificano rapidamente e non sono più complessi.</span><span class="sxs-lookup"><span data-stu-id="a0467-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> create sudden jumps between values, that is, changes to the animation occur quickly and are not subtle.</span></span>  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="a0467-108">Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](http://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="a0467-108">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0467-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0467-109">See Also</span></span>  
 <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>  
 <xref:System.Windows.Controls.ContentControl.Content%2A>  
 <xref:System.Windows.Controls.Button>  
 <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>  
 [<span data-ttu-id="a0467-110">Cenni preliminari sulle animazioni con fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="a0467-110">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="a0467-111">Procedure relative ai fotogrammi chiave</span><span class="sxs-lookup"><span data-stu-id="a0467-111">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
