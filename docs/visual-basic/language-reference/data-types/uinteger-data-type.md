---
title: Tipo di dati UInteger
ms.date: 01/31/2018
f1_keywords:
- vb.uinteger
helpviewer_keywords:
- numbers [Visual Basic], whole
- UInteger data type
- literal type characters [Visual Basic], UI
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- UI literal type characters [Visual Basic]
- data types [Visual Basic], integral
ms.assetid: db7ddd34-4f23-46f5-84dd-8b0f83bb8729
ms.openlocfilehash: 11070f6c7f3259b8c34528eb54d99b031b68f9f9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415544"
---
# <a name="uinteger-data-type"></a>UInteger (tipo di dati)

Include interi senza segno a 32 bit (4 byte) compresi tra 0 e 4.294.967.295.

## <a name="remarks"></a>Commenti

Il `UInteger` tipo di dati fornisce il valore senza segno più grande nella larghezza dei dati più efficiente.

Il valore predefinito di `UInteger` è 0.

## <a name="literal-assignments"></a>Assegnazioni di valori letterali

È possibile dichiarare e inizializzare una variabile assegnandogli un valore letterale `UInteger` decimale, un valore letterale esadecimale, un valore letterale ottale o (a partire da Visual Basic 2017) un valore letterale binario. Se il valore letterale integer è esterno all'intervallo di `UInteger`, vale a dire se è minore di <xref:System.UInt32.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.

Nell'esempio seguente, i valori interi uguali a 3.000.000.000 rappresentati come valori letterali decimali, esadecimali o binari vengono assegnati a valori `UInteger`.

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]

> [!NOTE]
> Usare il prefisso `&h` o `&H` per indicare un valore letterale esadecimale, il prefisso `&b` o `&B` per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale. I valori letterali decimali non hanno prefissi.

A partire da Visual Basic 2017, è anche possibile usare il carattere di sottolineatura, `_` , come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente.

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]

A partire da Visual Basic 15,5, è anche possibile usare il carattere di sottolineatura ( `_` ) come separatore iniziale tra il prefisso e le cifre esadecimali, binarie o ottali. Ad esempio:

```vb
Dim number As UInteger = &H_0F8C_0326
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

I valori letterali numerici possono includere anche il `UI` `ui` [carattere di tipo](../../programming-guide/language-features/data-types/type-characters.md) o per indicare il `UInteger` tipo di dati, come illustrato nell'esempio riportato di seguito.

```vb
Dim number = &H_0FAC_14D7ui
```

## <a name="programming-tips"></a>Suggerimenti per la programmazione

I `UInteger` `Integer` tipi di dati e offrono prestazioni ottimali in un processore a 32 bit, perché i tipi integer più piccoli ( `UShort` , `Short` , `Byte` e `SByte` ), anche se usano meno bit, richiedono più tempo per il caricamento, l'archiviazione e il recupero.

- **Numeri negativi.** Poiché `UInteger` è un tipo senza segno, non può rappresentare un numero negativo. Se si usa l'operatore unario meno ( `-` ) su un'espressione che restituisce il tipo `UInteger` , Visual Basic converte prima l'espressione in `Long` .

- **Conformità a CLS.** Il `UInteger` tipo di dati non fa parte del [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), pertanto il codice conforme a CLS non può utilizzare un componente che lo utilizza.

- **Considerazioni sull'interoperabilità.** Se si è connessi con componenti non scritti per il .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i tipi come `uint` possono avere una larghezza di dati diversa (16 bit) in altri ambienti. Se si passa un argomento a 16 bit a tale componente, dichiararlo come `UShort` anziché `UInteger` nel codice gestito del Visual Basic.

- **Conversioni.** Il `UInteger` tipo di dati viene ampliato in `Long` , `ULong` , `Decimal` , `Single` e `Double` . Ciò significa che è possibile `UInteger` eseguire la conversione in uno di questi tipi senza riscontrare un <xref:System.OverflowException?displayProperty=nameWithType> errore.

- **Digitare i caratteri.** L'aggiunta di caratteri di tipo letterale `UI` a un valore letterale impone il `UInteger` tipo di dati. `UInteger`non ha un carattere di tipo identificatore.

- **Tipo di framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.UInt32?displayProperty=nameWithType>.

## <a name="see-also"></a>Vedere anche

- <xref:System.UInt32>
- [Tipi di dati](index.md)
- [CString](../functions/type-conversion-functions.md)
- [Riepilogo della conversione](../keywords/conversion-summary.md)
- [Procedura: Chiamare una funzione Windows che accetta tipi senza segno](../../programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Uso efficiente dei tipi di dati](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
