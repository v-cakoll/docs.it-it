---
title: Operatore [] (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '[]_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- subscript operator [C#]
- square brackets [ ] operator [C#]
- '[] operator [C#]'
- indexing operator [C#]
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
caps.latest.revision: 20
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
ms.openlocfilehash: b49d41af0dd4dc34b1b74c62ce8779aa31d69f77
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="5da8f-102">Operatore [] (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="5da8f-102">[] Operator (C# Reference)</span></span>
<span data-ttu-id="5da8f-103">Le parentesi quadre (`[]`) sono usate per le matrici, gli indicizzatori e gli attributi</span><span class="sxs-lookup"><span data-stu-id="5da8f-103">Square brackets (`[]`) are used for arrays, indexers, and attributes.</span></span> <span data-ttu-id="5da8f-104">ma possono essere usate anche per i puntatori.</span><span class="sxs-lookup"><span data-stu-id="5da8f-104">They can also be used with pointers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5da8f-105">Note</span><span class="sxs-lookup"><span data-stu-id="5da8f-105">Remarks</span></span>  
 <span data-ttu-id="5da8f-106">Un tipo matrice è un tipo seguito da `[]`:</span><span class="sxs-lookup"><span data-stu-id="5da8f-106">An array type is a type followed by `[]`:</span></span>  
  
 <span data-ttu-id="5da8f-107">[!code-cs[csRefOperators#43](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="5da8f-107">[!code-cs[csRefOperators#43](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_1.cs)]</span></span>  
  
 <span data-ttu-id="5da8f-108">Per consentire l'accesso a un elemento di una matrice, l'indice dell'elemento desiderato viene racchiuso tra parentesi:</span><span class="sxs-lookup"><span data-stu-id="5da8f-108">To access an element of an array, the index of the desired element is enclosed in brackets:</span></span>  
  
 <span data-ttu-id="5da8f-109">[!code-cs[csRefOperators#44](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="5da8f-109">[!code-cs[csRefOperators#44](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_2.cs)]</span></span>  
  
 <span data-ttu-id="5da8f-110">Se l'indice di una matrice non è incluso nell'intervallo, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="5da8f-110">An exception is thrown if an array index is out of range.</span></span>  
  
 <span data-ttu-id="5da8f-111">L'operatore di indicizzazione della matrice non può essere sottoposto a overload. I tipi, tuttavia, possono definire gli indicizzatori nonché le proprietà che accettano uno o più parametri.</span><span class="sxs-lookup"><span data-stu-id="5da8f-111">The array indexing operator cannot be overloaded; however, types can define indexers, and properties that take one or more parameters.</span></span> <span data-ttu-id="5da8f-112">I parametri dell'indicizzatore sono racchiusi tra parentesi quadre, come gli indici di matrice, ma a differenza di questi ultimi, che devono essere integrali, possono essere dichiarati come appartenenti a un tipo qualsiasi.</span><span class="sxs-lookup"><span data-stu-id="5da8f-112">Indexer parameters are enclosed in square brackets, just like array indexes, but indexer parameters can be declared to be of any type, unlike array indexes, which must be integral.</span></span>  
  
 <span data-ttu-id="5da8f-113">In .NET Framework, ad esempio, è possibile definire un tipo `Hashtable` che associa chiavi e valori di tipo arbitrario:</span><span class="sxs-lookup"><span data-stu-id="5da8f-113">For example, the .NET Framework defines a `Hashtable` type that associates keys and values of arbitrary type:</span></span>  
  
 <span data-ttu-id="5da8f-114">[!code-cs[csRefOperators#45](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="5da8f-114">[!code-cs[csRefOperators#45](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_3.cs)]</span></span>  
  
 <span data-ttu-id="5da8f-115">Le parentesi quadre vengono usate anche per specificare [attributi](../../../csharp/programming-guide/concepts/attributes/index.md):</span><span class="sxs-lookup"><span data-stu-id="5da8f-115">Square brackets are also used to specify [Attributes](../../../csharp/programming-guide/concepts/attributes/index.md):</span></span>  
  
 <span data-ttu-id="5da8f-116">[!code-cs[csRefOperators#46](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="5da8f-116">[!code-cs[csRefOperators#46](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_4.cs)]</span></span>  
  
 <span data-ttu-id="5da8f-117">È possibile usare le parentesi quadre per effettuare l'indicizzazione a partire da un puntatore:</span><span class="sxs-lookup"><span data-stu-id="5da8f-117">You can use square brackets to index off a pointer:</span></span>  
  
 <span data-ttu-id="5da8f-118">[!code-cs[csRefOperators#47](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="5da8f-118">[!code-cs[csRefOperators#47](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_5.cs)]</span></span>  
  
 <span data-ttu-id="5da8f-119">Non viene eseguito alcun controllo dei limiti.</span><span class="sxs-lookup"><span data-stu-id="5da8f-119">No bounds checking is performed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="5da8f-120">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="5da8f-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5da8f-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5da8f-121">See Also</span></span>  
 <span data-ttu-id="5da8f-122">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="5da8f-122">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="5da8f-123">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5da8f-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="5da8f-124">[Operatori C#](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="5da8f-124">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 <span data-ttu-id="5da8f-125">[Matrici](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="5da8f-125">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="5da8f-126">[Indicizzatori](../../../csharp/programming-guide/indexers/index.md) </span><span class="sxs-lookup"><span data-stu-id="5da8f-126">[Indexers](../../../csharp/programming-guide/indexers/index.md) </span></span>  
 <span data-ttu-id="5da8f-127">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="5da8f-127">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 [<span data-ttu-id="5da8f-128">Istruzione fixed</span><span class="sxs-lookup"><span data-stu-id="5da8f-128">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)

