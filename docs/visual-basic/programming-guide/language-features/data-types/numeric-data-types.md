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
ms.openlocfilehash: 1188e8288bb73a49acc3e3bf0f72e3ac4fef5f7a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54636414"
---
# <a name="numeric-data-types-visual-basic"></a>Tipi di dati numerici (Visual Basic)
Visual Basic fornisce diversi *tipi di dati numerici* per la gestione dei numeri nelle diverse rappresentazioni. *Integrale* tipi di rappresentano solo numeri interi (positivi, negativi e zero), e *non integrali* tipi rappresentano numeri con intera e una parte frazionaria.  
  
 Per una tabella che mostra un confronto side-by-side dei tipi di dati Visual Basic, vedere [tipi di dati](../../../../visual-basic/language-reference/data-types/index.md).  
  
## <a name="integral-numeric-types"></a>Tipi numerici integrali  
 *Tipi di dati integrali* sono quelli che rappresentano solo numeri senza parte frazionaria.  
  
 Il *firmati* sono tipi di dati integrali [tipo di dati SByte](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md) (8 bit), [tipo di dati Short](../../../../visual-basic/language-reference/data-types/short-data-type.md) (16 bit), [tipo di dati Integer](../../../../visual-basic/language-reference/data-types/integer-data-type.md) (32-bit) e [ Tipo di dati long](../../../../visual-basic/language-reference/data-types/long-data-type.md) (64 bit). Se una variabile archivia sempre numeri interi anziché i numeri frazionari, dichiararlo come uno di questi tipi.  
  
 Il *unsigned* sono tipi integrali [tipo di dati Byte](../../../../visual-basic/language-reference/data-types/byte-data-type.md) (8 bit), [tipo di dati UShort](../../../../visual-basic/language-reference/data-types/ushort-data-type.md) (16 bit), [tipo di dati UInteger](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md) (32 bit) e [ Tipo di dati ULong](../../../../visual-basic/language-reference/data-types/ulong-data-type.md) (64 bit). Se una variabile contiene dati binari o dati di natura sconosciuta, dichiararlo come uno di questi tipi.  
  
### <a name="performance"></a>Prestazioni  
 Operazioni aritmetiche sono più veloci con tipi integrali che con altri tipi di dati. Essi sono le più rapide con le `Integer` e `UInteger` tipi in Visual Basic.  
  
### <a name="large-integers"></a>Numeri interi grandi  
 Se è necessario contenere un numero intero maggiore di `Integer` può contenere il tipo di dati, è possibile usare il `Long` invece del tipo di dati. `Long` le variabili possono contenere numeri compresi tra 9.223.372.036.854.775.808 a 9.223.372.036.854.775.807. Operazioni con `Long` sono leggermente più lente con `Integer`.  
  
 Se sono necessari valori di dimensioni ancora maggiori, è possibile usare la [tipo di dati Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md). È possibile archiviare numeri compresi tra -79.228.162.514.264.337.593.543.950.335 tramite 79.228.162.514.264.337.593.543.950.335 in un `Decimal` variabile se non si usano tutte le posizioni decimali. Tuttavia, le operazioni con `Decimal` numeri sono decisamente più lenti rispetto con qualsiasi altro tipo di dati numerici.  
  
### <a name="small-integers"></a>Valori interi piccoli  
 Se non è necessaria l'intera gamma del `Integer` tipo di dati, è possibile usare il `Short` tipo di dati che può contenere numeri interi compresi tra -32.768 e 32.767. Per l'intervallo di integer più piccolo, il `SByte` tipo di dati contiene numeri interi compresi tra -128 e 127. Se si dispone di un numero molto elevato di variabili che contengono small integer, common language runtime a volte è possibile archiviare le `Short` e `SByte` variabili in modo più efficiente e ridurre il consumo di memoria. Tuttavia, le operazioni con `Short` e `SByte` sono lente rispetto a quelle con `Integer`.  
  
