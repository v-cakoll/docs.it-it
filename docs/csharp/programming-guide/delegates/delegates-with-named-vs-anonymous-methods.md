---
title: Delegati con metodi denominati Metodi anonimi - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], with named vs. anonymous methods
- methods [C#], in delegates
ms.assetid: 98fa8c61-66b6-4146-986c-3236c4045733
ms.openlocfilehash: 8d3cecbaecc8cf5af1e06f29c9bb8a151523d3e8
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970948"
---
# <a name="delegates-with-named-vs-anonymous-methods-c-programming-guide"></a><span data-ttu-id="4afa1-102">Delegati con metodi denominati Metodi anonimi (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="4afa1-102">Delegates with Named vs. Anonymous Methods (C# Programming Guide)</span></span>
<span data-ttu-id="4afa1-103">È possibile associare un [delegato](../../../csharp/language-reference/keywords/delegate.md) a un metodo denominato.</span><span class="sxs-lookup"><span data-stu-id="4afa1-103">A [delegate](../../../csharp/language-reference/keywords/delegate.md) can be associated with a named method.</span></span> <span data-ttu-id="4afa1-104">Quando si crea un'istanza di un delegato usando un metodo denominato, il metodo viene passato come parametro, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4afa1-104">When you instantiate a delegate by using a named method, the method is passed as a parameter, for example:</span></span>  
  
 [!code-csharp[csProgGuideDelegates#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#1)]  
  
 <span data-ttu-id="4afa1-105">La chiamata viene eseguita usando un metodo denominato.</span><span class="sxs-lookup"><span data-stu-id="4afa1-105">This is called using a named method.</span></span> <span data-ttu-id="4afa1-106">I delegati costruiti con un metodo denominato possono incapsulare un metodo [statico](../../../csharp/language-reference/keywords/static.md) o un metodo di istanza.</span><span class="sxs-lookup"><span data-stu-id="4afa1-106">Delegates constructed with a named method can encapsulate either a [static](../../../csharp/language-reference/keywords/static.md) method or an instance method.</span></span> <span data-ttu-id="4afa1-107">I metodi denominati rappresentano l'unico modo per creare un'istanza di un delegato nelle versioni precedenti di C#.</span><span class="sxs-lookup"><span data-stu-id="4afa1-107">Named methods are the only way to instantiate a delegate in earlier versions of C#.</span></span> <span data-ttu-id="4afa1-108">In una situazione in cui la creazione di un nuovo metodo rappresenta un sovraccarico inutile, tuttavia, C# consente di creare un'istanza di un delegato e di specificare immediatamente un blocco di codice che verrà elaborato dal delegato al momento della chiamata.</span><span class="sxs-lookup"><span data-stu-id="4afa1-108">However, in a situation where creating a new method is unwanted overhead, C# enables you to instantiate a delegate and immediately specify a code block that the delegate will process when it is called.</span></span> <span data-ttu-id="4afa1-109">Il blocco può contenere un'espressione lambda oppure un metodo anonimo.</span><span class="sxs-lookup"><span data-stu-id="4afa1-109">The block can contain either a lambda expression or an anonymous method.</span></span> <span data-ttu-id="4afa1-110">Per altre informazioni, vedere [Funzioni anonime](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span><span class="sxs-lookup"><span data-stu-id="4afa1-110">For more information, see [Anonymous Functions](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4afa1-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4afa1-111">Remarks</span></span>  
 <span data-ttu-id="4afa1-112">La firma del metodo che viene passato come parametro del delegato deve essere uguale a quella della dichiarazione del delegato.</span><span class="sxs-lookup"><span data-stu-id="4afa1-112">The method that you pass as a delegate parameter must have the same signature as the delegate declaration.</span></span>  
  
 <span data-ttu-id="4afa1-113">Un'istanza di delegato può incapsulare un metodo statico o un metodo di istanza.</span><span class="sxs-lookup"><span data-stu-id="4afa1-113">A delegate instance may encapsulate either static or instance method.</span></span>  
  
 <span data-ttu-id="4afa1-114">Anche se il delegato può usare un parametro [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), è consigliabile non usarlo con delegati di eventi multicast perché non è possibile sapere quale delegato verrà chiamato.</span><span class="sxs-lookup"><span data-stu-id="4afa1-114">Although the delegate can use an [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter, we do not recommend its use with multicast event delegates because you cannot know which delegate will be called.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="4afa1-115">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="4afa1-115">Example 1</span></span>  
 <span data-ttu-id="4afa1-116">Di seguito è illustrato un semplice esempio di dichiarazione e uso di un delegato.</span><span class="sxs-lookup"><span data-stu-id="4afa1-116">The following is a simple example of declaring and using a delegate.</span></span> <span data-ttu-id="4afa1-117">Si noti che sia il delegato, `Del`, che il metodo associato, `MultiplyNumbers`, hanno la stessa firma</span><span class="sxs-lookup"><span data-stu-id="4afa1-117">Notice that both the delegate, `Del`, and the associated method, `MultiplyNumbers`, have the same signature</span></span>  
  
 [!code-csharp[csProgGuideDelegates#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#2)]  
  
## <a name="example-2"></a><span data-ttu-id="4afa1-118">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="4afa1-118">Example 2</span></span>  
 <span data-ttu-id="4afa1-119">Nell'esempio che segue un delegato viene mappato sia al metodo statico che al metodo di istanza e restituisce informazioni specifiche da ciascuno di essi.</span><span class="sxs-lookup"><span data-stu-id="4afa1-119">In the following example, one delegate is mapped to both static and instance methods and returns specific information from each.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#3)]  
  
## <a name="see-also"></a><span data-ttu-id="4afa1-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4afa1-120">See also</span></span>

- [<span data-ttu-id="4afa1-121">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="4afa1-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="4afa1-122">Delegati</span><span class="sxs-lookup"><span data-stu-id="4afa1-122">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
- [<span data-ttu-id="4afa1-123">Metodi anonimi</span><span class="sxs-lookup"><span data-stu-id="4afa1-123">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)
- [<span data-ttu-id="4afa1-124">Procedura: Combinare delegati multicast</span><span class="sxs-lookup"><span data-stu-id="4afa1-124">How to: Combine Delegates (Multicast Delegates)</span></span>](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)
- [<span data-ttu-id="4afa1-125">Eventi</span><span class="sxs-lookup"><span data-stu-id="4afa1-125">Events</span></span>](../../../csharp/programming-guide/events/index.md)
