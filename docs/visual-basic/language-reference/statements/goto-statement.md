---
title: Istruzione GoTo
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.GoTo
helpviewer_keywords:
- GoTo statement [Visual Basic]
- control flow [Visual Basic], branching
- unconditional branching [Visual Basic]
- branching [Visual Basic]
- branching [Visual Basic], unconditional
- branching [Visual Basic], conditional
- conditional statements [Visual Basic], GoTo statement
- GoTo statement [Visual Basic], syntax
ms.assetid: 313274c2-8ab3-4b9c-9ba3-0fd6798e4f6d
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 22a6315e69cd6c797d462d0835e85bb1dde67dcc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="goto-statement"></a>Istruzione GoTo
Branch in modo non condizionale in una riga specificata in una stored procedure.  
  
## <a name="syntax"></a>Sintassi  
  
```  
GoTo line  
```  
  
## <a name="part"></a>Parte  
 `line`  
 Obbligatorio. Qualsiasi etichetta di riga.  
  
## <a name="remarks"></a>Note  
 Il `GoTo` istruzione di diramazione solo righe della routine in cui è presente. La riga deve avere un'etichetta che una riga `GoTo` può fare riferimento a. Per ulteriori informazioni, vedere [come: etichetta istruzioni](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).  
  
> [!NOTE]
>  `GoTo`istruzioni possono ostacolare la lettura e la gestione del codice. Se possibile, è possibile utilizzare una struttura di controllo. Per ulteriori informazioni, vedere [flusso di controllo](../../../visual-basic/programming-guide/language-features/control-flow/index.md).  
  
 Non è possibile utilizzare un `GoTo` istruzione branch all'esterno di un `For`... `Next`, `For Each`... `Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, `With`... `End With`, o `Using`... `End Using` in un'etichetta all'interno.  
  
## <a name="branching-and-try-constructions"></a>Creazione di rami e costruzioni Try  
 All'interno di un `Try`... `Catch`... `Finally` costruzione, le regole seguenti si applicano a creare un ramo con il `GoTo` istruzione.  
  
|Blocco o area geografica|Branching dall'esterno|Branching all'esterno|  
|---------------------|-------------------------------|-------------------------------|  
|`Try`blocco|Solo da un `Catch` blocco della stessa costruzione <sup>1</sup>|Solo di fuori dell'intera costruzione|  
|`Catch`blocco|Non è consentito|Solo di fuori dell'intera costruzione oppure il `Try` blocco della stessa costruzione <sup>1</sup>|  
|`Finally`blocco|Non è consentito|Non è consentito|  
  
 <sup>1</sup> eventuale `Try`... `Catch`... `Finally` costruzione viene nidificata all'interno di un altro, un `Catch` può creare un ramo in blocco il `Try` blocco al proprio livello di nidificazione, ma non in qualsiasi altro `Try` blocco. Nidificate `Try`... `Catch`... `Finally` costruzione deve essere completamente contenuta in un `Try` o `Catch` blocco di costruzione entro il quale è annidata.  
  
 La figura seguente mostra uno `Try` costruzione annidati all'interno di un altro. Vari rami tra i blocchi delle due costruzioni vengono indicati come validi o non valido.  
  
 ![Diagramma grafico dei rami in costruzioni Try](../../../visual-basic/language-reference/statements/media/trybranching.gif "TryBranching")  
Validi e non validi i rami in costruzioni Try  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `GoTo` istruzione branch etichette di riga in una stored procedure.  
  
 [!code-vb[VbVbalrStatements#31](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/goto-statement_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [Istruzione For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Istruzione For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [Istruzione If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [Istruzione Select...Case](../../../visual-basic/language-reference/statements/select-case-statement.md)  
 [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Istruzione While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [Istruzione With...End With](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
