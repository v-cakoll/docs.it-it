---
title: Matrici tipizzate in modo implicito - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], implicity-typed
- implicitly-typed arrays [C#]
- C# language, implicitly typed arrays
ms.assetid: e05be95c-6732-403d-ae42-b35f057cbbea
ms.openlocfilehash: 9c235b6084238917c2cb3f2cd745aef0264f82ce
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53238273"
---
# <a name="implicitly-typed-arrays-c-programming-guide"></a><span data-ttu-id="a11d1-102">Matrici tipizzate in modo implicito (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="a11d1-102">Implicitly Typed Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="a11d1-103">È possibile creare una matrice tipizzata in modo implicito in cui il tipo dell'istanza della matrice viene derivato tramite inferenza dagli elementi specificati nell'inizializzatore di matrice.</span><span class="sxs-lookup"><span data-stu-id="a11d1-103">You can create an implicitly-typed array in which the type of the array instance is inferred from the elements specified in the array initializer.</span></span> <span data-ttu-id="a11d1-104">Le regole per qualsiasi variabile tipizzata in modo implicito si applicano anche alle matrici tipizzate in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="a11d1-104">The rules for any implicitly-typed variable also apply to implicitly-typed arrays.</span></span> <span data-ttu-id="a11d1-105">Per altre informazioni, vedere [Variabili locali tipizzate in modo implicito](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).</span><span class="sxs-lookup"><span data-stu-id="a11d1-105">For more information, see [Implicitly Typed Local Variables](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).</span></span>  
  
 <span data-ttu-id="a11d1-106">Le matrici tipizzate in modo implicito vengono in genere usate nelle espressioni di query insieme ai tipi anonimi e agli inizializzatori di oggetto e di raccolta.</span><span class="sxs-lookup"><span data-stu-id="a11d1-106">Implicitly-typed arrays are usually used in query expressions together with anonymous types and object and collection initializers.</span></span>  
  
 <span data-ttu-id="a11d1-107">Gli esempi seguenti illustrano come creare una matrice tipizzata in modo implicito:</span><span class="sxs-lookup"><span data-stu-id="a11d1-107">The following examples show how to create an implicitly-typed array:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_1.cs)]  
  
 <span data-ttu-id="a11d1-108">Nell'esempio precedente si noti che con le matrici tipizzate in modo implicito, non vengono usate parentesi quadre sul lato sinistro dell'istruzione di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="a11d1-108">In the previous example, notice that with implicitly-typed arrays, no square brackets are used on the left side of the initialization statement.</span></span> <span data-ttu-id="a11d1-109">Si noti anche che le matrici di matrici vengono inizializzate usando `new []` esattamente come le matrici unidimensionali.</span><span class="sxs-lookup"><span data-stu-id="a11d1-109">Note also that jagged arrays are initialized by using `new []` just like single-dimension arrays.</span></span>  
  
## <a name="implicitly-typed-arrays-in-object-initializers"></a><span data-ttu-id="a11d1-110">Matrici tipizzate in modo implicito negli inizializzatori di oggetto</span><span class="sxs-lookup"><span data-stu-id="a11d1-110">Implicitly-typed Arrays in Object Initializers</span></span>

 <span data-ttu-id="a11d1-111">Quando si crea un tipo anonimo che contiene una matrice, la matrice deve essere tipizzata in modo implicito nell'inizializzatore di oggetto del tipo.</span><span class="sxs-lookup"><span data-stu-id="a11d1-111">When you create an anonymous type that contains an array, the array must be implicitly typed in the type's object initializer.</span></span> <span data-ttu-id="a11d1-112">Nell'esempio seguente `contacts` è una matrice tipizzata in modo implicito di tipi anonimi, ognuno dei quali contiene una matrice denominata `PhoneNumbers`.</span><span class="sxs-lookup"><span data-stu-id="a11d1-112">In the following example, `contacts` is an implicitly-typed array of anonymous types, each of which contains an array named `PhoneNumbers`.</span></span> <span data-ttu-id="a11d1-113">Si noti che la parola chiave `var` non viene usata negli inizializzatori di oggetto.</span><span class="sxs-lookup"><span data-stu-id="a11d1-113">Note that the `var` keyword is not used inside the object initializers.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="a11d1-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a11d1-114">See Also</span></span>

- [<span data-ttu-id="a11d1-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="a11d1-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="a11d1-116">Variabili locali tipizzate in modo implicito</span><span class="sxs-lookup"><span data-stu-id="a11d1-116">Implicitly Typed Local Variables</span></span>](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)  
- [<span data-ttu-id="a11d1-117">Matrici</span><span class="sxs-lookup"><span data-stu-id="a11d1-117">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
- [<span data-ttu-id="a11d1-118">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="a11d1-118">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)  
- [<span data-ttu-id="a11d1-119">Inizializzatori di oggetto e di raccolta</span><span class="sxs-lookup"><span data-stu-id="a11d1-119">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)  
- [<span data-ttu-id="a11d1-120">var</span><span class="sxs-lookup"><span data-stu-id="a11d1-120">var</span></span>](../../../csharp/language-reference/keywords/var.md)  
- [<span data-ttu-id="a11d1-121">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="a11d1-121">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)
