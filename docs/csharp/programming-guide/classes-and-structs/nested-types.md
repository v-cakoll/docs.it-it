---
title: Tipi annidati (Guida per programmatori C#)
ms.date: 2017-07-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 853ec746d9be01ed63d7a229ca86e99d9f192374
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="nested-types-c-programming-guide"></a><span data-ttu-id="f82bf-102">Tipi annidati (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="f82bf-102">Nested Types (C# Programming Guide)</span></span>
<span data-ttu-id="f82bf-103">Per tipo annidato si intende un tipo definito all'interno di una [classe](../../../csharp/language-reference/keywords/class.md) o di uno [struct](../../../csharp/language-reference/keywords/struct.md).</span><span class="sxs-lookup"><span data-stu-id="f82bf-103">A type defined within a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md) is called a nested type.</span></span> <span data-ttu-id="f82bf-104">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f82bf-104">For example:</span></span>  
  
<span data-ttu-id="f82bf-105">[!code-cs[csProgGuideObjects#68](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f82bf-105">[!code-cs[csProgGuideObjects#68](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_1.cs)]</span></span>  
  
<span data-ttu-id="f82bf-106">Che il tipo esterno sia una classe o uno struct, per impostazione predefinita i tipi annidati sono [private](../../../csharp/language-reference/keywords/private.md) e sono accessibili solo dal relativo tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="f82bf-106">Regardless of whether the outer type is a class or a struct, nested types default to [private](../../../csharp/language-reference/keywords/private.md); they are accessible only from their containing type.</span></span> <span data-ttu-id="f82bf-107">Nell'esempio precedente, la classe `Nested` non è accessibile a tipi esterni.</span><span class="sxs-lookup"><span data-stu-id="f82bf-107">In the previous example, the `Nested` class is inaccessible to external types.</span></span> 

<span data-ttu-id="f82bf-108">È possibile anche specificare un [modificatore di accesso](../../language-reference/keywords/access-modifiers.md) per definire l'accessibilità di un tipo annidato, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f82bf-108">You can also specify an [access modifier](../../language-reference/keywords/access-modifiers.md) to define the accessibility of a nested type, as follows:</span></span>

- <span data-ttu-id="f82bf-109">I tipi annidati di una **classe** possono essere [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), `protected internal` o [private](../../../csharp/language-reference/keywords/private.md).</span><span class="sxs-lookup"><span data-stu-id="f82bf-109">Nested types of a **class** can be [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), `protected internal`, or [private](../../../csharp/language-reference/keywords/private.md).</span></span> 

   <span data-ttu-id="f82bf-110">La definizione di una classe annidata `protected` o `protected internal` all'interno di un [classe sealed](../../language-reference/keywords/sealed.md), tuttavia, genera l'avviso del compilatore [CS0628](../../misc/cs0628.md): "Il nuovo membro protected è stato dichiarato nella classe sealed".</span><span class="sxs-lookup"><span data-stu-id="f82bf-110">However, defining a `protected` or `protected internal` nested class inside a [sealed class](../../language-reference/keywords/sealed.md) generates compiler warning [CS0628](../../misc/cs0628.md), "new protected member declared in sealed class."</span></span>
  
- <span data-ttu-id="f82bf-111">I tipi annidati di uno **struct** possono essere [public](../../../csharp/language-reference/keywords/public.md), [internal](../../../csharp/language-reference/keywords/internal.md) o [private](../../../csharp/language-reference/keywords/private.md).</span><span class="sxs-lookup"><span data-stu-id="f82bf-111">Nested types of a **struct** can be [public](../../../csharp/language-reference/keywords/public.md), [internal](../../../csharp/language-reference/keywords/internal.md), or [private](../../../csharp/language-reference/keywords/private.md).</span></span>
  
<span data-ttu-id="f82bf-112">Nell'esempio seguente, la classe `Nested` viene resa public:</span><span class="sxs-lookup"><span data-stu-id="f82bf-112">The following example makes the `Nested` class public:</span></span>
  
<span data-ttu-id="f82bf-113">[!code-cs[csProgGuideObjects#69](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="f82bf-113">[!code-cs[csProgGuideObjects#69](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_2.cs)]</span></span>  
  
 <span data-ttu-id="f82bf-114">Il tipo annidato, o interno, può accedere al tipo contenitore, o esterno.</span><span class="sxs-lookup"><span data-stu-id="f82bf-114">The nested, or inner, type can access the containing, or outer, type.</span></span> <span data-ttu-id="f82bf-115">Per accedere al tipo contenitore, passarlo come argomento al costruttore del tipo annidato.</span><span class="sxs-lookup"><span data-stu-id="f82bf-115">To access the containing type, pass it as an argument to the constructor of the nested type.</span></span> <span data-ttu-id="f82bf-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f82bf-116">For example:</span></span>  
  
 <span data-ttu-id="f82bf-117">[!code-cs[csProgGuideObjects#70](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="f82bf-117">[!code-cs[csProgGuideObjects#70](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_3.cs)]</span></span>  
  
 <span data-ttu-id="f82bf-118">Un tipo annidato può accedere a tutti i membri accessibili al tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="f82bf-118">A nested type has access to all of the members that are accessible to its containing type.</span></span> <span data-ttu-id="f82bf-119">Può accedere a membri privati e protetti del tipo che li contengono, inclusi tutti i membri protetti ereditati.</span><span class="sxs-lookup"><span data-stu-id="f82bf-119">It can access private and protected members of the containing type, including any inherited protected members.</span></span>  
  
 <span data-ttu-id="f82bf-120">Nella dichiarazione precedente il nome completo della classe `Nested` è `Container.Nested`.</span><span class="sxs-lookup"><span data-stu-id="f82bf-120">In the previous declaration, the full name of class `Nested` is `Container.Nested`.</span></span> <span data-ttu-id="f82bf-121">Questo nome viene utilizzato per creare una nuova istanza della classe annidata, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f82bf-121">This is the name used to create a new instance of the nested class, as follows:</span></span>  
  
 <span data-ttu-id="f82bf-122">[!code-cs[csProgGuideObjects#71](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="f82bf-122">[!code-cs[csProgGuideObjects#71](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_4.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f82bf-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f82bf-123">See Also</span></span>  
 <span data-ttu-id="f82bf-124">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f82bf-124">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f82bf-125">[Classi e struct](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="f82bf-125">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="f82bf-126">[Modificatori di accesso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="f82bf-126">[Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span></span>  
 [<span data-ttu-id="f82bf-127">Costruttori</span><span class="sxs-lookup"><span data-stu-id="f82bf-127">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)

