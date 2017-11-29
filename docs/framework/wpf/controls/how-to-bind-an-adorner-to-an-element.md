---
title: 'Procedura: associare uno strumento decorativo visuale a un elemento'
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
- UIElements [WPF], binding adorners to
- adorners [WPF], binding to specified UIElements
ms.assetid: b2101611-a0ee-4137-bdb8-9b3673d2e6b9
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2b1da3216ce6d3507c304ff957728d33ba1b9bd9
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-bind-an-adorner-to-an-element"></a><span data-ttu-id="e7551-102">Procedura: associare uno strumento decorativo visuale a un elemento</span><span class="sxs-lookup"><span data-stu-id="e7551-102">How to: Bind an Adorner to an Element</span></span>
<span data-ttu-id="e7551-103">In questo esempio viene illustrato come associare a livello di codice uno strumento decorativo di un oggetto <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="e7551-103">This example shows how to programmatically bind an adorner to a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7551-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="e7551-104">Example</span></span>  
 <span data-ttu-id="e7551-105">Per associare un adorner a un particolare <xref:System.Windows.UIElement>, seguire questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="e7551-105">To bind an adorner to a particular <xref:System.Windows.UIElement>, follow these steps:</span></span>  
  
1.  <span data-ttu-id="e7551-106">Chiamare il `static` metodo <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> per ottenere un <xref:System.Windows.Documents.AdornerLayer> dell'oggetto per il <xref:System.Windows.UIElement> da decorare.</span><span class="sxs-lookup"><span data-stu-id="e7551-106">Call the `static` method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to get an <xref:System.Windows.Documents.AdornerLayer> object for the <xref:System.Windows.UIElement> to be adorned.</span></span> <span data-ttu-id="e7551-107"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>descrive la struttura ad albero visuale, inizia in corrispondenza **UIElement**e restituisce il primo livello dello strumento decorativo visuale trovato.</span><span class="sxs-lookup"><span data-stu-id="e7551-107"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> walks up the visual tree, starting at the specified **UIElement**, and returns the first adorner layer it finds.</span></span> <span data-ttu-id="e7551-108">(se non viene trovato alcun livello dello strumento decorativo, il metodo restituisce null).</span><span class="sxs-lookup"><span data-stu-id="e7551-108">(If no adorner layers are found, the method returns null.)</span></span>  
  
2.  <span data-ttu-id="e7551-109">Chiamare il <xref:System.Windows.Documents.AdornerLayer.Add%2A> metodo per associare lo strumento decorativo di destinazione **UIElement**.</span><span class="sxs-lookup"><span data-stu-id="e7551-109">Call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind the adorner to the target **UIElement**.</span></span>  
  
 <span data-ttu-id="e7551-110">Nell'esempio seguente viene associato un SimpleCircleAdorner (illustrato in precedenza) a un <xref:System.Windows.Controls.TextBox> denominato *myTextBox*.</span><span class="sxs-lookup"><span data-stu-id="e7551-110">The following example binds a SimpleCircleAdorner (shown above) to a <xref:System.Windows.Controls.TextBox> named *myTextBox*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  <span data-ttu-id="e7551-111">Non è attualmente possibile usare [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] per associare uno strumento decorativo a un altro elemento.</span><span class="sxs-lookup"><span data-stu-id="e7551-111">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7551-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7551-112">See Also</span></span>  
 [<span data-ttu-id="e7551-113">Panoramica sugli strumenti decorativi</span><span class="sxs-lookup"><span data-stu-id="e7551-113">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)
