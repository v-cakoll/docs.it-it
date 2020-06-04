---
title: MustOverride
ms.date: 07/20/2015
f1_keywords:
- vb.MustOverride
- MustOverride
helpviewer_keywords:
- virtual elements [Visual Basic], pure
- elements [Visual Basic], pure virtual
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- overriding, MustOverride keyword
- procedures [Visual Basic], redefining
- pure virtual elements [Visual Basic]
- MustOverride keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 6e9d9ad6-bb64-433f-b32b-3ef84293bf96
ms.openlocfilehash: 1b20108a2d42e82c0af7598fde8d60a08fea28ec
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396194"
---
# <a name="mustoverride-visual-basic"></a><span data-ttu-id="84eb3-102">MustOverride (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="84eb3-102">MustOverride (Visual Basic)</span></span>
<span data-ttu-id="84eb3-103">Specifica che una proprietà o una routine non è implementata in questa classe e deve essere sottoposta a override in una classe derivata prima di poter essere utilizzata.</span><span class="sxs-lookup"><span data-stu-id="84eb3-103">Specifies that a property or procedure is not implemented in this class and must be overridden in a derived class before it can be used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84eb3-104">Commenti</span><span class="sxs-lookup"><span data-stu-id="84eb3-104">Remarks</span></span>  
 <span data-ttu-id="84eb3-105">È possibile utilizzare `MustOverride` solo in un'istruzione di dichiarazione di proprietà o di routine.</span><span class="sxs-lookup"><span data-stu-id="84eb3-105">You can use `MustOverride` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="84eb3-106">La proprietà o la routine che specifica `MustOverride` deve essere un membro di una classe e la classe deve essere contrassegnata come [MustInherit](mustinherit.md).</span><span class="sxs-lookup"><span data-stu-id="84eb3-106">The property or procedure that specifies `MustOverride` must be a member of a class, and the class must be marked [MustInherit](mustinherit.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="84eb3-107">Regole</span><span class="sxs-lookup"><span data-stu-id="84eb3-107">Rules</span></span>  
  
- <span data-ttu-id="84eb3-108">**Dichiarazione incompleta.**</span><span class="sxs-lookup"><span data-stu-id="84eb3-108">**Incomplete Declaration.**</span></span> <span data-ttu-id="84eb3-109">Quando si specifica `MustOverride` , non vengono fornite righe di codice aggiuntive per la proprietà o la routine, non anche per l' `End Function` `End Property` istruzione, o `End Sub` .</span><span class="sxs-lookup"><span data-stu-id="84eb3-109">When you specify `MustOverride`, you do not supply any additional lines of code for the property or procedure, not even the `End Function`, `End Property`, or `End Sub` statement.</span></span>  
  
- <span data-ttu-id="84eb3-110">**Modificatori combinati.**</span><span class="sxs-lookup"><span data-stu-id="84eb3-110">**Combined Modifiers.**</span></span> <span data-ttu-id="84eb3-111">Non è possibile specificare `MustOverride` insieme a `NotOverridable` , `Overridable` o `Shared` nella stessa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="84eb3-111">You cannot specify `MustOverride` together with `NotOverridable`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
- <span data-ttu-id="84eb3-112">**Shadowing e override.**</span><span class="sxs-lookup"><span data-stu-id="84eb3-112">**Shadowing and Overriding.**</span></span> <span data-ttu-id="84eb3-113">Sebbene lo shadowing e l'override ridefiniscano entrambi un elemento ereditato, tra i due metodi esistono differenze sostanziali.</span><span class="sxs-lookup"><span data-stu-id="84eb3-113">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="84eb3-114">Per ulteriori informazioni, vedere [shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="84eb3-114">For more information, see [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
- <span data-ttu-id="84eb3-115">**Termini alternativi.**</span><span class="sxs-lookup"><span data-stu-id="84eb3-115">**Alternate Terms.**</span></span> <span data-ttu-id="84eb3-116">Un elemento che non può essere utilizzato ad eccezione di un override viene talvolta denominato elemento *virtuale puro* .</span><span class="sxs-lookup"><span data-stu-id="84eb3-116">An element that cannot be used except in an override is sometimes called a *pure virtual* element.</span></span>  
  
 <span data-ttu-id="84eb3-117">Il modificatore `MustOverride` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="84eb3-117">The `MustOverride` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="84eb3-118">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="84eb3-118">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="84eb3-119">Property Statement</span><span class="sxs-lookup"><span data-stu-id="84eb3-119">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="84eb3-120">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="84eb3-120">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="84eb3-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84eb3-121">See also</span></span>

- [<span data-ttu-id="84eb3-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="84eb3-122">NotOverridable</span></span>](notoverridable.md)
- [<span data-ttu-id="84eb3-123">Overridable</span><span class="sxs-lookup"><span data-stu-id="84eb3-123">Overridable</span></span>](overridable.md)
- [<span data-ttu-id="84eb3-124">Override</span><span class="sxs-lookup"><span data-stu-id="84eb3-124">Overrides</span></span>](overrides.md)
- [<span data-ttu-id="84eb3-125">MustInherit</span><span class="sxs-lookup"><span data-stu-id="84eb3-125">MustInherit</span></span>](mustinherit.md)
- [<span data-ttu-id="84eb3-126">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="84eb3-126">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="84eb3-127">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="84eb3-127">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
