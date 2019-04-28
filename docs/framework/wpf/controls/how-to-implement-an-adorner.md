---
title: 'Procedura: Implementare uno strumento decorativo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], implementing
ms.assetid: 56ae32b6-0599-455c-b52f-2ff97e6f1ec2
ms.openlocfilehash: da318fee42b4628351217774de2a2225cfb21ee1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770981"
---
# <a name="how-to-implement-an-adorner"></a><span data-ttu-id="56c91-102">Procedura: Implementare uno strumento decorativo</span><span class="sxs-lookup"><span data-stu-id="56c91-102">How to: Implement an Adorner</span></span>
<span data-ttu-id="56c91-103">Questo esempio illustra un'implementazione minima dello strumento decorativo visuale.</span><span class="sxs-lookup"><span data-stu-id="56c91-103">This example shows a minimal adorner implementation.</span></span>  
  
## <a name="notes-for-implementers"></a><span data-ttu-id="56c91-104">Note per gli implementatori</span><span class="sxs-lookup"><span data-stu-id="56c91-104">Notes for Implementers</span></span>  
 <span data-ttu-id="56c91-105">È importante notare che gli strumenti decorativi non includono alcun comportamento di rendering inerente, pertanto è responsabilità dell'implementatore garantire il rendering di uno strumento decorativo visuale.</span><span class="sxs-lookup"><span data-stu-id="56c91-105">It is important to note that adorners do not include any inherent rendering behavior; ensuring that an adorner renders is the responsibility of the adorner implementer.</span></span>   <span data-ttu-id="56c91-106">È un modo comune per implementare il comportamento di rendering per eseguire l'override di <xref:System.Windows.UIElement.OnRender%2A> metodo e usare uno o più <xref:System.Windows.Media.DrawingContext> oggetti per il rendering di oggetti visivi dello strumento decorativo in base alle esigenze (come illustrato in questo esempio).</span><span class="sxs-lookup"><span data-stu-id="56c91-106">A common way of implementing rendering behavior is to override the <xref:System.Windows.UIElement.OnRender%2A> method and use one or more <xref:System.Windows.Media.DrawingContext> objects to render the adorner's visuals as needed (as shown in this example).</span></span>  
  
## <a name="example"></a><span data-ttu-id="56c91-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="56c91-107">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="56c91-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="56c91-108">Description</span></span>  
 <span data-ttu-id="56c91-109">Uno strumento decorativo personalizzato viene creato mediante l'implementazione di una classe che eredita dalla classe astratta <xref:System.Windows.Documents.Adorner> classe.</span><span class="sxs-lookup"><span data-stu-id="56c91-109">A custom adorner is created by implementing a class that inherits from the abstract <xref:System.Windows.Documents.Adorner> class.</span></span>  <span data-ttu-id="56c91-110">Lo strumento decorativo visuale dell'esempio decora semplicemente gli angoli di un <xref:System.Windows.UIElement> con cerchi eseguendo l'override di <xref:System.Windows.UIElement.OnRender%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="56c91-110">The example adorner simply adorns the corners of a <xref:System.Windows.UIElement> with circles by overriding the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="56c91-111">Codice</span><span class="sxs-lookup"><span data-stu-id="56c91-111">Code</span></span>  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
## <a name="see-also"></a><span data-ttu-id="56c91-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56c91-112">See also</span></span>

- [<span data-ttu-id="56c91-113">Panoramica sugli strumenti decorativi</span><span class="sxs-lookup"><span data-stu-id="56c91-113">Adorners Overview</span></span>](adorners-overview.md)
