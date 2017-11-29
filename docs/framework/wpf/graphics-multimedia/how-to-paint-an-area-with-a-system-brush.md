---
title: 'Procedura: disegnare un''area con un pennello di sistema'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- system brushes [WPF], painting with
- painting [WPF], with system brushes
- brushes [WPF], painting with system brushes [WPF]
ms.assetid: 5141a763-9235-42cb-a6bb-afc75513eac7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 355df3718d90768cdfa8bc9780c44c19eb4bf9bf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-paint-an-area-with-a-system-brush"></a><span data-ttu-id="3e260-102">Procedura: disegnare un'area con un pennello di sistema</span><span class="sxs-lookup"><span data-stu-id="3e260-102">How to: Paint an Area with a System Brush</span></span>
<span data-ttu-id="3e260-103">Il <xref:System.Windows.SystemColors> classe fornisce l'accesso a pennelli di sistema e colori, ad esempio <xref:System.Windows.SystemColors.ControlBrush%2A>, <xref:System.Windows.SystemColors.ControlBrushKey%2A>, e <xref:System.Windows.SystemColors.DesktopBrush%2A>.</span><span class="sxs-lookup"><span data-stu-id="3e260-103">The <xref:System.Windows.SystemColors> class provides access to system brushes and colors, such as <xref:System.Windows.SystemColors.ControlBrush%2A>, <xref:System.Windows.SystemColors.ControlBrushKey%2A>, and <xref:System.Windows.SystemColors.DesktopBrush%2A>.</span></span> <span data-ttu-id="3e260-104">Un pennello di sistema è un <xref:System.Windows.Media.SolidColorBrush> che disegna un'area con il colore di sistema specificato.</span><span class="sxs-lookup"><span data-stu-id="3e260-104">A system brush is a <xref:System.Windows.Media.SolidColorBrush> object that paints an area with the specified system color.</span></span> <span data-ttu-id="3e260-105">Un pennello di sistema produce sempre un riempimento a tinta unita e non può essere usato per creare una sfumatura.</span><span class="sxs-lookup"><span data-stu-id="3e260-105">A system brush always produces a solid fill; it can't be used to create a gradient.</span></span>  
  
 <span data-ttu-id="3e260-106">È possibile usare i pennelli di sistema come risorsa statica o dinamica.</span><span class="sxs-lookup"><span data-stu-id="3e260-106">You can use system brushes as either a static or a dynamic resource.</span></span> <span data-ttu-id="3e260-107">Usare una risorsa dinamica se si desidera che il pennello si aggiorni automaticamente in caso di modifica mentre l'applicazione è in esecuzione. In caso contrario, usare una risorsa statica.</span><span class="sxs-lookup"><span data-stu-id="3e260-107">Use a dynamic resource if you want the brush to update automatically if the user changes the system brush as the application is running; otherwise, use a static resource.</span></span> <span data-ttu-id="3e260-108">La classe SystemColors contiene un'ampia gamma di proprietà statiche che seguono una rigida convenzione di denominazione:</span><span class="sxs-lookup"><span data-stu-id="3e260-108">The SystemColors class contains a variety of static properties that follow a strict naming convention:</span></span>  
  
-   <span data-ttu-id="3e260-109">*\<SystemColor>*Brush</span><span class="sxs-lookup"><span data-stu-id="3e260-109">*\<SystemColor>*Brush</span></span>  
  
     <span data-ttu-id="3e260-110">Ottiene un riferimento statico a una <xref:System.Windows.Media.SolidColorBrush> del colore di sistema specificato.</span><span class="sxs-lookup"><span data-stu-id="3e260-110">Gets a static reference to a <xref:System.Windows.Media.SolidColorBrush> of the specified system color.</span></span>  
  
-   <span data-ttu-id="3e260-111">*\<SystemColor>*BrushKey</span><span class="sxs-lookup"><span data-stu-id="3e260-111">*\<SystemColor>*BrushKey</span></span>  
  
     <span data-ttu-id="3e260-112">Ottiene un riferimento dinamico a un <xref:System.Windows.Media.SolidColorBrush> del colore di sistema specificato.</span><span class="sxs-lookup"><span data-stu-id="3e260-112">Gets a dynamic reference to a <xref:System.Windows.Media.SolidColorBrush> of the specified system color.</span></span>  
  
