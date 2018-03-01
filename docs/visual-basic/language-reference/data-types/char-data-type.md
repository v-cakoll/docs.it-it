---
title: Tipo di dati Char (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Char
helpviewer_keywords:
- literal type characters [Visual Basic], C
- Char data type
- C literal type character [Visual Basic]
- data types [Visual Basic], assigning
- Char data type [Visual Basic], character literals
ms.assetid: cd7547a9-7855-4e8e-b216-35d74a362657
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 16ff547fccbf4481d31ca79537962cc7090fc9b0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="char-data-type-visual-basic"></a>Tipo di dati Char (Visual Basic)
Contiene punti di codice di (2 byte) senza segno a 16 bit compresi nell'intervallo compreso tra 0 e 65535. Ogni *punto di codice*, o codice di carattere, rappresenta un singolo carattere Unicode.  
  
## <a name="remarks"></a>Note  
 Utilizzare il `Char` quando è necessario contenere un solo tipo di dati carattere e non è necessario l'overhead di `String`. In alcuni casi è possibile utilizzare `Char()`, una matrice di `Char` elementi, per contenere più caratteri.  
  
 Il valore predefinito di `Char` è il carattere con un punto di codice pari a 0.  
  
## <a name="unicode-characters"></a>Caratteri Unicode  
 I primo 128 punti di codice (0-127) di Unicode corrispondono alle lettere e simboli di tastiera standard. Questi primi punti di 128 codice sono gli stessi di quelli definisce il set di caratteri ASCII. I secondo 128 punti di codice (128 a 255) rappresentano i caratteri speciali, quali lettere dell'alfabeto latino, accenti, simboli di valuta e le frazioni di secondo. Unicode utilizza i punti di codice rimanenti (256-65535) per un'ampia gamma di simboli, inclusi i caratteri di testuali in tutto il mondo, segni diacritici e simboli matematici e tecnici.  
  
 È possibile utilizzare i metodi, ad esempio <xref:System.Char.IsDigit%2A> e <xref:System.Char.IsPunctuation%2A> su un `Char` variabile per determinarne la classificazione di Unicode.  
  
## <a name="type-conversions"></a>Conversione di tipi  
 Visual Basic non convertire direttamente tra `Char` e i tipi numerici. È possibile utilizzare il <xref:Microsoft.VisualBasic.Strings.Asc%2A> o <xref:Microsoft.VisualBasic.Strings.AscW%2A> funzione per convertire un `Char` valore un `Integer` che rappresenta il punto di codice. È possibile utilizzare il <xref:Microsoft.VisualBasic.Strings.Chr%2A> o <xref:Microsoft.VisualBasic.Strings.ChrW%2A> funzione per convertire un `Integer` valore un `Char` che dispone di tale punto di codice.  
  
 Se il controllo dei tipi passa ([istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)) è abilitato, è necessario aggiungere il tipo di valore letterale di carattere in una stringa di caratteri a singolo valore letterale per identificarlo come il `Char` tipo di dati. Questa condizione è illustrata nell'esempio seguente.  
  
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
  
-   **Numeri negativi.** `Char`è un tipo senza segno e non può rappresentare un valore negativo. In ogni caso, è consigliabile non utilizzare `Char` per contenere valori numerici.  
  
-   **Considerazioni sull'interoperabilità.** Se si prevede l'interazione con componenti non scritti per .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i tipi di carattere hanno un'ampiezza dei dati diversa (8 bit) in altri ambienti. Se si passa un argomento a 8 bit a tale componente, dichiararla come `Byte` anziché `Char` nel nuovo codice Visual Basic.  
  
-   **Ampliamento.** Il `Char` può ampliarsi nel tipo di dati `String`. È pertanto possibile convertire `Char` a `String` senza che si verifichi un <xref:System.OverflowException?displayProperty=nameWithType> errore.  
  
-   **Caratteri tipo.** Aggiungendo il tipo di valore letterale del carattere `C` in una stringa di caratteri a singolo valore letterale indica al sistema di `Char` tipo di dati. `Char`non include alcun carattere di tipo identificatore.  
  
-   **Tipo di Framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.Char?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Char?displayProperty=nameWithType>  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>  
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>  
 [Tipi di dati](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Tipo di dati String](../../../visual-basic/language-reference/data-types/string-data-type.md)  
 [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Procedura: Chiamare una funzione Windows che accetta tipi senza segno](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
