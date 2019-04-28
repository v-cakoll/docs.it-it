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
ms.openlocfilehash: 124f0ca0cd01d7fd218fd89dfb78e70fe8aad9e4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864935"
---
# <a name="concatenation-operators-in-visual-basic"></a>Operatori di concatenazione in Visual Basic
Gli operatori di concatenazione consentono di unire più stringhe in un'unica stringa. Sono disponibili due operatori di concatenazione: `+` e `&`. Entrambi eseguono operazioni di concatenazione di base, come illustrato nell'esempio seguente.  
  
```vb
Dim x As String = "Mic" & "ro" & "soft" 
Dim y As String = "Mic" + "ro" + "soft" 
' The preceding statements set both x and y to "Microsoft".
```  
  
 Questi operatori possono concatenare anche variabili di tipo `String`, come nell'esempio seguente.  
  
 [!code-vb[VbVbalrOperators#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#76)]  
  
## <a name="differences-between-the-two-concatenation-operators"></a>Differenze tra i due operatori di concatenazione  
 Il [operatore +](../../../../visual-basic/language-reference/operators/addition-operator.md) ha lo scopo principale dell'aggiunta di due numeri. Questo operatore consente però anche di concatenare operandi numerici con operandi stringa. L'operatore `+` include un insieme complesso di regole che determinano se aggiungere, concatenare, segnalare un errore del compilatore oppure generare un'eccezione <xref:System.InvalidCastException> in fase di esecuzione.  
  
 Il [& Operator](../../../../visual-basic/language-reference/operators/concatenation-operator.md) viene definito solo per `String` operandi che amplia sempre i propri operandi a `String`, indipendentemente dall'impostazione di `Option Strict`. L'operatore `&` rappresenta la scelta consigliata per la concatenazione delle stringhe poiché viene definito solo per le stringhe e riduce la possibilità di generare conversioni non intenzionali.  
  
## <a name="performance-string-and-stringbuilder"></a>Prestazioni: String e StringBuilder  
 Se una stringa subisce numerose manipolazioni, ad esempio concatenazioni, eliminazioni e sostituzioni, l'uso della classe <xref:System.Text.StringBuilder> nello spazio dei nomi <xref:System.Text> può migliorare le prestazioni. Questa classe richiede un'istruzione aggiuntiva per la creazione e l'inizializzazione di un oggetto <xref:System.Text.StringBuilder> e un'altra istruzione per la conversione del relativo valore finale in `String`, ma in questo caso è possibile eseguire il ripristino perché l'esecuzione di <xref:System.Text.StringBuilder> è più veloce.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Tipi di metodi di manipolazione delle stringhe in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/types-of-string-manipulation-methods.md)
- [Operatori aritmetici in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Operatori di confronto in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Operatori logici e bit per bit in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
