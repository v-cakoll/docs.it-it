---
title: Riepilogo dei tipi di dati
ms.date: 07/20/2015
helpviewer_keywords:
- Boolean data type [Visual Basic], supported types in Visual Basic
- storage [Visual Basic], order of storage
- data types [Visual Basic], Visual Basic
- Single data type [Visual Basic], supported types in Visual Basic
- notation [Visual Basic], scientific
- memory requirements, data types
- user-defined data types [Visual Basic], Visual Basic
- Date data type [Visual Basic], Visual Basic
- Visual Basic, data types
- storage [Visual Basic], allocation
- Integer data type [Visual Basic], Visual Basic data types
- storage [Visual Basic], space
- Variant data types [Visual Basic], supported types in Visual Basic
- Char data type [Visual Basic], Visual Basic data types
- intrinsic data types [Visual Basic]
- memory consumption [Visual Basic], data types
- single-precision numbers
- data types [Visual Basic], order of storage
- Long data type [Visual Basic], supported types in Visual Basic
- String data type [Visual Basic], Visual Basic data types
- storage order, data types
- StructLayoutAttribute class, Visual Basic data type storage
- scientific notation
- Double data type [Visual Basic], Visual Basic data types
- Byte data type [Visual Basic], Visual Basic data types
- Object data type [Visual Basic], supported types in Visual Basic
- data types [Visual Basic], storage allocation
- double-precision numbers
- data types [Visual Basic], summary
- dates [Visual Basic], data types
- strings [Visual Basic], data types
- memory consumption
- storage order, controlling in Visual Basic
- data types [Visual Basic], memory requirements
ms.assetid: e975cdb6-64d8-4a4a-ae27-f3b3ed198ae0
ms.openlocfilehash: 5eb52ef937a677c0b7498d058b5a39a375351ddc
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415622"
---
# <a name="data-type-summary-visual-basic"></a>Riepilogo dei tipi di dati (Visual Basic)

La tabella seguente illustra i tipi di dati Visual Basic, i tipi di Common Language Runtime di supporto, l'allocazione nominale dello spazio di archiviazione e i relativi intervalli di valori.  
  
