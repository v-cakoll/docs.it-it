---
title: Tipo di dati Char
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
ms.openlocfilehash: 3dbbf9f6a2c4079775e05f5d2dcd8704c1ec4259
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387478"
---
# <a name="char-data-type-visual-basic"></a>Tipo di dati Char (Visual Basic)

Include punti di codice senza segno a 16 bit (2 byte) compresi tra 0 e 65535. Ogni *punto di codice*, o codice carattere, rappresenta un singolo carattere Unicode.

## <a name="remarks"></a>Commenti

Utilizzare il `Char` tipo di dati quando è necessario mantenere un solo carattere e non è necessario il sovraccarico di `String` . In alcuni casi è possibile usare `Char()` , una matrice di `Char` elementi, per mantenere più caratteri.

Il valore predefinito di `Char` è il carattere con un punto di codice 0.

## <a name="unicode-characters"></a>Caratteri Unicode

I primi 128 punti di codice (0-127) di Unicode corrispondono a lettere e simboli in una tastiera standard degli Stati Uniti. Questi primi 128 punti di codice corrispondono a quelli definiti dal set di caratteri ASCII. I due punti di codice 128 (128-255) rappresentano caratteri speciali, ad esempio lettere di alfabeto latino, accenti, simboli di valuta e frazioni. Unicode usa i punti di codice rimanenti (256-65535) per un'ampia gamma di simboli, inclusi i caratteri testuali in tutto il mondo, i segni diacritici e i simboli matematici e tecnici.

È possibile utilizzare metodi quali <xref:System.Char.IsDigit%2A> e <xref:System.Char.IsPunctuation%2A> su una `Char` variabile per determinare la relativa classificazione Unicode.

## <a name="type-conversions"></a>Conversione di tipi

Visual Basic non esegue la conversione direttamente tra `Char` e i tipi numerici. È possibile utilizzare la <xref:Microsoft.VisualBasic.Strings.Asc%2A> <xref:Microsoft.VisualBasic.Strings.AscW%2A> funzione o per convertire un `Char` valore in un oggetto `Integer` che rappresenta il punto di codice. È possibile usare la <xref:Microsoft.VisualBasic.Strings.Chr%2A> <xref:Microsoft.VisualBasic.Strings.ChrW%2A> funzione o per convertire un `Integer` valore in un oggetto con `Char` tale punto di codice.

Se l'opzione di controllo del tipo (l' [istruzione Option Strict](../statements/option-strict-statement.md)) è impostata su on, è necessario aggiungere il carattere di tipo letterale a un valore letterale stringa a carattere singolo per identificarlo come `Char` tipo di dati. Questa condizione è illustrata nell'esempio seguente. La prima assegnazione alla `charVar` variabile genera l'errore del compilatore [BC30512](../../misc/bc30512.md) perché `Option Strict` è on. Il secondo compila correttamente perché il `c` carattere di tipo letterale identifica il valore letterale come `Char` valore.

```vb
Option Strict On

Module CharType
    Public Sub Main()
        Dim charVar As Char

        ' This statement generates compiler error BC30512 because Option Strict is On.  
        charVar = "Z"  

        ' The following statement succeeds because it specifies a Char literal.  
        charVar = "Z"c
    End Sub
End Module
```

## <a name="programming-tips"></a>Suggerimenti per la programmazione

- **Numeri negativi.** `Char`è un tipo senza segno e non può rappresentare un valore negativo. In ogni caso, è consigliabile non usare `Char` per mantenere i valori numerici.

- **Considerazioni sull'interoperabilità.** Se si interfaccia con componenti non scritti per il .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i tipi di carattere hanno una larghezza dati diversa (8 bit) in altri ambienti. Se si passa un argomento a 8 bit a tale componente, dichiararlo come `Byte` anziché `Char` nel nuovo codice Visual Basic.

- **Conversioni.** Il `Char` tipo di dati viene ampliato a `String` . Ciò significa che è possibile convertire `Char` in `String` e non si verificherà un oggetto <xref:System.OverflowException?displayProperty=nameWithType> .

- **Digitare i caratteri.** L'aggiunta del carattere di tipo letterale `C` a un valore letterale stringa a carattere singolo lo impone al `Char` tipo di dati. `Char`non ha un carattere di tipo identificatore.

- **Tipo di framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.Char?displayProperty=nameWithType>.

## <a name="see-also"></a>Vedere anche

- <xref:System.Char?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [Tipi di dati](index.md)
- [Tipo di dati String](string-data-type.md)
- [CString](../functions/type-conversion-functions.md)
- [Riepilogo della conversione](../keywords/conversion-summary.md)
- [Procedura: Chiamare una funzione Windows che accetta tipi senza segno](../../programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Uso efficiente dei tipi di dati](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
