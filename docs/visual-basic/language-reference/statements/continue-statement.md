---
title: Istruzione Continue (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: 9ee5fb19db6eafeb7e4bed12935d0b950d6368d6
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005111"
---
# <a name="continue-statement-visual-basic"></a>Istruzione Continue (Visual Basic)
Trasferisce immediatamente il controllo all'iterazione successiva di un ciclo.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a>Note  
 È possibile trasferire dall'interno di un ciclo `Do`, `For` o `While` alla successiva iterazione del ciclo. Il controllo passa immediatamente al test della condizione del ciclo, che equivale a trasferire l'istruzione `For` o `While` o all'istruzione `Do` o `Loop` che contiene la clausola `Until` o `While`.  
  
 È possibile utilizzare `Continue` in qualsiasi posizione del ciclo che consente i trasferimenti. Le regole che consentono il trasferimento del controllo sono le stesse dell' [istruzione goto](../../../visual-basic/language-reference/statements/goto-statement.md).  
  
 Se, ad esempio, un ciclo è interamente contenuto all'interno di un blocco `Try`, un blocco `Catch` o un blocco `Finally`, è possibile utilizzare `Continue` per trasferire il ciclo. Se, invece, la struttura `Try`... `End Try` è contenuta all'interno del ciclo, non è possibile usare `Continue` per trasferire il controllo dal blocco `Finally` ed è possibile usarlo per trasferire fuori da un blocco `Try` o `Catch` solo se si trasferisce completamente dal @no_ struttura _T-6... `End Try`.  
  
 Se si dispone di cicli annidati dello stesso tipo, ad esempio un ciclo `Do` in un altro ciclo `Do`, un'istruzione `Continue Do` passa alla successiva iterazione del ciclo `Do` più interno che lo contiene. Non è possibile usare `Continue` per passare all'iterazione successiva di un ciclo contenitore dello stesso tipo.  
  
 Se sono presenti cicli annidati di tipi diversi, ad esempio un ciclo `Do` all'interno di un ciclo `For`, è possibile passare all'iterazione successiva di uno dei due cicli usando `Continue Do` o `Continue For`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene utilizzata l'istruzione `Continue While` per passare alla colonna successiva di una matrice se il divisore è zero. Il `Continue While` si trova all'interno di un ciclo `For`. Trasferisce all'istruzione `While col < lastcol`, ovvero l'iterazione successiva del ciclo `While` più interno che contiene il ciclo `For`.  
  
 [!code-vb[VbVbalrStatements#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Istruzione For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Istruzione While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
