---
title: Tipo di dati Decimal
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
ms.openlocfilehash: d4d868ba7c05cf3c2d538de1217231df91d4f43d
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243323"
---
# <a name="decimal-data-type-visual-basic"></a>Tipo di dati Decimal (Visual Basic)

Contiene valori Signed a 128 bit (16 byte) che rappresentano numeri di tipo Integer a 96 bit (12 byte) scalati in base a una potenza variabile di 10. Il fattore di scala specifica il numero di cifre a destra del separatore decimale; è compreso tra 0 e 28. Con una scala pari a 0 (senza cifre decimali), il valore più grande possibile è :/-79.228.162.514.264.337.593.543.950.335 (z/-7228162514264337593543950335E-28). Con 28 posizioni decimali, il valore più grande è :/-7.228162514264337593543950335 e il valore diverso da zero più piccolo è /-0.00000000000000000000000000000001 (-1E-28).

## <a name="remarks"></a>Osservazioni

Il `Decimal` tipo di dati fornisce il maggior numero di cifre significative per un numero. Supporta fino a 29 cifre significative e può rappresentare valori superiori a 7,9228 x 10.28. È particolarmente adatto per calcoli, come quelli finanziari, che richiedono un numero elevato di cifre ma non possono tollerare errori di arrotondamento.

Il valore predefinito di `Decimal` è 0.

## <a name="programming-tips"></a>Suggerimenti per la programmazione

- **Precisione.** `Decimal`non è un tipo di dati a virgola mobile. La `Decimal` struttura contiene un valore integer binario, con un bit di segno e un fattore di scala integer che specifica quale parte del valore è una frazione decimale. Per questo `Decimal` motivo, i numeri hanno una rappresentazione`Single` `Double`più precisa in memoria rispetto ai tipi a virgola mobile ( e ).

- **Prestazione.** Il `Decimal` tipo di dati è il più lento di tutti i tipi numerici. È consigliabile valutare l'importanza della precisione rispetto alle prestazioni prima di scegliere un tipo di dati.

- **Ampliamento.** Il `Decimal` tipo di `Single` dati `Double`si allarga a o . Ciò significa `Decimal` che è possibile convertire in <xref:System.OverflowException?displayProperty=nameWithType> uno di questi tipi senza che si verifichi un errore.

- **Zeri finali.** Visual Basic non archivia gli `Decimal` zeri finali in un valore letterale. Tuttavia, `Decimal` una variabile mantiene tutti gli zeri finali acquisiti a livello di calcolo. Questa condizione è illustrata nell'esempio seguente.

  ```vb
  Dim d1, d2, d3, d4 As Decimal
  d1 = 2.375D
  d2 = 1.625D
  d3 = d1 + d2
  d4 = 4.000D
  MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &
        ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))
  ```

  L'output `MsgBox` di nell'esempio precedente è il seguente:

  ```console
  d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4
  ```

- **Digitare caratteri.** Aggiungendo il carattere di tipo letterale `D` a un valore letterale, se ne determina la conversione nel tipo di dati `Decimal`. Aggiungendo il carattere identificatore di tipo `@` a qualsiasi identificatore, se ne determina la conversione al tipo di dati `Decimal`.

- **Tipo di framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.Decimal?displayProperty=nameWithType>.

## <a name="range"></a>Range

 Potrebbe essere necessario `D` utilizzare il carattere di `Decimal` tipo per assegnare un valore elevato a una variabile o costante. Questo requisito è dovuto al `Long` fatto che il compilatore interpreta un valore letterale come a meno che un carattere di tipo letterale non segua il valore letterale, come illustrato nell'esempio seguente.

```vb
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.
```

La dichiarazione per `bigDec1` non produce un overflow perché il valore assegnato `Long`a essa rientra nell'intervallo per . Il `Long` valore può essere `Decimal` assegnato alla variabile.

La dichiarazione per `bigDec2` genera un errore di overflow perché il `Long`valore assegnato è troppo grande per . Poiché il valore letterale numerico `Long`non può prima essere `Decimal` interpretato come , non può essere assegnato alla variabile.

Per `bigDec3`, il `D` carattere di tipo letterale risolve il problema `Decimal` forzando `Long`il compilatore a interpretare il valore letterale come anziché come .

## <a name="see-also"></a>Vedere anche

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [Tipi di dati](../../../visual-basic/language-reference/data-types/index.md)
- [Tipo di dati Single](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [Tipo di dati Double](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Utilizzo efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
