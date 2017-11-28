---
title: Istruzione Continue (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4a47819600a6c1d58f09c2f8ed3443632e9dab68
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="continue-statement-visual-basic"></a>Istruzione Continue (Visual Basic)
Trasferisce il controllo immediatamente all'iterazione successiva di un ciclo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a>Note  
 È possibile trasferire da all'interno di un `Do`, `For`, o `While` ciclo all'iterazione successiva del ciclo. Il controllo passa immediatamente alla verifica della condizione di ciclo, che viene trasferito al `For` o `While` istruzione o il `Do` o `Loop` istruzione che contiene il `Until` o `While` clausola.  
  
 È possibile utilizzare `Continue` in qualsiasi posizione nel ciclo che consente i trasferimenti. Le regole che consentono il trasferimento del controllo sono la stessa utilizzata con la [istruzione GoTo](../../../visual-basic/language-reference/statements/goto-statement.md).  
  
 Ad esempio, se un ciclo è contenuto completamente all'interno di un `Try` blocco, una `Catch` blocco, o un `Finally` blocco, è possibile utilizzare `Continue` per il trasferimento all'esterno del ciclo. Se, invece, il `Try`... `End Try` struttura è contenuta all'interno del ciclo, è possibile utilizzare `Continue` per trasferire il controllo fuori il `Finally` blocco ed è possibile utilizzarla per uscire da un `Try` o `Catch` blocco solo se si trasferiscono completamente fuori il `Try`... `End Try` struttura.  
  
 Se sono presenti cicli annidati dello stesso tipo, ad esempio un `Do` ciclo all'interno di altra `Do` ciclo, un `Continue Do` istruzione passa all'iterazione successiva del ciclo `Do` ciclo che lo contiene. Non è possibile utilizzare `Continue` per passare all'iterazione successiva di un contenitore ciclo dello stesso tipo.  
  
 Se sono presenti cicli annidati di tipi diversi, ad esempio un `Do` ciclo all'interno di un `For` ciclo, è possibile passare all'iterazione successiva del ciclo di entrambi, utilizzando `Continue Do` o `Continue For`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice viene illustrato come utilizzare il `Continue While` istruzione per passare alla colonna successiva di una matrice, se un divisore è zero. Il `Continue While` è all'interno di un `For` ciclo. Passa al `While col < lastcol` istruzione, ovvero l'iterazione successiva del ciclo `While` che contiene il `For` ciclo.  
  
 [!code-vb[VbVbalrStatements#14](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/continue-statement_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [Istruzione For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Istruzione While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
