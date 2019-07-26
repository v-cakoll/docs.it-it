---
title: Tipo di dati Decimal (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Decimal
helpviewer_keywords:
- literal type characters [Visual Basic], D
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- Decimal data type
- D literal type character [Visual Basic]
- decimals, Decimal data type
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- decimal keyword [Visual Basic]
- numbers [Visual Basic], real
- variable-precision numbers
- zeros, trailing
- '@ identifier type character'
- identifier type characters [Visual Basic], @
ms.assetid: 1d855b45-afe2-45b0-a623-96b6f63a43d5
ms.openlocfilehash: bab5a0bd7e0a85d550362bc3c1166566f6dcb81b
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512778"
---
# <a name="decimal-data-type-visual-basic"></a>Tipo di dati Decimal (Visual Basic)

Include valori con segno a 128 bit (16 byte) che rappresentano numeri interi a 96 bit (12 byte) ridimensionati in base a una potenza variabile di 10. Il fattore di scala specifica il numero di cifre a destra del separatore decimale. l'intervallo è compreso tra 0 e 28. Con una scala pari a 0 (senza posizioni decimali), il valore massimo possibile è +/-79.228.162.514.264.337.593.543.950.335 (+/-7.9228162514264337593543950335E + 28). Con 28 cifre decimali, il valore più grande è +/-7.9228162514264337593543950335 e il valore diverso da zero è +/-0,0000000000000000000000000001 (+/-1E-28).

## <a name="remarks"></a>Note

Il `Decimal` tipo di dati fornisce il maggior numero di cifre significative per un numero. Supporta fino a 29 cifre significative e può rappresentare valori superiori a 7,9228 x 10 ^ 28. È particolarmente adatto per i calcoli, ad esempio Financial, che richiedono un numero elevato di cifre ma non tollerano errori di arrotondamento.

Il valore predefinito di `Decimal` è 0.

## <a name="programming-tips"></a>Suggerimenti per la programmazione

- **Precisione.** `Decimal`non è un tipo di dati a virgola mobile. La `Decimal` struttura include un valore intero binario, insieme a un bit di segno e a un fattore di scala integer che specifica quale parte del valore è una frazione decimale. Per questo motivo, `Decimal` i numeri presentano una rappresentazione più precisa in memoria rispetto ai tipi a virgola `Double`mobile (`Single` e).

- **Prestazioni.** Il `Decimal` tipo di dati è il più lento di tutti i tipi numerici. Prima di scegliere un tipo di dati, è necessario valutare l'importanza della precisione rispetto alle prestazioni.

- **Conversioni.** Il `Decimal` tipo di dati viene convertito `Single` in `Double`o. Ciò significa che è possibile `Decimal` eseguire la conversione in uno di questi tipi senza riscontrare un <xref:System.OverflowException?displayProperty=nameWithType> errore.

- **Zeri finali.** Visual Basic non archivia gli zeri finali in un `Decimal` valore letterale. Una variabile, `Decimal` tuttavia, conserva gli zeri finali acquisiti in modo computazionale. Questa condizione è illustrata nell'esempio seguente.

  ```vb
  Dim d1, d2, d3, d4 As Decimal
  d1 = 2.375D
  d2 = 1.625D
  d3 = d1 + d2
  d4 = 4.000D
  MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &
        ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))
  ```

  L'output di `MsgBox` nell'esempio precedente è il seguente:

  ```
  d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4
  ```

- **Digitare i caratteri.** Aggiungendo il carattere di tipo letterale `D` a un valore letterale, se ne determina la conversione nel tipo di dati `Decimal`. Aggiungendo il carattere identificatore di tipo `@` a qualsiasi identificatore, se ne determina la conversione al tipo di dati `Decimal`.

- **Tipo di Framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.Decimal?displayProperty=nameWithType>.

## <a name="range"></a>Intervallo
 Potrebbe essere necessario usare il `D` carattere tipo per assegnare un valore di grandi dimensioni a una variabile o a una `Decimal` costante. Questo requisito è dovuto al fatto che il compilatore interpreta un `Long` valore letterale come a meno che un carattere di tipo letterale non segua il valore letterale, come illustrato nell'esempio seguente.

```vb
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.
```

La dichiarazione per `bigDec1` non produce un overflow perché il valore assegnato è compreso nell'intervallo per. `Long` Il `Long` valore può essere assegnato `Decimal` alla variabile.

La dichiarazione per `bigDec2` genera un errore di overflow perché il valore assegnato è troppo grande per. `Long` Poiché il valore letterale numerico non può essere prima `Long`interpretato come, non può essere assegnato `Decimal` alla variabile.

Per `bigDec3`, il carattere `D` di tipo letterale risolve il problema forzando il compilatore a `Decimal` interpretare il valore letterale come anziché come `Long`.

## <a name="see-also"></a>Vedere anche

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A?displayProperty=nameWithType>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [Tipi di dati](../../../visual-basic/language-reference/data-types/index.md)
- [Tipo di dati Single](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [Tipo di dati Double](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
