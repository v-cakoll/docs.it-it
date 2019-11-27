---
title: Tipi di dati numerici
ms.date: 07/20/2015
helpviewer_keywords:
- integral types [Visual Basic], Visual Basic
- Short data type [Visual Basic], numeric data types
- Double data type [Visual Basic], numeric data types
- Long data type [Visual Basic], Visual Basic numeric data types
- numbers [Visual Basic], whole
- fractions
- numbers
- whole numbers
- integer numbers
- numbers [Visual Basic], integer
- fractional data types [Visual Basic]
- mantissas, of fractional numbers
- mantissas
- data types [Visual Basic], numeric
- Integer data type [Visual Basic], numeric data types
- exponent, of fractional numbers
- integers [Visual Basic]
- numeric data types [Visual Basic], Visual Basic
- Single data type [Visual Basic], numeric types
- Decimal data type [Visual Basic], numeric data types
ms.assetid: a27bd4d0-7e14-43eb-9cc4-b42eaab323c9
ms.openlocfilehash: dc8b630eebc48e5733344a00664b453360769c0b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346316"
---
# <a name="numeric-data-types-visual-basic"></a>Tipi di dati numerici (Visual Basic)
Visual Basic fornisce diversi *tipi di dati numerici* per la gestione di numeri in varie rappresentazioni. I tipi *integrali* rappresentano solo numeri interi (positivi, negativi e zero) e i tipi non *integrali* rappresentano numeri con parti intere e frazionarie.  
  
 Per una tabella che mostra un confronto affiancato dei tipi di dati Visual Basic, vedere tipi di [dati](../../../../visual-basic/language-reference/data-types/index.md).  
  
## <a name="integral-numeric-types"></a>Tipi numerici integrali  
 I *tipi di dati integrali* sono quelli che rappresentano solo numeri senza parti frazionarie.  
  
 I tipi di dati integrali con *segno* sono [tipo di dati SByte](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md) (8 bit), [tipo di dati Short](../../../../visual-basic/language-reference/data-types/short-data-type.md) (a 16 bit), [tipo di dati Integer](../../../../visual-basic/language-reference/data-types/integer-data-type.md) (a 32 bit) e [tipo di dati Long](../../../../visual-basic/language-reference/data-types/long-data-type.md) (64-bit). Se una variabile archivia sempre numeri interi anziché numeri frazionari, dichiararli come uno di questi tipi.  
  
 I tipi integrali *senza segno* sono [tipo di dati byte](../../../../visual-basic/language-reference/data-types/byte-data-type.md) (8 bit), [tipo di dati ushort](../../../../visual-basic/language-reference/data-types/ushort-data-type.md) (a 16 bit), [tipo di dati UInteger](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md) (32 bit) e [tipo di dati ulong](../../../../visual-basic/language-reference/data-types/ulong-data-type.md) (64 bit). Se una variabile contiene dati binari o dati di natura sconosciuta, dichiararli come uno di questi tipi.  
  
### <a name="performance"></a>Prestazioni  
 Le operazioni aritmetiche sono più veloci con i tipi integrali rispetto ad altri tipi di dati. Sono più veloci con i tipi di `Integer` e `UInteger` in Visual Basic.  
  
### <a name="large-integers"></a>Numeri interi grandi  
 Se è necessario mantenere un valore integer maggiore di quello `Integer` può essere utilizzato il tipo di dati, è invece possibile utilizzare il tipo di dati `Long`. `Long` variabili possono ospitare numeri da-9.223.372.036.854.775.808 a 9.223.372.036.854.775.807. Le operazioni con `Long` sono leggermente più lente rispetto a `Integer`.  
  
 Se sono necessari valori ancora maggiori, è possibile usare il [tipo di dati Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md). È possibile mantenere i numeri da-79.228.162.514.264.337.593.543.950.335 a 79.228.162.514.264.337.593.543.950.335 in una variabile `Decimal` se non si utilizzano posizioni decimali. Tuttavia, le operazioni con numeri di `Decimal` sono notevolmente più lente rispetto a qualsiasi altro tipo di dati numerico.  
  
### <a name="small-integers"></a>Numeri interi piccoli  
 Se non è necessario l'intervallo completo del tipo di dati `Integer`, è possibile usare il tipo di dati `Short`, che può ospitare numeri interi compresi tra-32.768 e 32.767. Per l'intervallo di valori integer più piccolo, il tipo di dati `SByte` include numeri interi compresi tra-128 e 127. Se si dispone di un numero molto elevato di variabili che contengono numeri interi di piccole dimensioni, il Common Language Runtime a volte può archiviare le variabili `Short` e `SByte` in modo più efficiente e risparmiare sull'utilizzo della memoria. Tuttavia, le operazioni con `Short` e `SByte` sono piuttosto più lente rispetto a `Integer`.  
  
