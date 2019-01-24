---
title: 'Procedura: Creare un oggetto Expander con un oggetto ScrollViewer'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Expander
- ScrollViewer control [WPF], with Expander control
- Expander control [WPF], creating
- controls [WPF], ScrollViewer
ms.assetid: 2ad124d2-2406-4157-aaf2-64e067298f01
ms.openlocfilehash: 8d21c7ec0172dca23f218a0d710c3976872f162c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54681963"
---
# <a name="how-to-create-an-expander-with-a-scrollviewer"></a><span data-ttu-id="d65bb-102">Procedura: Creare un oggetto Expander con un oggetto ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="d65bb-102">How to: Create an Expander with a ScrollViewer</span></span>
<span data-ttu-id="d65bb-103">In questo esempio viene illustrato come creare un <xref:System.Windows.Controls.Expander> controllo che contiene contenuto complesso, ad esempio un'immagine e testo.</span><span class="sxs-lookup"><span data-stu-id="d65bb-103">This example shows how to create an <xref:System.Windows.Controls.Expander> control that contains complex content, such as an image and text.</span></span> <span data-ttu-id="d65bb-104">L'esempio include anche il contenuto del <xref:System.Windows.Controls.Expander> in un <xref:System.Windows.Controls.ScrollViewer> controllo.</span><span class="sxs-lookup"><span data-stu-id="d65bb-104">The example also encloses the content of the <xref:System.Windows.Controls.Expander> in a <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d65bb-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="d65bb-105">Example</span></span>  
 <span data-ttu-id="d65bb-106">Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Controls.Expander>.</span><span class="sxs-lookup"><span data-stu-id="d65bb-106">The following example shows how to create an <xref:System.Windows.Controls.Expander>.</span></span> <span data-ttu-id="d65bb-107">L'esempio Usa un' <xref:System.Windows.Controls.Primitives.BulletDecorator> controllo, che contiene un'immagine e testo, per definire il <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>.</span><span class="sxs-lookup"><span data-stu-id="d65bb-107">The example uses a <xref:System.Windows.Controls.Primitives.BulletDecorator> control, which contains an image and text, in order to define the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>.</span></span> <span data-ttu-id="d65bb-108">Oggetto <xref:System.Windows.Controls.ScrollViewer> controllo fornisce un metodo per scorrere il contenuto espanso.</span><span class="sxs-lookup"><span data-stu-id="d65bb-108">A <xref:System.Windows.Controls.ScrollViewer> control provides a method for scrolling the expanded content.</span></span>  
  
 <span data-ttu-id="d65bb-109">Si noti che nell'esempio viene impostato il <xref:System.Windows.FrameworkElement.Height%2A> proprietà il <xref:System.Windows.Controls.ScrollViewer> anziché sul contenuto.</span><span class="sxs-lookup"><span data-stu-id="d65bb-109">Note that the example sets the <xref:System.Windows.FrameworkElement.Height%2A> property on the <xref:System.Windows.Controls.ScrollViewer> instead of on the content.</span></span> <span data-ttu-id="d65bb-110">Se il <xref:System.Windows.FrameworkElement.Height%2A> è impostato sul contenuto, il <xref:System.Windows.Controls.ScrollViewer> non consente all'utente di scorrere il contenuto.</span><span class="sxs-lookup"><span data-stu-id="d65bb-110">If the <xref:System.Windows.FrameworkElement.Height%2A> is set on the content, the <xref:System.Windows.Controls.ScrollViewer> does not allow the user to scroll the content.</span></span> <span data-ttu-id="d65bb-111">Il <xref:System.Windows.FrameworkElement.Width%2A> è impostata sul <xref:System.Windows.Controls.Expander> controllo e questa impostazione si applica al <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> e il contenuto espanso.</span><span class="sxs-lookup"><span data-stu-id="d65bb-111">The <xref:System.Windows.FrameworkElement.Width%2A> property is set on the <xref:System.Windows.Controls.Expander> control and this setting applies to the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the expanded content.</span></span>  
  
 [!code-xaml[ExpanderRichContent#CreateExpander](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#createexpander)]  
  
 [!code-csharp[ExpanderRichContent#CreateExpanderCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#createexpandercode)]  
  
## <a name="see-also"></a><span data-ttu-id="d65bb-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d65bb-112">See also</span></span>
- <xref:System.Windows.Controls.Expander>
- [<span data-ttu-id="d65bb-113">Panoramica sul controllo Expander</span><span class="sxs-lookup"><span data-stu-id="d65bb-113">Expander Overview</span></span>](../../../../docs/framework/wpf/controls/expander-overview.md)
- [<span data-ttu-id="d65bb-114">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="d65bb-114">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/expander-how-to-topics.md)
