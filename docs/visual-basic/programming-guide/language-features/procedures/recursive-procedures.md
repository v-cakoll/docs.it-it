---
title: Routine ricorsive (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], that call themselves
- procedures [Visual Basic], recursive
- procedures [Visual Basic], calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
ms.openlocfilehash: 8ea7741c943ea563fbd0c7649ac0ff85b2f9ebba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650215"
---
# <a name="recursive-procedures-visual-basic"></a><span data-ttu-id="6d988-102">Routine ricorsive (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6d988-102">Recursive Procedures (Visual Basic)</span></span>
<span data-ttu-id="6d988-103">Oggetto *ricorsiva* procedure è una classe che chiama se stessa.</span><span class="sxs-lookup"><span data-stu-id="6d988-103">A *recursive* procedure is one that calls itself.</span></span> <span data-ttu-id="6d988-104">In generale, non il modo più efficace per scrivere il codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="6d988-104">In general, this is not the most effective way to write Visual Basic code.</span></span>  
  
 <span data-ttu-id="6d988-105">La procedura seguente usa la ricorsione per calcolare il fattoriale del relativo argomento originale.</span><span class="sxs-lookup"><span data-stu-id="6d988-105">The following procedure uses recursion to calculate the factorial of its original argument.</span></span>  
  
 [!code-vb[VbVbcnProcedures#51](./codesnippet/VisualBasic/recursive-procedures_1.vb)]  
  
## <a name="considerations-with-recursive-procedures"></a><span data-ttu-id="6d988-106">Considerazioni sulle routine ricorsive</span><span class="sxs-lookup"><span data-stu-id="6d988-106">Considerations with Recursive Procedures</span></span>  
 <span data-ttu-id="6d988-107">**Le condizioni di limitazione**.</span><span class="sxs-lookup"><span data-stu-id="6d988-107">**Limiting Conditions**.</span></span> <span data-ttu-id="6d988-108">È necessario progettare una routine ricorsiva per verificare la presenza di almeno una condizione in grado di terminare la ricorsione e, è necessario gestire anche nel caso in cui tale condizione non viene soddisfatta entro un numero ragionevole di chiamate ricorsive.</span><span class="sxs-lookup"><span data-stu-id="6d988-108">You must design a recursive procedure to test for at least one condition that can terminate the recursion, and you must also handle the case where no such condition is satisfied within a reasonable number of recursive calls.</span></span> <span data-ttu-id="6d988-109">Senza almeno una condizione che può essere soddisfatta senza errori, la stored procedure viene eseguito un rischio elevato dell'esecuzione in un ciclo infinito.</span><span class="sxs-lookup"><span data-stu-id="6d988-109">Without at least one condition that can be met without fail, your procedure runs a high risk of executing in an infinite loop.</span></span>  
  
 <span data-ttu-id="6d988-110">**Utilizzo memoria**.</span><span class="sxs-lookup"><span data-stu-id="6d988-110">**Memory Usage**.</span></span> <span data-ttu-id="6d988-111">L'applicazione dispone di una quantità limitata di spazio per le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="6d988-111">Your application has a limited amount of space for local variables.</span></span> <span data-ttu-id="6d988-112">Ogni volta che una routine chiama se stessa, viene utilizzato più lo spazio per le copie aggiuntive delle variabili locali.</span><span class="sxs-lookup"><span data-stu-id="6d988-112">Each time a procedure calls itself, it uses more of that space for additional copies of its local variables.</span></span> <span data-ttu-id="6d988-113">Se questo processo continua in modo indefinito, provoca un <xref:System.StackOverflowException> errore.</span><span class="sxs-lookup"><span data-stu-id="6d988-113">If this process continues indefinitely, it eventually causes a <xref:System.StackOverflowException> error.</span></span>  
  
 <span data-ttu-id="6d988-114">**L'efficienza**.</span><span class="sxs-lookup"><span data-stu-id="6d988-114">**Efficiency**.</span></span> <span data-ttu-id="6d988-115">È quasi sempre possibile sostituire un ciclo per la ricorsione.</span><span class="sxs-lookup"><span data-stu-id="6d988-115">You can almost always substitute a loop for recursion.</span></span> <span data-ttu-id="6d988-116">L'overhead del passaggio degli argomenti, l'inizializzazione di ulteriore spazio di archiviazione e la restituzione di valori non dispone di un ciclo.</span><span class="sxs-lookup"><span data-stu-id="6d988-116">A loop does not have the overhead of passing arguments, initializing additional storage, and returning values.</span></span> <span data-ttu-id="6d988-117">Le prestazioni migliorano in modo significativo senza chiamate ricorsive.</span><span class="sxs-lookup"><span data-stu-id="6d988-117">Your performance can be much better without recursive calls.</span></span>  
  
 <span data-ttu-id="6d988-118">**Ricorsione reciproca**.</span><span class="sxs-lookup"><span data-stu-id="6d988-118">**Mutual Recursion**.</span></span> <span data-ttu-id="6d988-119">Si noterà probabilmente prestazioni estremamente insufficienti o anche un ciclo infinito se due procedure comunicano tra loro.</span><span class="sxs-lookup"><span data-stu-id="6d988-119">You might observe very poor performance, or even an infinite loop, if two procedures call each other.</span></span> <span data-ttu-id="6d988-120">Tale progettazione presenta gli stessi problemi come una singola routine ricorsiva, ma può essere difficile rilevare ed eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="6d988-120">Such a design presents the same problems as a single recursive procedure, but can be harder to detect and debug.</span></span>  
  
 <span data-ttu-id="6d988-121">**La chiamata con parentesi**.</span><span class="sxs-lookup"><span data-stu-id="6d988-121">**Calling with Parentheses**.</span></span> <span data-ttu-id="6d988-122">Quando un `Function` routine chiama se stessa in modo ricorsivo, è necessario seguire il nome della routine con parentesi, anche se è presente alcun elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="6d988-122">When a `Function` procedure calls itself recursively, you must follow the procedure name with parentheses, even if there is no argument list.</span></span> <span data-ttu-id="6d988-123">In caso contrario, il nome della funzione viene eseguito come rappresenta il valore restituito della funzione.</span><span class="sxs-lookup"><span data-stu-id="6d988-123">Otherwise, the function name is taken as representing the return value of the function.</span></span>  
  
 <span data-ttu-id="6d988-124">**Test**.</span><span class="sxs-lookup"><span data-stu-id="6d988-124">**Testing**.</span></span> <span data-ttu-id="6d988-125">Se si scrive una routine ricorsiva, è necessario eseguirne il test con molta attenzione per assicurarsi che soddisfi sempre alcune condizioni di limitazione.</span><span class="sxs-lookup"><span data-stu-id="6d988-125">If you write a recursive procedure, you should test it very carefully to make sure it always meets some limiting condition.</span></span> <span data-ttu-id="6d988-126">È inoltre necessario assicurarsi che non è possibile eseguire esaurito la memoria a causa di un numero eccessivo di chiamate ricorsive.</span><span class="sxs-lookup"><span data-stu-id="6d988-126">You should also ensure that you cannot run out of memory due to having too many recursive calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d988-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d988-127">See Also</span></span>  
 <xref:System.StackOverflowException>  
 [<span data-ttu-id="6d988-128">Routine</span><span class="sxs-lookup"><span data-stu-id="6d988-128">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="6d988-129">Routine Sub</span><span class="sxs-lookup"><span data-stu-id="6d988-129">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="6d988-130">Routine Function</span><span class="sxs-lookup"><span data-stu-id="6d988-130">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="6d988-131">Routine Property</span><span class="sxs-lookup"><span data-stu-id="6d988-131">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="6d988-132">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="6d988-132">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="6d988-133">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="6d988-133">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="6d988-134">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="6d988-134">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="6d988-135">Risoluzione dei problemi relativi alle routine</span><span class="sxs-lookup"><span data-stu-id="6d988-135">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)  
 [<span data-ttu-id="6d988-136">Strutture di ciclo</span><span class="sxs-lookup"><span data-stu-id="6d988-136">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="6d988-137">Risoluzione dei problemi relativi ad eccezioni: System.StackOverflowException</span><span class="sxs-lookup"><span data-stu-id="6d988-137">Troubleshooting Exceptions: System.StackOverflowException</span></span>](http://msdn.microsoft.com/library/51b71217-c507-4f5b-bc35-0236180d7968)
