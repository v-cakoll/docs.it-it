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
ms.openlocfilehash: 0bb89ac855d65d7677a062346db8665698dbb805
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43514342"
---
# <a name="recursive-procedures-visual-basic"></a><span data-ttu-id="81bd4-102">Routine ricorsive (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81bd4-102">Recursive Procedures (Visual Basic)</span></span>
<span data-ttu-id="81bd4-103">Oggetto *ricorsiva* routine è quella che chiama se stesso.</span><span class="sxs-lookup"><span data-stu-id="81bd4-103">A *recursive* procedure is one that calls itself.</span></span> <span data-ttu-id="81bd4-104">In generale, questo non è il modo più efficace per scrivere il codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="81bd4-104">In general, this is not the most effective way to write Visual Basic code.</span></span>  
  
 <span data-ttu-id="81bd4-105">La procedura seguente usa la ricorsione per la quale calcolare il fattoriale del relativo argomento originale.</span><span class="sxs-lookup"><span data-stu-id="81bd4-105">The following procedure uses recursion to calculate the factorial of its original argument.</span></span>  
  
 [!code-vb[VbVbcnProcedures#51](./codesnippet/VisualBasic/recursive-procedures_1.vb)]  
  
## <a name="considerations-with-recursive-procedures"></a><span data-ttu-id="81bd4-106">Considerazioni sulle routine ricorsive</span><span class="sxs-lookup"><span data-stu-id="81bd4-106">Considerations with Recursive Procedures</span></span>  
 <span data-ttu-id="81bd4-107">**Le condizioni di limitazione**.</span><span class="sxs-lookup"><span data-stu-id="81bd4-107">**Limiting Conditions**.</span></span> <span data-ttu-id="81bd4-108">È necessario progettare una routine ricorsiva da verificare per almeno una condizione che può terminare la ricorsione ed è anche necessario gestire il caso in cui nessun tale condizione viene soddisfatta entro un numero ragionevole di chiamate ricorsive.</span><span class="sxs-lookup"><span data-stu-id="81bd4-108">You must design a recursive procedure to test for at least one condition that can terminate the recursion, and you must also handle the case where no such condition is satisfied within a reasonable number of recursive calls.</span></span> <span data-ttu-id="81bd4-109">Senza almeno una condizione che può essere soddisfatti senza l'esito negativo, la routine esegue un elevato rischio di esecuzione in un ciclo infinito.</span><span class="sxs-lookup"><span data-stu-id="81bd4-109">Without at least one condition that can be met without fail, your procedure runs a high risk of executing in an infinite loop.</span></span>  
  
 <span data-ttu-id="81bd4-110">**Utilizzo memoria**.</span><span class="sxs-lookup"><span data-stu-id="81bd4-110">**Memory Usage**.</span></span> <span data-ttu-id="81bd4-111">L'applicazione dispone di una quantità limitata di spazio per le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="81bd4-111">Your application has a limited amount of space for local variables.</span></span> <span data-ttu-id="81bd4-112">Ogni volta che una routine chiama se stessa, utilizza una quantità di spazio per le altre copie delle variabili locali.</span><span class="sxs-lookup"><span data-stu-id="81bd4-112">Each time a procedure calls itself, it uses more of that space for additional copies of its local variables.</span></span> <span data-ttu-id="81bd4-113">Se questo processo continua per un periodo illimitato, provoca un <xref:System.StackOverflowException> errore.</span><span class="sxs-lookup"><span data-stu-id="81bd4-113">If this process continues indefinitely, it eventually causes a <xref:System.StackOverflowException> error.</span></span>  
  
 <span data-ttu-id="81bd4-114">**L'efficienza**.</span><span class="sxs-lookup"><span data-stu-id="81bd4-114">**Efficiency**.</span></span> <span data-ttu-id="81bd4-115">È quasi sempre possibile sostituire un ciclo di ricorsione.</span><span class="sxs-lookup"><span data-stu-id="81bd4-115">You can almost always substitute a loop for recursion.</span></span> <span data-ttu-id="81bd4-116">Un ciclo non ha l'overhead di passaggio di argomenti, l'inizializzazione ulteriore spazio di archiviazione e la restituzione di valori.</span><span class="sxs-lookup"><span data-stu-id="81bd4-116">A loop does not have the overhead of passing arguments, initializing additional storage, and returning values.</span></span> <span data-ttu-id="81bd4-117">Le prestazioni possono essere molto meglio senza le chiamate ricorsive.</span><span class="sxs-lookup"><span data-stu-id="81bd4-117">Your performance can be much better without recursive calls.</span></span>  
  
 <span data-ttu-id="81bd4-118">**Ricorsione reciproca**.</span><span class="sxs-lookup"><span data-stu-id="81bd4-118">**Mutual Recursion**.</span></span> <span data-ttu-id="81bd4-119">Si noterà probabilmente molto una riduzione delle prestazioni, o anche un ciclo infinito, se due procedure comunicano tra loro.</span><span class="sxs-lookup"><span data-stu-id="81bd4-119">You might observe very poor performance, or even an infinite loop, if two procedures call each other.</span></span> <span data-ttu-id="81bd4-120">Tale progettazione presenta gli stessi problemi come una singola routine ricorsiva, ma può essere difficile rilevare ed eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="81bd4-120">Such a design presents the same problems as a single recursive procedure, but can be harder to detect and debug.</span></span>  
  
 <span data-ttu-id="81bd4-121">**La chiamata con parentesi**.</span><span class="sxs-lookup"><span data-stu-id="81bd4-121">**Calling with Parentheses**.</span></span> <span data-ttu-id="81bd4-122">Quando un `Function` routine chiama se stessa in modo ricorsivo, è necessario seguire il nome della routine tra parentesi, anche se è presente alcun elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="81bd4-122">When a `Function` procedure calls itself recursively, you must follow the procedure name with parentheses, even if there is no argument list.</span></span> <span data-ttu-id="81bd4-123">In caso contrario, il nome della funzione viene eseguito in modo che rappresenti il valore restituito della funzione.</span><span class="sxs-lookup"><span data-stu-id="81bd4-123">Otherwise, the function name is taken as representing the return value of the function.</span></span>  
  
 <span data-ttu-id="81bd4-124">**Test**.</span><span class="sxs-lookup"><span data-stu-id="81bd4-124">**Testing**.</span></span> <span data-ttu-id="81bd4-125">Se si scrive una routine ricorsiva, è consigliabile testare con estrema attenzione per assicurarsi che soddisfi sempre una condizione di limitazione.</span><span class="sxs-lookup"><span data-stu-id="81bd4-125">If you write a recursive procedure, you should test it very carefully to make sure it always meets some limiting condition.</span></span> <span data-ttu-id="81bd4-126">È inoltre necessario assicurarsi che non è possibile eseguire esaurito la memoria a causa di un numero eccessivo di chiamate ricorsive.</span><span class="sxs-lookup"><span data-stu-id="81bd4-126">You should also ensure that you cannot run out of memory due to having too many recursive calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81bd4-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81bd4-127">See Also</span></span>  
 <xref:System.StackOverflowException>  
 [<span data-ttu-id="81bd4-128">Routine</span><span class="sxs-lookup"><span data-stu-id="81bd4-128">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="81bd4-129">Routine Sub</span><span class="sxs-lookup"><span data-stu-id="81bd4-129">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="81bd4-130">Routine Function</span><span class="sxs-lookup"><span data-stu-id="81bd4-130">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="81bd4-131">Routine Property</span><span class="sxs-lookup"><span data-stu-id="81bd4-131">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="81bd4-132">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="81bd4-132">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="81bd4-133">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="81bd4-133">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="81bd4-134">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="81bd4-134">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="81bd4-135">Risoluzione dei problemi relativi alle routine</span><span class="sxs-lookup"><span data-stu-id="81bd4-135">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)  
 [<span data-ttu-id="81bd4-136">Strutture di ciclo</span><span class="sxs-lookup"><span data-stu-id="81bd4-136">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="81bd4-137">Risoluzione dei problemi relativi ad eccezioni: System.StackOverflowException</span><span class="sxs-lookup"><span data-stu-id="81bd4-137">Troubleshooting Exceptions: System.StackOverflowException</span></span>](https://msdn.microsoft.com/library/51b71217-c507-4f5b-bc35-0236180d7968)
