---
title: Conversioni fra stringhe e altri tipi (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- data type conversion [Visual Basic], string
- conversions [Visual Basic], type
- string conversion [Visual Basic]
- conversions [Visual Basic], data type
- type conversion [Visual Basic], string
- regional options
ms.assetid: c3a99596-f09a-44a5-81dd-1b89a094f1df
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 82473d59d6b6aac21f2d7f2a0c9748217a61985f
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a>Conversioni fra stringhe e altri tipi (Visual Basic)
È possibile convertire un valore numerico, `Boolean`, o valore di data/ora un `String`. È anche possibile convertire in direzione inversa, ovvero da un valore di stringa numerici, `Boolean`, o `Date` , purché il contenuto della stringa può essere interpretato come un valore valido del tipo di dati di destinazione. In caso contrario, si verifica un errore di run-time.  
  
 Le conversioni per tutte queste assegnazioni, in entrambe le direzioni, sono conversioni di restrizione. È consigliabile utilizzare parole chiave di conversione del tipo (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, e `CType`). Il <xref:Microsoft.VisualBasic.Strings.Format%2A> e <xref:Microsoft.VisualBasic.Conversion.Val%2A> funzioni forniscono un maggiore controllo sulle conversioni fra stringhe e numeri.  
  
 Se è stato definito una classe o struttura, è possibile definire gli operatori di conversione di tipo tra `String` e il tipo di classe o struttura. Per ulteriori informazioni, vedere [procedura: definire un operatore di conversione](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="conversion-of-numbers-to-strings"></a>Conversione dei numeri in stringhe  
 È possibile utilizzare il `Format` funzione per convertire un numero in una stringa formattata, che può includere non solo le cifre appropriate, ma anche simboli, ad esempio un simbolo di valuta di formattazione (ad esempio `$`), migliaia separatori o *raggruppamento cifre simboli* (ad esempio `,`) e un separatore decimale (ad esempio `.`). `Format` Usa automaticamente i simboli appropriati in base al **opzioni internazionali** le impostazioni specificate nelle finestre **Pannello di controllo**.  
  
 Si noti che la concatenazione (`&`) (operatore) consente di convertire un numero in una stringa in modo implicito, come illustrato nell'esempio seguente.  
  
```  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a>Conversione di stringhe in numeri  
 È possibile utilizzare il `Val` funzione per convertire esplicitamente le cifre in una stringa in un numero. `Val` legge la stringa finché non incontra un carattere diverso da una cifra, spazio, scheda, avanzamento riga o periodo. Le sequenze di "& O" e "& H" alterano la base del sistema di numerazione e termina l'analisi. Finché termina la lettura, `Val` converte tutti i caratteri appropriati in un valore numerico. Ad esempio, l'istruzione seguente restituisce il valore `141.825`.  
  
 `Val("   14   1.825 miles")`  
  
 Quando Visual Basic converte una stringa in un valore numerico, utilizza il **opzioni internazionali** le impostazioni specificate nelle finestre **Pannello di controllo** per interpretare le migliaia separator, separatore decimale, e simbolo di valuta. Ciò significa che una conversione potrebbe avere esito positivo con un'impostazione ma non in un altro. Ad esempio, `"$14.20"` accettabile nelle impostazioni locali inglese (Stati Uniti) ma non in qualsiasi lingua francese.  
  
## <a name="see-also"></a>Vedere anche  
 [Conversioni di tipi in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Conversioni di ampliamento e restrizione](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Conversioni implicite ed esplicite](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Procedura: convertire un oggetto in un altro tipo in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [Conversioni di matrice](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 [Tipi di dati](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Funzioni di conversione del tipo](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Introduzione alle applicazioni internazionali basate su .NET Framework](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
