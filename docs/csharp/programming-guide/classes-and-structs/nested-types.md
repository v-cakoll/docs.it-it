---
title: Tipi annidati - Guida per programmatori C#
ms.date: 07/10/2017
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
ms.openlocfilehash: 982eeceb2088dd6e1e57fe796b38e46c0f2d4de8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705496"
---
# <a name="nested-types-c-programming-guide"></a><span data-ttu-id="d1541-102">Tipi annidati (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="d1541-102">Nested Types (C# Programming Guide)</span></span>
<span data-ttu-id="d1541-103">Per tipo annidato si intende un tipo definito all'interno di una [classe](../../language-reference/keywords/class.md) o di uno [struct](../../language-reference/keywords/struct.md).</span><span class="sxs-lookup"><span data-stu-id="d1541-103">A type defined within a [class](../../language-reference/keywords/class.md) or [struct](../../language-reference/keywords/struct.md) is called a nested type.</span></span> <span data-ttu-id="d1541-104">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d1541-104">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#68](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#68)]  
  
<span data-ttu-id="d1541-105">Che il tipo esterno sia una classe o uno struct, per impostazione predefinita i tipi annidati sono [private](../../language-reference/keywords/private.md) e sono accessibili solo dal relativo tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="d1541-105">Regardless of whether the outer type is a class or a struct, nested types default to [private](../../language-reference/keywords/private.md); they are accessible only from their containing type.</span></span> <span data-ttu-id="d1541-106">Nell'esempio precedente, la classe `Nested` non è accessibile a tipi esterni.</span><span class="sxs-lookup"><span data-stu-id="d1541-106">In the previous example, the `Nested` class is inaccessible to external types.</span></span> 

<span data-ttu-id="d1541-107">È possibile anche specificare un [modificatore di accesso](../../language-reference/keywords/access-modifiers.md) per definire l'accessibilità di un tipo annidato, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="d1541-107">You can also specify an [access modifier](../../language-reference/keywords/access-modifiers.md) to define the accessibility of a nested type, as follows:</span></span>

- <span data-ttu-id="d1541-108">I tipi annidati di una **classe** possono essere [public](../../language-reference/keywords/public.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md), [private](../../language-reference/keywords/private.md) o [private protected](../../language-reference/keywords/private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="d1541-108">Nested types of a **class** can be [public](../../language-reference/keywords/public.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md), [private](../../language-reference/keywords/private.md) or [private protected](../../language-reference/keywords/private-protected.md).</span></span> 

   <span data-ttu-id="d1541-109">La definizione di una classe annidata `protected`, `protected internal` o `private protected` all'interno di un [classe sealed](../../language-reference/keywords/sealed.md), tuttavia, genera l'avviso del compilatore [CS0628](../../misc/cs0628.md): "Il nuovo membro protected è stato dichiarato nella classe sealed".</span><span class="sxs-lookup"><span data-stu-id="d1541-109">However, defining a `protected`, `protected internal` or `private protected` nested class inside a [sealed class](../../language-reference/keywords/sealed.md) generates compiler warning [CS0628](../../misc/cs0628.md), "new protected member declared in sealed class."</span></span>
  
- <span data-ttu-id="d1541-110">I tipi annidati di uno **struct** possono essere [public](../../language-reference/keywords/public.md), [internal](../../language-reference/keywords/internal.md) o [private](../../language-reference/keywords/private.md).</span><span class="sxs-lookup"><span data-stu-id="d1541-110">Nested types of a **struct** can be [public](../../language-reference/keywords/public.md), [internal](../../language-reference/keywords/internal.md), or [private](../../language-reference/keywords/private.md).</span></span>
  
<span data-ttu-id="d1541-111">Nell'esempio seguente, la classe `Nested` viene resa public:</span><span class="sxs-lookup"><span data-stu-id="d1541-111">The following example makes the `Nested` class public:</span></span>
  
 [!code-csharp[csProgGuideObjects#69](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#69)]  
  
 <span data-ttu-id="d1541-112">Il tipo annidato, o interno, può accedere al tipo contenitore, o esterno.</span><span class="sxs-lookup"><span data-stu-id="d1541-112">The nested, or inner, type can access the containing, or outer, type.</span></span> <span data-ttu-id="d1541-113">Per accedere al tipo contenitore, passarlo come argomento al costruttore del tipo annidato.</span><span class="sxs-lookup"><span data-stu-id="d1541-113">To access the containing type, pass it as an argument to the constructor of the nested type.</span></span> <span data-ttu-id="d1541-114">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d1541-114">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#70](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#70)]  
  
 <span data-ttu-id="d1541-115">Un tipo annidato può accedere a tutti i membri accessibili al tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="d1541-115">A nested type has access to all of the members that are accessible to its containing type.</span></span> <span data-ttu-id="d1541-116">Può accedere a membri privati e protetti del tipo che li contengono, inclusi tutti i membri protetti ereditati.</span><span class="sxs-lookup"><span data-stu-id="d1541-116">It can access private and protected members of the containing type, including any inherited protected members.</span></span>  
  
 <span data-ttu-id="d1541-117">Nella dichiarazione precedente il nome completo della classe `Nested` è `Container.Nested`.</span><span class="sxs-lookup"><span data-stu-id="d1541-117">In the previous declaration, the full name of class `Nested` is `Container.Nested`.</span></span> <span data-ttu-id="d1541-118">Questo nome viene utilizzato per creare una nuova istanza della classe annidata, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="d1541-118">This is the name used to create a new instance of the nested class, as follows:</span></span>  
  
 [!code-csharp[csProgGuideObjects#71](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#71)]  
  
## <a name="see-also"></a><span data-ttu-id="d1541-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1541-119">See also</span></span>

- [<span data-ttu-id="d1541-120">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="d1541-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d1541-121">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="d1541-121">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="d1541-122">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="d1541-122">Access Modifiers</span></span>](./access-modifiers.md)
- [<span data-ttu-id="d1541-123">Costruttori</span><span class="sxs-lookup"><span data-stu-id="d1541-123">Constructors</span></span>](./constructors.md)
