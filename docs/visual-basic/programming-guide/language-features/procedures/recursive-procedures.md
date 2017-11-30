---
title: Routine ricorsive (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], that call themselves
- procedures [Visual Basic], recursive
- procedures [Visual Basic], calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 444eeaf043cf3710c5154fd7e8577590e3ce7d1e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="recursive-procedures-visual-basic"></a><span data-ttu-id="24427-102">Routine ricorsive (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="24427-102">Recursive Procedures (Visual Basic)</span></span>
<span data-ttu-id="24427-103">Oggetto *ricorsiva* procedure è una classe che chiama se stessa.</span><span class="sxs-lookup"><span data-stu-id="24427-103">A *recursive* procedure is one that calls itself.</span></span> <span data-ttu-id="24427-104">In generale, questo non è il modo più efficace per scrivere [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] codice.</span><span class="sxs-lookup"><span data-stu-id="24427-104">In general, this is not the most effective way to write [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] code.</span></span>  
  
 <span data-ttu-id="24427-105">La procedura seguente usa la ricorsione per calcolare il fattoriale del relativo argomento originale.</span><span class="sxs-lookup"><span data-stu-id="24427-105">The following procedure uses recursion to calculate the factorial of its original argument.</span></span>  
  
 [!code-vb[VbVbcnProcedures#51](./codesnippet/VisualBasic/recursive-procedures_1.vb)]  
  
## <a name="considerations-with-recursive-procedures"></a><span data-ttu-id="24427-106">Considerazioni sulle routine ricorsive</span><span class="sxs-lookup"><span data-stu-id="24427-106">Considerations with Recursive Procedures</span></span>  
 <span data-ttu-id="24427-107">**Le condizioni di limitazione**.</span><span class="sxs-lookup"><span data-stu-id="24427-107">**Limiting Conditions**.</span></span> <span data-ttu-id="24427-108">È necessario progettare una routine ricorsiva per verificare la presenza di almeno una condizione in grado di terminare la ricorsione e, è necessario gestire anche nel caso in cui tale condizione non viene soddisfatta entro un numero ragionevole di chiamate ricorsive.</span><span class="sxs-lookup"><span data-stu-id="24427-108">You must design a recursive procedure to test for at least one condition that can terminate the recursion, and you must also handle the case where no such condition is satisfied within a reasonable number of recursive calls.</span></span> <span data-ttu-id="24427-109">Senza almeno una condizione che può essere soddisfatta senza errori, la stored procedure viene eseguito un rischio elevato dell'esecuzione in un ciclo infinito.</span><span class="sxs-lookup"><span data-stu-id="24427-109">Without at least one condition that can be met without fail, your procedure runs a high risk of executing in an infinite loop.</span></span>  
  
 <span data-ttu-id="24427-110">**Utilizzo memoria**.</span><span class="sxs-lookup"><span data-stu-id="24427-110">**Memory Usage**.</span></span> <span data-ttu-id="24427-111">L'applicazione dispone di una quantità limitata di spazio per le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="24427-111">Your application has a limited amount of space for local variables.</span></span> <span data-ttu-id="24427-112">Ogni volta che una routine chiama se stessa, viene utilizzato più lo spazio per le copie aggiuntive delle variabili locali.</span><span class="sxs-lookup"><span data-stu-id="24427-112">Each time a procedure calls itself, it uses more of that space for additional copies of its local variables.</span></span> <span data-ttu-id="24427-113">Se questo processo continua in modo indefinito, provoca un <xref:System.StackOverflowException> errore.</span><span class="sxs-lookup"><span data-stu-id="24427-113">If this process continues indefinitely, it eventually causes a <xref:System.StackOverflowException> error.</span></span>  
  
 <span data-ttu-id="24427-114">**L'efficienza**.</span><span class="sxs-lookup"><span data-stu-id="24427-114">**Efficiency**.</span></span> <span data-ttu-id="24427-115">È quasi sempre possibile sostituire un ciclo per la ricorsione.</span><span class="sxs-lookup"><span data-stu-id="24427-115">You can almost always substitute a loop for recursion.</span></span> <span data-ttu-id="24427-116">L'overhead del passaggio degli argomenti, l'inizializzazione di ulteriore spazio di archiviazione e la restituzione di valori non dispone di un ciclo.</span><span class="sxs-lookup"><span data-stu-id="24427-116">A loop does not have the overhead of passing arguments, initializing additional storage, and returning values.</span></span> <span data-ttu-id="24427-117">Le prestazioni migliorano in modo significativo senza chiamate ricorsive.</span><span class="sxs-lookup"><span data-stu-id="24427-117">Your performance can be much better without recursive calls.</span></span>  
  
 <span data-ttu-id="24427-118">**Ricorsione reciproca**.</span><span class="sxs-lookup"><span data-stu-id="24427-118">**Mutual Recursion**.</span></span> <span data-ttu-id="24427-119">Si noterà probabilmente prestazioni estremamente insufficienti o anche un ciclo infinito se due procedure comunicano tra loro.</span><span class="sxs-lookup"><span data-stu-id="24427-119">You might observe very poor performance, or even an infinite loop, if two procedures call each other.</span></span> <span data-ttu-id="24427-120">Tale progettazione presenta gli stessi problemi come una singola routine ricorsiva, ma può essere difficile rilevare ed eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="24427-120">Such a design presents the same problems as a single recursive procedure, but can be harder to detect and debug.</span></span>  
  
 <span data-ttu-id="24427-121">**La chiamata con parentesi**.</span><span class="sxs-lookup"><span data-stu-id="24427-121">**Calling with Parentheses**.</span></span> <span data-ttu-id="24427-122">Quando un `Function` routine chiama se stessa in modo ricorsivo, è necessario seguire il nome della routine con parentesi, anche se è presente alcun elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="24427-122">When a `Function` procedure calls itself recursively, you must follow the procedure name with parentheses, even if there is no argument list.</span></span> <span data-ttu-id="24427-123">In caso contrario, il nome della funzione viene eseguito come rappresenta il valore restituito della funzione.</span><span class="sxs-lookup"><span data-stu-id="24427-123">Otherwise, the function name is taken as representing the return value of the function.</span></span>  
  
 <span data-ttu-id="24427-124">**Test**.</span><span class="sxs-lookup"><span data-stu-id="24427-124">**Testing**.</span></span> <span data-ttu-id="24427-125">Se si scrive una routine ricorsiva, è necessario eseguirne il test con molta attenzione per assicurarsi che soddisfi sempre alcune condizioni di limitazione.</span><span class="sxs-lookup"><span data-stu-id="24427-125">If you write a recursive procedure, you should test it very carefully to make sure it always meets some limiting condition.</span></span> <span data-ttu-id="24427-126">È inoltre necessario assicurarsi che non è possibile eseguire esaurito la memoria a causa di un numero eccessivo di chiamate ricorsive.</span><span class="sxs-lookup"><span data-stu-id="24427-126">You should also ensure that you cannot run out of memory due to having too many recursive calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24427-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24427-127">See Also</span></span>  
 <xref:System.StackOverflowException>  
 [<span data-ttu-id="24427-128">Routine</span><span class="sxs-lookup"><span data-stu-id="24427-128">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="24427-129">Routine Sub</span><span class="sxs-lookup"><span data-stu-id="24427-129">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="24427-130">Routine Function</span><span class="sxs-lookup"><span data-stu-id="24427-130">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="24427-131">Routine Property</span><span class="sxs-lookup"><span data-stu-id="24427-131">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="24427-132">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="24427-132">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="24427-133">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="24427-133">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="24427-134">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="24427-134">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="24427-135">Risoluzione dei problemi relativi alle routine</span><span class="sxs-lookup"><span data-stu-id="24427-135">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)  
 [<span data-ttu-id="24427-136">Strutture di ciclo</span><span class="sxs-lookup"><span data-stu-id="24427-136">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="24427-137">Risoluzione dei problemi relativi ad eccezioni: System.StackOverflowException</span><span class="sxs-lookup"><span data-stu-id="24427-137">Troubleshooting Exceptions: System.StackOverflowException</span></span>](http://msdn.microsoft.com/library/51b71217-c507-4f5b-bc35-0236180d7968)
