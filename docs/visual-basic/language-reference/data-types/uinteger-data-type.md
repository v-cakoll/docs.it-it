---
title: Tipo di dati UInteger
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.uinteger
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
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f3852bd56d11c19e327e6c2f3e23cfb082a54e0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="uinteger-data-type"></a>UInteger (tipo di dati)

Contiene interi senza segno a 32 bit (4 byte) nell'intervallo compreso tra 0 e 4.294.967.295.  
  
## <a name="remarks"></a>Note

 Il `UInteger` tipo di dati fornisce il valore senza segno maggiore larghezza di dati più efficiente.  
  
 Il valore predefinito di `UInteger` è 0.  
  
## <a name="literal-assignments"></a>Assegnazioni di valori letterali

È possibile dichiarare e inizializzare un `UInteger` variabile assegnando il valore letterale decimale, valore letterale esadecimale, un valore letterale ottale, o (a partire da Visual Basic 2017) un valore letterale binario. Se il valore letterale integer è esterno all'intervallo di `UInteger`, vale a dire se è minore di <xref:System.UInt32.MinValue?displayProperty=nameWithType> o maggiore di <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, si verifica un errore di compilazione.

Nell'esempio seguente, i valori interi uguali a 3.000.000.000 rappresentati come valori letterali decimali, esadecimali o binari vengono assegnati a valori `UInteger`.
  
[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]  

> [!NOTE] 
> Utilizzare il prefisso `&h` o `&H` per indicare un valore letterale esadecimale, il prefisso `&b` o `&B` per indicare un valore letterale binario e il prefisso `&o` o `&O` per indicare un valore letterale ottale. I valori letterali decimali non hanno prefissi.

A partire da Visual Basic 2017, è inoltre possibile utilizzare il carattere di sottolineatura, `_`, come un separatore di cifre per migliorare la leggibilità, come nell'esempio seguente viene illustrato.

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]  

Valori letterali numerici possono includere anche il `UI` o `ui` [carattere tipo](../../programming-guide\language-features\data-types/type-characters.md) per indicare il `UInteger` il tipo di dati, come illustrato nell'esempio seguente.

```vb
Dim number = &H0FAC14D7ui
```

## <a name="programming-tips"></a>Suggerimenti sulla programmazione

 Il `UInteger` e `Integer` tipi di dati forniscono prestazioni ottimali in un processore a 32 bit, poiché i tipi integer più piccolo (`UShort`, `Short`, `Byte`, e `SByte`), anche se utilizzano un numero inferiore di bits, richiedono più tempo caricare, archiviare e recuperare.  
  
-   **Numeri negativi.** Poiché `UInteger` è un tipo unsigned, non può rappresentare un numero negativo. Se si utilizza l'operatore meno unario (`-`) gli operatori di un'espressione che restituisce al tipo `UInteger`, Visual Basic converte l'espressione `Long` prima.  
  
-   **Conformità a CLS.** Il `UInteger` tipo di dati non è in parte il [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), pertanto codice conforme a CLS non può utilizzare un componente che utilizza tale.
  
-   **Considerazioni sull'interoperabilità.** Se si prevede l'interazione con componenti non scritti per .NET Framework, ad esempio oggetti COM o di automazione, tenere presente che i tipi, ad esempio `uint` può avere un'ampiezza dei dati diversa (16 bit) in altri ambienti. Se si passa un argomento a 16 bit a tale componente, dichiararla come `UShort` anziché `UInteger` nel codice gestito di Visual Basic.  
  
-   **Ampliamento.** Il `UInteger` può ampliarsi nel tipo di dati `Long`, `ULong`, `Decimal`, `Single`, e `Double`. È pertanto possibile convertire `UInteger` a uno di questi tipi senza generare un <xref:System.OverflowException?displayProperty=nameWithType> errore.  
  
-   **Caratteri tipo.** Aggiungendo i caratteri di tipo letterale `UI` a un valore letterale indica al sistema di `UInteger` tipo di dati. `UInteger`non include alcun carattere di tipo identificatore.  
  
-   **Tipo di Framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.UInt32?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.UInt32>  
 [Tipi di dati](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Procedura: Chiamare una funzione Windows che accetta tipi senza segno](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
