---
title: Delegati con metodi denominati e anonimi (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- delegates [C#], with named vs. anonymous methods
- methods [C#], in delegates
ms.assetid: 98fa8c61-66b6-4146-986c-3236c4045733
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f82519f42e75008fc78fe475b7e37040985a21a1
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="delegates-with-named-vs-anonymous-methods-c-programming-guide"></a><span data-ttu-id="6acc0-102">Delegati con metodi denominati e anonimi (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="6acc0-102">Delegates with Named vs. Anonymous Methods (C# Programming Guide)</span></span>
<span data-ttu-id="6acc0-103">È possibile associare un [delegato](../../../csharp/language-reference/keywords/delegate.md) a un metodo denominato.</span><span class="sxs-lookup"><span data-stu-id="6acc0-103">A [delegate](../../../csharp/language-reference/keywords/delegate.md) can be associated with a named method.</span></span> <span data-ttu-id="6acc0-104">Quando si crea un'istanza di un delegato usando un metodo denominato, il metodo viene passato come parametro, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6acc0-104">When you instantiate a delegate by using a named method, the method is passed as a parameter, for example:</span></span>  
  
 <span data-ttu-id="6acc0-105">[!code-cs[csProgGuideDelegates#1](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6acc0-105">[!code-cs[csProgGuideDelegates#1](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_1.cs)]</span></span>  
  
 <span data-ttu-id="6acc0-106">La chiamata viene eseguita usando un metodo denominato.</span><span class="sxs-lookup"><span data-stu-id="6acc0-106">This is called using a named method.</span></span> <span data-ttu-id="6acc0-107">I delegati costruiti con un metodo denominato possono incapsulare un metodo [statico](../../../csharp/language-reference/keywords/static.md) o un metodo di istanza.</span><span class="sxs-lookup"><span data-stu-id="6acc0-107">Delegates constructed with a named method can encapsulate either a [static](../../../csharp/language-reference/keywords/static.md) method or an instance method.</span></span> <span data-ttu-id="6acc0-108">I metodi denominati rappresentano l'unico modo per creare un'istanza di un delegato nelle versioni precedenti di C#.</span><span class="sxs-lookup"><span data-stu-id="6acc0-108">Named methods are the only way to instantiate a delegate in earlier versions of C#.</span></span> <span data-ttu-id="6acc0-109">In una situazione in cui la creazione di un nuovo metodo rappresenta un sovraccarico inutile, tuttavia, C# consente di creare un'istanza di un delegato e di specificare immediatamente un blocco di codice che verrà elaborato dal delegato al momento della chiamata.</span><span class="sxs-lookup"><span data-stu-id="6acc0-109">However, in a situation where creating a new method is unwanted overhead, C# enables you to instantiate a delegate and immediately specify a code block that the delegate will process when it is called.</span></span> <span data-ttu-id="6acc0-110">Il blocco può contenere un'espressione lambda oppure un metodo anonimo.</span><span class="sxs-lookup"><span data-stu-id="6acc0-110">The block can contain either a lambda expression or an anonymous method.</span></span> <span data-ttu-id="6acc0-111">Per altre informazioni, vedere [Funzioni anonime](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span><span class="sxs-lookup"><span data-stu-id="6acc0-111">For more information, see [Anonymous Functions](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6acc0-112">Note</span><span class="sxs-lookup"><span data-stu-id="6acc0-112">Remarks</span></span>  
 <span data-ttu-id="6acc0-113">La firma del metodo che viene passato come parametro del delegato deve essere uguale a quella della dichiarazione del delegato.</span><span class="sxs-lookup"><span data-stu-id="6acc0-113">The method that you pass as a delegate parameter must have the same signature as the delegate declaration.</span></span>  
  
 <span data-ttu-id="6acc0-114">Un'istanza di delegato può incapsulare un metodo statico o un metodo di istanza.</span><span class="sxs-lookup"><span data-stu-id="6acc0-114">A delegate instance may encapsulate either static or instance method.</span></span>  
  
 <span data-ttu-id="6acc0-115">Anche se il delegato può usare un parametro [out](../../../csharp/language-reference/keywords/out.md), è consigliabile non usarlo con delegati di eventi multicast perché non è possibile sapere quale delegato verrà chiamato.</span><span class="sxs-lookup"><span data-stu-id="6acc0-115">Although the delegate can use an [out](../../../csharp/language-reference/keywords/out.md) parameter, we do not recommend its use with multicast event delegates because you cannot know which delegate will be called.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="6acc0-116">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="6acc0-116">Example 1</span></span>  
 <span data-ttu-id="6acc0-117">Di seguito è illustrato un semplice esempio di dichiarazione e uso di un delegato.</span><span class="sxs-lookup"><span data-stu-id="6acc0-117">The following is a simple example of declaring and using a delegate.</span></span> <span data-ttu-id="6acc0-118">Si noti che sia il delegato, `Del`, che il metodo associato, `MultiplyNumbers`, hanno la stessa firma</span><span class="sxs-lookup"><span data-stu-id="6acc0-118">Notice that both the delegate, `Del`, and the associated method, `MultiplyNumbers`, have the same signature</span></span>  
  
 <span data-ttu-id="6acc0-119">[!code-cs[csProgGuideDelegates#2](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="6acc0-119">[!code-cs[csProgGuideDelegates#2](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_2.cs)]</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="6acc0-120">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="6acc0-120">Example 2</span></span>  
 <span data-ttu-id="6acc0-121">Nell'esempio che segue un delegato viene mappato sia al metodo statico che al metodo di istanza e restituisce informazioni specifiche da ciascuno di essi.</span><span class="sxs-lookup"><span data-stu-id="6acc0-121">In the following example, one delegate is mapped to both static and instance methods and returns specific information from each.</span></span>  
  
 <span data-ttu-id="6acc0-122">[!code-cs[csProgGuideDelegates#3](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="6acc0-122">[!code-cs[csProgGuideDelegates#3](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6acc0-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6acc0-123">See Also</span></span>  
 <span data-ttu-id="6acc0-124">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6acc0-124">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="6acc0-125">[Delegati](../../../csharp/programming-guide/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="6acc0-125">[Delegates](../../../csharp/programming-guide/delegates/index.md) </span></span>  
 <span data-ttu-id="6acc0-126">[Metodi anonimi](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) </span><span class="sxs-lookup"><span data-stu-id="6acc0-126">[Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) </span></span>  
 <span data-ttu-id="6acc0-127">[Procedura: Combinare delegati multicast](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md) </span><span class="sxs-lookup"><span data-stu-id="6acc0-127">[How to: Combine Delegates (Multicast Delegates)](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md) </span></span>  
 [<span data-ttu-id="6acc0-128">Eventi</span><span class="sxs-lookup"><span data-stu-id="6acc0-128">Events</span></span>](../../../csharp/programming-guide/events/index.md)

