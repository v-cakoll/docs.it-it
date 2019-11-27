---
title: NotOverridable
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
ms.openlocfilehash: c55d57bb3008b2825fe5382844908ea32f0d500c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351454"
---
# <a name="notoverridable-visual-basic"></a><span data-ttu-id="bc677-102">NotOverridable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc677-102">NotOverridable (Visual Basic)</span></span>
<span data-ttu-id="bc677-103">Specifica che una proprietà o una routine non può essere sottoposta a override in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="bc677-103">Specifies that a property or procedure cannot be overridden in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc677-104">Note</span><span class="sxs-lookup"><span data-stu-id="bc677-104">Remarks</span></span>  
 <span data-ttu-id="bc677-105">Il modificatore `NotOverridable` impedisce l'override di una proprietà o di un metodo in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="bc677-105">The `NotOverridable` modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="bc677-106">Il modificatore [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) consente di eseguire l'override di una proprietà o di un metodo in una classe in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="bc677-106">The [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="bc677-107">Per altre informazioni, vedere [Nozioni fondamentali sull'ereditarietà](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span><span class="sxs-lookup"><span data-stu-id="bc677-107">For more information, see [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="bc677-108">Se il modificatore `Overridable` o `NotOverridable` non è specificato, l'impostazione predefinita dipende dalla proprietà o dal metodo che esegue l'override di una proprietà o di un metodo della classe base.</span><span class="sxs-lookup"><span data-stu-id="bc677-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="bc677-109">Se la proprietà o il metodo esegue l'override di una proprietà o di un metodo della classe base, l'impostazione predefinita è `Overridable`; in caso contrario, viene `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="bc677-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="bc677-110">Un elemento che non può essere sottoposto a override è talvolta denominato elemento *sealed* .</span><span class="sxs-lookup"><span data-stu-id="bc677-110">An element that cannot be overridden is sometimes called a *sealed* element.</span></span>  
  
 <span data-ttu-id="bc677-111">È possibile utilizzare `NotOverridable` solo in un'istruzione di dichiarazione di proprietà o di routine.</span><span class="sxs-lookup"><span data-stu-id="bc677-111">You can use `NotOverridable` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="bc677-112">È possibile specificare `NotOverridable` solo in una proprietà o una routine che esegue l'override di un'altra proprietà o routine, ovvero solo in combinazione con `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="bc677-112">You can specify `NotOverridable` only on a property or procedure that overrides another property or procedure, that is, only in combination with `Overrides`.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="bc677-113">Modificatori combinati</span><span class="sxs-lookup"><span data-stu-id="bc677-113">Combined Modifiers</span></span>  
 <span data-ttu-id="bc677-114">Non è possibile specificare `Overridable` o `NotOverridable` per un metodo di `Private`.</span><span class="sxs-lookup"><span data-stu-id="bc677-114">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="bc677-115">Non è possibile specificare `NotOverridable` insieme `MustOverride`, `Overridable`o `Shared` nella stessa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="bc677-115">You cannot specify `NotOverridable` together with `MustOverride`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="bc677-116">Utilizzo</span><span class="sxs-lookup"><span data-stu-id="bc677-116">Usage</span></span>  
 <span data-ttu-id="bc677-117">Il modificatore `NotOverridable` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="bc677-117">The `NotOverridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="bc677-118">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="bc677-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="bc677-119">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="bc677-119">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="bc677-120">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="bc677-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="bc677-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc677-121">See also</span></span>

- [<span data-ttu-id="bc677-122">Modificatori</span><span class="sxs-lookup"><span data-stu-id="bc677-122">Modifiers</span></span>](../../../visual-basic/language-reference/modifiers/index.md)
- [<span data-ttu-id="bc677-123">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="bc677-123">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="bc677-124">MustOverride</span><span class="sxs-lookup"><span data-stu-id="bc677-124">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="bc677-125">Overridable</span><span class="sxs-lookup"><span data-stu-id="bc677-125">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="bc677-126">Overrides</span><span class="sxs-lookup"><span data-stu-id="bc677-126">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="bc677-127">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="bc677-127">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="bc677-128">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bc677-128">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
