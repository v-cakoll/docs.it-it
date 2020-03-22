---
title: Tipo di dati Byte
ms.date: 01/31/2018
f1_keywords:
- vb.Byte
helpviewer_keywords:
- Byte data type
- data types [Visual Basic], assigning
ms.assetid: eed44dff-eaee-4937-a89f-444e418e74f6
ms.openlocfilehash: 347d7e7d0f09e089886bc81bd0be659deaca9b46
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400743"
---
# <a name="byte-data-type-visual-basic"></a>Byte data type (Visual Basic)

Contiene interi senza segno a 8 bit (1 byte) compresi in un valore compreso tra 0 e 255.

## <a name="remarks"></a>Osservazioni

Utilizzare `Byte` il tipo di dati per contenere dati binari.  
  
Il valore predefinito di `Byte` è 0.

## <a name="literal-assignments"></a>Assegnazioni letterali

È possibile dichiarare `Byte` e inizializzare una variabile assegnandole un valore letterale decimale, un valore letterale esadecimale, un valore letterale ottale o (a partire da Visual Basic 2017) un valore letterale binario. Se il valore letterale integrale non è compreso nell'intervallo di un `Byte` oggetto , ovvero se è minore <xref:System.Byte.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.Byte.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.

Nell'esempio seguente, i numeri interi uguali a 201 rappresentati come valori letterali decimali, esadecimali e binari vengono convertiti in modo implicito da [Integer](integer-data-type.md) a `byte` valori.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Byte)]

> [!NOTE]
> Utilizzare il `&h` `&H` prefisso o per indicare un valore `&b` `&B` letterale esadecimale, il prefisso o per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale. I valori letterali decimali non hanno prefissi.

A partire da Visual Basic 2017, è `_`anche possibile utilizzare il carattere di sottolineatura, , come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente.

[!code-vb[Byte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ByteS)]  

A partire da Visual Basic 15.5, è`_`inoltre possibile utilizzare il carattere di sottolineatura ( ) come separatore iniziale tra il prefisso e le cifre esadecimali, binarie o ottali. Ad esempio:

```vb
Dim number As Byte = &H_6A
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

## <a name="programming-tips"></a>Suggerimenti per la programmazione

- **Numeri negativi.** Poiché `Byte` è un tipo senza segno, non può rappresentare un numero negativo. Se si utilizza l'operatore meno unario (`-` `Byte`) su un'espressione `Short` che restituisce type , Visual Basic converte l'espressione in prima.
  
- **Conversioni di formato.** Quando Visual Basic legge o scrive file o quando chiama DLL, metodi e proprietà, è possibile eseguire automaticamente la conversione tra i formati di dati. I dati `Byte` binari archiviati in variabili e matrici vengono mantenuti durante tali conversioni di formato. Non utilizzare una `String` variabile per i dati binari, perché il suo contenuto può essere danneggiato durante la conversione tra i formati ANSI e Unicode.

- **Ampliamento.** Il `Byte` tipo di `Short`dati `UShort` `Integer`si `UInteger` `Long`allarga a , , , , `ULong`, `Decimal` `Single`, o `Double`. Ciò significa `Byte` che è possibile eseguire la <xref:System.OverflowException?displayProperty=nameWithType> conversione in uno qualsiasi di questi tipi senza che si verifichi un errore.
  
- **Digitare caratteri.** `Byte`non dispone di alcun carattere di tipo letterale o tipo di identificatore.

- **Tipo di framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.Byte?displayProperty=nameWithType>.

## <a name="example"></a>Esempio

 Nell'esempio seguente, `b` `Byte` è una variabile. Le istruzioni illustrano l'intervallo della variabile e l'applicazione di operatori di spostamento di bit.

 [!code-vb[VbVbalrDataTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#16)]  

## <a name="see-also"></a>Vedere anche

- <xref:System.Byte?displayProperty=nameWithType>
- [Tipi di dati](../../../visual-basic/language-reference/data-types/index.md)
- [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Utilizzo efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
