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
ms.openlocfilehash: ffc1cd141ba624d2ce26e4b1c070431ff0ddd6fe
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "44036194"
---
# <a name="decimal-data-type-visual-basic"></a>Tipo di dati Decimal (Visual Basic)
Contiene con segno a 128 bit (16 byte) valori che rappresentano numeri integer a 96 bit (12 byte) scalati in base una potenza variabile di 10. Il fattore di scala specifica il numero di cifre a destra del separatore decimale; è compreso tra 0 e 28. Con una scala pari a 0 (nessuna posizione decimale), il massimo valore possibile è + /-79.228.162.514.264.337.593.543.950.335 (+ /-7 .9228162514264337593543950335E + 28). Il valore massimo è + /-7,9228162514264337593543950335 con 28 posizioni decimali, e il più piccolo valore diverso da zero è + /-0,0000000000000000000000000001 (+ /-1E-28).  
  
## <a name="remarks"></a>Note  
 Il `Decimal` tipo di dati fornisce il maggior numero di cifre significative per un numero. Supporta fino a 29 cifre significative e può rappresentare i valori che superano 7,9228 x 10 ^ 28. È particolarmente adatto per i calcoli, come finanziario, che richiedono un elevato numero di cifre, ma non è in grado di tollerare errori di arrotondamento.  
  
 Il valore predefinito di `Decimal` è 0.  
  
## <a name="programming-tips"></a>Suggerimenti per la programmazione  
  
-   **Precisione.** `Decimal` non è un tipo di dati a virgola mobile. Il `Decimal` struttura contiene un valore integer binario, insieme ai bit di segno e un numero intero che specifica quale parte del valore è una frazione decimale fattore di scala. Ne consegue `Decimal` numeri di avere una rappresentazione più precisa in memoria rispetto a tipi a virgola mobile (`Single` e `Double`).  
  
-   **Prestazioni.** Il `Decimal` tipo di dati è il più lento di tutti i tipi numerici. È opportuno valutare l'importanza della precisione rispetto alle prestazioni prima di scegliere un tipo di dati.  
  
-   **Ampliamento.** Il `Decimal` può ampliarsi nel tipo di dati `Single` o `Double`. Ciò significa che è possibile convertire `Decimal` a uno di questi tipi senza generare un <xref:System.OverflowException?displayProperty=nameWithType> errore.  
  
-   **Zeri finali.** Visual Basic non archivia gli zeri finali in un `Decimal` letterale. Tuttavia, un `Decimal` variabile mantiene gli zeri finali acquisiti dal punto di vista. Questa condizione è illustrata nell'esempio seguente.  
  
    ```  
    Dim d1, d2, d3, d4 As Decimal  
    d1 = 2.375D  
    d2 = 1.625D  
    d3 = d1 + d2  
    d4 = 4.000D  
    MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &  
          ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))  
    ```  
  
     L'output di `MsgBox` nell'esempio precedente è come segue:  
  
     D1 = profondità 2.375, d2 = 1.625, d3 = 4.000, d4 = 4  
  
-   **Caratteri tipo.** Aggiungendo il carattere di tipo letterale `D` a un valore letterale, se ne determina la conversione nel tipo di dati `Decimal`. Aggiungendo il carattere identificatore di tipo `@` a qualsiasi identificatore, se ne determina la conversione al tipo di dati `Decimal`.  
  
-   **Tipo di Framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.Decimal?displayProperty=nameWithType>.  
  
## <a name="range"></a>Intervallo  
 Potrebbe essere necessario usare il `D` tipo di carattere per assegnare un valore elevato per un `Decimal` variabile o costante. Questo requisito è perché il compilatore interpreta un valore letterale come `Long` , a meno che un carattere letterale di tipo segue il valore letterale, come illustrato nell'esempio seguente.  
  
```  
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.  
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.  
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.  
```  
  
 La dichiarazione `bigDec1` non produce un overflow perché il valore assegnato a esso rientra nell'intervallo per `Long`. Il `Long` valore può essere assegnato al `Decimal` variabile.  
  
 La dichiarazione `bigDec2` genera un errore di overflow perché è troppo grande per il valore assegnato a esso `Long`. Poiché i valori letterali numerici non possono essere interpretato prima di tutto come un `Long`, non può essere assegnato per il `Decimal` variabile.  
  
 Per la `bigDec3`, il carattere di tipo letterale `D` risolve il problema, forzando il compilatore a interpretare il valore letterale come una `Decimal` anziché come un `Long`.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Decimal?displayProperty=nameWithType>  
 <xref:System.Decimal.%23ctor%2A?displayProperty=nameWithType>  
 <xref:System.Math.Round%2A?displayProperty=nameWithType>  
 [Tipi di dati](../../../visual-basic/language-reference/data-types/index.md)  
 [Tipo di dati Single](../../../visual-basic/language-reference/data-types/single-data-type.md)  
 [Tipo di dati Double](../../../visual-basic/language-reference/data-types/double-data-type.md)  
 [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
