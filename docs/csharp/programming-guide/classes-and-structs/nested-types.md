---
title: Tipi annidati (Guida per programmatori C#)
ms.date: 07/10/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ab13c68b638062ab89c90dbfc51b51b8d72d3bde
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="nested-types-c-programming-guide"></a><span data-ttu-id="d2b01-102">Tipi annidati (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="d2b01-102">Nested Types (C# Programming Guide)</span></span>
<span data-ttu-id="d2b01-103">Per tipo annidato si intende un tipo definito all'interno di una [classe](../../../csharp/language-reference/keywords/class.md) o di uno [struct](../../../csharp/language-reference/keywords/struct.md).</span><span class="sxs-lookup"><span data-stu-id="d2b01-103">A type defined within a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md) is called a nested type.</span></span> <span data-ttu-id="d2b01-104">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d2b01-104">For example:</span></span>  
  
[!code-csharp[csProgGuideObjects#68](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_1.cs)]  
  
<span data-ttu-id="d2b01-105">Che il tipo esterno sia una classe o uno struct, per impostazione predefinita i tipi annidati sono [private](../../../csharp/language-reference/keywords/private.md) e sono accessibili solo dal relativo tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="d2b01-105">Regardless of whether the outer type is a class or a struct, nested types default to [private](../../../csharp/language-reference/keywords/private.md); they are accessible only from their containing type.</span></span> <span data-ttu-id="d2b01-106">Nell'esempio precedente, la classe `Nested` non è accessibile a tipi esterni.</span><span class="sxs-lookup"><span data-stu-id="d2b01-106">In the previous example, the `Nested` class is inaccessible to external types.</span></span> 

<span data-ttu-id="d2b01-107">È possibile anche specificare un [modificatore di accesso](../../language-reference/keywords/access-modifiers.md) per definire l'accessibilità di un tipo annidato, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="d2b01-107">You can also specify an [access modifier](../../language-reference/keywords/access-modifiers.md) to define the accessibility of a nested type, as follows:</span></span>

- <span data-ttu-id="d2b01-108">Annidati di tipi di un **classe** può essere [pubblica](../../../csharp/language-reference/keywords/public.md), [protetti](../../../csharp/language-reference/keywords/protected.md), [interno](../../../csharp/language-reference/keywords/internal.md), [protected internal](../../../csharp/language-reference/keywords/protected-internal.md), [privata](../../../csharp/language-reference/keywords/private.md) o [protetto privato](../../../csharp/language-reference/keywords/private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="d2b01-108">Nested types of a **class** can be [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [protected internal](../../../csharp/language-reference/keywords/protected-internal.md), [private](../../../csharp/language-reference/keywords/private.md) or [private protected](../../../csharp/language-reference/keywords/private-protected.md).</span></span> 

   <span data-ttu-id="d2b01-109">Tuttavia, la definizione di un `protected`, `protected internal` o `private protected` annidati classe all'interno di un [classe sealed](../../language-reference/keywords/sealed.md) genera l'avviso del compilatore [CS0628](../../misc/cs0628.md), "nuovo membro protetto dichiarato nella classe sealed".</span><span class="sxs-lookup"><span data-stu-id="d2b01-109">However, defining a `protected`, `protected internal` or `private protected` nested class inside a [sealed class](../../language-reference/keywords/sealed.md) generates compiler warning [CS0628](../../misc/cs0628.md), "new protected member declared in sealed class."</span></span>
  
- <span data-ttu-id="d2b01-110">I tipi annidati di uno **struct** possono essere [public](../../../csharp/language-reference/keywords/public.md), [internal](../../../csharp/language-reference/keywords/internal.md) o [private](../../../csharp/language-reference/keywords/private.md).</span><span class="sxs-lookup"><span data-stu-id="d2b01-110">Nested types of a **struct** can be [public](../../../csharp/language-reference/keywords/public.md), [internal](../../../csharp/language-reference/keywords/internal.md), or [private](../../../csharp/language-reference/keywords/private.md).</span></span>
  
<span data-ttu-id="d2b01-111">Nell'esempio seguente, la classe `Nested` viene resa public:</span><span class="sxs-lookup"><span data-stu-id="d2b01-111">The following example makes the `Nested` class public:</span></span>
  
[!code-csharp[csProgGuideObjects#69](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_2.cs)]  
  
 <span data-ttu-id="d2b01-112">Il tipo annidato, o interno, può accedere al tipo contenitore, o esterno.</span><span class="sxs-lookup"><span data-stu-id="d2b01-112">The nested, or inner, type can access the containing, or outer, type.</span></span> <span data-ttu-id="d2b01-113">Per accedere al tipo contenitore, passarlo come argomento al costruttore del tipo annidato.</span><span class="sxs-lookup"><span data-stu-id="d2b01-113">To access the containing type, pass it as an argument to the constructor of the nested type.</span></span> <span data-ttu-id="d2b01-114">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d2b01-114">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#70](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_3.cs)]  
  
 <span data-ttu-id="d2b01-115">Un tipo annidato può accedere a tutti i membri accessibili al tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="d2b01-115">A nested type has access to all of the members that are accessible to its containing type.</span></span> <span data-ttu-id="d2b01-116">Può accedere a membri privati e protetti del tipo che li contengono, inclusi tutti i membri protetti ereditati.</span><span class="sxs-lookup"><span data-stu-id="d2b01-116">It can access private and protected members of the containing type, including any inherited protected members.</span></span>  
  
 <span data-ttu-id="d2b01-117">Nella dichiarazione precedente il nome completo della classe `Nested` è `Container.Nested`.</span><span class="sxs-lookup"><span data-stu-id="d2b01-117">In the previous declaration, the full name of class `Nested` is `Container.Nested`.</span></span> <span data-ttu-id="d2b01-118">Questo nome viene utilizzato per creare una nuova istanza della classe annidata, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="d2b01-118">This is the name used to create a new instance of the nested class, as follows:</span></span>  
  
 [!code-csharp[csProgGuideObjects#71](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_4.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="d2b01-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2b01-119">See Also</span></span>  
 [<span data-ttu-id="d2b01-120">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="d2b01-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d2b01-121">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="d2b01-121">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="d2b01-122">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="d2b01-122">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="d2b01-123">Costruttori</span><span class="sxs-lookup"><span data-stu-id="d2b01-123">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)
