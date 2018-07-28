---
title: Istruzione GoTo (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: adb7668b6a818b2042a38f9458685a6f93085dc8
ms.sourcegitcommit: 869b5832b667915ac4a5dd8c86b1109ed26b6c08
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/28/2018
ms.locfileid: "39332987"
---
# <a name="goto-statement"></a>Istruzione GoTo
Rami in modo incondizionato a una determinata riga in una procedura.  
  
## <a name="syntax"></a>Sintassi  
  
```  
GoTo line  
```  
  
## <a name="part"></a>Parte  
 `line`  
 Obbligatorio. Qualsiasi etichetta di riga.  
  
## <a name="remarks"></a>Note  
 Il `GoTo` istruzione può creare rami solo righe della routine in cui è presente. La riga deve avere una riga di etichetta che `GoTo` farvi riferimento. Per altre informazioni, vedere [procedura: etichetta istruzioni](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).  
  
> [!NOTE]
>  `GoTo` le istruzioni possono ostacolare la lettura e la gestione del codice. Se possibile, usare invece una struttura di controllo. Per altre informazioni, vedere [flusso di controllo](../../../visual-basic/programming-guide/language-features/control-flow/index.md).  
  
 Non è possibile usare una `GoTo` branch dall'esterno dell'istruzione un `For`... `Next`, `For Each`... `Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, `With`... `End With`, o `Using`... `End Using` costruzione a un'etichetta all'interno.  
  
## <a name="branching-and-try-constructions"></a>Creazione di rami e costruzioni Try  
 All'interno di un `Try`... `Catch`... `Finally` costruzione, le regole seguenti si applicano alla creazione di rami con le `GoTo` istruzione.  
  
|Blocco o area geografica|Diramazione dall'esterno|Diramazione all'esterno|  
|---------------------|-------------------------------|-------------------------------|  
|`Try` Blocco|Solo da un `Catch` blocco della stessa costruzione <sup>1</sup>|Solo di fuori dell'intera costruzione|  
|`Catch` Blocco|Non è consentito|Solo all'esterno della costruzione intera o al `Try` blocco della stessa costruzione <sup>1</sup>|  
|`Finally` Blocco|Non è consentito|Non è consentito|  
  
 <sup>1</sup> eventuale `Try`... `Catch`... `Finally` costruzione viene nidificata all'interno di un altro, un `Catch` blocco può creare rami nel `Try` blocca il proprio livello di annidamento, ma non in qualsiasi altro `Try` blocco. Nidificato `Try`... `Catch`... `Finally` costruzione deve essere completamente contenuta in un `Try` o `Catch` blocco di costruzione all'interno del quale area è nidificata.  
  
 Nell'illustrazione seguente uno `Try` costruzione annidato in un altro. Vari rami tra blocchi di due costruzioni sono indicati come validi o non valido.  
  
 ![Diagramma grafico dei rami in costruzioni Try](../../../visual-basic/language-reference/statements/media/trybranching.gif "TryBranching")  
Validi e non validi i rami in costruzioni Try  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `GoTo` istruzione al ramo in etichette di riga in una procedura.  
  
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
