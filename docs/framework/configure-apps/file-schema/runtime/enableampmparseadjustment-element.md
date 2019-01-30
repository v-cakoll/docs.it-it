---
title: <EnableAmPmParseAdjustment> Elemento
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b3316184aaa624fffdd18f472a7f3a709b42045a
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269211"
---
# <a name="enableampmparseadjustment-element"></a>\<EnableAmPmParseAdjustment > elemento
Determina se analisi dell'ora e i metodi utilizzano un set di regole adattato per analizzare le stringhe di data che contengono un giorno, mese, ora e indicazione AM/PM.  
  
 \<configuration>  
 \<runtime>  
\<EnableAmPmParseAdjustment>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se analisi dell'ora e i metodi utilizzano un set di regole adattato per analizzare le stringhe di data che contengono solo un giorno, mese, ora e indicazione AM/PM.|  
  
### <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|0|Data e ora i metodi di analisi non usare regole adattate per l'analisi di stringhe di data che contengono solo un giorno, mese, ora e indicazione AM/PM.|  
|1|Data e ora i metodi di analisi usano regole adattate per l'analisi di stringhe di data che contengono solo un giorno, mese, ora e indicazione AM/PM.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.|  
  
## <a name="remarks"></a>Note  
 Il `<EnableAmPmParseAdjustment>` elemento controlla come i metodi seguenti analizzano una stringa di data che contiene un valore numerico del giorno e mese seguita da un'ora e un indicatore AM/PM (ad esempio "4/10 6 AM"):  
  
-   <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 Altri modelli non sono interessate.  
  
 Il `<EnableAmPmParseAdjustment>` elemento non ha alcun effetto sul <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, e <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> metodi.  
  
> [!IMPORTANT]
>  In .NET Core e .NET Native, le regole di analisi AM/PM adattate sono abilitate per impostazione predefinita.  
  
 Se non è abilitata la regola di rettifica analisi, la prima cifra della stringa viene interpretata come l'ora dell'orologio di 12 ore e il resto della stringa tranne l'indicatore AM/PM viene ignorato. Data e ora restituito dal metodo di analisi costituito la data corrente e l'ora del giorno estratto dalla stringa di Data.  
  
 Se è abilitata la regola di rettifica analisi, metodo di analisi di interpretare il giorno e mese come appartenente all'anno corrente e interpretare l'ora come l'ora dell'orologio di 12 ore.  
  
 Nella tabella seguente viene illustrata la differenza tra il <xref:System.DateTime> valore quando il <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> metodo viene utilizzato per analizzare la stringa "" 4/10 6 AM"con il `<EnableAmPmParseAdjustment>` dell'elemento `enabled` proprietà è impostata su"0"o"1". Si presuppone che data odierna è 5 gennaio 2017 e Visualizza la data come se viene formattato con stringa di formato "G" della cultura specificata.  
  
|Nome delle impostazioni cultura|enabled="0"|enabled="1"|  
|------------------|------------------|------------------|  
|en-US|1 O 5/2017:00 4:00|4/10/2017:00 6:00|  
|en-GB|5/1/2017 6:00:00|10/4/2017 6:00:00|  
  
## <a name="see-also"></a>Vedere anche
- [\<runtime > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)
- [Elemento \<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)
