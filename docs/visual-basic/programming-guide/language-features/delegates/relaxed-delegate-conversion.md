---
title: Conversione di tipo relaxed del delegato
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: a581ffae77c496908d2e4e38df53491a54ae2ab8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410670"
---
# <a name="relaxed-delegate-conversion-visual-basic"></a>Conversione di tipo relaxed del delegato (Visual Basic)
La conversione di un delegato rilassato consente di assegnare subroutine e funzioni a delegati o gestori anche quando le relative firme non sono identiche. Pertanto, l'associazione a delegati diventa coerente con l'associazione già consentita per le chiamate al metodo.  
  
## <a name="parameters-and-return-type"></a>Parametri e tipo restituito  
 Al posto della corrispondenza esatta della firma, la conversione rilassata richiede che vengano soddisfatte le condizioni seguenti quando `Option Strict` è impostato su `On` :  
  
- Deve esistere una conversione verso un tipo di dati più ampio dal tipo di dati di ogni parametro del delegato al tipo di dati del parametro corrispondente della funzione assegnata o `Sub` . Nell'esempio seguente, il delegato `Del1` ha un parametro, un oggetto `Integer` . `m`Il parametro nelle espressioni lambda assegnate deve avere un tipo di dati per il quale esiste una conversione verso un tipo di dati più ampio da `Integer` , ad esempio `Long` o `Double` .  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#2)]  
  
     Le conversioni verso un tipo di caratteri più piccolo sono consentite solo quando `Option Strict` è impostato su `Off` .  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#8)]  
  
- Una conversione verso un tipo di allargamento deve esistere nella direzione opposta dal tipo restituito della funzione assegnata o `Sub` al tipo restituito del delegato. Negli esempi seguenti, il corpo di ogni espressione lambda assegnata deve restituire un tipo di dati che viene ampliato a `Integer` perché il tipo restituito di `del1` è `Integer` .  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#3)]  
  
 Se `Option Strict` è impostato su `Off` , la restrizione di ampliamento viene rimossa in entrambe le direzioni.  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#4)]  
  
## <a name="omitting-parameter-specifications"></a>Omissione delle specifiche di parametro  
 I delegati rilassati consentono inoltre di omettere completamente le specifiche dei parametri nel metodo assegnato:  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#5)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#6)]  
  
 Si noti che non è possibile specificare alcuni parametri e ometterne altri.  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#15)]  
  
 La possibilità di omettere i parametri è utile in una situazione come la definizione di un gestore eventi, in cui sono interessati diversi parametri complessi. Gli argomenti per alcuni gestori di eventi non vengono usati. Al contrario, il gestore accede direttamente allo stato del controllo in cui è registrato l'evento e ignora gli argomenti. I delegati rilassati consentono di omettere gli argomenti in tali dichiarazioni quando non risultano ambiguità. Nell'esempio seguente, il metodo completamente specificato `OnClick` può essere riscritto come `RelaxedOnClick` .  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a>Esempi di AddressOf  
 Le espressioni lambda vengono usate negli esempi precedenti per semplificare la visualizzazione delle relazioni tra i tipi. Tuttavia, sono consentiti gli stessi relax per le assegnazioni di delegati che usano `AddressOf` , `Handles` o `AddHandler` .  
  
 Nell'esempio seguente le funzioni `f1` ,, `f2` `f3` e `f4` possono essere assegnate a `Del1` .  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#7)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#9)]  
  
 L'esempio seguente è valido solo quando `Option Strict` è impostato su `Off` .  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#14)]  
  
## <a name="dropping-function-returns"></a>Eliminazione della funzione restituita  
 La conversione di un delegato rilassato consente di assegnare una funzione a un `Sub` delegato, ignorando in modo efficace il valore restituito della funzione. Tuttavia, non è possibile assegnare un oggetto `Sub` a un delegato di funzione. Nell'esempio seguente, l'indirizzo della funzione `doubler` viene assegnato al `Sub` delegato `Del3` .  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#10)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#11)]  
  
## <a name="see-also"></a>Vedere anche

- [Espressioni lambda](../procedures/lambda-expressions.md)
- [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md)
- [Delegati](index.md)
- [Procedura: passare una routine a un'altra routine in Visual Basic](how-to-pass-procedures-to-another-procedure.md)
- [Inferenza del tipo di variabile locale](../variables/local-type-inference.md)
- [Option Strict Statement](../../../language-reference/statements/option-strict-statement.md)
