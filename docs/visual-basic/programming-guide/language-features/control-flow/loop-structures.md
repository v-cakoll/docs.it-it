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
ms.openlocfilehash: 56165eecce5e73c4e06235dac1691774fb39b794
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58833311"
---
# <a name="loop-structures-visual-basic"></a><span data-ttu-id="250b0-102">Strutture di ciclo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="250b0-102">Loop Structures (Visual Basic)</span></span>
<span data-ttu-id="250b0-103">Strutture di ciclo di Visual Basic consentono di eseguire ripetutamente una o più righe di codice.</span><span class="sxs-lookup"><span data-stu-id="250b0-103">Visual Basic loop structures allow you to run one or more lines of code repetitively.</span></span> <span data-ttu-id="250b0-104">È possibile ripetere le istruzioni in una struttura di ciclo fino a quando non è una condizione `True`, fino a quando una condizione è `False`, un numero di volte oppure una volta per ogni elemento specificato in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="250b0-104">You can repeat the statements in a loop structure until a condition is `True`, until a condition is `False`, a specified number of times, or once for each element in a collection.</span></span>  
  
 <span data-ttu-id="250b0-105">La figura seguente illustra una struttura di ciclo che esegue una serie di istruzioni finché una condizione non è true:</span><span class="sxs-lookup"><span data-stu-id="250b0-105">The following illustration shows a loop structure that runs a set of statements until a condition becomes true:</span></span>  
  
 ![Diagramma di flusso che mostra un Do... Fino al ciclo.](./media/loop-structures/do-until-loop-true-condition.gif)  
  
## <a name="while-loops"></a><span data-ttu-id="250b0-107">Cicli while</span><span class="sxs-lookup"><span data-stu-id="250b0-107">While Loops</span></span>  
 <span data-ttu-id="250b0-108">Il `While`... `End While` costruzione esegue una serie di istruzioni finché la condizione specificata di `While` istruzione è `True`.</span><span class="sxs-lookup"><span data-stu-id="250b0-108">The `While`...`End While` construction runs a set of statements as long as the condition specified in the `While` statement is `True`.</span></span> <span data-ttu-id="250b0-109">Per altre informazioni, vedere [mentre... End While (istruzione)](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span><span class="sxs-lookup"><span data-stu-id="250b0-109">For more information, see [While...End While Statement](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span></span>  
  
## <a name="do-loops"></a><span data-ttu-id="250b0-110">Cicli Do</span><span class="sxs-lookup"><span data-stu-id="250b0-110">Do Loops</span></span>  
 <span data-ttu-id="250b0-111">Il `Do`... `Loop` costruzione consente di testare una condizione all'inizio o fine di una struttura di ciclo.</span><span class="sxs-lookup"><span data-stu-id="250b0-111">The `Do`...`Loop` construction allows you to test a condition at either the beginning or the end of a loop structure.</span></span> <span data-ttu-id="250b0-112">È anche possibile specificare se ripetere il ciclo finché la condizione rimane `True` o finché non diventa `True`.</span><span class="sxs-lookup"><span data-stu-id="250b0-112">You can also specify whether to repeat the loop while the condition remains `True` or until it becomes `True`.</span></span> <span data-ttu-id="250b0-113">Per altre informazioni, vedere [è... Istruzione di ciclo](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="250b0-113">For more information, see [Do...Loop Statement](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="for-loops"></a><span data-ttu-id="250b0-114">Per i cicli</span><span class="sxs-lookup"><span data-stu-id="250b0-114">For Loops</span></span>  
 <span data-ttu-id="250b0-115">Il `For`... `Next` esegue il ciclo di un determinato numero di volte per.</span><span class="sxs-lookup"><span data-stu-id="250b0-115">The `For`...`Next` construction performs the loop a set number of times.</span></span> <span data-ttu-id="250b0-116">Viene utilizzata una variabile di controllo ciclo, detta anche un *contatore*, per tenere traccia delle ripetizioni.</span><span class="sxs-lookup"><span data-stu-id="250b0-116">It uses a loop control variable, also called a *counter*, to keep track of the repetitions.</span></span> <span data-ttu-id="250b0-117">Specificare i valori iniziale e finale per questo contatore, e, facoltativamente, è possibile specificare la quantità di cui aumenta da una ripetizione a quella successiva.</span><span class="sxs-lookup"><span data-stu-id="250b0-117">You specify the starting and ending values for this counter, and you can optionally specify the amount by which it increases from one repetition to the next.</span></span> <span data-ttu-id="250b0-118">Per altre informazioni, vedere [per... Istruzione Next](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="250b0-118">For more information, see [For...Next Statement](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
## <a name="for-each-loops"></a><span data-ttu-id="250b0-119">Cicli For Each</span><span class="sxs-lookup"><span data-stu-id="250b0-119">For Each Loops</span></span>  
 <span data-ttu-id="250b0-120">Il `For Each`... `Next` costruzione esegue una serie di istruzioni una sola volta per ogni elemento in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="250b0-120">The `For Each`...`Next` construction runs a set of statements once for each element in a collection.</span></span> <span data-ttu-id="250b0-121">Si specifica la variabile di controllo, ma non è necessario determinare i valori iniziale e finale per tale.</span><span class="sxs-lookup"><span data-stu-id="250b0-121">You specify the loop control variable, but you do not have to determine starting or ending values for it.</span></span> <span data-ttu-id="250b0-122">Per altre informazioni, vedere [For Each... Istruzione Next](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="250b0-122">For more information, see [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="250b0-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="250b0-123">See also</span></span>

- [<span data-ttu-id="250b0-124">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="250b0-124">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="250b0-125">Strutture decisionali</span><span class="sxs-lookup"><span data-stu-id="250b0-125">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="250b0-126">Altre strutture di controllo</span><span class="sxs-lookup"><span data-stu-id="250b0-126">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="250b0-127">Strutture di controllo annidate</span><span class="sxs-lookup"><span data-stu-id="250b0-127">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