|Tipo di Visual Basic|Struttura del tipo Common Language Runtime|Allocazione di spazio di archiviazione nominale|Intervallo di valori|  
|-----------------------|--------------------------------------------|--------------------------------|-----------------|  
|[Boolean](boolean-data-type.md)|<xref:System.Boolean>|Dipende dalla piattaforma di implementazione|`True` o `False`|  
|[Byte](byte-data-type.md)|<xref:System.Byte>|1 byte|da 0 a 255 (senza segno)|  
|[Char](char-data-type.md) (carattere singolo)|<xref:System.Char>|2 byte|da 0 a 65535 (senza segno)|  
|[Data](date-data-type.md)|<xref:System.DateTime>|8 byte|0:00:00 (mezzanotte) il 1 ° gennaio 0001-11:59:59 PM il 31 dicembre 9999|  
|[Decimale](decimal-data-type.md)|<xref:System.Decimal>|16 byte|da 0 a +/-79.228.162.514.264.337.593.543.950.335 (+/-7.9...E + 28) <sup>†</sup> senza virgola decimale; da 0 a +/-7.9228162514264337593543950335 con 28 posizioni a destra del separatore decimale;<br /><br /> il numero più piccolo diverso da zero è +/-0,0000000000000000000000000001 (+/-1E-28) <sup>†</sup>|  
|[Double](double-data-type.md) (a virgola mobile a precisione doppia)|<xref:System.Double>|8 byte|-1.79769313486231570 e + 308 a-4.94065645841246544 E-324 <sup>†</sup> per i valori negativi;<br /><br /> 4.94065645841246544 e-324 tramite 1.79769313486231570 E + 308 <sup>†</sup> per i valori positivi|  
|[Intero](integer-data-type.md)|<xref:System.Int32>|4 byte|da-2.147.483.648 a 2.147.483.647 (con segno)|  
|[Long](long-data-type.md) (Long Integer)|<xref:System.Int64>|8 byte|da-9.223.372.036.854.775.808 a 9.223.372.036.854.775.807 (9.2... E + 18 <sup>†</sup>) (con segno)|  
|[Object](object-data-type.md)|<xref:System.Object>classe|4 byte sulla piattaforma a 32 bit<br /><br /> 8 byte sulla piattaforma a 64 bit|Qualsiasi tipo può essere archiviato in una variabile di tipo`Object`|  
|[SByte](sbyte-data-type.md)|<xref:System.SByte>|1 byte|da-128 a 127 (con segno)|  
|[Short](short-data-type.md) (valore short Integer)|<xref:System.Int16>|2 byte|da-32.768 a 32.767 (con segno)|  
|[Single](single-data-type.md) (virgola mobile a precisione singola)|<xref:System.Single>|4 byte|-3.4028235 e + 38-401298E E-45 <sup>†</sup> per i valori negativi;<br /><br /> 401298E e-45 tramite 3.4028235 E + 38 <sup>†</sup> per i valori positivi|  
|[Stringa](string-data-type.md) (a lunghezza variabile)|<xref:System.String>classe|Dipende dalla piattaforma di implementazione|da 0 a circa 2 miliardi caratteri Unicode|  
|[UInteger](uinteger-data-type.md)|<xref:System.UInt32>|4 byte|da 0 a 4.294.967.295 (senza segno)|  
|[ULong](ulong-data-type.md)|<xref:System.UInt64>|8 byte|da 0 a 18.446.744.073.709.551.615 (1.8... E + 19 <sup>†</sup>) (senza segno)|  
|[Definito dall'utente](user-defined-data-type.md) (struttura)|(eredita da <xref:System.ValueType> )|Dipende dalla piattaforma di implementazione|Ogni membro della struttura ha un intervallo determinato dal tipo di dati e indipendente dagli intervalli degli altri membri|  
|[UShort](ushort-data-type.md)|<xref:System.UInt16>|2 byte|da 0 a 65.535 (senza segno)|  
  
 <sup>†</sup> Nella *notazione scientifica*"E" si riferisce a una potenza di 10. Quindi 3.56 E + 2 significa 3,56 x 10<sup>2</sup> o 356 e 3.56 e-2 indica 3,56/10<sup>2</sup> o 0,0356.  
  
> [!NOTE]
> Per le stringhe contenenti testo, usare la <xref:Microsoft.VisualBasic.Strings.StrConv%2A> funzione per convertire un formato di testo in un altro.  
  
 Oltre a specificare un tipo di dati in un'istruzione di dichiarazione, è possibile forzare il tipo di dati di alcuni elementi di programmazione usando un carattere di tipo. Vedere [caratteri di tipo](../../programming-guide/language-features/data-types/type-characters.md).  
  
## <a name="memory-consumption"></a>Consumo di memoria  

 Quando si dichiara un tipo di dati Elementary, non è sicuro supporre che il consumo di memoria corrisponda a quello dell'allocazione nominale di archiviazione. Questo problema è dovuto alle considerazioni seguenti:  
  
- **Assegnazione di archiviazione.** Il Common Language Runtime può assegnare lo spazio di archiviazione in base alle caratteristiche correnti della piattaforma in cui è in esecuzione l'applicazione. Se la memoria è quasi piena, potrebbe comprimere gli elementi dichiarati nel più vicino possibile. In altri casi, è possibile allineare gli indirizzi di memoria ai limiti hardware naturali per ottimizzare le prestazioni.  
  
- **Larghezza della piattaforma.** L'assegnazione di archiviazione in una piattaforma a 64 bit è diversa dall'assegnazione in una piattaforma a 32 bit.  
  
### <a name="composite-data-types"></a>Tipi di dati compositi  

 Le stesse considerazioni si applicano a ogni membro di un tipo di dati composito, ad esempio una struttura o una matrice. Non è possibile basarsi semplicemente sull'aggiunta delle allocazioni di archiviazione nominale dei membri del tipo. Sono inoltre presenti altre considerazioni, ad esempio le seguenti:  
  
- **Overhead.** Alcuni tipi compositi hanno requisiti di memoria aggiuntivi. Una matrice, ad esempio, utilizza memoria aggiuntiva per la matrice stessa, nonché per ogni dimensione. In una piattaforma a 32 bit, questo overhead è attualmente di 12 byte più 8 byte per ogni dimensione. In una piattaforma a 64 bit questo requisito è raddoppiato.  
  
- **Layout di archiviazione.** Non è possibile presupporre in modo sicuro che l'ordine di archiviazione in memoria corrisponda a quello dell'ordine di dichiarazione. Non è inoltre possibile creare presupposti sull'allineamento dei byte, ad esempio un limite di 2 o 4 byte. Se si definisce una classe o una struttura ed è necessario controllare il layout di archiviazione dei relativi membri, è possibile applicare l' <xref:System.Runtime.InteropServices.StructLayoutAttribute> attributo alla classe o alla struttura.  
  
### <a name="object-overhead"></a>Overhead oggetto  

 Un `Object` riferimento a un tipo di dati elementare o composito utilizza 4 byte oltre ai dati contenuti nel tipo di dati.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Strings.StrConv%2A>
- <xref:System.Runtime.InteropServices.StructLayoutAttribute>
- [CString](../functions/type-conversion-functions.md)
- [Riepilogo della conversione](../keywords/conversion-summary.md)
- [Caratteri tipo](../../programming-guide/language-features/data-types/type-characters.md)
- [Uso efficiente dei tipi di dati](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
