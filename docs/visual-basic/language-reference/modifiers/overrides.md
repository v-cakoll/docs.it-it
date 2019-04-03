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
ms.openlocfilehash: 9eb19bf5e89b12a32cae28b2c087570acc10f3ad
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826587"
---
# <a name="overrides-visual-basic"></a><span data-ttu-id="3c4d3-102">Overrides (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c4d3-102">Overrides (Visual Basic)</span></span>
<span data-ttu-id="3c4d3-103">Specifica che una proprietà o una routine esegue l'override di una proprietà o una routine con nome identico ereditata da una classe base.</span><span class="sxs-lookup"><span data-stu-id="3c4d3-103">Specifies that a property or procedure overrides an identically named property or procedure inherited from a base class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c4d3-104">Note</span><span class="sxs-lookup"><span data-stu-id="3c4d3-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="3c4d3-105">Regole</span><span class="sxs-lookup"><span data-stu-id="3c4d3-105">Rules</span></span>  
  
-   <span data-ttu-id="3c4d3-106">**Contesto della dichiarazione.**</span><span class="sxs-lookup"><span data-stu-id="3c4d3-106">**Declaration Context.**</span></span> <span data-ttu-id="3c4d3-107">È possibile usare `Overrides` solo in un'istruzione per la dichiarazione di proprietà o routine.</span><span class="sxs-lookup"><span data-stu-id="3c4d3-107">You can use `Overrides` only in a property or procedure declaration statement.</span></span>  
  
-   <span data-ttu-id="3c4d3-108">**Modificatori combinati.**</span><span class="sxs-lookup"><span data-stu-id="3c4d3-108">**Combined Modifiers.**</span></span> <span data-ttu-id="3c4d3-109">Non è possibile specificare `Overrides` insieme a `Shadows` o `Shared` nella stessa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="3c4d3-109">You cannot specify `Overrides` together with `Shadows` or `Shared` in the same declaration.</span></span> <span data-ttu-id="3c4d3-110">Poiché un elemento che esegue l'override può essere implicitamente sottoposto a override, non è possibile combinare `Overridable` e `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="3c4d3-110">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>  
  
-   <span data-ttu-id="3c4d3-111">**Corrispondenza delle firme.**</span><span class="sxs-lookup"><span data-stu-id="3c4d3-111">**Matching Signatures.**</span></span> <span data-ttu-id="3c4d3-112">La firma di questa dichiarazione deve corrispondere esattamente il *firma* della proprietà o routine sottoposta a override.</span><span class="sxs-lookup"><span data-stu-id="3c4d3-112">The signature of this declaration must exactly match the *signature* of the property or procedure that it overrides.</span></span> <span data-ttu-id="3c4d3-113">In altre parole, gli elenchi di parametri devono presentare lo stesso numero di parametri, nel medesimo ordine, e contenere gli stessi tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="3c4d3-113">This means the parameter lists must have the same number of parameters, in the same order, with the same data types.</span></span>  
  
     <span data-ttu-id="3c4d3-114">Oltre alla firma, la dichiarazione che esegue l'override deve anche corrispondere esattamente a quanto segue.</span><span class="sxs-lookup"><span data-stu-id="3c4d3-114">In addition to the signature, the overriding declaration must also exactly match the following:</span></span>  
  
    -   <span data-ttu-id="3c4d3-115">Livello di accesso</span><span class="sxs-lookup"><span data-stu-id="3c4d3-115">The access level</span></span>  
  
    -   <span data-ttu-id="3c4d3-116">Tipo restituito, se disponibile</span><span class="sxs-lookup"><span data-stu-id="3c4d3-116">The return type, if any</span></span>  
  
-   <span data-ttu-id="3c4d3-117">**Firme generiche.**</span><span class="sxs-lookup"><span data-stu-id="3c4d3-117">**Generic Signatures.**</span></span> <span data-ttu-id="3c4d3-118">Nel caso di una routine generica la firma include il numero di parametri del tipo.</span><span class="sxs-lookup"><span data-stu-id="3c4d3-118">For a generic procedure, the signature includes the number of type parameters.</span></span> <span data-ttu-id="3c4d3-119">La dichiarazione che esegue l'override, quindi, deve corrispondere alla versione della classe base anche in relazione a tali caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="3c4d3-119">Therefore, the overriding declaration must match the base class version in that respect as well.</span></span>  
  
-   <span data-ttu-id="3c4d3-120">**Corrispondenze aggiuntive.**</span><span class="sxs-lookup"><span data-stu-id="3c4d3-120">**Additional Matching.**</span></span> <span data-ttu-id="3c4d3-121">Oltre a corrispondere alla firma della versione della classe base, la dichiarazione deve presentare anche le corrispondenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="3c4d3-121">In addition to matching the signature of the base class version, this declaration must also match it in the following respects:</span></span>  
  
    -   <span data-ttu-id="3c4d3-122">Modificatore a livello di accesso (ad esempio [pubblica](../../../visual-basic/language-reference/modifiers/public.md))</span><span class="sxs-lookup"><span data-stu-id="3c4d3-122">Access-level modifier (such as [Public](../../../visual-basic/language-reference/modifiers/public.md))</span></span>  
  
    -   <span data-ttu-id="3c4d3-123">Meccanismo di passaggio di ogni parametro ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) oppure [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span><span class="sxs-lookup"><span data-stu-id="3c4d3-123">Passing mechanism of each parameter ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span></span>  
  
    -   <span data-ttu-id="3c4d3-124">Elenchi di vincoli su ogni parametro di tipo di una routine generica</span><span class="sxs-lookup"><span data-stu-id="3c4d3-124">Constraint lists on each type parameter of a generic procedure</span></span>  
  
-   <span data-ttu-id="3c4d3-125">**Shadowing e override.**</span><span class="sxs-lookup"><span data-stu-id="3c4d3-125">**Shadowing and Overriding.**</span></span> <span data-ttu-id="3c4d3-126">Sebbene lo shadowing e l'override ridefiniscano entrambi un elemento ereditato, tra i due metodi esistono differenze sostanziali.</span><span class="sxs-lookup"><span data-stu-id="3c4d3-126">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="3c4d3-127">Per altre informazioni, vedere [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="3c4d3-127">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
 <span data-ttu-id="3c4d3-128">Se si usa `Overrides`, il compilatore aggiunge implicitamente `Overloads` in modo che le API della libreria funzionino più facilmente con C#.</span><span class="sxs-lookup"><span data-stu-id="3c4d3-128">If you use `Overrides`, the compiler implicitly adds `Overloads` so that your library APIs work with C# more easily.</span></span>  
  
 <span data-ttu-id="3c4d3-129">Il modificatore `Overrides` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="3c4d3-129">The `Overrides` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="3c4d3-130">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="3c4d3-130">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="3c4d3-131">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="3c4d3-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="3c4d3-132">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="3c4d3-132">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="3c4d3-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c4d3-133">See also</span></span>

- [<span data-ttu-id="3c4d3-134">MustOverride</span><span class="sxs-lookup"><span data-stu-id="3c4d3-134">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="3c4d3-135">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="3c4d3-135">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="3c4d3-136">Overridable</span><span class="sxs-lookup"><span data-stu-id="3c4d3-136">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="3c4d3-137">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="3c4d3-137">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="3c4d3-138">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3c4d3-138">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="3c4d3-139">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3c4d3-139">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="3c4d3-140">Elenco dei tipi</span><span class="sxs-lookup"><span data-stu-id="3c4d3-140">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
