---
title: 'Procedura: creare un controllo Expander con un controllo ScrollViewer'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], Expander
- ScrollViewer control [WPF], with Expander control
- Expander control [WPF], creating
- controls [WPF], ScrollViewer
ms.assetid: 2ad124d2-2406-4157-aaf2-64e067298f01
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a2066ccce28138cfecf4e0b4574d45783a9ba4ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-an-expander-with-a-scrollviewer"></a><span data-ttu-id="d98e4-102">Procedura: creare un controllo Expander con un controllo ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="d98e4-102">How to: Create an Expander with a ScrollViewer</span></span>
<span data-ttu-id="d98e4-103">In questo esempio viene illustrato come creare un <xref:System.Windows.Controls.Expander> controllo che contiene contenuto complesso, ad esempio un'immagine e testo.</span><span class="sxs-lookup"><span data-stu-id="d98e4-103">This example shows how to create an <xref:System.Windows.Controls.Expander> control that contains complex content, such as an image and text.</span></span> <span data-ttu-id="d98e4-104">Nell'esempio viene inoltre incluso il contenuto del <xref:System.Windows.Controls.Expander> in un <xref:System.Windows.Controls.ScrollViewer> controllo.</span><span class="sxs-lookup"><span data-stu-id="d98e4-104">The example also encloses the content of the <xref:System.Windows.Controls.Expander> in a <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d98e4-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="d98e4-105">Example</span></span>  
 <span data-ttu-id="d98e4-106">Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Controls.Expander>.</span><span class="sxs-lookup"><span data-stu-id="d98e4-106">The following example shows how to create an <xref:System.Windows.Controls.Expander>.</span></span> <span data-ttu-id="d98e4-107">Nell'esempio viene utilizzato un <xref:System.Windows.Controls.Primitives.BulletDecorator> controllo che contiene un'immagine e testo, per definire il <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>.</span><span class="sxs-lookup"><span data-stu-id="d98e4-107">The example uses a <xref:System.Windows.Controls.Primitives.BulletDecorator> control, which contains an image and text, in order to define the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>.</span></span> <span data-ttu-id="d98e4-108">Oggetto <xref:System.Windows.Controls.ScrollViewer> controllo fornisce un metodo per scorrere il contenuto espanso.</span><span class="sxs-lookup"><span data-stu-id="d98e4-108">A <xref:System.Windows.Controls.ScrollViewer> control provides a method for scrolling the expanded content.</span></span>  
  
 <span data-ttu-id="d98e4-109">Si noti che nell'esempio viene impostato il <xref:System.Windows.FrameworkElement.Height%2A> proprietà il <xref:System.Windows.Controls.ScrollViewer> anziché sul contenuto.</span><span class="sxs-lookup"><span data-stu-id="d98e4-109">Note that the example sets the <xref:System.Windows.FrameworkElement.Height%2A> property on the <xref:System.Windows.Controls.ScrollViewer> instead of on the content.</span></span> <span data-ttu-id="d98e4-110">Se il <xref:System.Windows.FrameworkElement.Height%2A> è impostato sul contenuto, il <xref:System.Windows.Controls.ScrollViewer> non consente all'utente di scorrere il contenuto.</span><span class="sxs-lookup"><span data-stu-id="d98e4-110">If the <xref:System.Windows.FrameworkElement.Height%2A> is set on the content, the <xref:System.Windows.Controls.ScrollViewer> does not allow the user to scroll the content.</span></span> <span data-ttu-id="d98e4-111">Il <xref:System.Windows.FrameworkElement.Width%2A> proprietà è impostata sul <xref:System.Windows.Controls.Expander> controllo e questa impostazione si applica al <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> e il contenuto espanso.</span><span class="sxs-lookup"><span data-stu-id="d98e4-111">The <xref:System.Windows.FrameworkElement.Width%2A> property is set on the <xref:System.Windows.Controls.Expander> control and this setting applies to the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the expanded content.</span></span>  
  
 [!code-xaml[ExpanderRichContent#CreateExpander](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#createexpander)]  
  
 [!code-csharp[ExpanderRichContent#CreateExpanderCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#createexpandercode)]  
  
## <a name="see-also"></a><span data-ttu-id="d98e4-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d98e4-112">See Also</span></span>  
 <xref:System.Windows.Controls.Expander>  
 [<span data-ttu-id="d98e4-113">Panoramica sul controllo Expander</span><span class="sxs-lookup"><span data-stu-id="d98e4-113">Expander Overview</span></span>](../../../../docs/framework/wpf/controls/expander-overview.md)  
 [<span data-ttu-id="d98e4-114">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="d98e4-114">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/expander-how-to-topics.md)
