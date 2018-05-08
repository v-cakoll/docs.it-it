---
title: Operatori di concatenazione in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- '& operator [Visual Basic], concatenation'
- concatenation operators [Visual Basic]
- operators [Visual Basic], concatenation
- Visual Basic code, operators
- + operator [Visual Basic], concatenation
- concatenation operators [Visual Basic]
ms.assetid: e59908c3-89e0-41ae-933d-3e8826c16a04
ms.openlocfilehash: ab268e513e6f019ed651c94deb5e423cfcca7587
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="concatenation-operators-in-visual-basic"></a>Operatori di concatenazione in Visual Basic
Gli operatori di concatenazione consentono di unire più stringhe in un'unica stringa. Sono disponibili due operatori di concatenazione: `+` e `&`. Entrambi eseguono operazioni di concatenazione di base, come illustrato nell'esempio seguente.  
  
```vb
Dim x As String = "Mic" & "ro" & "soft" 
Dim y As String = "Mic" + "ro" + "soft" 
' The preceding statements set both x and y to "Microsoft".
```  
  
 Questi operatori possono concatenare anche variabili di tipo `String`, come nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#76](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operators_1.vb)]  
  
## <a name="differences-between-the-two-concatenation-operators"></a>Differenze tra i due operatori di concatenazione  
 Il [+ (operatore)](../../../../visual-basic/language-reference/operators/addition-operator.md) ha lo scopo principale di aggiunta di due numeri. Questo operatore consente però anche di concatenare operandi numerici con operandi stringa. L'operatore `+` include un insieme complesso di regole che determinano se aggiungere, concatenare, segnalare un errore del compilatore oppure generare un'eccezione <xref:System.InvalidCastException> in fase di esecuzione.  
  
 Il [& operatore](../../../../visual-basic/language-reference/operators/concatenation-operator.md) viene definito solo per `String` amplia sempre i propri operandi per gli operandi e `String`, indipendentemente dall'impostazione di `Option Strict`. L'operatore `&` rappresenta la scelta consigliata per la concatenazione delle stringhe poiché viene definito solo per le stringhe e riduce la possibilità di generare conversioni non intenzionali.  
  
## <a name="performance-string-and-stringbuilder"></a>Prestazioni: String e StringBuilder  
 Se una stringa subisce numerose manipolazioni, ad esempio concatenazioni, eliminazioni e sostituzioni, l'uso della classe <xref:System.Text.StringBuilder> nello spazio dei nomi <xref:System.Text> può migliorare le prestazioni. Questa classe richiede un'istruzione aggiuntiva per la creazione e l'inizializzazione di un oggetto <xref:System.Text.StringBuilder> e un'altra istruzione per la conversione del relativo valore finale in `String`, ma in questo caso è possibile eseguire il ripristino perché l'esecuzione di <xref:System.Text.StringBuilder> è più veloce.  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Tipi di metodi di modifica di stringhe in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/types-of-string-manipulation-methods.md)  
 [Operatori aritmetici in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [Operatori di confronto in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Operatori logici e bit per bit in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
