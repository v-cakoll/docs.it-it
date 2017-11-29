---
title: Private (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 07450c2a5443bf6bc147cad2cfc779072bfc363b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="private-visual-basic"></a><span data-ttu-id="bc41e-102">Private (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc41e-102">Private (Visual Basic)</span></span>
<span data-ttu-id="bc41e-103">Specifica che uno o più elementi di programmazione dichiarati sono accessibili solo dal contesto della dichiarazione, anche all'interno di qualsiasi tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="bc41e-103">Specifies that one or more declared programming elements are accessible only from within their declaration context, including from within any contained types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc41e-104">Note</span><span class="sxs-lookup"><span data-stu-id="bc41e-104">Remarks</span></span>  
 <span data-ttu-id="bc41e-105">Se un elemento di programmazione rappresenta una funzionalità proprietaria o contiene dati riservati, in genere si desidera limitare l'accesso come sia possibile.</span><span class="sxs-lookup"><span data-stu-id="bc41e-105">If a programming element represents proprietary functionality, or contains confidential data, you usually want to limit access to it as strictly as possible.</span></span> <span data-ttu-id="bc41e-106">Per ottenere il limite massimo di consentire solo il modulo, classe o struttura che definisce per accedervi.</span><span class="sxs-lookup"><span data-stu-id="bc41e-106">You achieve the maximum limitation by allowing only the module, class, or structure that defines it to access it.</span></span> <span data-ttu-id="bc41e-107">Per limitare l'accesso a un elemento in questo modo, è possibile dichiarare con `Private`.</span><span class="sxs-lookup"><span data-stu-id="bc41e-107">To limit access to an element in this way, you can declare it with `Private`.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="bc41e-108">Regole</span><span class="sxs-lookup"><span data-stu-id="bc41e-108">Rules</span></span>  
  
-   <span data-ttu-id="bc41e-109">**Contesto della dichiarazione.**</span><span class="sxs-lookup"><span data-stu-id="bc41e-109">**Declaration Context.**</span></span> <span data-ttu-id="bc41e-110">Si può usare `Private` solo a livello di modulo.</span><span class="sxs-lookup"><span data-stu-id="bc41e-110">You can use `Private` only at module level.</span></span> <span data-ttu-id="bc41e-111">Ciò significa che il contesto della dichiarazione per un `Private` elemento deve essere un modulo, classe o struttura e non può essere un file di origine, lo spazio dei nomi, interfaccia o stored procedure.</span><span class="sxs-lookup"><span data-stu-id="bc41e-111">This means the declaration context for a `Private` element must be a module, class, or structure, and cannot be a source file, namespace, interface, or procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="bc41e-112">Comportamento</span><span class="sxs-lookup"><span data-stu-id="bc41e-112">Behavior</span></span>  
  
-   <span data-ttu-id="bc41e-113">**Livello di accesso.**</span><span class="sxs-lookup"><span data-stu-id="bc41e-113">**Access Level.**</span></span> <span data-ttu-id="bc41e-114">Può accedere a tutto il codice all'interno di un contesto della dichiarazione relativa `Private` elementi.</span><span class="sxs-lookup"><span data-stu-id="bc41e-114">All code within a declaration context can access its `Private` elements.</span></span> <span data-ttu-id="bc41e-115">Ciò include il codice all'interno di un tipo di contenuto, ad esempio una classe annidata o un'espressione di assegnazione in un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bc41e-115">This includes code within a contained type, such as a nested class or an assignment expression in an enumeration.</span></span> <span data-ttu-id="bc41e-116">Nessun codice all'esterno del contesto di dichiarazione può accedere il `Private` elementi.</span><span class="sxs-lookup"><span data-stu-id="bc41e-116">No code outside of the declaration context can access its `Private` elements.</span></span>  
  
-   <span data-ttu-id="bc41e-117">**Modificatori di accesso.**</span><span class="sxs-lookup"><span data-stu-id="bc41e-117">**Access Modifiers.**</span></span> <span data-ttu-id="bc41e-118">Le parole chiave che specificano il livello di accesso vengono chiamate *modificatori di accesso*.</span><span class="sxs-lookup"><span data-stu-id="bc41e-118">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="bc41e-119">Per un confronto tra i modificatori di accesso, vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="bc41e-119">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="bc41e-120">Il modificatore `Private` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="bc41e-120">The `Private` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="bc41e-121">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="bc41e-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="bc41e-122">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="bc41e-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="bc41e-123">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="bc41e-123">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="bc41e-124">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="bc41e-124">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="bc41e-125">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="bc41e-125">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="bc41e-126">Istruzione Enum</span><span class="sxs-lookup"><span data-stu-id="bc41e-126">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="bc41e-127">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="bc41e-127">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="bc41e-128">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="bc41e-128">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="bc41e-129">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="bc41e-129">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="bc41e-130">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="bc41e-130">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="bc41e-131">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="bc41e-131">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="bc41e-132">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="bc41e-132">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="bc41e-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc41e-133">See Also</span></span>  
 [<span data-ttu-id="bc41e-134">Public</span><span class="sxs-lookup"><span data-stu-id="bc41e-134">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="bc41e-135">Protected</span><span class="sxs-lookup"><span data-stu-id="bc41e-135">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
 [<span data-ttu-id="bc41e-136">Friend</span><span class="sxs-lookup"><span data-stu-id="bc41e-136">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
 [<span data-ttu-id="bc41e-137">Livelli di accesso in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bc41e-137">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="bc41e-138">Routine</span><span class="sxs-lookup"><span data-stu-id="bc41e-138">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="bc41e-139">Strutture</span><span class="sxs-lookup"><span data-stu-id="bc41e-139">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="bc41e-140">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="bc41e-140">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
