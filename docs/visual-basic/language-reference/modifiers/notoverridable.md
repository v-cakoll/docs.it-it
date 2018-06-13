---
title: NotOverridable (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.NotOverridable
- NotOverridable
helpviewer_keywords:
- sealed methods [Visual Basic]
- NotOverridable keyword [Visual Basic]
- properties [Visual Basic], redefining
- elements [Visual Basic], sealed
- sealed [elements VB]
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- methods [Visual Basic], sealed
- properties [Visual Basic], overriding
ms.assetid: 66ec6984-f5f5-4857-b362-6a3907aaf9e0
ms.openlocfilehash: 3fae1a4b587c379dbc459cbc973982851e713785
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33600753"
---
# <a name="notoverridable-visual-basic"></a><span data-ttu-id="f844a-102">NotOverridable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f844a-102">NotOverridable (Visual Basic)</span></span>
<span data-ttu-id="f844a-103">Specifica che una proprietà o routine non può essere sottoposto a override in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="f844a-103">Specifies that a property or procedure cannot be overridden in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f844a-104">Note</span><span class="sxs-lookup"><span data-stu-id="f844a-104">Remarks</span></span>  
 <span data-ttu-id="f844a-105">Il `NotOverridable` modificatore impedisce una proprietà o metodo di override in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="f844a-105">The `NotOverridable` modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="f844a-106">Il [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) modificatore consente a una proprietà o metodo in una classe per eseguire l'override in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="f844a-106">The [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="f844a-107">Per altre informazioni, vedere [Nozioni fondamentali sull'ereditarietà](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span><span class="sxs-lookup"><span data-stu-id="f844a-107">For more information, see [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="f844a-108">Se il `Overridable` o `NotOverridable` modificatore non è specificato, l'impostazione predefinita varia a seconda se la proprietà o il metodo esegue l'override di metodo o una proprietà di classe di base.</span><span class="sxs-lookup"><span data-stu-id="f844a-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="f844a-109">Se la proprietà o il metodo esegue l'override di una proprietà della classe base o un metodo, l'impostazione predefinita è `Overridable`; in caso contrario, è `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="f844a-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="f844a-110">Un elemento che non può essere sottoposto a override viene talvolta definito un *sealed* elemento.</span><span class="sxs-lookup"><span data-stu-id="f844a-110">An element that cannot be overridden is sometimes called a *sealed* element.</span></span>  
  
 <span data-ttu-id="f844a-111">È possibile usare `NotOverridable` solo in un'istruzione per la dichiarazione di proprietà o routine.</span><span class="sxs-lookup"><span data-stu-id="f844a-111">You can use `NotOverridable` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="f844a-112">È possibile specificare `NotOverridable` solo su una proprietà o routine che esegue l'override di un'altra proprietà o routine, ovvero solo in combinazione con `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="f844a-112">You can specify `NotOverridable` only on a property or procedure that overrides another property or procedure, that is, only in combination with `Overrides`.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="f844a-113">Modificatori combinati</span><span class="sxs-lookup"><span data-stu-id="f844a-113">Combined Modifiers</span></span>  
 <span data-ttu-id="f844a-114">Non è possibile specificare `Overridable` o `NotOverridable` per un `Private` metodo.</span><span class="sxs-lookup"><span data-stu-id="f844a-114">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="f844a-115">Non è possibile specificare `NotOverridable` con `MustOverride`, `Overridable`, o `Shared` nella stessa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="f844a-115">You cannot specify `NotOverridable` together with `MustOverride`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="f844a-116">Utilizzo</span><span class="sxs-lookup"><span data-stu-id="f844a-116">Usage</span></span>  
 <span data-ttu-id="f844a-117">Il modificatore `NotOverridable` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f844a-117">The `NotOverridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="f844a-118">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="f844a-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="f844a-119">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="f844a-119">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="f844a-120">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="f844a-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="f844a-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f844a-121">See Also</span></span>  
 [<span data-ttu-id="f844a-122">Modificatori</span><span class="sxs-lookup"><span data-stu-id="f844a-122">Modifiers</span></span>](../../../visual-basic/language-reference/modifiers/index.md)  
 [<span data-ttu-id="f844a-123">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="f844a-123">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [<span data-ttu-id="f844a-124">MustOverride</span><span class="sxs-lookup"><span data-stu-id="f844a-124">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
 [<span data-ttu-id="f844a-125">Overridable</span><span class="sxs-lookup"><span data-stu-id="f844a-125">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
 [<span data-ttu-id="f844a-126">Overrides</span><span class="sxs-lookup"><span data-stu-id="f844a-126">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
 [<span data-ttu-id="f844a-127">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f844a-127">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="f844a-128">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f844a-128">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
