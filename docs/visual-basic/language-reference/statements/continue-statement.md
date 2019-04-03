---
title: Istruzione Continue (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: 5523be69f2901851c86f6c0263548e3577507ff9
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835385"
---
# <a name="continue-statement-visual-basic"></a>Istruzione Continue (Visual Basic)
Trasferisce il controllo immediatamente all'iterazione successiva di un ciclo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a>Note  
 È possibile trasferire da all'interno di un `Do`, `For`, o `While` ciclo all'iterazione successiva del ciclo. Il controllo passa immediatamente alla verifica della condizione di ciclo, che viene trasferito al `For` o `While` istruzione, o il `Do` o `Loop` istruzione che contiene la `Until` o `While` clausola.  
  
 È possibile usare `Continue` in qualsiasi posizione nel ciclo che consente i trasferimenti. Le regole che consentono il trasferimento del controllo sono le stesse usate con il [istruzione GoTo](../../../visual-basic/language-reference/statements/goto-statement.md).  
  
 Ad esempio, se un ciclo è completamente indipendente all'interno di un `Try` blocco, una `Catch` blocco, o una `Finally` blocco, è possibile usare `Continue` da trasferire all'esterno del ciclo. Se, d'altra parte, il `Try`... `End Try` struttura è contenuta all'interno del ciclo, non è possibile usare `Continue` per trasferire il controllo fuori il `Finally` blocco ed è possibile utilizzare per il trasferimento di una `Try` o `Catch` bloccare solo se si trasferiscono completamente fuori il `Try`... `End Try` struttura.  
  
 Se sono presenti cicli annidati dello stesso tipo, ad esempio un `Do` ciclo all'interno di altra `Do` ciclo, un `Continue Do` istruzione passa all'iterazione successiva del ciclo `Do` ciclo che lo contiene. Non è possibile usare `Continue` da ignorare all'iterazione successiva di un contenitore ciclo dello stesso tipo.  
  
 Se sono presenti cicli annidati di tipi diversi, ad esempio un `Do` ciclo all'interno di un `For` ciclo, è possibile passare all'iterazione successiva del ciclo di entrambi utilizzando `Continue Do` o `Continue For`.  
  
## <a name="example"></a>Esempio  
 Il codice seguente viene illustrato come utilizzare il `Continue While` istruzione per ignorare la successiva colonna di una matrice se il divisore è zero. Il `Continue While` si trova all'interno un `For` ciclo. Viene trasferita l'esecuzione di `While col < lastcol` istruzione, ovvero l'iterazione successiva del ciclo `While` ciclo che contiene il `For` ciclo.  
  
 [!code-vb[VbVbalrStatements#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Istruzione For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Istruzione While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
