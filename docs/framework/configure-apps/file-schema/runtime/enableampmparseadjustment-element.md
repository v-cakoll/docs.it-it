---
title: <EnableAmPmParseAdjustment> Elemento
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
ms.openlocfilehash: 8920e51fcaaca5cb78b80a99ea321163c9b5240f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73117364"
---
# <a name="enableampmparseadjustment-element"></a>\<elemento > EnableAmPmParseAdjustment
Determina se i metodi di analisi di data e ora usano un set di regole modificato per analizzare le stringhe di data contenenti un indicatore giorno, mese, ora e AM/PM.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp;&nbsp;&nbsp;&nbsp; **\<EnableAmPmParseAdjustment >**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se i metodi di analisi di data e ora usano un set di regole modificato per analizzare le stringhe di data che contengono solo il giorno, il mese, l'ora e l'indicatore AM/PM.|  
  
### <a name="enabled-attribute"></a>Attributo enabled  
  
|Value|Descrizione|  
|-----------|-----------------|  
|0|I metodi di analisi di data e ora non utilizzano regole regolate per l'analisi delle stringhe di data che contengono solo il giorno, il mese, l'ora e l'indicatore AM/PM.|  
|1|I metodi di analisi di data e ora usano regole regolate per l'analisi delle stringhe di data che contengono solo il giorno, il mese, l'ora e l'indicatore AM/PM.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuna.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.|  
  
## <a name="remarks"></a>Note  
 L'elemento `<EnableAmPmParseAdjustment>` controlla il modo in cui i metodi seguenti analizzano una stringa di data contenente un giorno e un mese numerici seguiti da un'ora e un indicatore AM/PM (ad esempio "4/10 6 AM"):  
  
- <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 Nessun altro modello è interessato.  
  
 L'elemento `<EnableAmPmParseAdjustment>` non ha alcun effetto sui metodi <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>e <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType>.  
  
> [!IMPORTANT]
> In .NET Core e .NET Native le regole di analisi AM/PM modificate sono abilitate per impostazione predefinita.  
  
 Se la regola di regolazione dell'analisi non è abilitata, la prima cifra della stringa viene interpretata come ora del formato a 12 ore e il resto della stringa, ad eccezione dell'indicatore AM/PM, viene ignorato. La data e l'ora restituite dal metodo di analisi sono costituite dalla data corrente e dall'ora del giorno estratta dalla stringa di data.  
  
 Se la regola di regolazione dell'analisi è abilitata, il metodo di analisi interpreta il giorno e il mese come appartenente all'anno corrente e interpreta l'ora come ora del formato a 12 ore.  
  
 Nella tabella seguente viene illustrata la differenza nel valore <xref:System.DateTime> quando viene utilizzato il metodo <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> per analizzare la stringa "" 4/10 6 AM "con la proprietà `enabled` dell'elemento `<EnableAmPmParseAdjustment>` impostata su" 0 "o" 1 ". Si presuppone che la data odierna sia il 5 gennaio 2017 e visualizzi la data come se fosse formattata usando la stringa di formato "G" delle impostazioni cultura specificate.  
  
|Nome delle impostazioni cultura|Enabled = "0"|Enabled = "1"|  
|------------------|------------------|------------------|  
|en-US|1/5/2017 4:00:00 AM|4/10/2017 6:00:00 AM|  
|en-GB|5/1/2017 6:00:00|10/4/2017 6:00:00|  
  
## <a name="see-also"></a>Vedere anche

- [\<elemento > Runtime](runtime-element.md)
- [Elemento \<configuration>](../configuration-element.md)
