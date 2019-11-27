---
title: Istruzione Continue
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: 20140cafb68c7e5518bf3d5fa80e56ca1c1de2c6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354116"
---
# <a name="continue-statement-visual-basic"></a>Istruzione Continue (Visual Basic)
Trasferisce immediatamente il controllo all'iterazione successiva di un ciclo.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a>Note  
 È possibile trasferire dall'interno di un ciclo di `Do`, `For`o `While` alla successiva iterazione del ciclo. Il controllo passa immediatamente al test della condizione del ciclo, che equivale a trasferire all'istruzione `For` o `While` o all'istruzione `Do` o `Loop` che contiene la clausola `Until` o `While`.  
  
 È possibile utilizzare `Continue` in qualsiasi posizione del ciclo che consente i trasferimenti. Le regole che consentono il trasferimento del controllo sono le stesse dell' [istruzione goto](../../../visual-basic/language-reference/statements/goto-statement.md).  
  
 Se, ad esempio, un ciclo è interamente contenuto all'interno di un blocco di `Try`, un blocco di `Catch` o un blocco `Finally`, è possibile utilizzare `Continue` per trasferire il ciclo. Se, d'altra parte, la struttura del `Try`...`End Try` è contenuta all'interno del ciclo, non è possibile utilizzare `Continue` per trasferire il controllo dal blocco `Finally` ed è possibile utilizzarlo per trasferire fuori da un blocco `Try` o `Catch` solo se si trasferisce completamente dalla struttura `Try`...`End Try`.  
  
 Se sono presenti cicli annidati dello stesso tipo, ad esempio un ciclo di `Do` all'interno di un altro ciclo `Do`, un'istruzione `Continue Do` passa alla successiva iterazione del ciclo di `Do` più interno che lo contiene. Non è possibile usare `Continue` per passare all'iterazione successiva di un ciclo contenitore dello stesso tipo.  
  
 Se sono presenti cicli annidati di tipi diversi, ad esempio un ciclo di `Do` all'interno di un ciclo `For`, è possibile passare all'iterazione successiva di uno dei due cicli usando `Continue Do` o `Continue For`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene usata l'istruzione `Continue While` per passare alla colonna successiva di una matrice se il divisore è zero. Il `Continue While` si trova all'interno di un ciclo di `For`. Trasferisce all'istruzione `While col < lastcol`, ovvero l'iterazione successiva del ciclo di `While` più interno che contiene il ciclo di `For`.  
  
 [!code-vb[VbVbalrStatements#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Do...Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Istruzione For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Istruzione While...End While](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Istruzione Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
