---
title: "Procedura: ottenere l'oggetto di associazione da una proprietà di destinazione associata"
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
ms.openlocfilehash: c528515124898c7deb6114e620ce21766123ab3c
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453052"
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a><span data-ttu-id="1267d-102">Procedura: ottenere l'oggetto di associazione da una proprietà di destinazione associata</span><span class="sxs-lookup"><span data-stu-id="1267d-102">How to: Get the Binding Object from a Bound Target Property</span></span>
<span data-ttu-id="1267d-103">Questo esempio illustra come ottenere l'oggetto di binding da una proprietà di destinazione associata a dati.</span><span class="sxs-lookup"><span data-stu-id="1267d-103">This example shows how to obtain the binding object from a data-bound target property.</span></span>

## <a name="example"></a><span data-ttu-id="1267d-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="1267d-104">Example</span></span>
 <span data-ttu-id="1267d-105">Per ottenere l'oggetto <xref:System.Windows.Data.Binding>, è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1267d-105">You can do the following to get the <xref:System.Windows.Data.Binding> object:</span></span>

 [!code-csharp[BindValidation#GetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]

> [!NOTE]
> <span data-ttu-id="1267d-106">È necessario specificare la proprietà di dipendenza per il binding desiderato, poiché è possibile che il data binding sia usato da più di una proprietà dell'oggetto di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1267d-106">You must specify the dependency property for the binding you want because it is possible that more than one property of the target object is using data binding.</span></span>

 <span data-ttu-id="1267d-107">In alternativa, è possibile ottenere il <xref:System.Windows.Data.BindingExpression> e quindi ottenere il valore della proprietà <xref:System.Windows.Data.BindingExpression.ParentBinding%2A>.</span><span class="sxs-lookup"><span data-stu-id="1267d-107">Alternatively, you can get the <xref:System.Windows.Data.BindingExpression> and then get the value of the <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> property.</span></span>

 <span data-ttu-id="1267d-108">Per l'esempio completo, vedere [Binding Validation Sample (Esempio di convalida binding)](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation).</span><span class="sxs-lookup"><span data-stu-id="1267d-108">For the complete example see [Binding Validation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation).</span></span>

> [!NOTE]
> <span data-ttu-id="1267d-109">Se l'associazione è una <xref:System.Windows.Data.MultiBinding>, utilizzare <xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1267d-109">If your binding is a <xref:System.Windows.Data.MultiBinding>, use <xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1267d-110">Se si tratta di una <xref:System.Windows.Data.PriorityBinding>, utilizzare <xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1267d-110">If it is a <xref:System.Windows.Data.PriorityBinding>, use <xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1267d-111">Se non si è certi che la proprietà di destinazione sia associata utilizzando un <xref:System.Windows.Data.Binding>, un <xref:System.Windows.Data.MultiBinding>o un <xref:System.Windows.Data.PriorityBinding>, è possibile utilizzare <xref:System.Windows.Data.BindingOperations.GetBindingBase%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1267d-111">If you are uncertain whether the target property is bound using a <xref:System.Windows.Data.Binding>, a <xref:System.Windows.Data.MultiBinding>, or a <xref:System.Windows.Data.PriorityBinding>, you can use <xref:System.Windows.Data.BindingOperations.GetBindingBase%2A?displayProperty=nameWithType>.</span></span>

## <a name="see-also"></a><span data-ttu-id="1267d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1267d-112">See also</span></span>

- [<span data-ttu-id="1267d-113">Creare un'associazione nel codice</span><span class="sxs-lookup"><span data-stu-id="1267d-113">Create a Binding in Code</span></span>](how-to-create-a-binding-in-code.md)
- [<span data-ttu-id="1267d-114">Procedure relative alla struttura ad albero e alla serializzazione degli elementi</span><span class="sxs-lookup"><span data-stu-id="1267d-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