### <a name="unsigned-integers"></a>Interi senza segno  
 Se si è certi che la variabile non deve mai avere un numero negativo, è possibile usare i *tipi senza segno*`Byte`, `UShort`, `UInteger`e `ULong`. Ognuno di questi tipi di dati può avere un numero intero positivo due volte superiore al tipo con segno corrispondente (`SByte`, `Short`, `Integer`e `Long`). In termini di prestazioni, ogni tipo senza segno è esattamente altrettanto efficiente del tipo con segno corrispondente. In particolare, `UInteger` condivide con `Integer` la distinzione tra il più efficiente di tutti i tipi di dati numerici elementari.  
  
## <a name="nonintegral-numeric-types"></a>Tipi numerici non integrali  
 I *tipi di dati non integrali* sono quelli che rappresentano numeri con parti intere e frazionarie.  
  
 I tipi di dati numerici non integrali sono `Decimal` (punto fisso a 128 bit), [tipo di dati singolo](../../../../visual-basic/language-reference/data-types/single-data-type.md) (virgola mobile a 32 bit) e [tipo di dati Double](../../../../visual-basic/language-reference/data-types/double-data-type.md) (a virgola mobile 64 bit). Sono tutti tipi firmati. Se una variabile può contenere una frazione, dichiararla come uno di questi tipi.  
  
 `Decimal` non è un tipo di dati a virgola mobile. i numeri di `Decimal` hanno un valore integer binario e un fattore di scala integer che specifica quale parte del valore è una frazione decimale.  
  
 È possibile utilizzare `Decimal` variabili per i valori money. Il vantaggio è la precisione dei valori. Il tipo di dati `Double` è più veloce e richiede un minor numero di memoria, ma è soggetto a errori di arrotondamento. Il tipo di dati `Decimal` mantiene l'accuratezza completa per 28 posizioni decimali.  
  
 I numeri a virgola mobile (`Single` e `Double`) hanno intervalli maggiori rispetto ai numeri `Decimal` ma possono essere soggetti a errori di arrotondamento. I tipi a virgola mobile supportano meno cifre significative rispetto a `Decimal` ma possono rappresentare valori di grandezza maggiore.  
  
 I valori numerici non integrali possono essere espressi come mmmEeee, in cui MMM è il *mantissa* (cifre significative) e Eee è l' *esponente* (una potenza di 10). I valori positivi più alti dei tipi non integrali sono 7.9228162514264337593543950335 E + 28 per `Decimal`, 3.4028235 E + 38 per `Single`e 1.79769313486231570 e + 308 per `Double`.  
  
### <a name="performance"></a>Prestazioni  
 `Double` è il più efficiente dei tipi di dati frazionari, perché i processori sulle piattaforme correnti eseguono operazioni a virgola mobile con precisione doppia. Tuttavia, le operazioni con `Double` non sono altrettanto veloci dei tipi integrali, ad esempio `Integer`.  
  
### <a name="small-magnitudes"></a>Magnitude ridotte  
 Per i numeri con la grandezza minima possibile (più vicino a 0), le variabili `Double` possono conservare i numeri come-4.94065645841246544 E-324 per i valori negativi e 4.94065645841246544 E-324 per i valori positivi.  
  
### <a name="small-fractional-numbers"></a>Numeri frazionari piccoli  
 Se non è necessario l'intervallo completo del tipo di dati `Double`, è possibile usare il tipo di dati `Single`, che può mantenere i numeri a virgola mobile da-3.4028235 E + 38 a 3.4028235 E + 38. Le Magnitude più piccole per le variabili `Single` sono-401298E E-45 per i valori negativi e 401298E e-45 per i valori positivi. Se si dispone di un numero molto elevato di variabili che contengono piccoli numeri a virgola mobile, il Common Language Runtime a volte archivia le variabili di `Single` in modo più efficiente e risparmia l'utilizzo della memoria.  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di dati elementari](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Dati di tipo carattere](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)
- [Tipi di dati vari](../../../../visual-basic/programming-guide/language-features/data-types/miscellaneous-data-types.md)
- [Risoluzione dei problemi relativi ai tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Procedura: Chiamare una funzione Windows che accetta tipi senza segno](../../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
