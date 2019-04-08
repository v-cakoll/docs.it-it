---
title: <trace> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace
- http://schemas.microsoft.com/.NetConfiguration/v2.0#trace
helpviewer_keywords:
- <trace> element
- listeners
- trace element
- trace listener, <trace> element
ms.assetid: 7931c942-63c1-47c3-a045-9d9de3cacdbf
ms.openlocfilehash: 5faf352dce2a459a999b3cf54209f6bd9793bde0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59073793"
---
# <a name="trace-element"></a>\<traccia > elemento
Contiene i listener che raccolgono, archiviano e indirizzano i messaggi di traccia.  
  
 \<configuration>  
\<system.diagnostics>  
\<trace>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<trace autoflush="true|false"   
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`autoflush`|Attributo facoltativo.<br /><br /> Specifica se i listener di traccia automaticamente svuotano del buffer di output dopo ogni operazione di scrittura.|  
|`indentsize`|Attributo facoltativo.<br /><br /> Specifica il numero di spazi del rientro.|  
|`useGlobalLock`|Attributo facoltativo.<br /><br /> Indica se il blocco globale deve essere utilizzato.|  
  
## <a name="autoflush-attribute"></a>Attributo AutoFlush  
  
|Value|Descrizione|  
|-----------|-----------------|  
|`false`|Non consente automaticamente di scaricare il buffer di output. Questa è l'impostazione predefinita.|  
|`true`|Scarica automaticamente il buffer di output.|  
  
## <a name="usegloballock-attribute"></a>Attributo useGlobalLock  
  
|Value|Descrizione|  
|-----------|-----------------|  
|`false`|Non utilizzare il blocco globale se il listener è thread-safe. in caso contrario, viene utilizzato il blocco globale.|  
|`true`|Usa il blocco globale indipendentemente dal fatto che il listener è thread-safe. Questa è l'impostazione predefinita.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<listeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|Specifica un listener che raccoglie, archivia e indirizza i messaggi.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`system.diagnostics`|Specifica i listener di traccia per raccogliere, archiviare e indirizzare i messaggi, oltre al livello di impostazione di un'opzione di traccia.|  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare il `<trace>` elemento a cui aggiungere il listener `MyListener` per il `Listeners` raccolta. `MyListener` Crea un file denominato `MyListener.log` e scrive l'output del file. Il `useGlobalLock` attributo è impostato su `false`, in modo che il blocco globale non può essere utilizzato se il listener di traccia è thread-safe. Il `autoflush` attributo è impostato su `true`, in modo che il listener di traccia da scrivere nel file indipendentemente dal fatto che il <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> viene chiamato il metodo. Il `indentsize` attributo è impostato su 0 (zero), che fa sì che il listener per il rientro quando la <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> viene chiamato il metodo.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace useGlobalLock="false" autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [Schema delle impostazioni di traccia e debug](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
