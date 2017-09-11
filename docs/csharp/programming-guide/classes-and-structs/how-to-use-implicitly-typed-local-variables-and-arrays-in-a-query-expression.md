---
title: 'Procedura: utilizzare variabili e matrici locali tipizzate in modo implicito in un''espressione di query (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- implicitly-typed local variables [C#], how to use
ms.assetid: 6b7354d2-af79-427a-b6a8-f74eb8fd0b91
caps.latest.revision: 15
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
ms.openlocfilehash: 60e22aacef05ae2fe1b5e7127396cc66f24661d3
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression-c-programming-guide"></a><span data-ttu-id="0795d-102">Procedura: utilizzare variabili e matrici locali tipizzate in modo implicito in un'espressione di query (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="0795d-102">How to: Use Implicitly Typed Local Variables and Arrays in a Query Expression (C# Programming Guide)</span></span>
<span data-ttu-id="0795d-103">È possibile usare le variabili locali tipizzate in modo implicito ogni volta che si vuole che il compilatore determini il tipo di una variabile locale.</span><span class="sxs-lookup"><span data-stu-id="0795d-103">You can use implicitly typed local variables whenever you want the compiler to determine the type of a local variable.</span></span> <span data-ttu-id="0795d-104">È necessario usare le variabili locali tipizzate in modo implicito per archiviare i tipi anonimi, che vengono spesso usati nelle espressioni di query.</span><span class="sxs-lookup"><span data-stu-id="0795d-104">You must use implicitly typed local variables to store anonymous types, which are often used in query expressions.</span></span> <span data-ttu-id="0795d-105">Gli esempi seguenti illustrano tipi d'uso facoltativi e obbligatori delle variabili locali tipizzate in modo implicito nelle query.</span><span class="sxs-lookup"><span data-stu-id="0795d-105">The following examples illustrate both optional and required uses of implicitly typed local variables in queries.</span></span>  
  
 <span data-ttu-id="0795d-106">Le variabili locali tipizzate in modo implicito vengono dichiarate usando la parola chiave contestuale [var](../../../csharp/language-reference/keywords/var.md).</span><span class="sxs-lookup"><span data-stu-id="0795d-106">Implicitly typed local variables are declared by using the [var](../../../csharp/language-reference/keywords/var.md) contextual keyword.</span></span> <span data-ttu-id="0795d-107">Per altre informazioni, vedere [Variabili locali tipizzate in modo implicito](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) e [Matrici tipizzate in modo implicito](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="0795d-107">For more information, see [Implicitly Typed Local Variables](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) and [Implicitly Typed Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0795d-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="0795d-108">Example</span></span>  
 <span data-ttu-id="0795d-109">L'esempio seguente mostra uno scenario comune in cui la parola chiave `var` è obbligatoria: un'espressione di query che produce una sequenza di tipi anonimi.</span><span class="sxs-lookup"><span data-stu-id="0795d-109">The following example shows a common scenario in which the `var` keyword is required: a query expression that produces a sequence of anonymous types.</span></span> <span data-ttu-id="0795d-110">In questo scenario sia la variabile di query che la variabile di iterazione nell'istruzione `foreach` devono essere tipizzate in modo implicito usando `var`, perché non si ha accesso a un nome di tipo per il tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="0795d-110">In this scenario, both the query variable and the iteration variable in the `foreach` statement must be implicitly typed by using `var` because you do not have access to a type name for the anonymous type.</span></span> <span data-ttu-id="0795d-111">Per altre informazioni sui tipi anonimi, vedere [Tipi anonimi](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="0795d-111">For more information about anonymous types, see [Anonymous Types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span>  
  
 <span data-ttu-id="0795d-112">[!code-cs[csProgGuideLINQ#32](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="0795d-112">[!code-cs[csProgGuideLINQ#32](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="0795d-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="0795d-113">Example</span></span>  
 <span data-ttu-id="0795d-114">L'esempio seguente usa la parola chiave `var` in una situazione simile, ma in cui l'uso di `var` è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0795d-114">The following example uses the `var` keyword in a situation that is similar, but in which the use of `var` is optional.</span></span> <span data-ttu-id="0795d-115">Poiché `student.LastName` è una stringa, l'esecuzione della query restituisce una sequenza di stringhe.</span><span class="sxs-lookup"><span data-stu-id="0795d-115">Because `student.LastName` is a string, execution of the query returns a sequence of strings.</span></span> <span data-ttu-id="0795d-116">Il tipo di `queryID` può quindi essere dichiarato come `System.Collections.Generic.IEnumerable<string>` invece di `var`.</span><span class="sxs-lookup"><span data-stu-id="0795d-116">Therefore, the type of `queryID` could be declared as `System.Collections.Generic.IEnumerable<string>` instead of `var`.</span></span> <span data-ttu-id="0795d-117">La parola chiave `var` viene usata per praticità.</span><span class="sxs-lookup"><span data-stu-id="0795d-117">Keyword `var` is used for convenience.</span></span> <span data-ttu-id="0795d-118">Nell'esempio la variabile di iterazione nell'istruzione `foreach` è tipizzata in modo esplicito come stringa, ma potrebbe invece essere dichiarata usando `var`.</span><span class="sxs-lookup"><span data-stu-id="0795d-118">In the example, the iteration variable in the `foreach` statement is explicitly typed as a string, but it could instead be declared by using `var`.</span></span> <span data-ttu-id="0795d-119">Poiché il tipo della variabile di iterazione non è un tipo anonimo, l'uso di `var` è facoltativo e non obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0795d-119">Because the type of the iteration variable is not an anonymous type, the use of `var` is an option, not a requirement.</span></span> <span data-ttu-id="0795d-120">Tenere presente che `var` non è un tipo, ma un'istruzione che indica al compilatore di derivare tramite inferenza e assegnare il tipo.</span><span class="sxs-lookup"><span data-stu-id="0795d-120">Remember, `var` itself is not a type, but an instruction to the compiler to infer and assign the type.</span></span>  
  
 <span data-ttu-id="0795d-121">[!code-cs[csProgGuideLINQ#33](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="0795d-121">[!code-cs[csProgGuideLINQ#33](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0795d-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0795d-122">See Also</span></span>  
 <span data-ttu-id="0795d-123">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0795d-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="0795d-124">[Metodi di estensione](../../../csharp/programming-guide/classes-and-structs/extension-methods.md) </span><span class="sxs-lookup"><span data-stu-id="0795d-124">[Extension Methods](../../../csharp/programming-guide/classes-and-structs/extension-methods.md) </span></span>  
 <span data-ttu-id="0795d-125">[LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) </span><span class="sxs-lookup"><span data-stu-id="0795d-125">[LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) </span></span>  
 <span data-ttu-id="0795d-126">[var](../../../csharp/language-reference/keywords/var.md) </span><span class="sxs-lookup"><span data-stu-id="0795d-126">[var](../../../csharp/language-reference/keywords/var.md) </span></span>  
 [<span data-ttu-id="0795d-127">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="0795d-127">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)

