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
ms.openlocfilehash: 9e256e93d7857c8674a1d711fa9cafd3ed9a29f5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33591626"
---
# <a name="decimal-data-type-visual-basic"></a>Tipo di dati Decimal (Visual Basic)
Contiene con segno a 128 bit (16 byte) valori che rappresentano numeri integer a 96 bit (12 byte) scalati in base a una potenza variabile di 10. Il fattore di scala specifica il numero di cifre a destra del separatore decimale; è compreso tra 0 e 28. Con una scala pari a 0 (senza cifre decimali), il valore massimo possibile è + /-79.228.162.514.264.337.593.543.950.335 (+ /-7 .9228162514264337593543950335E + 28). Il valore più grande è + /-7,9228162514264337593543950335 con 28 cifre decimali, e il più piccolo valore diverso da zero è + /-0,0000000000000000000000000001 (+ /-1E-28).  
  
## <a name="remarks"></a>Note  
 Il `Decimal` tipo di dati fornisce il maggior numero di cifre significative per un numero. Supporta fino a 29 cifre significative e può rappresentare valori che superano 7,9228 x 10 ^ 28. È particolarmente adatto per i calcoli, ad esempio finanziario, che richiedono un elevato numero di cifre ma non è in grado di tollerare errori di arrotondamento.  
  
 Il valore predefinito di `Decimal` è 0.  
  
## <a name="programming-tips"></a>Suggerimenti per la programmazione  
  
-   **Precisione.** `Decimal` non è un tipo di dati a virgola mobile. Il `Decimal` struttura contiene un valore integer binario, insieme a un bit di segno e un numero intero fattore che specifica quale parte del valore è una frazione decimale di scala. Per questo motivo, `Decimal` numeri hanno una rappresentazione più precisa nella memoria di tipi a virgola mobile (`Single` e `Double`).  
  
-   **Prestazioni.** Il `Decimal` tipo di dati è il più lento di tutti i tipi numerici. È opportuno valutare l'importanza della precisione rispetto alle prestazioni prima di scegliere un tipo di dati.  
  
-   **Ampliamento.** Il `Decimal` può ampliarsi nel tipo di dati `Single` o `Double`. È pertanto possibile convertire `Decimal` a uno di questi tipi senza generare un <xref:System.OverflowException?displayProperty=nameWithType> errore.  
  
-   **Zeri finali.** Visual Basic non archivia gli zeri finali in un `Decimal` letterale. Tuttavia, un `Decimal` variabile conserva gli zeri finali acquisiti dal punto di vista. Questa condizione è illustrata nell'esempio seguente.  
  
    ```  
    Dim d1, d2, d3, d4 As Decimal  
    d1 = 2.375D  
    d2 = 1.625D  
    d3 = d1 + d2  
    d4 = 4.000D  
    MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &  
          ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))  
    ```  
  
     L'output di `MsgBox` nell'esempio precedente è il seguente:  
  
     D1 = profondità 2.375, d2 = 1.625, d3 = 4.000, d4 = 4  
  
-   **Caratteri tipo.** Aggiungendo il carattere di tipo letterale `D` a un valore letterale, se ne determina la conversione nel tipo di dati `Decimal`. Aggiungendo il carattere identificatore di tipo `@` a qualsiasi identificatore, se ne determina la conversione al tipo di dati `Decimal`.  
  
-   **Tipo di Framework.** Il tipo corrispondente in .NET Framework è la struttura <xref:System.Decimal?displayProperty=nameWithType>.  
  
## <a name="range"></a>Intervallo  
 Potrebbe essere necessario utilizzare il `D` tipo di carattere per assegnare un valore elevato per un `Decimal` variabile o costante. Questo è un requisito perché il compilatore interpreta un valore letterale come `Long` , a meno che un carattere di tipo letterale segue il valore letterale, come illustrato nell'esempio seguente.  
  
```  
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.  
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.  
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.  
```  
  
 La dichiarazione per `bigDec1` non produce un overflow perché il valore assegnato a esso è compreso nell'intervallo per `Long`. Il `Long` valore può essere assegnato per il `Decimal` variabile.  
  
 La dichiarazione per `bigDec2` genera un errore di overflow perché è troppo grande per il valore assegnato a esso `Long`. Poiché il valore letterale numerico innanzitutto non può essere interpretato come un `Long`, non può essere assegnato per il `Decimal` variabile.  
  
 Per `bigDec3`, il tipo di valore letterale di carattere `D` risolve il problema, forzando il compilatore a interpretare il valore letterale come un `Decimal` anziché come un `Long`.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Decimal?displayProperty=nameWithType>  
 <xref:System.Decimal.%23ctor%2A?displayProperty=nameWithType>  
 <xref:System.Math.Round%2A?displayProperty=nameWithType>  
 [Tipi di dati](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Tipo di dati Single](../../../visual-basic/language-reference/data-types/single-data-type.md)  
 [Tipo di dati Double](../../../visual-basic/language-reference/data-types/double-data-type.md)  
 [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
