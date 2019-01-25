---
title: Tipo di dati Char (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Char
helpviewer_keywords:
- literal type characters [Visual Basic], C
- Char data type
- C literal type character [Visual Basic]
- data types [Visual Basic], assigning
- Char data type [Visual Basic], character literals
ms.assetid: cd7547a9-7855-4e8e-b216-35d74a362657
ms.openlocfilehash: f641f3dbcba32c77bcf73b14a9ac890d1ade5a2c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611917"
---
# <a name="char-data-type-visual-basic"></a>Tipo di dati Char (Visual Basic)
Contiene punti di codice (a 2 byte) a 16 bit senza segno compresi nell'intervallo compreso tra 0 e 65535. Ciascuna *punto di codice*, o il codice carattere rappresenta un singolo carattere Unicode.  
  
## <a name="remarks"></a>Note  
 Usare la `Char` quando è necessario contenere un solo tipo di dati carattere e non è necessario l'overhead di `String`. In alcuni casi è possibile usare `Char()`, una matrice di `Char` elementi, per contenere più caratteri.  
  
 Il valore predefinito di `Char` è il carattere con un punto di codice pari a 0.  
  
## <a name="unicode-characters"></a>Caratteri Unicode  
 I punti di 128 codice (0-127) prima di Unicode corrispondono alle lettere e simboli di una tastiera US standard. Questi primi punti di 128 codice sono identici a quelli definisce il set di caratteri ASCII. I secondo 128 punti di codice (128 a 255) rappresentano i caratteri speciali, ad esempio lettere dell'alfabeto basati sull'alfabeto latino, accenti, i simboli di valuta e le frazioni. Unicode utilizza i punti di codice rimanenti (256 e 65535) per un'ampia gamma di simboli, inclusi i caratteri di testo in tutto il mondo, i segni diacritici e simboli matematici e tecnici.  
  
 È possibile usare metodi quali <xref:System.Char.IsDigit%2A> e <xref:System.Char.IsPunctuation%2A> su un `Char` variabile per determinarne la classificazione di Unicode.  
  
## <a name="type-conversions"></a>Conversione di tipi  
 Visual Basic non converte direttamente tra `Char` e i tipi numerici. È possibile usare la <xref:Microsoft.VisualBasic.Strings.Asc%2A> oppure <xref:Microsoft.VisualBasic.Strings.AscW%2A> funzione per convertire un `Char` valore un `Integer` che rappresenta il punto di codice. È possibile usare il <xref:Microsoft.VisualBasic.Strings.Chr%2A> oppure <xref:Microsoft.VisualBasic.Strings.ChrW%2A> funzione per convertire un `Integer` valore un `Char` che dispone di tale punto di codice.  
  
 Se il controllo del tipo passa ([Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)) è attivo, è necessario aggiungere il carattere di tipo di valore letterale in una stringa di caratteri a un valore letterale per identificarlo come il `Char` tipo di dati. Questa condizione è illustrata nell'esempio seguente.  
  
```  
Option Strict On  
Dim charVar As Char  
' The following statement attempts to convert a String literal to Char.  
' Because Option Strict is On, it generates a compiler error.  
charVar = "Z"  
' The following statement succeeds because it specifies a Char literal.  
charVar = "Z"C  
```  
  
## <a name="programming-tips"></a>Suggerimenti per la programmazione  
  
-   **Numeri negativi.** `Char` è un tipo senza segno e non può rappresentare un valore negativo. In ogni caso, è consigliabile non usare `Char` per contenere valori numerici.  
  
-   **Considerazioni sull'interoperabilità.** Se si deve interfacciare con componenti non scritti per .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i tipi di carattere hanno un'ampiezza dei dati diverse (8 bit) in altri ambienti. Se si passa un argomento a 8 bit da tale componente, dichiararlo come `Byte` invece di `Char` nel nuovo codice Visual Basic.  
  
-   **Widening.** Il `Char` può ampliarsi nel tipo di dati `String`. Ciò significa che è possibile convertire `Char` al `String` senza che si verifichi un <xref:System.OverflowException?displayProperty=nameWithType> errore.  
  
-   **Caratteri tipo.** Aggiungendo il carattere di tipo di valore letterale `C` a una stringa di caratteri a un valore letterale, se ne determina la `Char` tipo di dati. `Char` possiede alcun carattere di tipo identificatore.  
  
-   **Tipo di Framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.Char?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Char?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [Tipi di dati](../../../visual-basic/language-reference/data-types/index.md)
- [Tipo di dati String](../../../visual-basic/language-reference/data-types/string-data-type.md)
- [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Procedura: Chiamare una funzione Windows che accetta tipi senza segno](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
