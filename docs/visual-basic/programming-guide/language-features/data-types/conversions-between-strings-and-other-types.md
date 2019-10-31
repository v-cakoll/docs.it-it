---
title: Conversioni fra stringhe e altri tipi (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- data type conversion [Visual Basic], string
- conversions [Visual Basic], type
- string conversion [Visual Basic]
- conversions [Visual Basic], data type
- type conversion [Visual Basic], string
- regional options
ms.assetid: c3a99596-f09a-44a5-81dd-1b89a094f1df
ms.openlocfilehash: 06dabbb5d5dfbfb545f01afb157fd532ca0551df
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197342"
---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a>Conversioni fra stringhe e altri tipi (Visual Basic)
È possibile convertire un valore numerico, `Boolean` o di data/ora in un `String`. È anche possibile eseguire la conversione in senso inverso, da un valore stringa a numeric, `Boolean` o `Date`, purché il contenuto della stringa possa essere interpretato come un valore valido del tipo di dati di destinazione. In caso affermativo, si verifica un errore in fase di esecuzione.  
  
 Le conversioni per tutte queste assegnazioni, in entrambe le direzioni, sono le conversioni verso un tipo di caratteri più piccolo. È necessario utilizzare le parole chiave di conversione del tipo (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, 0, 1 2 , 3 e 4). Le funzioni <xref:Microsoft.VisualBasic.Strings.Format%2A> e <xref:Microsoft.VisualBasic.Conversion.Val%2A> consentono di controllare ulteriormente le conversioni tra stringhe e numeri.  
  
 Se è stata definita una classe o una struttura, è possibile definire operatori di conversione dei tipi tra `String` e il tipo della classe o della struttura. Per altre informazioni, vedere [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="conversion-of-numbers-to-strings"></a>Conversione di numeri in stringhe  
 È possibile utilizzare la funzione `Format` per convertire un numero in una stringa formattata, che può includere non solo le cifre appropriate, ma anche la formattazione di simboli quali un segno di valuta, ad esempio `$`, i separatori delle migliaia o i *simboli di raggruppamento delle cifre* , ad esempio @no __t_3) e un separatore decimale, ad esempio `.`. `Format` utilizza automaticamente i simboli appropriati in base alle impostazioni delle **Opzioni internazionali** specificate nel **Pannello di controllo**di Windows.  
  
 Si noti che l'operatore di concatenazione (`&`) può convertire un numero in una stringa in modo implicito, come illustrato nell'esempio riportato di seguito.  
  
```vb  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a>Conversione di stringhe in numeri  
 È possibile utilizzare la funzione `Val` per convertire in modo esplicito le cifre di una stringa in un numero. `Val` legge la stringa fino a quando non viene rilevato un carattere diverso da una cifra, uno spazio, una tabulazione, un avanzamento riga o un punto. Le sequenze "& O" e "& H" modificano la base del sistema numerico e terminano l'analisi. Fino a quando non viene arrestata la lettura, `Val` converte tutti i caratteri appropriati in un valore numerico. Ad esempio, l'istruzione seguente restituisce il valore `141.825`.  
  
 `Val("   14   1.825 miles")`  
  
 Quando Visual Basic converte una stringa in un valore numerico, USA le impostazioni delle **Opzioni internazionali** specificate nel pannello di **controllo** di Windows per interpretare il separatore delle migliaia, il separatore decimale e il simbolo di valuta. Ciò significa che una conversione potrebbe avere esito positivo in un'impostazione ma non in un'altra. Ad esempio, `"$14.20"` è accettabile nelle impostazioni locali in inglese (Stati Uniti) ma non in tutte le impostazioni locali francesi.  
  
## <a name="see-also"></a>Vedere anche

- [Conversioni di tipi in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Conversioni di ampliamento e restrizione](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Conversioni implicite ed esplicite](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Procedura: convertire un oggetto in un altro tipo in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [Conversioni di matrice](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [Tipi di dati](../../../../visual-basic/language-reference/data-types/index.md)
- [Funzioni di conversione del tipo](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Sviluppare app globalizzate e localizzate](/visualstudio/ide/globalizing-and-localizing-applications)