### <a name="unsigned-integers"></a>Unsigned Integer  
 Se si sa che la variabile non deve mai contenere un numero negativo, è possibile usare la *tipi senza segno*`Byte`, `UShort`, `UInteger`, e `ULong`. Ognuno di questi tipi di dati può contenere un numero intero positivo due volte più grande come relativo valore corrispondente di tipo con segno (`SByte`, `Short`, `Integer`, e `Long`). In termini di prestazioni, ogni tipo senza segno è esattamente efficiente quanto il tipo con segno corrispondente. In particolare `UInteger` condivide con `Integer` la distinzione di essere più efficiente di tutti i tipi di dati numerici di base.  
  
## <a name="nonintegral-numeric-types"></a>Tipi numerici non integrali  
 *Tipi di dati non integrale* sono quelli che rappresentano numeri con intera e una parte frazionaria.  
  
 Sono i tipi di dati numerico non integrale `Decimal` (a virgola fissa a 128 bit) [singolo tipo di dati](../../../../visual-basic/language-reference/data-types/single-data-type.md) (a virgola mobile a 32 bit) e [tipo di dati Double](../../../../visual-basic/language-reference/data-types/double-data-type.md) (a virgola mobile a 64 bit). Sono tutti tipi con segno. Se una variabile può contenere una frazione, dichiararlo come uno di questi tipi.  
  
 `Decimal` non è un tipo di dati a virgola mobile. `Decimal` i numeri hanno un valore integer binario e un fattore di scala di integer che specifica quale parte del valore è una frazione decimale.  
  
 È possibile usare `Decimal` variabili per i valori di denaro. Il vantaggio è la precisione dei valori. Il `Double` tipo di dati è più veloce e richiede la quantità di memoria inferiore, ma è soggetto a errori di arrotondamento. Il `Decimal` tipo di dati mantiene la precisione completa a 28 cifre decimali.  
  
 A virgola mobile (`Single` e `Double`) i numeri hanno intervalli più ampi rispetto a `Decimal` numeri ma possono essere soggette a errori di arrotondamento. Tipi a virgola mobile supportano meno cifre significative `Decimal` ma può rappresentare i valori dell'ordine di grandezza maggiore.  
  
 Valori numerici non integrali possono essere espresso come mmmEeee, in cui mmm è il *mantissa* (le cifre significative) e apparecchiature elettriche ed elettroniche è la *esponente* (potenza di 10). I valori più alti positivi dei tipi non integrali sono 7.9228162514264337593543950335 + 28 per `Decimal`, 3,4028235E + 38 per `Single`e 1.79769313486231570 e + 308 per `Double`.  
  
### <a name="performance"></a>Prestazioni  
 `Double` è la più efficiente dei tipi di dati frazionari, perché i processori in piattaforme corrente eseguono operazioni a virgola mobile a precisione doppia. Tuttavia, le operazioni con `Double` non sono veloci come con i tipi integrali, ad esempio `Integer`.  
  
### <a name="small-magnitudes"></a>Ordini di grandezza Small  
 Per i numeri con la grandezza più piccolo possibile (il più vicino a 0), `Double` le variabili possono contenere numeri - 4.94065645841246544-324 per i valori negativi e fino a 4.94065645841246544-324 per i valori positivi.  
  
### <a name="small-fractional-numbers"></a>Piccoli numeri frazionari  
 Se non è necessaria l'intera gamma del `Double` tipo di dati, è possibile usare il `Single` tipo di dati, che può contenere numeri a virgola mobile e compresi tra - 3,4028235E + 38 e 3,4028235E + 38. I più piccolo ordini di grandezza per `Single` variabili sono - 1,401298E-45 per valori negativi e tra 1,401298E-45 per valori positivi. Se si dispone di un numero molto elevato di variabili che contengono un numero limitato a virgola mobile, common language runtime a volte è possibile archiviare il `Single` variabili in modo più efficiente e ridurre il consumo di memoria.  
  
## <a name="see-also"></a>Vedere anche
- [Tipi di dati elementari](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Dati di tipo carattere](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)
- [Tipi di dati vari](../../../../visual-basic/programming-guide/language-features/data-types/miscellaneous-data-types.md)
- [Risoluzione dei problemi relativi ai tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Procedura: Chiamare una funzione Windows che accetta tipi senza segno](../../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
