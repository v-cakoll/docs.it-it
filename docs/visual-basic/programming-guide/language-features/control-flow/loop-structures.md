---
title: Strutture di ciclo (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- control flow [Visual Basic], loops
- For keyword [Visual Basic], loop structures
- loops
- loop structures [Visual Basic]
- statements [Visual Basic], loop
- Do statement [Visual Basic], Do loops
- conditional statements [Visual Basic], loop structures
ms.assetid: ecacb09b-a4c9-42be-98b2-a15d368b5db8
ms.openlocfilehash: 8138609f06d82b53ef5b5afb480e8609461ffc33
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647891"
---
# <a name="loop-structures-visual-basic"></a><span data-ttu-id="f1662-102">Strutture di ciclo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f1662-102">Loop Structures (Visual Basic)</span></span>
<span data-ttu-id="f1662-103">Visual Basic cicli (strutture) consentono di eseguire ripetutamente una o più righe di codice.</span><span class="sxs-lookup"><span data-stu-id="f1662-103">Visual Basic loop structures allow you to run one or more lines of code repetitively.</span></span> <span data-ttu-id="f1662-104">È possibile ripetere le istruzioni in una struttura di ciclo finché una condizione è `True`, fino a quando non è una condizione `False`, un numero di volte o una volta per ogni elemento specificato in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="f1662-104">You can repeat the statements in a loop structure until a condition is `True`, until a condition is `False`, a specified number of times, or once for each element in a collection.</span></span>  
  
 <span data-ttu-id="f1662-105">Nella figura seguente mostra una struttura di ciclo che esegue una serie di istruzioni finché una condizione non diventa true.</span><span class="sxs-lookup"><span data-stu-id="f1662-105">The following illustration shows a loop structure that runs a set of statements until a condition becomes true.</span></span>  
  
 <span data-ttu-id="f1662-106">![Diagramma di flusso di un ciclo Do... Fino al ciclo](../../../../visual-basic/programming-guide/language-features/control-flow/media/dountilloop.gif "DoUntilLoop")</span><span class="sxs-lookup"><span data-stu-id="f1662-106">![Flow chart of a Do...Until loop](../../../../visual-basic/programming-guide/language-features/control-flow/media/dountilloop.gif "DoUntilLoop")</span></span>  
<span data-ttu-id="f1662-107">Esecuzione di un set di istruzioni finché una condizione non diventa true</span><span class="sxs-lookup"><span data-stu-id="f1662-107">Running a set of statements until a condition becomes true</span></span>  
  
## <a name="while-loops"></a><span data-ttu-id="f1662-108">Cicli while</span><span class="sxs-lookup"><span data-stu-id="f1662-108">While Loops</span></span>  
 <span data-ttu-id="f1662-109">Il `While`... `End While` esegue un set di istruzioni fino a quando la condizione specificata nel `While` istruzione `True`.</span><span class="sxs-lookup"><span data-stu-id="f1662-109">The `While`...`End While` construction runs a set of statements as long as the condition specified in the `While` statement is `True`.</span></span> <span data-ttu-id="f1662-110">Per ulteriori informazioni, vedere [mentre... End While (istruzione)](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f1662-110">For more information, see [While...End While Statement](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span></span>  
  
## <a name="do-loops"></a><span data-ttu-id="f1662-111">Cicli Do</span><span class="sxs-lookup"><span data-stu-id="f1662-111">Do Loops</span></span>  
 <span data-ttu-id="f1662-112">Il `Do`... `Loop` costruzione consente di testare una condizione all'inizio o fine di una struttura di ciclo.</span><span class="sxs-lookup"><span data-stu-id="f1662-112">The `Do`...`Loop` construction allows you to test a condition at either the beginning or the end of a loop structure.</span></span> <span data-ttu-id="f1662-113">È anche possibile specificare se ripetere il ciclo mentre la condizione rimane `True` o finché diventa `True`.</span><span class="sxs-lookup"><span data-stu-id="f1662-113">You can also specify whether to repeat the loop while the condition remains `True` or until it becomes `True`.</span></span> <span data-ttu-id="f1662-114">Per ulteriori informazioni, vedere [si... Istruzione di ciclo](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f1662-114">For more information, see [Do...Loop Statement](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="for-loops"></a><span data-ttu-id="f1662-115">Per i cicli</span><span class="sxs-lookup"><span data-stu-id="f1662-115">For Loops</span></span>  
 <span data-ttu-id="f1662-116">Il `For`... `Next` esegue il ciclo di un determinato numero di volte per.</span><span class="sxs-lookup"><span data-stu-id="f1662-116">The `For`...`Next` construction performs the loop a set number of times.</span></span> <span data-ttu-id="f1662-117">Viene utilizzata una variabile di controllo del ciclo, detta anche un *contatore*, per tenere traccia delle ripetizioni.</span><span class="sxs-lookup"><span data-stu-id="f1662-117">It uses a loop control variable, also called a *counter*, to keep track of the repetitions.</span></span> <span data-ttu-id="f1662-118">Specificare i valori iniziale e finale per questo contatore e, facoltativamente, è possibile specificare la quantità di cui aumenta da una ripetizione al successivo.</span><span class="sxs-lookup"><span data-stu-id="f1662-118">You specify the starting and ending values for this counter, and you can optionally specify the amount by which it increases from one repetition to the next.</span></span> <span data-ttu-id="f1662-119">Per ulteriori informazioni, vedere [per... Istruzione successiva](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f1662-119">For more information, see [For...Next Statement](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
## <a name="for-each-loops"></a><span data-ttu-id="f1662-120">Cicli For Each</span><span class="sxs-lookup"><span data-stu-id="f1662-120">For Each Loops</span></span>  
 <span data-ttu-id="f1662-121">Il `For Each`... `Next` esegue un set di istruzioni una volta per ogni elemento in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="f1662-121">The `For Each`...`Next` construction runs a set of statements once for each element in a collection.</span></span> <span data-ttu-id="f1662-122">Specificare la variabile di controllo, ma non è necessario determinare i valori iniziale e finale per tale.</span><span class="sxs-lookup"><span data-stu-id="f1662-122">You specify the loop control variable, but you do not have to determine starting or ending values for it.</span></span> <span data-ttu-id="f1662-123">Per ulteriori informazioni, vedere [For Each... Istruzione successiva](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f1662-123">For more information, see [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1662-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1662-124">See Also</span></span>  
 [<span data-ttu-id="f1662-125">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="f1662-125">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [<span data-ttu-id="f1662-126">Strutture decisionali</span><span class="sxs-lookup"><span data-stu-id="f1662-126">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="f1662-127">Altre strutture di controllo</span><span class="sxs-lookup"><span data-stu-id="f1662-127">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)  
 [<span data-ttu-id="f1662-128">Strutture di controllo annidate</span><span class="sxs-lookup"><span data-stu-id="f1662-128">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
