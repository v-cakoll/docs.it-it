---
title: Tipo di dati Byte (Visual Basic)
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28189ab4ab1a9be9265d1cca020039b5302fb5d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="byte-data-type-visual-basic"></a>Tipo di dati byte (Visual Basic)
Contiene interi senza segno a 8 bit (1-byte) in un intervallo compreso tra 0 e 255.

## <a name="remarks"></a>Note

Utilizzare il `Byte` il tipo di dati per contenere dati binari.  
  
Il valore predefinito di `Byte` è 0.

## <a name="literal-assignments"></a>Assegnazioni di valori letterali

È possibile dichiarare e inizializzare un `Byte` variabile assegnando il valore letterale decimale, valore letterale esadecimale, un valore letterale ottale, o (a partire da Visual Basic 2017) un valore letterale binario. Se il valore letterale integrale non rientra nell'intervallo di un `Byte` (ovvero, se è minore di <xref:System.Byte.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.Byte.MaxValue?displayProperty=nameWithType>), si verifica un errore di compilazione.

Nell'esempio seguente, i numeri interi uguale a 201 rappresentati come decimali, esadecimali, e valori letterali binari vengono convertiti implicitamente dal [intero](integer-data-type.md) a `byte` valori.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> Utilizzare il prefisso `&h` o `&H` per indicare un valore letterale esadecimale, il prefisso `&b` o `&B` per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale. I valori letterali decimali non hanno prefissi.

A partire da Visual Basic 2017, è inoltre possibile utilizzare il carattere di sottolineatura, `_`, come un separatore di cifre per migliorare la leggibilità, come nell'esempio seguente viene illustrato.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

A partire da Visual Basic 15,5, è inoltre possibile utilizzare il carattere di sottolineatura (`_`) come separatore iniziale tra il prefisso e le cifre binarie, ottale o esadecimale. Ad esempio:

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a>Suggerimenti sulla programmazione

-   **Numeri negativi.** Poiché `Byte` è un tipo unsigned, non può rappresentare un numero negativo. Se si utilizza l'operatore meno unario (`-`) gli operatori di un'espressione che restituisce al tipo `Byte`, Visual Basic converte l'espressione `Short` prima.
  
-   **Conversioni di formato.** Quando legge o scrive i file di Visual Basic o durante la chiamata di DLL, metodi e proprietà, è possibile convertire automaticamente tra formati di dati. Dati binari archiviati in `Byte` variabili e matrici vengono conservati durante queste conversioni di formato. Non è consigliabile utilizzare un `String` variabili per i dati binari, perché il relativo contenuto può essere danneggiato durante la conversione tra formati ANSI e Unicode.

-   **Ampliamento.** Il `Byte` può ampliarsi nel tipo di dati `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, o `Double`. È pertanto possibile convertire `Byte` a uno di questi tipi senza generare un <xref:System.OverflowException?displayProperty=nameWithType> errore.
  
-   **Caratteri tipo.** `Byte` non dispone di alcun carattere di tipo letterale o un carattere di tipo identificatore.

-   **Tipo di Framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.Byte?displayProperty=nameWithType>.

## <a name="example"></a>Esempio

 Nell'esempio seguente, `b` è un `Byte` variabile. Le istruzioni illustrano l'intervallo della variabile e l'applicazione degli operatori di spostamento di bit a esso.

[!code-vb[VbVbalrDataTypes#16](../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/byte-data-type_1.vb)]  

## <a name="see-also"></a>Vedere anche

 <xref:System.Byte?displayProperty=nameWithType>  
 [Tipi di dati](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
