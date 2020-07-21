---
title: Matrici tipizzate in modo implicito - Guida per programmatori C#
description: Il tipo di una matrice tipizzata in modo implicito in C# viene dedotto dagli elementi nell'inizializzatore di matrice. Utilizzare matrici tipizzate in modo implicito nelle espressioni di query.
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], implicitly-typed
- implicitly-typed arrays [C#]
- C# language, implicitly typed arrays
ms.assetid: e05be95c-6732-403d-ae42-b35f057cbbea
ms.openlocfilehash: 1f14f68207dfb79c92eaa01ac2a8ffaa08facc03
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474709"
---
# <a name="implicitly-typed-arrays-c-programming-guide"></a><span data-ttu-id="9b10d-104">Matrici tipizzate in modo implicito (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="9b10d-104">Implicitly Typed Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="9b10d-105">È possibile creare una matrice tipizzata in modo implicito in cui il tipo dell'istanza della matrice viene derivato tramite inferenza dagli elementi specificati nell'inizializzatore di matrice.</span><span class="sxs-lookup"><span data-stu-id="9b10d-105">You can create an implicitly-typed array in which the type of the array instance is inferred from the elements specified in the array initializer.</span></span> <span data-ttu-id="9b10d-106">Le regole per qualsiasi variabile tipizzata in modo implicito si applicano anche alle matrici tipizzate in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="9b10d-106">The rules for any implicitly-typed variable also apply to implicitly-typed arrays.</span></span> <span data-ttu-id="9b10d-107">Per altre informazioni, vedere [Variabili locali tipizzate in modo implicito](../classes-and-structs/implicitly-typed-local-variables.md).</span><span class="sxs-lookup"><span data-stu-id="9b10d-107">For more information, see [Implicitly Typed Local Variables](../classes-and-structs/implicitly-typed-local-variables.md).</span></span>

<span data-ttu-id="9b10d-108">Le matrici tipizzate in modo implicito vengono in genere usate nelle espressioni di query insieme ai tipi anonimi e agli inizializzatori di oggetto e di raccolta.</span><span class="sxs-lookup"><span data-stu-id="9b10d-108">Implicitly-typed arrays are usually used in query expressions together with anonymous types and object and collection initializers.</span></span>

<span data-ttu-id="9b10d-109">Gli esempi seguenti illustrano come creare una matrice tipizzata in modo implicito:</span><span class="sxs-lookup"><span data-stu-id="9b10d-109">The following examples show how to create an implicitly-typed array:</span></span>

[!code-csharp[csProgGuideLINQ#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#37)]

<span data-ttu-id="9b10d-110">Nell'esempio precedente si noti che con le matrici tipizzate in modo implicito, non vengono usate parentesi quadre sul lato sinistro dell'istruzione di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="9b10d-110">In the previous example, notice that with implicitly-typed arrays, no square brackets are used on the left side of the initialization statement.</span></span> <span data-ttu-id="9b10d-111">Si noti anche che le matrici di matrici vengono inizializzate usando `new []` esattamente come le matrici unidimensionali.</span><span class="sxs-lookup"><span data-stu-id="9b10d-111">Note also that jagged arrays are initialized by using `new []` just like single-dimension arrays.</span></span>

## <a name="implicitly-typed-arrays-in-object-initializers"></a><span data-ttu-id="9b10d-112">Matrici tipizzate in modo implicito negli inizializzatori di oggetto</span><span class="sxs-lookup"><span data-stu-id="9b10d-112">Implicitly-typed Arrays in Object Initializers</span></span>

<span data-ttu-id="9b10d-113">Quando si crea un tipo anonimo che contiene una matrice, la matrice deve essere tipizzata in modo implicito nell'inizializzatore di oggetto del tipo.</span><span class="sxs-lookup"><span data-stu-id="9b10d-113">When you create an anonymous type that contains an array, the array must be implicitly typed in the type's object initializer.</span></span> <span data-ttu-id="9b10d-114">Nell'esempio seguente `contacts` è una matrice tipizzata in modo implicito di tipi anonimi, ognuno dei quali contiene una matrice denominata `PhoneNumbers`.</span><span class="sxs-lookup"><span data-stu-id="9b10d-114">In the following example, `contacts` is an implicitly-typed array of anonymous types, each of which contains an array named `PhoneNumbers`.</span></span> <span data-ttu-id="9b10d-115">Si noti che la parola chiave `var` non viene usata negli inizializzatori di oggetto.</span><span class="sxs-lookup"><span data-stu-id="9b10d-115">Note that the `var` keyword is not used inside the object initializers.</span></span>

[!code-csharp[csProgGuideLINQ#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#38)]

## <a name="see-also"></a><span data-ttu-id="9b10d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b10d-116">See also</span></span>

- [<span data-ttu-id="9b10d-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="9b10d-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="9b10d-118">Variabili locali tipizzate in modo implicito</span><span class="sxs-lookup"><span data-stu-id="9b10d-118">Implicitly Typed Local Variables</span></span>](../classes-and-structs/implicitly-typed-local-variables.md)
- [<span data-ttu-id="9b10d-119">Matrici</span><span class="sxs-lookup"><span data-stu-id="9b10d-119">Arrays</span></span>](./index.md)
- [<span data-ttu-id="9b10d-120">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="9b10d-120">Anonymous Types</span></span>](../classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="9b10d-121">Inizializzatori di oggetto e di raccolta</span><span class="sxs-lookup"><span data-stu-id="9b10d-121">Object and Collection Initializers</span></span>](../classes-and-structs/object-and-collection-initializers.md)
- [<span data-ttu-id="9b10d-122">var</span><span class="sxs-lookup"><span data-stu-id="9b10d-122">var</span></span>](../../language-reference/keywords/var.md)
- [<span data-ttu-id="9b10d-123">LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="9b10d-123">LINQ in C#</span></span>](../../linq/index.md)
