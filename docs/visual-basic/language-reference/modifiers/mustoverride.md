---
title: MustOverride (Visual Basic)
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
ms.openlocfilehash: f5932b28c4664dd59dad829228f2186e78108af5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64661248"
---
# <a name="mustoverride-visual-basic"></a><span data-ttu-id="e57da-102">MustOverride (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e57da-102">MustOverride (Visual Basic)</span></span>
<span data-ttu-id="e57da-103">Specifica che una proprietà o routine non è implementato in questa classe e deve essere sottoposto a override in una classe derivata prima che possa essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="e57da-103">Specifies that a property or procedure is not implemented in this class and must be overridden in a derived class before it can be used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e57da-104">Note</span><span class="sxs-lookup"><span data-stu-id="e57da-104">Remarks</span></span>  
 <span data-ttu-id="e57da-105">È possibile usare `MustOverride` solo in un'istruzione per la dichiarazione di proprietà o routine.</span><span class="sxs-lookup"><span data-stu-id="e57da-105">You can use `MustOverride` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="e57da-106">La proprietà o una routine che specifica `MustOverride` deve essere un membro di una classe, mentre la classe deve essere contrassegnata [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span><span class="sxs-lookup"><span data-stu-id="e57da-106">The property or procedure that specifies `MustOverride` must be a member of a class, and the class must be marked [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="e57da-107">Regole</span><span class="sxs-lookup"><span data-stu-id="e57da-107">Rules</span></span>  
  
- <span data-ttu-id="e57da-108">**Dichiarazione di non completata.**</span><span class="sxs-lookup"><span data-stu-id="e57da-108">**Incomplete Declaration.**</span></span> <span data-ttu-id="e57da-109">Quando si specifica `MustOverride`, non si specifica una riga di codice per la proprietà o routine, non ancora il `End Function`, `End Property`, o `End Sub` istruzione.</span><span class="sxs-lookup"><span data-stu-id="e57da-109">When you specify `MustOverride`, you do not supply any additional lines of code for the property or procedure, not even the `End Function`, `End Property`, or `End Sub` statement.</span></span>  
  
- <span data-ttu-id="e57da-110">**Modificatori combinati.**</span><span class="sxs-lookup"><span data-stu-id="e57da-110">**Combined Modifiers.**</span></span> <span data-ttu-id="e57da-111">Non è possibile specificare `MustOverride` assieme `NotOverridable`, `Overridable`, o `Shared` nella stessa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="e57da-111">You cannot specify `MustOverride` together with `NotOverridable`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
- <span data-ttu-id="e57da-112">**Shadowing e override.**</span><span class="sxs-lookup"><span data-stu-id="e57da-112">**Shadowing and Overriding.**</span></span> <span data-ttu-id="e57da-113">Sebbene lo shadowing e l'override ridefiniscano entrambi un elemento ereditato, tra i due metodi esistono differenze sostanziali.</span><span class="sxs-lookup"><span data-stu-id="e57da-113">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="e57da-114">Per altre informazioni, vedere [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="e57da-114">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
- <span data-ttu-id="e57da-115">**Condizioni di alternative.**</span><span class="sxs-lookup"><span data-stu-id="e57da-115">**Alternate Terms.**</span></span> <span data-ttu-id="e57da-116">Un elemento che può essere utilizzato solo in un override viene chiamato talvolta un *pure virtuale* elemento.</span><span class="sxs-lookup"><span data-stu-id="e57da-116">An element that cannot be used except in an override is sometimes called a *pure virtual* element.</span></span>  
  
 <span data-ttu-id="e57da-117">Il modificatore `MustOverride` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e57da-117">The `MustOverride` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="e57da-118">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="e57da-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="e57da-119">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="e57da-119">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="e57da-120">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="e57da-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="e57da-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e57da-121">See also</span></span>

- [<span data-ttu-id="e57da-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="e57da-122">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="e57da-123">Overridable</span><span class="sxs-lookup"><span data-stu-id="e57da-123">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="e57da-124">Overrides</span><span class="sxs-lookup"><span data-stu-id="e57da-124">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="e57da-125">MustInherit</span><span class="sxs-lookup"><span data-stu-id="e57da-125">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [<span data-ttu-id="e57da-126">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="e57da-126">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="e57da-127">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e57da-127">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
