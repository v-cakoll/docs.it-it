---
title: 'Procedura: Animare un controllo Popup'
ms.date: 03/30/2017
helpviewer_keywords:
- Popup control [WPF], animating
- animation [WPF], Popup controls
ms.assetid: acaa2a0a-6137-4efd-9cd1-75ece222e390
ms.openlocfilehash: b70d9c4cb1bca26a6c77d3a7c50add517ca8ef92
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61911287"
---
# <a name="how-to-animate-a-popup"></a><span data-ttu-id="a2398-102">Procedura: Animare un controllo Popup</span><span class="sxs-lookup"><span data-stu-id="a2398-102">How to: Animate a Popup</span></span>
<span data-ttu-id="a2398-103">Questo esempio illustra due modi per animare un <xref:System.Windows.Controls.Primitives.Popup> controllo.</span><span class="sxs-lookup"><span data-stu-id="a2398-103">This example shows two ways to animate a <xref:System.Windows.Controls.Primitives.Popup> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2398-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="a2398-104">Example</span></span>  
 <span data-ttu-id="a2398-105">L'esempio seguente imposta la <xref:System.Windows.Controls.Primitives.PopupAnimation> un valore della proprietà <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>, determinando in tal modo il <xref:System.Windows.Controls.Primitives.Popup> "diapositiva-in" quando viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="a2398-105">The following example sets the <xref:System.Windows.Controls.Primitives.PopupAnimation> property to a value of <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>, which causes the <xref:System.Windows.Controls.Primitives.Popup> to "slide-in" when it appears.</span></span>  
  
 <span data-ttu-id="a2398-106">Per poter essere ruotate il <xref:System.Windows.Controls.Primitives.Popup>, in questo esempio viene assegnato un <xref:System.Windows.Media.RotateTransform> per il <xref:System.Windows.UIElement.RenderTransform%2A> proprietà la <xref:System.Windows.Controls.Canvas>, che è l'elemento figlio del <xref:System.Windows.Controls.Primitives.Popup>.</span><span class="sxs-lookup"><span data-stu-id="a2398-106">In order to rotate the <xref:System.Windows.Controls.Primitives.Popup>, this example assigns a <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property on the <xref:System.Windows.Controls.Canvas>, which is the child element of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  
  
 <span data-ttu-id="a2398-107">Per la trasformazione a funzionare correttamente, l'esempio è necessario impostare il <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="a2398-107">For the transform to work correctly, the example must set the <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> property to `true`.</span></span> <span data-ttu-id="a2398-108">Inoltre, il <xref:System.Windows.FrameworkElement.Margin%2A> nella <xref:System.Windows.Controls.Canvas> contenuto è necessario specificare uno spazio sufficiente per il <xref:System.Windows.Controls.Primitives.Popup> per ruotare.</span><span class="sxs-lookup"><span data-stu-id="a2398-108">In addition, the <xref:System.Windows.FrameworkElement.Margin%2A> on the <xref:System.Windows.Controls.Canvas> content must specify enough space for the <xref:System.Windows.Controls.Primitives.Popup> to rotate.</span></span>  
  
 [!code-xaml[AnimatedPopup#RotateTransform2](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform2)]  
  
 <span data-ttu-id="a2398-109">L'esempio seguente mostra come un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento si verifica quando un <xref:System.Windows.Controls.Button> viene fatto clic, i trigger la <xref:System.Windows.Media.Animation.Storyboard> che inizia l'animazione.</span><span class="sxs-lookup"><span data-stu-id="a2398-109">The following example shows how a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, which occurs when a <xref:System.Windows.Controls.Button> is clicked, triggers the <xref:System.Windows.Media.Animation.Storyboard> that starts the animation.</span></span>  
  
 [!code-xaml[AnimatedPopup#RotateTransform1](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform1)]  
  
## <a name="see-also"></a><span data-ttu-id="a2398-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2398-110">See also</span></span>

- <xref:System.Windows.UIElement.RenderTransform%2A>
- <xref:System.Windows.Controls.Primitives.BulletDecorator>
- <xref:System.Windows.Media.RotateTransform>
- <xref:System.Windows.Media.Animation.Storyboard>
- <xref:System.Windows.Controls.Primitives.Popup>
- [<span data-ttu-id="a2398-111">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="a2398-111">How-to Topics</span></span>](popup-how-to-topics.md)
- [<span data-ttu-id="a2398-112">Panoramica sul controllo Popup</span><span class="sxs-lookup"><span data-stu-id="a2398-112">Popup Overview</span></span>](popup-overview.md)
