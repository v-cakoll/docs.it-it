---
title: Mapping di funzioni canoniche del modello concettuale a funzioni SQL Server
ms.date: 03/30/2017
ms.assetid: 1a2631bc-a426-4c0a-ba8d-26d9c80d39e2
ms.openlocfilehash: f997fbf39f3dee07cc0d58a39fca779f55236606
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251683"
---
# <a name="conceptual-model-canonical-to-sql-server-functions-mapping"></a>Mapping di funzioni canoniche del modello concettuale a funzioni SQL Server
In questo argomento viene descritto il mapping delle funzioni canoniche del modello concettuale alle corrispondenti funzioni SQL Server.  
  
## <a name="date-and-time-functions"></a>Funzioni data e ora  
 Nella tabella seguente viene descritto il mapping delle funzioni di data e ora:  
  
|Funzioni canoniche|Funzioni SQL Server|  
|-------------------------|--------------------------|  
|[AddDays(expression)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(day, number, date)`|  
|[AddHours(expression)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(hour, number, date)`|  
|[AddMicroseconds(expression)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(microsecond, number, date)`|  
|[AddMilliseconds(expression)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(millisecond, number, date)`|  
|[AddMinutes (espressione)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(minute, number, date)`|  
|[AddMonths(expression)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(month, number, date)`|  
|[AddNanoseconds(expression)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(nanosecond, number, date)`|  
|[AddSeconds (espressione)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(second, number, date)`|  
|[AddYears (espressione)](./language-reference/date-and-time-canonical-functions.md)|`DATEADD(year, number, date)`|  
|[CreateDateTime (anno, mese, giorno, ora, minuto, secondo)](./language-reference/date-and-time-canonical-functions.md)|Per SQL Server 2000 e SQL Server 2005, un valore formattato in `datetime` viene creato nel server. Per SQL Server 2008 e versioni successive, un valore `datetime2` viene creato nel server.|  
|[CreateDateTimeOffset(year, month, day, hour, minute, second, tzoffset)](./language-reference/date-and-time-canonical-functions.md)|Un valore formattato in `datetimeoffset` viene creato nel server.<br /><br /> Non supportata in SQL Server 2000 o SQL Server 2005.|  
|[CreateTime(hour, minute, second)](./language-reference/date-and-time-canonical-functions.md)|Un valore formattato in `time` viene creato nel server.<br /><br /> Non supportata in SQL Server 2000 o SQL Server 2005.|  
|[CurrentDateTime()](./language-reference/date-and-time-canonical-functions.md)|`SysDateTime()` in SQLServer 2008.<br /><br /> `GetDate()` in SQLServer 2000 e in SQLServer 2005.|  
|[CurrentDateTimeOffset()](./language-reference/date-and-time-canonical-functions.md)|`SysDateTimeOffset()` in SQL Server 2008.<br /><br /> Non supportata in SQL Server 2000 o SQL Server 2005.|  
|[CurrentUtcDateTime()](./language-reference/date-and-time-canonical-functions.md)|`SysUtcDateTime()` in SQLServer 2008. `GetUtcDate()` in SQL Server 2000 e in SQL Server 2005.|  
|[DayOfYear (espressione)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(dayofyear, expression)`|  
|[Day (espressione)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(day, expression)`|  
|[DiffDays(startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(day, startdate, enddate)`|  
|[DiffHours(startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(hour, startdate, enddate)`|  
|[DiffMicroseconds(startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(microsecond, startdate, enddate)`|  
|[DiffMilliseconds(startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(millisecond, startdate, enddate)`|  
|[DiffMinutes (startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(minute, startdate, enddate)`|  
|[DiffNanoseconds(startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(nanosecond, startdate, enddate)`|  
|[DiffSeconds (startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(second, startdate, enddate)`|  
|[DiffYears (startExpression, endExpression)](./language-reference/date-and-time-canonical-functions.md)|`DATEDIFF(year, startdate, enddate)`|  
|[GetTotalOffsetMinutes(DateTimeOffset)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(tzoffset, expression)`|  
|[Ora (espressione)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(hour, expression)`|  
|[Millisecondo (espressione)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(millisecond, expression)`|  
|[Minuto (espressione)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(minute, expression)`|  
|[Mese (espressione)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(month, expression)`|  
|[Secondo (espressione)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(second, expression)`|  
|[Truncate (espressione)](./language-reference/date-and-time-canonical-functions.md)|Per SQL Server 2000 e SQL Server 2005, nel server viene `datetime` creato un valore formattato troncato. Per SQL Server 2008 e versioni successive, un valore `datetime2` o `datetimeoffset` troncato viene creato nel server.|  
|[Year (espressione)](./language-reference/date-and-time-canonical-functions.md)|`DatePart(YEAR, expression)`|  
  
## <a name="aggregate-functions"></a>Funzioni di aggregazione  
 Nella tabella seguente viene descritto il mapping delle funzioni di aggregazione:  
  
|Funzioni canoniche|Funzioni SQL Server|  
|-------------------------|--------------------------|  
|[AVG (espressione)](./language-reference/aggregate-canonical-functions.md)|`AVG(expression)`|  
|[BigCount(expression)](./language-reference/aggregate-canonical-functions.md)|`BIGCOUNT(expression)`|  
|[Conteggio (espressione)](./language-reference/aggregate-canonical-functions.md)|`COUNT(expression)`|  
|[Min (espressione)](./language-reference/aggregate-canonical-functions.md)|`MIN(expression)`|  
|[Max (espressione)](./language-reference/aggregate-canonical-functions.md)|`MAX(expression)`|  
|[StDev(expression)](./language-reference/aggregate-canonical-functions.md)|`STDEV(expression)`|  
|[StDevP(expression)](./language-reference/aggregate-canonical-functions.md)|`STDEVP(expression)`|  
|[Sum(expression)](./language-reference/aggregate-canonical-functions.md)|`SUM(expression)`|  
|[Var (espressione)](./language-reference/aggregate-canonical-functions.md)|`VAR(expression)`|  
|[VarP (espressione)](./language-reference/aggregate-canonical-functions.md)|`VARP(expression)`|  
  
## <a name="math-functions"></a>Funzioni matematiche  
 Nella tabella seguente viene descritto il mapping delle funzioni matematiche:  
  
|Funzioni canoniche|Funzioni SQL Server|  
|-------------------------|--------------------------|  
|[Abs(value)](./language-reference/math-canonical-functions.md)|`ABS(value)`|  
|[Ceiling (valore)](./language-reference/math-canonical-functions.md)|`CEILING(value)`|  
|[Floor(value)](./language-reference/math-canonical-functions.md)|`FLOOR(value)`|  
|[Power (valore)](./language-reference/math-canonical-functions.md)|`POWER(value, exponent)`|  
|[Round(value)](./language-reference/math-canonical-functions.md)|`ROUND(value, digits, 0)`|  
|[Troncare](./language-reference/math-canonical-functions.md)|`ROUND(value , digits, 1)`|  
  
## <a name="string-functions"></a>Funzioni stringa  
 Nella tabella seguente viene descritto il mapping delle funzioni di stringa:  
  
|Funzioni canoniche|Funzioni SQL Server|  
|-------------------------|--------------------------|  
|[Contains (String, target)](./language-reference/string-canonical-functions.md)|`CHARINDEX(target, string)`|  
|[Concat(string1, string2)](./language-reference/string-canonical-functions.md)|string1 + string2|  
|[EndsWith(string, target)](./language-reference/string-canonical-functions.md)|`CHARINDEX(REVERSE(target), REVERSE(string)) = 1`<br /><br /> **Nota** La `CHARINDEX` funzione restituisce `false` se l' `string` oggetto viene archiviato in una colonna di stringhe a `target` lunghezza fissa ed è una costante. In questo caso, la ricerca viene eseguita nell'intera stringa, inclusa la spaziatura interna finale. Una possibile soluzione alternativa consiste nel tagliare i dati nella stringa a lunghezza fissa prima di passare la stringa alla funzione `EndsWith`, come nell'esempio seguente: `EndsWith(TRIM(string), target)`|  
|[IndexOf(target, string2)](./language-reference/string-canonical-functions.md)|`CHARINDEX(target, string2)`|  
|[Left (string1, length)](./language-reference/string-canonical-functions.md)|`LEFT(string1, length)`|  
|[Length (stringa)](./language-reference/string-canonical-functions.md)|`LEN(string)`|  
|[LTrim(string)](./language-reference/string-canonical-functions.md)|`LTRIM(string)`|  
|[Right (string1, length)](./language-reference/string-canonical-functions.md)|`RIGHT (string1, length)`|  
|[Trim(string)](./language-reference/string-canonical-functions.md)|`LTRIM(RTRIM(string))`|  
|[Replace (string1, string2, string3)](./language-reference/string-canonical-functions.md)|`REPLACE(string1, string2, string3)`|  
|[Reverse (stringa)](./language-reference/string-canonical-functions.md)|`REVERSE (string)`|  
|[RTrim(string)](./language-reference/string-canonical-functions.md)|`RTRIM(string)`|  
|[StartsWith(string, target)](./language-reference/string-canonical-functions.md)|`CHARINDEX(target, string)`|  
|[Substring (String, Start, length)](./language-reference/string-canonical-functions.md)|`SUBSTRING(string, start, length)`|  
|[ToLower(string)](./language-reference/string-canonical-functions.md)|`LOWER(string)`|  
|[ToUpper(string)](./language-reference/string-canonical-functions.md)|`UPPER(string)`|  
  
## <a name="bitwise-functions"></a>Funzioni bit per bit  
 Nella tabella seguente viene descritto il mapping delle funzioni bit per bit:  
  
|Funzioni canoniche|Funzioni SQL Server|  
|-------------------------|--------------------------|  
|[BitWiseAnd (value1, value2)](./language-reference/bitwise-canonical-functions.md)|value1 & value2|  
|[BitWiseNot (valore)](./language-reference/bitwise-canonical-functions.md)|~value|  
|[BitWiseOr (value1, value2)](./language-reference/bitwise-canonical-functions.md)|value1 &#124; value2|  
|[BitWiseXor (value1, value2)](./language-reference/bitwise-canonical-functions.md)|value1 ^ value2|
