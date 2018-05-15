---
title: delegate (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- delegate_CSharpKeyword
- delegate
- CS0123
helpviewer_keywords:
- delegate keyword [C#]
- function pointers [C#]
ms.assetid: 0bb8cb6d-2f87-47c7-9d1f-d65c1cd01e9f
ms.openlocfilehash: 923d746927063490236a721e8d2600889084dac0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="delegate-c-reference"></a><span data-ttu-id="e0996-102">delegate (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e0996-102">delegate (C# Reference)</span></span>
<span data-ttu-id="e0996-103">La dichiarazione di un tipo delegato è simile alla firma di un metodo.</span><span class="sxs-lookup"><span data-stu-id="e0996-103">The declaration of a delegate type is similar to a method signature.</span></span> <span data-ttu-id="e0996-104">Ha un valore restituito e una serie di parametri di qualsiasi tipo:</span><span class="sxs-lookup"><span data-stu-id="e0996-104">It has a return value and any number of parameters of any type:</span></span>  
  
```  
public delegate void TestDelegate(string message);  
public delegate int TestDelegate(MyType m, long num);  
```  
  
 <span data-ttu-id="e0996-105">`delegate` è un tipo riferimento che può essere usato per incapsulare un metodo denominato o anonimo.</span><span class="sxs-lookup"><span data-stu-id="e0996-105">A `delegate` is a reference type that can be used to encapsulate a named or an anonymous method.</span></span> <span data-ttu-id="e0996-106">I delegati sono simili ai puntatori a funzioni in C++, ma sono indipendenti dai tipi e protetti.</span><span class="sxs-lookup"><span data-stu-id="e0996-106">Delegates are similar to function pointers in C++; however, delegates are type-safe and secure.</span></span> <span data-ttu-id="e0996-107">Per le applicazioni dei delegati, vedere  [Delegati](../../../csharp/programming-guide/delegates/index.md) e [Delegati generici](../../../csharp/programming-guide/generics/generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="e0996-107">For applications of delegates, see [Delegates](../../../csharp/programming-guide/delegates/index.md) and [Generic Delegates](../../../csharp/programming-guide/generics/generic-delegates.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0996-108">Note</span><span class="sxs-lookup"><span data-stu-id="e0996-108">Remarks</span></span>  
 <span data-ttu-id="e0996-109">I delegati sono la base degli [eventi](../../../csharp/programming-guide/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="e0996-109">Delegates are the basis for [Events](../../../csharp/programming-guide/events/index.md).</span></span>  
  
 <span data-ttu-id="e0996-110">È possibile creare un'istanza di un delegato associandolo a un metodo denominato o anonimo.</span><span class="sxs-lookup"><span data-stu-id="e0996-110">A delegate can be instantiated by associating it either with a named or anonymous method.</span></span> <span data-ttu-id="e0996-111">Per altre informazioni, vedere [Metodi denominati](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) e [Metodi anonimi](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span><span class="sxs-lookup"><span data-stu-id="e0996-111">For more information, see [Named Methods](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) and [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span></span>  
  
 <span data-ttu-id="e0996-112">È necessario creare un'istanza del delegato con un metodo o un'espressione lambda con tipo restituito compatibile e parametri di input.</span><span class="sxs-lookup"><span data-stu-id="e0996-112">The delegate must be instantiated with a method or lambda expression that has a compatible return type and input parameters.</span></span> <span data-ttu-id="e0996-113">Per altre informazioni sul grado di varianza consentito nella firma del metodo, vedere [Varianza nei delegati](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="e0996-113">For more information on the degree of variance that is allowed in the method signature, see [Variance in Delegates](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span> <span data-ttu-id="e0996-114">Per l'uso con i metodi anonimi, è necessario dichiarare insieme il delegato e il codice da associare ad esso.</span><span class="sxs-lookup"><span data-stu-id="e0996-114">For use with anonymous methods, the delegate and the code to be associated with it are declared together.</span></span> <span data-ttu-id="e0996-115">In questa sezione sono descritti entrambi i metodi per la creazione di istanze di delegati.</span><span class="sxs-lookup"><span data-stu-id="e0996-115">Both ways of instantiating delegates are discussed in this section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0996-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="e0996-116">Example</span></span>  
 [!code-csharp[csrefKeywordsTypes#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/delegate_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="e0996-117">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="e0996-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e0996-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0996-118">See Also</span></span>  
 [<span data-ttu-id="e0996-119">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="e0996-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e0996-120">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e0996-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e0996-121">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="e0996-121">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="e0996-122">Tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="e0996-122">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
 [<span data-ttu-id="e0996-123">Delegati</span><span class="sxs-lookup"><span data-stu-id="e0996-123">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
 [<span data-ttu-id="e0996-124">Eventi</span><span class="sxs-lookup"><span data-stu-id="e0996-124">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
 [<span data-ttu-id="e0996-125">Delegati con metodi denominati o metodi anonimi</span><span class="sxs-lookup"><span data-stu-id="e0996-125">Delegates with Named vs. Anonymous Methods</span></span>](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)  
 [<span data-ttu-id="e0996-126">Metodi anonimi</span><span class="sxs-lookup"><span data-stu-id="e0996-126">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)
