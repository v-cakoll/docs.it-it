---
title: Conversione di tipo relaxed del delegato (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: 57e863d9781721a997ae49e1a5c9d8f3562a1bd0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58842720"
---
# <a name="relaxed-delegate-conversion-visual-basic"></a>Conversione di tipo relaxed del delegato (Visual Basic)
Conversione di tipo relaxed del delegato consente di assegnare subroutine e funzioni a delegati o gestori anche quando le relative firme non sono identiche. Pertanto, l'associazione ai delegati diventa coerenti con l'associazione già consentito per le chiamate ai metodi.  
  
## <a name="parameters-and-return-type"></a>I parametri e il tipo restituito  
 Al posto di esatta corrispondenza della firma, la conversione di tipo "relaxed" richiede che essere soddisfatte le condizioni seguenti quando si `Option Strict` è impostata su `On`:  
  
-   Deve esistere una conversione verso un dal tipo di dati di ogni parametro del delegato per il tipo di dati del parametro corrispondente della funzione assegnata o `Sub`. Nell'esempio seguente, il delegato `Del1` ha un parametro, un `Integer`. Parametro `m` nell'espressione lambda assegnata espressioni devono presentare un tipo di dati per il quale viene eseguita una conversione widening dal `Integer`, ad esempio `Long` o `Double`.  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#2)]  
  
     Conversioni di Narrowing sono consentite solo quando `Option Strict` è impostata su `Off`.  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#8)]  
  
-   Deve esistere una conversione verso un nella direzione opposta dal tipo restituito della funzione assegnata o `Sub` nel tipo restituito del delegato. Negli esempi seguenti, deve restituire il corpo di ogni espressione lambda assegnata a un tipo di dati che si amplia in `Integer` perché il tipo restituito di `del1` è `Integer`.  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#3)]  
  
 Se `Option Strict` è impostata su `Off`, l'ampliamento restrizione è stata rimossa in entrambe le direzioni.  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#4)]  
  
## <a name="omitting-parameter-specifications"></a>Omettendo le specifiche dei parametri  
 Delegati di tipo relaxed consentono anche di omettere completamente le specifiche dei parametri nel metodo assegnato:  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#5)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#6)]  
  
 Si noti che non è possibile specificare alcuni parametri e omettere gli altri.  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#15)]  
  
 La possibilità di omettere i parametri è utile in situazioni, ad esempio definendo un gestore eventi, in cui sono coinvolti diversi parametri complessi. Gli argomenti per alcuni gestori di eventi non vengono utilizzati. Al contrario, il gestore accede direttamente lo stato del controllo in cui è registrato l'evento e gli argomenti vengono ignorati. Delegati di tipo relaxed consentono di omettere gli argomenti nelle dichiarazioni di questo tipo quando nessun risultato le ambiguità. Nell'esempio seguente, il metodo specificato completamente `OnClick` può essere riscritta come `RelaxedOnClick`.  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a>Esempi di AddressOf  
 Le espressioni lambda vengono usate negli esempi precedenti in modo semplice visualizzare le relazioni di tipo. Tuttavia, gli allentamenti stesso sono consentiti per le assegnazioni di delegato che usano `AddressOf`, `Handles`, o `AddHandler`.  
  
 Nell'esempio seguente, le funzioni `f1`, `f2`, `f3`, e `f4` possono essere assegnati a `Del1`.  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#7)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#9)]  
  
 L'esempio seguente è valido solo quando `Option Strict` è impostata su `Off`.  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#14)]  
  
## <a name="dropping-function-returns"></a>Eliminazione di elementi restituiti da funzioni  
 Conversione di tipo relaxed del delegato che consente di assegnare una funzione a un `Sub` delegato, in modo efficace, ignorando il valore restituito della funzione. Tuttavia, non è possibile assegnare un `Sub` a un delegato di funzione. Nell'esempio seguente, l'indirizzo della funzione `doubler` viene assegnato a `Sub` delegare `Del3`.  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#10)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#11)]  
  
## <a name="see-also"></a>Vedere anche

- [Espressioni lambda](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [Conversioni di ampliamento e restrizione](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Delegati](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Procedura: Passare una routine a un'altra routine in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [Inferenza del tipo di variabile locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
