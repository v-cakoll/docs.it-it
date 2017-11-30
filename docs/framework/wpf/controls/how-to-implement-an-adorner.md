---
title: 'Procedura: implementare strumenti decorativi'
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
helpviewer_keywords: adorners [WPF], implementing
ms.assetid: 56ae32b6-0599-455c-b52f-2ff97e6f1ec2
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a3f69fee64ea65e8d49cce523c85669993cc6bce
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-implement-an-adorner"></a><span data-ttu-id="97770-102">Procedura: implementare strumenti decorativi</span><span class="sxs-lookup"><span data-stu-id="97770-102">How to: Implement an Adorner</span></span>
<span data-ttu-id="97770-103">In questo esempio viene illustrata un'implementazione minima dello strumento decorativo.</span><span class="sxs-lookup"><span data-stu-id="97770-103">This example shows a minimal adorner implementation.</span></span>  
  
## <a name="notes-for-implementers"></a><span data-ttu-id="97770-104">Note per gli implementatori</span><span class="sxs-lookup"><span data-stu-id="97770-104">Notes for Implementers</span></span>  
 <span data-ttu-id="97770-105">È importante notare che gli strumenti decorativi non includono alcun comportamento di rendering inerente, pertanto è responsabilità dell'implementatore garantire il rendering di uno strumento decorativo visuale.</span><span class="sxs-lookup"><span data-stu-id="97770-105">It is important to note that adorners do not include any inherent rendering behavior; ensuring that an adorner renders is the responsibility of the adorner implementer.</span></span>   <span data-ttu-id="97770-106">È un modo comune di implementare il comportamento di rendering per eseguire l'override di <xref:System.Windows.UIElement.OnRender%2A> metodo e utilizzare uno o più <xref:System.Windows.Media.DrawingContext> oggetti per eseguire il rendering degli elementi visivi dello strumento decorativo in base alle esigenze (come illustrato in questo esempio).</span><span class="sxs-lookup"><span data-stu-id="97770-106">A common way of implementing rendering behavior is to override the <xref:System.Windows.UIElement.OnRender%2A> method and use one or more <xref:System.Windows.Media.DrawingContext> objects to render the adorner's visuals as needed (as shown in this example).</span></span>  
  
## <a name="example"></a><span data-ttu-id="97770-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="97770-107">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="97770-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="97770-108">Description</span></span>  
 <span data-ttu-id="97770-109">Viene creato uno strumento decorativo personalizzato implementando una classe che eredita dalla classe astratta <xref:System.Windows.Documents.Adorner> classe.</span><span class="sxs-lookup"><span data-stu-id="97770-109">A custom adorner is created by implementing a class that inherits from the abstract <xref:System.Windows.Documents.Adorner> class.</span></span>  <span data-ttu-id="97770-110">Lo strumento decorativo di esempio decora semplicemente gli angoli di un <xref:System.Windows.UIElement> con cerchi eseguendo l'override di <xref:System.Windows.UIElement.OnRender%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="97770-110">The example adorner simply adorns the corners of a <xref:System.Windows.UIElement> with circles by overriding the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="97770-111">Codice</span><span class="sxs-lookup"><span data-stu-id="97770-111">Code</span></span>  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
## <a name="see-also"></a><span data-ttu-id="97770-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97770-112">See Also</span></span>  
 [<span data-ttu-id="97770-113">Panoramica sugli strumenti decorativi</span><span class="sxs-lookup"><span data-stu-id="97770-113">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)