-   <span data-ttu-id="3e260-113">*\<SystemColor>*Color</span><span class="sxs-lookup"><span data-stu-id="3e260-113">*\<SystemColor>*Color</span></span>  
  
     <span data-ttu-id="3e260-114">Ottiene un riferimento statico a una <xref:System.Windows.Media.Color> struttura del colore di sistema specificato.</span><span class="sxs-lookup"><span data-stu-id="3e260-114">Gets a static reference to a <xref:System.Windows.Media.Color> structure of the specified system color.</span></span>  
  
-   <span data-ttu-id="3e260-115">*\<SystemColor>*ColorKey</span><span class="sxs-lookup"><span data-stu-id="3e260-115">*\<SystemColor>*ColorKey</span></span>  
  
     <span data-ttu-id="3e260-116">Ottiene un riferimento dinamico per il <xref:System.Windows.Media.Color> struttura del colore di sistema specificato.</span><span class="sxs-lookup"><span data-stu-id="3e260-116">Gets a dynamic reference to the <xref:System.Windows.Media.Color> structure of the specified system color.</span></span>  
  
 <span data-ttu-id="3e260-117">Un colore di sistema è un <xref:System.Windows.Media.Color> struttura che può essere usato per configurare un pennello.</span><span class="sxs-lookup"><span data-stu-id="3e260-117">A system color is a <xref:System.Windows.Media.Color> structure that can be used to configure a brush.</span></span> <span data-ttu-id="3e260-118">Ad esempio, è possibile creare una sfumatura tramite colori di sistema impostando il <xref:System.Windows.Media.GradientStop.Color%2A> le proprietà di un <xref:System.Windows.Media.LinearGradientBrush> sfumatura dell'oggetto con colori di sistema.</span><span class="sxs-lookup"><span data-stu-id="3e260-118">For example, you can create a gradient using system colors by setting the <xref:System.Windows.Media.GradientStop.Color%2A> properties of a <xref:System.Windows.Media.LinearGradientBrush> object's gradient stops with system colors.</span></span> <span data-ttu-id="3e260-119">Per un esempio, vedere [Usa colori di sistema in una sfumatura](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).</span><span class="sxs-lookup"><span data-stu-id="3e260-119">For an example, see [Use System Colors in a Gradient](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e260-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="3e260-120">Example</span></span>  
 <span data-ttu-id="3e260-121">L'esempio seguente usa un riferimento di pennello di sistema dinamico per impostare lo sfondo di un pulsante.</span><span class="sxs-lookup"><span data-stu-id="3e260-121">The following example uses a dynamic system brush reference to set the Background of a button.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorDesktopBrushKeyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemBrushExample.xaml#graphicsmmdynamicsystemcolordesktopbrushkeyexamplewholepage)]  
  
 <span data-ttu-id="3e260-122">L'esempio seguente usa un riferimento di pennello di sistema statico per impostare lo sfondo di un pulsante.</span><span class="sxs-lookup"><span data-stu-id="3e260-122">The next example uses a static system brush reference to set the Background of a button.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorDesktopBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemBrushExample.xaml#graphicsmmstaticsystemcolordesktopbrushexamplewholepage)]  
  
 <span data-ttu-id="3e260-123">Per un esempio che illustra come utilizzare un colore di sistema in una sfumatura, vedere [Usa colori di sistema in una sfumatura](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).</span><span class="sxs-lookup"><span data-stu-id="3e260-123">For an example showing how to use a system color in a gradient, see [Use System Colors in a Gradient](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e260-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e260-124">See Also</span></span>  
 [<span data-ttu-id="3e260-125">Usare i colori di sistema in una sfumatura</span><span class="sxs-lookup"><span data-stu-id="3e260-125">Use System Colors in a Gradient</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md)  
 [<span data-ttu-id="3e260-126">Cenni sul disegno con colori a tinta unita e sfumature</span><span class="sxs-lookup"><span data-stu-id="3e260-126">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
