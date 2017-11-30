---
title: 'Procedura: personalizzare i segni di graduazione di un controllo Slider'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TickBar [WPF]
- Slider control [WPF], creating with TickBar
ms.assetid: 4fa694f2-a620-4b15-be78-5f4286f89361
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5d266d85e10ca8e77cd32338096cf3a3b761c188
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-customize-the-ticks-on-a-slider"></a><span data-ttu-id="3ddd2-102">Procedura: personalizzare i segni di graduazione di un controllo Slider</span><span class="sxs-lookup"><span data-stu-id="3ddd2-102">How to: Customize the Ticks on a Slider</span></span>
<span data-ttu-id="3ddd2-103">In questo esempio viene illustrato come creare un <xref:System.Windows.Controls.Slider> controllo con i segni di graduazione.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-103">This example shows how to create a <xref:System.Windows.Controls.Slider> control that has tick marks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ddd2-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="3ddd2-104">Example</span></span>  
 <span data-ttu-id="3ddd2-105">Il <xref:System.Windows.Controls.Primitives.TickBar> viene visualizzato quando imposta la <xref:System.Windows.Controls.Slider.TickPlacement%2A> proprietà su un valore diverso da <xref:System.Windows.Controls.Primitives.TickPlacement.None>, ovvero il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-105">The <xref:System.Windows.Controls.Primitives.TickBar> displays when you set the <xref:System.Windows.Controls.Slider.TickPlacement%2A> property to a value other than <xref:System.Windows.Controls.Primitives.TickPlacement.None>, which is the default value.</span></span>  
  
 <span data-ttu-id="3ddd2-106">Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Controls.Slider> con un <xref:System.Windows.Controls.Primitives.TickBar> che consente di visualizzare i segni di graduazione.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-106">The following example shows how to create a <xref:System.Windows.Controls.Slider> with a <xref:System.Windows.Controls.Primitives.TickBar> that displays tick marks.</span></span> <span data-ttu-id="3ddd2-107">Il <xref:System.Windows.Controls.Slider.TickPlacement%2A> e <xref:System.Windows.Controls.Slider.TickFrequency%2A> definiscono la posizione dei segni di graduazione e l'intervallo tra di essi.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-107">The <xref:System.Windows.Controls.Slider.TickPlacement%2A> and <xref:System.Windows.Controls.Slider.TickFrequency%2A> properties define the location of the tick marks and the interval between them.</span></span> <span data-ttu-id="3ddd2-108">Quando si sposta il <xref:System.Windows.Controls.Primitives.Thumb>, le descrizioni comandi forniscono il valore di <xref:System.Windows.Controls.Slider>.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-108">When you move the <xref:System.Windows.Controls.Primitives.Thumb>, tooltips display the value of the <xref:System.Windows.Controls.Slider>.</span></span> <span data-ttu-id="3ddd2-109">Il <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> proprietà definisce in cui si verificano le descrizioni comandi.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-109">The <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> property defines where the tooltips occur.</span></span> <span data-ttu-id="3ddd2-110">Il <xref:System.Windows.Controls.Primitives.Thumb> movimenti corrispondono alla posizione dei segni di graduazione poiché <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> è impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-110">The <xref:System.Windows.Controls.Primitives.Thumb> movements correspond to the location of the tick marks because <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> is set to `true`.</span></span>  
  
 <span data-ttu-id="3ddd2-111">Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.Controls.Slider.Ticks%2A> proprietà da creare segni di graduazione lungo la <xref:System.Windows.Controls.Slider> in modo intermittente.</span><span class="sxs-lookup"><span data-stu-id="3ddd2-111">The following example shows how to use the <xref:System.Windows.Controls.Slider.Ticks%2A> property to create tick marks along the <xref:System.Windows.Controls.Slider> at irregular intervals.</span></span>  
  
 [!code-xaml[Slider#4](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Slider/xaml/window1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="3ddd2-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ddd2-112">See Also</span></span>  
 <xref:System.Windows.Controls.Slider>  
 <xref:System.Windows.Controls.Primitives.TickBar>  
 <xref:System.Windows.Controls.Slider.TickPlacement%2A>  
 [<span data-ttu-id="3ddd2-113">Procedure relative a Slider</span><span class="sxs-lookup"><span data-stu-id="3ddd2-113">Slider How-to Topics</span></span>](http://msdn.microsoft.com/en-us/534be86c-afb2-425d-8186-631278a9925e)
