---
title: Tipo di dati Byte
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
ms.openlocfilehash: 97acd1bc2ff29bac6588216b9ee4a4f187078815
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374317"
---
# <a name="byte-data-type-visual-basic"></a>Tipo di dati byte (Visual Basic)

Include interi senza segno a 8 bit (1 byte) che variano in valore compreso tra 0 e 255.

## <a name="remarks"></a>Commenti

Utilizzare il `Byte` tipo di dati per contenere dati binari.  
  
Il valore predefinito di `Byte` è 0.

## <a name="literal-assignments"></a>Assegnazioni di valori letterali

È possibile dichiarare e inizializzare una variabile assegnandogli un valore letterale `Byte` decimale, un valore letterale esadecimale, un valore letterale ottale o (a partire da Visual Basic 2017) un valore letterale binario. Se il valore letterale integrale non è compreso nell'intervallo di un oggetto, `Byte` ovvero se è minore di <xref:System.Byte.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.Byte.MaxValue?displayProperty=nameWithType> , si verifica un errore di compilazione.

Nell'esempio seguente, i numeri interi uguali a 201 rappresentati come valori letterali decimali, esadecimali e binari vengono convertiti in modo implicito da [Integer](integer-data-type.md) a `byte` valori.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> Usare il prefisso `&h` o `&H` per indicare un valore letterale esadecimale, il prefisso `&b` o `&B` per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale. I valori letterali decimali non hanno prefissi.

A partire da Visual Basic 2017, è anche possibile usare il carattere di sottolineatura, `_` , come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

A partire da Visual Basic 15,5, è anche possibile usare il carattere di sottolineatura ( `_` ) come separatore iniziale tra il prefisso e le cifre esadecimali, binarie o ottali. Ad esempio:

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a>Suggerimenti per la programmazione

- **Numeri negativi.** Poiché `Byte` è un tipo senza segno, non può rappresentare un numero negativo. Se si usa l'operatore unario meno ( `-` ) su un'espressione che restituisce il tipo `Byte` , Visual Basic converte prima l'espressione in `Short` .
  
- **Conversioni di formato.** Quando Visual Basic legge o scrive file oppure quando chiama dll, metodi e proprietà, può eseguire automaticamente la conversione tra i formati di dati. I dati binari archiviati in `Byte` variabili e matrici vengono conservati durante tali conversioni di formato. Non usare una `String` variabile per i dati binari, perché il relativo contenuto può essere danneggiato durante la conversione tra i formati ANSI e Unicode.

- **Conversioni.** Il `Byte` tipo di dati viene ampliato in `Short` , `UShort` , `Integer` , `UInteger` , `Long` , `ULong` , `Decimal` , `Single` o `Double` . Ciò significa che è possibile `Byte` eseguire la conversione in uno di questi tipi senza riscontrare un <xref:System.OverflowException?displayProperty=nameWithType> errore.
  
- **Digitare i caratteri.** `Byte`non ha un carattere di tipo letterale o un carattere di tipo identificatore.

- **Tipo di framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.Byte?displayProperty=nameWithType>.

## <a name="example"></a>Esempio

 Nell'esempio seguente `b` è una `Byte` variabile. Le istruzioni illustrano l'intervallo della variabile e l'applicazione degli operatori di spostamento di bit.

 [!code-vb[VbVbalrDataTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#16)]  

## <a name="see-also"></a>Vedere anche

- <xref:System.Byte?displayProperty=nameWithType>
- [Tipi di dati](index.md)
- [CString](../functions/type-conversion-functions.md)
- [Riepilogo della conversione](../keywords/conversion-summary.md)
- [Uso efficiente dei tipi di dati](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
