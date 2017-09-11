---
title: Matrici tipizzate in modo implicito (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#], implicity-typed
- implicitly-typed arrays [C#]
- C# language, implicitly typed arrays
ms.assetid: e05be95c-6732-403d-ae42-b35f057cbbea
caps.latest.revision: 13
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
ms.openlocfilehash: 5a042bdebd07062debe70cbea0a9661fbd425804
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="implicitly-typed-arrays-c-programming-guide"></a><span data-ttu-id="e29e6-102">Matrici tipizzate in modo implicito (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="e29e6-102">Implicitly Typed Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="e29e6-103">È possibile creare una matrice tipizzata in modo implicito in cui il tipo dell'istanza della matrice viene derivato tramite inferenza dagli elementi specificati nell'inizializzatore di matrice.</span><span class="sxs-lookup"><span data-stu-id="e29e6-103">You can create an implicitly-typed array in which the type of the array instance is inferred from the elements specified in the array initializer.</span></span> <span data-ttu-id="e29e6-104">Le regole per qualsiasi variabile tipizzata in modo implicito si applicano anche alle matrici tipizzate in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="e29e6-104">The rules for any implicitly-typed variable also apply to implicitly-typed arrays.</span></span> <span data-ttu-id="e29e6-105">Per altre informazioni, vedere [Variabili locali tipizzate in modo implicito](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).</span><span class="sxs-lookup"><span data-stu-id="e29e6-105">For more information, see [Implicitly Typed Local Variables](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).</span></span>  
  
 <span data-ttu-id="e29e6-106">Le matrici tipizzate in modo implicito vengono in genere usate nelle espressioni di query insieme ai tipi anonimi e agli inizializzatori di oggetto e di raccolta.</span><span class="sxs-lookup"><span data-stu-id="e29e6-106">Implicitly-typed arrays are usually used in query expressions together with anonymous types and object and collection initializers.</span></span>  
  
 <span data-ttu-id="e29e6-107">Gli esempi seguenti illustrano come creare una matrice tipizzata in modo implicito:</span><span class="sxs-lookup"><span data-stu-id="e29e6-107">The following examples show how to create an implicitly-typed array:</span></span>  
  
 <span data-ttu-id="e29e6-108">[!code-cs[csProgGuideLINQ#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e29e6-108">[!code-cs[csProgGuideLINQ#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_1.cs)]</span></span>  
  
 <span data-ttu-id="e29e6-109">Nell'esempio precedente si noti che con le matrici tipizzate in modo implicito, non vengono usate parentesi quadre sul lato sinistro dell'istruzione di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="e29e6-109">In the previous example, notice that with implicitly-typed arrays, no square brackets are used on the left side of the initialization statement.</span></span> <span data-ttu-id="e29e6-110">Si noti anche che le matrici di matrici vengono inizializzate usando `new []` esattamente come le matrici unidimensionali.</span><span class="sxs-lookup"><span data-stu-id="e29e6-110">Note also that jagged arrays are initialized by using `new []` just like single-dimension arrays.</span></span>  
  
## <a name="implicitly-typed-arrays-in-object-initializers"></a><span data-ttu-id="e29e6-111">Matrici tipizzate in modo implicito negli inizializzatori di oggetto</span><span class="sxs-lookup"><span data-stu-id="e29e6-111">Implicitly-typed Arrays in Object Initializers</span></span>  
 <span data-ttu-id="e29e6-112">Quando si crea un tipo anonimo che contiene una matrice, la matrice deve essere tipizzata in modo implicito nell'inizializzatore di oggetto del tipo.</span><span class="sxs-lookup"><span data-stu-id="e29e6-112">When you create an anonymous type that contains an array, the array must be implicitly typed in the type's object initializer.</span></span> <span data-ttu-id="e29e6-113">Nell'esempio seguente `contacts` è una matrice tipizzata in modo implicito di tipi anonimi, ognuno dei quali contiene una matrice denominata `PhoneNumbers`.</span><span class="sxs-lookup"><span data-stu-id="e29e6-113">In the following example, `contacts` is an implicitly-typed array of anonymous types, each of which contains an array named `PhoneNumbers`.</span></span> <span data-ttu-id="e29e6-114">Si noti che la parola chiave `var` non viene usata negli inizializzatori di oggetto.</span><span class="sxs-lookup"><span data-stu-id="e29e6-114">Note that the `var` keyword is not used inside the object initializers.</span></span>  
  
 <span data-ttu-id="e29e6-115">[!code-cs[csProgGuideLINQ#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="e29e6-115">[!code-cs[csProgGuideLINQ#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e29e6-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e29e6-116">See Also</span></span>  
 <span data-ttu-id="e29e6-117">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e29e6-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e29e6-118">[Variabili locali tipizzate in modo implicito](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) </span><span class="sxs-lookup"><span data-stu-id="e29e6-118">[Implicitly Typed Local Variables](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) </span></span>  
 <span data-ttu-id="e29e6-119">[Matrici](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="e29e6-119">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="e29e6-120">[Tipi anonimi](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="e29e6-120">[Anonymous Types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) </span></span>  
 <span data-ttu-id="e29e6-121">[Inizializzatori di oggetto e di raccolta](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md) </span><span class="sxs-lookup"><span data-stu-id="e29e6-121">[Object and Collection Initializers](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md) </span></span>  
 <span data-ttu-id="e29e6-122">[var](../../../csharp/language-reference/keywords/var.md) </span><span class="sxs-lookup"><span data-stu-id="e29e6-122">[var](../../../csharp/language-reference/keywords/var.md) </span></span>  
 [<span data-ttu-id="e29e6-123">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="e29e6-123">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)

