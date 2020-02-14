---
title: dateTimeInvalidLocalFormat (MDA)
ms.date: 03/30/2017
helpviewer_keywords:
- dates [.NET Framework], formatting
- invalid date time local format
- invalid local formats
- MDAs (managed debugging assistants), invalid local formats
- managed debugging assistants (MDAs), invalid local formats
- dateTimeInvalidLocalFormat MDA
- date formatting
- time formatting
- UTC formatting
ms.assetid: c4a942bb-2651-4b65-8718-809f892a0659
ms.openlocfilehash: 2fdace8a9c7bcc090fd801be3bd717e4a2b34a87
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217542"
---
# <a name="datetimeinvalidlocalformat-mda"></a>dateTimeInvalidLocalFormat (MDA)
L'assistente al debug gestito `dateTimeInvalidLocalFormat` viene attivato quando per la formattazione di un'istanza di <xref:System.DateTime> archiviata in formato UTC (Universal Coordinated Time) viene usato un formato riservato alle istanze locali di <xref:System.DateTime>. Questo assistente non viene attivato per le istanze di <xref:System.DateTime> non specificate o predefinite.  
  
## <a name="symptom"></a>Sintomo  
 Un'applicazione sta serializzando manualmente un'istanza di <xref:System.DateTime> in formato UTC usando un formato locale:  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("yyyy-MM-dd'T'HH:mm:ss.fffffffzzz"));  
```  
  
### <a name="cause"></a>Causa  
 Il formato 'z' del metodo <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> include l'offset del fuso orario locale, ad esempio "+10:00" per l'ora di Sydney. Di conseguenza, verrà generato un risultato significativo solo se il valore di <xref:System.DateTime> è locale. Se il valore è in formato UTC, <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> include l'offset del fuso orario locale, ma non visualizza né modifica l'identificatore del fuso orario.  
  
### <a name="resolution"></a>Risoluzione  
 Le istanze di <xref:System.DateTime> in formato UTC devono essere formattate in modo che vengano identificate come UTC. Per indicare un'ora in formato UTC è consigliabile usare una 'Z':  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("yyyy-MM-dd'T'HH:mm:ss.fffffffZ"));  
```  
  
 Esiste anche un formato "o" che serializza un'istanza di <xref:System.DateTime> usando la proprietà <xref:System.DateTime.Kind%2A> che viene serializzata correttamente indipendentemente dal fatto che l'istanza sia in formato locale, UTC o non specificato:  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("o"));  
```  
  
## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione  
 Questo assistente al debug gestito non ha alcun effetto sul runtime.  
  
## <a name="output"></a>Output  
 L'attivazione di questo assistente al debug gestito non genera alcun output specifico. È possibile, tuttavia, usare lo stack di chiamate per determinare la posizione della chiamata <xref:System.DateTime.ToString%2A> che ha attivato l'assistente.  
  
## <a name="configuration"></a>Configurazione  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dateTimeInvalidLocalFormat />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Esempio  
 Si consideri ad esempio un'applicazione che stia serializzando indirettamente un valore <xref:System.DateTime> UTC tramite la classe <xref:System.Xml.XmlConvert> o <xref:System.Data.DataSet>, come descritto di seguito.  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
String serialized = XMLConvert.ToString(myDateTime);  
```  
  
 Per impostazione predefinita, <xref:System.Xml.XmlConvert> e <xref:System.Data.DataSet> usano formati locali per la serializzazione. Per serializzare altri tipi di valori <xref:System.DateTime>, ad esempio UTC, sono necessarie opzioni aggiuntive.  
  
 Per questo esempio specifico, passare `XmlDateTimeSerializationMode.RoundtripKind` alla chiamata `ToString` su `XmlConvert`. In questo modo i dati vengono serializzati come ora UTC.  
  
 Se si usa <xref:System.Data.DataSet>, impostare la proprietà <xref:System.Data.DataColumn.DateTimeMode%2A> dell'oggetto <xref:System.Data.DataColumn> su <xref:System.Data.DataSetDateTime.Utc>.  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
String serialized = XmlConvert.ToString(myDateTime,   
    XmlDateTimeSerializationMode.RoundtripKind);  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Globalization.DateTimeFormatInfo>
- [Diagnostica degli errori tramite gli assistenti al debug gestito](diagnosing-errors-with-managed-debugging-assistants.md)
