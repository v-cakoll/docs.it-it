---
title: Protected Friend
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: f92021f5f0dab9762470c270bdd5182187d587e5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351314"
---
# <a name="protected-friend-visual-basic"></a><span data-ttu-id="5e254-102">Friend protetto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5e254-102">Protected Friend (Visual Basic)</span></span>

<span data-ttu-id="5e254-103">La combinazione delle parole chiave `Protected Friend` è un modificatore di accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="5e254-103">The `Protected Friend` keyword combination is a member access modifier.</span></span> <span data-ttu-id="5e254-104">Conferisce sia l'accesso [Friend](friend.md) che l'accesso [protetto](protected.md) sugli elementi dichiarati, in modo che siano accessibili da qualsiasi punto dello stesso assembly, dalla propria classe e dalle classi derivate.</span><span class="sxs-lookup"><span data-stu-id="5e254-104">It confers both [Friend](friend.md) access and [Protected](protected.md) access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="5e254-105">È possibile specificare `Protected Friend` solo per i membri delle classi; non è possibile applicare `Protected Friend` ai membri di una struttura perché le strutture non possono essere ereditate.</span><span class="sxs-lookup"><span data-stu-id="5e254-105">You can specify `Protected Friend` only on members of classes; you cannot apply `Protected Friend` to members of a structure because structures cannot be inherited.</span></span>

> [!NOTE]
> <span data-ttu-id="5e254-106">In Visual Studio, selezionando la Guida sensibile al contesto `protected friend` viene fornita una guida per [protected](protected.md) o [Friend](friend.md).</span><span class="sxs-lookup"><span data-stu-id="5e254-106">In Visual Studio, selecting F1 help on `protected friend` provides help for either [protected](protected.md) or [friend](friend.md).</span></span> <span data-ttu-id="5e254-107">L'IDE sceglie il singolo token sotto il cursore anziché la parola composta.</span><span class="sxs-lookup"><span data-stu-id="5e254-107">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="5e254-108">Regole</span><span class="sxs-lookup"><span data-stu-id="5e254-108">Rules</span></span>

<span data-ttu-id="5e254-109">**Contesto di dichiarazione.**</span><span class="sxs-lookup"><span data-stu-id="5e254-109">**Declaration Context.**</span></span> <span data-ttu-id="5e254-110">È possibile utilizzare `Protected Friend` solo a livello di classe.</span><span class="sxs-lookup"><span data-stu-id="5e254-110">You can use `Protected Friend` only at the class level.</span></span> <span data-ttu-id="5e254-111">Ciò significa che il contesto di dichiarazione per un elemento di `Protected` deve essere una classe e non può essere un file di origine, uno spazio dei nomi, un'interfaccia, un modulo, una struttura o una procedura.</span><span class="sxs-lookup"><span data-stu-id="5e254-111">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e254-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e254-112">See also</span></span>

- [<span data-ttu-id="5e254-113">Public</span><span class="sxs-lookup"><span data-stu-id="5e254-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="5e254-114">Protected</span><span class="sxs-lookup"><span data-stu-id="5e254-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="5e254-115">Friend</span><span class="sxs-lookup"><span data-stu-id="5e254-115">Friend</span></span>](friend.md)
- [<span data-ttu-id="5e254-116">Private</span><span class="sxs-lookup"><span data-stu-id="5e254-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="5e254-117">Private Protected</span><span class="sxs-lookup"><span data-stu-id="5e254-117">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="5e254-118">Livelli di accesso in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5e254-118">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="5e254-119">Routine</span><span class="sxs-lookup"><span data-stu-id="5e254-119">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="5e254-120">Strutture</span><span class="sxs-lookup"><span data-stu-id="5e254-120">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="5e254-121">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="5e254-121">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
