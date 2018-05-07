---
title: Riepilogo dei tipi di dati (Visual Basic)
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
ms.openlocfilehash: 8afeba3f88c4bfe6e1c9777f950c3b458665e340
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="data-type-summary-visual-basic"></a>Riepilogo dei tipi di dati (Visual Basic)
La tabella seguente illustra i tipi di dati Visual Basic, i tipi in common language runtime di supporto, l'allocazione di memoria nominale e i relativi intervalli di valori.  
  
|Tipo di Visual Basic|Struttura di tipo Common language runtime|Allocazione di memoria nominale|Intervallo di valori|  
|-----------------------|--------------------------------------------|--------------------------------|-----------------|  
|[Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<xref:System.Boolean>|Dipende dall'implementazione della piattaforma|`True` o `False`|  
|[Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<xref:System.Byte>|1 byte|da 0 a 255 (senza segno)|  
|[Char](../../../visual-basic/language-reference/data-types/char-data-type.md) (carattere singolo)|<xref:System.Char>|2 byte|tra 0 e 65535 (senza segno)|  
|[Date](../../../visual-basic/language-reference/data-types/date-data-type.md)|<xref:System.DateTime>|8 byte|0:00:00 (mezzanotte) il 1 ° gennaio 0001 a 11:59:59 PM, 31 dicembre 9999|  
|[Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<xref:System.Decimal>|16 byte|da 0 a + /-79.228.162.514.264.337.593.543.950.335 (+ /-7,9... E + 28) <sup>†</sup> senza alcun separatore decimale, tra 0 e + /-7,9228162514264337593543950335 con 28 posizioni a destra del separatore decimale;<br /><br /> il numero più piccolo diverso da zero è + /-0,0000000000000000000000000001 (+ /-1E-28) <sup>†</sup>|  
|[Double](../../../visual-basic/language-reference/data-types/double-data-type.md) (a virgola mobile a precisione doppia)|<xref:System.Double>|8 byte|-1.79769313486231570 e + 308 e - 4, 94065645841246544E-324 <sup>†</sup> per valori negativi.<br /><br /> 4, 94065645841246544E-324 e 1.79769313486231570 e + 308 <sup>†</sup> per i valori positivi|  
|[Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<xref:System.Int32>|4 byte|-2.147.483.648 e 2.147.483.647 (con segno)|  
|[Long](../../../visual-basic/language-reference/data-types/long-data-type.md) (valore long integer)|<xref:System.Int64>|8 byte|-9.223.372.036.854.775.808 e 9.223.372.036.854.775.807 (9.2 … E + 18 <sup>†</sup>) (con segno)|  
|[Oggetto](../../../visual-basic/language-reference/data-types/object-data-type.md)|<xref:System.Object> (classe)|4 byte in una piattaforma a 32 bit<br /><br /> 8 byte in una piattaforma a 64 bit|Qualsiasi tipo può essere archiviato in una variabile di tipo `Object`|  
|[SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<xref:System.SByte>|1 byte|-128 e 127 (con segno)|  
|[Breve](../../../visual-basic/language-reference/data-types/short-data-type.md) (valore short integer)|<xref:System.Int16>|2 byte|da -32.768 e 32.767 (con segno)|  
|[Singolo](../../../visual-basic/language-reference/data-types/single-data-type.md) (a virgola mobile a precisione singola)|<xref:System.Single>|4 byte|-3, 4028235E + 38 a - 1, 401298E-45 <sup>†</sup> per valori negativi.<br /><br /> 1, 401298E-45 a 3, 4028235E + 38 <sup>†</sup> per i valori positivi|  
|[Stringa](../../../visual-basic/language-reference/data-types/string-data-type.md) (a lunghezza variabile)|<xref:System.String> (classe)|Dipende dall'implementazione della piattaforma|da 0 a circa 2 miliardi di caratteri Unicode|  
|[UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<xref:System.UInt32>|4 byte|da 0 a 4.294.967.295 (senza segno)|  
|[ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<xref:System.UInt64>|8 byte|da 0 a 18.446.744.073.709.551.615 (1,8... E + 19 <sup>†</sup>) (senza segno)|  
|[Definite dall'utente](../../../visual-basic/language-reference/data-types/user-defined-data-type.md) (struttura)|(eredita da <xref:System.ValueType>)|Dipende dall'implementazione della piattaforma|Ogni membro della struttura è un intervallo determinato dal tipo di dati e indipendente dagli intervalli degli altri membri|  
|[UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<xref:System.UInt16>|2 byte|tra 0 e 65.535 (senza segno)|  
  
 <sup>†</sup> In *notazione scientifica*, "E" si riferisce a una potenza di 10. Pertanto 3, 56E + 2 indica 3.56 x 10<sup>2</sup> o 356 e 3, 56E-2 indica 3.56 / 10<sup>2</sup> o 0,0356.  
  
> [!NOTE]
>  Per le stringhe contenenti testo, utilizzare il <xref:Microsoft.VisualBasic.Strings.StrConv%2A> funzione per convertire da un formato di testo a un altro.  
  
 Oltre a specificare un tipo di dati in un'istruzione di dichiarazione, è possibile forzare il tipo di dati di alcuni elementi di programmazione utilizzando un tipo di carattere. Vedere [digitare caratteri](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).  
  
## <a name="memory-consumption"></a>Consumo di memoria  
 Quando si dichiara un tipo di dati elementare, non è sicuro presumere che l'utilizzo della memoria sia lo stesso come l'allocazione di archiviazione nominale. Ciò è dovuto a quanto segue:  
  
-   **Assegnazione di archiviazione.** Common language runtime può assegnare spazio di archiviazione in base alle caratteristiche della piattaforma su cui è in esecuzione l'applicazione corrente. Se la memoria è quasi esaurita, è possibile comprimere gli elementi dichiarati più vicino possibile. In altri casi, è possibile allineare gli indirizzi di memoria per i limiti dell'hardware per ottimizzare le prestazioni.  
  
-   **Larghezza della piattaforma.** Assegnazione di archiviazione in una piattaforma a 64 bit è diversa dall'assegnazione su una piattaforma a 32 bit.  
  
### <a name="composite-data-types"></a>Tipi di dati compositi  
 Le stesse considerazioni si applicano a ogni membro di un tipo di dati compositi, ad esempio una struttura o una matrice. È possibile basarsi su sufficiente sommare le allocazioni di memoria nominale di membri del tipo. Inoltre, esistono altre considerazioni, ad esempio le operazioni seguenti:  
  
-   **Sovraccarico.** Alcuni tipi compositi hanno requisiti di memoria aggiuntiva. Ad esempio, una matrice utilizza memoria aggiuntiva per la matrice stessa, nonché per ogni dimensione. In una piattaforma a 32 bit, l'overhead è attualmente 12 byte e a 8 byte per ogni dimensione. In una piattaforma a 64 bit viene raddoppiato questo requisito.  
  
-   **Layout di archiviazione.** Non è possibile presupporre che l'ordine di archiviazione in memoria è identico all'ordine di dichiarazione. Non è possibile anche supposizioni sull'allineamento di byte, ad esempio un limite di 2 o 4 byte. Se si sta definendo una classe o struttura ed è necessario controllare il layout di archiviazione dei relativi membri, è possibile applicare il <xref:System.Runtime.InteropServices.StructLayoutAttribute> attributo alla classe o struttura.  
  
### <a name="object-overhead"></a>Overhead di oggetto  
 Un `Object` che fa riferimento a tutti i dati elementari o compositi di tipo utilizza 4 byte oltre ai dati contenuti nel tipo di dati.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.Strings.StrConv%2A>  
 <xref:System.Runtime.InteropServices.StructLayoutAttribute>  
 [Funzioni di conversione del tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Riepilogo della conversione](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Caratteri tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [Uso efficiente dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
