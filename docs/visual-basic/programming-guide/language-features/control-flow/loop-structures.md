---
title: Strutture di ciclo
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
ms.openlocfilehash: 0a75205a7d52c332094d624d082e5db3e89447f5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353921"
---
# <a name="loop-structures-visual-basic"></a><span data-ttu-id="0535e-102">Strutture di ciclo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0535e-102">Loop Structures (Visual Basic)</span></span>
<span data-ttu-id="0535e-103">Le strutture del ciclo Visual Basic consentono di eseguire ripetutamente una o più righe di codice.</span><span class="sxs-lookup"><span data-stu-id="0535e-103">Visual Basic loop structures allow you to run one or more lines of code repetitively.</span></span> <span data-ttu-id="0535e-104">È possibile ripetere le istruzioni in una struttura di ciclo fino a quando non viene `True`una condizione, fino a quando non viene `False`una condizione, un numero specificato di volte o una volta per ogni elemento di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="0535e-104">You can repeat the statements in a loop structure until a condition is `True`, until a condition is `False`, a specified number of times, or once for each element in a collection.</span></span>  
  
 <span data-ttu-id="0535e-105">Nella figura seguente è illustrata una struttura di ciclo che esegue un set di istruzioni fino a quando non diventa true una condizione:</span><span class="sxs-lookup"><span data-stu-id="0535e-105">The following illustration shows a loop structure that runs a set of statements until a condition becomes true:</span></span>  
  
 ![Diagramma di flusso che mostra un... Ciclo until.](./media/loop-structures/do-until-loop-true-condition.gif)  
  
## <a name="while-loops"></a><span data-ttu-id="0535e-107">Cicli while</span><span class="sxs-lookup"><span data-stu-id="0535e-107">While Loops</span></span>  
 <span data-ttu-id="0535e-108">La costruzione `While`...`End While` esegue un set di istruzioni finché la condizione specificata nell'istruzione `While` è `True`.</span><span class="sxs-lookup"><span data-stu-id="0535e-108">The `While`...`End While` construction runs a set of statements as long as the condition specified in the `While` statement is `True`.</span></span> <span data-ttu-id="0535e-109">Per ulteriori informazioni, vedere [while... End While (istruzione](../../../../visual-basic/language-reference/statements/while-end-while-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="0535e-109">For more information, see [While...End While Statement](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span></span>  
  
## <a name="do-loops"></a><span data-ttu-id="0535e-110">Cicli Do</span><span class="sxs-lookup"><span data-stu-id="0535e-110">Do Loops</span></span>  
 <span data-ttu-id="0535e-111">La costruzione `Do`...`Loop` consente di testare una condizione all'inizio o alla fine di una struttura del ciclo.</span><span class="sxs-lookup"><span data-stu-id="0535e-111">The `Do`...`Loop` construction allows you to test a condition at either the beginning or the end of a loop structure.</span></span> <span data-ttu-id="0535e-112">È inoltre possibile specificare se ripetere il ciclo mentre la condizione rimane `True` o fino a quando non diventa `True`.</span><span class="sxs-lookup"><span data-stu-id="0535e-112">You can also specify whether to repeat the loop while the condition remains `True` or until it becomes `True`.</span></span> <span data-ttu-id="0535e-113">Per ulteriori informazioni, vedere [... Istruzione Loop](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0535e-113">For more information, see [Do...Loop Statement](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="for-loops"></a><span data-ttu-id="0535e-114">Cicli for</span><span class="sxs-lookup"><span data-stu-id="0535e-114">For Loops</span></span>  
 <span data-ttu-id="0535e-115">La costruzione del `For`...`Next` esegue il ciclo per un numero di volte definito.</span><span class="sxs-lookup"><span data-stu-id="0535e-115">The `For`...`Next` construction performs the loop a set number of times.</span></span> <span data-ttu-id="0535e-116">Usa una variabile di controllo del ciclo, denominata anche *contatore*, per tenere traccia delle ripetizioni.</span><span class="sxs-lookup"><span data-stu-id="0535e-116">It uses a loop control variable, also called a *counter*, to keep track of the repetitions.</span></span> <span data-ttu-id="0535e-117">Si specificano i valori iniziale e finale per questo contatore ed è possibile specificare facoltativamente la quantità in base alla quale aumenta da una ripetizione a quella successiva.</span><span class="sxs-lookup"><span data-stu-id="0535e-117">You specify the starting and ending values for this counter, and you can optionally specify the amount by which it increases from one repetition to the next.</span></span> <span data-ttu-id="0535e-118">Per ulteriori informazioni, vedere [per... Istruzione successiva](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0535e-118">For more information, see [For...Next Statement](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
## <a name="for-each-loops"></a><span data-ttu-id="0535e-119">Cicli for each</span><span class="sxs-lookup"><span data-stu-id="0535e-119">For Each Loops</span></span>  
 <span data-ttu-id="0535e-120">La costruzione `For Each`...`Next` esegue un set di istruzioni una volta per ogni elemento di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="0535e-120">The `For Each`...`Next` construction runs a set of statements once for each element in a collection.</span></span> <span data-ttu-id="0535e-121">È possibile specificare la variabile di controllo del ciclo, ma non è necessario determinare i valori iniziali o finali.</span><span class="sxs-lookup"><span data-stu-id="0535e-121">You specify the loop control variable, but you do not have to determine starting or ending values for it.</span></span> <span data-ttu-id="0535e-122">Per ulteriori informazioni, vedere [for each... Istruzione successiva](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0535e-122">For more information, see [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0535e-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0535e-123">See also</span></span>

- [<span data-ttu-id="0535e-124">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="0535e-124">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="0535e-125">Strutture decisionali</span><span class="sxs-lookup"><span data-stu-id="0535e-125">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="0535e-126">Altre strutture di controllo</span><span class="sxs-lookup"><span data-stu-id="0535e-126">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="0535e-127">Strutture di controllo annidate</span><span class="sxs-lookup"><span data-stu-id="0535e-127">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
