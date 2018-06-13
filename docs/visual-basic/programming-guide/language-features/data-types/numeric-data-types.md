---
title: Tipi di dati numerici (Visual Basic)
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
ms.openlocfilehash: 8fa88172c9914a071e1b24e959c9030e6d219a30
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654203"
---
# <a name="numeric-data-types-visual-basic"></a>Tipi di dati numerici (Visual Basic)
Visual Basic fornisce diversi *tipi di dati numerici* per gestire i numeri in diverse rappresentazioni. *Integrale* tipi rappresentano solo numeri interi (positivi, negativi e zero), e *non integrali* tipi rappresentano numeri con entrambi numero intero e frazione.  
  
 Per una tabella che mostra un confronto side-by-side dei tipi di dati Visual Basic, vedere [tipi di dati](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## <a name="integral-numeric-types"></a>Tipi numerici integrali  
 *Tipi di dati integrali* sono quelli che rappresentano solo i numeri senza parti frazionarie.  
  
 Il *firmato* sono tipi di dati integrali [tipo di dati SByte](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md) (8 bit), [tipo di dati Short](../../../../visual-basic/language-reference/data-types/short-data-type.md) (16 bit), [tipo di dati Integer](../../../../visual-basic/language-reference/data-types/integer-data-type.md) (32 bit) e [ Tipo di dati long](../../../../visual-basic/language-reference/data-types/long-data-type.md) (64 bit). Se una variabile memorizza sempre numeri interi anziché numeri frazionari, dichiararla come uno di questi tipi.  
  
 Il *senza segno* tipi integrali sono [tipo di dati Byte](../../../../visual-basic/language-reference/data-types/byte-data-type.md) (8 bit), [tipo di dati UShort](../../../../visual-basic/language-reference/data-types/ushort-data-type.md) (16 bit), [tipo di dati UInteger](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md) (32 bit) e [ Tipo di dati ULong](../../../../visual-basic/language-reference/data-types/ulong-data-type.md) (64 bit). Se una variabile contiene dati binari o dati di natura sconosciuta, dichiararla come uno di questi tipi.  
  
### <a name="performance"></a>Prestazioni  
 Operazioni aritmetiche sono più veloci con tipi integrali che con altri tipi di dati. Sono più veloci con il `Integer` e `UInteger` tipi in Visual Basic.  
  
### <a name="large-integers"></a>Numeri interi grandi  
 Se è necessario includere un numero intero maggiore di `Integer` può contenere il tipo di dati, è possibile utilizzare il `Long` invece del tipo di dati. `Long` le variabili possono contenere numeri compresi tra -9.223.372.036.854.775.808 a 9.223.372.036.854.775.807. Operazioni con `Long` sono leggermente più lente con `Integer`.  
  
 Se sono necessari valori di dimensioni ancora maggiori, è possibile utilizzare il [tipo di dati Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md). È possibile archiviare numeri compresi tra -79.228.162.514.264.337.593.543.950.335 e 79.228.162.514.264.337.593.543.950.335 in un `Decimal` variabile se non si utilizzano tutte le posizioni decimali. Tuttavia, le operazioni con `Decimal` numeri sono molto più lenti con qualsiasi altro tipo di dati numerici.  
  
### <a name="small-integers"></a>Small integer  
 Se non è necessaria l'intera gamma del `Integer` tipo di dati, è possibile utilizzare il `Short` tipo di dati, che può contenere valori integer compresi tra -32.768 e 32.767. Per l'intervallo di integer più piccolo, il `SByte` tipo di dati contiene numeri interi compresi tra -128 e 127. Se si dispone di un numero molto elevato di variabili che contengono small integer, common language runtime in alcuni casi è possibile archiviare il `Short` e `SByte` variabili in modo efficace e ridurre il consumo di memoria. Tuttavia, le operazioni con `Short` e `SByte` sono leggermente più lente con `Integer`.  
  
### <a name="unsigned-integers"></a>Numeri interi senza segno  
 Se si è certi che la variabile non deve mai contenere un numero negativo, è possibile utilizzare il *tipi senza segno*`Byte`, `UShort`, `UInteger`, e `ULong`. Ognuno di questi tipi di dati può contenere un numero intero positivo due volte più grande come corrispondente tipo con segno (`SByte`, `Short`, `Integer`, e `Long`). In termini di prestazioni, un tipo senza segno è esattamente efficiente quanto il tipo con segno corrispondente. In particolare, `UInteger` condivide con `Integer` sono più efficiente di tutti i tipi di dati numerici di base.  
  
## <a name="nonintegral-numeric-types"></a>Tipi numerici non integrali  
 *Tipi di dati non integrale* sono quelli che rappresentano numeri con entrambi numero intero e frazione.  
  
 I tipi di dati numerici non integrali sono `Decimal` (a virgola fissa a 128 bit), [singolo tipo di dati](../../../../visual-basic/language-reference/data-types/single-data-type.md) (a virgola mobile a 32 bit) e [tipo di dati Double](../../../../visual-basic/language-reference/data-types/double-data-type.md) (a virgola mobile a 64 bit). Si tratta di tipi tutti firmati. Se una variabile può contenere una frazione, dichiararla come uno di questi tipi.  
  
 `Decimal` non è un tipo di dati a virgola mobile. `Decimal` numeri contengono un valore integer binario e un fattore di scala integer che specifica quale parte del valore è una frazione decimale.  
  
 È possibile utilizzare `Decimal` variabili per valori di valuta. Il vantaggio è la precisione dei valori. Il `Double` tipo di dati è più veloce e richiede una minore quantità di memoria, ma è soggetto a errori di arrotondamento. Il `Decimal` tipo di dati mantiene la massima precisione a 28 cifre decimali.  
  
 A virgola mobile (`Single` e `Double`) i numeri hanno intervalli più ampi rispetto `Decimal` numeri, ma può essere soggetta a errori di arrotondamento. Tipi a virgola mobile supportano un numero di cifre significative rispetto a `Decimal` ma può rappresentare valori dell'ordine di grandezza maggiore.  
  
 Valori numerici non integrali possono essere espresso come mmmEeee, ovvero mmm il *mantissa* (le cifre significative) e apparecchiature elettriche ed elettroniche è il *esponente* (una potenza di 10). I valori più alti positivo dei tipi non integrali sono 7.9228162514264337593543950335 + 28 per `Decimal`, 3, 4028235E + 38 per `Single`e 1.79769313486231570 e + 308 per `Double`.  
  
### <a name="performance"></a>Prestazioni  
 `Double` è la più efficiente dei tipi di dati frazionari, poiché i processori in piattaforme corrente eseguono operazioni a virgola mobile a precisione doppia. Tuttavia, le operazioni con `Double` non sono veloci come con i tipi integrali, ad esempio `Integer`.  
  
### <a name="small-magnitudes"></a>Grandezza di piccole dimensioni  
 Per i numeri con la grandezza più piccolo possibile (il più vicino a 0), `Double` le variabili possono contenere numeri - 4.94065645841246544-324 per i valori negativi e 4, 94065645841246544E-324 per i valori positivi.  
  
### <a name="small-fractional-numbers"></a>Numeri frazionari piccoli  
 Se non è necessaria l'intera gamma del `Double` tipo di dati, è possibile utilizzare il `Single` tipo di dati, che può contenere numeri a virgola mobile da - 3, 4028235E + 38 a 3, 4028235E + 38. La grandezza più piccolo per `Single` le variabili sono - 1, 401298E-45 per i valori negativi e 1, 401298E-45 per i valori positivi. Se si dispone di un numero molto elevato di variabili che contengono numeri a virgola mobile piccoli, common language runtime in alcuni casi è possibile archiviare il `Single` variabili in modo efficace e ridurre il consumo di memoria.  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di dati elementari](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Dati di tipo carattere](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)  
 [Tipi di dati vari](../../../../visual-basic/programming-guide/language-features/data-types/miscellaneous-data-types.md)  
 [Risoluzione dei problemi relativi ai tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Procedura: Chiamare una funzione Windows che accetta tipi senza segno](../../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
