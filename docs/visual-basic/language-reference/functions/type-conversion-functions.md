---
title: Funzioni di conversione del tipo (Visual Basic)
ms.date: 10/24/2018
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
ms.openlocfilehash: ea7cc2c7f988617de67bf0ea46aeb3396acdf4b1
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56980620"
---
# <a name="type-conversion-functions-visual-basic"></a>Funzioni di conversione del tipo (Visual Basic)
Queste funzioni vengono compilate inline, vale a dire che il codice di conversione fa parte del codice che valuta l'espressione. In alcuni casi non vi è alcuna chiamata a una procedura per eseguire la conversione, che migliora le prestazioni. Ogni funzione converte un'espressione per un tipo di dati specifico.  
  
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
  
## <a name="return-value-data-type"></a>Restituire il tipo di dati di valore  
 Il nome della funzione determina il tipo di dati del valore restituito, come illustrato nella tabella seguente.  
  
|Nome funzione|Tipo di dati restituito|Intervallo per `expression` argomento|  
|-------------------|----------------------|-------------------------------------|  
|`CBool`|[Tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Qualunque `Char` o `String` o espressione numerica.|  
|`CByte`|[Tipo di dati Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<xref:System.Byte.MinValue?displayProperty=nameWithType> (0) attraverso <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (senza segno); vengono arrotondate parti frazionarie.<sup> 1</sup><br/><br/>A partire da Visual Basic 15.8, Visual Basic consente di ottimizzare le prestazioni della virgola mobile per la conversione di byte con il `CByte` funzione; vedere la [osservazioni](#remarks) sezione per altre informazioni. Vedere le [CInt esempio](#cint-example) sezione per un esempio.|  
|`CChar`|[Tipo di dati Char](../../../visual-basic/language-reference/data-types/char-data-type.md)|Qualunque `Char` o `String` espressione; solo primo carattere di un `String` viene convertito; valore può essere 0 e 65535 (senza segno).|  
|`CDate`|[Tipo di dati Date](../../../visual-basic/language-reference/data-types/date-data-type.md)|Qualsiasi rappresentazione valida di una data e ora.|  
|`CDbl`|[Tipo di dati Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|-1.79769313486231570 e + 308 e - fino a 4.94065645841246544-324 per valori negativi. Fino a 4.94065645841246544-324 e 1.79769313486231570 e + 308 per i valori positivi.|  
|`CDec`|[Tipo di dati Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|+ /-79.228.162.514.264.337.593.543.950.335 per i numeri da zero a scalabilità, ovvero numeri senza cifre decimali. Per i numeri con 28 posizioni decimali, l'intervallo è + /-7,9228162514264337593543950335. Il minor numero possibile di diverso da zero è 0,0000000000000000000000000001 (+ /-1E-28).|  
|`CInt`|[Tipo di dati Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<xref:System.Int32.MinValue?displayProperty=nameWithType> (da -2.147.483.648) attraverso <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2,147,483,647); vengono arrotondate parti frazionarie.<sup> 1</sup> <br/><br/>A partire da 15.8 Visual Basic, Visual Basic ottimizza le prestazioni della virgola mobile per la conversione di integer con il `CInt` funzione; vedere la [osservazioni](#remarks) sezione per altre informazioni. Vedere le [CInt esempio](#cint-example) sezione per un esempio. |  
|`CLng`|[Tipo di dati Long](../../../visual-basic/language-reference/data-types/long-data-type.md)|<xref:System.Int64.MinValue?displayProperty=nameWithType> (da -9.223.372.036.854.775.808) attraverso <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9.223.372.036.854.775.807); vengono arrotondate parti frazionarie.<sup> 1</sup><br/><br/>A partire da Visual Basic 15.8, Visual Basic consente di ottimizzare le prestazioni della virgola mobile per la conversione di integer a 64 bit con la `CLng` funzione; vedere la [osservazioni](#remarks) sezione per altre informazioni. Vedere le [CInt esempio](#cint-example) sezione per un esempio.|  
|`CObj`|[Tipo di dati Object](../../../visual-basic/language-reference/data-types/object-data-type.md)|Qualsiasi espressione valida.|  
|`CSByte`|[Tipo di dati SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<xref:System.SByte.MinValue?displayProperty=nameWithType> (da -128) attraverso <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127); vengono arrotondate parti frazionarie.<sup> 1</sup><br/><br/>A partire da Visual Basic 15.8, Visual Basic consente di ottimizzare le prestazioni della virgola mobile per la conversione di byte con segno con il `CSByte` funzione; vedere la [osservazioni](#remarks) sezione per altre informazioni. Vedere le [CInt esempio](#cint-example) sezione per un esempio.|  
|`CShort`|[Tipo di dati Short](../../../visual-basic/language-reference/data-types/short-data-type.md)|<xref:System.Int16.MinValue?displayProperty=nameWithType> (-32.768) attraverso <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32.767); vengono arrotondate parti frazionarie.<sup> 1</sup><br/><br/>A partire da Visual Basic 15.8, Visual Basic consente di ottimizzare le prestazioni della virgola mobile per la conversione di integer a 16 bit con la `CShort` funzione; vedere la [osservazioni](#remarks) sezione per altre informazioni. Vedere le [CInt esempio](#cint-example) sezione per un esempio.|  
|`CSng`|[Tipo di dati Single](../../../visual-basic/language-reference/data-types/single-data-type.md)|-3,402823E+38 a - 1,401298E-45 per valori negativi. 1,401298E-45 a 3,402823E+38 per valori positivi.|  
|`CStr`|[Tipo di dati String](../../../visual-basic/language-reference/data-types/string-data-type.md)|Restituisce relativi `CStr` dipendono il `expression` argomento. Visualizzare [valori restituiti dalla funzione CStr](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).|  
|`CUInt`|[Tipo di dati UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<xref:System.UInt32.MinValue?displayProperty=nameWithType> (0) attraverso <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4.294.967.295) (senza segno); vengono arrotondate parti frazionarie.<sup> 1</sup><br/><br/>A partire da Visual Basic 15.8, Visual Basic consente di ottimizzare le prestazioni della virgola mobile per la conversione dell'intero senza segno con il `CUInt` funzione; vedere la [osservazioni](#remarks) sezione per altre informazioni. Vedere le [CInt esempio](#cint-example) sezione per un esempio.|  
|`CULng`|[Tipo di dati ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<xref:System.UInt64.MinValue?displayProperty=nameWithType> (0) attraverso <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18.446.744.073.709.551.615) (senza segno); vengono arrotondate parti frazionarie.<sup> 1</sup><br/><br/>A partire da Visual Basic 15.8, Visual Basic consente di ottimizzare le prestazioni della virgola mobile per la conversione dell'intero lungo senza segno con il `CULng` funzione; vedere la [osservazioni](#remarks) sezione per altre informazioni. Vedere le [CInt esempio](#cint-example) sezione per un esempio.|  
|`CUShort`|[Tipo di dati UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<xref:System.UInt16.MinValue?displayProperty=nameWithType> (0) attraverso <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65.535) (senza segno); vengono arrotondate parti frazionarie.<sup> 1</sup><br/><br/>A partire da Visual Basic 15.8, Visual Basic consente di ottimizzare le prestazioni della virgola mobile per la conversione dell'intero senza segno a 16 bit con la `CUShort` funzione; vedere la [osservazioni](#remarks) sezione per altre informazioni. Vedere le [CInt esempio](#cint-example) sezione per un esempio.|  
  
 <sup>1</sup> parti frazionarie possono essere soggetta a un tipo speciale di arrotondamento chiamato *arrotondamento*. Per ulteriori informazioni, vedere "la sezione Osservazioni".  
  
## <a name="remarks"></a>Note  
 Di norma, è consigliabile usare le funzioni di conversione di tipo Visual Basic anziché i metodi .NET Framework, ad esempio `ToString()`, ad esempio nel <xref:System.Convert> classe o in una classe o struttura di tipo individuale. Le funzioni di Visual Basic sono progettate per l'interazione ottimale con codice Visual Basic e rendono il codice sorgente più breve e facile da leggere. Inoltre, i metodi di conversione di .NET Framework non restituiscono sempre gli stessi risultati di funzioni di Visual Basic, ad esempio quando si convertono `Boolean` a `Integer`. Per altre informazioni, vedere [tipi di dati di risoluzione dei problemi](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  


A partire da Visual Basic 15.8, le prestazioni della conversione a virgola mobile-virgola-a numero intero sono ottimizzata quando si passa il <xref:System.Single> oppure <xref:System.Double> valore restituito dai metodi seguenti per una delle funzioni di conversione di integer (`CByte`, `CShort`, `CInt`, `CLng`, `CSByte`, `CUShort`, `CUInt`, `CULng`):

- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Single)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Single)?displayProperty=nameWithType>
- <xref:System.Math.Ceiling(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Floor(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Round(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Truncate(System.Double)?displayProperty=nameWithType>

Questa ottimizzazione consente al codice che esegue un numero elevato di conversioni di integer per eseguire un massimo di due volte più veloci. L'esempio seguente illustra queste conversioni ottimizzate di Mobile-virgola-a-integer:

```vb
Dim s As Single = 173.7619
Dim d As Double = s 

Dim i1 As Integer = CInt(Fix(s))               ' Result: 173
Dim b1 As Byte = CByte(Int(d))                 ' Result: 173
Dim s1 AS Short = CShort(Math.Truncate(s))     ' Result: 173
Dim i2 As Integer = CInt(Math.Ceiling(d))      ' Result: 174
Dim i3 As Integer = CInt(Math.Round(s))        ' Result: 174
```

## <a name="behavior"></a>Comportamento  
  
-   **Coercion.** In generale, è possibile utilizzare le funzioni di conversione di tipi di dati per assegnare il risultato di un'operazione a un particolare tipo di dati anziché il tipo di dati predefinito. Ad esempio, usare `CDec` forzare operazioni aritmetiche decimali nei casi in cui con precisione singola e precisione doppia o calcoli di interi normalmente avverrebbero.  
  
-   **Conversioni non riuscite.** Se il `expression` passati alla funzione è compreso nell'intervallo del tipo di dati a cui si desidera convertire, un <xref:System.OverflowException> si verifica.  
  
-   **Parti frazionarie.** Quando si converte un valore non integrale in un valore integrale digita, le funzioni di conversione di valori integer (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, e `CUShort`) rimuovere il frazionari parte e arrotondare il valore all'intero più vicino.  
  
     Se la parte frazionaria è identica 0,5, le funzioni di conversione di valori integer arrotondano per l'intero pari più vicino. Ad esempio 0,5 verrà arrotondato a 0 e 1,5 e 2,5 che entrambi arrotondato a 2. Questa operazione è denominata *arrotondamento*, e il suo scopo consiste nel compensare la distorsione che può accumularsi quando aggiungono molti tali numeri.  
  
     `CInt` e `CLng` differiscono dalle <xref:Microsoft.VisualBasic.Conversion.Int%2A> e <xref:Microsoft.VisualBasic.Conversion.Fix%2A> funzioni, che troncano, anziché round, la parte frazionaria di un numero. È inoltre `Fix` e `Int` restituiscono sempre un valore del tipo di dati stesso di quello passato.  
  
-   **Conversioni di data/ora.** Usare il <xref:Microsoft.VisualBasic.Information.IsDate%2A> funzione per determinare se un valore può essere convertito in una data e ora. `CDate` riconosce i valori letterali di data e ora, ma i valori non numerici. La conversione di Visual Basic 6.0 `Date` valore per un `Date` valore in Visual Basic 2005 o versioni successive, è possibile usare il <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> (metodo).  
  
-   **Neutro valori data/ora.** Il [tipo di dati Date](../../../visual-basic/language-reference/data-types/date-data-type.md) contiene sempre le informazioni sia data e ora. Ai fini di conversione del tipo, Visual Basic considera come 1/1/0001 (1 ° gennaio dell'anno 1) da un *valore neutro* per la data e 00:00:00 (mezzanotte) su un valore neutro per il periodo di tempo. Se si converte un `Date` valore da una stringa, `CStr` non include valori neutri nella stringa risultante. Ad esempio, se si converte `#January 1, 0001 9:30:00#` in una stringa, il risultato è "9:30: 12:00:00 AM"; le informazioni sulla data viene eliminate. Tuttavia, le informazioni sulla data è ancora presente nell'originale `Date` valore e possono essere recuperate con le funzioni, ad esempio <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> (funzione).  
  
-   **Sensibilità delle impostazioni cultura.** Le funzioni di conversione di tipo che interessa le stringhe di eseguono conversioni in base alle impostazioni cultura correnti per l'applicazione. Ad esempio, `CDate` riconosce i formati di data in base alle impostazioni locali del sistema. È necessario specificare il giorno, mese e anno nell'ordine corretto per le impostazioni locali, o alla data potrà essere interpretata erroneamente. Se contiene una stringa di giorno della settimana, ad esempio "Wednesday", un formato di data estesa non è riconosciuto.  
  
     Se è necessario convertire a o da una rappresentazione di stringa di un valore in un formato diverso da quello specificato dalle impostazioni locali, è possibile usare le funzioni di conversione di tipo Visual Basic. A questo scopo, usare il `ToString(IFormatProvider)` e `Parse(String, IFormatProvider)` metodi del tipo di valore. Ad esempio, usare <xref:System.Double.Parse%2A?displayProperty=nameWithType> quando si converte una stringa in un `Double`e usare <xref:System.Double.ToString%2A?displayProperty=nameWithType> durante la conversione di un valore di tipo `Double` in una stringa.  
  
## <a name="ctype-function"></a>CType Function  
 Il [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) accetta un secondo argomento `typename`e assegna `expression` a `typename`, dove `typename` può essere qualsiasi tipo di dati, struttura, classe o interfaccia a cui è presente una conversione valida.  
  
 Per un confronto delle `CType` con l'altra tipo parole chiave di conversione, vedere [operatore DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) e [operatore TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md).  
  
## <a name="cbool-example"></a>Esempio CBool  
 L'esempio seguente usa il `CBool` funzione per convertire le espressioni `Boolean` valori. Se un'espressione restituisce un valore diverso da zero, `CBool` restituisce `True`; in caso contrario, restituisce `False`.  
  
 [!code-vb[VbVbalrFunctions#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#1)]  
  
## <a name="cbyte-example"></a>Esempio CByte  
 L'esempio seguente usa il `CByte` funzione per convertire un'espressione in un `Byte`.  
  
 [!code-vb[VbVbalrFunctions#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#2)]  
  
## <a name="cchar-example"></a>Esempio di CChar  
 L'esempio seguente usa il `CChar` funzione per convertire il primo carattere di una `String` espressione da un `Char` tipo.  
  
 [!code-vb[VbVbalrFunctions#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#3)]  
  
 L'argomento di input per `CChar` deve essere del tipo di dati `Char` o `String`. Non è possibile usare `CChar` per convertire un numero in un carattere, in quanto `CChar` non può accettare un tipo di dati numerici. Nell'esempio seguente ottiene un numero che rappresenta un punto di codice (codice di carattere) e lo converte nel carattere corrispondente. Usa il <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> funzione per ottenere la stringa di cifre `CInt` per convertire la stringa al tipo `Integer`, e `ChrW` effettuare la conversione al tipo `Char`.  
  
 [!code-vb[VbVbalrFunctions#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#4)]  
  
## <a name="cdate-example"></a>Esempio CDate  
 L'esempio seguente usa il `CDate` funzione per convertire le stringhe a `Date` valori. In generale, non è consigliabile impostare come hardcoded date e ore sotto forma di stringhe (come illustrato in questo esempio). Usare valori letterali di data e ora, ad esempio #Feb 12, 1969 # e # 4:45:23 PM # invece.  
  
 [!code-vb[VbVbalrFunctions#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#5)]  
  
## <a name="cdbl-example"></a>Esempio CDbl  
 [!code-vb[VbVbalrFunctions#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#6)]  
  
## <a name="cdec-example"></a>Esempio CDec  
 L'esempio seguente usa il `CDec` funzione per convertire un valore numerico a `Decimal`.  
  
 [!code-vb[VbVbalrFunctions#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#7)]  
  
## <a name="cint-example"></a>Esempio CInt  
 L'esempio seguente usa il `CInt` funzione per convertire un valore a `Integer`.  
  
 [!code-vb[VbVbalrFunctions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#8)]  

## <a name="clng-example"></a>Esempio CLng
 L'esempio seguente usa il `CLng` funzione per convertire i valori per `Long`.  
  
 [!code-vb[VbVbalrFunctions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#9)]  
  
## <a name="cobj-example"></a>CObj esempio  
 L'esempio seguente usa il `CObj` funzione per convertire un valore numerico a `Object`. Il `Object` variabile contiene solo un puntatore a quattro byte, che fa riferimento al `Double` valore assegnato a esso.  
  
 [!code-vb[VbVbalrFunctions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#10)]  
  
## <a name="csbyte-example"></a>CSByte Example  
 L'esempio seguente usa il `CSByte` funzione per convertire un valore numerico a `SByte`.  
  
 [!code-vb[VbVbalrFunctions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#11)]  
  
## <a name="cshort-example"></a>Esempio di CShort  
 L'esempio seguente usa il `CShort` funzione per convertire un valore numerico a `Short`.  
  
 [!code-vb[VbVbalrFunctions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#12)]  
  
## <a name="csng-example"></a>Esempio di CSng  
 L'esempio seguente usa il `CSng` funzione per convertire i valori per `Single`.  
  
 [!code-vb[VbVbalrFunctions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#13)]  
  
## <a name="cstr-example"></a>Esempio di funzione CStr  
 L'esempio seguente usa il `CStr` funzione per convertire un valore numerico a `String`.  
  
 [!code-vb[VbVbalrFunctions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#14)]  
  
 L'esempio seguente usa il `CStr` funzione per convertire `Date` valori `String` valori.  
  
 [!code-vb[VbVbalrFunctions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#15)]  
  
 `CStr` Visualizza sempre un `Date` valore nel formato breve standard per le impostazioni locali correnti, ad esempio, "6/15/2003 4 35 47 PM". Tuttavia `CStr` Elimina il *valori neutri* 1/1/0001 per la data e 00:00:00 per l'ora.  
  
 Per informazioni dettagliate sui valori restituiti dal `CStr`, vedere [valori restituiti dalla funzione CStr](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).  
  
## <a name="cuint-example"></a>Esempio di CUInt  
 L'esempio seguente usa il `CUInt` funzione per convertire un valore numerico a `UInteger`.  
  
 [!code-vb[VbVbalrFunctions#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#16)]  
  
## <a name="culng-example"></a>Esempio di CULng  
 L'esempio seguente usa il `CULng` funzione per convertire un valore numerico a `ULong`.  
  
 [!code-vb[VbVbalrFunctions#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#17)]  
  
## <a name="cushort-example"></a>Esempio di CUShort  
 L'esempio seguente usa il `CUShort` funzione per convertire un valore numerico a `UShort`.  
  
 [!code-vb[VbVbalrFunctions#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#18)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- <xref:Microsoft.VisualBasic.Strings.Format%2A>
- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:Microsoft.VisualBasic.Conversion.Oct%2A>
- <xref:Microsoft.VisualBasic.Conversion.Str%2A>
- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [Funzioni di conversione](../../../visual-basic/language-reference/functions/conversion-functions.md)
- [Conversioni di tipi in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
