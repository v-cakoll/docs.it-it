---
title: Tipi annidati - Guida per programmatori C#
description: Un tipo definito all'interno di una classe, uno struct o un'interfaccia viene definito tipo annidato in C#.
ms.date: 02/08/2020
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
ms.openlocfilehash: 9e1c6c1e8b22b5447d43915ab02984aa13146301
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864943"
---
# <a name="nested-types-c-programming-guide"></a><span data-ttu-id="d54c1-103">Tipi annidati (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="d54c1-103">Nested Types (C# Programming Guide)</span></span>

<span data-ttu-id="d54c1-104">Un tipo definito all'interno di una [classe](../../language-reference/keywords/class.md), uno [struct](../../language-reference/builtin-types/struct.md)o un' [interfaccia](../../language-reference/keywords/interface.md) viene definito tipo annidato.</span><span class="sxs-lookup"><span data-stu-id="d54c1-104">A type defined within a [class](../../language-reference/keywords/class.md), [struct](../../language-reference/builtin-types/struct.md), or [interface](../../language-reference/keywords/interface.md) is called a nested type.</span></span> <span data-ttu-id="d54c1-105">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d54c1-105">For example</span></span>

[!code-csharp[DeclareNestedClass](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#DeclareNestedClass)]

<span data-ttu-id="d54c1-106">Indipendentemente dal fatto che il tipo esterno sia una classe, un'interfaccia o uno struct, i tipi annidati per impostazione predefinita sono [privati](../../language-reference/keywords/private.md); sono accessibili solo dal tipo che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="d54c1-106">Regardless of whether the outer type is a class, interface, or struct, nested types default to [private](../../language-reference/keywords/private.md); they are accessible only from their containing type.</span></span> <span data-ttu-id="d54c1-107">Nell'esempio precedente, la classe `Nested` non è accessibile a tipi esterni.</span><span class="sxs-lookup"><span data-stu-id="d54c1-107">In the previous example, the `Nested` class is inaccessible to external types.</span></span>

<span data-ttu-id="d54c1-108">È possibile anche specificare un [modificatore di accesso](../../language-reference/keywords/access-modifiers.md) per definire l'accessibilità di un tipo annidato, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="d54c1-108">You can also specify an [access modifier](../../language-reference/keywords/access-modifiers.md) to define the accessibility of a nested type, as follows:</span></span>

- <span data-ttu-id="d54c1-109">I tipi annidati di una **classe** possono essere [public](../../language-reference/keywords/public.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md), [private](../../language-reference/keywords/private.md) o [private protected](../../language-reference/keywords/private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="d54c1-109">Nested types of a **class** can be [public](../../language-reference/keywords/public.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md), [private](../../language-reference/keywords/private.md) or [private protected](../../language-reference/keywords/private-protected.md).</span></span>

   <span data-ttu-id="d54c1-110">La definizione di una classe annidata `protected`, `protected internal` o `private protected` all'interno di un [classe sealed](../../language-reference/keywords/sealed.md), tuttavia, genera l'avviso del compilatore [CS0628](../../misc/cs0628.md): "Il nuovo membro protected è stato dichiarato nella classe sealed".</span><span class="sxs-lookup"><span data-stu-id="d54c1-110">However, defining a `protected`, `protected internal` or `private protected` nested class inside a [sealed class](../../language-reference/keywords/sealed.md) generates compiler warning [CS0628](../../misc/cs0628.md), "new protected member declared in sealed class."</span></span>
  
- <span data-ttu-id="d54c1-111">I tipi annidati di uno **struct** possono essere [public](../../language-reference/keywords/public.md), [internal](../../language-reference/keywords/internal.md) o [private](../../language-reference/keywords/private.md).</span><span class="sxs-lookup"><span data-stu-id="d54c1-111">Nested types of a **struct** can be [public](../../language-reference/keywords/public.md), [internal](../../language-reference/keywords/internal.md), or [private](../../language-reference/keywords/private.md).</span></span>

<span data-ttu-id="d54c1-112">Nell'esempio seguente, la classe `Nested` viene resa public:</span><span class="sxs-lookup"><span data-stu-id="d54c1-112">The following example makes the `Nested` class public:</span></span>

[!code-csharp[PublicNestedClass](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#PublicNestedClass)]

<span data-ttu-id="d54c1-113">Il tipo annidato, o interno, può accedere al tipo contenitore, o esterno.</span><span class="sxs-lookup"><span data-stu-id="d54c1-113">The nested, or inner, type can access the containing, or outer, type.</span></span> <span data-ttu-id="d54c1-114">Per accedere al tipo contenitore, passarlo come argomento al costruttore del tipo annidato.</span><span class="sxs-lookup"><span data-stu-id="d54c1-114">To access the containing type, pass it as an argument to the constructor of the nested type.</span></span> <span data-ttu-id="d54c1-115">ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d54c1-115">For example:</span></span>

[!code-csharp[DeclareNestedInstance](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#DeclareNestedInstance)]

<span data-ttu-id="d54c1-116">Un tipo annidato può accedere a tutti i membri accessibili al tipo contenitore.</span><span class="sxs-lookup"><span data-stu-id="d54c1-116">A nested type has access to all of the members that are accessible to its containing type.</span></span> <span data-ttu-id="d54c1-117">Può accedere a membri privati e protetti del tipo che li contengono, inclusi tutti i membri protetti ereditati.</span><span class="sxs-lookup"><span data-stu-id="d54c1-117">It can access private and protected members of the containing type, including any inherited protected members.</span></span>

<span data-ttu-id="d54c1-118">Nella dichiarazione precedente il nome completo della classe `Nested` è `Container.Nested`.</span><span class="sxs-lookup"><span data-stu-id="d54c1-118">In the previous declaration, the full name of class `Nested` is `Container.Nested`.</span></span> <span data-ttu-id="d54c1-119">Questo nome viene utilizzato per creare una nuova istanza della classe annidata, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="d54c1-119">This is the name used to create a new instance of the nested class, as follows:</span></span>

[!code-csharp[UseNestedInstance](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#UseNestedInstance)]

## <a name="see-also"></a><span data-ttu-id="d54c1-120">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="d54c1-120">See also</span></span>

- [<span data-ttu-id="d54c1-121">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="d54c1-121">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d54c1-122">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="d54c1-122">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="d54c1-123">Modificatori di accesso</span><span class="sxs-lookup"><span data-stu-id="d54c1-123">Access Modifiers</span></span>](./access-modifiers.md)
- [<span data-ttu-id="d54c1-124">Costruttori</span><span class="sxs-lookup"><span data-stu-id="d54c1-124">Constructors</span></span>](./constructors.md)
