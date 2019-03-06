---
title: 'Procedura: Associare uno strumento decorativo visuale a un elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UIElements [WPF], binding adorners to
- adorners [WPF], binding to specified UIElements
ms.assetid: b2101611-a0ee-4137-bdb8-9b3673d2e6b9
ms.openlocfilehash: 4943121aaf8ee6524be3fc9004eafee4fa92e527
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353920"
---
# <a name="how-to-bind-an-adorner-to-an-element"></a><span data-ttu-id="7628a-102">Procedura: Associare uno strumento decorativo visuale a un elemento</span><span class="sxs-lookup"><span data-stu-id="7628a-102">How to: Bind an Adorner to an Element</span></span>
<span data-ttu-id="7628a-103">Questo esempio illustra come associare programmaticamente uno strumento decorativo a un oggetto specificato <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="7628a-103">This example shows how to programmatically bind an adorner to a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7628a-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="7628a-104">Example</span></span>  
 <span data-ttu-id="7628a-105">Per associare uno strumento decorativo a un determinato <xref:System.Windows.UIElement>, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="7628a-105">To bind an adorner to a particular <xref:System.Windows.UIElement>, follow these steps:</span></span>  
  
1.  <span data-ttu-id="7628a-106">Chiamare il `static` metodo <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> per ottenere un <xref:System.Windows.Documents.AdornerLayer> dell'oggetto per il <xref:System.Windows.UIElement> da decorare.</span><span class="sxs-lookup"><span data-stu-id="7628a-106">Call the `static` method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to get an <xref:System.Windows.Documents.AdornerLayer> object for the <xref:System.Windows.UIElement> to be adorned.</span></span> <span data-ttu-id="7628a-107"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> risale la struttura ad albero visuale, iniziando in corrispondenza di oggetto specificato **UIElement**e restituisce il primo livello dello strumento decorativo trovato.</span><span class="sxs-lookup"><span data-stu-id="7628a-107"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> walks up the visual tree, starting at the specified **UIElement**, and returns the first adorner layer it finds.</span></span> <span data-ttu-id="7628a-108">(se non viene trovato alcun livello dello strumento decorativo, il metodo restituisce null).</span><span class="sxs-lookup"><span data-stu-id="7628a-108">(If no adorner layers are found, the method returns null.)</span></span>  
  
2.  <span data-ttu-id="7628a-109">Chiamare il <xref:System.Windows.Documents.AdornerLayer.Add%2A> metodo a cui associare lo strumento decorativo visuale di destinazione **UIElement**.</span><span class="sxs-lookup"><span data-stu-id="7628a-109">Call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind the adorner to the target **UIElement**.</span></span>  
  
 <span data-ttu-id="7628a-110">Nell'esempio seguente viene associato un SimpleCircleAdorner (illustrato in precedenza) a un <xref:System.Windows.Controls.TextBox> denominate *myTextBox*.</span><span class="sxs-lookup"><span data-stu-id="7628a-110">The following example binds a SimpleCircleAdorner (shown above) to a <xref:System.Windows.Controls.TextBox> named *myTextBox*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  <span data-ttu-id="7628a-111">Non è attualmente possibile usare [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] per associare uno strumento decorativo a un altro elemento.</span><span class="sxs-lookup"><span data-stu-id="7628a-111">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7628a-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7628a-112">See also</span></span>
- [<span data-ttu-id="7628a-113">Panoramica sugli strumenti decorativi</span><span class="sxs-lookup"><span data-stu-id="7628a-113">Adorners Overview</span></span>](adorners-overview.md)
