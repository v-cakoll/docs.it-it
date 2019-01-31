---
title: Elemento < NetFx40_PInvokeStackResilience >
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8bc0d7c9222c31900cad9a8be05c79f7f8a04719
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55289341"
---
# <a name="netfx40pinvokestackresilience-element"></a>\<NetFx40_PInvokeStackResilience > elemento
Specifica se il runtime corregge automaticamente le dichiarazioni platform invoke non corrette in fase di esecuzione, al costo di transizioni più lente tra codice gestito e quello non gestito.  
  
 \<configuration>  
\<runtime>  
<NetFx40_PInvokeStackResilience>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<NetFx40_PInvokeStackResilience  enabled="1|0"/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se il runtime rileva piattaforma non corretta richiamare le dichiarazioni e corregge automaticamente lo stack in fase di esecuzione su piattaforme a 32 bit.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`0`|Il runtime Usa introdotto nell'architettura di marshalling di interoperabilità più veloce il [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], che non ne rileva e Correggi dichiarazioni platform invoke errate. Questa è l'impostazione predefinita.|  
|`1`|Dichiarazioni di richiamo il runtime utilizza transizioni più lente che rileva e Correggi piattaforma non corretta.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.|  
  
## <a name="remarks"></a>Note  
 Questo elemento consente di scambiare più veloce il marshalling di interoperabilità per dichiarazioni di richiamo di resilienza in fase di esecuzione per la piattaforma non corretta.  
  
 A partire dal [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], una semplice interoperabilità marshalling architettura fornisce un miglioramento significativo delle prestazioni per le transizioni da codice gestito a codice non gestito. Nelle versioni precedenti di .NET Framework, la piattaforma non corretto a livello rilevato marshalling richiamare le dichiarazioni in piattaforme a 32 bit e corretti automaticamente lo stack. La nuova architettura di marshalling consente di eliminare questo passaggio. Di conseguenza, le transizioni sono molto veloci, ma un platform invoke non corrette dichiarazione possono causare un errore di programma.  
  
 Per renderlo semplice rilevare le dichiarazioni di non corrette durante lo sviluppo, è stata migliorata l'esperienza di debug di Visual Studio. Il [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) assistente al debug gestito (MDA) notifica della piattaforma non corretta invoke dichiarazioni quando l'applicazione viene eseguita con il debugger collegato.  
  
 In questi scenari in cui l'applicazione utilizza componenti che non è possibile ricompilare e che hanno dichiarazioni platform invoke errate, è possibile usare il `NetFx40_PInvokeStackResilience` elemento. Aggiunta di questo elemento per il file di configurazione dell'applicazione con `enabled="1"` opts in una modalità di compatibilità con il comportamento delle versioni precedenti di .NET Framework, al costo di transizioni più lente. Gli assembly che sono stati compilati con versioni precedenti di .NET Framework vengono scelti automaticamente in questa modalità di compatibilità e non sono necessario questo elemento.  
  
## <a name="configuration-file"></a>File di configurazione  
 Questo elemento può essere usato solo nel file di configurazione dell'applicazione.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra la modalità per acconsentire esplicitamente aumentare la resilienza contro errato dichiarazioni platform invoke per un'applicazione, al costo di transizioni più lente tra codice gestito e.  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_PInvokeStackResilience enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche
- [Schema delle impostazioni di runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Schema dei file di configurazione](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)
