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
ms.openlocfilehash: 72cdca295e209935687f67ad290e816775d9fe13
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393676"
---
# <a name="numeric-data-types-visual-basic"></a>Tipi di dati numerici (Visual Basic)
Visual Basic fornisce diversi *tipi di dati numerici* per la gestione di numeri in varie rappresentazioni. I tipi *integrali* rappresentano solo numeri interi (positivi, negativi e zero) e i tipi non *integrali* rappresentano numeri con parti intere e frazionarie.  
  
 Per una tabella che mostra un confronto affiancato dei tipi di dati Visual Basic, vedere tipi di [dati](../../../language-reference/data-types/index.md).  
  
## <a name="integral-numeric-types"></a>Tipi numerici integrali  
 I *tipi di dati integrali* sono quelli che rappresentano solo numeri senza parti frazionarie.  
  
 I tipi di dati integrali con *segno* sono [tipo di dati SByte](../../../language-reference/data-types/sbyte-data-type.md) (8 bit), [tipo di dati Short](../../../language-reference/data-types/short-data-type.md) (a 16 bit), [tipo di dati Integer](../../../language-reference/data-types/integer-data-type.md) (a 32 bit) e [tipo di dati Long](../../../language-reference/data-types/long-data-type.md) (64-bit). Se una variabile archivia sempre numeri interi anziché numeri frazionari, dichiararli come uno di questi tipi.  
  
 I tipi integrali *senza segno* sono [tipo di dati byte](../../../language-reference/data-types/byte-data-type.md) (8 bit), [tipo di dati ushort](../../../language-reference/data-types/ushort-data-type.md) (a 16 bit), [tipo di dati UInteger](../../../language-reference/data-types/uinteger-data-type.md) (32 bit) e [tipo di dati ulong](../../../language-reference/data-types/ulong-data-type.md) (64 bit). Se una variabile contiene dati binari o dati di natura sconosciuta, dichiararli come uno di questi tipi.  
  
### <a name="performance"></a>Prestazioni  
 Le operazioni aritmetiche sono più veloci con i tipi integrali rispetto ad altri tipi di dati. Sono più veloci con i `Integer` tipi e `UInteger` in Visual Basic.  
  
### <a name="large-integers"></a>Numeri interi grandi  
 Se è necessario mantenere un numero intero maggiore di quello che `Integer` può essere utilizzato dal tipo di dati, è possibile utilizzare il tipo di `Long` dati. `Long`le variabili possono ospitare numeri da-9.223.372.036.854.775.808 a 9.223.372.036.854.775.807. Le operazioni con `Long` sono leggermente più lente rispetto a `Integer` .  
  
 Se sono necessari valori ancora maggiori, è possibile usare il [tipo di dati Decimal](../../../language-reference/data-types/decimal-data-type.md). `Decimal`Se non si utilizzano posizioni decimali, è possibile mantenere i numeri da-79.228.162.514.264.337.593.543.950.335 a 79.228.162.514.264.337.593.543.950.335 in una variabile. Tuttavia, le operazioni con `Decimal` numeri sono notevolmente più lente rispetto a qualsiasi altro tipo di dati numerico.  
  
### <a name="small-integers"></a>Numeri interi piccoli  
 Se non è necessario l'intervallo completo del tipo di `Integer` dati, è possibile usare il `Short` tipo di dati, che può ospitare numeri interi compresi tra-32.768 e 32.767. Per l'intervallo di valori integer più piccolo, il `SByte` tipo di dati include numeri interi compresi tra-128 e 127. Se si dispone di un numero molto elevato di variabili che contengono numeri interi di piccole dimensioni, i Common Language Runtime a volte possono archiviare le `Short` variabili e in `SByte` modo più efficiente e risparmiare sull'utilizzo della memoria. Tuttavia, le operazioni con `Short` e `SByte` sono piuttosto più lente rispetto a `Integer` .  
  
