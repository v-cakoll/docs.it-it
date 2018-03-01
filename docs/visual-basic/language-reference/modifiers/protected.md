---
title: Protected (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Protected
helpviewer_keywords:
- Protected Friend keyword combination
- Protected keyword [Visual Basic], and Friend
- Protected keyword [Visual Basic], syntax
- Protected access modifier
- Protected keyword [Visual Basic]
ms.assetid: 74ad3d56-309f-49d2-b60c-1d0157d010e8
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2d0cc7a0cb626a9ec8e2a0e47abc02e5268aed56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="protected-visual-basic"></a><span data-ttu-id="1af5f-102">Protected (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1af5f-102">Protected (Visual Basic)</span></span>
<span data-ttu-id="1af5f-103">Specifica che uno o più elementi di programmazione dichiarati sono accessibili solo dall'interno della propria classe o da una classe derivata.</span><span class="sxs-lookup"><span data-stu-id="1af5f-103">Specifies that one or more declared programming elements are accessible only from within their own class or from a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1af5f-104">Note</span><span class="sxs-lookup"><span data-stu-id="1af5f-104">Remarks</span></span>  
 <span data-ttu-id="1af5f-105">Talvolta un elemento di programmazione dichiarato in una classe contiene dati sensibili o codice con restrizioni, e si desidera limitare l'accesso all'elemento.</span><span class="sxs-lookup"><span data-stu-id="1af5f-105">Sometimes a programming element declared in a class contains sensitive data or restricted code, and you want to limit access to the element.</span></span> <span data-ttu-id="1af5f-106">Tuttavia, se la classe è ereditabile e si prevede una gerarchia di classi derivate, potrebbe essere necessario per queste classi derivate di accedere ai dati o codice.</span><span class="sxs-lookup"><span data-stu-id="1af5f-106">However, if the class is inheritable and you expect a hierarchy of derived classes, it might be necessary for these derived classes to access the data or code.</span></span> <span data-ttu-id="1af5f-107">In tal caso, si desidera l'elemento deve essere accessibile dalla classe di base e da tutte le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="1af5f-107">In such a case, you want the element to be accessible both from the base class and from all derived classes.</span></span> <span data-ttu-id="1af5f-108">Per limitare l'accesso a un elemento in questo modo, è possibile dichiarare con `Protected`.</span><span class="sxs-lookup"><span data-stu-id="1af5f-108">To limit access to an element in this manner, you can declare it with `Protected`.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="1af5f-109">Regole</span><span class="sxs-lookup"><span data-stu-id="1af5f-109">Rules</span></span>  
  
-   <span data-ttu-id="1af5f-110">**Contesto della dichiarazione.**</span><span class="sxs-lookup"><span data-stu-id="1af5f-110">**Declaration Context.**</span></span> <span data-ttu-id="1af5f-111">È possibile utilizzare `Protected` solo a livello di classe.</span><span class="sxs-lookup"><span data-stu-id="1af5f-111">You can use `Protected` only at class level.</span></span> <span data-ttu-id="1af5f-112">Ciò significa che il contesto della dichiarazione per un `Protected` elemento deve essere una classe e non può essere un file di origine, lo spazio dei nomi, interfaccia, modulo, struttura o stored procedure.</span><span class="sxs-lookup"><span data-stu-id="1af5f-112">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>  
  
-   <span data-ttu-id="1af5f-113">**Modificatori combinati.**</span><span class="sxs-lookup"><span data-stu-id="1af5f-113">**Combined Modifiers.**</span></span> <span data-ttu-id="1af5f-114">È possibile utilizzare il `Protected` modificatore insieme con il [Friend](../../../visual-basic/language-reference/modifiers/friend.md) modificatore nella stessa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="1af5f-114">You can use the `Protected` modifier together with the [Friend](../../../visual-basic/language-reference/modifiers/friend.md) modifier in the same declaration.</span></span> <span data-ttu-id="1af5f-115">Questa combinazione rende gli elementi dichiarati accessibili da un punto qualsiasi nello stesso assembly, dalla rispettiva classe e dalle classi derivate.</span><span class="sxs-lookup"><span data-stu-id="1af5f-115">This combination makes the declared elements accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="1af5f-116">È possibile specificare `Protected Friend` solo in membri di classi.</span><span class="sxs-lookup"><span data-stu-id="1af5f-116">You can specify `Protected Friend` only on members of classes.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="1af5f-117">Comportamento</span><span class="sxs-lookup"><span data-stu-id="1af5f-117">Behavior</span></span>  
  
-   <span data-ttu-id="1af5f-118">**Livello di accesso.**</span><span class="sxs-lookup"><span data-stu-id="1af5f-118">**Access Level.**</span></span> <span data-ttu-id="1af5f-119">Tutto il codice in una classe possa accedere ai relativi elementi.</span><span class="sxs-lookup"><span data-stu-id="1af5f-119">All code in a class can access its elements.</span></span> <span data-ttu-id="1af5f-120">Codice di qualsiasi classe che deriva da una classe di base può accedere a tutti i `Protected` gli elementi della classe di base.</span><span class="sxs-lookup"><span data-stu-id="1af5f-120">Code in any class that derives from a base class can access all the `Protected` elements of the base class.</span></span> <span data-ttu-id="1af5f-121">Questo vale per tutte le generazioni di derivazione.</span><span class="sxs-lookup"><span data-stu-id="1af5f-121">This is true for all generations of derivation.</span></span> <span data-ttu-id="1af5f-122">Ciò significa che possa accedere a una classe `Protected` gli elementi della classe di base della classe base e così via.</span><span class="sxs-lookup"><span data-stu-id="1af5f-122">This means that a class can access `Protected` elements of the base class of the base class, and so on.</span></span>  
  
     <span data-ttu-id="1af5f-123">Accesso protetto non è un superset o un sottoinsieme di accesso friend.</span><span class="sxs-lookup"><span data-stu-id="1af5f-123">Protected access is not a superset or subset of friend access.</span></span>  
  
-   <span data-ttu-id="1af5f-124">**Modificatori di accesso.**</span><span class="sxs-lookup"><span data-stu-id="1af5f-124">**Access Modifiers.**</span></span> <span data-ttu-id="1af5f-125">Le parole chiave che specificano il livello di accesso vengono chiamate *modificatori di accesso*.</span><span class="sxs-lookup"><span data-stu-id="1af5f-125">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="1af5f-126">Per un confronto tra i modificatori di accesso, vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="1af5f-126">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="1af5f-127">Il modificatore `Protected` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1af5f-127">The `Protected` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="1af5f-128">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="1af5f-128">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="1af5f-129">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="1af5f-129">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="1af5f-130">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="1af5f-130">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="1af5f-131">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="1af5f-131">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="1af5f-132">Istruzione Dim</span><span class="sxs-lookup"><span data-stu-id="1af5f-132">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="1af5f-133">Istruzione Enum</span><span class="sxs-lookup"><span data-stu-id="1af5f-133">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="1af5f-134">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="1af5f-134">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="1af5f-135">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="1af5f-135">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="1af5f-136">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="1af5f-136">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="1af5f-137">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="1af5f-137">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="1af5f-138">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="1af5f-138">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="1af5f-139">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="1af5f-139">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="1af5f-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1af5f-140">See Also</span></span>  
 [<span data-ttu-id="1af5f-141">Public</span><span class="sxs-lookup"><span data-stu-id="1af5f-141">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="1af5f-142">Friend</span><span class="sxs-lookup"><span data-stu-id="1af5f-142">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
 [<span data-ttu-id="1af5f-143">Private</span><span class="sxs-lookup"><span data-stu-id="1af5f-143">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
 [<span data-ttu-id="1af5f-144">Livelli di accesso in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1af5f-144">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="1af5f-145">Routine</span><span class="sxs-lookup"><span data-stu-id="1af5f-145">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="1af5f-146">Strutture</span><span class="sxs-lookup"><span data-stu-id="1af5f-146">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="1af5f-147">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="1af5f-147">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
