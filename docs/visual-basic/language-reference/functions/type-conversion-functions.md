---
title: Funzioni di conversione del tipo (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.CUShort
- vb.csng
- vb.CDate
- CByte
- CSng
- vb.CDec
- CBool
- CStr
- vb.CULng
- CDec
- CVErr
- CDbl
- CShort
- vb.CObj
- vb.CVErr
- CULng
- vb.cdbl
- vb.cbool
- CObj
- CDate
- CLng
- vb.cstr
- vb.cbyte
- vb.clng
- vb.CChar
- CUShort
- vb.CUInt
- vb.cint
- vb.CShort
- CInt
- CUInt
- CChar
helpviewer_keywords:
- CDate function
- CByte function
- Integer data type [Visual Basic], converting
- string conversion [Visual Basic], conversion functions
- fractions
- data types [Visual Basic], converting
- text, converting
- CDec function
- Char data type [Visual Basic], converting
- type conversion [Visual Basic], functions for
- Single data type [Visual Basic], converting
- numbers [Visual Basic], rounding
- rounding numbers [Visual Basic], type conversion
- CUShort function
- Long data type [Visual Basic], converting
- return values [Visual Basic], data types
- single-precision numbers [Visual Basic], converting
- data type conversion [Visual Basic], functions for
- CStr function
- times [Visual Basic], converting
- CSng function
- conversions [Visual Basic], type conversion functions
- CBool function
- CDbl function
- CUInt function
- Currency data type [Visual Basic], conversion functions
- numbers [Visual Basic], converting
- Double data type [Visual Basic], converting
- CLng function
- CSByte function
- double-precision numbers
- Decimal data type [Visual Basic], converting
- Boolean data type [Visual Basic], converting
- integers [Visual Basic], type conversion functions
- dates [Visual Basic], converting
- CULng function
- CInt function
- Date data type [Visual Basic], converting
- Byte data type [Visual Basic], converting
- String data type [Visual Basic], converting
- CChar function
- banker's rounding
- Short data type [Visual Basic], converting
- rounding numbers [Visual Basic], banker's rounding
- type conversion [Visual Basic], Visual Basic vs. .NET Framework
ms.assetid: d9d8d165-f967-44ff-a6cd-598e4740a99e
ms.openlocfilehash: c9222bdb31f4fd7c792d5a50c100067e29e9d537
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605082"
---
# <a name="type-conversion-functions-visual-basic"></a>Funzioni di conversione del tipo (Visual Basic)
Queste funzioni vengono compilate inline, ovvero che la conversione di codice fa parte del codice che valuta l'espressione. A volte non sussiste alcuna chiamata a una stored procedure per eseguire la conversione, che migliora le prestazioni. Ogni funzione forza un'espressione al tipo di dati specifico.  
  
## <a name="syntax"></a>Sintassi  
  
```  
CBool(expression)  
CByte(expression)  
CChar(expression)  
CDate(expression)  
CDbl(expression)  
CDec(expression)  
CInt(expression)  
CLng(expression)  
CObj(expression)  
CSByte(expression)  
CShort(expression)  
CSng(expression)  
CStr(expression)  
CUInt(expression)  
CULng(expression)  
CUShort(expression)  
```  
  
## <a name="part"></a>Parte  
 `expression`  
 Obbligatorio. Qualsiasi espressione del tipo di dati di origine.  
  
## <a name="return-value-data-type"></a>Tipo di dati di valore restituito  
 Il nome della funzione determina il tipo di dati del valore che viene restituito, come illustrato nella tabella seguente.  
  
|Nome della funzione|Tipo di dati restituito|Intervallo per `expression` argomento|  
|-------------------|----------------------|-------------------------------------|  
|`CBool`|[Tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Qualsiasi `Char` o `String` o espressione numerica.|  
|`CByte`|[Tipo di dati Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md)|da 0 a 255 (senza segno). parti frazionarie vengono arrotondate. <sup>1</sup>|  
|`CChar`|[Tipo di dati Char](../../../visual-basic/language-reference/data-types/char-data-type.md)|Qualsiasi `Char` o `String` espressione; solo primo carattere di un `String` viene convertito; valore può essere 0 e 65535 (senza segno).|  
|`CDate`|[Tipo di dati Date](../../../visual-basic/language-reference/data-types/date-data-type.md)|Qualsiasi rappresentazione valida di una data e ora.|  
|`CDbl`|[Tipo di dati Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|-1.79769313486231570 e + 308 e - 4, 94065645841246544E-324 per valori negativi. 4, 94065645841246544E-324 e 1.79769313486231570 e + 308 per i valori positivi.|  
|`CDec`|[Tipo di dati Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|+ /-79.228.162.514.264.337.593.543.950.335 per zero-numeri, ovvero numeri senza cifre decimali. Per i numeri con 28 cifre decimali, l'intervallo è + /-7,9228162514264337593543950335. Il minor numero possibile di diverso da zero è 0,0000000000000000000000000001 (+ /-1E-28).|  
|`CInt`|[Tipo di dati Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)|tra -2.147.483.648 e 2.147.483.647. parti frazionarie vengono arrotondate. <sup>1</sup>|  
|`CLng`|[Tipo di dati Long](../../../visual-basic/language-reference/data-types/long-data-type.md)|-9.223.372.036.854.775.808 a 9.223.372.036.854.775.807; parti frazionarie vengono arrotondate. <sup>1</sup>|  
|`CObj`|[Tipo di dati Object](../../../visual-basic/language-reference/data-types/object-data-type.md)|Qualsiasi espressione valida.|  
|`CSByte`|[Tipo di dati SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|-128 e 127; parti frazionarie vengono arrotondate. <sup>1</sup>|  
|`CShort`|[Tipo di dati Short](../../../visual-basic/language-reference/data-types/short-data-type.md)|da -32.768 e 32.767; parti frazionarie vengono arrotondate. <sup>1</sup>|  
|`CSng`|[Tipo di dati Single](../../../visual-basic/language-reference/data-types/single-data-type.md)|-3, 402823E + 38 a - 1, 401298E-45 per valori negativi. 1, 401298E-45 a 3, 402823E + 38 per i valori positivi.|  
|`CStr`|[Tipo di dati String](../../../visual-basic/language-reference/data-types/string-data-type.md)|Restituisce per `CStr` dipendono il `expression` argomento. Vedere [valori restituiti dalla funzione CStr](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).|  
|`CUInt`|[Tipo di dati UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|da 0 a 4.294.967.295 (senza segno). parti frazionarie vengono arrotondate. <sup>1</sup>|  
|`CULng`|[Tipo di dati ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|da 0 a 18.446.744.073.709.551.615 (senza segno). parti frazionarie vengono arrotondate. <sup>1</sup>|  
|`CUShort`|[Tipo di dati UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|da 0 a 65.535 (senza segno). parti frazionarie vengono arrotondate. <sup>1</sup>|  
  
 <sup>1</sup> parti frazionarie possono essere soggetta a un tipo speciale di arrotondamento chiamato *arrotondamento*. Per ulteriori informazioni, vedere "la sezione Osservazioni".  
  
## <a name="remarks"></a>Note  
 Come regola, utilizzare le funzioni di conversione di tipo Visual Basic anziché i metodi di .NET Framework, ad esempio `ToString()`, entrambi nel <xref:System.Convert> classe o in una classe o struttura di tipo individuale. Le funzioni di Visual Basic sono progettate per l'interazione ottimale con codice di Visual Basic e rendono il codice sorgente più breve e facile da leggere. Inoltre, i metodi di conversione di .NET Framework non producono sempre gli stessi risultati di funzioni di Visual Basic, ad esempio durante la conversione `Boolean` a `Integer`. Per ulteriori informazioni, vedere [risoluzione dei problemi dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## <a name="behavior"></a>Comportamento  
  
-   **Coercizione.** In generale, è possibile utilizzare le funzioni di conversione di tipo di dati per assegnare il risultato di un'operazione a un particolare tipo di dati anziché il tipo di dati predefinito. Ad esempio, utilizzare `CDec` per forzare l'aritmetica decimale nei casi in cui e con precisione singola e precisione doppia o calcoli di interi normalmente avrà luogo.  
  
-   **Conversioni non riuscite.** Se il `expression` passato alla funzione è compreso nell'intervallo del tipo di dati a cui si desidera convertire, un <xref:System.OverflowException> si verifica.  
  
-   **Parti frazionarie.** Quando si converte un valore non integrale in un tipo integrale tipo, le funzioni di conversione di integer (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, e `CUShort`) rimuovere il frazionari parte e arrotondare il valore all'intero più vicino.  
  
     Se la parte frazionaria è esattamente 0,5, arrotondano le funzioni di conversione di valori integer per l'intero pari più vicino. Ad esempio 0,5 verrà arrotondato a 0 e 1,5 e 2,5 che entrambi arrotondato a 2. Talvolta chiamato *arrotondamento*, e il suo scopo consiste nel compensare la distorsione che potrebbero accumularsi quando aggiungono molti tali numeri.  
  
     `CInt` e `CLng` diversi dai <xref:Microsoft.VisualBasic.Conversion.Int%2A> e <xref:Microsoft.VisualBasic.Conversion.Fix%2A> funzioni, che, anziché troncano l'arrotondamento, la parte frazionaria di un numero. Inoltre, `Fix` e `Int` restituiscono sempre un valore dello stesso tipo di dati di quello passato.  
  
-   **Conversioni di data/ora.** Utilizzare il <xref:Microsoft.VisualBasic.Information.IsDate%2A> funzione per determinare se un valore può essere convertito in una data e ora. `CDate` riconosce i valori letterali data e ora, ma i valori non numerici. Per convertire un Visual Basic 6.0 `Date` valore un `Date` valore in Visual Basic 2005 o versioni successive, è possibile utilizzare il <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> metodo.  
  
-   **Neutro valori data/ora.** Il [tipo di dati Date](../../../visual-basic/language-reference/data-types/date-data-type.md) contiene sempre le informazioni sia data e ora. Ai fini della conversione del tipo, Visual Basic considera 1/1/0001 (1 ° gennaio dell'anno 1) da un *valore neutro* per la data e 00:00:00 (mezzanotte) come valore neutro per l'ora. Se si converte un `Date` , una stringa a valore `CStr` non include valori neutri nella stringa risultante. Ad esempio, se si converte `#January 1, 0001 9:30:00#` in una stringa, il risultato è "9:30:00 AM"; le informazioni sulla data viene eliminate. Tuttavia, le informazioni sulla data è ancora presente nell'originale `Date` valore e possono essere recuperate con funzioni, ad esempio <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> (funzione).  
  
-   **Distinzione di impostazioni cultura.** Le funzioni di conversione di tipo che riguardano le stringhe eseguono conversioni in base alle impostazioni cultura correnti per l'applicazione. Ad esempio, `CDate` riconosce i formati di data in base all'impostazione delle impostazioni locali del sistema. È necessario specificare il giorno, mese e anno nell'ordine corretto delle impostazioni locali o la data potrebbe non essere interpretata correttamente. Se contiene una stringa di giorno della settimana, ad esempio "Mercoledì", un formato di data estesa non è riconosciuto.  
  
     Se è necessario convertire verso o da una rappresentazione di stringa di un valore in un formato diverso da quello specificato dalle impostazioni locali, è possibile utilizzare le funzioni di conversione di tipo Visual Basic. A tale scopo, utilizzare il `ToString(IFormatProvider)` e `Parse(String, IFormatProvider)` metodi del tipo di valore. Ad esempio, utilizzare <xref:System.Double.Parse%2A?displayProperty=nameWithType> quando si converte una stringa in un `Double`e utilizzare <xref:System.Double.ToString%2A?displayProperty=nameWithType> durante la conversione di un valore di tipo `Double` in una stringa.  
  
## <a name="ctype-function"></a>CType Function  
 Il [CType (funzione)](../../../visual-basic/language-reference/functions/ctype-function.md) accetta un secondo argomento `typename`e assegna `expression` a `typename`, dove `typename` può essere qualsiasi tipo di dati, struttura, classe o interfaccia a cui è presente una conversione valida.  
  
 Per un confronto tra `CType` con l'altra tipo parole chiave di conversione, vedere [operatore DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) e [operatore TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md).  
  
## <a name="cbool-example"></a>Esempio di CBool  
 L'esempio seguente usa il `CBool` funzione per convertire le espressioni di `Boolean` valori. Se un'espressione restituisce un valore diverso da zero, `CBool` restituisce `True`; in caso contrario, restituisce `False`.  
  
 [!code-vb[VbVbalrFunctions#1](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_1.vb)]  
  
## <a name="cbyte-example"></a>Esempio di CByte  
 L'esempio seguente usa il `CByte` funzione per convertire un'espressione in un `Byte`.  
  
 [!code-vb[VbVbalrFunctions#2](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_2.vb)]  
  
## <a name="cchar-example"></a>Esempio di CChar  
 L'esempio seguente usa il `CChar` funzione per convertire il primo carattere di un `String` espressione da un `Char` tipo.  
  
 [!code-vb[VbVbalrFunctions#3](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_3.vb)]  
  
 Argomento di input per `CChar` deve essere di tipo di dati `Char` o `String`. Non è possibile utilizzare `CChar` per convertire un numero in un carattere, perché `CChar` non può accettare un tipo di dati numerici. Nell'esempio seguente viene ottenuto un numero che rappresenta un punto di codice (codice carattere) e converte il carattere corrispondente. Usa il <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> funzione per ottenere la stringa di cifre, `CInt` per convertire la stringa al tipo `Integer`, e `ChrW` effettuare la conversione al tipo `Char`.  
  
 [!code-vb[VbVbalrFunctions#4](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_4.vb)]  
  
## <a name="cdate-example"></a>Esempio di CDate  
 L'esempio seguente usa il `CDate` funzione per convertire le stringhe in `Date` valori. In generale, non è consigliabile impostare come hardcoded date e ore come stringhe (come illustrato in questo esempio). Utilizzare valori letterali di data e ora, ad esempio #Feb 12, 1969 # e # 4:45:23 PM # invece.  
  
 [!code-vb[VbVbalrFunctions#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_5.vb)]  
  
## <a name="cdbl-example"></a>Esempio di CDbl  
 [!code-vb[VbVbalrFunctions#6](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_6.vb)]  
  
## <a name="cdec-example"></a>Esempio di CDec  
 L'esempio seguente usa il `CDec` funzione per convertire un valore numerico per `Decimal`.  
  
 [!code-vb[VbVbalrFunctions#7](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_7.vb)]  
  
## <a name="cint-example"></a>Esempio di CInt  
 L'esempio seguente usa il `CInt` funzione per convertire un valore `Integer`.  
  
 [!code-vb[VbVbalrFunctions#8](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_8.vb)]  
  
## <a name="clng-example"></a>Esempio di CLng  
 L'esempio seguente usa il `CLng` funzione per convertire i valori per `Long`.  
  
 [!code-vb[VbVbalrFunctions#9](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_9.vb)]  
  
## <a name="cobj-example"></a>Esempio di CObj  
 L'esempio seguente usa il `CObj` funzione per convertire un valore numerico per `Object`. Il `Object` variabile contiene solo un puntatore a quattro byte, che fa riferimento al `Double` valore assegnato a esso.  
  
 [!code-vb[VbVbalrFunctions#10](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_10.vb)]  
  
## <a name="csbyte-example"></a>Esempio di CSByte  
 L'esempio seguente usa il `CSByte` funzione per convertire un valore numerico per `SByte`.  
  
 [!code-vb[VbVbalrFunctions#11](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_11.vb)]  
  
## <a name="cshort-example"></a>Esempio di CShort  
 L'esempio seguente usa il `CShort` funzione per convertire un valore numerico per `Short`.  
  
 [!code-vb[VbVbalrFunctions#12](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_12.vb)]  
  
## <a name="csng-example"></a>Esempio di CSng  
 L'esempio seguente usa il `CSng` funzione per convertire i valori per `Single`.  
  
 [!code-vb[VbVbalrFunctions#13](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_13.vb)]  
  
## <a name="cstr-example"></a>Esempio di funzione CStr  
 L'esempio seguente usa il `CStr` funzione per convertire un valore numerico per `String`.  
  
 [!code-vb[VbVbalrFunctions#14](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_14.vb)]  
  
 L'esempio seguente usa il `CStr` funzione per convertire `Date` valori `String` valori.  
  
 [!code-vb[VbVbalrFunctions#15](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_15.vb)]  
  
 `CStr` Visualizza sempre un `Date` valore nel formato breve standard per le impostazioni locali correnti, ad esempio, "6/15/2003 4:35:47 PM". Tuttavia, `CStr` Sopprime il *valori neutri* di 1/1/0001 per la data e 00:00:00 per il periodo di tempo.  
  
 Per informazioni dettagliate sui valori restituiti da `CStr`, vedere [valori restituiti dalla funzione CStr](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).  
  
## <a name="cuint-example"></a>Esempio di CUInt  
 L'esempio seguente usa il `CUInt` funzione per convertire un valore numerico per `UInteger`.  
  
 [!code-vb[VbVbalrFunctions#16](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_16.vb)]  
  
## <a name="culng-example"></a>Esempio di CULng  
 L'esempio seguente usa il `CULng` funzione per convertire un valore numerico per `ULong`.  
  
 [!code-vb[VbVbalrFunctions#17](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_17.vb)]  
  
## <a name="cushort-example"></a>Esempio di CUShort  
 L'esempio seguente usa il `CUShort` funzione per convertire un valore numerico per `UShort`.  
  
 [!code-vb[VbVbalrFunctions#18](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_18.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>  
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Int%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Fix%2A>  
 <xref:Microsoft.VisualBasic.Strings.Format%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Oct%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Str%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Val%2A>  
 [Funzioni di conversione](../../../visual-basic/language-reference/functions/conversion-functions.md)  
 [Conversioni di tipi in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
