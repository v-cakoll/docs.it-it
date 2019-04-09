---
title: Protected Friend (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: 331c63dc290d4096e8158f265ee869b47743a273
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59151775"
---
# <a name="protected-friend-visual-basic"></a><span data-ttu-id="92a07-102">Protected Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="92a07-102">Protected Friend (Visual Basic)</span></span>

<span data-ttu-id="92a07-103">La combinazione delle parole chiave `Protected Friend` è un modificatore di accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="92a07-103">The `Protected Friend` keyword combination is a member access modifier.</span></span> <span data-ttu-id="92a07-104">Entrambi conferisce [Friend](friend.md) l'accesso e [Protected](protected.md) accesso per gli elementi dichiarati, in modo che siano accessibili da qualsiasi punto nello stesso assembly, dalla propria classe e dalle classi derivate.</span><span class="sxs-lookup"><span data-stu-id="92a07-104">It confers both [Friend](friend.md) access and [Protected](protected.md) access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="92a07-105">È possibile specificare `Protected Friend` solo in membri di classi; non è possibile applicare `Protected Friend` ai membri di una struttura perché le strutture non possono essere ereditate.</span><span class="sxs-lookup"><span data-stu-id="92a07-105">You can specify `Protected Friend` only on members of classes; you cannot apply `Protected Friend` to members of a structure because structures cannot be inherited.</span></span>

> [!NOTE]
> <span data-ttu-id="92a07-106">In Visual Studio, selezionare la Guida F1 nei `protected friend` vengono fornite informazioni per uno [protetti](protected.md) oppure [friend](friend.md).</span><span class="sxs-lookup"><span data-stu-id="92a07-106">In Visual Studio, selecting F1 help on `protected friend` provides help for either [protected](protected.md) or [friend](friend.md).</span></span> <span data-ttu-id="92a07-107">L'IDE sceglie il token single sotto il cursore anziché la parola composta.</span><span class="sxs-lookup"><span data-stu-id="92a07-107">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="92a07-108">Regole</span><span class="sxs-lookup"><span data-stu-id="92a07-108">Rules</span></span>

- **<span data-ttu-id="92a07-109">Contesto della dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="92a07-109">Declaration Context.</span></span>** <span data-ttu-id="92a07-110">È possibile usare `Protected Friend` solo a livello di classe.</span><span class="sxs-lookup"><span data-stu-id="92a07-110">You can use `Protected Friend` only at the class level.</span></span> <span data-ttu-id="92a07-111">Ciò significa che il contesto della dichiarazione per un `Protected` elemento deve essere una classe e non può essere un file di origine, lo spazio dei nomi, interfaccia, modulo, struttura o procedure.</span><span class="sxs-lookup"><span data-stu-id="92a07-111">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span> 

## <a name="see-also"></a><span data-ttu-id="92a07-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92a07-112">See also</span></span>

- [<span data-ttu-id="92a07-113">Public</span><span class="sxs-lookup"><span data-stu-id="92a07-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="92a07-114">Protetta</span><span class="sxs-lookup"><span data-stu-id="92a07-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="92a07-115">Friend</span><span class="sxs-lookup"><span data-stu-id="92a07-115">Friend</span></span>](friend.md)
- [<span data-ttu-id="92a07-116">Private</span><span class="sxs-lookup"><span data-stu-id="92a07-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="92a07-117">Private Protected</span><span class="sxs-lookup"><span data-stu-id="92a07-117">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="92a07-118">Livelli di accesso in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="92a07-118">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="92a07-119">Procedure</span><span class="sxs-lookup"><span data-stu-id="92a07-119">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="92a07-120">Strutture</span><span class="sxs-lookup"><span data-stu-id="92a07-120">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="92a07-121">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="92a07-121">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
