---
title: 'Procedura: ottenere una copia scrivibile di un oggetto Freezable di sola lettura'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cloning Freezable objects [WPF]
- Freezable objects [WPF], modifiable clones
ms.assetid: d028de61-bbe9-4d62-b656-8fe3b1b2ca24
ms.openlocfilehash: 894a2e42ca3f5cbb159c3129227f4b03e71fc4ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543621"
---
# <a name="how-to-obtain-a-writable-copy-of-a-read-only-freezable"></a><span data-ttu-id="debe1-102">Procedura: ottenere una copia scrivibile di un oggetto Freezable di sola lettura</span><span class="sxs-lookup"><span data-stu-id="debe1-102">How to: Obtain a Writable Copy of a Read-Only Freezable</span></span>
<span data-ttu-id="debe1-103">In questo esempio viene illustrato come utilizzare il <xref:System.Windows.Freezable.Clone%2A> metodo per creare una copia modificabile di sola lettura <xref:System.Windows.Freezable>.</span><span class="sxs-lookup"><span data-stu-id="debe1-103">This example shows how to use the <xref:System.Windows.Freezable.Clone%2A> method to create a writable copy of a read-only <xref:System.Windows.Freezable>.</span></span>  
  
 <span data-ttu-id="debe1-104">Dopo un <xref:System.Windows.Freezable> oggetto viene contrassegnato come di sola lettura ("bloccato"), è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="debe1-104">After a <xref:System.Windows.Freezable> object is marked as read-only ("frozen"), you cannot modify it.</span></span> <span data-ttu-id="debe1-105">Tuttavia, è possibile utilizzare il <xref:System.Windows.Freezable.Clone%2A> metodo per creare un clone modificabile dell'oggetto bloccato.</span><span class="sxs-lookup"><span data-stu-id="debe1-105">However, you can use the <xref:System.Windows.Freezable.Clone%2A> method to create a modifiable clone of the frozen object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="debe1-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="debe1-106">Example</span></span>  
 <span data-ttu-id="debe1-107">L'esempio seguente crea un clone modificabile di un oggetto bloccato <xref:System.Windows.Media.SolidColorBrush> oggetto.</span><span class="sxs-lookup"><span data-stu-id="debe1-107">The following example creates a modifiable clone of a frozen <xref:System.Windows.Media.SolidColorBrush> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CloneExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
 <span data-ttu-id="debe1-108">Per ulteriori informazioni su <xref:System.Windows.Freezable> degli oggetti, vedere il [panoramica sugli oggetti Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="debe1-108">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="debe1-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="debe1-109">See Also</span></span>  
 <xref:System.Windows.Freezable>  
 <xref:System.Windows.Freezable.CloneCurrentValue%2A>  
 [<span data-ttu-id="debe1-110">Cenni preliminari sugli oggetti Freezable</span><span class="sxs-lookup"><span data-stu-id="debe1-110">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="debe1-111">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="debe1-111">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
