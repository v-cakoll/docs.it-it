---
title: Conversione di tipo relaxed del delegato (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0cca3d09b538905714f627c9fa006187b8927383
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="relaxed-delegate-conversion-visual-basic"></a>Conversione di tipo relaxed del delegato (Visual Basic)
Conversione di tipo relaxed del delegato consente di assegnare subroutine e funzioni a delegati o gestori anche quando le firme non sono identiche. Pertanto, l'associazione di delegati diventa coerente con l'associazione già consentita per le chiamate di metodo.  
  
## <a name="parameters-and-return-type"></a>Parametri e tipo restituito  
 Al posto di corrispondenza esatta delle firme, conversione di tipo relaxed richiede che le condizioni seguenti quando `Option Strict` è impostato su `On`:  
  
-   Deve esistere una conversione dal tipo di dati di ogni parametro del delegato al tipo di dati del parametro corrispondente della funzione assegnata o `Sub`. Nell'esempio seguente, il delegato `Del1` dispone di un parametro, un `Integer`. Parametro `m` nell'espressione lambda assegnata espressioni devono avere un tipo di dati per cui è disponibile una conversione da `Integer`, ad esempio `Long` o `Double`.  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_2.vb)]  
  
     Conversioni di restrizione sono consentite solo quando `Option Strict` è impostato su `Off`.  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_3.vb)]  
  
-   Deve esistere una conversione widening nella direzione opposta dal tipo restituito della funzione assegnata o `Sub` per il tipo restituito del delegato. Negli esempi seguenti, il corpo di ogni espressione lambda assegnata deve restituire un tipo di dati che si amplia in `Integer` perché il tipo restituito di `del1` è `Integer`.  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_4.vb)]  
  
 Se `Option Strict` è impostato su `Off`, l'ampliamento restrizione è stata rimossa in entrambe le direzioni.  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_5.vb)]  
  
## <a name="omitting-parameter-specifications"></a>L'omissione di specifiche di parametro  
 Delegati di tipo relaxed consentono anche di omettere completamente le specifiche dei parametri nel metodo assegnato:  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_6.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_7.vb)]  
  
 Si noti che non è possibile specificare alcuni parametri e omettere gli altri.  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_8.vb)]  
  
 La possibilità di omettere i parametri è utile in una situazione ad esempio la definizione di un gestore eventi, in cui sono coinvolti diversi parametri complessi. Non vengono utilizzati gli argomenti per alcuni gestori di eventi. Invece, il gestore accede direttamente lo stato del controllo in cui è registrato l'evento e gli argomenti vengono ignorati. Delegati di tipo relaxed consentono di omettere gli argomenti in tali dichiarazioni quando non risultano ambiguità. Nell'esempio seguente, il metodo specificato completamente `OnClick` può essere riscritta come `RelaxedOnClick`.  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a>Esempi di AddressOf  
 Espressioni lambda vengono utilizzate negli esempi precedenti in modo semplice visualizzare le relazioni di tipo. Tuttavia, le stesse conversioni di tipo relaxed sono consentite per le assegnazioni di delegato che utilizzano `AddressOf`, `Handles`, o `AddHandler`.  
  
 Nell'esempio seguente, le funzioni `f1`, `f2`, `f3`, e `f4` può essere assegnato a `Del1`.  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_9.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_10.vb)]  
  
 Nell'esempio seguente è valido solo quando `Option Strict` è impostato su `Off`.  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_11.vb)]  
  
## <a name="dropping-function-returns"></a>Eliminazione di elementi restituiti da funzioni  
 Conversione di tipo relaxed del delegato consente di assegnare una funzione da un `Sub` delegato, in modo efficace, ignorando il valore restituito della funzione. Tuttavia, non è possibile assegnare un `Sub` a un delegato della funzione. Nell'esempio seguente, l'indirizzo della funzione `doubler` viene assegnato a `Sub` delegato `Del3`.  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_12.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_13.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Espressioni lambda](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [Conversioni di ampliamento e restrizione](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Delegati](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Procedura: Passare una routine a un'altra routine in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)  
 [Inferenza del tipo di variabile locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