### <a name="unsigned-integers"></a>Interi senza segno  
 Se si è certi che la variabile non deve mai avere un numero negativo, è possibile usare i *tipi non firmati* `Byte` ,, `UShort` `UInteger` e `ULong` . Ognuno di questi tipi di dati può avere un numero intero positivo due volte superiore al tipo con segno corrispondente ( `SByte` ,, `Short` `Integer` e `Long` ). In termini di prestazioni, ogni tipo senza segno è esattamente altrettanto efficiente del tipo con segno corrispondente. In particolare, `UInteger` condivide con `Integer` la differenza che è più efficiente di tutti i tipi di dati numerici elementari.  
  
## <a name="nonintegral-numeric-types"></a>Tipi numerici non integrali  
 I *tipi di dati non integrali* sono quelli che rappresentano numeri con parti intere e frazionarie.  
  
 I tipi di dati numerici non integrali sono `Decimal` (punto fisso a 128 bit), [tipo di dati singolo](../../../language-reference/data-types/single-data-type.md) (virgola mobile a 32 bit) e [tipo di dati Double](../../../language-reference/data-types/double-data-type.md) (virgola mobile a 64 bit). Sono tutti tipi firmati. Se una variabile può contenere una frazione, dichiararla come uno di questi tipi.  
  
 `Decimal`non è un tipo di dati a virgola mobile. `Decimal`i numeri hanno un valore integer binario e un fattore di scala integer che specifica quale parte del valore è una frazione decimale.  
  
 È possibile usare le `Decimal` variabili per i valori money. Il vantaggio è la precisione dei valori. Il `Double` tipo di dati è più veloce e richiede un minor numero di memoria, ma è soggetto a errori di arrotondamento. Il `Decimal` tipo di dati mantiene l'accuratezza completa per 28 posizioni decimali.  
  
 I numeri a virgola mobile ( `Single` e `Double` ) hanno intervalli maggiori dei `Decimal` numeri, ma possono essere soggetti a errori di arrotondamento. I tipi a virgola mobile supportano meno cifre significative di `Decimal` ma possono rappresentare valori di grandezza maggiore.  
  
 I valori numerici non integrali possono essere espressi come mmmEeee, in cui MMM è il *mantissa* (cifre significative) e Eee è l' *esponente* (una potenza di 10). I valori positivi più alti dei tipi non integrali sono 7.9228162514264337593543950335 E + 28 per `Decimal` , 3.4028235 e + 38 per `Single` e 1.79769313486231570 e + 308 per `Double` .  
  
### <a name="performance"></a>Prestazioni  
 `Double`è il più efficiente dei tipi di dati frazionari, perché i processori sulle piattaforme correnti eseguono operazioni a virgola mobile con precisione doppia. Tuttavia, le operazioni con `Double` non sono altrettanto veloci dei tipi integrali, ad esempio `Integer` .  
  
### <a name="small-magnitudes"></a>Magnitude ridotte  
 Per i numeri con la grandezza minima possibile (più vicino a 0), le `Double` variabili possono mantenere i numeri 4.94065645841246544 e-324 per i valori negativi e 4.94065645841246544 e-324 per i valori positivi.  
  
### <a name="small-fractional-numbers"></a>Numeri frazionari piccoli  
 Se non è necessario l'intervallo completo del tipo di `Double` dati, è possibile usare il `Single` tipo di dati, che può mantenere i numeri a virgola mobile da-3.4028235 e + 38 a 3.4028235 e + 38. Le Magnitude più piccole per le `Single` variabili sono-401298E e-45 per i valori negativi e 401298E e-45 per i valori positivi. Se si dispone di un numero molto elevato di variabili che contengono numeri a virgola mobile ridotti, i Common Language Runtime a volte possono archiviare le `Single` variabili in modo più efficiente e risparmiare sull'utilizzo della memoria.  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di dati elementari](elementary-data-types.md)
- [Tipi di dati carattere](character-data-types.md)
- [Tipi di dati vari](miscellaneous-data-types.md)
- [Risoluzione dei problemi relativi ai tipi di dati](troubleshooting-data-types.md)
- [Procedura: Chiamare una funzione Windows che accetta tipi senza segno](../../com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
