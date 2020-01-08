---
title: Private
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: 0c855c4e08b365b4cb75ab062d2ec304a79612ab
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347909"
---
# <a name="private-visual-basic"></a><span data-ttu-id="6ba9a-102">Private (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6ba9a-102">Private (Visual Basic)</span></span>
<span data-ttu-id="6ba9a-103">Specifica che uno o più elementi di programmazione dichiarati sono accessibili solo dall'interno del contesto di dichiarazione, incluso all'interno di qualsiasi tipo contenuto.</span><span class="sxs-lookup"><span data-stu-id="6ba9a-103">Specifies that one or more declared programming elements are accessible only from within their declaration context, including from within any contained types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ba9a-104">Note</span><span class="sxs-lookup"><span data-stu-id="6ba9a-104">Remarks</span></span>  
 <span data-ttu-id="6ba9a-105">Se un elemento di programmazione rappresenta una funzionalità proprietaria o contiene dati riservati, in genere si vuole limitarne l'accesso al più possibile.</span><span class="sxs-lookup"><span data-stu-id="6ba9a-105">If a programming element represents proprietary functionality, or contains confidential data, you usually want to limit access to it as strictly as possible.</span></span> <span data-ttu-id="6ba9a-106">Si ottiene la massima limitazione consentendo solo il modulo, la classe o la struttura che lo definisce per accedervi.</span><span class="sxs-lookup"><span data-stu-id="6ba9a-106">You achieve the maximum limitation by allowing only the module, class, or structure that defines it to access it.</span></span> <span data-ttu-id="6ba9a-107">Per limitare l'accesso a un elemento in questo modo, è possibile dichiararlo con `Private`.</span><span class="sxs-lookup"><span data-stu-id="6ba9a-107">To limit access to an element in this way, you can declare it with `Private`.</span></span>  

> [!NOTE]
> <span data-ttu-id="6ba9a-108">È anche possibile usare il modificatore di accesso [privato protetto](private-protected.md) , che rende accessibile un membro all'interno di tale classe e dalle classi derivate presenti nell'assembly contenitore.</span><span class="sxs-lookup"><span data-stu-id="6ba9a-108">You can also use the [Private Protected](private-protected.md) access modifier, which makes a member accessible from within that class and from derived classes located in its containing assembly.</span></span>

## <a name="rules"></a><span data-ttu-id="6ba9a-109">regole</span><span class="sxs-lookup"><span data-stu-id="6ba9a-109">Rules</span></span>  

- <span data-ttu-id="6ba9a-110">**Contesto di dichiarazione.**</span><span class="sxs-lookup"><span data-stu-id="6ba9a-110">**Declaration Context.**</span></span> <span data-ttu-id="6ba9a-111">Si può usare `Private` solo a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="6ba9a-111">You can use `Private` only at module level.</span></span> <span data-ttu-id="6ba9a-112">Ciò significa che il contesto di dichiarazione per un elemento di `Private` deve essere un modulo, una classe o una struttura e non può essere un file di origine, uno spazio dei nomi, un'interfaccia o una routine.</span><span class="sxs-lookup"><span data-stu-id="6ba9a-112">This means the declaration context for a `Private` element must be a module, class, or structure, and cannot be a source file, namespace, interface, or procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="6ba9a-113">Comportamento di</span><span class="sxs-lookup"><span data-stu-id="6ba9a-113">Behavior</span></span>  
  
- <span data-ttu-id="6ba9a-114">**Livello di accesso.**</span><span class="sxs-lookup"><span data-stu-id="6ba9a-114">**Access Level.**</span></span> <span data-ttu-id="6ba9a-115">Tutto il codice all'interno di un contesto di dichiarazione può accedere ai relativi elementi `Private`.</span><span class="sxs-lookup"><span data-stu-id="6ba9a-115">All code within a declaration context can access its `Private` elements.</span></span> <span data-ttu-id="6ba9a-116">Incluso il codice all'interno di un tipo contenuto, ad esempio una classe annidata o un'espressione di assegnazione in un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="6ba9a-116">This includes code within a contained type, such as a nested class or an assignment expression in an enumeration.</span></span> <span data-ttu-id="6ba9a-117">Nessun codice esterno al contesto di dichiarazione può accedere ai relativi elementi `Private`.</span><span class="sxs-lookup"><span data-stu-id="6ba9a-117">No code outside of the declaration context can access its `Private` elements.</span></span>  
  
- <span data-ttu-id="6ba9a-118">**Modificatori di accesso.**</span><span class="sxs-lookup"><span data-stu-id="6ba9a-118">**Access Modifiers.**</span></span> <span data-ttu-id="6ba9a-119">Le parole chiave che specificano il livello di accesso sono denominate *modificatori di accesso*.</span><span class="sxs-lookup"><span data-stu-id="6ba9a-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="6ba9a-120">Per un confronto dei modificatori di accesso, vedere [livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="6ba9a-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="6ba9a-121">Il modificatore `Private` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ba9a-121">The `Private` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="6ba9a-122">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="6ba9a-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="6ba9a-123">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="6ba9a-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="6ba9a-124">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="6ba9a-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="6ba9a-125">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="6ba9a-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="6ba9a-126">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="6ba9a-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="6ba9a-127">Istruzione Enum</span><span class="sxs-lookup"><span data-stu-id="6ba9a-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="6ba9a-128">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="6ba9a-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="6ba9a-129">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="6ba9a-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="6ba9a-130">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="6ba9a-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="6ba9a-131">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="6ba9a-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="6ba9a-132">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="6ba9a-132">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="6ba9a-133">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="6ba9a-133">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="6ba9a-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ba9a-134">See also</span></span>

- [<span data-ttu-id="6ba9a-135">Public</span><span class="sxs-lookup"><span data-stu-id="6ba9a-135">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="6ba9a-136">Protected</span><span class="sxs-lookup"><span data-stu-id="6ba9a-136">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="6ba9a-137">Friend</span><span class="sxs-lookup"><span data-stu-id="6ba9a-137">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="6ba9a-138">Private Protected</span><span class="sxs-lookup"><span data-stu-id="6ba9a-138">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="6ba9a-139">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="6ba9a-139">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="6ba9a-140">Livelli di accesso in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6ba9a-140">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="6ba9a-141">Routine</span><span class="sxs-lookup"><span data-stu-id="6ba9a-141">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="6ba9a-142">Strutture</span><span class="sxs-lookup"><span data-stu-id="6ba9a-142">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="6ba9a-143">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="6ba9a-143">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
