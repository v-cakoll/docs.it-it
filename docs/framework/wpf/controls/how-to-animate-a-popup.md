---
title: 'Procedura: animare un controllo Popup'
ms.date: 03/30/2017
helpviewer_keywords:
- Popup control [WPF], animating
- animation [WPF], Popup controls
ms.assetid: acaa2a0a-6137-4efd-9cd1-75ece222e390
ms.openlocfilehash: 05b84eea7fe983340ebb8c5cdb20ff39eb2f0858
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33553754"
---
# <a name="how-to-animate-a-popup"></a><span data-ttu-id="9ea18-102">Procedura: animare un controllo Popup</span><span class="sxs-lookup"><span data-stu-id="9ea18-102">How to: Animate a Popup</span></span>
<span data-ttu-id="9ea18-103">In questo esempio mostra due modi per aggiungere un'animazione a un <xref:System.Windows.Controls.Primitives.Popup> controllo.</span><span class="sxs-lookup"><span data-stu-id="9ea18-103">This example shows two ways to animate a <xref:System.Windows.Controls.Primitives.Popup> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ea18-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="9ea18-104">Example</span></span>  
 <span data-ttu-id="9ea18-105">L'esempio seguente imposta il <xref:System.Windows.Controls.Primitives.PopupAnimation> un valore di proprietà <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>, causando il <xref:System.Windows.Controls.Primitives.Popup> "diapositiva-in" quando viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="9ea18-105">The following example sets the <xref:System.Windows.Controls.Primitives.PopupAnimation> property to a value of <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>, which causes the <xref:System.Windows.Controls.Primitives.Popup> to "slide-in" when it appears.</span></span>  
  
 <span data-ttu-id="9ea18-106">Per ruotare il <xref:System.Windows.Controls.Primitives.Popup>, questo esempio viene assegnato un <xref:System.Windows.Media.RotateTransform> per il <xref:System.Windows.UIElement.RenderTransform%2A> proprietà il <xref:System.Windows.Controls.Canvas>, che è l'elemento figlio del <xref:System.Windows.Controls.Primitives.Popup>.</span><span class="sxs-lookup"><span data-stu-id="9ea18-106">In order to rotate the <xref:System.Windows.Controls.Primitives.Popup>, this example assigns a <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property on the <xref:System.Windows.Controls.Canvas>, which is the child element of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  
  
 <span data-ttu-id="9ea18-107">Per la trasformazione funzionare correttamente, è necessario impostare l'esempio di <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="9ea18-107">For the transform to work correctly, the example must set the <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> property to `true`.</span></span> <span data-ttu-id="9ea18-108">Inoltre, il <xref:System.Windows.FrameworkElement.Margin%2A> sul <xref:System.Windows.Controls.Canvas> deve specificare quantità di spazio sufficiente per il <xref:System.Windows.Controls.Primitives.Popup> da ruotare.</span><span class="sxs-lookup"><span data-stu-id="9ea18-108">In addition, the <xref:System.Windows.FrameworkElement.Margin%2A> on the <xref:System.Windows.Controls.Canvas> content must specify enough space for the <xref:System.Windows.Controls.Primitives.Popup> to rotate.</span></span>  
  
 [!code-xaml[AnimatedPopup#RotateTransform2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform2)]  
  
 <span data-ttu-id="9ea18-109">L'esempio seguente viene illustrato come un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento che si verifica quando un <xref:System.Windows.Controls.Button> si fa clic, i trigger il <xref:System.Windows.Media.Animation.Storyboard> che inizia l'animazione.</span><span class="sxs-lookup"><span data-stu-id="9ea18-109">The following example shows how a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, which occurs when a <xref:System.Windows.Controls.Button> is clicked, triggers the <xref:System.Windows.Media.Animation.Storyboard> that starts the animation.</span></span>  
  
 [!code-xaml[AnimatedPopup#RotateTransform1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform1)]  
  
## <a name="see-also"></a><span data-ttu-id="9ea18-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ea18-110">See Also</span></span>  
 <xref:System.Windows.UIElement.RenderTransform%2A>  
 <xref:System.Windows.Controls.Primitives.BulletDecorator>  
 <xref:System.Windows.Media.RotateTransform>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 <xref:System.Windows.Controls.Primitives.Popup>  
 [<span data-ttu-id="9ea18-111">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="9ea18-111">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)  
 [<span data-ttu-id="9ea18-112">Panoramica sul controllo Popup</span><span class="sxs-lookup"><span data-stu-id="9ea18-112">Popup Overview</span></span>](../../../../docs/framework/wpf/controls/popup-overview.md)
