---
title: Istruzione Continue
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: fd604b281a590073a5e76398788d7648cadd145c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84382094"
---
# <a name="continue-statement-visual-basic"></a>Istruzione Continue (Visual Basic)
Trasferisce immediatamente il controllo all'iterazione successiva di un ciclo.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a>Osservazioni  
 È possibile trasferire dall'interno di `Do` un `For` ciclo, o `While` all'iterazione successiva del ciclo. Il controllo passa immediatamente al test della condizione del ciclo, equivalente al trasferimento all' `For` istruzione o o `While` all' `Do` `Loop` istruzione o che contiene la `Until` `While` clausola o.  
  
 È possibile usare in `Continue` qualsiasi posizione del ciclo che consente i trasferimenti. Le regole che consentono il trasferimento del controllo sono le stesse dell' [istruzione goto](goto-statement.md).  
  
 Se, ad esempio, un ciclo è interamente contenuto all'interno di un blocco, di `Try` un `Catch` blocco o di un `Finally` blocco, è possibile utilizzare `Continue` per trasferire il ciclo. Se, invece, la `Try` struttura... `End Try` è contenuta all'interno del ciclo, non è possibile utilizzare `Continue` per trasferire il controllo fuori dal `Finally` blocco ed è possibile utilizzarlo per il trasferimento da un `Try` blocco o `Catch` solo se si trasferisce completamente dalla struttura. `Try` . `End Try` ..  
  
 Se sono presenti cicli annidati dello stesso tipo, ad esempio un `Do` ciclo all'interno di un altro `Do` ciclo, un' `Continue Do` istruzione passa all'iterazione successiva del `Do` ciclo più interno che la contiene. Non è possibile usare `Continue` per passare all'iterazione successiva di un ciclo contenitore dello stesso tipo.  
  
 Se sono presenti cicli annidati di tipi diversi, ad esempio un `Do` ciclo all'interno di un `For` ciclo, è possibile passare all'iterazione successiva di uno dei due cicli usando `Continue Do` o `Continue For` .  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene utilizzata l' `Continue While` istruzione per passare alla colonna successiva di una matrice se il divisore è zero. L'oggetto `Continue While` si trova all'interno di un `For` ciclo. Trasferisce all' `While col < lastcol` istruzione, che è l'iterazione successiva del ciclo più interno `While` che contiene il `For` ciclo.  
  
 [!code-vb[VbVbalrStatements#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Do...Loop](do-loop-statement.md)
- [Istruzione For...Next](for-next-statement.md)
- [Istruzione While...End While](while-end-while-statement.md)
- [Istruzione Try...Catch...Finally](try-catch-finally-statement.md)
