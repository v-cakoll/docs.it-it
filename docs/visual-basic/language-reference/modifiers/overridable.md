---
title: Overridable (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Overridable
- vb.Overridable
helpviewer_keywords:
- elements [Visual Basic], concrete
- properties [Visual Basic], redefining
- overriding, Overridable keyword
- elements [Visual Basic], virtual
- virtual [elements VB]
- procedures [Visual Basic], overriding
- concrete [elements VB]
- procedures [Visual Basic], redefining
- Overridable keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 612581e7-8a4c-4a5d-beff-3402fffa6f35
ms.openlocfilehash: 7002589b303c41b26b611588f339fa70dd19f959
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54537595"
---
# <a name="overridable-visual-basic"></a><span data-ttu-id="be0fc-102">Overridable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be0fc-102">Overridable (Visual Basic)</span></span>
<span data-ttu-id="be0fc-103">Specifica che una proprietà o routine può essere sostituita da una proprietà con nome identico o routine in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="be0fc-103">Specifies that a property or procedure can be overridden by an identically named property or procedure in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be0fc-104">Note</span><span class="sxs-lookup"><span data-stu-id="be0fc-104">Remarks</span></span>  
 <span data-ttu-id="be0fc-105">Il `Overridable` modificatore consente a una proprietà o metodo in una classe per eseguire l'override in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="be0fc-105">The `Overridable` modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="be0fc-106">Il [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) modificatore impedisce una proprietà o metodo da sottoporre a override in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="be0fc-106">The [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="be0fc-107">Per altre informazioni, vedere [Nozioni fondamentali sull'ereditarietà](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span><span class="sxs-lookup"><span data-stu-id="be0fc-107">For more information, see [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="be0fc-108">Se il `Overridable` o `NotOverridable` modificatore non è specificato, l'impostazione predefinita dipende dal fatto che la proprietà o il metodo esegue l'override di una proprietà della classe base o un metodo.</span><span class="sxs-lookup"><span data-stu-id="be0fc-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="be0fc-109">Se la proprietà o il metodo esegue l'override di una proprietà della classe base o un metodo, l'impostazione predefinita è `Overridable`; in caso contrario, è `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="be0fc-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="be0fc-110">È possibile nascondere o sottoporre a override per ridefinire un elemento ereditato, ma esistono differenze significative tra i due approcci.</span><span class="sxs-lookup"><span data-stu-id="be0fc-110">You can shadow or override to redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="be0fc-111">Per altre informazioni, vedere [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="be0fc-111">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
 <span data-ttu-id="be0fc-112">Un elemento che può essere sottoposto a override è talvolta detta un *virtuale* elemento.</span><span class="sxs-lookup"><span data-stu-id="be0fc-112">An element that can be overridden is sometimes referred to as a *virtual* element.</span></span> <span data-ttu-id="be0fc-113">Se è possibile eseguire l'override, ma non deve essere, detto a volte anche un *concreta* elemento.</span><span class="sxs-lookup"><span data-stu-id="be0fc-113">If it can be overridden, but does not have to be, it is sometimes also called a *concrete* element.</span></span>  
  
 <span data-ttu-id="be0fc-114">È possibile usare `Overridable` solo in un'istruzione per la dichiarazione di proprietà o routine.</span><span class="sxs-lookup"><span data-stu-id="be0fc-114">You can use `Overridable` only in a property or procedure declaration statement.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="be0fc-115">Modificatori combinati</span><span class="sxs-lookup"><span data-stu-id="be0fc-115">Combined Modifiers</span></span>  
 <span data-ttu-id="be0fc-116">Non è possibile specificare `Overridable` oppure `NotOverridable` per un `Private` (metodo).</span><span class="sxs-lookup"><span data-stu-id="be0fc-116">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="be0fc-117">Non è possibile specificare `Overridable` assieme `MustOverride`, `NotOverridable`, o `Shared` nella stessa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="be0fc-117">You cannot specify `Overridable` together with `MustOverride`, `NotOverridable`, or `Shared` in the same declaration.</span></span>  
  
 <span data-ttu-id="be0fc-118">Poiché un elemento che esegue l'override può essere implicitamente sottoposto a override, non è possibile combinare `Overridable` e `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="be0fc-118">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="be0fc-119">Utilizzo</span><span class="sxs-lookup"><span data-stu-id="be0fc-119">Usage</span></span>  
 <span data-ttu-id="be0fc-120">Il modificatore `Overridable` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="be0fc-120">The `Overridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="be0fc-121">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="be0fc-121">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="be0fc-122">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="be0fc-122">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="be0fc-123">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="be0fc-123">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="be0fc-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be0fc-124">See also</span></span>
- [<span data-ttu-id="be0fc-125">Modificatori</span><span class="sxs-lookup"><span data-stu-id="be0fc-125">Modifiers</span></span>](../../../visual-basic/language-reference/modifiers/index.md)
- [<span data-ttu-id="be0fc-126">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="be0fc-126">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="be0fc-127">MustOverride</span><span class="sxs-lookup"><span data-stu-id="be0fc-127">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="be0fc-128">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="be0fc-128">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="be0fc-129">Overrides</span><span class="sxs-lookup"><span data-stu-id="be0fc-129">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="be0fc-130">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="be0fc-130">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="be0fc-131">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="be0fc-131">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
