---
title: '&lt;EnableAmPmParseAdjustment&gt; elemento'
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b17f521be31fa4082d9418c7dad734e37994bbb5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltenableampmparseadjustmentgt-element"></a>&lt;EnableAmPmParseAdjustment&gt; elemento
Determina se data e ora di metodi di analisi utilizzare un set di regole adattato per analizzare le stringhe di data che contengono un giorno, mese, ora e indicatore AM/PM.  
  
 \<configuration>  
 \<runtime>  
\<EnableAmPmParseAdjustment >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se data e ora di metodi di analisi usare un set di regole adattato per analizzare le stringhe di data che contengono solo un giorno, mese, ora e indicatore AM/PM.|  
  
### <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|0|Data e ora di metodi di analisi non utilizzano regole adattate per l'analisi di stringhe di data che contengono solo un giorno, mese, ora e indicatore AM/PM.|  
|1|Data e ora di metodi di analisi utilizzare regole adattate per l'analisi di stringhe di data che contengono solo un giorno, mese, ora e indicatore AM/PM.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.|  
  
## <a name="remarks"></a>Note  
 Il `<EnableAmPmParseAdjustment>` elemento determina come i metodi seguenti analizzano una stringa di data che contiene un valore numerico del giorno e mese seguita da un'ora e un indicatore AM/PM (ad esempio "4/10 6 AM"):  
  
-   <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 Altri schemi non sono interessate.  
  
 Il `<EnableAmPmParseAdjustment>` elemento non ha alcun effetto <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, e <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> metodi.  
  
> [!IMPORTANT]
>  In .NET Core e .NET Native, le regole di analisi di AM/PM rettificate sono abilitate per impostazione predefinita.  
  
 Se la regola di rettifica analisi non è abilitata, la prima cifra della stringa viene interpretata come l'ora dell'orologio di 12 ore e il resto della stringa, ad eccezione di indicatore AM/PM viene ignorato. Data e ora restituito dal metodo di analisi costituito dalla data corrente e l'ora del giorno estratto dalla stringa di Data.  
  
 Se è abilitata la regola di rettifica analisi, l'analisi del metodo interpretare il giorno e mese come appartenente all'anno corrente e interpretare l'ora come ora dell'orologio di 12 ore.  
  
 Nella tabella seguente viene illustrata la differenza di <xref:System.DateTime> valore quando il <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> metodo viene utilizzato per analizzare la stringa "" 4/10 6 AM"con il `<EnableAmPmParseAdjustment>` dell'elemento `enabled` proprietà è impostata su"0"o"1". Si presuppone che data è il 5 gennaio January 2017 e Visualizza la data come se viene formattato con una stringa di formato "G" le impostazioni cultura specificate.  
  
|Nome delle impostazioni cultura|attivato = "0"|attivato = "1"|  
|------------------|------------------|------------------|  
|it-IT|5/1/2017 4:00:00 AM|10/4/2017 6:00:00 AM|  
|en-GB|5/1/2017 6:00:00|10/4/2017 6:00:00|  
  
## <a name="see-also"></a>Vedere anche  
 [\<runtime > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)  
 [Elemento \<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)
