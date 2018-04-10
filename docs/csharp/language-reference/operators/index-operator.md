---
title: Operatore [] (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '[]_CSharpKeyword'
helpviewer_keywords:
- subscript operator [C#]
- square brackets [ ] operator [C#]
- '[] operator [C#]'
- indexing operator [C#]
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 03664f5604bb7d7dce9e8ae2ff0ec045c6a203b1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="0b78c-102">Operatore [] (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="0b78c-102">[] Operator (C# Reference)</span></span>
<span data-ttu-id="0b78c-103">Le parentesi quadre (`[]`) sono usate per le matrici, gli indicizzatori e gli attributi</span><span class="sxs-lookup"><span data-stu-id="0b78c-103">Square brackets (`[]`) are used for arrays, indexers, and attributes.</span></span> <span data-ttu-id="0b78c-104">ma possono essere usate anche per i puntatori.</span><span class="sxs-lookup"><span data-stu-id="0b78c-104">They can also be used with pointers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b78c-105">Note</span><span class="sxs-lookup"><span data-stu-id="0b78c-105">Remarks</span></span>  
 <span data-ttu-id="0b78c-106">Un tipo matrice è un tipo seguito da `[]`:</span><span class="sxs-lookup"><span data-stu-id="0b78c-106">An array type is a type followed by `[]`:</span></span>  
  
 [!code-csharp[csRefOperators#43](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_1.cs)]  
  
 <span data-ttu-id="0b78c-107">Per consentire l'accesso a un elemento di una matrice, l'indice dell'elemento desiderato viene racchiuso tra parentesi:</span><span class="sxs-lookup"><span data-stu-id="0b78c-107">To access an element of an array, the index of the desired element is enclosed in brackets:</span></span>  
  
 [!code-csharp[csRefOperators#44](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_2.cs)]  
  
 <span data-ttu-id="0b78c-108">Se l'indice di una matrice non è incluso nell'intervallo, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="0b78c-108">An exception is thrown if an array index is out of range.</span></span>  
  
 <span data-ttu-id="0b78c-109">L'operatore di indicizzazione della matrice non può essere sottoposto a overload. I tipi, tuttavia, possono definire gli indicizzatori nonché le proprietà che accettano uno o più parametri.</span><span class="sxs-lookup"><span data-stu-id="0b78c-109">The array indexing operator cannot be overloaded; however, types can define indexers, and properties that take one or more parameters.</span></span> <span data-ttu-id="0b78c-110">I parametri dell'indicizzatore sono racchiusi tra parentesi quadre, come gli indici di matrice, ma a differenza di questi ultimi, che devono essere integrali, possono essere dichiarati come appartenenti a un tipo qualsiasi.</span><span class="sxs-lookup"><span data-stu-id="0b78c-110">Indexer parameters are enclosed in square brackets, just like array indexes, but indexer parameters can be declared to be of any type, unlike array indexes, which must be integral.</span></span>  
  
 <span data-ttu-id="0b78c-111">In .NET Framework, ad esempio, è possibile definire un tipo `Hashtable` che associa chiavi e valori di tipo arbitrario:</span><span class="sxs-lookup"><span data-stu-id="0b78c-111">For example, the .NET Framework defines a `Hashtable` type that associates keys and values of arbitrary type:</span></span>  
  
 [!code-csharp[csRefOperators#45](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_3.cs)]  
  
 <span data-ttu-id="0b78c-112">Le parentesi quadre vengono usate anche per specificare [attributi](../../../csharp/programming-guide/concepts/attributes/index.md):</span><span class="sxs-lookup"><span data-stu-id="0b78c-112">Square brackets are also used to specify [Attributes](../../../csharp/programming-guide/concepts/attributes/index.md):</span></span>  
  
 [!code-csharp[csRefOperators#46](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_4.cs)]  
  
 <span data-ttu-id="0b78c-113">È possibile usare le parentesi quadre per effettuare l'indicizzazione a partire da un puntatore:</span><span class="sxs-lookup"><span data-stu-id="0b78c-113">You can use square brackets to index off a pointer:</span></span>  
  
 [!code-csharp[csRefOperators#47](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_5.cs)]  
  
 <span data-ttu-id="0b78c-114">Non viene eseguito alcun controllo dei limiti.</span><span class="sxs-lookup"><span data-stu-id="0b78c-114">No bounds checking is performed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="0b78c-115">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="0b78c-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0b78c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b78c-116">See Also</span></span>  
 [<span data-ttu-id="0b78c-117">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="0b78c-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="0b78c-118">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="0b78c-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0b78c-119">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="0b78c-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="0b78c-120">Array</span><span class="sxs-lookup"><span data-stu-id="0b78c-120">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="0b78c-121">Indicizzatori</span><span class="sxs-lookup"><span data-stu-id="0b78c-121">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)  
 [<span data-ttu-id="0b78c-122">unsafe</span><span class="sxs-lookup"><span data-stu-id="0b78c-122">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="0b78c-123">Istruzione fixed</span><span class="sxs-lookup"><span data-stu-id="0b78c-123">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
