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
ms.openlocfilehash: ca40e6c8dcba3da29bdb68b29c91c852e477f8f7
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512782"
---
# <a name="char-data-type-visual-basic"></a>Tipo di dati Char (Visual Basic)

Include punti di codice senza segno a 16 bit (2 byte) compresi tra 0 e 65535. Ogni *punto di codice*, o codice carattere, rappresenta un singolo carattere Unicode.

## <a name="remarks"></a>Note

Utilizzare il `Char` tipo di dati quando è necessario mantenere un solo carattere e non è necessario il sovraccarico di `String`. In alcuni casi è possibile usare `Char()`, una matrice di `Char` elementi, per mantenere più caratteri.

Il valore predefinito di `Char` è il carattere con un punto di codice 0.

## <a name="unicode-characters"></a>Caratteri Unicode

I primi 128 punti di codice (0-127) di Unicode corrispondono a lettere e simboli in una tastiera standard degli Stati Uniti. Questi primi 128 punti di codice corrispondono a quelli definiti dal set di caratteri ASCII. I due punti di codice 128 (128-255) rappresentano caratteri speciali, ad esempio lettere di alfabeto latino, accenti, simboli di valuta e frazioni. Unicode usa i punti di codice rimanenti (256-65535) per un'ampia gamma di simboli, inclusi i caratteri testuali in tutto il mondo, i segni diacritici e i simboli matematici e tecnici.

È possibile utilizzare metodi quali <xref:System.Char.IsDigit%2A> e <xref:System.Char.IsPunctuation%2A> su una `Char` variabile per determinare la relativa classificazione Unicode.

## <a name="type-conversions"></a>Conversione di tipi

Visual Basic non esegue la conversione direttamente `Char` tra e i tipi numerici. È possibile utilizzare la <xref:Microsoft.VisualBasic.Strings.Asc%2A> funzione <xref:Microsoft.VisualBasic.Strings.AscW%2A> o per convertire un `Char` valore in un `Integer` oggetto che rappresenta il punto di codice. È possibile usare la <xref:Microsoft.VisualBasic.Strings.Chr%2A> funzione <xref:Microsoft.VisualBasic.Strings.ChrW%2A> o per convertire un `Integer` valore in un `Char` oggetto con tale punto di codice.

Se l'opzione di controllo del tipo ([Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)) è impostata su on, è necessario aggiungere il carattere di tipo letterale a un valore letterale stringa `Char` a carattere singolo per identificarlo come tipo di dati. Questa condizione è illustrata nell'esempio seguente.

```vb
Option Strict On
Dim charVar As Char
' The following statement attempts to convert a String literal to Char.
' Because Option Strict is On, it generates a compiler error.
charVar = "Z"
' The following statement succeeds because it specifies a Char literal.
charVar = "Z"C
```

## <a name="programming-tips"></a>Suggerimenti per la programmazione

- **Numeri negativi.** `Char`è un tipo senza segno e non può rappresentare un valore negativo. In ogni caso, è consigliabile non usare `Char` per mantenere i valori numerici.

- **Considerazioni sull'interoperabilità.** Se si interfaccia con componenti non scritti per il .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i tipi di carattere hanno una larghezza dati diversa (8 bit) in altri ambienti. Se si passa un argomento a 8 bit a tale componente, dichiararlo come `Byte` `Char` anziché nel nuovo codice Visual Basic.

- **Conversioni.** Il `Char` tipo di dati viene ampliato a `String`. Ciò significa che è possibile `Char` eseguire `String` la conversione in e non <xref:System.OverflowException?displayProperty=nameWithType> si verificherà un errore.

- **Digitare i caratteri.** L'aggiunta del carattere `C` di tipo letterale a un valore letterale stringa a carattere singolo lo impone `Char` al tipo di dati. `Char`non ha un carattere di tipo identificatore.

- **Tipo di Framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.Char?displayProperty=nameWithType>.

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
