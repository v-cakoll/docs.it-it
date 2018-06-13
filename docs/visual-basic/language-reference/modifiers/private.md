---
title: Private (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: 40b64b8d2b6306d458b7a9cc657c5b7dc4270eb2
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2018
ms.locfileid: "34234555"
---
# <a name="private-visual-basic"></a><span data-ttu-id="73bb0-102">Private (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73bb0-102">Private (Visual Basic)</span></span>
<span data-ttu-id="73bb0-103">Specifica che uno o più elementi di programmazione dichiarati sono accessibili solo dal contesto della dichiarazione, anche all'interno di qualsiasi tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="73bb0-103">Specifies that one or more declared programming elements are accessible only from within their declaration context, including from within any contained types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73bb0-104">Note</span><span class="sxs-lookup"><span data-stu-id="73bb0-104">Remarks</span></span>  
 <span data-ttu-id="73bb0-105">Se un elemento di programmazione rappresenta una funzionalità proprietaria o contiene dati riservati, in genere si desidera limitare l'accesso come sia possibile.</span><span class="sxs-lookup"><span data-stu-id="73bb0-105">If a programming element represents proprietary functionality, or contains confidential data, you usually want to limit access to it as strictly as possible.</span></span> <span data-ttu-id="73bb0-106">Per ottenere il limite massimo di consentire solo il modulo, classe o struttura che definisce per accedervi.</span><span class="sxs-lookup"><span data-stu-id="73bb0-106">You achieve the maximum limitation by allowing only the module, class, or structure that defines it to access it.</span></span> <span data-ttu-id="73bb0-107">Per limitare l'accesso a un elemento in questo modo, è possibile dichiarare con `Private`.</span><span class="sxs-lookup"><span data-stu-id="73bb0-107">To limit access to an element in this way, you can declare it with `Private`.</span></span>  

> [!NOTE]
> <span data-ttu-id="73bb0-108">È anche possibile usare il [privato protetto](private-protected.md) modificatore di accesso, che rende accessibili da all'interno della classe e dalle classi derivate che si trova nell'assembly che contiene un membro.</span><span class="sxs-lookup"><span data-stu-id="73bb0-108">You can also use the [Private Protected](private-protected.md) access modifier, which makes a member accessible from within that class and from derived classes located in its containing assembly.</span></span>

## <a name="rules"></a><span data-ttu-id="73bb0-109">Regole</span><span class="sxs-lookup"><span data-stu-id="73bb0-109">Rules</span></span>  

-   <span data-ttu-id="73bb0-110">**Contesto della dichiarazione.**</span><span class="sxs-lookup"><span data-stu-id="73bb0-110">**Declaration Context.**</span></span> <span data-ttu-id="73bb0-111">Si può usare `Private` solo a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="73bb0-111">You can use `Private` only at module level.</span></span> <span data-ttu-id="73bb0-112">Ciò significa che il contesto della dichiarazione per un `Private` elemento deve essere un modulo, classe o struttura e non può essere un file di origine, lo spazio dei nomi, interfaccia o stored procedure.</span><span class="sxs-lookup"><span data-stu-id="73bb0-112">This means the declaration context for a `Private` element must be a module, class, or structure, and cannot be a source file, namespace, interface, or procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="73bb0-113">Comportamento</span><span class="sxs-lookup"><span data-stu-id="73bb0-113">Behavior</span></span>  
  
-   <span data-ttu-id="73bb0-114">**Livello di accesso.**</span><span class="sxs-lookup"><span data-stu-id="73bb0-114">**Access Level.**</span></span> <span data-ttu-id="73bb0-115">Può accedere a tutto il codice all'interno di un contesto della dichiarazione relativa `Private` elementi.</span><span class="sxs-lookup"><span data-stu-id="73bb0-115">All code within a declaration context can access its `Private` elements.</span></span> <span data-ttu-id="73bb0-116">Ciò include il codice all'interno di un tipo di contenuto, ad esempio una classe annidata o un'espressione di assegnazione in un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="73bb0-116">This includes code within a contained type, such as a nested class or an assignment expression in an enumeration.</span></span> <span data-ttu-id="73bb0-117">Nessun codice all'esterno del contesto di dichiarazione può accedere il `Private` elementi.</span><span class="sxs-lookup"><span data-stu-id="73bb0-117">No code outside of the declaration context can access its `Private` elements.</span></span>  
  
-   <span data-ttu-id="73bb0-118">**Modificatori di accesso.**</span><span class="sxs-lookup"><span data-stu-id="73bb0-118">**Access Modifiers.**</span></span> <span data-ttu-id="73bb0-119">Le parole chiave che specificano il livello di accesso vengono chiamate *modificatori di accesso*.</span><span class="sxs-lookup"><span data-stu-id="73bb0-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="73bb0-120">Per un confronto tra i modificatori di accesso, vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="73bb0-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="73bb0-121">Il modificatore `Private` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="73bb0-121">The `Private` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="73bb0-122">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="73bb0-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="73bb0-123">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="73bb0-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="73bb0-124">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="73bb0-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="73bb0-125">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="73bb0-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="73bb0-126">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="73bb0-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="73bb0-127">Istruzione Enum</span><span class="sxs-lookup"><span data-stu-id="73bb0-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="73bb0-128">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="73bb0-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="73bb0-129">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="73bb0-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="73bb0-130">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="73bb0-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="73bb0-131">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="73bb0-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="73bb0-132">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="73bb0-132">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="73bb0-133">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="73bb0-133">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="73bb0-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73bb0-134">See Also</span></span>  
 [<span data-ttu-id="73bb0-135">Public</span><span class="sxs-lookup"><span data-stu-id="73bb0-135">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="73bb0-136">Protected</span><span class="sxs-lookup"><span data-stu-id="73bb0-136">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
 [<span data-ttu-id="73bb0-137">Friend</span><span class="sxs-lookup"><span data-stu-id="73bb0-137">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
 <span data-ttu-id="73bb0-138">[Protetto privato](./private-protected.md) </span><span class="sxs-lookup"><span data-stu-id="73bb0-138">[Private Protected](./private-protected.md) </span></span>  
 <span data-ttu-id="73bb0-139">[Protected Friend](./protected-friend.md)[accedere livelli in Visual Basic    ](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)</span><span class="sxs-lookup"><span data-stu-id="73bb0-139">[Protected Friend](./protected-friend.md)    [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)</span></span>  
 [<span data-ttu-id="73bb0-140">Routine</span><span class="sxs-lookup"><span data-stu-id="73bb0-140">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="73bb0-141">Strutture</span><span class="sxs-lookup"><span data-stu-id="73bb0-141">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="73bb0-142">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="73bb0-142">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
