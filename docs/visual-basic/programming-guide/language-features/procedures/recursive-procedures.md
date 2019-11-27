---
title: Routine ricorsive
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
ms.openlocfilehash: 646d4e29ed7a0b6367d4b35a7f8641bcf659e616
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352548"
---
# <a name="recursive-procedures-visual-basic"></a><span data-ttu-id="d72fd-102">Routine ricorsive (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d72fd-102">Recursive Procedures (Visual Basic)</span></span>

<span data-ttu-id="d72fd-103">Una routine *ricorsiva* è una procedura che chiama se stessa.</span><span class="sxs-lookup"><span data-stu-id="d72fd-103">A *recursive* procedure is one that calls itself.</span></span> <span data-ttu-id="d72fd-104">In generale, questo non è il modo più efficace per scrivere codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d72fd-104">In general, this is not the most effective way to write Visual Basic code.</span></span>  
  
 <span data-ttu-id="d72fd-105">Nella procedura riportata di seguito viene utilizzata la ricorsione per calcolare il fattoriale dell'argomento originale.</span><span class="sxs-lookup"><span data-stu-id="d72fd-105">The following procedure uses recursion to calculate the factorial of its original argument.</span></span>  
  
 [!code-vb[VbVbcnProcedures#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#51)]  
  
## <a name="considerations-with-recursive-procedures"></a><span data-ttu-id="d72fd-106">Considerazioni sulle procedure ricorsive</span><span class="sxs-lookup"><span data-stu-id="d72fd-106">Considerations with Recursive Procedures</span></span>

 <span data-ttu-id="d72fd-107">**Condizioni di limitazione**.</span><span class="sxs-lookup"><span data-stu-id="d72fd-107">**Limiting Conditions**.</span></span> <span data-ttu-id="d72fd-108">È necessario progettare una procedura ricorsiva per testare almeno una condizione in grado di terminare la ricorsione ed è inoltre necessario gestire il caso in cui la condizione non venga soddisfatta entro un numero ragionevole di chiamate ricorsive.</span><span class="sxs-lookup"><span data-stu-id="d72fd-108">You must design a recursive procedure to test for at least one condition that can terminate the recursion, and you must also handle the case where no such condition is satisfied within a reasonable number of recursive calls.</span></span> <span data-ttu-id="d72fd-109">Senza almeno una condizione che può essere soddisfatta senza esito negativo, la procedura esegue un elevato rischio di esecuzione in un ciclo infinito.</span><span class="sxs-lookup"><span data-stu-id="d72fd-109">Without at least one condition that can be met without fail, your procedure runs a high risk of executing in an infinite loop.</span></span>

 <span data-ttu-id="d72fd-110">**Utilizzo memoria**.</span><span class="sxs-lookup"><span data-stu-id="d72fd-110">**Memory Usage**.</span></span> <span data-ttu-id="d72fd-111">L'applicazione dispone di una quantità limitata di spazio per le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="d72fd-111">Your application has a limited amount of space for local variables.</span></span> <span data-ttu-id="d72fd-112">Ogni volta che una routine chiama se stessa, USA più spazio per le copie aggiuntive delle variabili locali.</span><span class="sxs-lookup"><span data-stu-id="d72fd-112">Each time a procedure calls itself, it uses more of that space for additional copies of its local variables.</span></span> <span data-ttu-id="d72fd-113">Se questo processo continua per un periodo illimitato, causa un errore di <xref:System.StackOverflowException>.</span><span class="sxs-lookup"><span data-stu-id="d72fd-113">If this process continues indefinitely, it eventually causes a <xref:System.StackOverflowException> error.</span></span>

 <span data-ttu-id="d72fd-114">**Efficienza**.</span><span class="sxs-lookup"><span data-stu-id="d72fd-114">**Efficiency**.</span></span> <span data-ttu-id="d72fd-115">È quasi sempre possibile sostituire un ciclo per la ricorsione.</span><span class="sxs-lookup"><span data-stu-id="d72fd-115">You can almost always substitute a loop for recursion.</span></span> <span data-ttu-id="d72fd-116">Un ciclo non ha il sovraccarico del passaggio di argomenti, l'inizializzazione di archiviazione aggiuntiva e la restituzione di valori.</span><span class="sxs-lookup"><span data-stu-id="d72fd-116">A loop does not have the overhead of passing arguments, initializing additional storage, and returning values.</span></span> <span data-ttu-id="d72fd-117">Le prestazioni possono essere molto migliori senza chiamate ricorsive.</span><span class="sxs-lookup"><span data-stu-id="d72fd-117">Your performance can be much better without recursive calls.</span></span>

 <span data-ttu-id="d72fd-118">**Ricorsione reciproca**.</span><span class="sxs-lookup"><span data-stu-id="d72fd-118">**Mutual Recursion**.</span></span> <span data-ttu-id="d72fd-119">Se due procedure si chiamano a vicenda, è possibile che si osservi un numero di prestazioni molto ridotto o anche un ciclo infinito.</span><span class="sxs-lookup"><span data-stu-id="d72fd-119">You might observe very poor performance, or even an infinite loop, if two procedures call each other.</span></span> <span data-ttu-id="d72fd-120">Tale progettazione presenta gli stessi problemi di una singola routine ricorsiva, ma può essere più difficile da rilevare ed eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="d72fd-120">Such a design presents the same problems as a single recursive procedure, but can be harder to detect and debug.</span></span>

 <span data-ttu-id="d72fd-121">**Chiamata con le parentesi**.</span><span class="sxs-lookup"><span data-stu-id="d72fd-121">**Calling with Parentheses**.</span></span> <span data-ttu-id="d72fd-122">Quando una `Function` routine chiama se stessa in modo ricorsivo, è necessario seguire il nome della procedura con le parentesi, anche se non è presente alcun elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="d72fd-122">When a `Function` procedure calls itself recursively, you must follow the procedure name with parentheses, even if there is no argument list.</span></span> <span data-ttu-id="d72fd-123">In caso contrario, il nome della funzione viene considerato come che rappresenta il valore restituito della funzione.</span><span class="sxs-lookup"><span data-stu-id="d72fd-123">Otherwise, the function name is taken as representing the return value of the function.</span></span>

 <span data-ttu-id="d72fd-124">**Test**.</span><span class="sxs-lookup"><span data-stu-id="d72fd-124">**Testing**.</span></span> <span data-ttu-id="d72fd-125">Se si scrive una routine ricorsiva, è consigliabile testarla con molta attenzione per assicurarsi che soddisfi sempre una condizione di limitazione.</span><span class="sxs-lookup"><span data-stu-id="d72fd-125">If you write a recursive procedure, you should test it very carefully to make sure it always meets some limiting condition.</span></span> <span data-ttu-id="d72fd-126">È inoltre necessario assicurarsi che non sia possibile esaurire la memoria a causa di un numero eccessivo di chiamate ricorsive.</span><span class="sxs-lookup"><span data-stu-id="d72fd-126">You should also ensure that you cannot run out of memory due to having too many recursive calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="d72fd-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d72fd-127">See also</span></span>

- <xref:System.StackOverflowException>
- [<span data-ttu-id="d72fd-128">Routine</span><span class="sxs-lookup"><span data-stu-id="d72fd-128">Procedures</span></span>](index.md)
- [<span data-ttu-id="d72fd-129">Routine Sub</span><span class="sxs-lookup"><span data-stu-id="d72fd-129">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="d72fd-130">Routine Function</span><span class="sxs-lookup"><span data-stu-id="d72fd-130">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="d72fd-131">Routine Property</span><span class="sxs-lookup"><span data-stu-id="d72fd-131">Property Procedures</span></span>](property-procedures.md)
- [<span data-ttu-id="d72fd-132">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="d72fd-132">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="d72fd-133">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="d72fd-133">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="d72fd-134">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="d72fd-134">Procedure Overloading</span></span>](procedure-overloading.md)
- [<span data-ttu-id="d72fd-135">Risoluzione dei problemi relativi alle routine</span><span class="sxs-lookup"><span data-stu-id="d72fd-135">Troubleshooting Procedures</span></span>](troubleshooting-procedures.md)
- [<span data-ttu-id="d72fd-136">Strutture di ciclo</span><span class="sxs-lookup"><span data-stu-id="d72fd-136">Loop Structures</span></span>](../control-flow/loop-structures.md)
