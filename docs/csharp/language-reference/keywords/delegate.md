---
title: delegate (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- delegate_CSharpKeyword
- delegate
- CS0123
dev_langs:
- CSharp
helpviewer_keywords:
- delegate keyword [C#]
- function pointers [C#]
ms.assetid: 0bb8cb6d-2f87-47c7-9d1f-d65c1cd01e9f
caps.latest.revision: 24
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
ms.openlocfilehash: 402eedd0c59b5c95e1a9b44faca66ccb4d4e04e7
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="delegate-c-reference"></a><span data-ttu-id="7d790-102">delegate (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="7d790-102">delegate (C# Reference)</span></span>
<span data-ttu-id="7d790-103">La dichiarazione di un tipo delegato è simile alla firma di un metodo.</span><span class="sxs-lookup"><span data-stu-id="7d790-103">The declaration of a delegate type is similar to a method signature.</span></span> <span data-ttu-id="7d790-104">Ha un valore restituito e una serie di parametri di qualsiasi tipo:</span><span class="sxs-lookup"><span data-stu-id="7d790-104">It has a return value and any number of parameters of any type:</span></span>  
  
```  
public delegate void TestDelegate(string message);  
public delegate int TestDelegate(MyType m, long num);  
```  
  
 <span data-ttu-id="7d790-105">`delegate` è un tipo riferimento che può essere usato per incapsulare un metodo denominato o anonimo.</span><span class="sxs-lookup"><span data-stu-id="7d790-105">A `delegate` is a reference type that can be used to encapsulate a named or an anonymous method.</span></span> <span data-ttu-id="7d790-106">I delegati sono simili ai puntatori a funzioni in C++, ma sono indipendenti dai tipi e protetti.</span><span class="sxs-lookup"><span data-stu-id="7d790-106">Delegates are similar to function pointers in C++; however, delegates are type-safe and secure.</span></span> <span data-ttu-id="7d790-107">Per le applicazioni dei delegati, vedere  [Delegati](../../../csharp/programming-guide/delegates/index.md) e [Delegati generici](../../../csharp/programming-guide/generics/generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="7d790-107">For applications of delegates, see [Delegates](../../../csharp/programming-guide/delegates/index.md) and [Generic Delegates](../../../csharp/programming-guide/generics/generic-delegates.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d790-108">Note</span><span class="sxs-lookup"><span data-stu-id="7d790-108">Remarks</span></span>  
 <span data-ttu-id="7d790-109">I delegati sono la base degli [eventi](../../../csharp/programming-guide/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="7d790-109">Delegates are the basis for [Events](../../../csharp/programming-guide/events/index.md).</span></span>  
  
 <span data-ttu-id="7d790-110">È possibile creare un'istanza di un delegato associandolo a un metodo denominato o anonimo.</span><span class="sxs-lookup"><span data-stu-id="7d790-110">A delegate can be instantiated by associating it either with a named or anonymous method.</span></span> <span data-ttu-id="7d790-111">Per altre informazioni, vedere [Metodi denominati](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) e [Metodi anonimi](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span><span class="sxs-lookup"><span data-stu-id="7d790-111">For more information, see [Named Methods](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) and [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span></span>  
  
 <span data-ttu-id="7d790-112">È necessario creare un'istanza del delegato con un metodo o un'espressione lambda con tipo restituito compatibile e parametri di input.</span><span class="sxs-lookup"><span data-stu-id="7d790-112">The delegate must be instantiated with a method or lambda expression that has a compatible return type and input parameters.</span></span> <span data-ttu-id="7d790-113">Per altre informazioni sul grado di varianza consentito nella firma del metodo, vedere [Varianza nei delegati](http://msdn.microsoft.com/library/e3b98197-6c5b-4e55-9c6e-9739b60645ca).</span><span class="sxs-lookup"><span data-stu-id="7d790-113">For more information on the degree of variance that is allowed in the method signature, see [Variance in Delegates](http://msdn.microsoft.com/library/e3b98197-6c5b-4e55-9c6e-9739b60645ca).</span></span> <span data-ttu-id="7d790-114">Per l'uso con i metodi anonimi, è necessario dichiarare insieme il delegato e il codice da associare ad esso.</span><span class="sxs-lookup"><span data-stu-id="7d790-114">For use with anonymous methods, the delegate and the code to be associated with it are declared together.</span></span> <span data-ttu-id="7d790-115">In questa sezione sono descritti entrambi i metodi per la creazione di istanze di delegati.</span><span class="sxs-lookup"><span data-stu-id="7d790-115">Both ways of instantiating delegates are discussed in this section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d790-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="7d790-116">Example</span></span>  
 <span data-ttu-id="7d790-117">[!code-cs[csrefKeywordsTypes#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/delegate_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="7d790-117">[!code-cs[csrefKeywordsTypes#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/delegate_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="7d790-118">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="7d790-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7d790-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d790-119">See Also</span></span>  
 <span data-ttu-id="7d790-120">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="7d790-120">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="7d790-121">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="7d790-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="7d790-122">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="7d790-122">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="7d790-123">[Tipi di riferimento](../../../csharp/language-reference/keywords/reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="7d790-123">[Reference Types](../../../csharp/language-reference/keywords/reference-types.md) </span></span>  
 <span data-ttu-id="7d790-124">[Delegati](../../../csharp/programming-guide/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="7d790-124">[Delegates](../../../csharp/programming-guide/delegates/index.md) </span></span>  
 <span data-ttu-id="7d790-125">[Eventi](../../../csharp/programming-guide/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="7d790-125">[Events](../../../csharp/programming-guide/events/index.md) </span></span>  
 <span data-ttu-id="7d790-126">[Delegati con metodi denominati e anonimi](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) </span><span class="sxs-lookup"><span data-stu-id="7d790-126">[Delegates with Named vs. Anonymous Methods](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) </span></span>  
 [<span data-ttu-id="7d790-127">Metodi anonimi</span><span class="sxs-lookup"><span data-stu-id="7d790-127">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)

