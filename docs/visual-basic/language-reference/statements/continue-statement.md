---
title: Istruzione Continue (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: eb8596c43bf6232eec4bcb844e6202c5de373404
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
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
