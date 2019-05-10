---
title: Overrides (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Overrides
- vb.Overrides
helpviewer_keywords:
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- Overrides keyword [Visual Basic]
- overriding, Overrides keyword
- properties [Visual Basic], overriding
ms.assetid: 9f5e6144-ce10-465e-842b-1a8f8760af90
ms.openlocfilehash: 7fff91d993743574d13030aa3d5cc1e462e76838
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64751034"
---
# <a name="overrides-visual-basic"></a><span data-ttu-id="31895-102">Overrides (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31895-102">Overrides (Visual Basic)</span></span>

<span data-ttu-id="31895-103">Specifica che una proprietà o una routine esegue l'override di una proprietà o una routine con nome identico ereditata da una classe base.</span><span class="sxs-lookup"><span data-stu-id="31895-103">Specifies that a property or procedure overrides an identically named property or procedure inherited from a base class.</span></span>

## <a name="rules"></a><span data-ttu-id="31895-104">Regole</span><span class="sxs-lookup"><span data-stu-id="31895-104">Rules</span></span>

- <span data-ttu-id="31895-105">**Contesto della dichiarazione.**</span><span class="sxs-lookup"><span data-stu-id="31895-105">**Declaration Context.**</span></span> <span data-ttu-id="31895-106">È possibile usare `Overrides` solo in un'istruzione per la dichiarazione di proprietà o routine.</span><span class="sxs-lookup"><span data-stu-id="31895-106">You can use `Overrides` only in a property or procedure declaration statement.</span></span>

- <span data-ttu-id="31895-107">**Modificatori combinati.**</span><span class="sxs-lookup"><span data-stu-id="31895-107">**Combined Modifiers.**</span></span> <span data-ttu-id="31895-108">Non è possibile specificare `Overrides` insieme a `Shadows` o `Shared` nella stessa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="31895-108">You cannot specify `Overrides` together with `Shadows` or `Shared` in the same declaration.</span></span> <span data-ttu-id="31895-109">Poiché un elemento che esegue l'override può essere implicitamente sottoposto a override, non è possibile combinare `Overridable` e `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="31895-109">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>

- <span data-ttu-id="31895-110">**Corrispondenza delle firme.**</span><span class="sxs-lookup"><span data-stu-id="31895-110">**Matching Signatures.**</span></span> <span data-ttu-id="31895-111">La firma di questa dichiarazione deve corrispondere esattamente il *firma* della proprietà o routine sottoposta a override.</span><span class="sxs-lookup"><span data-stu-id="31895-111">The signature of this declaration must exactly match the *signature* of the property or procedure that it overrides.</span></span> <span data-ttu-id="31895-112">In altre parole, gli elenchi di parametri devono presentare lo stesso numero di parametri, nel medesimo ordine, e contenere gli stessi tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="31895-112">This means the parameter lists must have the same number of parameters, in the same order, with the same data types.</span></span>

  <span data-ttu-id="31895-113">Oltre alla firma, la dichiarazione che esegue l'override deve anche corrispondere esattamente a quanto segue.</span><span class="sxs-lookup"><span data-stu-id="31895-113">In addition to the signature, the overriding declaration must also exactly match the following:</span></span>

  - <span data-ttu-id="31895-114">Livello di accesso</span><span class="sxs-lookup"><span data-stu-id="31895-114">The access level</span></span>

  - <span data-ttu-id="31895-115">Tipo restituito, se disponibile</span><span class="sxs-lookup"><span data-stu-id="31895-115">The return type, if any</span></span>

- <span data-ttu-id="31895-116">**Firme generiche.**</span><span class="sxs-lookup"><span data-stu-id="31895-116">**Generic Signatures.**</span></span> <span data-ttu-id="31895-117">Nel caso di una routine generica la firma include il numero di parametri del tipo.</span><span class="sxs-lookup"><span data-stu-id="31895-117">For a generic procedure, the signature includes the number of type parameters.</span></span> <span data-ttu-id="31895-118">La dichiarazione che esegue l'override, quindi, deve corrispondere alla versione della classe base anche in relazione a tali caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="31895-118">Therefore, the overriding declaration must match the base class version in that respect as well.</span></span>

- <span data-ttu-id="31895-119">**Corrispondenze aggiuntive.**</span><span class="sxs-lookup"><span data-stu-id="31895-119">**Additional Matching.**</span></span> <span data-ttu-id="31895-120">Oltre a corrispondere alla firma della versione della classe base, la dichiarazione deve presentare anche le corrispondenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="31895-120">In addition to matching the signature of the base class version, this declaration must also match it in the following respects:</span></span>

  - <span data-ttu-id="31895-121">Modificatore a livello di accesso (ad esempio [pubblica](../../../visual-basic/language-reference/modifiers/public.md))</span><span class="sxs-lookup"><span data-stu-id="31895-121">Access-level modifier (such as [Public](../../../visual-basic/language-reference/modifiers/public.md))</span></span>

  - <span data-ttu-id="31895-122">Meccanismo di passaggio di ogni parametro ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) oppure [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span><span class="sxs-lookup"><span data-stu-id="31895-122">Passing mechanism of each parameter ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span></span>

  - <span data-ttu-id="31895-123">Elenchi di vincoli su ogni parametro di tipo di una routine generica</span><span class="sxs-lookup"><span data-stu-id="31895-123">Constraint lists on each type parameter of a generic procedure</span></span>

- <span data-ttu-id="31895-124">**Shadowing e override.**</span><span class="sxs-lookup"><span data-stu-id="31895-124">**Shadowing and Overriding.**</span></span> <span data-ttu-id="31895-125">Sebbene lo shadowing e l'override ridefiniscano entrambi un elemento ereditato, tra i due metodi esistono differenze sostanziali.</span><span class="sxs-lookup"><span data-stu-id="31895-125">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="31895-126">Per altre informazioni, vedere [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="31895-126">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>

<span data-ttu-id="31895-127">Se si usa `Overrides`, il compilatore aggiunge implicitamente `Overloads` in modo che le API della libreria funzionino più facilmente con C#.</span><span class="sxs-lookup"><span data-stu-id="31895-127">If you use `Overrides`, the compiler implicitly adds `Overloads` so that your library APIs work with C# more easily.</span></span>

<span data-ttu-id="31895-128">Il modificatore `Overrides` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="31895-128">The `Overrides` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="31895-129">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="31895-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- [<span data-ttu-id="31895-130">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="31895-130">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- [<span data-ttu-id="31895-131">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="31895-131">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="31895-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31895-132">See also</span></span>

- [<span data-ttu-id="31895-133">MustOverride</span><span class="sxs-lookup"><span data-stu-id="31895-133">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="31895-134">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="31895-134">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="31895-135">Overridable</span><span class="sxs-lookup"><span data-stu-id="31895-135">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="31895-136">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="31895-136">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="31895-137">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="31895-137">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="31895-138">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="31895-138">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="31895-139">Elenco dei tipi</span><span class="sxs-lookup"><span data-stu-id="31895-139">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
