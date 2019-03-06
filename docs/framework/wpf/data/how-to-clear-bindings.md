---
title: 'Procedura: Cancellare le associazioni'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bindings [WPF], clearing
- clearing bindings [WPF]
- data binding [WPF], clearing bindings
ms.assetid: 73962a93-32a9-4bcd-9240-bcfbb239093a
ms.openlocfilehash: 8bffc34864a2bf929bcbed09f16eac282e1ba2a5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360226"
---
# <a name="how-to-clear-bindings"></a><span data-ttu-id="4bcd5-102">Procedura: Cancellare le associazioni</span><span class="sxs-lookup"><span data-stu-id="4bcd5-102">How to: Clear Bindings</span></span>
<span data-ttu-id="4bcd5-103">Questo esempio illustra come cancellare le associazioni da un oggetto.</span><span class="sxs-lookup"><span data-stu-id="4bcd5-103">This example shows how to clear bindings from an object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4bcd5-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="4bcd5-104">Example</span></span>  
 <span data-ttu-id="4bcd5-105">Per eliminare un'associazione da una singola proprietà in un oggetto, chiamare <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="4bcd5-105">To clear a binding from an individual property on an object, call <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> as shown in the following example.</span></span> <span data-ttu-id="4bcd5-106">L'esempio seguente rimuove l'associazione dal <xref:System.Windows.Controls.TextBlock.TextProperty> dei *mytext*, un <xref:System.Windows.Controls.TextBlock> oggetto.</span><span class="sxs-lookup"><span data-stu-id="4bcd5-106">The following example removes the binding from the <xref:System.Windows.Controls.TextBlock.TextProperty> of *mytext*, a <xref:System.Windows.Controls.TextBlock> object.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#ClearBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#clearbinding)]
 [!code-vb[CodeOnlyBinding#ClearBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#clearbinding)]  
  
 <span data-ttu-id="4bcd5-107">La cancellazione rimuove l'associazione in modo che il valore della proprietà di dipendenza venga modificato in quello avrebbe assunto senza l'associazione.</span><span class="sxs-lookup"><span data-stu-id="4bcd5-107">Clearing the binding removes the binding so that the value of the dependency property is changed to whatever it would have been without the binding.</span></span> <span data-ttu-id="4bcd5-108">Questo valore potrebbe essere un valore predefinito, un valore ereditato o un valore ottenuto da un'associazione di modelli di dati.</span><span class="sxs-lookup"><span data-stu-id="4bcd5-108">This value could be a default value, an inherited value, or a value from a data template binding.</span></span>  
  
 <span data-ttu-id="4bcd5-109">Per cancellare le associazioni da tutte le possibili proprietà in un oggetto, usare <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.</span><span class="sxs-lookup"><span data-stu-id="4bcd5-109">To clear bindings from all possible properties on an object, use <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bcd5-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4bcd5-110">See also</span></span>
- <xref:System.Windows.Data.BindingOperations>
- [<span data-ttu-id="4bcd5-111">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="4bcd5-111">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="4bcd5-112">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="4bcd5-112">How-to Topics</span></span>](data-binding-how-to-topics.md)
