---
title: Overridable
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
ms.openlocfilehash: dcbabde8464dd8a0ce5fad24d7d72b1e780270d3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392119"
---
# <a name="overridable-visual-basic"></a><span data-ttu-id="839b4-102">Overridable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="839b4-102">Overridable (Visual Basic)</span></span>
<span data-ttu-id="839b4-103">Specifica che una proprietà o una routine può essere sottoposta a override da una proprietà o una routine con nome identico in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="839b4-103">Specifies that a property or procedure can be overridden by an identically named property or procedure in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="839b4-104">Commenti</span><span class="sxs-lookup"><span data-stu-id="839b4-104">Remarks</span></span>  
 <span data-ttu-id="839b4-105">Il `Overridable` modificatore consente di eseguire l'override di una proprietà o di un metodo in una classe in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="839b4-105">The `Overridable` modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="839b4-106">Il modificatore [NotOverridable](notoverridable.md) impedisce l'override di una proprietà o di un metodo in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="839b4-106">The [NotOverridable](notoverridable.md) modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="839b4-107">Per altre informazioni, vedere [Nozioni fondamentali sull'ereditarietà](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span><span class="sxs-lookup"><span data-stu-id="839b4-107">For more information, see [Inheritance Basics](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="839b4-108">Se il `Overridable` `NotOverridable` modificatore o non è specificato, l'impostazione predefinita dipende dalla proprietà o dal metodo che esegue l'override di una proprietà o di un metodo della classe base.</span><span class="sxs-lookup"><span data-stu-id="839b4-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="839b4-109">Se la proprietà o il metodo esegue l'override di una proprietà o di un metodo della classe base, l'impostazione predefinita è `Overridable` ; in caso contrario, è `NotOverridable` .</span><span class="sxs-lookup"><span data-stu-id="839b4-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="839b4-110">È possibile eseguire l'ombreggiatura o l'override per ridefinire un elemento ereditato, ma esistono differenze significative tra i due approcci.</span><span class="sxs-lookup"><span data-stu-id="839b4-110">You can shadow or override to redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="839b4-111">Per ulteriori informazioni, vedere [shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="839b4-111">For more information, see [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
 <span data-ttu-id="839b4-112">Un elemento di cui è possibile eseguire l'override viene talvolta definito come elemento *virtuale* .</span><span class="sxs-lookup"><span data-stu-id="839b4-112">An element that can be overridden is sometimes referred to as a *virtual* element.</span></span> <span data-ttu-id="839b4-113">Se è possibile eseguirne l'override, ma non è necessario, viene talvolta chiamato anche elemento *concreto* .</span><span class="sxs-lookup"><span data-stu-id="839b4-113">If it can be overridden, but does not have to be, it is sometimes also called a *concrete* element.</span></span>  
  
 <span data-ttu-id="839b4-114">È possibile utilizzare `Overridable` solo in un'istruzione di dichiarazione di proprietà o di routine.</span><span class="sxs-lookup"><span data-stu-id="839b4-114">You can use `Overridable` only in a property or procedure declaration statement.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="839b4-115">Modificatori combinati</span><span class="sxs-lookup"><span data-stu-id="839b4-115">Combined Modifiers</span></span>  
 <span data-ttu-id="839b4-116">Non è possibile specificare `Overridable` o `NotOverridable` per un `Private` metodo.</span><span class="sxs-lookup"><span data-stu-id="839b4-116">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="839b4-117">Non è possibile specificare `Overridable` insieme a `MustOverride` , `NotOverridable` o `Shared` nella stessa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="839b4-117">You cannot specify `Overridable` together with `MustOverride`, `NotOverridable`, or `Shared` in the same declaration.</span></span>  
  
 <span data-ttu-id="839b4-118">Poiché un elemento che esegue l'override può essere implicitamente sottoposto a override, non è possibile combinare `Overridable` e `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="839b4-118">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="839b4-119">Uso</span><span class="sxs-lookup"><span data-stu-id="839b4-119">Usage</span></span>  
 <span data-ttu-id="839b4-120">Il modificatore `Overridable` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="839b4-120">The `Overridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="839b4-121">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="839b4-121">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="839b4-122">Property Statement</span><span class="sxs-lookup"><span data-stu-id="839b4-122">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="839b4-123">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="839b4-123">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="839b4-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="839b4-124">See also</span></span>

- [<span data-ttu-id="839b4-125">Modificatori</span><span class="sxs-lookup"><span data-stu-id="839b4-125">Modifiers</span></span>](index.md)
- [<span data-ttu-id="839b4-126">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="839b4-126">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="839b4-127">MustOverride</span><span class="sxs-lookup"><span data-stu-id="839b4-127">MustOverride</span></span>](mustoverride.md)
- [<span data-ttu-id="839b4-128">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="839b4-128">NotOverridable</span></span>](notoverridable.md)
- [<span data-ttu-id="839b4-129">Override</span><span class="sxs-lookup"><span data-stu-id="839b4-129">Overrides</span></span>](overrides.md)
- [<span data-ttu-id="839b4-130">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="839b4-130">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="839b4-131">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="839b4-131">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
