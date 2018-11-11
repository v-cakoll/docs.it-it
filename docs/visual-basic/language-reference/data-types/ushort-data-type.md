---
title: Tipo di dati UShort (Visual Basic)
ms.date: 01/31/2018
f1_keywords:
- vb.ushort
helpviewer_keywords:
- numbers [Visual Basic], whole
- literal type characters [Visual Basic], US
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- UShort data type
- US literal type characters [Visual Basic]
ms.assetid: 138db892-665d-4ba8-9cae-d8d91c4a8f39
ms.openlocfilehash: a3d60747400d570a3e5a930377e9be9c0aca4f35
ms.sourcegitcommit: 296183dbe35077b5c5e5e74d5fbe7f399bc507ee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/05/2018
ms.locfileid: "50982711"
---
# <a name="ushort-data-type-visual-basic"></a>Tipo di dati UShort (Visual Basic)

Contiene interi senza segno a 16 bit (a 2 byte) nell'intervallo compreso tra 0 e 65.535.  
  
## <a name="remarks"></a>Note

 Usare la `UShort` tipo di dati per contenere dati binari troppo grandi per `Byte`.  
  
 Il valore predefinito di `UShort` è 0.  

# <a name="literal-assignments"></a>Assegnazioni di valori letterali

È possibile dichiarare e inizializzare un `UShort` variabile da assegnarle un valore letterale decimale, un valore letterale esadecimale, un valore letterale ottale, o (a partire da Visual Basic 2017) un valore letterale binario. Se il valore letterale integer è esterno all'intervallo di `UShort`, vale a dire se è minore di <xref:System.UInt16.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.UInt16.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.

Nell'esempio seguente, i valori interi uguali a 65,034 rappresentati come decimali, esadecimali o valori letterali binari vengono assegnati a `UShort` valori.
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> Il prefisso viene usato `&h` oppure `&H` per indicare un valore letterale esadecimale, il prefisso `&b` oppure `&B` per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale. I valori letterali decimali non hanno prefissi.

A partire da Visual Basic 2017, è anche possibile usare il carattere di sottolineatura `_`, come separatore di cifre per migliorare la leggibilità, come illustrato nell'esempio seguente viene illustrato.

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

A partire da Visual Basic 15.5, è anche possibile usare il carattere di sottolineatura (`_`) come separatore iniziale tra il prefisso e le cifre esadecimali, binarie o ottale. Ad esempio:

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Valori letterali numerici possono includere anche il `US` o `us` [Digita carattere](../../programming-guide/language-features/data-types/type-characters.md) per indicare il `UShort` tipo di dati, come illustrato nell'esempio seguente.

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a>Suggerimenti sulla programmazione
  
-   **Numeri negativi.** Poiché `UShort` è un tipo unsigned, non può rappresentare un numero negativo. Se si usa l'operatore meno unario (`-`) gli operatori di un'espressione che restituisce il tipo `UShort`, Visual Basic consente di convertire l'espressione da `Integer` prima.  
  
-   **Conformità a CLS.** Il `UShort` tipo di dati non è in parte il [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), in modo che il codice conforme a CLS non è possibile utilizzare un componente che lo usa.
  
-   **Ampliamento.** Il `UShort` può ampliarsi nel tipo di dati `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, e `Double`. Ciò significa che è possibile convertire `UShort` a uno di questi tipi senza generare un <xref:System.OverflowException?displayProperty=nameWithType> errore.  
  
-   **Caratteri tipo.** Aggiungendo i caratteri di tipo di valore letterale `US` a un valore letterale, se ne determina la `UShort` tipo di dati. `UShort` possiede alcun carattere di tipo identificatore.  
  
-   **Tipo di Framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.UInt16?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.UInt16>  
 [Tipi di dati](../../../visual-basic/language-reference/data-types/index.md)  
 [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Procedura: Chiamare una funzione Windows che accetta tipi senza segno](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
