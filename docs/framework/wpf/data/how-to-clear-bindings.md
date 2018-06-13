---
title: 'Procedura: cancellare associazioni'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bindings [WPF], clearing
- clearing bindings [WPF]
- data binding [WPF], clearing bindings
ms.assetid: 73962a93-32a9-4bcd-9240-bcfbb239093a
ms.openlocfilehash: f66477fc857a9e7a065e01b8cddf43789042b59c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555857"
---
# <a name="how-to-clear-bindings"></a><span data-ttu-id="b4215-102">Procedura: cancellare associazioni</span><span class="sxs-lookup"><span data-stu-id="b4215-102">How to: Clear Bindings</span></span>
<span data-ttu-id="b4215-103">Questo esempio illustra come cancellare le associazioni da un oggetto.</span><span class="sxs-lookup"><span data-stu-id="b4215-103">This example shows how to clear bindings from an object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4215-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="b4215-104">Example</span></span>  
 <span data-ttu-id="b4215-105">Per eliminare un'associazione da una singola proprietà in un oggetto, chiamare <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="b4215-105">To clear a binding from an individual property on an object, call <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> as shown in the following example.</span></span> <span data-ttu-id="b4215-106">Nell'esempio seguente viene rimossa l'associazione dal <xref:System.Windows.Controls.TextBlock.TextProperty> di *mytext*, <xref:System.Windows.Controls.TextBlock> oggetto.</span><span class="sxs-lookup"><span data-stu-id="b4215-106">The following example removes the binding from the <xref:System.Windows.Controls.TextBlock.TextProperty> of *mytext*, a <xref:System.Windows.Controls.TextBlock> object.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#clearbinding)]
 [!code-vb[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#clearbinding)]  
  
 <span data-ttu-id="b4215-107">La cancellazione rimuove l'associazione in modo che il valore della proprietà di dipendenza venga modificato in quello avrebbe assunto senza l'associazione.</span><span class="sxs-lookup"><span data-stu-id="b4215-107">Clearing the binding removes the binding so that the value of the dependency property is changed to whatever it would have been without the binding.</span></span> <span data-ttu-id="b4215-108">Questo valore potrebbe essere un valore predefinito, un valore ereditato o un valore ottenuto da un'associazione di modelli di dati.</span><span class="sxs-lookup"><span data-stu-id="b4215-108">This value could be a default value, an inherited value, or a value from a data template binding.</span></span>  
  
 <span data-ttu-id="b4215-109">Per cancellare le associazioni da tutte le possibili proprietà su un oggetto, utilizzare <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.</span><span class="sxs-lookup"><span data-stu-id="b4215-109">To clear bindings from all possible properties on an object, use <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4215-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4215-110">See Also</span></span>  
 <xref:System.Windows.Data.BindingOperations>  
 [<span data-ttu-id="b4215-111">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="b4215-111">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="b4215-112">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="b4215-112">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
