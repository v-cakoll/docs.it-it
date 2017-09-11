---
title: Routine ricorsive (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, procedures
- procedures, that call themselves
- procedures, recursive
- procedures, calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 5e4838bb14125dcfd27798acf0c196f351ba5b90
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="recursive-procedures-visual-basic"></a><span data-ttu-id="85b79-102">Routine ricorsive (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85b79-102">Recursive Procedures (Visual Basic)</span></span>
<span data-ttu-id="85b79-103">Oggetto *ricorsiva* procedura è quella che chiama se stesso.</span><span class="sxs-lookup"><span data-stu-id="85b79-103">A *recursive* procedure is one that calls itself.</span></span> <span data-ttu-id="85b79-104">In generale, questo non è il modo più efficace per scrivere [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] codice.</span><span class="sxs-lookup"><span data-stu-id="85b79-104">In general, this is not the most effective way to write [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] code.</span></span>  
  
 <span data-ttu-id="85b79-105">La procedura seguente utilizza la ricorsione per calcolare il fattoriale del relativo argomento originale.</span><span class="sxs-lookup"><span data-stu-id="85b79-105">The following procedure uses recursion to calculate the factorial of its original argument.</span></span>  
  
 <span data-ttu-id="85b79-106">[!code-vb[51 VbVbcnProcedures](./codesnippet/VisualBasic/recursive-procedures_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="85b79-106">[!code-vb[VbVbcnProcedures#51](./codesnippet/VisualBasic/recursive-procedures_1.vb)]</span></span>  
  
## <a name="considerations-with-recursive-procedures"></a><span data-ttu-id="85b79-107">Considerazioni sulle routine ricorsive</span><span class="sxs-lookup"><span data-stu-id="85b79-107">Considerations with Recursive Procedures</span></span>  
 <span data-ttu-id="85b79-108">**Le condizioni di limitazione**.</span><span class="sxs-lookup"><span data-stu-id="85b79-108">**Limiting Conditions**.</span></span> <span data-ttu-id="85b79-109">È necessario progettare una routine ricorsiva per verificare se almeno una condizione in grado di terminare la ricorsione ed è necessario gestire anche nel caso in cui tale condizione non viene soddisfatta entro un numero ragionevole di chiamate ricorsive.</span><span class="sxs-lookup"><span data-stu-id="85b79-109">You must design a recursive procedure to test for at least one condition that can terminate the recursion, and you must also handle the case where no such condition is satisfied within a reasonable number of recursive calls.</span></span> <span data-ttu-id="85b79-110">Senza almeno una condizione che può essere soddisfatta senza errori, la routine esegue un elevato rischio di esecuzione in un ciclo infinito.</span><span class="sxs-lookup"><span data-stu-id="85b79-110">Without at least one condition that can be met without fail, your procedure runs a high risk of executing in an infinite loop.</span></span>  
  
 <span data-ttu-id="85b79-111">**Utilizzo della memoria**.</span><span class="sxs-lookup"><span data-stu-id="85b79-111">**Memory Usage**.</span></span> <span data-ttu-id="85b79-112">L'applicazione dispone di una quantità limitata di spazio per le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="85b79-112">Your application has a limited amount of space for local variables.</span></span> <span data-ttu-id="85b79-113">Ogni volta che una routine chiama se stessa, utilizza una quantità di spazio per le copie aggiuntive delle variabili locali.</span><span class="sxs-lookup"><span data-stu-id="85b79-113">Each time a procedure calls itself, it uses more of that space for additional copies of its local variables.</span></span> <span data-ttu-id="85b79-114">Se questo processo continua in modo indefinito, provoca un <xref:System.StackOverflowException>errore.</xref:System.StackOverflowException></span><span class="sxs-lookup"><span data-stu-id="85b79-114">If this process continues indefinitely, it eventually causes a <xref:System.StackOverflowException> error.</span></span>  
  
 <span data-ttu-id="85b79-115">**Efficienza**.</span><span class="sxs-lookup"><span data-stu-id="85b79-115">**Efficiency**.</span></span> <span data-ttu-id="85b79-116">È quasi sempre possibile sostituire un ciclo per la ricorsione.</span><span class="sxs-lookup"><span data-stu-id="85b79-116">You can almost always substitute a loop for recursion.</span></span> <span data-ttu-id="85b79-117">Un ciclo non hanno il sovraccarico del passaggio di argomenti, l'inizializzazione di ulteriore spazio di archiviazione e la restituzione di valori.</span><span class="sxs-lookup"><span data-stu-id="85b79-117">A loop does not have the overhead of passing arguments, initializing additional storage, and returning values.</span></span> <span data-ttu-id="85b79-118">Le prestazioni migliorano in modo significativo senza chiamate ricorsive.</span><span class="sxs-lookup"><span data-stu-id="85b79-118">Your performance can be much better without recursive calls.</span></span>  
  
 <span data-ttu-id="85b79-119">**Ricorsione reciproca**.</span><span class="sxs-lookup"><span data-stu-id="85b79-119">**Mutual Recursion**.</span></span> <span data-ttu-id="85b79-120">È possibile osservare molto scarse prestazioni, o anche un ciclo infinito, se due procedure comunicano tra loro.</span><span class="sxs-lookup"><span data-stu-id="85b79-120">You might observe very poor performance, or even an infinite loop, if two procedures call each other.</span></span> <span data-ttu-id="85b79-121">Tale progettazione presenta gli stessi problemi come una singola routine ricorsiva, ma può essere difficile rilevare ed eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="85b79-121">Such a design presents the same problems as a single recursive procedure, but can be harder to detect and debug.</span></span>  
  
 <span data-ttu-id="85b79-122">**La chiamata con parentesi**.</span><span class="sxs-lookup"><span data-stu-id="85b79-122">**Calling with Parentheses**.</span></span> <span data-ttu-id="85b79-123">Quando un `Function` routine chiama se stessa in modo ricorsivo, è necessario seguire il nome della routine tra parentesi, anche se non esiste alcun elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="85b79-123">When a `Function` procedure calls itself recursively, you must follow the procedure name with parentheses, even if there is no argument list.</span></span> <span data-ttu-id="85b79-124">In caso contrario, il nome della funzione viene eseguito come che rappresenta il valore restituito della funzione.</span><span class="sxs-lookup"><span data-stu-id="85b79-124">Otherwise, the function name is taken as representing the return value of the function.</span></span>  
  
 <span data-ttu-id="85b79-125">**Test**.</span><span class="sxs-lookup"><span data-stu-id="85b79-125">**Testing**.</span></span> <span data-ttu-id="85b79-126">Se si scrive una routine ricorsiva, è necessario eseguirne il test con molta attenzione per assicurarsi che soddisfi sempre alcune condizioni di limitazione.</span><span class="sxs-lookup"><span data-stu-id="85b79-126">If you write a recursive procedure, you should test it very carefully to make sure it always meets some limiting condition.</span></span> <span data-ttu-id="85b79-127">È inoltre necessario assicurarsi che non è possibile eseguire esaurito la memoria a causa di un numero eccessivo di chiamate ricorsive.</span><span class="sxs-lookup"><span data-stu-id="85b79-127">You should also ensure that you cannot run out of memory due to having too many recursive calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85b79-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85b79-128">See Also</span></span>  
 <span data-ttu-id="85b79-129"><xref:System.StackOverflowException></xref:System.StackOverflowException></span><span class="sxs-lookup"><span data-stu-id="85b79-129"><xref:System.StackOverflowException></span></span>   
<span data-ttu-id="85b79-130"> [Procedure](./index.md) </span><span class="sxs-lookup"><span data-stu-id="85b79-130"> [Procedures](./index.md) </span></span>  
<span data-ttu-id="85b79-131"> [Sub (routine)](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="85b79-131"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="85b79-132"> [Routine di funzione](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="85b79-132"> [Function Procedures](./function-procedures.md) </span></span>  
<span data-ttu-id="85b79-133"> [Proprietà (routine)](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="85b79-133"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="85b79-134"> [Routine di operatore](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="85b79-134"> [Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="85b79-135"> [Gli argomenti e parametri di routine](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="85b79-135"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="85b79-136"> [Overload di routine](./procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="85b79-136"> [Procedure Overloading](./procedure-overloading.md) </span></span>  
<span data-ttu-id="85b79-137"> [Le procedure di risoluzione](./troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="85b79-137"> [Troubleshooting Procedures](./troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="85b79-138"> [Cicli (strutture)](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span><span class="sxs-lookup"><span data-stu-id="85b79-138"> [Loop Structures](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span></span>  
<span data-ttu-id="85b79-139"> [Risoluzione dei problemi relativi ad eccezioni: System.StackOverflowException](http://msdn.microsoft.com/library/51b71217-c507-4f5b-bc35-0236180d7968)</span><span class="sxs-lookup"><span data-stu-id="85b79-139"> [Troubleshooting Exceptions: System.StackOverflowException](http://msdn.microsoft.com/library/51b71217-c507-4f5b-bc35-0236180d7968)</span></span>
