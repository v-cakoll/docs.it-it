---
title: Cicli (strutture (Visual Basic)) | Documenti di Microsoft
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
- control flow, loops
- For keyword [Visual Basic], loop structures
- loops
- loop structures
- statements [Visual Basic], loop
- Do statement, Do loops
- conditional statements, loop structures
ms.assetid: ecacb09b-a4c9-42be-98b2-a15d368b5db8
caps.latest.revision: 18
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
ms.openlocfilehash: eba728d782bb5a6259467fb48f738f35580049c0
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="loop-structures-visual-basic"></a><span data-ttu-id="8ef42-102">Strutture di ciclo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8ef42-102">Loop Structures (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="8ef42-103">cicli (strutture) consentono di eseguire ripetutamente una o più righe di codice.</span><span class="sxs-lookup"><span data-stu-id="8ef42-103"> loop structures allow you to run one or more lines of code repetitively.</span></span> <span data-ttu-id="8ef42-104">È possibile ripetere le istruzioni in una struttura di ciclo fino a quando non è una condizione `True`, fino a quando una condizione è `False`, un numero di volte o una volta per ogni elemento specificato in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="8ef42-104">You can repeat the statements in a loop structure until a condition is `True`, until a condition is `False`, a specified number of times, or once for each element in a collection.</span></span>  
  
 <span data-ttu-id="8ef42-105">Nella figura seguente viene mostrata una struttura di ciclo che esegue una serie di istruzioni finché una condizione non diventa true.</span><span class="sxs-lookup"><span data-stu-id="8ef42-105">The following illustration shows a loop structure that runs a set of statements until a condition becomes true.</span></span>  
  
 <span data-ttu-id="8ef42-106">![Diagramma di flusso di un ciclo Do... Fino al ciclo](../../../../visual-basic/programming-guide/language-features/control-flow/media/dountilloop.gif "DoUntilLoop")</span><span class="sxs-lookup"><span data-stu-id="8ef42-106">![Flow chart of a Do...Until loop](../../../../visual-basic/programming-guide/language-features/control-flow/media/dountilloop.gif "DoUntilLoop")</span></span>  
<span data-ttu-id="8ef42-107">Esecuzione di un set di istruzioni finché una condizione non diventa true</span><span class="sxs-lookup"><span data-stu-id="8ef42-107">Running a set of statements until a condition becomes true</span></span>  
  
## <a name="while-loops"></a><span data-ttu-id="8ef42-108">Cicli while</span><span class="sxs-lookup"><span data-stu-id="8ef42-108">While Loops</span></span>  
 <span data-ttu-id="8ef42-109">The `While`... `End While` esegue un set di istruzioni finché la condizione specificata nel `While` istruzione `True`.</span><span class="sxs-lookup"><span data-stu-id="8ef42-109">The `While`...`End While` construction runs a set of statements as long as the condition specified in the `While` statement is `True`.</span></span> <span data-ttu-id="8ef42-110">Per ulteriori informazioni, vedere [mentre... Fine istruzione While](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8ef42-110">For more information, see [While...End While Statement](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span></span>  
  
## <a name="do-loops"></a><span data-ttu-id="8ef42-111">Cicli Do</span><span class="sxs-lookup"><span data-stu-id="8ef42-111">Do Loops</span></span>  
 <span data-ttu-id="8ef42-112">The `Do`... `Loop` costruzione consente di verificare una condizione all'inizio o fine di una struttura di ciclo.</span><span class="sxs-lookup"><span data-stu-id="8ef42-112">The `Do`...`Loop` construction allows you to test a condition at either the beginning or the end of a loop structure.</span></span> <span data-ttu-id="8ef42-113">È anche possibile specificare se ripetere il ciclo mentre la condizione rimane `True` o fino a quando non diventa `True`.</span><span class="sxs-lookup"><span data-stu-id="8ef42-113">You can also specify whether to repeat the loop while the condition remains `True` or until it becomes `True`.</span></span> <span data-ttu-id="8ef42-114">Per ulteriori informazioni, vedere [si... Istruzione di ciclo](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8ef42-114">For more information, see [Do...Loop Statement](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="for-loops"></a><span data-ttu-id="8ef42-115">Per i cicli</span><span class="sxs-lookup"><span data-stu-id="8ef42-115">For Loops</span></span>  
 <span data-ttu-id="8ef42-116">The `For`... `Next` esegue il ciclo di un determinato numero di volte per.</span><span class="sxs-lookup"><span data-stu-id="8ef42-116">The `For`...`Next` construction performs the loop a set number of times.</span></span> <span data-ttu-id="8ef42-117">Viene utilizzata una variabile di controllo del ciclo, detta anche un *contatore*, per tenere traccia delle ripetizioni.</span><span class="sxs-lookup"><span data-stu-id="8ef42-117">It uses a loop control variable, also called a *counter*, to keep track of the repetitions.</span></span> <span data-ttu-id="8ef42-118">Specificare i valori iniziale e finale per questo contatore e, facoltativamente, è possibile specificare la quantità di cui aumenta da una ripetizione alla successiva.</span><span class="sxs-lookup"><span data-stu-id="8ef42-118">You specify the starting and ending values for this counter, and you can optionally specify the amount by which it increases from one repetition to the next.</span></span> <span data-ttu-id="8ef42-119">Per ulteriori informazioni, vedere [per... Istruzione successiva](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8ef42-119">For more information, see [For...Next Statement](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
## <a name="for-each-loops"></a><span data-ttu-id="8ef42-120">Cicli For Each</span><span class="sxs-lookup"><span data-stu-id="8ef42-120">For Each Loops</span></span>  
 <span data-ttu-id="8ef42-121">The `For Each`... `Next` esegue un set di istruzioni una volta per ogni elemento in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="8ef42-121">The `For Each`...`Next` construction runs a set of statements once for each element in a collection.</span></span> <span data-ttu-id="8ef42-122">Specificare la variabile di controllo, ma non è necessario determinare i valori iniziale e finale per esso.</span><span class="sxs-lookup"><span data-stu-id="8ef42-122">You specify the loop control variable, but you do not have to determine starting or ending values for it.</span></span> <span data-ttu-id="8ef42-123">Per ulteriori informazioni, vedere [For Each... Istruzione successiva](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8ef42-123">For more information, see [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ef42-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ef42-124">See Also</span></span>  
 <span data-ttu-id="8ef42-125">[Flusso di controllo](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span><span class="sxs-lookup"><span data-stu-id="8ef42-125">[Control Flow](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span></span>  
<span data-ttu-id="8ef42-126"> [Strutture decisionali](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md) </span><span class="sxs-lookup"><span data-stu-id="8ef42-126"> [Decision Structures](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md) </span></span>  
<span data-ttu-id="8ef42-127"> [Altre strutture di controllo](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md) </span><span class="sxs-lookup"><span data-stu-id="8ef42-127"> [Other Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md) </span></span>  
<span data-ttu-id="8ef42-128"> [Strutture di controllo annidate](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)</span><span class="sxs-lookup"><span data-stu-id="8ef42-128"> [Nested Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)</span></span>
