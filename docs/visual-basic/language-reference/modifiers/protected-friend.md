---
title: Protected Friend (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: b72cbee0394043620e792d1c014bfe55121e175e
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2018
ms.locfileid: "34306542"
---
# <a name="protected-friend-visual-basic"></a><span data-ttu-id="12b7d-102">Protected Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="12b7d-102">Protected Friend (Visual Basic)</span></span>

<span data-ttu-id="12b7d-103">La combinazione delle parole chiave `Protected Friend` è un modificatore di accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="12b7d-103">The `Protected Friend` keyword combination is a member access modifier.</span></span> <span data-ttu-id="12b7d-104">Entrambi conferisce [Friend](friend.md) l'accesso e [Protected](protected.md) l'accesso per gli elementi dichiarati, in modo che siano accessibili da qualsiasi punto nello stesso assembly, dalla rispettiva classe e dalle classi derivate.</span><span class="sxs-lookup"><span data-stu-id="12b7d-104">It confers both [Friend](friend.md) access and [Protected](protected.md) access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="12b7d-105">È possibile specificare `Protected Friend` solo in membri di classi; non è possibile applicare `Protected Friend` ai membri di una struttura perché le strutture non possono essere ereditate.</span><span class="sxs-lookup"><span data-stu-id="12b7d-105">You can specify `Protected Friend` only on members of classes; you cannot apply `Protected Friend` to members of a structure because structures cannot be inherited.</span></span>

> [!NOTE]
> <span data-ttu-id="12b7d-106">In Visual Studio, selezionare la Guida F1 nei `protected friend` viene fornita la Guida per uno [protetti](protected.md) o [friend](friend.md).</span><span class="sxs-lookup"><span data-stu-id="12b7d-106">In Visual Studio, selecting F1 help on `protected friend` provides help for either [protected](protected.md) or [friend](friend.md).</span></span> <span data-ttu-id="12b7d-107">L'IDE sceglie il token singolo sotto il cursore anziché la parola composta.</span><span class="sxs-lookup"><span data-stu-id="12b7d-107">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="12b7d-108">Regole</span><span class="sxs-lookup"><span data-stu-id="12b7d-108">Rules</span></span>

- <span data-ttu-id="12b7d-109">**Contesto della dichiarazione.**</span><span class="sxs-lookup"><span data-stu-id="12b7d-109">**Declaration Context.**</span></span> <span data-ttu-id="12b7d-110">È possibile utilizzare `Protected Friend` solo a livello di classe.</span><span class="sxs-lookup"><span data-stu-id="12b7d-110">You can use `Protected Friend` only at the class level.</span></span> <span data-ttu-id="12b7d-111">Ciò significa che il contesto della dichiarazione per un `Protected` elemento deve essere una classe e non può essere un file di origine, lo spazio dei nomi, interfaccia, modulo, struttura o stored procedure.</span><span class="sxs-lookup"><span data-stu-id="12b7d-111">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span> 


## <a name="see-also"></a><span data-ttu-id="12b7d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12b7d-112">See Also</span></span>

[<span data-ttu-id="12b7d-113">Public</span><span class="sxs-lookup"><span data-stu-id="12b7d-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
[<span data-ttu-id="12b7d-114">Protected</span><span class="sxs-lookup"><span data-stu-id="12b7d-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
<span data-ttu-id="12b7d-115">[Friend](friend.md) </span><span class="sxs-lookup"><span data-stu-id="12b7d-115">[Friend](friend.md) </span></span>  
[<span data-ttu-id="12b7d-116">Private</span><span class="sxs-lookup"><span data-stu-id="12b7d-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
<span data-ttu-id="12b7d-117">[Protetto privato](./private-protected.md) </span><span class="sxs-lookup"><span data-stu-id="12b7d-117">[Private Protected](./private-protected.md) </span></span>  
[<span data-ttu-id="12b7d-118">Livelli di accesso in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="12b7d-118">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
[<span data-ttu-id="12b7d-119">Routine</span><span class="sxs-lookup"><span data-stu-id="12b7d-119">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
[<span data-ttu-id="12b7d-120">Strutture</span><span class="sxs-lookup"><span data-stu-id="12b7d-120">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
[<span data-ttu-id="12b7d-121">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="12b7d-121">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
