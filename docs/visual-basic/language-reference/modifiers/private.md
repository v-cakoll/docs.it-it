---
title: Private (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: ddb2d165de330758f58fbbcb5872e820e639808f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64642792"
---
# <a name="private-visual-basic"></a><span data-ttu-id="b1678-102">Private (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1678-102">Private (Visual Basic)</span></span>
<span data-ttu-id="b1678-103">Specifica che uno o più elementi di programmazione dichiarati sono accessibili solo dal contesto della dichiarazione, anche all'interno di qualsiasi tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="b1678-103">Specifies that one or more declared programming elements are accessible only from within their declaration context, including from within any contained types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1678-104">Note</span><span class="sxs-lookup"><span data-stu-id="b1678-104">Remarks</span></span>  
 <span data-ttu-id="b1678-105">Se un elemento di programmazione rappresenta funzionalità proprietarie o contiene dati riservati, in genere si desidera limitare l'accesso come rigorosamente possibili.</span><span class="sxs-lookup"><span data-stu-id="b1678-105">If a programming element represents proprietary functionality, or contains confidential data, you usually want to limit access to it as strictly as possible.</span></span> <span data-ttu-id="b1678-106">Per ottenere il limite massimo di consentendo solo il modulo, classe o struttura che definisca in modo da accedervi.</span><span class="sxs-lookup"><span data-stu-id="b1678-106">You achieve the maximum limitation by allowing only the module, class, or structure that defines it to access it.</span></span> <span data-ttu-id="b1678-107">Per limitare l'accesso a un elemento in questo modo, è possibile dichiararla con `Private`.</span><span class="sxs-lookup"><span data-stu-id="b1678-107">To limit access to an element in this way, you can declare it with `Private`.</span></span>  

> [!NOTE]
> <span data-ttu-id="b1678-108">È anche possibile usare la [Private Protected](private-protected.md) modificatore di accesso, che rende accessibili da all'interno di tale classe e dalle classi derivate che si trova nel relativo assembly che contiene un membro.</span><span class="sxs-lookup"><span data-stu-id="b1678-108">You can also use the [Private Protected](private-protected.md) access modifier, which makes a member accessible from within that class and from derived classes located in its containing assembly.</span></span>

## <a name="rules"></a><span data-ttu-id="b1678-109">Regole</span><span class="sxs-lookup"><span data-stu-id="b1678-109">Rules</span></span>  

- <span data-ttu-id="b1678-110">**Contesto della dichiarazione.**</span><span class="sxs-lookup"><span data-stu-id="b1678-110">**Declaration Context.**</span></span> <span data-ttu-id="b1678-111">Si può usare `Private` solo a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="b1678-111">You can use `Private` only at module level.</span></span> <span data-ttu-id="b1678-112">Ciò significa che il contesto della dichiarazione per un `Private` elemento deve essere un modulo, classe o struttura e non può essere un file di origine, lo spazio dei nomi, interfaccia o procedura.</span><span class="sxs-lookup"><span data-stu-id="b1678-112">This means the declaration context for a `Private` element must be a module, class, or structure, and cannot be a source file, namespace, interface, or procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="b1678-113">Comportamento</span><span class="sxs-lookup"><span data-stu-id="b1678-113">Behavior</span></span>  
  
- <span data-ttu-id="b1678-114">**Livello di accesso.**</span><span class="sxs-lookup"><span data-stu-id="b1678-114">**Access Level.**</span></span> <span data-ttu-id="b1678-115">Può accedere a tutto il codice all'interno di un contesto della dichiarazione relativo `Private` elementi.</span><span class="sxs-lookup"><span data-stu-id="b1678-115">All code within a declaration context can access its `Private` elements.</span></span> <span data-ttu-id="b1678-116">Ciò include il codice all'interno di un tipo di contenuto, ad esempio una classe annidata o un'espressione di assegnazione in un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="b1678-116">This includes code within a contained type, such as a nested class or an assignment expression in an enumeration.</span></span> <span data-ttu-id="b1678-117">Non può accedere a nessun codice all'esterno del contesto di dichiarazione relativa `Private` elementi.</span><span class="sxs-lookup"><span data-stu-id="b1678-117">No code outside of the declaration context can access its `Private` elements.</span></span>  
  
- <span data-ttu-id="b1678-118">**Modificatori di accesso.**</span><span class="sxs-lookup"><span data-stu-id="b1678-118">**Access Modifiers.**</span></span> <span data-ttu-id="b1678-119">Le parole chiave che specificano il livello di accesso vengono chiamate *modificatori di accesso*.</span><span class="sxs-lookup"><span data-stu-id="b1678-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="b1678-120">Per un confronto tra i modificatori di accesso, vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="b1678-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="b1678-121">Il modificatore `Private` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b1678-121">The `Private` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="b1678-122">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="b1678-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="b1678-123">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="b1678-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="b1678-124">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="b1678-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="b1678-125">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="b1678-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="b1678-126">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="b1678-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="b1678-127">Istruzione Enum</span><span class="sxs-lookup"><span data-stu-id="b1678-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="b1678-128">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="b1678-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="b1678-129">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="b1678-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="b1678-130">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="b1678-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="b1678-131">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="b1678-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="b1678-132">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="b1678-132">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="b1678-133">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="b1678-133">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="b1678-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1678-134">See also</span></span>

- [<span data-ttu-id="b1678-135">Public</span><span class="sxs-lookup"><span data-stu-id="b1678-135">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="b1678-136">Protected</span><span class="sxs-lookup"><span data-stu-id="b1678-136">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="b1678-137">Friend</span><span class="sxs-lookup"><span data-stu-id="b1678-137">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="b1678-138">Private Protected</span><span class="sxs-lookup"><span data-stu-id="b1678-138">Private Protected</span></span>](./private-protected.md)
- <span data-ttu-id="b1678-139">[Protected Friend](./protected-friend.md)[Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)</span><span class="sxs-lookup"><span data-stu-id="b1678-139">[Protected Friend](./protected-friend.md)    [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)</span></span>
- [<span data-ttu-id="b1678-140">Routine</span><span class="sxs-lookup"><span data-stu-id="b1678-140">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="b1678-141">Strutture</span><span class="sxs-lookup"><span data-stu-id="b1678-141">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="b1678-142">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="b1678-142">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
