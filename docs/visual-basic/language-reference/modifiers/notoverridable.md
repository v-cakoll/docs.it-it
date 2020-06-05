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
ms.openlocfilehash: 463dd2454aafebf11554fb7bacdb73724c3130d8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392158"
---
# <a name="notoverridable-visual-basic"></a><span data-ttu-id="2be3b-102">NotOverridable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2be3b-102">NotOverridable (Visual Basic)</span></span>
<span data-ttu-id="2be3b-103">Specifica che una proprietà o una routine non può essere sottoposta a override in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="2be3b-103">Specifies that a property or procedure cannot be overridden in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2be3b-104">Commenti</span><span class="sxs-lookup"><span data-stu-id="2be3b-104">Remarks</span></span>  
 <span data-ttu-id="2be3b-105">Il `NotOverridable` modificatore impedisce che una proprietà o un metodo venga sottoposto a override in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="2be3b-105">The `NotOverridable` modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="2be3b-106">Il modificatore [Overridable](overridable.md) consente di eseguire l'override di una proprietà o di un metodo in una classe in una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="2be3b-106">The [Overridable](overridable.md) modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="2be3b-107">Per altre informazioni, vedere [Nozioni fondamentali sull'ereditarietà](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span><span class="sxs-lookup"><span data-stu-id="2be3b-107">For more information, see [Inheritance Basics](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="2be3b-108">Se il `Overridable` `NotOverridable` modificatore o non è specificato, l'impostazione predefinita dipende dalla proprietà o dal metodo che esegue l'override di una proprietà o di un metodo della classe base.</span><span class="sxs-lookup"><span data-stu-id="2be3b-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="2be3b-109">Se la proprietà o il metodo esegue l'override di una proprietà o di un metodo della classe base, l'impostazione predefinita è `Overridable` ; in caso contrario, è `NotOverridable` .</span><span class="sxs-lookup"><span data-stu-id="2be3b-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="2be3b-110">Un elemento che non può essere sottoposto a override è talvolta denominato elemento *sealed* .</span><span class="sxs-lookup"><span data-stu-id="2be3b-110">An element that cannot be overridden is sometimes called a *sealed* element.</span></span>  
  
 <span data-ttu-id="2be3b-111">È possibile utilizzare `NotOverridable` solo in un'istruzione di dichiarazione di proprietà o di routine.</span><span class="sxs-lookup"><span data-stu-id="2be3b-111">You can use `NotOverridable` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="2be3b-112">È possibile specificare `NotOverridable` solo su una proprietà o una routine che esegue l'override di un'altra proprietà o routine, ovvero solo in combinazione con `Overrides` .</span><span class="sxs-lookup"><span data-stu-id="2be3b-112">You can specify `NotOverridable` only on a property or procedure that overrides another property or procedure, that is, only in combination with `Overrides`.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="2be3b-113">Modificatori combinati</span><span class="sxs-lookup"><span data-stu-id="2be3b-113">Combined Modifiers</span></span>  
 <span data-ttu-id="2be3b-114">Non è possibile specificare `Overridable` o `NotOverridable` per un `Private` metodo.</span><span class="sxs-lookup"><span data-stu-id="2be3b-114">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="2be3b-115">Non è possibile specificare `NotOverridable` insieme a `MustOverride` , `Overridable` o `Shared` nella stessa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="2be3b-115">You cannot specify `NotOverridable` together with `MustOverride`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="2be3b-116">Uso</span><span class="sxs-lookup"><span data-stu-id="2be3b-116">Usage</span></span>  
 <span data-ttu-id="2be3b-117">Il modificatore `NotOverridable` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2be3b-117">The `NotOverridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="2be3b-118">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="2be3b-118">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="2be3b-119">Property Statement</span><span class="sxs-lookup"><span data-stu-id="2be3b-119">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="2be3b-120">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="2be3b-120">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="2be3b-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2be3b-121">See also</span></span>

- [<span data-ttu-id="2be3b-122">Modificatori</span><span class="sxs-lookup"><span data-stu-id="2be3b-122">Modifiers</span></span>](index.md)
- [<span data-ttu-id="2be3b-123">Nozioni fondamentali sull'ereditarietà</span><span class="sxs-lookup"><span data-stu-id="2be3b-123">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="2be3b-124">MustOverride</span><span class="sxs-lookup"><span data-stu-id="2be3b-124">MustOverride</span></span>](mustoverride.md)
- [<span data-ttu-id="2be3b-125">Overridable</span><span class="sxs-lookup"><span data-stu-id="2be3b-125">Overridable</span></span>](overridable.md)
- [<span data-ttu-id="2be3b-126">Override</span><span class="sxs-lookup"><span data-stu-id="2be3b-126">Overrides</span></span>](overrides.md)
- [<span data-ttu-id="2be3b-127">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2be3b-127">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="2be3b-128">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2be3b-128">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
