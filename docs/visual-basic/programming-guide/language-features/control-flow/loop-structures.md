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
ms.openlocfilehash: 3f60e9dc83dc7174e765903be13f2870ea40ce4c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403518"
---
# <a name="loop-structures-visual-basic"></a><span data-ttu-id="c2df9-102">Strutture di ciclo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c2df9-102">Loop Structures (Visual Basic)</span></span>
<span data-ttu-id="c2df9-103">Le strutture del ciclo Visual Basic consentono di eseguire ripetutamente una o più righe di codice.</span><span class="sxs-lookup"><span data-stu-id="c2df9-103">Visual Basic loop structures allow you to run one or more lines of code repetitively.</span></span> <span data-ttu-id="c2df9-104">È possibile ripetere le istruzioni in una struttura di ciclo fino a quando una condizione non è, fino a una `True` condizione `False` , un numero specificato di volte o una volta per ogni elemento di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="c2df9-104">You can repeat the statements in a loop structure until a condition is `True`, until a condition is `False`, a specified number of times, or once for each element in a collection.</span></span>  
  
 <span data-ttu-id="c2df9-105">Nella figura seguente è illustrata una struttura di ciclo che esegue un set di istruzioni fino a quando non diventa true una condizione:</span><span class="sxs-lookup"><span data-stu-id="c2df9-105">The following illustration shows a loop structure that runs a set of statements until a condition becomes true:</span></span>  
  
 ![Diagramma di flusso che mostra un... Ciclo until.](./media/loop-structures/do-until-loop-true-condition.gif)  
  
## <a name="while-loops"></a><span data-ttu-id="c2df9-107">Cicli while</span><span class="sxs-lookup"><span data-stu-id="c2df9-107">While Loops</span></span>  
 <span data-ttu-id="c2df9-108">La `While` costruzione... `End While` esegue un set di istruzioni finché la condizione specificata nell' `While` istruzione è `True` .</span><span class="sxs-lookup"><span data-stu-id="c2df9-108">The `While`...`End While` construction runs a set of statements as long as the condition specified in the `While` statement is `True`.</span></span> <span data-ttu-id="c2df9-109">Per ulteriori informazioni, vedere [while... End While (istruzione](../../../language-reference/statements/while-end-while-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="c2df9-109">For more information, see [While...End While Statement](../../../language-reference/statements/while-end-while-statement.md).</span></span>  
  
## <a name="do-loops"></a><span data-ttu-id="c2df9-110">Cicli Do</span><span class="sxs-lookup"><span data-stu-id="c2df9-110">Do Loops</span></span>  
 <span data-ttu-id="c2df9-111">La `Do` costruzione... `Loop` consente di testare una condizione all'inizio o alla fine di una struttura del ciclo.</span><span class="sxs-lookup"><span data-stu-id="c2df9-111">The `Do`...`Loop` construction allows you to test a condition at either the beginning or the end of a loop structure.</span></span> <span data-ttu-id="c2df9-112">È inoltre possibile specificare se ripetere il ciclo mentre la condizione rimane `True` o finché non diventa `True` .</span><span class="sxs-lookup"><span data-stu-id="c2df9-112">You can also specify whether to repeat the loop while the condition remains `True` or until it becomes `True`.</span></span> <span data-ttu-id="c2df9-113">Per ulteriori informazioni, vedere [... Istruzione Loop](../../../language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c2df9-113">For more information, see [Do...Loop Statement](../../../language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="for-loops"></a><span data-ttu-id="c2df9-114">Cicli for</span><span class="sxs-lookup"><span data-stu-id="c2df9-114">For Loops</span></span>  
 <span data-ttu-id="c2df9-115">La `For` costruzione... `Next` esegue il ciclo un numero impostato di volte.</span><span class="sxs-lookup"><span data-stu-id="c2df9-115">The `For`...`Next` construction performs the loop a set number of times.</span></span> <span data-ttu-id="c2df9-116">Usa una variabile di controllo del ciclo, denominata anche *contatore*, per tenere traccia delle ripetizioni.</span><span class="sxs-lookup"><span data-stu-id="c2df9-116">It uses a loop control variable, also called a *counter*, to keep track of the repetitions.</span></span> <span data-ttu-id="c2df9-117">Si specificano i valori iniziale e finale per questo contatore ed è possibile specificare facoltativamente la quantità in base alla quale aumenta da una ripetizione a quella successiva.</span><span class="sxs-lookup"><span data-stu-id="c2df9-117">You specify the starting and ending values for this counter, and you can optionally specify the amount by which it increases from one repetition to the next.</span></span> <span data-ttu-id="c2df9-118">Per ulteriori informazioni, vedere [per... Istruzione successiva](../../../language-reference/statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c2df9-118">For more information, see [For...Next Statement](../../../language-reference/statements/for-next-statement.md).</span></span>  
  
## <a name="for-each-loops"></a><span data-ttu-id="c2df9-119">Cicli for each</span><span class="sxs-lookup"><span data-stu-id="c2df9-119">For Each Loops</span></span>  
 <span data-ttu-id="c2df9-120">La `For Each` costruzione... `Next` esegue un set di istruzioni una volta per ogni elemento di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="c2df9-120">The `For Each`...`Next` construction runs a set of statements once for each element in a collection.</span></span> <span data-ttu-id="c2df9-121">È possibile specificare la variabile di controllo del ciclo, ma non è necessario determinare i valori iniziali o finali.</span><span class="sxs-lookup"><span data-stu-id="c2df9-121">You specify the loop control variable, but you do not have to determine starting or ending values for it.</span></span> <span data-ttu-id="c2df9-122">Per ulteriori informazioni, vedere [for each... Istruzione successiva](../../../language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c2df9-122">For more information, see [For Each...Next Statement](../../../language-reference/statements/for-each-next-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2df9-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2df9-123">See also</span></span>

- [<span data-ttu-id="c2df9-124">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="c2df9-124">Control Flow</span></span>](index.md)
- [<span data-ttu-id="c2df9-125">Strutture decisionali</span><span class="sxs-lookup"><span data-stu-id="c2df9-125">Decision Structures</span></span>](decision-structures.md)
- [<span data-ttu-id="c2df9-126">Altre strutture di controllo</span><span class="sxs-lookup"><span data-stu-id="c2df9-126">Other Control Structures</span></span>](other-control-structures.md)
- [<span data-ttu-id="c2df9-127">Strutture di controllo annidate</span><span class="sxs-lookup"><span data-stu-id="c2df9-127">Nested Control Structures</span></span>](nested-control-structures.md)
